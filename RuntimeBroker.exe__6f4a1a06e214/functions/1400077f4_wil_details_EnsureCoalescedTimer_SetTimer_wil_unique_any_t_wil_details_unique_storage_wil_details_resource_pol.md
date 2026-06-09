# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x1400077f4`
- end: `0x14000782f`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007474`
- `0x14000850c`
- `0x14000a1ac`

## callees

- `0x1400077f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007820`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007820`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (_FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x1400077f4  push    rbx
0x1400077f6  sub     rsp, 20h
0x1400077fa  mov     rcx, [rcx]; pti
0x1400077fd  mov     rbx, rdx
0x140007800  test    rcx, rcx
0x140007803  jz      short loc_140007829
0x140007805  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x14000780c  shr     r8d, 2
0x140007810  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x140007815  mov     r9d, r8d; msWindowLength
0x140007818  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x14000781d  xor     r8d, r8d; msPeriod
0x140007820  call    cs:__imp_SetThreadpoolTimer
0x140007826  mov     byte ptr [rbx], 1
0x140007829  add     rsp, 20h
0x14000782d  pop     rbx
0x14000782e  retn
```
