# _lambda_abec86eb39d26369503aaafa1ba2d18c_::operator()

- ea: `0x140002d00`
- end: `0x140002e61`
- name: `_lambda_abec86eb39d26369503aaafa1ba2d18c_::operator()`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007280`

## callees

- `0x140002d00`
- `0x140006010`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002d2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d2b`
- `fwpkclnt!FwpsApplyModifiedLayerData0` at `0x140002d54`
- `fwpkclnt!FwpsApplyModifiedLayerData0` at `0x140002d54`
- `fwpkclnt!FwpsReleaseClassifyHandle0` at `0x140002d84`
- `fwpkclnt!FwpsReleaseClassifyHandle0` at `0x140002d84`
- `fwpkclnt!FwpsCompleteClassify0` at `0x140002d6f`
- `fwpkclnt!FwpsCompleteClassify0` at `0x140002d6f`

## pseudocode

```c
__int64 __fastcall lambda_abec86eb39d26369503aaafa1ba2d18c_::operator()(__int64 a1)
{
  void *v2; // rcx
  __int128 *v3; // rax
  __int128 *v4; // rsi
  __int128 *v5; // rbx
  __int128 v6; // xmm6
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-28h] BYREF

  v2 = *(void **)(**(_QWORD **)a1 + 56LL);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x64667072u);
  *(_DWORD *)(**(_QWORD **)a1 + 32LL) |= 1u;
  FwpsApplyModifiedLayerData0(***(_QWORD ***)a1, *(PVOID *)(**(_QWORD **)a1 + 72LL), 1u);
  FwpsCompleteClassify0(***(_QWORD ***)a1, 0, (const FWPS_CLASSIFY_OUT0 *)(**(_QWORD **)a1 + 8LL));
  FwpsReleaseClassifyHandle0(***(_QWORD ***)a1);
  if ( !**(_QWORD **)(a1 + 8) )
  {
    v3 = (__int128 *)AcquireSpinLock(&v8, (char *)RoutePolicyCallout::g_pCalloutContext + 40);
    v4 = *(__int128 **)(a1 + 8);
    v5 = v3;
    if ( v4 != v3 )
    {
      v6 = *v3;
      if ( *(_QWORD *)v4 )
      {
        v9 = *v4;
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v9);
      }
      *v4 = v6;
      *(_QWORD *)v5 = 0;
      *((_BYTE *)v5 + 8) = 0;
      *(_DWORD *)((char *)v5 + 9) = *(_DWORD *)((char *)&v8 + 9);
      *(_WORD *)((char *)v5 + 13) = *(_WORD *)((char *)&v8 + 13);
      *((_BYTE *)v5 + 15) = HIBYTE(v8);
    }
    if ( (_QWORD)v8 )
    {
      v9 = v8;
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v9);
    }
  }
  RemoveWorkItem(**(_QWORD **)(a1 + 16));
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(
           WdfDriverGlobals,
           **(_QWORD **)(a1 + 16));
}

```

## disassembly

