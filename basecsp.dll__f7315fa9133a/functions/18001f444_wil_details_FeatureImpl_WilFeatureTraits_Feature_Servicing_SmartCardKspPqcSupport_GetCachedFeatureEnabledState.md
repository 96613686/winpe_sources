# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f444`
- end: `0x18001f51d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f950`
- `0x18001fa64`

## callees

- `0x18000d7e0`
- `0x1800170d0`
- `0x18001f444`
- `0x18001f75c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_SmartCardKspPqcSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_SmartCardKspPqcSupport__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_SmartCardKspPqcSupport__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_SmartCardKspPqcSupport__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001f444  mov     [rsp+arg_10], rbx
0x18001f449  mov     [rsp+arg_0], rcx
0x18001f44e  push    rbp
0x18001f44f  push    rsi
0x18001f450  push    rdi
0x18001f451  sub     rsp, 20h
0x18001f455  mov     rsi, cs:Feature_Servicing_SmartCardKspPqcSupport__descriptor
0x18001f45c  mov     rdi, rdx
0x18001f45f  mov     qword ptr [rdx], 0
0x18001f466  mov     eax, [rsi]
0x18001f468  mov     [rdx], eax
0x18001f46a  and     eax, 6
0x18001f46d  cmp     al, 6
0x18001f46f  jz      loc_18001F50D
0x18001f475  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f47a  lea     r8, [rsp+38h+arg_0]
0x18001f47f  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f487  lea     rdx, [rsp+38h+arg_8]
0x18001f48c  mov     ebp, eax
0x18001f48e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(int *)
0x18001f493  mov     eax, [rdi]
0x18001f495  mov     rbx, [rsp+38h+arg_8]
0x18001f49a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f49f  mov     edx, eax
0x18001f4a1  mov     [rdi], eax
0x18001f4a3  mov     ecx, eax
0x18001f4a5  jz      short loc_18001F4C0
0x18001f4a7  test    dl, 2
0x18001f4aa  jnz     short loc_18001F4C0
0x18001f4ac  and     ecx, 0FFFFF63Eh
0x18001f4b2  mov     eax, ebx
0x18001f4b4  and     eax, 9C1h
0x18001f4b9  or      ecx, eax
0x18001f4bb  or      ecx, 2
0x18001f4be  mov     [rdi], ecx
0x18001f4c0  mov     r8d, edx
0x18001f4c3  and     r8d, 4
0x18001f4c7  jnz     short loc_18001F4DB
0x18001f4c9  btr     ecx, 0Ah
0x18001f4cd  mov     eax, ebx
0x18001f4cf  and     eax, 400h
0x18001f4d4  or      ecx, eax
0x18001f4d6  or      ecx, 4
0x18001f4d9  mov     [rdi], ecx
0x18001f4db  mov     eax, edx
0x18001f4dd  lock cmpxchg [rsi], ecx
0x18001f4e1  jnz     short loc_18001F49A
0x18001f4e3  test    r8d, r8d
0x18001f4e6  jnz     short loc_18001F4F8
0x18001f4e8  mov     r8d, ebp
0x18001f4eb  mov     edx, 1
0x18001f4f0  mov     rcx, rsi
0x18001f4f3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f4f8  mov     eax, [rdi]
0x18001f4fa  test    al, 2
0x18001f4fc  jnz     short loc_18001F50D
0x18001f4fe  and     eax, 0FFFFF63Eh
0x18001f503  and     ebx, 9C1h
0x18001f509  or      eax, ebx
0x18001f50b  mov     [rdi], eax
0x18001f50d  mov     rbx, [rsp+38h+arg_10]
0x18001f512  mov     rax, rdi
0x18001f515  add     rsp, 20h
0x18001f519  pop     rdi
0x18001f51a  pop     rsi
0x18001f51b  pop     rbp
0x18001f51c  retn
```
