# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x140011b60`
- end: `0x140011be5`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011bf0`

## callees

- `0x14000abb4`
- `0x14000e8cc`
- `0x140011b60`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  void **v6; // r8
  __int64 v7; // r9
  const struct _GUID *v8; // r10
  unsigned int v9; // ebx
  int CanCastTo; // eax

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_b632d79c_0ff8_53ae_b1bd_636f69576fcf) )
  {
    *v6 = (void *)v7;
    v9 = 0;
LABEL_6:
    (*(void (__fastcall **)(void *))(*(_QWORD *)*v6 + 8LL))(*v6);
    return v9;
  }
  CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v7 + 8), v8, v6);
  v9 = -2147467262;
  if ( CanCastTo != -2147467262 )
  {
    v9 = CanCastTo;
    if ( CanCastTo >= 0 )
      goto LABEL_6;
  }
  return v9;
}

```

## disassembly

```asm
0x140011b60  push    rbx
0x140011b62  sub     rsp, 20h
0x140011b66  mov     r10, rdx
0x140011b69  mov     qword ptr [r8], 0
0x140011b70  mov     r9, rcx
0x140011b73  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x140011b7a  mov     rcx, r10; struct _GUID *
0x140011b7d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140011b82  test    eax, eax
0x140011b84  jnz     short loc_140011BC9
0x140011b86  lea     rdx, _GUID_b632d79c_0ff8_53ae_b1bd_636f69576fcf; struct _GUID *
0x140011b8d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140011b92  test    eax, eax
0x140011b94  jz      short loc_140011B9D
0x140011b96  mov     [r8], r9
0x140011b99  xor     ebx, ebx
0x140011b9b  jmp     short loc_140011BB8
0x140011b9d  lea     rcx, [r9+8]; this
0x140011ba1  mov     rdx, r10; struct _GUID *
0x140011ba4  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x140011ba9  mov     ebx, 80004002h
0x140011bae  cmp     eax, ebx
0x140011bb0  jz      short loc_140011BDD
0x140011bb2  mov     ebx, eax
0x140011bb4  test    eax, eax
0x140011bb6  js      short loc_140011BDD
0x140011bb8  mov     rcx, [r8]
0x140011bbb  mov     rax, [rcx]
0x140011bbe  mov     rax, [rax+8]
0x140011bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bc7  jmp     short loc_140011BDD
0x140011bc9  mov     [r8], r9
0x140011bcc  mov     rcx, r9
0x140011bcf  mov     rax, [r9]
0x140011bd2  mov     rax, [rax+8]
0x140011bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bdb  xor     ebx, ebx
0x140011bdd  mov     eax, ebx
0x140011bdf  add     rsp, 20h
0x140011be3  pop     rbx
0x140011be4  retn
```
