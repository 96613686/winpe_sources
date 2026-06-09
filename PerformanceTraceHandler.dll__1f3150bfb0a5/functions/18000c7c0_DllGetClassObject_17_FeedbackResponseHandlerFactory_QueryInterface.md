# _DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::QueryInterface

- ea: `0x18000c7c0`
- end: `0x18000c842`
- name: `_DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::QueryInterface`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e980`

## callees

- `0x180007f3c`
- `0x18000c7c0`
- `0x18001c010`

## string_xrefs

- `0x18000c7ce`: `pcshell\shell\performancetracehandler\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 && a2[1] == *(_QWORD *)IID_IUnknown.Data4
      || *a2 == *(_QWORD *)&IID_IClassFactory.Data1 && a2[1] == *(_QWORD *)IID_IClassFactory.Data4 )
    {
      *a3 = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      return 0;
    }
    else
    {
      return 2147500034LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (int)"pcshell\\shell\\performancetracehandler\\dll\\dllmain.cpp",
      (const char *)0x80004003LL);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000c7c0  sub     rsp, 28h
0x18000c7c4  test    r8, r8
0x18000c7c7  jnz     short loc_18000C7EC
0x18000c7c9  mov     rcx, [rsp+28h]; this
0x18000c7ce  lea     r8, aPcshellShellPe_0; "pcshell\\shell\\performancetracehandler"...
0x18000c7d5  mov     r9d, 80004003h; char *
0x18000c7db  mov     edx, 60h ; '`'; void *
0x18000c7e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7e5  mov     eax, 80004003h
0x18000c7ea  jmp     short loc_18000C83D
0x18000c7ec  mov     qword ptr [r8], 0
0x18000c7f3  mov     rax, [rdx]
0x18000c7f6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c7fd  jnz     short loc_18000C80C
0x18000c7ff  mov     rax, [rdx+8]
0x18000c803  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c80a  jz      short loc_18000C825
0x18000c80c  mov     rax, [rdx]
0x18000c80f  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000c816  jnz     short loc_18000C838
0x18000c818  mov     rax, [rdx+8]
0x18000c81c  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000c823  jnz     short loc_18000C838
0x18000c825  mov     [r8], rcx
0x18000c828  mov     rax, [rcx]
0x18000c82b  mov     rax, [rax+8]
0x18000c82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c834  xor     eax, eax
0x18000c836  jmp     short loc_18000C83D
0x18000c838  mov     eax, 80004002h
0x18000c83d  add     rsp, 28h
0x18000c841  retn
```
