# CW32System::UiaGetReservedMixedAttributeValue(IUnknown * *)

- ea: `0x180040ef4`
- end: `0x180040f93`
- name: `?UiaGetReservedMixedAttributeValue@CW32System@@SAJPEAPEAUIUnknown@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004097c`

## callees

- `0x18002ab44`
- `0x18002abb0`
- `0x180040ef4`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040f56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040f56`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180040f3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180040f3a`

## string_xrefs

- `0x180040f2d`: `uiautomationcore.dll`

## pseudocode

```c
__int64 __fastcall CW32System::UiaGetReservedMixedAttributeValue(struct IUnknown **a1)
{
  __int64 (__fastcall *v1)(__int64 *); // rax
  HMODULE Library; // rax
  struct IUnknown **v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  v1 = (__int64 (__fastcall *)(__int64 *))pUiaGetReservedMixedAttributeValue;
  if ( pUiaGetReservedMixedAttributeValue )
    return v1(&qword_1802DF188);
  CWriteLock::CWriteLock((unsigned int *)&v4, 0);
  if ( !pUiaGetReservedMixedAttributeValue )
  {
    Library = qword_1802DF240;
    if ( qword_1802DF240
      || (Library = LoadLibraryExW(L"uiautomationcore.dll", 0, 0x800u), (qword_1802DF240 = Library) != 0) )
    {
      pUiaGetReservedMixedAttributeValue = GetProcAddress(Library, "UiaGetReservedMixedAttributeValue");
    }
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  v1 = (__int64 (__fastcall *)(__int64 *))pUiaGetReservedMixedAttributeValue;
  if ( pUiaGetReservedMixedAttributeValue )
    return v1(&qword_1802DF188);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x180040ef4  mov     [rsp+arg_0], rcx
0x180040ef9  sub     rsp, 28h
0x180040efd  mov     rax, cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA; void * pUiaGetReservedMixedAttributeValue
0x180040f04  test    rax, rax
0x180040f07  jnz     short loc_180040F83
0x180040f09  xor     edx, edx
0x180040f0b  lea     rcx, [rsp+28h+arg_0]
0x180040f10  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180040f15  cmp     cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA, 0; void * pUiaGetReservedMixedAttributeValue
0x180040f1d  jnz     short loc_180040F63
0x180040f1f  mov     rax, cs:qword_1802DF240
0x180040f26  test    rax, rax
0x180040f29  jnz     short loc_180040F4C
0x180040f2b  xor     edx, edx; hFile
0x180040f2d  lea     rcx, aUiautomationco; "uiautomationcore.dll"
0x180040f34  mov     r8d, 800h; dwFlags
0x180040f3a  call    cs:__imp_LoadLibraryExW
0x180040f40  mov     cs:qword_1802DF240, rax
0x180040f47  test    rax, rax
0x180040f4a  jz      short loc_180040F63
0x180040f4c  lea     rdx, aUiagetreserved; "UiaGetReservedMixedAttributeValue"
0x180040f53  mov     rcx, rax; hModule
0x180040f56  call    cs:__imp_GetProcAddress
0x180040f5c  mov     cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA, rax; void * pUiaGetReservedMixedAttributeValue
0x180040f63  lea     rcx, [rsp+28h+arg_0]; this
0x180040f68  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180040f6d  mov     rax, cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA; void * pUiaGetReservedMixedAttributeValue
0x180040f74  test    rax, rax
0x180040f77  jnz     short loc_180040F83
0x180040f79  mov     eax, 80004002h
0x180040f7e  add     rsp, 28h
0x180040f82  retn
0x180040f83  lea     rcx, qword_1802DF188
0x180040f8a  add     rsp, 28h
0x180040f8e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
