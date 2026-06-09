# Old_IsRNGWinNT

- ea: `0x180064b64`
- end: `0x180064c10`
- name: `Old_IsRNGWinNT`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006400c`
- `0x180064a00`

## callees

- `0x180064b64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180064b84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180064b84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064ba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064bce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064beb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064ba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064bce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064beb`

## string_xrefs

- `0x180064b7d`: `ntdll.dll`
- `0x180064bc4`: `NtOpenFile`

## pseudocode

```c
__int64 Old_IsRNGWinNT()
{
  __int64 result; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE v2; // rbx

  if ( dword_1800E5D48 )
    return 1;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v2 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    __NtQuerySystemInformationRNG = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                      ModuleHandleW,
                                                                                      "NtQuerySystemInformation");
    if ( __NtQuerySystemInformationRNG )
      dword_1800E53A4 = 0x4000;
    __NtOpenFileRNG = (__int64)GetProcAddress(v2, "NtOpenFile");
    __RtlInitUnicodeStringRNG = (__int64)GetProcAddress(v2, "RtlInitUnicodeString");
  }
  result = 1;
  dword_1800E5D48 = 1;
  return result;
}

```

## disassembly

```asm
0x180064b64  push    rbx
0x180064b66  sub     rsp, 20h
0x180064b6a  cmp     cs:dword_1800E5D48, 0
0x180064b71  jz      short loc_180064B7D
0x180064b73  mov     eax, 1
0x180064b78  jmp     loc_180064C09
0x180064b7d  lea     rcx, ModuleName; "ntdll.dll"
0x180064b84  call    cs:__imp_GetModuleHandleW
0x180064b8b  nop     dword ptr [rax+rax+00h]
0x180064b90  mov     rbx, rax
0x180064b93  test    rax, rax
0x180064b96  jz      short loc_180064BFE
0x180064b98  lea     rdx, ProcName; "NtQuerySystemInformation"
0x180064b9f  mov     rcx, rax; hModule
0x180064ba2  call    cs:__imp_GetProcAddress
0x180064ba9  nop     dword ptr [rax+rax+00h]
0x180064bae  mov     cs:___NtQuerySystemInformationRNG, rax
0x180064bb5  test    rax, rax
0x180064bb8  jz      short loc_180064BC4
0x180064bba  mov     cs:dword_1800E53A4, 4000h
0x180064bc4  lea     rdx, aNtopenfile; "NtOpenFile"
0x180064bcb  mov     rcx, rbx; hModule
0x180064bce  call    cs:__imp_GetProcAddress
0x180064bd5  nop     dword ptr [rax+rax+00h]
0x180064bda  lea     rdx, aRtlinitunicode; "RtlInitUnicodeString"
0x180064be1  mov     rcx, rbx; hModule
0x180064be4  mov     cs:___NtOpenFileRNG, rax
0x180064beb  call    cs:__imp_GetProcAddress
0x180064bf2  nop     dword ptr [rax+rax+00h]
0x180064bf7  mov     cs:___RtlInitUnicodeStringRNG, rax
0x180064bfe  mov     eax, 1
0x180064c03  mov     cs:dword_1800E5D48, eax
0x180064c09  add     rsp, 20h
0x180064c0d  pop     rbx
0x180064c0e  retn
```
