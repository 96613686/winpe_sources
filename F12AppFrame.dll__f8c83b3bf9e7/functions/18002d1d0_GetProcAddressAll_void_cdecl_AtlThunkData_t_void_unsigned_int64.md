# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_

- ea: `0x18002d1d0`
- end: `0x18002d2c4`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t___void___unsigned___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d524`

## callees

- `0x18002d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d21d`
- `KERNEL32!GetProcAddress` at `0x18002d246`
- `KERNEL32!GetProcAddress` at `0x18002d26b`
- `KERNEL32!GetProcAddress` at `0x18002d290`
- `KERNEL32!GetProcAddress` at `0x18002d21d`
- `KERNEL32!GetProcAddress` at `0x18002d246`
- `KERNEL32!GetProcAddress` at `0x18002d26b`
- `KERNEL32!GetProcAddress` at `0x18002d290`
- `KERNEL32!LoadLibraryExA` at `0x18002d201`
- `KERNEL32!LoadLibraryExA` at `0x18002d201`
- `KERNEL32!EncodePointer` at `0x18002d22f`
- `KERNEL32!EncodePointer` at `0x18002d254`
- `KERNEL32!EncodePointer` at `0x18002d279`
- `KERNEL32!EncodePointer` at `0x18002d29e`
- `KERNEL32!EncodePointer` at `0x18002d22f`
- `KERNEL32!EncodePointer` at `0x18002d254`
- `KERNEL32!EncodePointer` at `0x18002d279`
- `KERNEL32!EncodePointer` at `0x18002d29e`
- `KERNEL32!DecodePointer` at `0x18002d1eb`

## string_xrefs

- `0x18002d1f4`: `atlthunk.dll`

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

  if ( byte_180050880 )
    return DecodePointer((PVOID)qword_180050878);
  Library = LoadLibraryExA("atlthunk.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AtlThunk_AllocateData");
    if ( ProcAddress )
    {
      qword_180050888 = (__int64)EncodePointer(ProcAddress);
      v4 = GetProcAddress(v2, "AtlThunk_InitData");
      if ( v4 )
      {
        qword_180050878 = (__int64)EncodePointer(v4);
        v5 = GetProcAddress(v2, "AtlThunk_DataToCode");
        if ( v5 )
        {
          qword_180050870 = (__int64)EncodePointer(v5);
          v6 = GetProcAddress(v2, "AtlThunk_FreeData");
          if ( v6 )
          {
            qword_180050868 = (__int64)EncodePointer(v6);
            _InterlockedOr(v7, 0);
            byte_180050880 = 1;
            return DecodePointer((PVOID)qword_180050878);
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
0x18002d1d0  push    rbx
0x18002d1d2  sub     rsp, 20h
0x18002d1d6  cmp     cs:byte_180050880, 0
0x18002d1dd  jz      short loc_18002D1F2
0x18002d1df  mov     rcx, cs:qword_180050878
0x18002d1e6  add     rsp, 20h
0x18002d1ea  pop     rbx
0x18002d1eb  jmp     cs:__imp_DecodePointer
0x18002d1f2  xor     edx, edx; hFile
0x18002d1f4  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18002d1fb  mov     r8d, 800h; dwFlags
0x18002d201  call    cs:__imp_LoadLibraryExA
0x18002d207  mov     rbx, rax
0x18002d20a  test    rax, rax
0x18002d20d  jz      loc_18002D2BC
0x18002d213  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d21a  mov     rcx, rax; hModule
0x18002d21d  call    cs:__imp_GetProcAddress
0x18002d223  test    rax, rax
0x18002d226  jz      loc_18002D2BC
0x18002d22c  mov     rcx, rax; Ptr
0x18002d22f  call    cs:__imp_EncodePointer
0x18002d235  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d23c  mov     rcx, rbx; hModule
0x18002d23f  mov     cs:qword_180050888, rax
0x18002d246  call    cs:__imp_GetProcAddress
0x18002d24c  test    rax, rax
0x18002d24f  jz      short loc_18002D2BC
0x18002d251  mov     rcx, rax; Ptr
0x18002d254  call    cs:__imp_EncodePointer
0x18002d25a  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d261  mov     rcx, rbx; hModule
0x18002d264  mov     cs:qword_180050878, rax
0x18002d26b  call    cs:__imp_GetProcAddress
0x18002d271  test    rax, rax
0x18002d274  jz      short loc_18002D2BC
0x18002d276  mov     rcx, rax; Ptr
0x18002d279  call    cs:__imp_EncodePointer
0x18002d27f  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d286  mov     rcx, rbx; hModule
0x18002d289  mov     cs:qword_180050870, rax
0x18002d290  call    cs:__imp_GetProcAddress
0x18002d296  test    rax, rax
0x18002d299  jz      short loc_18002D2BC
0x18002d29b  mov     rcx, rax; Ptr
0x18002d29e  call    cs:__imp_EncodePointer
0x18002d2a4  mov     cs:qword_180050868, rax
0x18002d2ab  lock or [rsp+28h+var_28], 0
0x18002d2b0  mov     cs:byte_180050880, 1
0x18002d2b7  jmp     loc_18002D1DF
0x18002d2bc  xor     eax, eax
0x18002d2be  add     rsp, 20h
0x18002d2c2  pop     rbx
0x18002d2c3  retn
```
