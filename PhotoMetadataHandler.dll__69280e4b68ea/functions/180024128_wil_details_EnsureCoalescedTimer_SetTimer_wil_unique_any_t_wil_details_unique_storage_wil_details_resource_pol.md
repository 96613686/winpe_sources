# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180024128`
- end: `0x18002416a`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180022f44`
- `0x180022fc8`

## callees

- `0x180024128`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024154`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024154`

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
0x180024128  push    rbx
0x18002412a  sub     rsp, 20h
0x18002412e  mov     rcx, [rcx]; pti
0x180024131  mov     rbx, rdx
0x180024134  test    rcx, rcx
0x180024137  jz      short loc_180024163
0x180024139  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x180024140  shr     r8d, 2
0x180024144  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180024149  mov     r9d, r8d; msWindowLength
0x18002414c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180024151  xor     r8d, r8d; msPeriod
0x180024154  call    cs:__imp_SetThreadpoolTimer
0x18002415b  nop     dword ptr [rax+rax+00h]
0x180024160  mov     byte ptr [rbx], 1
0x180024163  add     rsp, 20h
0x180024167  pop     rbx
0x180024168  retn
```
