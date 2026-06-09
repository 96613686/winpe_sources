# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x18000a3c4`
- end: `0x18000a4b8`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a7b4`

## callees

- `0x18000a3c4`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18000a3df`
- `KERNEL32!EncodePointer` at `0x18000a423`
- `KERNEL32!EncodePointer` at `0x18000a448`
- `KERNEL32!EncodePointer` at `0x18000a46d`
- `KERNEL32!EncodePointer` at `0x18000a492`
- `KERNEL32!EncodePointer` at `0x18000a423`
- `KERNEL32!EncodePointer` at `0x18000a448`
- `KERNEL32!EncodePointer` at `0x18000a46d`
- `KERNEL32!EncodePointer` at `0x18000a492`
- `KERNEL32!LoadLibraryExA` at `0x18000a3f5`
- `KERNEL32!LoadLibraryExA` at `0x18000a3f5`
- `KERNEL32!GetProcAddress` at `0x18000a411`
- `KERNEL32!GetProcAddress` at `0x18000a43a`
- `KERNEL32!GetProcAddress` at `0x18000a45f`
- `KERNEL32!GetProcAddress` at `0x18000a484`
- `KERNEL32!GetProcAddress` at `0x18000a411`
- `KERNEL32!GetProcAddress` at `0x18000a43a`
- `KERNEL32!GetProcAddress` at `0x18000a45f`
- `KERNEL32!GetProcAddress` at `0x18000a484`

## string_xrefs

- `0x18000a3e8`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_void____cdecl___AtlThunkData_t____()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180013A28 )
    return DecodePointer((PVOID)qword_180013A10);
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
            return DecodePointer((PVOID)qword_180013A10);
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
0x18000a3c4  push    rbx
0x18000a3c6  sub     rsp, 20h
0x18000a3ca  cmp     cs:byte_180013A28, 0
0x18000a3d1  jz      short loc_18000A3E6
0x18000a3d3  mov     rcx, cs:qword_180013A10
0x18000a3da  add     rsp, 20h
0x18000a3de  pop     rbx
0x18000a3df  jmp     cs:__imp_DecodePointer
0x18000a3e6  xor     edx, edx; hFile
0x18000a3e8  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000a3ef  mov     r8d, 800h; dwFlags
0x18000a3f5  call    cs:__imp_LoadLibraryExA
0x18000a3fb  mov     rbx, rax
0x18000a3fe  test    rax, rax
0x18000a401  jz      loc_18000A4B0
0x18000a407  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000a40e  mov     rcx, rax; hModule
0x18000a411  call    cs:__imp_GetProcAddress
0x18000a417  test    rax, rax
0x18000a41a  jz      loc_18000A4B0
0x18000a420  mov     rcx, rax; Ptr
0x18000a423  call    cs:__imp_EncodePointer
0x18000a429  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000a430  mov     rcx, rbx; hModule
0x18000a433  mov     cs:qword_180013A30, rax
0x18000a43a  call    cs:__imp_GetProcAddress
0x18000a440  test    rax, rax
0x18000a443  jz      short loc_18000A4B0
0x18000a445  mov     rcx, rax; Ptr
0x18000a448  call    cs:__imp_EncodePointer
0x18000a44e  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000a455  mov     rcx, rbx; hModule
0x18000a458  mov     cs:qword_180013A20, rax
0x18000a45f  call    cs:__imp_GetProcAddress
0x18000a465  test    rax, rax
0x18000a468  jz      short loc_18000A4B0
0x18000a46a  mov     rcx, rax; Ptr
0x18000a46d  call    cs:__imp_EncodePointer
0x18000a473  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000a47a  mov     rcx, rbx; hModule
0x18000a47d  mov     cs:qword_180013A18, rax
0x18000a484  call    cs:__imp_GetProcAddress
0x18000a48a  test    rax, rax
0x18000a48d  jz      short loc_18000A4B0
0x18000a48f  mov     rcx, rax; Ptr
0x18000a492  call    cs:__imp_EncodePointer
0x18000a498  mov     cs:qword_180013A10, rax
0x18000a49f  lock or [rsp+28h+var_28], 0
0x18000a4a4  mov     cs:byte_180013A28, 1
0x18000a4ab  jmp     loc_18000A3D3
0x18000a4b0  xor     eax, eax
0x18000a4b2  add     rsp, 20h
0x18000a4b6  pop     rbx
0x18000a4b7  retn
```
