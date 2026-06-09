# AdviseInstance::AdviseInstance(RadioManager *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ulong)

- ea: `0x18001b600`
- end: `0x18001b694`
- name: `??0AdviseInstance@@QEAA@PEAVRadioManager@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z`
- size: `148`
- prototype: `char *__fastcall(char *pv, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dac0`

## callees

- `0x180005e00`
- `0x180006350`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001b67f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001b67f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b63f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b63f`

## string_xrefs

- `0x18001b655`: `CreateThreadpoolWait`
- `0x18001b664`: `onecoreuap\net\mobility\radiomanagement\dll\RadioManagementAPI.h`

## pseudocode

```c
char *__fastcall AdviseInstance::AdviseInstance(char *pv, __int64 a2, _QWORD *a3, int a4)
{
  const char **v5; // rbx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)pv = a2;
  v5 = (const char **)(pv + 8);
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 2) = *a3;
  *a3 = 0;
  *((_DWORD *)pv + 6) = a4;
  ThreadpoolWait = CreateThreadpoolWait(AdviseInstance::TPWaitCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v5,
    ThreadpoolWait);
  wil::details::in1diag3::Throw_IfHandleNullMsg(
    retaddr,
    (void *)0xC1,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\RadioManagementAPI.h",
    *v5,
    "CreateThreadpoolWait",
    v8);
  SetThreadpoolWait((PTP_WAIT)*v5, *((HANDLE *)pv + 2), 0);
  return pv;
}

```

## disassembly

```asm
0x18001b600  mov     [rsp+arg_8], rbx
0x18001b605  mov     [rsp+arg_0], rcx
0x18001b60a  push    rdi
0x18001b60b  sub     rsp, 30h
0x18001b60f  mov     rdi, rcx
0x18001b612  mov     [rcx], rdx
0x18001b615  lea     rbx, [rcx+8]
0x18001b619  mov     qword ptr [rbx], 0
0x18001b620  mov     rax, [r8]
0x18001b623  mov     [rcx+10h], rax
0x18001b627  mov     qword ptr [r8], 0
0x18001b62e  mov     [rcx+18h], r9d
0x18001b632  xor     r8d, r8d; pcbe
0x18001b635  mov     rdx, rcx; pv
0x18001b638  lea     rcx, ?TPWaitCallback@AdviseInstance@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001b63f  call    cs:__imp_CreateThreadpoolWait
0x18001b645  mov     rdx, rax
0x18001b648  mov     rcx, rbx
0x18001b64b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18001b650  mov     rcx, [rsp+38h]; this
0x18001b655  lea     rax, aCreatethreadpo; "CreateThreadpoolWait"
0x18001b65c  mov     [rsp+38h+var_18], rax; void *
0x18001b661  mov     r9, [rbx]; char *
0x18001b664  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobility\\radiomanagem"...
0x18001b66b  mov     edx, 0C1h; void *
0x18001b670  call    ?Throw_IfHandleNullMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleNullMsg(void *,uint,char const *,void *,char const *,...)
0x18001b675  xor     r8d, r8d; pftTimeout
0x18001b678  mov     rdx, [rdi+10h]; h
0x18001b67c  mov     rcx, [rbx]; pwa
0x18001b67f  call    cs:__imp_SetThreadpoolWait
0x18001b685  nop
0x18001b686  mov     rax, rdi
0x18001b689  mov     rbx, [rsp+38h+arg_8]
0x18001b68e  add     rsp, 30h
0x18001b692  pop     rdi
0x18001b693  retn
```
