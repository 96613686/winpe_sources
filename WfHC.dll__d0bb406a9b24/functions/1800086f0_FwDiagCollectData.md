# FwDiagCollectData

- ea: `0x1800086f0`
- end: `0x180008985`
- name: `FwDiagCollectData`
- size: `661`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800049d0`

## callees

- `0x1800086f0`
- `0x180008990`

## import_xrefs

- `FirewallAPI!FWOpenPolicyStore` at `0x180008741`
- `FirewallAPI!FWOpenPolicyStore` at `0x180008741`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800088c3`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800088c3`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000890a`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000891e`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000890a`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000891e`
- `FirewallAPI!FWClosePolicyStore` at `0x18000895f`
- `FirewallAPI!FWClosePolicyStore` at `0x18000895f`
- `fwpuclnt!FwpmEngineOpen0` at `0x180008767`
- `fwpuclnt!FwpmEngineOpen0` at `0x180008767`
- `fwpuclnt!FwpmEngineClose0` at `0x180008936`
- `fwpuclnt!FwpmEngineClose0` at `0x180008936`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800088f6`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800088f6`
- `fwpuclnt!FwpmFilterGetById0` at `0x180008789`
- `fwpuclnt!FwpmFilterGetById0` at `0x180008789`

## pseudocode

```c
__int64 __fastcall FwDiagCollectData(__int64 a1)
{
  DWORD v2; // edi
  DWORD v3; // eax
  __int64 v4; // rdx
  unsigned __int64 i; // rcx
  _QWORD *v6; // r8
  __int64 v7; // rcx
  _QWORD *v8; // r8
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v15; // [rsp+38h] [rbp-9h] BYREF
  __int64 *v16; // [rsp+40h] [rbp-1h]
  __int128 v17; // [rsp+48h] [rbp+7h] BYREF
  __int64 v18; // [rsp+58h] [rbp+17h]
  __int64 v19; // [rsp+60h] [rbp+1Fh] BYREF
  int v20; // [rsp+68h] [rbp+27h]
  __int64 v21; // [rsp+70h] [rbp+2Fh]
  int v22; // [rsp+B0h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+B8h] [rbp+77h] BYREF
  HANDLE engineHandle; // [rsp+C0h] [rbp+7Fh] BYREF

  v23 = 0;
  engineHandle = 0;
  v2 = FWOpenPolicyStore(545, 0, 5, 1, 0, &v23);
  if ( v2 )
    goto LABEL_21;
  v2 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &engineHandle);
  if ( v2 )
    goto LABEL_21;
  v3 = FwpmFilterGetById0(engineHandle, *(_QWORD *)(a1 + 296), (FWPM_FILTER0 **)(a1 + 312));
  v2 = v3;
  if ( v3 )
  {
    if ( v3 != -2144206845 )
      goto LABEL_21;
  }
  v4 = *(_QWORD *)(a1 + 312);
  if ( v4 )
  {
    for ( i = 0; i < 0x15; ++i )
    {
      v6 = (_QWORD *)*((_QWORD *)&off_18000FEF0 + i);
      if ( *v6 == *(_QWORD *)(v4 + 64) && v6[1] == *(_QWORD *)(v4 + 72) )
      {
        v9 = 1;
        goto LABEL_15;
      }
    }
    v7 = 0;
    while ( 1 )
    {
      v8 = (_QWORD *)*((_QWORD *)&off_18000FE60 + v7);
      if ( *v8 == *(_QWORD *)(v4 + 64) && v8[1] == *(_QWORD *)(v4 + 72) )
        break;
      if ( (unsigned __int64)++v7 >= 0x11 )
      {
        v9 = 0;
        goto LABEL_15;
      }
    }
    v9 = 2;
LABEL_15:
    *(_DWORD *)(a1 + 320) = v9;
    *(_QWORD *)(a1 + 328) = 0;
    v10 = *(_QWORD **)(v4 + 40);
    v18 = 0;
    v22 = 0;
    v17 = 0;
    if ( v10 )
    {
      if ( *v10 == *(_QWORD *)WF_FILTER_PROVIDER_GUID && v10[1] == 0x623D0FAEB48F1EBELL && *(_DWORD *)(v4 + 48) == 8 )
      {
        v11 = **(_QWORD **)(v4 + 56);
        *((_QWORD *)&v17 + 1) = &v15;
        v21 = v11;
        v16 = &v19;
        LOWORD(v17) = 545;
        DWORD1(v17) = 1;
        LODWORD(v18) = -65536;
        v15 = 1;
        v19 = 3;
        v20 = 4;
        v2 = FWQueryFirewallRules(v23, &v17, 67, &v22, a1 + 328);
        if ( v2 )
          goto LABEL_21;
      }
    }
  }
  v2 = FwDiagCollectFirewallRules(v23, a1, a1 + 336, a1 + 344);
  if ( v2 )
  {
LABEL_21:
    FwpmFreeMemory0((void **)(a1 + 312));
    v12 = *(_QWORD *)(a1 + 328);
    *(_QWORD *)(a1 + 312) = 0;
    FWFreeFirewallRules(v12);
    v13 = *(_QWORD *)(a1 + 336);
    *(_QWORD *)(a1 + 328) = 0;
    FWFreeFirewallRules(v13);
    *(_QWORD *)(a1 + 336) = 0;
    *(_DWORD *)(a1 + 344) = 0;
  }
  FwpmEngineClose0(engineHandle);
  if ( v23 )
    FWClosePolicyStore();
  return v2;
}

