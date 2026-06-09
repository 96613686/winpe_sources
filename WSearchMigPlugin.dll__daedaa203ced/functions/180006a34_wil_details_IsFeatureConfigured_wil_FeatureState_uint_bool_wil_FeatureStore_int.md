# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180006a34`
- end: `0x180006b16`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009950`

## callees

- `0x1800058e8`
- `0x180006a34`
- `0x180009270`
- `0x18000a538`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, int a2, unsigned __int8 a3, int a4, __int64 a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  int v8; // ebp
  volatile __int32 v9; // r9d
  unsigned int v11; // r14d
  int v12; // r9d
  int FeatureState; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  v8 = (int)a1;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(_DWORD *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((_DWORD)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  FeatureState = wil_QueryFeatureState(v8, a2, v5, v12, (__int64)&v17, a5);
  v14 = v17;
  v15 = FeatureState != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x180006a34  mov     [rsp+arg_0], rbx
0x180006a39  mov     [rsp+arg_8], rbp
0x180006a3e  push    rsi
0x180006a3f  push    rdi
0x180006a40  push    r14
0x180006a42  sub     rsp, 30h
0x180006a46  test    r9d, r9d
0x180006a49  movzx   edi, r8b
0x180006a4d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180006a54  mov     esi, edx
0x180006a56  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006a5d  mov     rbp, rcx
0x180006a60  cmovnz  rbx, rax
0x180006a64  mov     r9d, [rbx]
0x180006a67  mov     eax, r9d
0x180006a6a  and     al, 3
0x180006a6c  cmp     al, 2
0x180006a6e  jnz     short loc_180006A77
0x180006a70  xor     al, al
0x180006a72  jmp     loc_180006B03
0x180006a77  test    r9b, 2
0x180006a7b  jnz     short loc_180006AE3
0x180006a7d  mov     [rsp+48h+arg_18], 1
0x180006a85  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006a8a  mov     rcx, [rsp+48h+arg_20]
0x180006a8f  mov     r14d, eax
0x180006a92  mov     [rsp+48h+var_20], rcx
0x180006a97  lea     rax, [rsp+48h+arg_18]
0x180006a9c  mov     rcx, rbp
0x180006a9f  mov     [rsp+48h+var_28], rax
0x180006aa4  mov     r8d, edi
0x180006aa7  mov     edx, esi
0x180006aa9  call    wil_QueryFeatureState
0x180006aae  mov     edx, [rsp+48h+arg_18]
0x180006ab2  test    eax, eax
0x180006ab4  mov     ecx, edx
0x180006ab6  setnz   dil
0x180006aba  neg     ecx
0x180006abc  sbb     r8d, r8d
0x180006abf  neg     r8d
0x180006ac2  add     r8d, 6
0x180006ac6  xchg    r8d, [rbx]
0x180006ac9  test    edx, edx
0x180006acb  jnz     short loc_180006ADE
0x180006acd  test    r8b, 4
0x180006ad1  jnz     short loc_180006ADE
0x180006ad3  mov     r8d, r14d
0x180006ad6  mov     rcx, rbx
0x180006ad9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006ade  mov     al, dil
0x180006ae1  jmp     short loc_180006B03
0x180006ae3  mov     rax, [rsp+48h+arg_20]
0x180006ae8  mov     r8d, edi
0x180006aeb  mov     [rsp+48h+var_20], rax
0x180006af0  mov     [rsp+48h+var_28], 0
0x180006af9  call    wil_QueryFeatureState
0x180006afe  test    eax, eax
0x180006b00  setnz   al
0x180006b03  mov     rbx, [rsp+48h+arg_0]
0x180006b08  mov     rbp, [rsp+48h+arg_8]
0x180006b0d  add     rsp, 30h
0x180006b11  pop     r14
0x180006b13  pop     rdi
0x180006b14  pop     rsi
0x180006b15  retn
```
