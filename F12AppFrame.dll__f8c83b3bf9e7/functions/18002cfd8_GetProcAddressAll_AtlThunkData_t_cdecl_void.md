# GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_

- ea: `0x18002cfd8`
- end: `0x18002d0cc`
- name: `GetProcAddressAll_AtlThunkData_t___(__cdecl_)(void)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d408`

## callees

- `0x18002cfd8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d025`
- `KERNEL32!GetProcAddress` at `0x18002d04e`
- `KERNEL32!GetProcAddress` at `0x18002d073`
- `KERNEL32!GetProcAddress` at `0x18002d098`
- `KERNEL32!GetProcAddress` at `0x18002d025`
- `KERNEL32!GetProcAddress` at `0x18002d04e`
- `KERNEL32!GetProcAddress` at `0x18002d073`
- `KERNEL32!GetProcAddress` at `0x18002d098`
- `KERNEL32!LoadLibraryExA` at `0x18002d009`
- `KERNEL32!LoadLibraryExA` at `0x18002d009`
- `KERNEL32!EncodePointer` at `0x18002d037`
- `KERNEL32!EncodePointer` at `0x18002d05c`
- `KERNEL32!EncodePointer` at `0x18002d081`
- `KERNEL32!EncodePointer` at `0x18002d0a6`
- `KERNEL32!EncodePointer` at `0x18002d037`
- `KERNEL32!EncodePointer` at `0x18002d05c`
- `KERNEL32!EncodePointer` at `0x18002d081`
- `KERNEL32!EncodePointer` at `0x18002d0a6`
- `KERNEL32!DecodePointer` at `0x18002cff3`

## string_xrefs

- `0x18002cffc`: `atlthunk.dll`

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

  if ( byte_180050880 )
    return DecodePointer((PVOID)qword_180050888);
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
            return DecodePointer((PVOID)qword_180050888);
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
0x18002cfd8  push    rbx
0x18002cfda  sub     rsp, 20h
0x18002cfde  cmp     cs:byte_180050880, 0
0x18002cfe5  jz      short loc_18002CFFA
0x18002cfe7  mov     rcx, cs:qword_180050888
0x18002cfee  add     rsp, 20h
0x18002cff2  pop     rbx
0x18002cff3  jmp     cs:__imp_DecodePointer
0x18002cffa  xor     edx, edx; hFile
0x18002cffc  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18002d003  mov     r8d, 800h; dwFlags
0x18002d009  call    cs:__imp_LoadLibraryExA
0x18002d00f  mov     rbx, rax
0x18002d012  test    rax, rax
0x18002d015  jz      loc_18002D0C4
0x18002d01b  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002d022  mov     rcx, rax; hModule
0x18002d025  call    cs:__imp_GetProcAddress
0x18002d02b  test    rax, rax
0x18002d02e  jz      loc_18002D0C4
0x18002d034  mov     rcx, rax; Ptr
0x18002d037  call    cs:__imp_EncodePointer
0x18002d03d  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002d044  mov     rcx, rbx; hModule
0x18002d047  mov     cs:qword_180050888, rax
0x18002d04e  call    cs:__imp_GetProcAddress
0x18002d054  test    rax, rax
0x18002d057  jz      short loc_18002D0C4
0x18002d059  mov     rcx, rax; Ptr
0x18002d05c  call    cs:__imp_EncodePointer
0x18002d062  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002d069  mov     rcx, rbx; hModule
0x18002d06c  mov     cs:qword_180050878, rax
0x18002d073  call    cs:__imp_GetProcAddress
0x18002d079  test    rax, rax
0x18002d07c  jz      short loc_18002D0C4
0x18002d07e  mov     rcx, rax; Ptr
0x18002d081  call    cs:__imp_EncodePointer
0x18002d087  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002d08e  mov     rcx, rbx; hModule
0x18002d091  mov     cs:qword_180050870, rax
0x18002d098  call    cs:__imp_GetProcAddress
0x18002d09e  test    rax, rax
0x18002d0a1  jz      short loc_18002D0C4
0x18002d0a3  mov     rcx, rax; Ptr
0x18002d0a6  call    cs:__imp_EncodePointer
0x18002d0ac  mov     cs:qword_180050868, rax
0x18002d0b3  lock or [rsp+28h+var_28], 0
0x18002d0b8  mov     cs:byte_180050880, 1
0x18002d0bf  jmp     loc_18002CFE7
0x18002d0c4  xor     eax, eax
0x18002d0c6  add     rsp, 20h
0x18002d0ca  pop     rbx
0x18002d0cb  retn
```
