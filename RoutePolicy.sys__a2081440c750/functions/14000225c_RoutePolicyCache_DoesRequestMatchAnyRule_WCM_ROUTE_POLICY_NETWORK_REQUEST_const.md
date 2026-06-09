# RoutePolicyCache::DoesRequestMatchAnyRule(_WCM_ROUTE_POLICY_NETWORK_REQUEST const &)

- ea: `0x14000225c`
- end: `0x1400023ba`
- name: `?DoesRequestMatchAnyRule@RoutePolicyCache@@YA_NAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@@Z`
- size: `350`
- prototype: `bool __fastcall(RoutePolicyCache *__hidden this, const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007280`

## callees

- `0x14000225c`
- `0x140002590`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`

## pseudocode

```c
char __fastcall RoutePolicyCache::DoesRequestMatchAnyRule(
        RoutePolicyCache *this,
        const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *a2)
{
  PVOID *i; // rdi
  __int64 v4; // rcx
  PVOID *v5; // rsi
  unsigned int v6; // r14d
  __int64 v7; // rbx
  int v8; // edx
  int v9; // ecx
  int v10; // ecx
  bool v11; // zf
  _QWORD v13[9]; // [rsp+20h] [rbp-48h] BYREF

  AcquireSpinLock(v13, &g_cacheLock);
  for ( i = (PVOID *)g_rulesListHead; ; i = (PVOID *)*i )
  {
    if ( i == &g_rulesListHead )
    {
      if ( v13[0] )
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)v13);
      return 0;
    }
    v4 = *((_QWORD *)this + 4);
    v5 = i + 2;
    if ( !v4 || *(_QWORD *)*v5 == v4 )
    {
      v6 = 0;
      v7 = (__int64)*v5 + 12;
      if ( *((_DWORD *)*v5 + 2) )
        break;
    }
LABEL_21:
    ;
  }
  while ( 1 )
  {
    v8 = *(_DWORD *)v7;
    if ( !*(_DWORD *)v7 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      goto LABEL_20;
    }
    if ( (*(_DWORD *)this & v8) != v8 )
      goto LABEL_20;
    if ( (v8 & 0x10000) == 0 )
      goto LABEL_16;
    v9 = *((_DWORD *)this + 6);
    if ( !v9 )
      break;
    v10 = v9 - 1;
    if ( !v10 )
    {
      v11 = (*(_DWORD *)(v7 + 464) & 2) == 0;
      goto LABEL_15;
    }
    if ( v10 == 1 )
    {
      v11 = (*(_DWORD *)(v7 + 464) & 4) == 0;
      goto LABEL_15;
    }
LABEL_20:
    ++v6;
    v7 += *(unsigned int *)(v7 + 468) + 472LL;
    if ( v6 >= *((_DWORD *)*v5 + 2) )
      goto LABEL_21;
  }
  v11 = (*(_DWORD *)(v7 + 464) & 1) == 0;
LABEL_15:
  if ( v11 )
    goto LABEL_20;
LABEL_16:
  if ( (v8 & 0x800) != 0 && !NPDoStringParametersMatch((PCWSTR)(v7 + 4), *((PCWSTR *)this + 1), 1)
    || (*(_DWORD *)v7 & 0x1000) != 0 && !NPDoStringParametersMatch((PCWSTR)(v7 + 260), *((PCWSTR *)this + 2), 0) )
  {
    goto LABEL_20;
  }
  if ( v13[0] )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)v13);
  return 1;
}

