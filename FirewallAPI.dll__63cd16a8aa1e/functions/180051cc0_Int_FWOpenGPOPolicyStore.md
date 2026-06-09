# Int_FWOpenGPOPolicyStore

- ea: `0x180051cc0`
- end: `0x180051e0b`
- name: `Int_FWOpenGPOPolicyStore`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052c0`
- `0x180008b30`
- `0x18000cd90`
- `0x18000db60`
- `0x18000e6c0`
- `0x18001494c`
- `0x1800266b0`
- `0x1800520b0`

## callees

- `0x180005954`
- `0x18002514c`
- `0x1800516bc`
- `0x180051cc0`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180051d76`
- `fwbase!FwHResultToWindowsError` at `0x180051db7`
- `fwbase!FwHResultToWindowsError` at `0x180051d76`
- `fwbase!FwHResultToWindowsError` at `0x180051db7`
- `FWPolicyIOMgr!FWOpenGPOAndGetRegKey` at `0x180051d6e`
- `FWPolicyIOMgr!FWOpenGPOAndGetRegKey` at `0x180051d6e`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180051daf`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180051daf`

## pseudocode

```c
__int64 __fastcall Int_FWOpenGPOPolicyStore(__int64 a1)
{
  int v1; // r9d
  unsigned int v2; // edi
  unsigned int v4; // ebp
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  unsigned int v8; // r14d
  unsigned int RegKey; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  FwPolicy2 *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax

  v1 = *(_DWORD *)(a1 + 72);
  v2 = 0;
  v4 = 0;
  v5 = 3;
  if ( *(_DWORD *)(a1 + 20) != 1 )
    v5 = 1;
  LOBYTE(v4) = (*(_DWORD *)(a1 + 72) & 2) != 0;
  v6 = (unsigned int)v5 | 8;
  if ( (v1 & 2) == 0 )
    v6 = (unsigned int)v5;
  if ( (v1 & 4) != 0 )
    v4 = 1;
  v7 = (unsigned int)v6 | 0xC;
  if ( (v1 & 4) == 0 )
    v7 = (unsigned int)v6;
  if ( (v1 & 8) != 0 )
    v4 = 1;
  v8 = v7 | 4;
  if ( (v1 & 8) == 0 )
    v8 = v7;
  if ( *(_DWORD *)(a1 + 4) != 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v5, v6);
  if ( !*(_QWORD *)(a1 + 40) )
  {
    RegKey = FWOpenGPOAndGetRegKey(*(_QWORD *)(a1 + 8), v8, v4, a1 + 64, a1 + 40, a1 + 48, a1 + 32);
    v2 = FwHResultToWindowsError(RegKey);
    if ( v2 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v13 = 375;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v2);
LABEL_25:
      Int_FWCleanupGPOPolicyStore(a1, v10, v11);
      return v2;
    }
    v14 = FwOpenPolicyStore(*(unsigned int *)(a1 + 16), *(unsigned int *)(a1 + 20), *(_QWORD *)(a1 + 48), a1 + 56);
    v2 = FwHResultToWindowsError(v14);
    if ( v2 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v13 = 376;
      goto LABEL_24;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180051cc0  push    rbx
0x180051cc2  push    rbp
0x180051cc3  push    rsi
0x180051cc4  push    rdi
0x180051cc5  push    r14
0x180051cc7  push    r15
0x180051cc9  sub     rsp, 48h
0x180051ccd  mov     r9d, [rcx+48h]
0x180051cd1  xor     edi, edi
0x180051cd3  mov     rbx, rcx
0x180051cd6  mov     ebp, edi
0x180051cd8  lea     r15d, [rdi+1]
0x180051cdc  cmp     [rcx+14h], r15d
0x180051ce0  lea     edx, [rdi+3]
0x180051ce3  cmovnz  edx, r15d
0x180051ce7  bt      r9d, 1
0x180051cec  mov     r8d, edx
0x180051cef  setb    bpl
0x180051cf3  or      r8d, 8
0x180051cf7  bt      r9d, 1
0x180051cfc  cmovnb  r8d, edx
0x180051d00  bt      r9d, 2
0x180051d05  mov     ecx, r8d
0x180051d08  cmovb   ebp, r15d
0x180051d0c  or      ecx, 0Ch
0x180051d0f  bt      r9d, 2
0x180051d14  cmovnb  ecx, r8d
0x180051d18  bt      r9d, 3
0x180051d1d  mov     r14d, ecx
0x180051d20  cmovb   ebp, r15d
0x180051d24  or      r14d, 4
0x180051d28  bt      r9d, 3
0x180051d2d  cmovnb  r14d, ecx
0x180051d31  cmp     dword ptr [rbx+4], 2
0x180051d35  jz      short loc_180051D3C
0x180051d37  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180051d3c  lea     rcx, [rbx+28h]
0x180051d40  cmp     [rcx], rdi
0x180051d43  jnz     loc_180051DFC
0x180051d49  lea     rax, [rbx+20h]
0x180051d4d  mov     r8d, ebp
0x180051d50  mov     [rsp+78h+var_48], rax
0x180051d55  lea     rsi, [rbx+30h]
0x180051d59  mov     [rsp+78h+var_50], rsi
0x180051d5e  lea     r9, [rbx+40h]
0x180051d62  mov     [rsp+78h+var_58], rcx
0x180051d67  mov     edx, r14d
0x180051d6a  mov     rcx, [rbx+8]
0x180051d6e  call    cs:__imp_FWOpenGPOAndGetRegKey
0x180051d74  mov     ecx, eax
0x180051d76  call    cs:__imp_FwHResultToWindowsError
0x180051d7c  mov     edi, eax
0x180051d7e  test    eax, eax
0x180051d80  jz      short loc_180051DA2
0x180051d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d89  lea     rax, WPP_GLOBAL_Control
0x180051d90  cmp     rcx, rax
0x180051d93  jz      short loc_180051DF4
0x180051d95  test    [rcx+1Ch], r15b
0x180051d99  jz      short loc_180051DF4
0x180051d9b  mov     edx, 177h
0x180051da0  jmp     short loc_180051DE1
0x180051da2  mov     r8, [rsi]
0x180051da5  lea     r9, [rbx+38h]
0x180051da9  mov     edx, [rbx+14h]
0x180051dac  mov     ecx, [rbx+10h]
0x180051daf  call    cs:__imp_FwOpenPolicyStore
0x180051db5  mov     ecx, eax
0x180051db7  call    cs:__imp_FwHResultToWindowsError
0x180051dbd  mov     edi, eax
0x180051dbf  test    eax, eax
0x180051dc1  jz      short loc_180051DFC
0x180051dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180051dca  lea     rax, WPP_GLOBAL_Control
0x180051dd1  cmp     rcx, rax
0x180051dd4  jz      short loc_180051DF4
0x180051dd6  test    [rcx+1Ch], r15b
0x180051dda  jz      short loc_180051DF4
0x180051ddc  mov     edx, 178h
0x180051de1  mov     rcx, [rcx+10h]
0x180051de5  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180051dec  mov     r9d, edi
0x180051def  call    WPP_SF_d
0x180051df4  mov     rcx, rbx
0x180051df7  call    Int_FWCleanupGPOPolicyStore
0x180051dfc  mov     eax, edi
0x180051dfe  add     rsp, 48h
0x180051e02  pop     r15
0x180051e04  pop     r14
0x180051e06  pop     rdi
0x180051e07  pop     rsi
0x180051e08  pop     rbp
0x180051e09  pop     rbx
0x180051e0a  retn
```
