# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x14000b4cc`
- end: `0x14000b5ae`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e3b0`

## callees

- `0x140009dc8`
- `0x14000b4cc`
- `0x14000dd0c`
- `0x14000fa08`

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
0x14000b4cc  mov     [rsp+arg_0], rbx
0x14000b4d1  mov     [rsp+arg_8], rbp
0x14000b4d6  push    rsi
0x14000b4d7  push    rdi
0x14000b4d8  push    r14
0x14000b4da  sub     rsp, 30h
0x14000b4de  test    r9d, r9d
0x14000b4e1  movzx   edi, r8b
0x14000b4e5  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x14000b4ec  mov     esi, edx
0x14000b4ee  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x14000b4f5  mov     rbp, rcx
0x14000b4f8  cmovnz  rbx, rax
0x14000b4fc  mov     r9d, [rbx]
0x14000b4ff  mov     eax, r9d
0x14000b502  and     al, 3
0x14000b504  cmp     al, 2
0x14000b506  jnz     short loc_14000B50F
0x14000b508  xor     al, al
0x14000b50a  jmp     loc_14000B59B
0x14000b50f  test    r9b, 2
0x14000b513  jnz     short loc_14000B57B
0x14000b515  mov     [rsp+48h+arg_18], 1
0x14000b51d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000b522  mov     rcx, [rsp+48h+arg_20]
0x14000b527  mov     r14d, eax
0x14000b52a  mov     [rsp+48h+var_20], rcx
0x14000b52f  lea     rax, [rsp+48h+arg_18]
0x14000b534  mov     rcx, rbp
0x14000b537  mov     [rsp+48h+var_28], rax
0x14000b53c  mov     r8d, edi
0x14000b53f  mov     edx, esi
0x14000b541  call    wil_QueryFeatureState
0x14000b546  mov     edx, [rsp+48h+arg_18]
0x14000b54a  test    eax, eax
0x14000b54c  mov     ecx, edx
0x14000b54e  setnz   dil
0x14000b552  neg     ecx
0x14000b554  sbb     r8d, r8d
0x14000b557  neg     r8d
0x14000b55a  add     r8d, 6
0x14000b55e  xchg    r8d, [rbx]
0x14000b561  test    edx, edx
0x14000b563  jnz     short loc_14000B576
0x14000b565  test    r8b, 4
0x14000b569  jnz     short loc_14000B576
0x14000b56b  mov     r8d, r14d
0x14000b56e  mov     rcx, rbx
0x14000b571  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000b576  mov     al, dil
0x14000b579  jmp     short loc_14000B59B
0x14000b57b  mov     rax, [rsp+48h+arg_20]
0x14000b580  mov     r8d, edi
0x14000b583  mov     [rsp+48h+var_20], rax
0x14000b588  mov     [rsp+48h+var_28], 0
0x14000b591  call    wil_QueryFeatureState
0x14000b596  test    eax, eax
0x14000b598  setnz   al
0x14000b59b  mov     rbx, [rsp+48h+arg_0]
0x14000b5a0  mov     rbp, [rsp+48h+arg_8]
0x14000b5a5  add     rsp, 30h
0x14000b5a9  pop     r14
0x14000b5ab  pop     rdi
0x14000b5ac  pop     rsi
0x14000b5ad  retn
```
