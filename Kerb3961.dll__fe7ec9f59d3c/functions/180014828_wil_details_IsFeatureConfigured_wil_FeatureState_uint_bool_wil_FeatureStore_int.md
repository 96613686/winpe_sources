# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180014828`
- end: `0x18001490a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017a20`

## callees

- `0x180013584`
- `0x180014828`
- `0x180017240`
- `0x18001863c`

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
  int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  int v14; // edx
  bool v15; // di
  char v16; // r8
  int v17; // [rsp+68h] [rbp+20h] BYREF

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
  if ( !v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
  return v15;
}

```

## disassembly

```asm
0x180014828  mov     [rsp+arg_0], rbx
0x18001482d  mov     [rsp+arg_8], rbp
0x180014832  push    rsi
0x180014833  push    rdi
0x180014834  push    r14
0x180014836  sub     rsp, 30h
0x18001483a  test    r9d, r9d
0x18001483d  movzx   edi, r8b
0x180014841  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180014848  mov     esi, edx
0x18001484a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180014851  mov     rbp, rcx
0x180014854  cmovnz  rbx, rax
0x180014858  mov     r9d, [rbx]
0x18001485b  mov     eax, r9d
0x18001485e  and     al, 3
0x180014860  cmp     al, 2
0x180014862  jnz     short loc_18001486B
0x180014864  xor     al, al
0x180014866  jmp     loc_1800148F7
0x18001486b  test    r9b, 2
0x18001486f  jnz     short loc_1800148D7
0x180014871  mov     [rsp+48h+arg_18], 1
0x180014879  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001487e  mov     rcx, [rsp+48h+arg_20]
0x180014883  mov     r14d, eax
0x180014886  mov     [rsp+48h+var_20], rcx
0x18001488b  lea     rax, [rsp+48h+arg_18]
0x180014890  mov     rcx, rbp
0x180014893  mov     [rsp+48h+var_28], rax
0x180014898  mov     r8d, edi
0x18001489b  mov     edx, esi
0x18001489d  call    wil_QueryFeatureState
0x1800148a2  mov     edx, [rsp+48h+arg_18]
0x1800148a6  test    eax, eax
0x1800148a8  mov     ecx, edx
0x1800148aa  setnz   dil
0x1800148ae  neg     ecx
0x1800148b0  sbb     r8d, r8d
0x1800148b3  neg     r8d
0x1800148b6  add     r8d, 6
0x1800148ba  xchg    r8d, [rbx]
0x1800148bd  test    edx, edx
0x1800148bf  jnz     short loc_1800148D2
0x1800148c1  test    r8b, 4
0x1800148c5  jnz     short loc_1800148D2
0x1800148c7  mov     r8d, r14d
0x1800148ca  mov     rcx, rbx
0x1800148cd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800148d2  mov     al, dil
0x1800148d5  jmp     short loc_1800148F7
0x1800148d7  mov     rax, [rsp+48h+arg_20]
0x1800148dc  mov     r8d, edi
0x1800148df  mov     [rsp+48h+var_20], rax
0x1800148e4  mov     [rsp+48h+var_28], 0
0x1800148ed  call    wil_QueryFeatureState
0x1800148f2  test    eax, eax
0x1800148f4  setnz   al
0x1800148f7  mov     rbx, [rsp+48h+arg_0]
0x1800148fc  mov     rbp, [rsp+48h+arg_8]
0x180014901  add     rsp, 30h
0x180014905  pop     r14
0x180014907  pop     rdi
0x180014908  pop     rsi
0x180014909  retn
```
