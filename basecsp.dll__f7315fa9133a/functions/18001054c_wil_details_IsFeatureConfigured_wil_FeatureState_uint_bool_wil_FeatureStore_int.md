# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18001054c`
- end: `0x180010625`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017810`

## callees

- `0x18000d7e0`
- `0x18001054c`
- `0x1800170d0`
- `0x18001992c`

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
  unsigned int v10; // eax
  int v11; // r14d
  int v12; // eax
  int v13; // edx
  bool v14; // di
  char v15; // r8
  int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x18001054c  mov     [rsp+arg_0], rbx
0x180010551  mov     [rsp+arg_8], rbp
0x180010556  push    rsi
0x180010557  push    rdi
0x180010558  push    r14
0x18001055a  sub     rsp, 20h
0x18001055e  test    r9d, r9d
0x180010561  movzx   edi, r8b
0x180010565  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18001056c  mov     esi, edx
0x18001056e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180010575  mov     rbp, rcx
0x180010578  cmovnz  rbx, rax
0x18001057c  mov     r9d, [rbx]
0x18001057f  mov     eax, r9d
0x180010582  and     al, 3
0x180010584  cmp     al, 2
0x180010586  jnz     short loc_18001058F
0x180010588  xor     al, al
0x18001058a  jmp     loc_180010612
0x18001058f  test    r9b, 2
0x180010593  jnz     short loc_1800105F7
0x180010595  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001059a  mov     rcx, [rsp+38h+arg_20]
0x18001059f  lea     r9, [rsp+38h+arg_18]
0x1800105a4  mov     r8d, edi
0x1800105a7  mov     [rsp+38h+arg_18], 0
0x1800105af  mov     edx, esi
0x1800105b1  mov     r14d, eax
0x1800105b4  mov     dword ptr [rcx], 1
0x1800105ba  mov     rcx, rbp
0x1800105bd  call    wil_RtlStagingConfig_QueryFeatureState
0x1800105c2  mov     edx, [rsp+38h+arg_18]
0x1800105c6  test    eax, eax
0x1800105c8  mov     ecx, edx
0x1800105ca  setnz   dil
0x1800105ce  neg     ecx
0x1800105d0  sbb     r8d, r8d
0x1800105d3  neg     r8d
0x1800105d6  add     r8d, 6
0x1800105da  xchg    r8d, [rbx]
0x1800105dd  test    edx, edx
0x1800105df  jnz     short loc_1800105F2
0x1800105e1  test    r8b, 4
0x1800105e5  jnz     short loc_1800105F2
0x1800105e7  mov     r8d, r14d
0x1800105ea  mov     rcx, rbx
0x1800105ed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800105f2  mov     al, dil
0x1800105f5  jmp     short loc_180010612
0x1800105f7  mov     rax, [rsp+38h+arg_20]
0x1800105fc  mov     r8d, edi
0x1800105ff  xor     r9d, r9d
0x180010602  mov     dword ptr [rax], 1
0x180010608  call    wil_RtlStagingConfig_QueryFeatureState
0x18001060d  test    eax, eax
0x18001060f  setnz   al
0x180010612  mov     rbx, [rsp+38h+arg_0]
0x180010617  mov     rbp, [rsp+38h+arg_8]
0x18001061c  add     rsp, 20h
0x180010620  pop     r14
0x180010622  pop     rdi
0x180010623  pop     rsi
0x180010624  retn
```
