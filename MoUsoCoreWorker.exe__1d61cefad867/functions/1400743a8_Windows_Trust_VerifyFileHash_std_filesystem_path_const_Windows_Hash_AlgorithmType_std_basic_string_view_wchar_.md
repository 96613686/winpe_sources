# Windows::Trust::VerifyFileHash(std::filesystem::path const &,Windows::Hash::AlgorithmType,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1400743a8`
- end: `0x1400745c6`
- name: `?VerifyFileHash@Trust@Windows@@YA_NAEBVpath@filesystem@std@@W4AlgorithmType@Hash@2@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `542`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1401a6ff8`
- `0x140354bc4`

## callees

- `0x14003c578`
- `0x1400413a8`
- `0x140045404`
- `0x1400454a0`
- `0x1400743a8`
- `0x140075300`
- `0x1400753a4`
- `0x14007563c`
- `0x140075bdc`
- `0x140379070`
- `0x14037f840`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400744e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400744e8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140074485`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140074485`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140074439`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140074439`
- `bcrypt!BCryptHashData` at `0x1400744a9`
- `bcrypt!BCryptHashData` at `0x1400744a9`

## string_xrefs

- `0x1400745b1`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x14007456c`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`
- `0x140074584`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`
- `0x140074596`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Windows::Trust::VerifyFileHash(const WCHAR *a1, __int64 a2, __m128i *a3)
{
  bool v4; // di
  char v5; // al
  char *FileW; // rbx
  const char *v7; // r9
  NTSTATUS v8; // eax
  const wchar_t *v9; // rdx
  wchar_t *v10; // xmm0_8
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *S2[4]; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm[6]; // [rsp+70h] [rbp-90h] BYREF
  UCHAR Buffer[4096]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10C8h] [rbp+FC8h]

  v4 = 0;
  if ( !*((_QWORD *)a1 + 2) || (v5 = 0, !a3->m128i_i64[1]) )
    v5 = 1;
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  if ( !*((_QWORD *)a1 + 2) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  memset(Buffer, 0, sizeof(Buffer));
  anonymous_namespace_::StartHash(phAlgorithm);
  while ( 1 )
  {
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, Buffer, 0x1000u, &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x86,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
        v7);
    if ( !NumberOfBytesRead )
      break;
    v8 = BCryptHashData(phAlgorithm[1], Buffer, NumberOfBytesRead, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x8D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
        (const char *)(unsigned int)v8,
        dwCreationDispositiona);
  }
  anonymous_namespace_::FinishHash(S2, phAlgorithm);
  anonymous_namespace_::HashWrapper::_HashWrapper(phAlgorithm);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  v9 = (const wchar_t *)S2;
  if ( S2[3] > (wchar_t *)7 )
    v9 = S2[0];
  v10 = (wchar_t *)_mm_srli_si128(*a3, 8).m128i_u64[0];
  if ( v10 == S2[2] )
  {
    if ( v10 )
      v4 = wmemcmp((const wchar_t *)a3->m128i_i64[0], v9, (size_t)v10) == 0;
    else
      v4 = 1;
  }
  std::wstring::~wstring(S2, v9);
  return v4;
}

```

## disassembly

