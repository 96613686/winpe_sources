# IsDomainJoined(void)

- ea: `0x14000e9a0`
- end: `0x14000eb0a`
- name: `?IsDomainJoined@@YA_NXZ`
- size: `362`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000e590`

## callees

- `0x14000a390`
- `0x14000e9a0`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000e9ee`
- `KERNEL32!GetProcAddress` at `0x14000ea01`
- `KERNEL32!GetProcAddress` at `0x14000ea6e`
- `KERNEL32!GetProcAddress` at `0x14000ea81`
- `KERNEL32!GetProcAddress` at `0x14000e9ee`
- `KERNEL32!GetProcAddress` at `0x14000ea01`
- `KERNEL32!GetProcAddress` at `0x14000ea6e`
- `KERNEL32!GetProcAddress` at `0x14000ea81`
- `KERNEL32!FreeLibrary` at `0x14000ea54`
- `KERNEL32!FreeLibrary` at `0x14000eae0`
- `KERNEL32!FreeLibrary` at `0x14000ea54`
- `KERNEL32!FreeLibrary` at `0x14000eae0`
- `KERNEL32!LoadLibraryExW` at `0x14000e9d2`
- `KERNEL32!LoadLibraryExW` at `0x14000e9d2`

## string_xrefs

- `0x14000e9c5`: `netapi32.dll`

## pseudocode

```c
bool IsDomainJoined(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rdi
  FARPROC ProcAddress; // rsi
  FARPROC v3; // rax
  void (__fastcall *v4)(_QWORD); // rbx
  FARPROC v5; // rbx
  FARPROC v6; // rax
  void (*v7)(void); // rbp
  char v8; // bl
  char v9; // si
  _DWORD *v11; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+28h] [rbp-20h] BYREF

  Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
  v1 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NetGetJoinInformation");
    v3 = GetProcAddress(v1, "NetApiBufferFree");
    v4 = (void (__fastcall *)(_QWORD))v3;
    if ( ProcAddress
      && v3
      && (v11 = 0, v12 = 0, !((unsigned int (__fastcall *)(_QWORD, _DWORD **, int *))ProcAddress)(0, &v11, &v12))
      && (v4(v11), v12 == 3) )
    {
      FreeLibrary(v1);
      LOBYTE(Library) = 1;
    }
    else
    {
      v5 = GetProcAddress(v1, "NetGetAadJoinInformation");
      v6 = GetProcAddress(v1, "NetFreeAadJoinInformation");
      v7 = (void (*)(void))v6;
      if ( !v5
        || !v6
        || (v11 = 0, ((unsigned int (__fastcall *)(_QWORD, _DWORD **))v5)(0, &v11))
        || !v11
        || ((v8 = 1, *v11 == 1) || *v11 == 2 ? (v9 = 1) : (v9 = 0), v7(), !v9) )
      {
        v8 = 0;
      }
      FreeLibrary(v1);
      LOBYTE(Library) = v8;
    }
  }
  return (char)Library;
}

```

## disassembly

