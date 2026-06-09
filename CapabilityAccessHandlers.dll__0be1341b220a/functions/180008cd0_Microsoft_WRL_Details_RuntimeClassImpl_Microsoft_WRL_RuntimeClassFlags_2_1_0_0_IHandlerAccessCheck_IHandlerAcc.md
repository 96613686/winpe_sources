# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerAccessChange>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008cd0`
- end: `0x180008d4c`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008d60`

## callees

- `0x1800017d0`
- `0x18000302c`
- `0x180008cd0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerAccessChange>::QueryInterface(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  _QWORD *v6; // r8
  __int64 v7; // r9
  _DWORD *v8; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046, a3, a1) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_c5e24244_3c21_4b41_8b86_7e671a675702, v4, v5) )
  {
    *v6 = v7;
    CanCastTo = 0;
LABEL_5:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>::CanCastTo(
                v7 + 8,
                v8,
                v6);
  if ( CanCastTo >= 0 )
    goto LABEL_5;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180008cd0  push    rbx
0x180008cd2  sub     rsp, 20h
0x180008cd6  mov     r10, rdx
0x180008cd9  mov     r9, rcx
0x180008cdc  mov     qword ptr [r8], 0
0x180008ce3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008cea  mov     rcx, r10
0x180008ced  call    InlineIsEqualGUID
0x180008cf2  test    eax, eax
0x180008cf4  jnz     short loc_180008D30
0x180008cf6  lea     rdx, _GUID_c5e24244_3c21_4b41_8b86_7e671a675702
0x180008cfd  call    InlineIsEqualGUID
0x180008d02  test    eax, eax
0x180008d04  jz      short loc_180008D0D
0x180008d06  mov     [r8], r9
0x180008d09  xor     ebx, ebx
0x180008d0b  jmp     short loc_180008D1F
0x180008d0d  lea     rcx, [r9+8]
0x180008d11  mov     rdx, r10
0x180008d14  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerAccessChange@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>::CanCastTo(_GUID const &,void * *,bool *)
0x180008d19  mov     ebx, eax
0x180008d1b  test    eax, eax
0x180008d1d  js      short loc_180008D44
0x180008d1f  mov     rcx, [r8]
0x180008d22  mov     rax, [rcx]
0x180008d25  mov     rax, [rax+8]
0x180008d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2e  jmp     short loc_180008D44
0x180008d30  mov     [r8], r9
0x180008d33  mov     rax, [r9]
0x180008d36  mov     rcx, r9
0x180008d39  mov     rax, [rax+8]
0x180008d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d42  xor     ebx, ebx
0x180008d44  mov     eax, ebx
0x180008d46  add     rsp, 20h
0x180008d4a  pop     rbx
0x180008d4b  retn
```
