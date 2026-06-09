# SHSendChangeMenuNotify

- ea: `0x180016428`
- end: `0x18001649d`
- name: `SHSendChangeMenuNotify`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180016fa8`

## callees

- `0x180002ce0`
- `0x180016428`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001646b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001646b`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180016484`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180016484`

## pseudocode

```c
void __fastcall SHSendChangeMenuNotify(__int64 a1, __int64 a2, __int64 a3, const void *a4)
{
  __int16 dwItem1; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+22h] [rbp-26h]
  __int64 v7; // [rsp+26h] [rbp-22h]
  DWORD CurrentProcessId; // [rsp+2Eh] [rbp-1Ah]
  __int16 v9; // [rsp+32h] [rbp-16h]

  CurrentProcessId = 0;
  v9 = 0;
  dwItem1 = 18;
  v6 = 2;
  v7 = a1;
  if ( a1 )
    CurrentProcessId = GetCurrentProcessId();
  SHChangeNotify(0x4000000, 0, &dwItem1, a4);
}

```

## disassembly

```asm
0x180016428  push    rbx
0x18001642a  sub     rsp, 40h
0x18001642e  mov     rax, cs:__security_cookie
0x180016435  xor     rax, rsp
0x180016438  mov     [rsp+48h+var_10], rax
0x18001643d  xor     eax, eax
0x18001643f  mov     [rsp+48h+var_1A], 0
0x180016447  mov     [rsp+48h+var_16], ax
0x18001644c  mov     eax, 12h
0x180016451  mov     [rsp+48h+dwItem1], ax
0x180016456  mov     rbx, r9
0x180016459  mov     [rsp+48h+var_26], 2
0x180016461  mov     [rsp+48h+var_22], rcx
0x180016466  test    rcx, rcx
0x180016469  jz      short loc_180016475
0x18001646b  call    cs:__imp_GetCurrentProcessId
0x180016471  mov     [rsp+48h+var_1A], eax
0x180016475  mov     r9, rbx; dwItem2
0x180016478  lea     r8, [rsp+48h+dwItem1]; dwItem1
0x18001647d  xor     edx, edx; uFlags
0x18001647f  mov     ecx, 4000000h; wEventId
0x180016484  call    cs:__imp_SHChangeNotify
0x18001648a  mov     rcx, [rsp+48h+var_10]
0x18001648f  xor     rcx, rsp; StackCookie
0x180016492  call    __security_check_cookie
0x180016497  add     rsp, 40h
0x18001649b  pop     rbx
0x18001649c  retn
```
