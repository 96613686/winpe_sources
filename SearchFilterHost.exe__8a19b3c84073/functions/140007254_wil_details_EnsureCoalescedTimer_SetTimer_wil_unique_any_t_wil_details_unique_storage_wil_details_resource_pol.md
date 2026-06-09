# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x140007254`
- end: `0x14000728f`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009078`
- `0x14000950c`
- `0x140013b5c`

## callees

- `0x140007254`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007280`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007280`

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
0x140007254  push    rbx
0x140007256  sub     rsp, 20h
0x14000725a  mov     rcx, [rcx]; pti
0x14000725d  mov     rbx, rdx
0x140007260  test    rcx, rcx
0x140007263  jz      short loc_140007289
0x140007265  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x14000726c  shr     r8d, 2
0x140007270  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x140007275  mov     r9d, r8d; msWindowLength
0x140007278  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x14000727d  xor     r8d, r8d; msPeriod
0x140007280  call    cs:__imp_SetThreadpoolTimer
0x140007286  mov     byte ptr [rbx], 1
0x140007289  add     rsp, 20h
0x14000728d  pop     rbx
0x14000728e  retn
```
