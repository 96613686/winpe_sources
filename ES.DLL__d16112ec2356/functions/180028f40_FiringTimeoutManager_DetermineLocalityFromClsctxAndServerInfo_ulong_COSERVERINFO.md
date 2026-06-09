# FiringTimeoutManager::DetermineLocalityFromClsctxAndServerInfo(ulong,_COSERVERINFO *)

- ea: `0x180028f40`
- end: `0x180029011`
- name: `?DetermineLocalityFromClsctxAndServerInfo@FiringTimeoutManager@@AEAA?AW4Locality@@KPEAU_COSERVERINFO@@@Z`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001adb0`
- `0x18002efc8`

## callees

- `0x180003d54`
- `0x180028f40`
- `0x180043510`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180028fd0`
- `msvcrt!_wcsicmp` at `0x180028fd0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180028fbd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180028fbd`

## string_xrefs

- `0x180028f7b`: `com\complus\src\events\tier1\agent.cpp`
- `0x180028f93`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
__int64 __fastcall FiringTimeoutManager::DetermineLocalityFromClsctxAndServerInfo(__int64 a1, int a2, __int64 a3)
{
  DWORD nSize[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( a2 != 16 )
    return (a2 & 1) == 0 ? 3 : 0;
  if ( !a3 )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x829u, 0x80001203, 0x12u);
  if ( !*(_QWORD *)(a3 + 8) )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x82Au, 0x80001203, 0x12u);
  nSize[0] = 261;
  if ( !GetComputerNameW(Buffer, nSize) )
    return 0;
  if ( _wcsicmp(Buffer, *(const wchar_t **)(a3 + 8)) )
    return 4;
  return 3;
}

```

## disassembly

```asm
0x180028f40  push    rbx
0x180028f42  sub     rsp, 250h
0x180028f49  mov     rax, cs:__security_cookie
0x180028f50  xor     rax, rsp
0x180028f53  mov     [rsp+258h+var_18], rax
0x180028f5b  mov     rbx, r8
0x180028f5e  cmp     edx, 10h
0x180028f61  jnz     loc_180028FEC
0x180028f67  test    rbx, rbx
0x180028f6a  jnz     short loc_180028F87
0x180028f6c  lea     r9d, [r8+12h]; unsigned __int16
0x180028f70  mov     edx, 829h; unsigned int
0x180028f75  mov     r8d, 80001203h; unsigned int
0x180028f7b  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180028f82  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180028f87  cmp     qword ptr [rbx+8], 0
0x180028f8c  jnz     short loc_180028FAB
0x180028f8e  mov     edx, 82Ah; unsigned int
0x180028f93  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180028f9a  mov     r9d, 12h; unsigned __int16
0x180028fa0  mov     r8d, 80001203h; unsigned int
0x180028fa6  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180028fab  lea     rdx, [rsp+258h+nSize]; nSize
0x180028fb0  mov     [rsp+258h+nSize], 105h
0x180028fb8  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180028fbd  call    cs:__imp_GetComputerNameW
0x180028fc3  test    eax, eax
0x180028fc5  jz      short loc_180028FE8
0x180028fc7  mov     rdx, [rbx+8]; String2
0x180028fcb  lea     rcx, [rsp+258h+Buffer]; String1
0x180028fd0  call    cs:__imp__wcsicmp
0x180028fd6  test    eax, eax
0x180028fd8  jz      short loc_180028FE1
0x180028fda  mov     eax, 4
0x180028fdf  jmp     short loc_180028FF8
0x180028fe1  mov     eax, 3
0x180028fe6  jmp     short loc_180028FF8
0x180028fe8  xor     eax, eax
0x180028fea  jmp     short loc_180028FF8
0x180028fec  and     dl, 1
0x180028fef  neg     dl
0x180028ff1  sbb     eax, eax
0x180028ff3  not     eax
0x180028ff5  and     eax, 3
0x180028ff8  mov     rcx, [rsp+258h+var_18]
0x180029000  xor     rcx, rsp; StackCookie
0x180029003  call    __security_check_cookie
0x180029008  add     rsp, 250h
0x18002900f  pop     rbx
0x180029010  retn
```
