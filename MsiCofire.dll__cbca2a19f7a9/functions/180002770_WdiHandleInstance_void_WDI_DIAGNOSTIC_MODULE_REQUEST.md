# WdiHandleInstance(void *,WDI_DIAGNOSTIC_MODULE_REQUEST)

- ea: `0x180002770`
- end: `0x1800028d4`
- name: `?WdiHandleInstance@@YAJPEAXW4WDI_DIAGNOSTIC_MODULE_REQUEST@@@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002590`
- `0x180002770`
- `0x1800036f0`
- `0x1800038cc`
- `0x180003ac8`
- `0x180004f1c`
- `0x180005020`
- `0x180005b1c`
- `0x180005b78`

## import_xrefs

- `wdi!WdiSetResolution` at `0x180002871`
- `wdi!WdiSetResolution` at `0x180002871`

## string_xrefs

- `0x18000279d`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x18000288e`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall WdiHandleInstance(void *a1, int a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  __int64 result; // rax
  int v9; // eax
  int v10; // r9d
  __int128 v11; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+48h] [rbp-20h]
  unsigned int v14; // [rsp+50h] [rbp-18h]

  if ( a2 != 6 && !a1 )
  {
    v3 = -2147024809;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WdiHandleInstance", 192, -2147024809);
LABEL_22:
    SetScenarioResultParameter(a1, 1);
    SetScenarioDMError(a1, v3);
    return v3;
  }
  v3 = 0;
  v4 = a2 - 2;
  if ( !v4 )
  {
    result = RunProblemDetect(a1);
    goto LABEL_14;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v12 = 0;
    v13 = 0;
    v11 = 0;
    v14 = 0;
    v9 = CrashEventData::LoadFromWdi((CrashEventData *)&v11, a1);
    v3 = v9;
    if ( v9 >= 0 )
    {
      v9 = WdiSetResolution(a1, &CfrMsiDmGUID, v13, v14, 1, 0);
      v3 = v9;
      if ( v9 >= 0 )
        goto LABEL_21;
      v10 = 222;
    }
    else
    {
      v10 = 213;
    }
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "WdiHandleInstance", v10, v9);
LABEL_21:
    CrashEventData::Free((CrashEventData *)&v11);
    if ( (v3 & 0x80000000) != 0 )
      goto LABEL_22;
    return v3;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        g_bDmCanceled = 1;
        SetScenarioResultParameter(a1, 2);
      }
      return v3;
    }
    if ( !g_bInResolver )
      return RunInstanceCompletion(a1);
    return v3;
  }
  g_bInResolver = 1;
  result = RunResolver(a1);
LABEL_14:
  v3 = result;
  if ( (int)result >= 0 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x180002770  mov     [rsp+arg_0], rbx
0x180002775  push    rdi
0x180002776  sub     rsp, 60h
0x18000277a  mov     rdi, rcx
0x18000277d  cmp     edx, 6
0x180002780  jz      short loc_1800027AE
0x180002782  test    rcx, rcx
0x180002785  jnz     short loc_1800027AE
0x180002787  mov     ebx, 80070057h
0x18000278c  lea     r8, aWdihandleinsta_0; "WdiHandleInstance"
0x180002793  mov     r9d, 0C0h
0x180002799  mov     [rsp+68h+var_48], ebx
0x18000279d  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x1800027a4  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800027a9  jmp     loc_1800028AE
0x1800027ae  xor     ebx, ebx
0x1800027b0  sub     edx, 2
0x1800027b3  jz      loc_1800028CA
0x1800027b9  sub     edx, 1
0x1800027bc  jz      short loc_18000280E
0x1800027be  sub     edx, 1
0x1800027c1  jz      short loc_1800027F7
0x1800027c3  sub     edx, 1
0x1800027c6  jz      short loc_1800027E8
0x1800027c8  cmp     edx, 1
0x1800027cb  jnz     short loc_1800027DB
0x1800027cd  mov     cs:g_bDmCanceled, edx
0x1800027d3  lea     edx, [rbx+2]
0x1800027d6  call    SetScenarioResultParameter
0x1800027db  mov     eax, ebx
0x1800027dd  mov     rbx, [rsp+68h+arg_0]
0x1800027e2  add     rsp, 60h
0x1800027e6  pop     rdi
0x1800027e7  retn
0x1800027e8  cmp     cs:g_bInResolver, ebx
0x1800027ee  jnz     short loc_1800027DB
0x1800027f0  call    RunInstanceCompletion
0x1800027f5  jmp     short loc_1800027DD
0x1800027f7  mov     cs:g_bInResolver, 1
0x180002801  call    RunResolver
0x180002806  mov     ebx, eax
0x180002808  test    eax, eax
0x18000280a  jns     short loc_1800027DB
0x18000280c  jmp     short loc_1800027DD
0x18000280e  xorps   xmm0, xmm0
0x180002811  mov     [rsp+68h+arg_10], rbx
0x180002819  mov     rdx, rdi; void *
0x18000281c  mov     [rsp+68h+var_28], rbx
0x180002821  lea     rcx, [rsp+68h+var_38]; this
0x180002826  mov     [rsp+68h+var_20], rbx
0x18000282b  movdqu  [rsp+68h+var_38], xmm0
0x180002831  mov     [rsp+68h+var_18], ebx
0x180002835  call    ?LoadFromWdi@CrashEventData@@QEAAJPEAX@Z; CrashEventData::LoadFromWdi(void *)
0x18000283a  mov     ebx, eax
0x18000283c  test    eax, eax
0x18000283e  jns     short loc_180002848
0x180002840  mov     r9d, 0D5h
0x180002846  jmp     short loc_180002883
0x180002848  mov     rax, [rsp+68h+arg_10]
0x180002850  lea     rdx, CfrMsiDmGUID
0x180002857  mov     r9d, [rsp+68h+var_18]
0x18000285c  mov     rcx, rdi
0x18000285f  mov     r8, [rsp+68h+var_20]
0x180002864  mov     [rsp+68h+var_40], rax
0x180002869  mov     [rsp+68h+var_48], 1
0x180002871  call    cs:__imp_WdiSetResolution
0x180002877  mov     ebx, eax
0x180002879  test    eax, eax
0x18000287b  jns     short loc_18000289C
0x18000287d  mov     r9d, 0DEh
0x180002883  lea     r8, aWdihandleinsta_0; "WdiHandleInstance"
0x18000288a  mov     [rsp+68h+var_48], eax
0x18000288e  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180002895  xor     ecx, ecx; Level
0x180002897  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x18000289c  lea     rcx, [rsp+68h+var_38]; this
0x1800028a1  call    ?Free@CrashEventData@@QEAAXXZ; CrashEventData::Free(void)
0x1800028a6  test    ebx, ebx
0x1800028a8  jns     loc_1800027DB
0x1800028ae  mov     edx, 1
0x1800028b3  mov     rcx, rdi
0x1800028b6  call    SetScenarioResultParameter
0x1800028bb  mov     edx, ebx
0x1800028bd  mov     rcx, rdi
0x1800028c0  call    SetScenarioDMError
0x1800028c5  jmp     loc_1800027DB
0x1800028ca  call    RunProblemDetect
0x1800028cf  jmp     loc_180002806
```
