# CModelDownloadComponent::ValidateModelFilesList(ushort const *)

- ea: `0x140012998`
- end: `0x140012b62`
- name: `?ValidateModelFilesList@CModelDownloadComponent@@CAJPEBG@Z`
- size: `458`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d5a4`
- `0x1400127e4`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x14000985c`
- `0x140012998`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140012a07`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x140012a07`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x140012a93`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x140012a93`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012b30`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x140012b30`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x140012ac9`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x140012ac9`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140012a5e`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140012abe`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140012a5e`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140012abe`

## string_xrefs

- `0x140012b0c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2178)`
- `0x140012a22`: `CModelDownloadComponent::ValidateModelFilesList`
- `0x140012af1`: `CModelDownloadComponent::ValidateModelFilesList`
- `0x140012a13`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2185)`
- `0x140012a6a`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2190)`
- `0x140012ae0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2200)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::ValidateModelFilesList(wchar_t *FileName)
{
  errno_t v2; // edi
  const wchar_t *v3; // rax
  int v4; // ebx
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  struct _stat64i32 Stat; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v9; // [rsp+280h] [rbp+180h]

  memset_0(Buffer, 0, 0x218u);
  Stream = 0;
  if ( !FileName || !*FileName )
  {
    v4 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::ValidateModelFilesList",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2178)",
      -2147024809);
    v2 = (int)Stream;
    goto LABEL_17;
  }
  v2 = _wfopen_s(&Stream, FileName, L"rb");
  if ( v2 )
  {
    v3 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2185)";
LABEL_5:
    v4 = -2147024891;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::ValidateModelFilesList",
      v3,
      -2147024891);
    goto LABEL_17;
  }
  if ( fread(Buffer, 0x218u, 1u, Stream) != 1 )
  {
    v3 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2190)";
    goto LABEL_5;
  }
  v4 = 0;
  while ( !feof(Stream) )
  {
    memset(&Stat, 0, sizeof(Stat));
    v2 = _wstat64i32(Buffer, &Stat);
    if ( v2 || Stat.st_mtime != v9 )
    {
      v4 = -2147024809;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::ValidateModelFilesList",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2200)",
        -2147024809);
      break;
    }
    fread(Buffer, 0x218u, (unsigned int)(v2 + 1), Stream);
  }
LABEL_17:
  if ( Stream )
    fclose(Stream);
  if ( v2 || v4 < 0 )
    return (unsigned int)-2147024891;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140012998  push    rbp
0x14001299a  push    rbx
0x14001299b  push    rsi
0x14001299c  push    rdi
0x14001299d  push    r14
0x14001299f  push    r15
0x1400129a1  lea     rbp, [rsp-1A8h]
0x1400129a9  sub     rsp, 2A8h
0x1400129b0  mov     rax, cs:__security_cookie
0x1400129b7  xor     rax, rsp
0x1400129ba  mov     [rbp+1D0h+var_40], rax
0x1400129c1  mov     rbx, rcx
0x1400129c4  mov     r15d, 218h
0x1400129ca  mov     r8d, r15d; Size
0x1400129cd  lea     rcx, [rsp+2D0h+Buffer]; void *
0x1400129d2  xor     edx, edx; Val
0x1400129d4  call    memset_0
0x1400129d9  xor     esi, esi
0x1400129db  mov     r14d, 80070005h
0x1400129e1  mov     [rsp+2D0h+Stream], rsi
0x1400129e6  test    rbx, rbx
0x1400129e9  jz      loc_140012AEC
0x1400129ef  cmp     [rbx], si
0x1400129f2  jz      loc_140012AEC
0x1400129f8  lea     r8, aRb; "rb"
0x1400129ff  mov     rdx, rbx; FileName
0x140012a02  lea     rcx, [rsp+2D0h+Stream]; Stream
0x140012a07  call    cs:__imp__wfopen_s
0x140012a0d  mov     edi, eax
0x140012a0f  test    eax, eax
0x140012a11  jz      short loc_140012A4B
0x140012a13  lea     rax, aOnecoreuapEndu_63; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012a1a  mov     [rsp+2D0h+var_2A8], r14d
0x140012a1f  mov     ebx, r14d
0x140012a22  lea     r9, aCmodeldownload_7; "CModelDownloadComponent::ValidateModelF"...
0x140012a29  mov     [rsp+2D0h+var_2B0], rax
0x140012a2e  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x140012a35  mov     ecx, 2; int
0x140012a3a  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x140012a41  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140012a46  jmp     loc_140012B26
0x140012a4b  mov     r9, [rsp+2D0h+Stream]; Stream
0x140012a50  lea     rcx, [rsp+2D0h+Buffer]; Buffer
0x140012a55  mov     r8d, 1; ElementCount
0x140012a5b  mov     rdx, r15; ElementSize
0x140012a5e  call    cs:__imp_fread
0x140012a64  cmp     rax, 1
0x140012a68  jz      short loc_140012A73
0x140012a6a  lea     rax, aOnecoreuapEndu_43; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012a71  jmp     short loc_140012A1A
0x140012a73  mov     ebx, esi
0x140012a75  jmp     short loc_140012AC4
0x140012a77  xorps   xmm0, xmm0
0x140012a7a  lea     rdx, [rsp+2D0h+Stat]; Stat
0x140012a7f  lea     rcx, [rsp+2D0h+Buffer]; FileName
0x140012a84  movups  xmmword ptr [rsp+2D0h+Stat.st_dev], xmm0
0x140012a89  movups  xmmword ptr [rsp+2D0h+Stat.st_rdev], xmm0
0x140012a8e  movups  xmmword ptr [rsp+2D0h+Stat.st_mtime], xmm0
0x140012a93  call    cs:__imp__wstat64i32
0x140012a99  mov     edi, eax
0x140012a9b  test    eax, eax
0x140012a9d  jnz     short loc_140012AD5
0x140012a9f  mov     rax, [rbp+1D0h+var_50]
0x140012aa6  cmp     [rsp+2D0h+Stat.st_mtime], rax
0x140012aab  jnz     short loc_140012AD5
0x140012aad  mov     r9, [rsp+2D0h+Stream]; Stream
0x140012ab2  lea     r8d, [rdi+1]; ElementCount
0x140012ab6  mov     rdx, r15; ElementSize
0x140012ab9  lea     rcx, [rsp+2D0h+Buffer]; Buffer
0x140012abe  call    cs:__imp_fread
0x140012ac4  mov     rcx, [rsp+2D0h+Stream]; Stream
0x140012ac9  call    cs:__imp_feof
0x140012acf  test    eax, eax
0x140012ad1  jz      short loc_140012A77
0x140012ad3  jmp     short loc_140012B26
0x140012ad5  mov     eax, 80070057h
0x140012ada  mov     ebx, eax
0x140012adc  mov     [rsp+2D0h+var_2A8], eax
0x140012ae0  lea     rax, aOnecoreuapEndu_167; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012ae7  jmp     loc_140012A22
0x140012aec  mov     eax, 80070057h
0x140012af1  lea     r9, aCmodeldownload_7; "CModelDownloadComponent::ValidateModelF"...
0x140012af8  mov     [rsp+2D0h+var_2A8], eax
0x140012afc  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x140012b03  mov     ebx, eax
0x140012b05  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x140012b0c  lea     rax, aOnecoreuapEndu_71; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x140012b13  mov     ecx, 2; int
0x140012b18  mov     [rsp+2D0h+var_2B0], rax
0x140012b1d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140012b22  mov     edi, dword ptr [rsp+2D0h+Stream]
0x140012b26  mov     rcx, [rsp+2D0h+Stream]; Stream
0x140012b2b  test    rcx, rcx
0x140012b2e  jz      short loc_140012B36
0x140012b30  call    cs:__imp_fclose
0x140012b36  test    edi, edi
0x140012b38  jnz     short loc_140012B3E
0x140012b3a  test    ebx, ebx
0x140012b3c  jns     short loc_140012B41
0x140012b3e  mov     ebx, r14d
0x140012b41  mov     eax, ebx
0x140012b43  mov     rcx, [rbp+1D0h+var_40]
0x140012b4a  xor     rcx, rsp; StackCookie
0x140012b4d  call    __security_check_cookie
0x140012b52  add     rsp, 2A8h
0x140012b59  pop     r15
0x140012b5b  pop     r14
0x140012b5d  pop     rdi
0x140012b5e  pop     rsi
0x140012b5f  pop     rbx
0x140012b60  pop     rbp
0x140012b61  retn
```