```

## disassembly

```asm
0x14000225c  push    rbx
0x14000225e  push    rbp
0x14000225f  push    rsi
0x140002260  push    rdi
0x140002261  push    r12
0x140002263  push    r14
0x140002265  sub     rsp, 38h
0x140002269  mov     rbp, rcx
0x14000226c  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140002273  lea     rcx, [rsp+68h+var_48]
0x140002278  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x14000227d  mov     rdi, cs:?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140002284  lea     r12, ?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x14000228b  jmp     loc_140002363
0x140002290  mov     rcx, [rbp+20h]
0x140002294  lea     rsi, [rdi+10h]
0x140002298  test    rcx, rcx
0x14000229b  jz      short loc_1400022A9
0x14000229d  mov     rax, [rsi]
0x1400022a0  cmp     [rax], rcx
0x1400022a3  jnz     loc_140002360
0x1400022a9  mov     rax, [rsi]
0x1400022ac  xor     r14d, r14d
0x1400022af  lea     rbx, [rax+0Ch]
0x1400022b3  cmp     [rax+8], r14d
0x1400022b7  jbe     loc_140002360
0x1400022bd  mov     edx, [rbx]
0x1400022bf  test    edx, edx
0x1400022c1  jnz     short loc_1400022CA
0x1400022c3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400022c8  jmp     short loc_140002341
0x1400022ca  mov     eax, edx
0x1400022cc  and     eax, [rbp+0]
0x1400022cf  cmp     eax, edx
0x1400022d1  jnz     short loc_140002341
0x1400022d3  bt      edx, 10h
0x1400022d7  jnb     short loc_140002308
0x1400022d9  mov     ecx, [rbp+18h]
0x1400022dc  test    ecx, ecx
0x1400022de  jz      short loc_1400022FE
0x1400022e0  sub     ecx, 1
0x1400022e3  jz      short loc_1400022F4
0x1400022e5  cmp     ecx, 1
0x1400022e8  jnz     short loc_140002341
0x1400022ea  mov     eax, [rbx+1D0h]
0x1400022f0  test    al, 4
0x1400022f2  jmp     short loc_140002306
0x1400022f4  mov     eax, [rbx+1D0h]
0x1400022fa  test    al, 2
0x1400022fc  jmp     short loc_140002306
0x1400022fe  mov     eax, [rbx+1D0h]
0x140002304  test    al, 1
0x140002306  jz      short loc_140002341
0x140002308  bt      edx, 0Bh
0x14000230c  jnb     short loc_140002322
0x14000230e  mov     rdx, [rbp+8]; PCWSTR
0x140002312  lea     rcx, [rbx+4]; SourceString
0x140002316  mov     r8b, 1; bool
0x140002319  call    ?NPDoStringParametersMatch@@YA_NPEBG0_N@Z; NPDoStringParametersMatch(ushort const *,ushort const *,bool)
0x14000231e  test    al, al
0x140002320  jz      short loc_140002341
0x140002322  test    dword ptr [rbx], 1000h
0x140002328  jz      short loc_140002399
0x14000232a  mov     rdx, [rbp+10h]; PCWSTR
0x14000232e  lea     rcx, [rbx+104h]; SourceString
0x140002335  xor     r8d, r8d; bool
0x140002338  call    ?NPDoStringParametersMatch@@YA_NPEBG0_N@Z; NPDoStringParametersMatch(ushort const *,ushort const *,bool)
0x14000233d  test    al, al
0x14000233f  jnz     short loc_140002399
0x140002341  mov     eax, [rbx+1D4h]
0x140002347  inc     r14d
0x14000234a  add     rax, 1D8h
0x140002350  add     rbx, rax
0x140002353  mov     rax, [rsi]
0x140002356  cmp     r14d, [rax+8]
0x14000235a  jb      loc_1400022BD
0x140002360  mov     rdi, [rdi]
0x140002363  cmp     rdi, r12
0x140002366  jnz     loc_140002290
0x14000236c  cmp     [rsp+68h+var_48], 0
0x140002372  jz      short loc_140002389
0x140002374  movaps  xmm0, xmmword ptr [rsp+68h+var_48]
0x140002379  lea     rcx, [rsp+68h+var_48]; struct SpinLockAndSavedIrql *
0x14000237e  movdqa  xmmword ptr [rsp+68h+var_48], xmm0
0x140002384  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002389  xor     al, al
0x14000238b  add     rsp, 38h
0x14000238f  pop     r14
0x140002391  pop     r12
0x140002393  pop     rdi
0x140002394  pop     rsi
0x140002395  pop     rbp
0x140002396  pop     rbx
0x140002397  retn
0x140002399  cmp     [rsp+68h+var_48], 0
0x14000239f  jz      short loc_1400023B6
0x1400023a1  movaps  xmm0, xmmword ptr [rsp+68h+var_48]
0x1400023a6  lea     rcx, [rsp+68h+var_48]; struct SpinLockAndSavedIrql *
0x1400023ab  movdqa  xmmword ptr [rsp+68h+var_48], xmm0
0x1400023b1  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x1400023b6  mov     al, 1
0x1400023b8  jmp     short loc_14000238B
```
