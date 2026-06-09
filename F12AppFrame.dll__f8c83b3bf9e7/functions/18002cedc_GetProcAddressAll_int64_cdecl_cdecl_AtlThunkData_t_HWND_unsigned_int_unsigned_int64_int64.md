# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x18002cedc`
- end: `0x18002cfd0`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d480`

## callees

- `0x18002cedc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002cf29`
- `KERNEL32!GetProcAddress` at `0x18002cf52`
- `KERNEL32!GetProcAddress` at `0x18002cf77`
- `KERNEL32!GetProcAddress` at `0x18002cf9c`
- `KERNEL32!GetProcAddress` at `0x18002cf29`
- `KERNEL32!GetProcAddress` at `0x18002cf52`
- `KERNEL32!GetProcAddress` at `0x18002cf77`
- `KERNEL32!GetProcAddress` at `0x18002cf9c`
- `KERNEL32!LoadLibraryExA` at `0x18002cf0d`
- `KERNEL32!LoadLibraryExA` at `0x18002cf0d`
- `KERNEL32!EncodePointer` at `0x18002cf3b`
- `KERNEL32!EncodePointer` at `0x18002cf60`
- `KERNEL32!EncodePointer` at `0x18002cf85`
- `KERNEL32!EncodePointer` at `0x18002cfaa`
- `KERNEL32!EncodePointer` at `0x18002cf3b`
- `KERNEL32!EncodePointer` at `0x18002cf60`
- `KERNEL32!EncodePointer` at `0x18002cf85`
- `KERNEL32!EncodePointer` at `0x18002cfaa`
- `KERNEL32!DecodePointer` at `0x18002cef7`

## string_xrefs

- `0x18002cf00`: `atlthunk.dll`

## pseudocode

```c
PVOID GetProcAddressAll___int64____cdecl____cdecl___AtlThunkData_t_____HWND_____unsigned_int_unsigned___int64___int64__()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  signed __int32 v7[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( byte_180050880 )
    return DecodePointer((PVOID)qword_180050870);
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
            return DecodePointer((PVOID)qword_180050870);
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
0x18002cedc  push    rbx
0x18002cede  sub     rsp, 20h
0x18002cee2  cmp     cs:byte_180050880, 0
0x18002cee9  jz      short loc_18002CEFE
0x18002ceeb  mov     rcx, cs:qword_180050870
0x18002cef2  add     rsp, 20h
0x18002cef6  pop     rbx
0x18002cef7  jmp     cs:__imp_DecodePointer
0x18002cefe  xor     edx, edx; hFile
0x18002cf00  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18002cf07  mov     r8d, 800h; dwFlags
0x18002cf0d  call    cs:__imp_LoadLibraryExA
0x18002cf13  mov     rbx, rax
0x18002cf16  test    rax, rax
0x18002cf19  jz      loc_18002CFC8
0x18002cf1f  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18002cf26  mov     rcx, rax; hModule
0x18002cf29  call    cs:__imp_GetProcAddress
0x18002cf2f  test    rax, rax
0x18002cf32  jz      loc_18002CFC8
0x18002cf38  mov     rcx, rax; Ptr
0x18002cf3b  call    cs:__imp_EncodePointer
0x18002cf41  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18002cf48  mov     rcx, rbx; hModule
0x18002cf4b  mov     cs:qword_180050888, rax
0x18002cf52  call    cs:__imp_GetProcAddress
0x18002cf58  test    rax, rax
0x18002cf5b  jz      short loc_18002CFC8
0x18002cf5d  mov     rcx, rax; Ptr
0x18002cf60  call    cs:__imp_EncodePointer
0x18002cf66  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18002cf6d  mov     rcx, rbx; hModule
0x18002cf70  mov     cs:qword_180050878, rax
0x18002cf77  call    cs:__imp_GetProcAddress
0x18002cf7d  test    rax, rax
0x18002cf80  jz      short loc_18002CFC8
0x18002cf82  mov     rcx, rax; Ptr
0x18002cf85  call    cs:__imp_EncodePointer
0x18002cf8b  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18002cf92  mov     rcx, rbx; hModule
0x18002cf95  mov     cs:qword_180050870, rax
0x18002cf9c  call    cs:__imp_GetProcAddress
0x18002cfa2  test    rax, rax
0x18002cfa5  jz      short loc_18002CFC8
0x18002cfa7  mov     rcx, rax; Ptr
0x18002cfaa  call    cs:__imp_EncodePointer
0x18002cfb0  mov     cs:qword_180050868, rax
0x18002cfb7  lock or [rsp+28h+var_28], 0
0x18002cfbc  mov     cs:byte_180050880, 1
0x18002cfc3  jmp     loc_18002CEEB
0x18002cfc8  xor     eax, eax
0x18002cfca  add     rsp, 20h
0x18002cfce  pop     rbx
0x18002cfcf  retn
```
