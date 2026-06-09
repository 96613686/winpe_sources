# Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(TrustLevel *)

- ea: `0x180003cd0`
- end: `0x180003cfc`
- name: `?GetTrustLevel@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAJPEAW4TrustLevel@@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003d10`

## callees

- `0x180003cd0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(
        __int64 a1,
        int *a2)
{
  __int64 v2; // rax
  int v4; // eax

  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 )
    v4 = (*(__int64 (**)(void))(v2 + 16))();
  else
    v4 = 2;
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x180003cd0  push    rbx
0x180003cd2  sub     rsp, 20h
0x180003cd6  mov     rax, [rcx+20h]
0x180003cda  mov     rbx, rdx
0x180003cdd  test    rax, rax
0x180003ce0  jz      short loc_180003CED
0x180003ce2  mov     rax, [rax+10h]
0x180003ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ceb  jmp     short loc_180003CF2
0x180003ced  mov     eax, 2
0x180003cf2  mov     [rbx], eax
0x180003cf4  xor     eax, eax
0x180003cf6  add     rsp, 20h
0x180003cfa  pop     rbx
0x180003cfb  retn
```
