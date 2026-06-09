# CAutoVerifierPlugin::GetOriginalBucket(HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140049df4`
- end: `0x140049efa`
- name: `?GetOriginalBucket@CAutoVerifierPlugin@@AEAAJPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14004a590`

## callees

- `0x140002470`
- `0x14000c8a0`
- `0x140049df4`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140049ed4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140049ed4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140049e75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140049e75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140049e37`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140049e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049e4a`

## string_xrefs

- `0x140049e30`: `werdiagcontroller.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoVerifierPlugin::GetOriginalBucket(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v6; // rcx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  signed int LastError; // eax
  signed int v10; // ebx
  FARPROC ProcAddress; // rax
  __int64 v12; // r8
  _WORD v14[256]; // [rsp+40h] [rbp-238h] BYREF

  v6 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  *v6 = 0;
  Library = LoadLibraryExW(L"werdiagcontroller.dll", 0, 0);
  v8 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "QueryOriginalBucket")) != 0 )
  {
    v10 = ((__int64 (__fastcall *)(_QWORD, __int64, _WORD *, __int64))ProcAddress)(*(_QWORD *)(a1 + 784), a2, v14, 256);
    if ( v10 >= 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v14[v12] );
      v10 = (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a3,
                               v14,
                               v12) == 0
          ? 0x8007000E
          : 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
  }
  if ( v8 )
    FreeLibrary(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140049df4  push    rbx
0x140049df6  push    rbp
0x140049df7  push    rsi
0x140049df8  push    rdi
0x140049df9  push    r14
0x140049dfb  sub     rsp, 250h
0x140049e02  mov     rax, cs:__security_cookie
0x140049e09  xor     rax, rsp
0x140049e0c  mov     [rsp+278h+var_38], rax
0x140049e14  mov     rsi, r8
0x140049e17  mov     rbp, rdx
0x140049e1a  mov     rbx, rcx
0x140049e1d  mov     rcx, [r8]
0x140049e20  mov     [r8+8], rcx
0x140049e24  xor     r14d, r14d
0x140049e27  mov     [rcx], r14w
0x140049e2b  xor     r8d, r8d; dwFlags
0x140049e2e  xor     edx, edx; hFile
0x140049e30  lea     rcx, aWerdiagcontrol; "werdiagcontroller.dll"
0x140049e37  call    cs:__imp_LoadLibraryExW
0x140049e3d  mov     rdi, rax
0x140049e40  mov     [rsp+278h+var_248], rax
0x140049e45  test    rax, rax
0x140049e48  jnz     short loc_140049E6B
0x140049e4a  call    cs:__imp_GetLastError
0x140049e50  mov     ebx, eax
0x140049e52  test    eax, eax
0x140049e54  jle     short loc_140049E5F
0x140049e56  movzx   ebx, ax
0x140049e59  or      ebx, 80070000h
0x140049e5f  mov     eax, 80004005h
0x140049e64  test    ebx, ebx
0x140049e66  cmovns  ebx, eax
0x140049e69  jmp     short loc_140049ECC
0x140049e6b  lea     rdx, aQueryoriginalb; "QueryOriginalBucket"
0x140049e72  mov     rcx, rdi; hModule
0x140049e75  call    cs:__imp_GetProcAddress
0x140049e7b  test    rax, rax
0x140049e7e  jz      short loc_140049E4A
0x140049e80  mov     r9d, 100h
0x140049e86  lea     r8, [rsp+278h+var_238]
0x140049e8b  mov     rdx, rbp
0x140049e8e  mov     rcx, [rbx+310h]
0x140049e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049e9a  mov     ebx, eax
0x140049e9c  test    eax, eax
0x140049e9e  js      short loc_140049ECC
0x140049ea0  lea     rax, [rsp+278h+var_238]
0x140049ea5  or      r8, 0FFFFFFFFFFFFFFFFh
0x140049ea9  inc     r8
0x140049eac  cmp     [rax+r8*2], r14w
0x140049eb1  jnz     short loc_140049EA9
0x140049eb3  lea     rdx, [rsp+278h+var_238]
0x140049eb8  mov     rcx, rsi
0x140049ebb  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140049ec0  neg     al
0x140049ec2  sbb     ebx, ebx
0x140049ec4  not     ebx
0x140049ec6  and     ebx, 8007000Eh
0x140049ecc  test    rdi, rdi
0x140049ecf  jz      short loc_140049EDA
0x140049ed1  mov     rcx, rdi; hLibModule
0x140049ed4  call    cs:__imp_FreeLibrary
0x140049eda  mov     eax, ebx
0x140049edc  mov     rcx, [rsp+278h+var_38]
0x140049ee4  xor     rcx, rsp; StackCookie
0x140049ee7  call    __security_check_cookie
0x140049eec  add     rsp, 250h
0x140049ef3  pop     r14
0x140049ef5  pop     rdi
0x140049ef6  pop     rsi
0x140049ef7  pop     rbp
0x140049ef8  pop     rbx
0x140049ef9  retn
```
