# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x1800a4080`
- end: `0x1800a4124`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800a444c`
- `0x1800ad1a0`

## callees

- `0x180096010`
- `0x1800970ec`
- `0x1800a4080`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  void **v7; // r8
  __int64 v8; // r9
  int CanCastTo; // ebx
  const struct _GUID *v10; // r10

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_eac84b1b_aafe_4ffc_8146_cf4ac9209912)
      || (unsigned int)InlineIsEqualGUID(v6, &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803) )
    {
      *v7 = (void *)v8;
      CanCastTo = 0;
    }
    else
    {
      CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v8 + 8), v10, v7);
      if ( CanCastTo == -2147467262 )
        CanCastTo = -2147467262;
      if ( CanCastTo < 0 )
        return (unsigned int)CanCastTo;
    }
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v7 + 8LL))(*v7, *(_QWORD *)*v7);
    return (unsigned int)CanCastTo;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x1800a4080  push    rbx
0x1800a4082  sub     rsp, 30h
0x1800a4086  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a408f  mov     r10, rdx
0x1800a4092  mov     r9, rcx
0x1800a4095  mov     qword ptr [r8], 0
0x1800a409c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800a40a3  mov     rcx, r10
0x1800a40a6  call    InlineIsEqualGUID
0x1800a40ab  test    eax, eax
0x1800a40ad  jnz     short loc_1800A4109
0x1800a40af  lea     rdx, _GUID_eac84b1b_aafe_4ffc_8146_cf4ac9209912
0x1800a40b6  call    InlineIsEqualGUID
0x1800a40bb  test    eax, eax
0x1800a40bd  jz      short loc_1800A40C6
0x1800a40bf  mov     [r8], r9
0x1800a40c2  xor     ebx, ebx
0x1800a40c4  jmp     short loc_1800A40F6
0x1800a40c6  add     r9, 8
0x1800a40ca  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x1800a40d1  call    InlineIsEqualGUID
0x1800a40d6  test    eax, eax
0x1800a40d8  jnz     short loc_1800A40BF
0x1800a40da  lea     rcx, [r9+8]; this
0x1800a40de  mov     rdx, r10; struct _GUID *
0x1800a40e1  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x1800a40e6  mov     ebx, eax
0x1800a40e8  mov     eax, 80004002h
0x1800a40ed  cmp     ebx, eax
0x1800a40ef  cmovz   ebx, eax
0x1800a40f2  test    ebx, ebx
0x1800a40f4  js      short loc_1800A4105
0x1800a40f6  mov     rcx, [r8]
0x1800a40f9  mov     rdx, [rcx]
0x1800a40fc  mov     rax, [rdx+8]
0x1800a4100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4105  mov     eax, ebx
0x1800a4107  jmp     short loc_1800A411D
0x1800a4109  mov     [r8], r9
0x1800a410c  mov     rax, [r9]
0x1800a410f  mov     rcx, r9
0x1800a4112  mov     rax, [rax+8]
0x1800a4116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a411b  xor     eax, eax
0x1800a411d  add     rsp, 30h
0x1800a4121  pop     rbx
0x1800a4122  retn
```
