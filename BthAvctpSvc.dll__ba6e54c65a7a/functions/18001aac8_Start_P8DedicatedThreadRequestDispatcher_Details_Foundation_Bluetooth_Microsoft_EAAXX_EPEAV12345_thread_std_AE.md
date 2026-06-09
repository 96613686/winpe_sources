# ??$_Start@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@thread@std@@AEAAX$$QEAP8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_E$$QEAPEAV23456@@Z

- ea: `0x18001aac8`
- end: `0x18001ab5e`
- name: `??$_Start@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@thread@std@@AEAAX$$QEAP8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_E$$QEAPEAV23456@@Z`
- size: `150`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b274`

## callees

- `0x1800021dc`
- `0x18001aac8`
- `0x18001b6b0`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ab57`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ab57`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001ab1b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001ab1b`

## pseudocode

```c
__int64 __fastcall ____Start_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__thread_std__AEAAX__QEAP8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_E__QEAPEAV23456__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v9; // [rsp+40h] [rbp+8h] BYREF

  v6 = operator new(0x10u);
  *v6 = *a3;
  v6[1] = *a2;
  v9 = v6;
  v7 = _o__beginthreadex(
         0,
         0,
         ____Invoke_V__tuple_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__std___0A__00_thread_std__CAIPEAX_Z,
         v6,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v7;
  if ( !v7 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18001AB5DLL);
  }
  v9 = 0;
  return __1__unique_ptr_V__tuple_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__std__U__default_delete_V__tuple_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__std___2__std__QEAA_XZ(&v9);
}

```

## disassembly

```asm
0x18001aac8  mov     [rsp+arg_8], rbx
0x18001aacd  mov     [rsp+arg_10], rsi
0x18001aad2  push    rdi
0x18001aad3  sub     rsp, 30h
0x18001aad7  mov     rbx, r8
0x18001aada  mov     rdi, rdx
0x18001aadd  mov     rsi, rcx
0x18001aae0  mov     ecx, 10h; Size
0x18001aae5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aaea  mov     r8, [rbx]
0x18001aaed  mov     [rax], r8
0x18001aaf0  mov     rdx, [rdi]
0x18001aaf3  mov     [rax+8], rdx
0x18001aaf7  mov     [rsp+38h+arg_0], rax
0x18001aafc  lea     rbx, [rsi+8]
0x18001ab00  mov     [rsp+38h+var_10], rbx
0x18001ab05  mov     [rsp+38h+var_18], 0
0x18001ab0d  mov     r9, rax
0x18001ab10  lea     r8, ??$_Invoke@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@$0A@$00@thread@std@@CAIPEAX@Z
0x18001ab17  xor     edx, edx
0x18001ab19  xor     ecx, ecx
0x18001ab1b  call    cs:__imp__o__beginthreadex
0x18001ab21  mov     [rsi], rax
0x18001ab24  test    rax, rax
0x18001ab27  jz      short loc_18001AB4C
0x18001ab29  mov     [rsp+38h+arg_0], 0
0x18001ab32  lea     rcx, [rsp+38h+arg_0]
0x18001ab37  call    ??1?$unique_ptr@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@U?$default_delete@V?$tuple@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@std@@@2@@std@@QEAA@XZ
0x18001ab3c  mov     rbx, [rsp+38h+arg_8]
0x18001ab41  mov     rsi, [rsp+38h+arg_10]
0x18001ab46  add     rsp, 30h
0x18001ab4a  pop     rdi
0x18001ab4b  retn
0x18001ab4c  mov     dword ptr [rbx], 0
0x18001ab52  mov     ecx, 6
0x18001ab57  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
