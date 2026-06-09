# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180053728`
- end: `0x18005376a`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `66`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180055f04`
- `0x180056354`
- `0x18006e0dc`

## callees

- `0x180053728`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180053754`
- `KERNEL32!SetThreadpoolTimer` at `0x180053754`

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
0x180053728  push    rbx
0x18005372a  sub     rsp, 20h
0x18005372e  mov     rcx, [rcx]; pti
0x180053731  mov     rbx, rdx
0x180053734  test    rcx, rcx
0x180053737  jz      short loc_180053763
0x180053739  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x180053740  shr     r8d, 2
0x180053744  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180053749  mov     r9d, r8d; msWindowLength
0x18005374c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180053751  xor     r8d, r8d; msPeriod
0x180053754  call    cs:__imp_SetThreadpoolTimer
0x18005375b  nop     dword ptr [rax+rax+00h]
0x180053760  mov     byte ptr [rbx], 1
0x180053763  add     rsp, 20h
0x180053767  pop     rbx
0x180053768  retn
```