```asm
0x14000e9a0  mov     [rsp+arg_0], rbx
0x14000e9a5  mov     [rsp+arg_8], rbp
0x14000e9aa  mov     [rsp+arg_10], rsi
0x14000e9af  push    rdi
0x14000e9b0  sub     rsp, 40h
0x14000e9b4  mov     rax, cs:__security_cookie
0x14000e9bb  xor     rax, rsp
0x14000e9be  mov     [rsp+48h+var_18], rax
0x14000e9c3  xor     edx, edx; hFile
0x14000e9c5  lea     rcx, LibFileName; "netapi32.dll"
0x14000e9cc  mov     r8d, 800h; dwFlags
0x14000e9d2  call    cs:__imp_LoadLibraryExW
0x14000e9d8  mov     rdi, rax
0x14000e9db  test    rax, rax
0x14000e9de  jz      loc_14000EAE8
0x14000e9e4  lea     rdx, aNetgetjoininfo; "NetGetJoinInformation"
0x14000e9eb  mov     rcx, rdi; hModule
0x14000e9ee  call    cs:__imp_GetProcAddress
0x14000e9f4  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x14000e9fb  mov     rcx, rdi; hModule
0x14000e9fe  mov     rsi, rax
0x14000ea01  call    cs:__imp_GetProcAddress
0x14000ea07  mov     rbx, rax
0x14000ea0a  test    rsi, rsi
0x14000ea0d  jz      short loc_14000EA64
0x14000ea0f  test    rax, rax
0x14000ea12  jz      short loc_14000EA64
0x14000ea14  lea     r8, [rsp+48h+var_20]
0x14000ea19  mov     [rsp+48h+var_28], 0
0x14000ea22  lea     rdx, [rsp+48h+var_28]
0x14000ea27  mov     [rsp+48h+var_20], 0
0x14000ea2f  xor     ecx, ecx
0x14000ea31  mov     rax, rsi
0x14000ea34  call    _guard_dispatch_icall
0x14000ea39  test    eax, eax
0x14000ea3b  jnz     short loc_14000EA64
0x14000ea3d  mov     rcx, [rsp+48h+var_28]
0x14000ea42  mov     rax, rbx
0x14000ea45  call    _guard_dispatch_icall
0x14000ea4a  cmp     [rsp+48h+var_20], 3
0x14000ea4f  jnz     short loc_14000EA64
0x14000ea51  mov     rcx, rdi; hLibModule
0x14000ea54  call    cs:__imp_FreeLibrary
0x14000ea5a  mov     eax, 1
0x14000ea5f  jmp     loc_14000EAE8
0x14000ea64  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x14000ea6b  mov     rcx, rdi; hModule
0x14000ea6e  call    cs:__imp_GetProcAddress
0x14000ea74  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x14000ea7b  mov     rcx, rdi; hModule
0x14000ea7e  mov     rbx, rax
0x14000ea81  call    cs:__imp_GetProcAddress
0x14000ea87  mov     rbp, rax
0x14000ea8a  test    rbx, rbx
0x14000ea8d  jz      short loc_14000EADB
0x14000ea8f  test    rax, rax
0x14000ea92  jz      short loc_14000EADB
0x14000ea94  lea     rdx, [rsp+48h+var_28]
0x14000ea99  mov     [rsp+48h+var_28], 0
0x14000eaa2  xor     ecx, ecx
0x14000eaa4  mov     rax, rbx
0x14000eaa7  call    _guard_dispatch_icall
0x14000eaac  test    eax, eax
0x14000eaae  jnz     short loc_14000EADB
0x14000eab0  mov     rcx, [rsp+48h+var_28]
0x14000eab5  test    rcx, rcx
0x14000eab8  jz      short loc_14000EADB
0x14000eaba  lea     ebx, [rax+1]
0x14000eabd  cmp     [rcx], ebx
0x14000eabf  jz      short loc_14000EACB
0x14000eac1  cmp     dword ptr [rcx], 2
0x14000eac4  jz      short loc_14000EACB
0x14000eac6  xor     sil, sil
0x14000eac9  jmp     short loc_14000EACE
0x14000eacb  mov     sil, bl
0x14000eace  mov     rax, rbp
0x14000ead1  call    _guard_dispatch_icall
0x14000ead6  test    sil, sil
0x14000ead9  jnz     short loc_14000EADD
0x14000eadb  xor     bl, bl
0x14000eadd  mov     rcx, rdi; hLibModule
0x14000eae0  call    cs:__imp_FreeLibrary
0x14000eae6  mov     al, bl
0x14000eae8  mov     rcx, [rsp+48h+var_18]
0x14000eaed  xor     rcx, rsp; StackCookie
0x14000eaf0  call    __security_check_cookie
0x14000eaf5  mov     rbx, [rsp+48h+arg_0]
0x14000eafa  mov     rbp, [rsp+48h+arg_8]
0x14000eaff  mov     rsi, [rsp+48h+arg_10]
0x14000eb04  add     rsp, 40h
0x14000eb08  pop     rdi
0x14000eb09  retn
```
