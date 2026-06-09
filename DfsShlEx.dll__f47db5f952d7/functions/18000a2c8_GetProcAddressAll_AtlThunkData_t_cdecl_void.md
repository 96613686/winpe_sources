# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x18000a2c8`
- end: `0x18000a3bc`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a6f8`

## callees

- `0x18000a2c8`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18000a2e3`
- `KERNEL32!EncodePointer` at `0x18000a327`
- `KERNEL32!EncodePointer` at `0x18000a34c`
- `KERNEL32!EncodePointer` at `0x18000a371`
- `KERNEL32!EncodePointer` at `0x18000a396`
- `KERNEL32!EncodePointer` at `0x18000a327`
- `KERNEL32!EncodePointer` at `0x18000a34c`
- `KERNEL32!EncodePointer` at `0x18000a371`
- `KERNEL32!EncodePointer` at `0x18000a396`
- `KERNEL32!LoadLibraryExA` at `0x18000a2f9`
- `KERNEL32!LoadLibraryExA` at `0x18000a2f9`
- `KERNEL32!GetProcAddress` at `0x18000a315`
- `KERNEL32!GetProcAddress` at `0x18000a33e`
- `KERNEL32!GetProcAddress` at `0x18000a363`
- `KERNEL32!GetProcAddress` at `0x18000a388`
- `KERNEL32!GetProcAddress` at `0x18000a315`
- `KERNEL32!GetProcAddress` at `0x18000a33e`
- `KERNEL32!GetProcAddress` at `0x18000a363`
- `KERNEL32!GetProcAddress` at `0x18000a388`

## string_xrefs

- `0x18000a2ec`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll_AtlThunkData_t______cdecl___void__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180013A28 )
    return DecodePointer((PVOID)qword_180013A30);
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
            return DecodePointer((PVOID)qword_180013A30);
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
0x18000a2c8  push    rbx
0x18000a2ca  sub     rsp, 20h
0x18000a2ce  cmp     cs:byte_180013A28, 0
0x18000a2d5  jz      short loc_18000A2EA
0x18000a2d7  mov     rcx, cs:qword_180013A30
0x18000a2de  add     rsp, 20h
0x18000a2e2  pop     rbx
0x18000a2e3  jmp     cs:__imp_DecodePointer
0x18000a2ea  xor     edx, edx; hFile
0x18000a2ec  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000a2f3  mov     r8d, 800h; dwFlags
0x18000a2f9  call    cs:__imp_LoadLibraryExA
0x18000a2ff  mov     rbx, rax
0x18000a302  test    rax, rax
0x18000a305  jz      loc_18000A3B4
0x18000a30b  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000a312  mov     rcx, rax; hModule
0x18000a315  call    cs:__imp_GetProcAddress
0x18000a31b  test    rax, rax
0x18000a31e  jz      loc_18000A3B4
0x18000a324  mov     rcx, rax; Ptr
0x18000a327  call    cs:__imp_EncodePointer
0x18000a32d  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000a334  mov     rcx, rbx; hModule
0x18000a337  mov     cs:qword_180013A30, rax
0x18000a33e  call    cs:__imp_GetProcAddress
0x18000a344  test    rax, rax
0x18000a347  jz      short loc_18000A3B4
0x18000a349  mov     rcx, rax; Ptr
0x18000a34c  call    cs:__imp_EncodePointer
0x18000a352  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000a359  mov     rcx, rbx; hModule
0x18000a35c  mov     cs:qword_180013A20, rax
0x18000a363  call    cs:__imp_GetProcAddress
0x18000a369  test    rax, rax
0x18000a36c  jz      short loc_18000A3B4
0x18000a36e  mov     rcx, rax; Ptr
0x18000a371  call    cs:__imp_EncodePointer
0x18000a377  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000a37e  mov     rcx, rbx; hModule
0x18000a381  mov     cs:qword_180013A18, rax
0x18000a388  call    cs:__imp_GetProcAddress
0x18000a38e  test    rax, rax
0x18000a391  jz      short loc_18000A3B4
0x18000a393  mov     rcx, rax; Ptr
0x18000a396  call    cs:__imp_EncodePointer
0x18000a39c  mov     cs:qword_180013A10, rax
0x18000a3a3  lock or [rsp+28h+var_28], 0
0x18000a3a8  mov     cs:byte_180013A28, 1
0x18000a3af  jmp     loc_18000A2D7
0x18000a3b4  xor     eax, eax
0x18000a3b6  add     rsp, 20h
0x18000a3ba  pop     rbx
0x18000a3bb  retn
```
