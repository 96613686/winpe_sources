# CModelDownloadComponent::UpdateModelCurrentVersion(void)

- ea: `0x1400125f0`
- end: `0x1400127dc`
- name: `?UpdateModelCurrentVersion@CModelDownloadComponent@@AEAAJXZ`
- size: `492`
- prototype: `__int64 __fastcall(const wchar_t *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14000d5a4`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x14000985c`
- `0x1400125f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140012672`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140012672`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x1400126da`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x1400126da`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012798`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012798`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14001272e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14001272e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140012707`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140012707`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400127ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400127ad`

## string_xrefs

- `0x140012756`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2245)`
- `0x140012690`: `CModelDownloadComponent::UpdateModelCurrentVersion`
- `0x140012766`: `CModelDownloadComponent::UpdateModelCurrentVersion`
- `0x140012689`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2252)`
- `0x1400126f1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2260)`
- `0x140012745`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2268)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::UpdateModelCurrentVersion(const wchar_t *this)
{
  errno_t v2; // esi
  int v3; // edi
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  struct _stat64i32 Stat; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v7[528]; // [rsp+70h] [rbp-90h] BYREF
  __time64_t st_mtime; // [rsp+280h] [rbp+180h]

  memset_0(v7, 0, 0x218u);
  Stream = 0;
  if ( *((_QWORD *)this + 3074) && this[3676] && *((int *)this + 6150) > 0 )
  {
    v2 = _wfopen_s(&Stream, this + 3676, L"wb");
    if ( v2 )
    {
      v3 = -2147024891;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::UpdateModelCurrentVersion",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2252)",
        -2147024891);
    }
    else
    {
      memset(&Stat, 0, sizeof(Stat));
      v2 = _wstat64i32(this + 3415, &Stat);
      if ( v2 )
      {
        v3 = -2147024891;
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::UpdateModelCurrentVersion",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2260)",
          -2147024891);
      }
      else
      {
        _o_wcscpy_s(v7, 260, this + 3415);
        st_mtime = Stat.st_mtime;
        if ( _o_fwrite(v7, 536, 1, Stream) == 1 )
        {
          v3 = 0;
        }
        else
        {
          v3 = -2147024891;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::UpdateModelCurrentVersion",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2268)",
            -2147024891);
        }
      }
    }
  }
  else
  {
    v3 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::UpdateModelCurrentVersion",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2245)",
      -2147024809);
    v2 = (int)Stream;
  }
  if ( Stream )
    fclose(Stream);
  if ( v2 || v3 < 0 )
    DeleteFileW(this + 3676);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400125f0  mov     [rsp-8+arg_8], rbx
0x1400125f5  mov     [rsp-8+arg_10], rsi
0x1400125fa  push    rbp
0x1400125fb  push    rdi
0x1400125fc  push    r14
0x1400125fe  lea     rbp, [rsp-1A0h]
0x140012606  sub     rsp, 2A0h
0x14001260d  mov     rax, cs:__security_cookie
0x140012614  xor     rax, rsp
0x140012617  mov     [rbp+1B0h+var_20], rax
0x14001261e  mov     rbx, rcx
0x140012621  xor     edx, edx; Val
0x140012623  lea     rcx, [rsp+2B0h+var_240]; void *
0x140012628  mov     r8d, 218h; Size
0x14001262e  call    memset_0
0x140012633  xor     r14d, r14d
0x140012636  mov     [rsp+2B0h+Stream], r14
0x14001263b  cmp     [rbx+6010h], r14
0x140012642  jz      loc_140012756
0x140012648  lea     rdx, [rbx+1CB8h]; FileName
0x14001264f  cmp     [rdx], r14w
0x140012653  jz      loc_140012756
0x140012659  cmp     [rbx+6018h], r14d
0x140012660  jle     loc_140012756
0x140012666  lea     r8, aWb; "wb"
0x14001266d  lea     rcx, [rsp+2B0h+Stream]; Stream
0x140012672  call    cs:__imp__wfopen_s
0x140012678  mov     esi, eax
0x14001267a  test    eax, eax
0x14001267c  jz      short loc_1400126B9
0x14001267e  mov     eax, 80070005h
0x140012683  mov     edi, eax
0x140012685  mov     [rsp+2B0h+var_288], eax
0x140012689  lea     rax, aOnecoreuapEndu_58; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012690  lea     r9, aCmodeldownload_4; "CModelDownloadComponent::UpdateModelCur"...
0x140012697  mov     [rsp+2B0h+var_290], rax
0x14001269c  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1400126a3  mov     ecx, 2; int
0x1400126a8  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1400126af  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1400126b4  jmp     loc_14001278E
0x1400126b9  xorps   xmm0, xmm0
0x1400126bc  lea     rdi, [rbx+1AAEh]
0x1400126c3  mov     rcx, rdi; FileName
0x1400126c6  lea     rdx, [rsp+2B0h+Stat]; Stat
0x1400126cb  movups  xmmword ptr [rsp+2B0h+Stat.st_dev], xmm0
0x1400126d0  movups  xmmword ptr [rsp+2B0h+Stat.st_rdev], xmm0
0x1400126d5  movups  xmmword ptr [rsp+2B0h+Stat.st_mtime], xmm0
0x1400126da  call    cs:__imp__wstat64i32
0x1400126e0  mov     esi, eax
0x1400126e2  test    eax, eax
0x1400126e4  jz      short loc_1400126FA
0x1400126e6  mov     eax, 80070005h
0x1400126eb  mov     edi, eax
0x1400126ed  mov     [rsp+2B0h+var_288], eax
0x1400126f1  lea     rax, aOnecoreuapEndu_135; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1400126f8  jmp     short loc_140012690
0x1400126fa  mov     r8, rdi
0x1400126fd  lea     rcx, [rsp+2B0h+var_240]
0x140012702  mov     edx, 104h
0x140012707  call    cs:__imp__o_wcscpy_s
0x14001270d  mov     rax, [rsp+2B0h+Stat.st_mtime]
0x140012712  lea     rcx, [rsp+2B0h+var_240]
0x140012717  mov     r9, [rsp+2B0h+Stream]
0x14001271c  mov     edx, 218h
0x140012721  mov     r8d, 1
0x140012727  mov     [rbp+1B0h+var_30], rax
0x14001272e  call    cs:__imp__o_fwrite
0x140012734  cmp     rax, 1
0x140012738  jz      short loc_140012751
0x14001273a  mov     eax, 80070005h
0x14001273f  mov     edi, eax
0x140012741  mov     [rsp+2B0h+var_288], eax
0x140012745  lea     rax, aOnecoreuapEndu_8; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14001274c  jmp     loc_140012690
0x140012751  mov     edi, r14d
0x140012754  jmp     short loc_14001278E
0x140012756  lea     rax, aOnecoreuapEndu_118; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14001275d  mov     edi, 80070057h
0x140012762  mov     [rsp+2B0h+var_288], edi
0x140012766  lea     r9, aCmodeldownload_4; "CModelDownloadComponent::UpdateModelCur"...
0x14001276d  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x140012774  mov     [rsp+2B0h+var_290], rax
0x140012779  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x140012780  mov     ecx, 2; int
0x140012785  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001278a  mov     esi, dword ptr [rsp+2B0h+Stream]
0x14001278e  mov     rcx, [rsp+2B0h+Stream]; Stream
0x140012793  test    rcx, rcx
0x140012796  jz      short loc_14001279E
0x140012798  call    cs:__imp_fclose
0x14001279e  test    esi, esi
0x1400127a0  jnz     short loc_1400127A6
0x1400127a2  test    edi, edi
0x1400127a4  jns     short loc_1400127B3
0x1400127a6  lea     rcx, [rbx+1CB8h]; lpFileName
0x1400127ad  call    cs:__imp_DeleteFileW
0x1400127b3  mov     eax, edi
0x1400127b5  mov     rcx, [rbp+1B0h+var_20]
0x1400127bc  xor     rcx, rsp; StackCookie
0x1400127bf  call    __security_check_cookie
0x1400127c4  lea     r11, [rsp+2B0h+var_10]
0x1400127cc  mov     rbx, [r11+28h]
0x1400127d0  mov     rsi, [r11+30h]
0x1400127d4  mov     rsp, r11
0x1400127d7  pop     r14
0x1400127d9  pop     rdi
0x1400127da  pop     rbp
0x1400127db  retn
```
