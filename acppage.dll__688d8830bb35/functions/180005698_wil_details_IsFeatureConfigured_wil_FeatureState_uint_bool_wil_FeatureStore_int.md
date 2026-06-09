# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005698`
- end: `0x18000577a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007d00`

## callees

- `0x1800044e4`
- `0x180005698`
- `0x180007690`
- `0x1800089c8`

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
0x180005698  mov     [rsp+arg_0], rbx
0x18000569d  mov     [rsp+arg_8], rbp
0x1800056a2  push    rsi
0x1800056a3  push    rdi
0x1800056a4  push    r14
0x1800056a6  sub     rsp, 30h
0x1800056aa  test    r9d, r9d
0x1800056ad  movzx   edi, r8b
0x1800056b1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800056b8  mov     esi, edx
0x1800056ba  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800056c1  mov     rbp, rcx
0x1800056c4  cmovnz  rbx, rax
0x1800056c8  mov     r9d, [rbx]
0x1800056cb  mov     eax, r9d
0x1800056ce  and     al, 3
0x1800056d0  cmp     al, 2
0x1800056d2  jnz     short loc_1800056DB
0x1800056d4  xor     al, al
0x1800056d6  jmp     loc_180005767
0x1800056db  test    r9b, 2
0x1800056df  jnz     short loc_180005747
0x1800056e1  mov     [rsp+48h+arg_18], 1
0x1800056e9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800056ee  mov     rcx, [rsp+48h+arg_20]
0x1800056f3  mov     r14d, eax
0x1800056f6  mov     [rsp+48h+var_20], rcx
0x1800056fb  lea     rax, [rsp+48h+arg_18]
0x180005700  mov     rcx, rbp
0x180005703  mov     [rsp+48h+var_28], rax
0x180005708  mov     r8d, edi
0x18000570b  mov     edx, esi
0x18000570d  call    wil_QueryFeatureState
0x180005712  mov     edx, [rsp+48h+arg_18]
0x180005716  test    eax, eax
0x180005718  mov     ecx, edx
0x18000571a  setnz   dil
0x18000571e  neg     ecx
0x180005720  sbb     r8d, r8d
0x180005723  neg     r8d
0x180005726  add     r8d, 6
0x18000572a  xchg    r8d, [rbx]
0x18000572d  test    edx, edx
0x18000572f  jnz     short loc_180005742
0x180005731  test    r8b, 4
0x180005735  jnz     short loc_180005742
0x180005737  mov     r8d, r14d
0x18000573a  mov     rcx, rbx
0x18000573d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005742  mov     al, dil
0x180005745  jmp     short loc_180005767
0x180005747  mov     rax, [rsp+48h+arg_20]
0x18000574c  mov     r8d, edi
0x18000574f  mov     [rsp+48h+var_20], rax
0x180005754  mov     [rsp+48h+var_28], 0
0x18000575d  call    wil_QueryFeatureState
0x180005762  test    eax, eax
0x180005764  setnz   al
0x180005767  mov     rbx, [rsp+48h+arg_0]
0x18000576c  mov     rbp, [rsp+48h+arg_8]
0x180005771  add     rsp, 30h
0x180005775  pop     r14
0x180005777  pop     rdi
0x180005778  pop     rsi
0x180005779  retn
```
