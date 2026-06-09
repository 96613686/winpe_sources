# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x140001c00`
- end: `0x140001c3b`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140001a30`
- `0x140001b18`

## callees

- `0x140001c00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140001c2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140001c2c`

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
0x140001c00  push    rbx
0x140001c02  sub     rsp, 20h
0x140001c06  mov     rcx, [rcx]; pti
0x140001c09  mov     rbx, rdx
0x140001c0c  test    rcx, rcx
0x140001c0f  jz      short loc_140001C35
0x140001c11  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x140001c18  shr     r8d, 2
0x140001c1c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x140001c21  mov     r9d, r8d; msWindowLength
0x140001c24  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x140001c29  xor     r8d, r8d; msPeriod
0x140001c2c  call    cs:__imp_SetThreadpoolTimer
0x140001c32  mov     byte ptr [rbx], 1
0x140001c35  add     rsp, 20h
0x140001c39  pop     rbx
0x140001c3a  retn
```
