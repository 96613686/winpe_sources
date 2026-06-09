# GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_

- ea: `0x18000a1cc`
- end: `0x18000a2c0`
- name: `GetProcAddressAll___int64_(__cdecl_(__cdecl_)(AtlThunkData_t__))(HWND_____unsigned_int_unsigned___int64___int64)_`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a770`

## callees

- `0x18000a1cc`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18000a1e7`
- `KERNEL32!EncodePointer` at `0x18000a22b`
- `KERNEL32!EncodePointer` at `0x18000a250`
- `KERNEL32!EncodePointer` at `0x18000a275`
- `KERNEL32!EncodePointer` at `0x18000a29a`
- `KERNEL32!EncodePointer` at `0x18000a22b`
- `KERNEL32!EncodePointer` at `0x18000a250`
- `KERNEL32!EncodePointer` at `0x18000a275`
- `KERNEL32!EncodePointer` at `0x18000a29a`
- `KERNEL32!LoadLibraryExA` at `0x18000a1fd`
- `KERNEL32!LoadLibraryExA` at `0x18000a1fd`
- `KERNEL32!GetProcAddress` at `0x18000a219`
- `KERNEL32!GetProcAddress` at `0x18000a242`
- `KERNEL32!GetProcAddress` at `0x18000a267`
- `KERNEL32!GetProcAddress` at `0x18000a28c`
- `KERNEL32!GetProcAddress` at `0x18000a219`
- `KERNEL32!GetProcAddress` at `0x18000a242`
- `KERNEL32!GetProcAddress` at `0x18000a267`
- `KERNEL32!GetProcAddress` at `0x18000a28c`

## string_xrefs

- `0x18000a1f0`: `atlthunk.dll`

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

  if ( byte_180013A28 )
    return DecodePointer((PVOID)qword_180013A18);
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
            return DecodePointer((PVOID)qword_180013A18);
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
0x18000a1cc  push    rbx
0x18000a1ce  sub     rsp, 20h
0x18000a1d2  cmp     cs:byte_180013A28, 0
0x18000a1d9  jz      short loc_18000A1EE
0x18000a1db  mov     rcx, cs:qword_180013A18
0x18000a1e2  add     rsp, 20h
0x18000a1e6  pop     rbx
0x18000a1e7  jmp     cs:__imp_DecodePointer
0x18000a1ee  xor     edx, edx; hFile
0x18000a1f0  lea     rcx, aAtlthunkDll; "atlthunk.dll"
0x18000a1f7  mov     r8d, 800h; dwFlags
0x18000a1fd  call    cs:__imp_LoadLibraryExA
0x18000a203  mov     rbx, rax
0x18000a206  test    rax, rax
0x18000a209  jz      loc_18000A2B8
0x18000a20f  lea     rdx, aAtlthunkAlloca; "AtlThunk_AllocateData"
0x18000a216  mov     rcx, rax; hModule
0x18000a219  call    cs:__imp_GetProcAddress
0x18000a21f  test    rax, rax
0x18000a222  jz      loc_18000A2B8
0x18000a228  mov     rcx, rax; Ptr
0x18000a22b  call    cs:__imp_EncodePointer
0x18000a231  lea     rdx, aAtlthunkInitda; "AtlThunk_InitData"
0x18000a238  mov     rcx, rbx; hModule
0x18000a23b  mov     cs:qword_180013A30, rax
0x18000a242  call    cs:__imp_GetProcAddress
0x18000a248  test    rax, rax
0x18000a24b  jz      short loc_18000A2B8
0x18000a24d  mov     rcx, rax; Ptr
0x18000a250  call    cs:__imp_EncodePointer
0x18000a256  lea     rdx, aAtlthunkDatato; "AtlThunk_DataToCode"
0x18000a25d  mov     rcx, rbx; hModule
0x18000a260  mov     cs:qword_180013A20, rax
0x18000a267  call    cs:__imp_GetProcAddress
0x18000a26d  test    rax, rax
0x18000a270  jz      short loc_18000A2B8
0x18000a272  mov     rcx, rax; Ptr
0x18000a275  call    cs:__imp_EncodePointer
0x18000a27b  lea     rdx, aAtlthunkFreeda; "AtlThunk_FreeData"
0x18000a282  mov     rcx, rbx; hModule
0x18000a285  mov     cs:qword_180013A18, rax
0x18000a28c  call    cs:__imp_GetProcAddress
0x18000a292  test    rax, rax
0x18000a295  jz      short loc_18000A2B8
0x18000a297  mov     rcx, rax; Ptr
0x18000a29a  call    cs:__imp_EncodePointer
0x18000a2a0  mov     cs:qword_180013A10, rax
0x18000a2a7  lock or [rsp+28h+var_28], 0
0x18000a2ac  mov     cs:byte_180013A28, 1
0x18000a2b3  jmp     loc_18000A1DB
0x18000a2b8  xor     eax, eax
0x18000a2ba  add     rsp, 20h
0x18000a2be  pop     rbx
0x18000a2bf  retn
```
