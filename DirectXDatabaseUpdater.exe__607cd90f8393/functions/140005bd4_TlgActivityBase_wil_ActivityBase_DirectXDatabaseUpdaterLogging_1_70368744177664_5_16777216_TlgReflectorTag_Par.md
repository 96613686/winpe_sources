# _TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(void)

- ea: `0x140005bd4`
- end: `0x140005c0e`
- name: `??1?$_TlgActivityBase@V?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0EAAAAAAAAAAA@$04@@IEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400058bc`

## callees

- `0x1400050c8`
- `0x140005bd4`
- `0x140009460`

## pseudocode

```c
void __fastcall _TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(
        _DWORD *a1)
{
  ULONG *v2; // rax

  if ( *a1 == 1 )
  {
    *a1 = 2;
    v2 = (ULONG *)wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v2);
  }
  *a1 = 3;
}

```

## disassembly

```asm
0x140005bd4  mov     [rsp+arg_0], rbx
0x140005bd9  push    rdi
0x140005bda  sub     rsp, 20h
0x140005bde  cmp     dword ptr [rcx], 1
0x140005be1  mov     rdi, rcx
0x140005be4  jnz     short loc_140005BFD
0x140005be6  mov     dword ptr [rcx], 2
0x140005bec  call    ?Provider@?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::Provider(void)
0x140005bf1  mov     rcx, rax
0x140005bf4  lea     rdx, [rdi+8]
0x140005bf8  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x140005bfd  mov     rbx, [rsp+28h+arg_0]
0x140005c02  mov     dword ptr [rdi], 3
0x140005c08  add     rsp, 20h
0x140005c0c  pop     rdi
0x140005c0d  retn
```
