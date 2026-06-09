# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x18000a4c0`
- end: `0x18000a5b4`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a814`

## callees

- `0x18000a4c0`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18000a4db`
- `KERNEL32!EncodePointer` at `0x18000a51f`
- `KERNEL32!EncodePointer` at `0x18000a544`
- `KERNEL32!EncodePointer` at `0x18000a569`
- `KERNEL32!EncodePointer` at `0x18000a58e`
- `KERNEL32!EncodePointer` at `0x18000a51f`
- `KERNEL32!EncodePointer` at `0x18000a544`
- `KERNEL32!EncodePointer` at `0x18000a569`
- `KERNEL32!EncodePointer` at `0x18000a58e`
- `KERNEL32!LoadLibraryExA` at `0x18000a4f1`
- `KERNEL32!LoadLibraryExA` at `0x18000a4f1`
- `KERNEL32!GetProcAddress` at `0x18000a50d`
- `KERNEL32!GetProcAddress` at `0x18000a536`
- `KERNEL32!GetProcAddress` at `0x18000a55b`
- `KERNEL32!GetProcAddress` at `0x18000a580`
- `KERNEL32!GetProcAddress` at `0x18000a50d`
- `KERNEL32!GetProcAddress` at `0x18000a536`
- `KERNEL32!GetProcAddress` at `0x18000a55b`
- `KERNEL32!GetProcAddress` at `0x18000a580`

## string_xrefs

- `0x18000a4e4`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180013A28 )
    return DecodePointer((PVOID)qword_180013A20);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AtlThunk_AllocateData");
    if ( ProcAddress )
    {
      qword_180013A30 = (__int64)EncodePointer(ProcAddress);
      v4 = GetProcAddress(v2, "AtlThunk_InitData");
      if ( v4 )
      {
        qword_180013A20 = (__int64)EncodePointer(v4);
        v5 = GetProcAddress(v2, "AtlThunk_DataToCode");
        if ( v5 )
        {
          qword_180013A18 = (__int64)EncodePointer(v5);
          v6 = GetProcAddress(v2, "AtlThunk_FreeData");
          if ( v6 )
          {
            qword_180013A10 = (__int64)EncodePointer(v6);
            _InterlockedOr(v7, 0);
            byte_180013A28 = 1;
            return DecodePointer((PVOID)qword_180013A20);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a4c0  push    rbx
0x18000a4c2  sub     rsp, 20h
0x18000a4c6  cmp     cs:byte_180013A28, 0
0x18000a4cd  jz      short loc_18000A4E2
0x18000a4cf  mov     rcx, cs:qword_180013A20
0x18000a4d6  add     rsp, 20h
0x18000a4da  pop     rbx
0x18000a4db  jmp     cs:__imp_DecodePointer
0x18000a4e2  xor     edx, edx; hFile
0x18000a4e4  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000a4eb  mov     r8d, 800h; dwFlags
0x18000a4f1  call    cs:__imp_LoadLibraryExA
0x18000a4f7  mov     rbx, rax
0x18000a4fa  test    rax, rax
0x18000a4fd  jz      loc_18000A5AC
0x18000a503  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000a50a  mov     rcx, rax; hModule
0x18000a50d  call    cs:__imp_GetProcAddress
0x18000a513  test    rax, rax
0x18000a516  jz      loc_18000A5AC
0x18000a51c  mov     rcx, rax; Ptr
0x18000a51f  call    cs:__imp_EncodePointer
0x18000a525  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000a52c  mov     rcx, rbx; hModule
0x18000a52f  mov     cs:qword_180013A30, rax
0x18000a536  call    cs:__imp_GetProcAddress
0x18000a53c  test    rax, rax
0x18000a53f  jz      short loc_18000A5AC
0x18000a541  mov     rcx, rax; Ptr
0x18000a544  call    cs:__imp_EncodePointer
0x18000a54a  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000a551  mov     rcx, rbx; hModule
0x18000a554  mov     cs:qword_180013A20, rax
0x18000a55b  call    cs:__imp_GetProcAddress
0x18000a561  test    rax, rax
0x18000a564  jz      short loc_18000A5AC
0x18000a566  mov     rcx, rax; Ptr
0x18000a569  call    cs:__imp_EncodePointer
0x18000a56f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000a576  mov     rcx, rbx; hModule
0x18000a579  mov     cs:qword_180013A18, rax
0x18000a580  call    cs:__imp_GetProcAddress
0x18000a586  test    rax, rax
0x18000a589  jz      short loc_18000A5AC
0x18000a58b  mov     rcx, rax; Ptr
0x18000a58e  call    cs:__imp_EncodePointer
0x18000a594  mov     cs:qword_180013A10, rax
0x18000a59b  lock or [rsp+28h+var_28], 0
0x18000a5a0  mov     cs:byte_180013A28, 1
0x18000a5a7  jmp     loc_18000A4CF
0x18000a5ac  xor     eax, eax
0x18000a5ae  add     rsp, 20h
0x18000a5b2  pop     rbx
0x18000a5b3  retn
```