```asm
0x140002d00  mov     [rsp+arg_0], rbx
0x140002d05  mov     [rsp+arg_8], rsi
0x140002d0a  push    rdi
0x140002d0b  sub     rsp, 50h
0x140002d0f  mov     rax, [rcx]
0x140002d12  mov     rdi, rcx
0x140002d15  movaps  [rsp+58h+var_18], xmm6
0x140002d1a  mov     rdx, [rax]
0x140002d1d  mov     rcx, [rdx+38h]; P
0x140002d21  test    rcx, rcx
0x140002d24  jz      short loc_140002D37
0x140002d26  mov     edx, 64667072h; Tag
0x140002d2b  call    cs:__imp_ExFreePoolWithTag
0x140002d32  nop     dword ptr [rax+rax+00h]
0x140002d37  mov     rax, [rdi]
0x140002d3a  mov     r8d, 1; flags
0x140002d40  mov     rcx, [rax]
0x140002d43  or      [rcx+20h], r8d
0x140002d47  mov     rax, [rdi]
0x140002d4a  mov     rcx, [rax]
0x140002d4d  mov     rdx, [rcx+48h]; modifiedLayerData
0x140002d51  mov     rcx, [rcx]; classifyHandle
0x140002d54  call    cs:__imp_FwpsApplyModifiedLayerData0
0x140002d5b  nop     dword ptr [rax+rax+00h]
0x140002d60  mov     rax, [rdi]
0x140002d63  xor     edx, edx; flags
0x140002d65  mov     rcx, [rax]
0x140002d68  lea     r8, [rcx+8]; classifyOut
0x140002d6c  mov     rcx, [rcx]; classifyHandle
0x140002d6f  call    cs:__imp_FwpsCompleteClassify0
0x140002d76  nop     dword ptr [rax+rax+00h]
0x140002d7b  mov     rax, [rdi]
0x140002d7e  mov     rcx, [rax]
0x140002d81  mov     rcx, [rcx]; classifyHandle
0x140002d84  call    cs:__imp_FwpsReleaseClassifyHandle0
0x140002d8b  nop     dword ptr [rax+rax+00h]
0x140002d90  mov     rax, [rdi+8]
0x140002d94  cmp     qword ptr [rax], 0
0x140002d98  jnz     loc_140002E1E
0x140002d9e  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140002da5  lea     rcx, [rsp+58h+var_38]
0x140002daa  add     rdx, 28h ; '('
0x140002dae  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140002db3  mov     rsi, [rdi+8]
0x140002db7  mov     rbx, rax
0x140002dba  cmp     rsi, rax
0x140002dbd  jz      short loc_140002E01
0x140002dbf  cmp     qword ptr [rsi], 0
0x140002dc3  movups  xmm6, xmmword ptr [rax]
0x140002dc6  jz      short loc_140002DDB
0x140002dc8  movups  xmm0, xmmword ptr [rsi]
0x140002dcb  lea     rcx, [rsp+58h+var_28]; struct SpinLockAndSavedIrql *
0x140002dd0  movdqu  [rsp+58h+var_28], xmm0
0x140002dd6  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002ddb  movdqu  xmmword ptr [rsi], xmm6
0x140002ddf  mov     qword ptr [rbx], 0
0x140002de6  mov     byte ptr [rbx+8], 0
0x140002dea  mov     eax, dword ptr [rsp+58h+var_38+9]
0x140002dee  mov     [rbx+9], eax
0x140002df1  movzx   eax, word ptr [rsp+58h+var_38+0Dh]
0x140002df6  mov     [rbx+0Dh], ax
0x140002dfa  mov     al, byte ptr [rsp+58h+var_38+0Fh]
0x140002dfe  mov     [rbx+0Fh], al
0x140002e01  cmp     qword ptr [rsp+58h+var_38], 0
0x140002e07  jz      short loc_140002E1E
0x140002e09  movaps  xmm0, [rsp+58h+var_38]
0x140002e0e  lea     rcx, [rsp+58h+var_28]; struct SpinLockAndSavedIrql *
0x140002e13  movdqa  [rsp+58h+var_28], xmm0
0x140002e19  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002e1e  mov     rcx, [rdi+10h]
0x140002e22  mov     rcx, [rcx]
0x140002e25  call    RemoveWorkItem
0x140002e2a  mov     rdx, [rdi+10h]
0x140002e2e  mov     rax, cs:WdfFunctions_01015
0x140002e35  mov     rcx, cs:WdfDriverGlobals
0x140002e3c  mov     rdx, [rdx]
0x140002e3f  mov     rax, [rax+680h]
0x140002e46  call    _guard_dispatch_icall
0x140002e4b  mov     rbx, [rsp+58h+arg_0]
0x140002e50  mov     rsi, [rsp+58h+arg_8]
0x140002e55  movaps  xmm6, [rsp+58h+var_18]
0x140002e5a  add     rsp, 50h
0x140002e5e  pop     rdi
0x140002e5f  retn
```
