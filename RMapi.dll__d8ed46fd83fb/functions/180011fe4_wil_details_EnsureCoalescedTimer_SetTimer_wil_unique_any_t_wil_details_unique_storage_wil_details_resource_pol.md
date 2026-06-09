# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180011fe4`
- end: `0x18001203b`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014250`
- `0x18001432c`
- `0x18001473c`

## callees

- `0x18000d2a0`
- `0x180011fe4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001201f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001201f`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

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
0x180011fe4  push    rbx
0x180011fe6  sub     rsp, 30h
0x180011fea  mov     rax, cs:__security_cookie
0x180011ff1  xor     rax, rsp
0x180011ff4  mov     [rsp+38h+var_10], rax
0x180011ff9  mov     rcx, [rcx]; pti
0x180011ffc  mov     rbx, rdx
0x180011fff  test    rcx, rcx
0x180012002  jz      short loc_180012028
0x180012004  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18001200b  shr     r8d, 2
0x18001200f  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012014  mov     r9d, r8d; msWindowLength
0x180012017  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001201c  xor     r8d, r8d; msPeriod
0x18001201f  call    cs:__imp_SetThreadpoolTimer
0x180012025  mov     byte ptr [rbx], 1
0x180012028  mov     rcx, [rsp+38h+var_10]
0x18001202d  xor     rcx, rsp; StackCookie
0x180012030  call    __security_check_cookie
0x180012035  add     rsp, 30h
0x180012039  pop     rbx
0x18001203a  retn
```
