# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001ded0`
- end: `0x18001df43`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001df50`

## callees

- `0x18001d7d0`
- `0x18001ded0`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  const struct _GUID *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9

  v3 = 0;
  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v5 = v6;
    goto LABEL_8;
  }
  if ( (unsigned int)InlineIsEqualGUID(v4, &GUID_f1b926d1_1796_597a_9bea_6c6449d03eef) )
  {
LABEL_5:
    *v8 = v6;
LABEL_8:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    return v3;
  }
  if ( (unsigned int)InlineIsEqualGUID(v7, &GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719) )
  {
    v6 = v9 + 8;
    goto LABEL_5;
  }
  return (unsigned int)-2147467262;
}

```

## disassembly

```asm
0x18001ded0  push    rbx
0x18001ded2  sub     rsp, 20h
0x18001ded6  mov     r10, rdx
0x18001ded9  mov     r9, rcx
0x18001dedc  xor     ebx, ebx
0x18001dede  mov     [r8], rbx
0x18001dee1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18001dee8  mov     rcx, r10; struct _GUID *
0x18001deeb  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001def0  test    eax, eax
0x18001def2  jnz     short loc_18001DF27
0x18001def4  lea     rdx, _GUID_f1b926d1_1796_597a_9bea_6c6449d03eef; struct _GUID *
0x18001defb  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001df00  test    eax, eax
0x18001df02  jnz     short loc_18001DF18
0x18001df04  lea     rdx, _GUID_6e1c7129_61e0_5d88_9fd4_f3ce65a05719; struct _GUID *
0x18001df0b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001df10  test    eax, eax
0x18001df12  jz      short loc_18001DF20
0x18001df14  add     r9, 8
0x18001df18  mov     rax, r9
0x18001df1b  mov     [r8], rax
0x18001df1e  jmp     short loc_18001DF2A
0x18001df20  mov     ebx, 80004002h
0x18001df25  jmp     short loc_18001DF3A
0x18001df27  mov     [r8], r9
0x18001df2a  mov     rax, [r9]
0x18001df2d  mov     rcx, r9
0x18001df30  mov     rax, [rax+8]
0x18001df34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df39  nop
0x18001df3a  mov     eax, ebx
0x18001df3c  add     rsp, 20h
0x18001df40  pop     rbx
0x18001df41  retn
```
