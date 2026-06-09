# WcmCommon::details::TPEnvironment::create_tp(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)

- ea: `0x180005390`
- end: `0x1800053ed`
- name: `?create_tp@TPEnvironment@details@WcmCommon@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000521c`
- `0x180009e14`

## callees

- `0x180005390`
- `0x180019570`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800053be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800053be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PTP_WORK *__fastcall WcmCommon::details::TPEnvironment::create_tp(
        __int64 a1,
        PTP_WORK *a2,
        void (__stdcall *a3)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work),
        void *a4)
{
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a2 = 0;
  if ( !*(_QWORD *)(a1 + 72) )
    a1 = 0;
  ThreadpoolWork = CreateThreadpoolWork(a3, a4, (PTP_CALLBACK_ENVIRON)a1);
  *a2 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x75, v6, v7);
  return a2;
}

```

## disassembly

```asm
0x180005390  mov     [rsp+arg_8], rdx
0x180005395  push    rbx
0x180005396  sub     rsp, 30h
0x18000539a  mov     r10, r8
0x18000539d  mov     rbx, rdx
0x1800053a0  mov     [rsp+38h+var_18], 0
0x1800053a8  xor     eax, eax
0x1800053aa  mov     [rdx], rax
0x1800053ad  cmp     [rcx+48h], rax
0x1800053b1  cmovz   rcx, rax
0x1800053b5  mov     r8, rcx; pcbe
0x1800053b8  mov     rdx, r9; pv
0x1800053bb  mov     rcx, r10; pfnwk
0x1800053be  call    cs:__imp_CreateThreadpoolWork
0x1800053c4  mov     [rbx], rax
0x1800053c7  mov     [rsp+38h+var_18], 1
0x1800053cf  test    rax, rax
0x1800053d2  jz      short loc_1800053DD
0x1800053d4  mov     rax, rbx
0x1800053d7  add     rsp, 30h
0x1800053db  pop     rbx
0x1800053dc  retn
0x1800053dd  mov     rcx, [rsp+38h]; this
0x1800053e2  mov     edx, 75h ; 'u'; void *
0x1800053e7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
