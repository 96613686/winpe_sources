# CInstallService::AddJob(_DeployJob)

- ea: `0x180017aac`
- end: `0x180017b4f`
- name: `?AddJob@CInstallService@@QEAAJU_DeployJob@@@Z`
- size: `163`
- prototype: `int __high(struct _DeployJob)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000d2cc`
- `0x18000dcb4`

## callees

- `0x18000bbf8`
- `0x180017a38`
- `0x180017aac`
- `0x18001f420`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017b08`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017b08`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInstallService::AddJob(_QWORD *a1, _DeployJob *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rax

  v4 = *a1;
  v5 = std::_List_buy<_DeployJob>::_Buynode<_DeployJob const &>(a1, *a1, *(_QWORD *)(*a1 + 8LL), a2, a2);
  v6 = a1[1];
  if ( v6 == 0x1C71C71C71C71C6LL )
    std::_Xlength_error("list<T> too long");
  a1[1] = v6 + 1;
  *(_QWORD *)(v4 + 8) = v5;
  **(_QWORD **)(v5 + 8) = v5;
  _DeployJob::~_DeployJob(a2);
  return 0;
}

```

## disassembly

```asm
0x180017aac  mov     [rsp+arg_10], rbx
0x180017ab1  mov     [rsp+arg_18], rsi
0x180017ab6  push    rdi
0x180017ab7  sub     rsp, 30h
0x180017abb  mov     rax, cs:__security_cookie
0x180017ac2  xor     rax, rsp
0x180017ac5  mov     [rsp+38h+var_10], rax
0x180017aca  mov     rbx, rdx
0x180017acd  mov     rdi, rcx
0x180017ad0  mov     [rsp+38h+var_18], rdx
0x180017ad5  mov     rsi, [rcx]
0x180017ad8  mov     r9, rdx
0x180017adb  mov     r8, [rsi+8]
0x180017adf  mov     rdx, rsi
0x180017ae2  call    ??$_Buynode@AEBU_DeployJob@@@?$_List_buy@U_DeployJob@@V?$allocator@U_DeployJob@@@std@@@std@@QEAAPEAU?$_List_node@U_DeployJob@@PEAX@1@PEAU21@0AEBU_DeployJob@@@Z; std::_List_buy<_DeployJob>::_Buynode<_DeployJob const &>(std::_List_node<_DeployJob,void *> *,std::_List_node<_DeployJob,void *> *,_DeployJob const &)
0x180017ae7  mov     rdx, rax
0x180017aea  mov     rax, [rdi+8]
0x180017aee  mov     rcx, 1C71C71C71C71C6h
0x180017af8  sub     rcx, rax
0x180017afb  cmp     rcx, 1
0x180017aff  jnb     short loc_180017B15
0x180017b01  lea     rcx, aListTTooLong; "list<T> too long"
0x180017b08  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017b15  inc     rax
0x180017b18  mov     [rdi+8], rax
0x180017b1c  mov     [rsi+8], rdx
0x180017b20  mov     rax, [rdx+8]
0x180017b24  mov     [rax], rdx
0x180017b27  mov     rcx, rbx; this
0x180017b2a  call    ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
0x180017b2f  xor     eax, eax
0x180017b31  mov     rcx, [rsp+38h+var_10]
0x180017b36  xor     rcx, rsp; StackCookie
0x180017b39  call    __security_check_cookie
0x180017b3e  mov     rbx, [rsp+38h+arg_10]
0x180017b43  mov     rsi, [rsp+38h+arg_18]
0x180017b48  add     rsp, 30h
0x180017b4c  pop     rdi
0x180017b4d  retn
```