```asm
0x1400743a8  mov     [rsp-8+arg_8], rbx
0x1400743ad  mov     [rsp-8+arg_18], rsi
0x1400743b2  push    rbp
0x1400743b3  push    rdi
0x1400743b4  push    r14
0x1400743b6  lea     rbp, [rsp-0FB0h]
0x1400743be  mov     eax, 10B0h
0x1400743c3  call    _alloca_probe
0x1400743c8  sub     rsp, rax
0x1400743cb  mov     rax, cs:__security_cookie
0x1400743d2  xor     rax, rsp
0x1400743d5  mov     [rbp+0FC0h+var_20], rax
0x1400743dc  mov     r14, r8
0x1400743df  xor     edi, edi
0x1400743e1  cmp     [rcx+10h], rdi
0x1400743e5  jz      short loc_1400743F0
0x1400743e7  cmp     [r8+8], rdi
0x1400743eb  mov     al, dil
0x1400743ee  jnz     short loc_1400743F2
0x1400743f0  mov     al, 1
0x1400743f2  mov     r10, [rbp+0FC8h]
0x1400743f9  test    al, al
0x1400743fb  jnz     loc_1400745AB
0x140074401  mov     rax, [rbp+0FC8h]
0x140074408  cmp     [rcx+10h], rdi
0x14007440c  jz      loc_140074566
0x140074412  cmp     qword ptr [rcx+18h], 7
0x140074417  jbe     short loc_14007441C
0x140074419  mov     rcx, [rcx]; lpFileName
0x14007441c  mov     [rsp+10C0h+hTemplateFile], rdi; hTemplateFile
0x140074421  mov     [rsp+10C0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x140074425  mov     [rsp+10C0h+dwCreationDisposition], 3; dwCreationDisposition
0x14007442d  xor     r9d, r9d; lpSecurityAttributes
0x140074430  mov     edx, 80000000h; dwDesiredAccess
0x140074435  lea     r8d, [r9+1]; dwShareMode
0x140074439  call    cs:__imp_CreateFileW
0x14007443f  mov     rbx, rax
0x140074442  mov     [rsp+10C0h+var_1080], rax
0x140074447  xor     edx, edx; Val
0x140074449  mov     r8d, 1000h; Size
0x14007444f  lea     rcx, [rbp+0FC0h+Buffer]; void *
0x140074453  call    memset
0x140074458  lea     rcx, [rsp+10C0h+phAlgorithm]; phAlgorithm
0x14007445d  call    _anonymous_namespace___StartHash
0x140074462  nop
0x140074463  mov     [rsp+10C0h+NumberOfBytesRead], edi
0x140074467  mov     rsi, [rbp+0FC8h]
0x14007446e  mov     qword ptr [rsp+10C0h+dwCreationDisposition], rdi; int
0x140074473  lea     r9, [rsp+10C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140074478  mov     r8d, 1000h; nNumberOfBytesToRead
0x14007447e  lea     rdx, [rbp+0FC0h+Buffer]; lpBuffer
0x140074482  mov     rcx, rbx; hFile
0x140074485  call    cs:__imp_ReadFile
0x14007448b  test    eax, eax
0x14007448d  jz      loc_140074596
0x140074493  mov     r8d, [rsp+10C0h+NumberOfBytesRead]; cbInput
0x140074498  test    r8d, r8d
0x14007449b  jz      short loc_1400744C0
0x14007449d  xor     r9d, r9d; dwFlags
0x1400744a0  lea     rdx, [rbp+0FC0h+Buffer]; pbInput
0x1400744a4  mov     rcx, [rsp+10C0h+hHash]; hHash
0x1400744a9  call    cs:__imp_BCryptHashData
0x1400744af  mov     rcx, [rbp+0FC8h]; this
0x1400744b6  test    eax, eax
0x1400744b8  js      loc_140074581
0x1400744be  jmp     short loc_140074463
0x1400744c0  lea     rdx, [rsp+10C0h+phAlgorithm]
0x1400744c5  lea     rcx, [rsp+10C0h+S2]
0x1400744ca  call    _anonymous_namespace___FinishHash
0x1400744cf  nop
0x1400744d0  lea     rcx, [rsp+10C0h+phAlgorithm]
0x1400744d5  call    _anonymous_namespace___HashWrapper___HashWrapper
0x1400744da  nop
0x1400744db  lea     rax, [rbx-1]
0x1400744df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400744e3  ja      short loc_1400744EE
0x1400744e5  mov     rcx, rbx; hObject
0x1400744e8  call    cs:__imp_CloseHandle
0x1400744ee  lea     rdx, [rsp+10C0h+S2]
0x1400744f3  cmp     [rsp+10C0h+var_1058], 7
0x1400744f9  cmova   rdx, [rsp+10C0h+S2]; S2
0x1400744ff  movaps  xmm1, xmmword ptr [r14]
0x140074503  movdqa  xmm0, xmm1
0x140074507  psrldq  xmm0, 8
0x14007450c  movq    r8, xmm0; N
0x140074511  cmp     r8, [rsp+10C0h+var_1060]
0x140074516  jnz     short loc_140074532
0x140074518  test    r8, r8
0x14007451b  jnz     short loc_140074522
0x14007451d  mov     dil, 1
0x140074520  jmp     short loc_140074532
0x140074522  movq    rcx, xmm1; S1
0x140074527  call    wmemcmp
0x14007452c  test    eax, eax
0x14007452e  setz    dil
0x140074532  lea     rcx, [rsp+10C0h+S2]
0x140074537  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14007453c  mov     al, dil
0x14007453f  mov     rcx, [rbp+0FC0h+var_20]
0x140074546  xor     rcx, rsp; StackCookie
0x140074549  call    __security_check_cookie
0x14007454e  lea     r11, [rsp+10C0h+var_10]
0x140074556  mov     rbx, [r11+28h]
0x14007455a  mov     rsi, [r11+38h]
0x14007455e  mov     rsp, r11
0x140074561  pop     r14
0x140074563  pop     rdi
0x140074564  pop     rbp
0x140074565  retn
0x140074566  mov     r9d, 80070057h; char *
0x14007456c  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140074573  mov     edx, 7Bh ; '{'; void *
0x140074578  mov     rcx, rax; this
0x14007457b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140074581  mov     r9d, eax; char *
0x140074584  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14007458b  mov     edx, 8Dh; void *
0x140074590  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140074596  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14007459d  mov     edx, 86h; void *
0x1400745a2  mov     rcx, rsi; this
0x1400745a5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400745ab  mov     r9d, 80070057h; char *
0x1400745b1  lea     r8, aCW1SSrcOrchest_114; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1400745b8  mov     edx, 0E6h; void *
0x1400745bd  mov     rcx, r10; this
0x1400745c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
