# wil::details::shared_object<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)

- ea: `0x14000e5e0`
- end: `0x14000e631`
- name: `?reset@?$shared_object@V?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x140005884`
- `0x140006b80`

## callees

- `0x140003218`
- `0x1400058bc`
- `0x14000e5e0`

## pseudocode

```c
void __fastcall wil::details::shared_object<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rdi

  v2 = *a1;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *a1;
      if ( *a1 )
      {
        wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>((__int64)(v3 + 2));
        operator delete((void *)v3);
      }
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x14000e5e0  mov     [rsp+arg_0], rbx
0x14000e5e5  push    rdi
0x14000e5e6  sub     rsp, 20h
0x14000e5ea  mov     rbx, rcx
0x14000e5ed  mov     rcx, [rcx]
0x14000e5f0  test    rcx, rcx
0x14000e5f3  jz      short loc_14000E626
0x14000e5f5  or      eax, 0FFFFFFFFh
0x14000e5f8  lock xadd [rcx], eax
0x14000e5fc  cmp     eax, 1
0x14000e5ff  jnz     short loc_14000E61F
0x14000e601  mov     rdi, [rbx]
0x14000e604  test    rdi, rdi
0x14000e607  jz      short loc_14000E61F
0x14000e609  lea     rcx, [rdi+8]
0x14000e60d  call    ??1?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000e612  mov     edx, 110h; unsigned __int64
0x14000e617  mov     rcx, rdi; void *
0x14000e61a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e61f  mov     qword ptr [rbx], 0
0x14000e626  mov     rbx, [rsp+28h+arg_0]
0x14000e62b  add     rsp, 20h
0x14000e62f  pop     rdi
0x14000e630  retn
```
