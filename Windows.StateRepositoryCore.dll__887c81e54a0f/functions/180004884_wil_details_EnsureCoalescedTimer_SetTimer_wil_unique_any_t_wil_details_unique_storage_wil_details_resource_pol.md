# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180004884`
- end: `0x1800048bf`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002dcc`
- `0x180002e48`
- `0x180007d50`

## callees

- `0x180004884`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048b0`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x180004884  push    rbx
0x180004886  sub     rsp, 20h
0x18000488a  mov     rcx, [rcx]; pti
0x18000488d  mov     rbx, rdx
0x180004890  test    rcx, rcx
0x180004893  jz      short loc_1800048B9
0x180004895  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000489c  shr     r8d, 2
0x1800048a0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800048a5  mov     r9d, r8d; msWindowLength
0x1800048a8  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x1800048ad  xor     r8d, r8d; msPeriod
0x1800048b0  call    cs:__imp_SetThreadpoolTimer
0x1800048b6  mov     byte ptr [rbx], 1
0x1800048b9  add     rsp, 20h
0x1800048bd  pop     rbx
0x1800048be  retn
```
