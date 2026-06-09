# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180009dd8`
- end: `0x180009e13`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ba5c`
- `0x18001b480`
- `0x18001b4fc`

## callees

- `0x180009dd8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009e04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009e04`

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
0x180009dd8  push    rbx
0x180009dda  sub     rsp, 20h
0x180009dde  mov     rcx, [rcx]; pti
0x180009de1  mov     rbx, rdx
0x180009de4  test    rcx, rcx
0x180009de7  jz      short loc_180009E0D
0x180009de9  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x180009df0  shr     r8d, 2
0x180009df4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180009df9  mov     r9d, r8d; msWindowLength
0x180009dfc  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180009e01  xor     r8d, r8d; msPeriod
0x180009e04  call    cs:__imp_SetThreadpoolTimer
0x180009e0a  mov     byte ptr [rbx], 1
0x180009e0d  add     rsp, 20h
0x180009e11  pop     rbx
0x180009e12  retn
```
