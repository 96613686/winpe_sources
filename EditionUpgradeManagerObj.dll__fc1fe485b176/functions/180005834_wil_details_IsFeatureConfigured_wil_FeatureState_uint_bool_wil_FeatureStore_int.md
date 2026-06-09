# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005834`
- end: `0x180005916`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008130`

## callees

- `0x180004728`
- `0x180005834`
- `0x180007a78`
- `0x180008b24`

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
0x180005834  mov     [rsp+arg_0], rbx
0x180005839  mov     [rsp+arg_8], rbp
0x18000583e  push    rsi
0x18000583f  push    rdi
0x180005840  push    r14
0x180005842  sub     rsp, 30h
0x180005846  test    r9d, r9d
0x180005849  movzx   edi, r8b
0x18000584d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180005854  mov     esi, edx
0x180005856  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000585d  mov     rbp, rcx
0x180005860  cmovnz  rbx, rax
0x180005864  mov     r9d, [rbx]
0x180005867  mov     eax, r9d
0x18000586a  and     al, 3
0x18000586c  cmp     al, 2
0x18000586e  jnz     short loc_180005877
0x180005870  xor     al, al
0x180005872  jmp     loc_180005903
0x180005877  test    r9b, 2
0x18000587b  jnz     short loc_1800058E3
0x18000587d  mov     [rsp+48h+arg_18], 1
0x180005885  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000588a  mov     rcx, [rsp+48h+arg_20]
0x18000588f  mov     r14d, eax
0x180005892  mov     [rsp+48h+var_20], rcx
0x180005897  lea     rax, [rsp+48h+arg_18]
0x18000589c  mov     rcx, rbp
0x18000589f  mov     [rsp+48h+var_28], rax
0x1800058a4  mov     r8d, edi
0x1800058a7  mov     edx, esi
0x1800058a9  call    wil_QueryFeatureState
0x1800058ae  mov     edx, [rsp+48h+arg_18]
0x1800058b2  test    eax, eax
0x1800058b4  mov     ecx, edx
0x1800058b6  setnz   dil
0x1800058ba  neg     ecx
0x1800058bc  sbb     r8d, r8d
0x1800058bf  neg     r8d
0x1800058c2  add     r8d, 6
0x1800058c6  xchg    r8d, [rbx]
0x1800058c9  test    edx, edx
0x1800058cb  jnz     short loc_1800058DE
0x1800058cd  test    r8b, 4
0x1800058d1  jnz     short loc_1800058DE
0x1800058d3  mov     r8d, r14d
0x1800058d6  mov     rcx, rbx
0x1800058d9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800058de  mov     al, dil
0x1800058e1  jmp     short loc_180005903
0x1800058e3  mov     rax, [rsp+48h+arg_20]
0x1800058e8  mov     r8d, edi
0x1800058eb  mov     [rsp+48h+var_20], rax
0x1800058f0  mov     [rsp+48h+var_28], 0
0x1800058f9  call    wil_QueryFeatureState
0x1800058fe  test    eax, eax
0x180005900  setnz   al
0x180005903  mov     rbx, [rsp+48h+arg_0]
0x180005908  mov     rbp, [rsp+48h+arg_8]
0x18000590d  add     rsp, 30h
0x180005911  pop     r14
0x180005913  pop     rdi
0x180005914  pop     rsi
0x180005915  retn
```
