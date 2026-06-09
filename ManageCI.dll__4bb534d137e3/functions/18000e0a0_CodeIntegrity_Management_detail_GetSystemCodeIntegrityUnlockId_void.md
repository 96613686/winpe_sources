# CodeIntegrity::Management::detail::GetSystemCodeIntegrityUnlockId(void)

- ea: `0x18000e0a0`
- end: `0x18000e13f`
- name: `?GetSystemCodeIntegrityUnlockId@detail@Management@CodeIntegrity@@YA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `159`
- prototype: `char **__fastcall(char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180012f70`

## callees

- `0x180002a90`
- `0x18000d470`
- `0x18000ddd8`
- `0x18000df40`
- `0x18000e0a0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000e0e1`
- `ntdll!NtQuerySystemInformation` at `0x18000e0e1`

## string_xrefs

- `0x18000e0f0`: `onecore\base\ci\management\dll\ntextensions.cpp`

## pseudocode

```c
char **__fastcall CodeIntegrity::Management::detail::GetSystemCodeIntegrityUnlockId(char **a1)
{
  NTSTATUS v2; // eax
  int v4; // [rsp+20h] [rbp-48h]
  char **v5; // [rsp+28h] [rbp-40h] BYREF
  _OWORD SystemInformation[2]; // [rsp+30h] [rbp-38h] BYREF
  int v7; // [rsp+50h] [rbp-18h]
  _BYTE v8[4]; // [rsp+54h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a1;
  v7 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v2 = NtQuerySystemInformation(SystemEmulationBasicInformation|0x80, SystemInformation, 0x24u, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x26,
      (int)"onecore\\base\\ci\\management\\dll\\ntextensions.cpp",
      (const char *)(unsigned int)v2,
      v4);
  std::vector<unsigned char>::vector<unsigned char>(a1, 32);
  std::copy<unsigned char *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>>(
    &v5,
    (char *)SystemInformation + 4,
    (__int64)v8,
    *a1);
  return a1;
}

```

## disassembly

```asm
0x18000e0a0  push    rbx
0x18000e0a2  sub     rsp, 60h
0x18000e0a6  mov     rax, cs:__security_cookie
0x18000e0ad  xor     rax, rsp
0x18000e0b0  mov     [rsp+68h+var_10], rax
0x18000e0b5  mov     [rsp+68h+var_40], rcx
0x18000e0ba  lea     rdx, [rsp+68h+SystemInformation]; SystemInformation
0x18000e0bf  xor     eax, eax
0x18000e0c1  xorps   xmm0, xmm0
0x18000e0c4  mov     rbx, rcx
0x18000e0c7  mov     [rsp+68h+var_18], eax
0x18000e0cb  xor     r9d, r9d; ReturnLength
0x18000e0ce  mov     ecx, 0BEh; SystemInformationClass
0x18000e0d3  movups  [rsp+68h+SystemInformation], xmm0
0x18000e0d8  lea     r8d, [rax+24h]; SystemInformationLength
0x18000e0dc  movups  [rsp+68h+var_28], xmm0
0x18000e0e1  call    cs:__imp_NtQuerySystemInformation
0x18000e0e7  test    eax, eax
0x18000e0e9  jns     short loc_18000E105
0x18000e0eb  mov     rcx, [rsp+68h]; this
0x18000e0f0  lea     r8, aOnecoreBaseCiM_0; "onecore\\base\\ci\\management\\dll\\nte"...
0x18000e0f7  mov     r9d, eax; char *
0x18000e0fa  mov     edx, 26h ; '&'; void *
0x18000e0ff  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18000e105  mov     edx, 20h ; ' '
0x18000e10a  mov     rcx, rbx
0x18000e10d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000e112  mov     r9, [rbx]
0x18000e115  lea     r8, [rsp+68h+var_14]
0x18000e11a  lea     rdx, [rsp+68h+SystemInformation+4]
0x18000e11f  lea     rcx, [rsp+68h+var_40]
0x18000e124  call    ??$copy@PEAEV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@PEAE0V10@@Z; std::copy<uchar *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>>(uchar *,uchar *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>)
0x18000e129  mov     rax, rbx
0x18000e12c  mov     rcx, [rsp+68h+var_10]
0x18000e131  xor     rcx, rsp; StackCookie
0x18000e134  call    __security_check_cookie
0x18000e139  add     rsp, 60h
0x18000e13d  pop     rbx
0x18000e13e  retn
```
