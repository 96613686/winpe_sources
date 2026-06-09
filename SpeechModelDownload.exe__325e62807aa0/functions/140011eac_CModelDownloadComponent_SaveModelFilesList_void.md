# CModelDownloadComponent::SaveModelFilesList(void)

- ea: `0x140011eac`
- end: `0x1400120b8`
- name: `?SaveModelFilesList@CModelDownloadComponent@@AEAAJXZ`
- size: `524`
- prototype: `__int64 __fastcall(const wchar_t *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d5a4`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x14000985c`
- `0x140011eac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140011f30`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140011f30`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x140011fb4`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x140011fb4`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14001207b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14001207b`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140011ffb`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140011ffb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140011fd4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140011fd4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001208d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001208d`

## string_xrefs

- `0x140012031`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2112)`
- `0x140011f49`: `CModelDownloadComponent::SaveModelFilesList`
- `0x140012041`: `CModelDownloadComponent::SaveModelFilesList`
- `0x140011f3d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2119)`
- `0x140012025`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2129)`
- `0x140012019`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2137)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::SaveModelFilesList(const wchar_t *this)
{
  const WCHAR *v2; // rsi
  errno_t v3; // r15d
  const wchar_t *v4; // rax
  int v5; // edi
  int v6; // r14d
  __int64 v7; // rcx
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  _stat64i32 Stat; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[528]; // [rsp+70h] [rbp-90h] BYREF
  __time64_t st_mtime; // [rsp+280h] [rbp+180h]

  memset_0(v11, 0, 0x218u);
  Stream = 0;
  if ( *((_QWORD *)this + 3074) && (v2 = this + 3415, this[3415]) && *((int *)this + 6150) > 0 )
  {
    v3 = _wfopen_s(&Stream, this + 3415, L"wb");
    if ( v3 )
    {
      v4 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2119)";
LABEL_6:
      v5 = -2147024891;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::SaveModelFilesList",
        v4,
        -2147024891);
      goto LABEL_15;
    }
    v5 = 0;
    v6 = 0;
    if ( *((int *)this + 6150) > 0 )
    {
      while ( 1 )
      {
        v7 = *((_QWORD *)this + 3074);
        memset(&Stat, 0, sizeof(Stat));
        if ( _wstat64i32(*(const wchar_t **)(v7 + 16LL * v6 + 8), &Stat) )
          break;
        _o_wcscpy_s(v11, 260, *(_QWORD *)(*((_QWORD *)this + 3074) + 16LL * v6 + 8));
        st_mtime = Stat.st_mtime;
        if ( _o_fwrite(v11, 536, 1, Stream) != 1 )
        {
          v4 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2137)";
          goto LABEL_6;
        }
        if ( ++v6 >= *((_DWORD *)this + 6150) )
          goto LABEL_15;
      }
      v4 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2129)";
      goto LABEL_6;
    }
  }
  else
  {
    v5 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::SaveModelFilesList",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2112)",
      -2147024809);
    v3 = (int)Stream;
    v2 = this + 3415;
  }
LABEL_15:
  if ( Stream )
    fclose(Stream);
  if ( v3 || v5 < 0 )
    DeleteFileW(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140011eac  push    rbp
0x140011eae  push    rbx
0x140011eaf  push    rsi
0x140011eb0  push    rdi
0x140011eb1  push    r12
0x140011eb3  push    r13
0x140011eb5  push    r14
0x140011eb7  push    r15
0x140011eb9  lea     rbp, [rsp-1A8h]
0x140011ec1  sub     rsp, 2A8h
0x140011ec8  mov     rax, cs:__security_cookie
0x140011ecf  xor     rax, rsp
0x140011ed2  mov     [rbp+1E0h+var_50], rax
0x140011ed9  mov     rbx, rcx
0x140011edc  xor     edx, edx; Val
0x140011ede  lea     rcx, [rsp+2E0h+var_270]; void *
0x140011ee3  mov     r8d, 218h; Size
0x140011ee9  call    memset_0
0x140011eee  xor     r13d, r13d
0x140011ef1  mov     [rsp+2E0h+Stream], r13
0x140011ef6  cmp     [rbx+6010h], r13
0x140011efd  jz      loc_140012031
0x140011f03  lea     rsi, [rbx+1AAEh]
0x140011f0a  cmp     [rsi], r13w
0x140011f0e  jz      loc_140012031
0x140011f14  cmp     [rbx+6018h], r13d
0x140011f1b  jle     loc_140012031
0x140011f21  lea     r8, aWb; "wb"
0x140011f28  mov     rdx, rsi; FileName
0x140011f2b  lea     rcx, [rsp+2E0h+Stream]; Stream
0x140011f30  call    cs:__imp__wfopen_s
0x140011f36  mov     r15d, eax
0x140011f39  test    eax, eax
0x140011f3b  jz      short loc_140011F78
0x140011f3d  lea     rax, aOnecoreuapEndu_153; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140011f44  mov     ecx, 80070005h
0x140011f49  lea     r9, aCmodeldownload_25; "CModelDownloadComponent::SaveModelFiles"...
0x140011f50  mov     [rsp+2E0h+var_2B8], ecx
0x140011f54  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x140011f5b  mov     edi, ecx
0x140011f5d  mov     [rsp+2E0h+var_2C0], rax
0x140011f62  mov     ecx, 2; int
0x140011f67  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x140011f6e  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140011f73  jmp     loc_140012071
0x140011f78  mov     edi, r13d
0x140011f7b  mov     r14d, r13d
0x140011f7e  cmp     [rbx+6018h], r13d
0x140011f85  jle     loc_140012071
0x140011f8b  mov     rcx, [rbx+6010h]
0x140011f92  lea     rdx, [rsp+2E0h+Stat]; Stat
0x140011f97  xorps   xmm0, xmm0
0x140011f9a  movsxd  r12, r14d
0x140011f9d  movups  xmmword ptr [rsp+2E0h+Stat.st_dev], xmm0
0x140011fa2  add     r12, r12
0x140011fa5  movups  xmmword ptr [rsp+2E0h+Stat.st_rdev], xmm0
0x140011faa  movups  xmmword ptr [rsp+2E0h+Stat.st_mtime], xmm0
0x140011faf  mov     rcx, [rcx+r12*8+8]; FileName
0x140011fb4  call    cs:__imp__wstat64i32
0x140011fba  test    eax, eax
0x140011fbc  jnz     short loc_140012025
0x140011fbe  mov     r8, [rbx+6010h]
0x140011fc5  lea     rcx, [rsp+2E0h+var_270]
0x140011fca  mov     edx, 104h
0x140011fcf  mov     r8, [r8+r12*8+8]
0x140011fd4  call    cs:__imp__o_wcscpy_s
0x140011fda  mov     rax, [rsp+2E0h+Stat.st_mtime]
0x140011fdf  lea     rcx, [rsp+2E0h+var_270]
0x140011fe4  mov     r9, [rsp+2E0h+Stream]
0x140011fe9  mov     edx, 218h
0x140011fee  mov     r8d, 1
0x140011ff4  mov     [rbp+1E0h+var_60], rax
0x140011ffb  call    cs:__imp__o_fwrite
0x140012001  cmp     rax, 1
0x140012005  jnz     short loc_140012019
0x140012007  inc     r14d
0x14001200a  cmp     r14d, [rbx+6018h]
0x140012011  jl      loc_140011F8B
0x140012017  jmp     short loc_140012071
0x140012019  lea     rax, aOnecoreuapEndu_105; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012020  jmp     loc_140011F44
0x140012025  lea     rax, aOnecoreuapEndu_22; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14001202c  jmp     loc_140011F44
0x140012031  lea     rax, aOnecoreuapEndu_140; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012038  mov     edi, 80070057h
0x14001203d  mov     [rsp+2E0h+var_2B8], edi
0x140012041  lea     r9, aCmodeldownload_25; "CModelDownloadComponent::SaveModelFiles"...
0x140012048  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001204f  mov     [rsp+2E0h+var_2C0], rax
0x140012054  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001205b  mov     ecx, 2; int
0x140012060  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140012065  mov     r15d, dword ptr [rsp+2E0h+Stream]
0x14001206a  lea     rsi, [rbx+1AAEh]
0x140012071  mov     rcx, [rsp+2E0h+Stream]; Stream
0x140012076  test    rcx, rcx
0x140012079  jz      short loc_140012081
0x14001207b  call    cs:__imp_fclose
0x140012081  test    r15d, r15d
0x140012084  jnz     short loc_14001208A
0x140012086  test    edi, edi
0x140012088  jns     short loc_140012093
0x14001208a  mov     rcx, rsi; lpFileName
0x14001208d  call    cs:__imp_DeleteFileW
0x140012093  mov     eax, edi
0x140012095  mov     rcx, [rbp+1E0h+var_50]
0x14001209c  xor     rcx, rsp; StackCookie
0x14001209f  call    __security_check_cookie
0x1400120a4  add     rsp, 2A8h
0x1400120ab  pop     r15
0x1400120ad  pop     r14
0x1400120af  pop     r13
0x1400120b1  pop     r12
0x1400120b3  pop     rdi
0x1400120b4  pop     rsi
0x1400120b5  pop     rbx
0x1400120b6  pop     rbp
0x1400120b7  retn
```