```

## disassembly

```asm
0x1800086f0  mov     r11, rsp
0x1800086f3  push    rbp
0x1800086f4  push    rdi
0x1800086f5  lea     rbp, [r11-5Fh]
0x1800086f9  sub     rsp, 88h
0x180008700  mov     [r11+8], rbx
0x180008704  lea     rax, [rbp+57h+arg_10]
0x180008708  mov     [r11-18h], rsi
0x18000870c  xor     edx, edx
0x18000870e  mov     [r11-20h], r14
0x180008712  mov     rsi, rcx
0x180008715  xor     r14d, r14d
0x180008718  mov     [r11-28h], r15
0x18000871c  mov     [r11-70h], rax
0x180008720  mov     r15d, 221h
0x180008726  mov     ecx, r15d
0x180008729  mov     [rbp+57h+arg_10], r14
0x18000872d  mov     r9d, 1
0x180008733  mov     [rbp+57h+engineHandle], r14
0x180008737  mov     r8d, 5
0x18000873d  mov     [r11-78h], r14d
0x180008741  call    cs:__imp_FWOpenPolicyStore
0x180008747  mov     edi, eax
0x180008749  test    eax, eax
0x18000874b  jnz     loc_1800088EF
0x180008751  lea     rax, [rbp+57h+engineHandle]
0x180008755  xor     r9d, r9d; session
0x180008758  xor     r8d, r8d; authIdentity
0x18000875b  mov     [rsp+20h], rax; engineHandle
0x180008760  mov     edx, 0FFFFFFFFh; authnService
0x180008765  xor     ecx, ecx; serverName
0x180008767  call    cs:__imp_FwpmEngineOpen0
0x18000876d  mov     edi, eax
0x18000876f  test    eax, eax
0x180008771  jnz     loc_1800088EF
0x180008777  mov     rdx, [rsi+128h]; id
0x18000877e  lea     r8, [rsi+138h]; filter
0x180008785  mov     rcx, [rbp+57h+engineHandle]; engineHandle
0x180008789  call    cs:__imp_FwpmFilterGetById0
0x18000878f  mov     edi, eax
0x180008791  test    eax, eax
0x180008793  jz      short loc_1800087A0
0x180008795  cmp     eax, 80320003h
0x18000879a  jnz     loc_1800088EF
0x1800087a0  mov     rdx, [rsi+138h]
0x1800087a7  test    rdx, rdx
0x1800087aa  jz      loc_1800088CF
0x1800087b0  mov     rcx, r14
0x1800087b3  lea     r9, cs:180000000h
0x1800087ba  nop     word ptr [rax+rax+00h]
0x1800087c0  mov     r8, ds:rva off_18000FEF0[r9+rcx*8]
0x1800087c8  mov     rax, [r8]
0x1800087cb  cmp     rax, [rdx+40h]
0x1800087cf  jnz     short loc_1800087DF
0x1800087d1  mov     rax, [r8+8]
0x1800087d5  cmp     rax, [rdx+48h]
0x1800087d9  jz      loc_180008971
0x1800087df  inc     rcx
0x1800087e2  cmp     rcx, 15h
0x1800087e6  jb      short loc_1800087C0
0x1800087e8  mov     rcx, r14
0x1800087eb  nop     dword ptr [rax+rax+00h]
0x1800087f0  mov     r8, ds:rva off_18000FE60[r9+rcx*8]
0x1800087f8  mov     rax, [r8]
0x1800087fb  cmp     rax, [rdx+40h]
0x1800087ff  jnz     short loc_18000880F
0x180008801  mov     rax, [r8+8]
0x180008805  cmp     rax, [rdx+48h]
0x180008809  jz      loc_18000897B
0x18000880f  inc     rcx
0x180008812  cmp     rcx, 11h
0x180008816  jb      short loc_1800087F0
0x180008818  mov     eax, r14d
0x18000881b  mov     [rsi+140h], eax
0x180008821  lea     r9, [rsi+148h]
0x180008828  xor     eax, eax
0x18000882a  mov     [r9], r14
0x18000882d  mov     rcx, [rdx+28h]
0x180008831  xorps   xmm0, xmm0
0x180008834  mov     [rbp+57h+var_40], rax
0x180008838  mov     [rbp+57h+arg_8], r14d
0x18000883c  movups  [rbp+57h+var_50], xmm0
0x180008840  test    rcx, rcx
0x180008843  jz      loc_1800088CF
0x180008849  mov     rax, [rcx]
0x18000884c  cmp     rax, qword ptr cs:WF_FILTER_PROVIDER_GUID
0x180008853  jnz     short loc_1800088CF
0x180008855  mov     rax, [rcx+8]
0x180008859  cmp     rax, cs:qword_180011828
0x180008860  jnz     short loc_1800088CF
0x180008862  cmp     dword ptr [rdx+30h], 8
0x180008866  jnz     short loc_1800088CF
0x180008868  mov     rax, [rdx+38h]
0x18000886c  mov     r8d, 43h ; 'C'
0x180008872  mov     rcx, [rbp+57h+arg_10]
0x180008876  mov     [rsp+20h], r9
0x18000887b  lea     r9, [rbp+57h+arg_8]
0x18000887f  mov     rdx, [rax]
0x180008882  lea     rax, [rbp+57h+var_60]
0x180008886  mov     qword ptr [rbp+57h+var_50+8], rax
0x18000888a  lea     rax, [rbp+57h+var_38]
0x18000888e  mov     [rbp+57h+var_28], rdx
0x180008892  lea     rdx, [rbp+57h+var_50]
0x180008896  mov     [rbp+57h+var_58], rax
0x18000889a  mov     word ptr [rbp+57h+var_50], r15w
0x18000889f  mov     dword ptr [rbp+57h+var_50+4], 1
0x1800088a6  mov     dword ptr [rbp+57h+var_40], 0FFFF0000h
0x1800088ad  mov     [rbp+57h+var_60], 1
0x1800088b4  mov     [rbp+57h+var_38], 3
0x1800088bc  mov     [rbp+57h+var_30], 4
0x1800088c3  call    cs:__imp_FWQueryFirewallRules
0x1800088c9  mov     edi, eax
0x1800088cb  test    eax, eax
0x1800088cd  jnz     short loc_1800088EF
0x1800088cf  mov     rcx, [rbp+57h+arg_10]
0x1800088d3  lea     r9, [rsi+158h]
0x1800088da  lea     r8, [rsi+150h]
0x1800088e1  mov     rdx, rsi
0x1800088e4  call    FwDiagCollectFirewallRules
0x1800088e9  mov     edi, eax
0x1800088eb  test    eax, eax
0x1800088ed  jz      short loc_180008932
0x1800088ef  lea     rcx, [rsi+138h]; p
0x1800088f6  call    cs:__imp_FwpmFreeMemory0
0x1800088fc  mov     rcx, [rsi+148h]
0x180008903  mov     [rsi+138h], r14
0x18000890a  call    cs:__imp_FWFreeFirewallRules
0x180008910  mov     rcx, [rsi+150h]
0x180008917  mov     [rsi+148h], r14
0x18000891e  call    cs:__imp_FWFreeFirewallRules
0x180008924  mov     [rsi+150h], r14
0x18000892b  mov     [rsi+158h], r14d
0x180008932  mov     rcx, [rbp+57h+engineHandle]; engineHandle
0x180008936  call    cs:__imp_FwpmEngineClose0
0x18000893c  mov     rcx, [rbp+57h+arg_10]
0x180008940  mov     r15, [rsp+90h+var_20]
0x180008945  mov     r14, [rsp+90h+var_18]
0x18000894a  mov     rsi, [rsp+80h]
0x180008952  mov     rbx, [rsp+90h+arg_0]
0x18000895a  test    rcx, rcx
0x18000895d  jz      short loc_180008965
0x18000895f  call    cs:__imp_FWClosePolicyStore
0x180008965  mov     eax, edi
0x180008967  add     rsp, 88h
0x18000896e  pop     rdi
0x18000896f  pop     rbp
0x180008970  retn
0x180008971  mov     eax, 1
0x180008976  jmp     loc_18000881B
0x18000897b  mov     eax, 2
0x180008980  jmp     loc_18000881B
```
