# Windows::Trust::IsUMCIEnabled(void)

- ea: `0x180062ac0`
- end: `0x180062b91`
- name: `?IsUMCIEnabled@Trust@Windows@@YA_NXZ`
- size: `209`
- prototype: `bool __fastcall(Windows::Trust *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800728a0`

## callees

- `0x180062ac0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180062b11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180062b11`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180062b6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180062b6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180062aed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180062aed`

## string_xrefs

- `0x180062ae6`: `WLDP.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Trust::IsUMCIEnabled(Windows::Trust *this)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  bool v3; // si
  FARPROC ProcAddress; // rax
  char v5; // di
  _DWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF
  __int128 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+40h] [rbp-18h] BYREF

  Library = LoadLibraryExW(L"WLDP.DLL", 0, 0x800u);
  v2 = Library;
  v3 = Library != 0;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "WldpGetLockdownPolicy")) == 0
    || (v5 = 1,
        v7[0] = 1,
        v7[1] = 1,
        v8 = 0,
        v9 = 0,
        ((int (__fastcall *)(_DWORD *, int *, _QWORD))ProcAddress)(v7, &v9, 0) < 0)
    || (v9 & 0x80000004) == 0x80000000 )
  {
    v5 = 0;
  }
  if ( v3 )
    FreeLibrary(v2);
  return v5;
}

```

## disassembly

```asm
0x180062ac0  mov     [rsp+arg_0], rbx
0x180062ac5  mov     [rsp+arg_8], rsi
0x180062aca  push    rdi
0x180062acb  sub     rsp, 50h
0x180062acf  mov     rax, cs:__security_cookie
0x180062ad6  xor     rax, rsp
0x180062ad9  mov     [rsp+58h+var_10], rax
0x180062ade  xor     edx, edx; hFile
0x180062ae0  mov     r8d, 800h; dwFlags
0x180062ae6  lea     rcx, aWldpDll; "WLDP.DLL"
0x180062aed  call    cs:__imp_LoadLibraryExW
0x180062af3  mov     rbx, rax
0x180062af6  mov     [rsp+58h+var_38], rax
0x180062afb  test    rax, rax
0x180062afe  setnz   sil
0x180062b02  test    rax, rax
0x180062b05  jz      short loc_180062B60
0x180062b07  lea     rdx, aWldpgetlockdow; "WldpGetLockdownPolicy"
0x180062b0e  mov     rcx, rax; hModule
0x180062b11  call    cs:__imp_GetProcAddress
0x180062b17  test    rax, rax
0x180062b1a  jz      short loc_180062B60
0x180062b1c  mov     edi, 1
0x180062b21  mov     [rsp+58h+var_30], edi
0x180062b25  mov     [rsp+58h+var_2C], edi
0x180062b29  xorps   xmm0, xmm0
0x180062b2c  movdqu  [rsp+58h+var_28], xmm0
0x180062b32  mov     [rsp+58h+var_18], 0
0x180062b3a  xor     r8d, r8d
0x180062b3d  lea     rdx, [rsp+58h+var_18]
0x180062b42  lea     rcx, [rsp+58h+var_30]
0x180062b47  call    _guard_dispatch_icall
0x180062b4c  test    eax, eax
0x180062b4e  js      short loc_180062B60
0x180062b50  mov     eax, [rsp+58h+var_18]
0x180062b54  and     eax, 80000004h
0x180062b59  cmp     eax, 80000000h
0x180062b5e  jnz     short loc_180062B63
0x180062b60  xor     dil, dil
0x180062b63  test    sil, sil
0x180062b66  jz      short loc_180062B71
0x180062b68  mov     rcx, rbx; hLibModule
0x180062b6b  call    cs:__imp_FreeLibrary
0x180062b71  mov     al, dil
0x180062b74  mov     rcx, [rsp+58h+var_10]
0x180062b79  xor     rcx, rsp; StackCookie
0x180062b7c  call    __security_check_cookie
0x180062b81  mov     rbx, [rsp+58h+arg_0]
0x180062b86  mov     rsi, [rsp+58h+arg_8]
0x180062b8b  add     rsp, 50h
0x180062b8f  pop     rdi
0x180062b90  retn
```
