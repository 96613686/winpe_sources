# GetPersistedRegistryLocationTargetPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800226e4`
- end: `0x1800227de`
- name: `?GetPersistedRegistryLocationTargetPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@0@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800223cc`
- `0x1800227e4`
- `0x18002297c`

## callees

- `0x18000a1bc`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x180013dcc`
- `0x1800151fc`
- `0x1800198f4`
- `0x1800226e4`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002272d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180022796`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002272d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180022796`

## string_xrefs

- `0x180022740`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`
- `0x1800227a8`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetPersistedRegistryLocationTargetPath(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int PersistedRegistryLocationW; // eax
  _QWORD v13[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v15; // [rsp+88h] [rbp+10h] BYREF

  v15 = 0;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( (unsigned int)GetPersistedRegistryLocationW(v6, v7, 0, 0) != 234 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v15);
  std::vector<unsigned short>::vector<unsigned short>(v13, (unsigned int)v15);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(v8, v9, v10, (v13[1] - v10) >> 1);
  if ( PersistedRegistryLocationW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x17,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)PersistedRegistryLocationW,
      0);
  std::wstring::wstring(a1, v13[0]);
  std::vector<unsigned short>::_Tidy(v13);
  return a1;
}

```

## disassembly

```asm
0x1800226e4  mov     rax, rsp
0x1800226e7  push    rbx
0x1800226e8  push    rbp
0x1800226e9  push    rsi
0x1800226ea  push    rdi
0x1800226eb  sub     rsp, 58h
0x1800226ef  mov     rsi, r8
0x1800226f2  mov     rbp, rdx
0x1800226f5  mov     rbx, rcx
0x1800226f8  mov     dword ptr [rax+10h], 0
0x1800226ff  mov     rcx, r8
0x180022702  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022707  mov     rdx, rax
0x18002270a  mov     rcx, rbp
0x18002270d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022712  mov     rdi, [rsp+78h]
0x180022717  lea     rcx, [rsp+78h+arg_8]
0x18002271f  mov     qword ptr [rsp+78h+var_58], rcx; int
0x180022724  xor     r9d, r9d
0x180022727  xor     r8d, r8d
0x18002272a  mov     rcx, rax
0x18002272d  call    cs:__imp_GetPersistedRegistryLocationW
0x180022733  cmp     eax, 0EAh
0x180022738  jz      short loc_180022755
0x18002273a  mov     r9d, 8000FFFFh; char *
0x180022740  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x180022747  mov     edx, 14h; void *
0x18002274c  mov     rcx, rdi; this
0x18002274f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022755  mov     edx, [rsp+78h+arg_8]
0x18002275c  lea     rcx, [rsp+78h+var_40]
0x180022761  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180022766  nop
0x180022767  mov     r8, [rsp+78h+var_40]
0x18002276c  mov     rcx, rsi
0x18002276f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022774  mov     rdx, rax
0x180022777  mov     rcx, rbp
0x18002277a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002277f  mov     r9, [rsp+78h+var_38]
0x180022784  sub     r9, r8
0x180022787  sar     r9, 1
0x18002278a  mov     qword ptr [rsp+78h+var_58], 0; unsigned int
0x180022793  mov     rcx, rax
0x180022796  call    cs:__imp_GetPersistedRegistryLocationW
0x18002279c  mov     rcx, [rsp+78h]; this
0x1800227a1  test    eax, eax
0x1800227a3  jz      short loc_1800227BA
0x1800227a5  mov     r9d, eax; char *
0x1800227a8  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800227af  mov     edx, 17h; void *
0x1800227b4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800227ba  mov     rdx, [rsp+78h+var_40]
0x1800227bf  mov     rcx, rbx
0x1800227c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800227c7  nop
0x1800227c8  lea     rcx, [rsp+78h+var_40]
0x1800227cd  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800227d2  mov     rax, rbx
0x1800227d5  add     rsp, 58h
0x1800227d9  pop     rdi
0x1800227da  pop     rsi
0x1800227db  pop     rbp
0x1800227dc  pop     rbx
0x1800227dd  retn
```
