# GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_

- ea: `0x18002d0d4`
- end: `0x18002d1c8`
- name: `GetProcAddressAll_void_(__cdecl_)(AtlThunkData_t__)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d4c4`

## callees

- `0x18002d0d4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d121`
- `KERNEL32!GetProcAddress` at `0x18002d14a`
- `KERNEL32!GetProcAddress` at `0x18002d16f`
- `KERNEL32!GetProcAddress` at `0x18002d194`
- `KERNEL32!GetProcAddress` at `0x18002d121`
- `KERNEL32!GetProcAddress` at `0x18002d14a`
- `KERNEL32!GetProcAddress` at `0x18002d16f`
- `KERNEL32!GetProcAddress` at `0x18002d194`
- `KERNEL32!LoadLibraryExA` at `0x18002d105`
- `KERNEL32!LoadLibraryExA` at `0x18002d105`
- `KERNEL32!EncodePointer` at `0x18002d133`
- `KERNEL32!EncodePointer` at `0x18002d158`
- `KERNEL32!EncodePointer` at `0x18002d17d`
- `KERNEL32!EncodePointer` at `0x18002d1a2`
- `KERNEL32!EncodePointer` at `0x18002d133`
- `KERNEL32!EncodePointer` at `0x18002d158`
- `KERNEL32!EncodePointer` at `0x18002d17d`
- `KERNEL32!EncodePointer` at `0x18002d1a2`
- `KERNEL32!DecodePointer` at `0x18002d0ef`

## string_xrefs

- `0x18002d0f8`: `atlthunk.dll`

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

  if ( byte_180050880 )
    return DecodePointer((PVOID)qword_180050868);
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
            return DecodePointer((PVOID)qword_180050868);
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
0x18002d0d4  push    rbx
0x18002d0d6  sub     rsp, 20h
0x18002d0da  cmp     cs:byte_180050880, 0
0x18002d0e1  jz      short loc_18002D0F6
0x18002d0e3  mov     rcx, cs:qword_180050868
0x18002d0ea  add     rsp, 20h
0x18002d0ee  pop     rbx
0x18002d0ef  jmp     cs:__imp_DecodePointer
0x18002d0f6  xor     edx, edx; hFile
0x18002d0f8  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18002d0ff  mov     r8d, 800h; dwFlags
0x18002d105  call    cs:__imp_LoadLibraryExA
0x18002d10b  mov     rbx, rax
0x18002d10e  test    rax, rax
0x18002d111  jz      loc_18002D1C0
0x18002d117  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d11e  mov     rcx, rax; hModule
0x18002d121  call    cs:__imp_GetProcAddress
0x18002d127  test    rax, rax
0x18002d12a  jz      loc_18002D1C0
0x18002d130  mov     rcx, rax; Ptr
0x18002d133  call    cs:__imp_EncodePointer
0x18002d139  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d140  mov     rcx, rbx; hModule
0x18002d143  mov     cs:qword_180050888, rax
0x18002d14a  call    cs:__imp_GetProcAddress
0x18002d150  test    rax, rax
0x18002d153  jz      short loc_18002D1C0
0x18002d155  mov     rcx, rax; Ptr
0x18002d158  call    cs:__imp_EncodePointer
0x18002d15e  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d165  mov     rcx, rbx; hModule
0x18002d168  mov     cs:qword_180050878, rax
0x18002d16f  call    cs:__imp_GetProcAddress
0x18002d175  test    rax, rax
0x18002d178  jz      short loc_18002D1C0
0x18002d17a  mov     rcx, rax; Ptr
0x18002d17d  call    cs:__imp_EncodePointer
0x18002d183  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d18a  mov     rcx, rbx; hModule
0x18002d18d  mov     cs:qword_180050870, rax
0x18002d194  call    cs:__imp_GetProcAddress
0x18002d19a  test    rax, rax
0x18002d19d  jz      short loc_18002D1C0
0x18002d19f  mov     rcx, rax; Ptr
0x18002d1a2  call    cs:__imp_EncodePointer
0x18002d1a8  mov     cs:qword_180050868, rax
0x18002d1af  lock or [rsp+28h+var_28], 0
0x18002d1b4  mov     cs:byte_180050880, 1
0x18002d1bb  jmp     loc_18002D0E3
0x18002d1c0  xor     eax, eax
0x18002d1c2  add     rsp, 20h
0x18002d1c6  pop     rbx
0x18002d1c7  retn
```
