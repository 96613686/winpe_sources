# FwApiHelperInit

- ea: `0x180038350`
- end: `0x18003841f`
- name: `FwApiHelperInit`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003336c`
- `0x1800382d0`
- `0x180038350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800383d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800383d3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180038388`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180038388`
- `fwbase!FwReportReturnError` at `0x1800383ee`
- `fwbase!FwReportReturnError` at `0x180038408`
- `fwbase!FwReportReturnError` at `0x1800383ee`
- `fwbase!FwReportReturnError` at `0x180038408`

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
0x180038350  push    rbx
0x180038352  sub     rsp, 30h
0x180038356  mov     rcx, cs:WPP_GLOBAL_Control
0x18003835d  lea     rax, WPP_GLOBAL_Control
0x180038364  cmp     rcx, rax
0x180038367  jz      short loc_180038384
0x180038369  test    byte ptr [rcx+1Ch], 8
0x18003836d  jz      short loc_180038384
0x18003836f  mov     rcx, [rcx+10h]
0x180038373  lea     r8, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids
0x18003837a  mov     edx, 0Ch
0x18003837f  call    WPP_SF_
0x180038384  xor     edx, edx; dwCoInit
0x180038386  xor     ecx, ecx; pvReserved
0x180038388  call    cs:__imp_CoInitializeEx
0x18003838f  nop     dword ptr [rax+rax+00h]
0x180038394  mov     ecx, 80000000h
0x180038399  mov     cs:?gFwApiComInit@@3JA, eax; long gFwApiComInit
0x18003839f  mov     ebx, eax
0x1800383a1  add     eax, ecx
0x1800383a3  test    ecx, eax
0x1800383a5  jnz     short loc_1800383B3
0x1800383a7  cmp     ebx, 80010106h
0x1800383ad  jz      short loc_1800383B3
0x1800383af  mov     edx, ebx
0x1800383b1  jmp     short loc_1800383E7
0x1800383b3  xor     edx, edx; pUnkOuter
0x1800383b5  lea     rax, ?gFwApiMgr@@3PEAUINetFwMgr@@EA; INetFwMgr * gFwApiMgr
0x1800383bc  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x1800383c3  mov     [rsp+38h+ppv], rax; ppv
0x1800383c8  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x1800383cf  lea     r8d, [rdx+1]; dwClsContext
0x1800383d3  call    cs:__imp_CoCreateInstance
0x1800383da  nop     dword ptr [rax+rax+00h]
0x1800383df  mov     ebx, eax
0x1800383e1  test    eax, eax
0x1800383e3  jns     short loc_180038416
0x1800383e5  mov     edx, eax
0x1800383e7  lea     rcx, aFwapihelperini_0; "FwApiHelperInit"
0x1800383ee  call    cs:__imp_FwReportReturnError
0x1800383f5  nop     dword ptr [rax+rax+00h]
0x1800383fa  call    FwApiHelperFree
0x1800383ff  mov     edx, ebx
0x180038401  lea     rcx, aFwapihelperini_0; "FwApiHelperInit"
0x180038408  call    cs:__imp_FwReportReturnError
0x18003840f  nop     dword ptr [rax+rax+00h]
0x180038414  mov     ebx, eax
0x180038416  mov     eax, ebx
0x180038418  add     rsp, 30h
0x18003841c  pop     rbx
0x18003841d  retn
```
