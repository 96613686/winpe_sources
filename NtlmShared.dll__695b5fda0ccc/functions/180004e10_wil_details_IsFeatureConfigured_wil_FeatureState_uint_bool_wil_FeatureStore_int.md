# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180004e10`
- end: `0x180004ef2`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800076a0`

## callees

- `0x180003d18`
- `0x180004e10`
- `0x180007058`
- `0x1800098ac`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  __int64 v9; // r9
  unsigned int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(unsigned int *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v13 = wil_QueryFeatureState((__int64)a1, a2, v5, v12, &v17, a5);
  v14 = v17;
  v15 = v13 != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x180004e10  mov     [rsp+arg_0], rbx
0x180004e15  mov     [rsp+arg_8], rbp
0x180004e1a  push    rsi
0x180004e1b  push    rdi
0x180004e1c  push    r14
0x180004e1e  sub     rsp, 30h
0x180004e22  test    r9d, r9d
0x180004e25  movzx   edi, r8b
0x180004e29  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180004e30  mov     esi, edx
0x180004e32  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180004e39  mov     rbp, rcx
0x180004e3c  cmovnz  rbx, rax
0x180004e40  mov     r9d, [rbx]
0x180004e43  mov     eax, r9d
0x180004e46  and     al, 3
0x180004e48  cmp     al, 2
0x180004e4a  jnz     short loc_180004E53
0x180004e4c  xor     al, al
0x180004e4e  jmp     loc_180004EDF
0x180004e53  test    r9b, 2
0x180004e57  jnz     short loc_180004EBF
0x180004e59  mov     [rsp+48h+arg_18], 1
0x180004e61  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004e66  mov     rcx, [rsp+48h+arg_20]
0x180004e6b  mov     r14d, eax
0x180004e6e  mov     [rsp+48h+var_20], rcx
0x180004e73  lea     rax, [rsp+48h+arg_18]
0x180004e78  mov     rcx, rbp
0x180004e7b  mov     [rsp+48h+var_28], rax
0x180004e80  mov     r8d, edi
0x180004e83  mov     edx, esi
0x180004e85  call    wil_QueryFeatureState
0x180004e8a  mov     edx, [rsp+48h+arg_18]
0x180004e8e  test    eax, eax
0x180004e90  mov     ecx, edx
0x180004e92  setnz   dil
0x180004e96  neg     ecx
0x180004e98  sbb     r8d, r8d
0x180004e9b  neg     r8d
0x180004e9e  add     r8d, 6
0x180004ea2  xchg    r8d, [rbx]
0x180004ea5  test    edx, edx
0x180004ea7  jnz     short loc_180004EBA
0x180004ea9  test    r8b, 4
0x180004ead  jnz     short loc_180004EBA
0x180004eaf  mov     r8d, r14d
0x180004eb2  mov     rcx, rbx
0x180004eb5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180004eba  mov     al, dil
0x180004ebd  jmp     short loc_180004EDF
0x180004ebf  mov     rax, [rsp+48h+arg_20]
0x180004ec4  mov     r8d, edi
0x180004ec7  mov     [rsp+48h+var_20], rax
0x180004ecc  mov     [rsp+48h+var_28], 0
0x180004ed5  call    wil_QueryFeatureState
0x180004eda  test    eax, eax
0x180004edc  setnz   al
0x180004edf  mov     rbx, [rsp+48h+arg_0]
0x180004ee4  mov     rbp, [rsp+48h+arg_8]
0x180004ee9  add     rsp, 30h
0x180004eed  pop     r14
0x180004eef  pop     rdi
0x180004ef0  pop     rsi
0x180004ef1  retn
```
