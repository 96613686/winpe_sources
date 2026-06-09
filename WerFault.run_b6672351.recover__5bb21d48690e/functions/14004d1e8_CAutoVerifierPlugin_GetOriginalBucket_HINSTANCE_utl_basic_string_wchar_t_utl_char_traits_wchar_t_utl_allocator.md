# CAutoVerifierPlugin::GetOriginalBucket(HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x14004d1e8`
- end: `0x14004d307`
- name: `?GetOriginalBucket@CAutoVerifierPlugin@@AEAAJPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14004d9bc`

## callees

- `0x140002490`
- `0x14000ca20`
- `0x14004d1e8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004d2da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004d2da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004d275`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004d275`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004d22b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004d22b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d244`

## string_xrefs

- `0x14004d224`: `werdiagcontroller.dll`

## pseudocode

```c
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
                               v14) == 0
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
0x14004d1e8  push    rbx
0x14004d1ea  push    rbp
0x14004d1eb  push    rsi
0x14004d1ec  push    rdi
0x14004d1ed  push    r14
0x14004d1ef  sub     rsp, 250h
0x14004d1f6  mov     rax, cs:__security_cookie
0x14004d1fd  xor     rax, rsp
0x14004d200  mov     [rsp+278h+var_38], rax
0x14004d208  mov     rsi, r8
0x14004d20b  mov     rbp, rdx
0x14004d20e  mov     rbx, rcx
0x14004d211  mov     rcx, [r8]
0x14004d214  mov     [r8+8], rcx
0x14004d218  xor     r14d, r14d
0x14004d21b  mov     [rcx], r14w
0x14004d21f  xor     r8d, r8d; dwFlags
0x14004d222  xor     edx, edx; hFile
0x14004d224  lea     rcx, aWerdiagcontrol; "werdiagcontroller.dll"
0x14004d22b  call    cs:__imp_LoadLibraryExW
0x14004d232  nop     dword ptr [rax+rax+00h]
0x14004d237  mov     rdi, rax
0x14004d23a  mov     [rsp+278h+var_248], rax
0x14004d23f  test    rax, rax
0x14004d242  jnz     short loc_14004D26B
0x14004d244  call    cs:__imp_GetLastError
0x14004d24b  nop     dword ptr [rax+rax+00h]
0x14004d250  mov     ebx, eax
0x14004d252  test    eax, eax
0x14004d254  jle     short loc_14004D25F
0x14004d256  movzx   ebx, ax
0x14004d259  or      ebx, 80070000h
0x14004d25f  mov     eax, 80004005h
0x14004d264  test    ebx, ebx
0x14004d266  cmovns  ebx, eax
0x14004d269  jmp     short loc_14004D2D2
0x14004d26b  lea     rdx, aQueryoriginalb; "QueryOriginalBucket"
0x14004d272  mov     rcx, rdi; hModule
0x14004d275  call    cs:__imp_GetProcAddress
0x14004d27c  nop     dword ptr [rax+rax+00h]
0x14004d281  test    rax, rax
0x14004d284  jz      short loc_14004D244
0x14004d286  mov     r9d, 100h
0x14004d28c  lea     r8, [rsp+278h+var_238]
0x14004d291  mov     rdx, rbp
0x14004d294  mov     rcx, [rbx+310h]
0x14004d29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d2a0  mov     ebx, eax
0x14004d2a2  test    eax, eax
0x14004d2a4  js      short loc_14004D2D2
0x14004d2a6  lea     rax, [rsp+278h+var_238]
0x14004d2ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004d2af  inc     r8
0x14004d2b2  cmp     [rax+r8*2], r14w
0x14004d2b7  jnz     short loc_14004D2AF
0x14004d2b9  lea     rdx, [rsp+278h+var_238]
0x14004d2be  mov     rcx, rsi
0x14004d2c1  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004d2c6  neg     al
0x14004d2c8  sbb     ebx, ebx
0x14004d2ca  not     ebx
0x14004d2cc  and     ebx, 8007000Eh
0x14004d2d2  test    rdi, rdi
0x14004d2d5  jz      short loc_14004D2E6
0x14004d2d7  mov     rcx, rdi; hLibModule
0x14004d2da  call    cs:__imp_FreeLibrary
0x14004d2e1  nop     dword ptr [rax+rax+00h]
0x14004d2e6  mov     eax, ebx
0x14004d2e8  mov     rcx, [rsp+278h+var_38]
0x14004d2f0  xor     rcx, rsp; StackCookie
0x14004d2f3  call    __security_check_cookie
0x14004d2f8  add     rsp, 250h
0x14004d2ff  pop     r14
0x14004d301  pop     rdi
0x14004d302  pop     rsi
0x14004d303  pop     rbp
0x14004d304  pop     rbx
0x14004d305  retn
```
