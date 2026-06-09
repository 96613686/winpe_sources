# FwApiHelperInit

- ea: `0x180035b90`
- end: `0x180035c46`
- name: `FwApiHelperInit`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003104c`
- `0x180035b10`
- `0x180035b90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035c0d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035c0d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035bc8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180035bc8`
- `fwbase!FwReportReturnError` at `0x180035c22`
- `fwbase!FwReportReturnError` at `0x180035c36`
- `fwbase!FwReportReturnError` at `0x180035c22`
- `fwbase!FwReportReturnError` at `0x180035c36`

## pseudocode

```c
__int64 FwApiHelperInit()
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  HRESULT Instance; // eax

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids);
  gFwApiComInit = CoInitializeEx(0, 0);
  v0 = gFwApiComInit;
  if ( (int)(gFwApiComInit + 0x80000000) >= 0 && gFwApiComInit != -2147417850 )
  {
    v1 = (unsigned int)gFwApiComInit;
LABEL_9:
    FwReportReturnError("FwApiHelperInit", v1);
    FwApiHelperFree();
    return (unsigned int)FwReportReturnError("FwApiHelperInit", v0);
  }
  Instance = CoCreateInstance(
               &GUID_304ce942_6e39_40d8_943a_b913c40c9cd4,
               0,
               1u,
               &GUID_f7898af5_cac4_4632_a2ec_da06e5111af2,
               &gFwApiMgr);
  v0 = Instance;
  if ( Instance < 0 )
  {
    v1 = (unsigned int)Instance;
    goto LABEL_9;
  }
  return v0;
}

```

## disassembly

```asm
0x180035b90  push    rbx
0x180035b92  sub     rsp, 30h
0x180035b96  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b9d  lea     rax, WPP_GLOBAL_Control
0x180035ba4  cmp     rcx, rax
0x180035ba7  jz      short loc_180035BC4
0x180035ba9  test    byte ptr [rcx+1Ch], 8
0x180035bad  jz      short loc_180035BC4
0x180035baf  mov     rcx, [rcx+10h]
0x180035bb3  lea     r8, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids
0x180035bba  mov     edx, 0Ch
0x180035bbf  call    WPP_SF_
0x180035bc4  xor     edx, edx; dwCoInit
0x180035bc6  xor     ecx, ecx; pvReserved
0x180035bc8  call    cs:__imp_CoInitializeEx
0x180035bce  mov     ecx, 80000000h
0x180035bd3  mov     cs:?gFwApiComInit@@3JA, eax; long gFwApiComInit
0x180035bd9  mov     ebx, eax
0x180035bdb  add     eax, ecx
0x180035bdd  test    ecx, eax
0x180035bdf  jnz     short loc_180035BED
0x180035be1  cmp     ebx, 80010106h
0x180035be7  jz      short loc_180035BED
0x180035be9  mov     edx, ebx
0x180035beb  jmp     short loc_180035C1B
0x180035bed  xor     edx, edx; pUnkOuter
0x180035bef  lea     rax, ?gFwApiMgr@@3PEAUINetFwMgr@@EA; INetFwMgr * gFwApiMgr
0x180035bf6  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x180035bfd  mov     [rsp+38h+ppv], rax; ppv
0x180035c02  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x180035c09  lea     r8d, [rdx+1]; dwClsContext
0x180035c0d  call    cs:__imp_CoCreateInstance
0x180035c13  mov     ebx, eax
0x180035c15  test    eax, eax
0x180035c17  jns     short loc_180035C3E
0x180035c19  mov     edx, eax
0x180035c1b  lea     rcx, aFwapihelperini_0; "FwApiHelperInit"
0x180035c22  call    cs:__imp_FwReportReturnError
0x180035c28  call    FwApiHelperFree
0x180035c2d  mov     edx, ebx
0x180035c2f  lea     rcx, aFwapihelperini_0; "FwApiHelperInit"
0x180035c36  call    cs:__imp_FwReportReturnError
0x180035c3c  mov     ebx, eax
0x180035c3e  mov     eax, ebx
0x180035c40  add     rsp, 30h
0x180035c44  pop     rbx
0x180035c45  retn
```
