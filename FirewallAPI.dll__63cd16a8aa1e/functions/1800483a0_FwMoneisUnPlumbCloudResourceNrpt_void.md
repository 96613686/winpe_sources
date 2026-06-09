# FwMoneisUnPlumbCloudResourceNrpt(void)

- ea: `0x1800483a0`
- end: `0x180048615`
- name: `?FwMoneisUnPlumbCloudResourceNrpt@@YAKXZ`
- size: `629`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180047fa4`
- `0x180053310`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x1800483a0`
- `0x18005a9f4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180048572`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180048572`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800484e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800484e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800484f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800484f6`
- `ntdll!RtlNtStatusToDosError` at `0x18004853a`
- `ntdll!RtlNtStatusToDosError` at `0x18004853a`
- `fwbase!FwRegDeleteValue` at `0x1800485b2`
- `fwbase!FwRegDeleteValue` at `0x1800485b2`
- `fwbase!FwBaseFree` at `0x1800485cc`
- `fwbase!FwBaseFree` at `0x1800485cc`
- `fwbase!FwHResultToWindowsError` at `0x18004846f`
- `fwbase!FwHResultToWindowsError` at `0x18004846f`
- `fwbase!FwStringCopy` at `0x180048467`
- `fwbase!FwStringCopy` at `0x180048467`

## string_xrefs

- `0x1800484df`: `ntdll.dll`
- `0x180048406`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x180048516`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x180048522`: `TargetPath`
- `0x180048529`: `Dnscache`

## pseudocode

```c
__int64 FwMoneisUnPlumbCloudResourceNrpt(void)
{
  unsigned int v0; // eax
  ULONG v1; // eax
  unsigned int v2; // ebx
  FwPolicy2 *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  NTSTATUS v8; // eax
  _BYTE v10[48]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v12[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v13[22]; // [rsp+C0h] [rbp-40h]
  _BYTE v14[442]; // [rsp+D6h] [rbp-2Ah] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 426, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  memset_0(v10, 0, 0x40u);
  v12[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\dnscache";
  v12[1] = *(_OWORD *)L"urrentControlSet\\Services\\dnscache";
  v12[2] = *(_OWORD *)L"ntrolSet\\Services\\dnscache";
  v12[3] = *(_OWORD *)L"\\Services\\dnscache";
  *(_OWORD *)v13 = *(_OWORD *)L"s\\dnscache";
  *(_QWORD *)&v13[14] = *(_QWORD *)L"che";
  memset_0(v14, 0, 0x1B2u);
  v0 = FwStringCopy(L"EDP_", &v11);
  v1 = FwHResultToWindowsError(v0);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 427;
LABEL_8:
      v5 = v1;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v5);
LABEL_24:
      v3 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v1 = RasRemoveNrptRules(v10);
    v2 = v1;
    if ( v1 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 428;
        goto LABEL_8;
      }
    }
    else
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
      if ( ProcAddress
        && (v8 = ((__int64 (__fastcall *)(const wchar_t *, const wchar_t *, const wchar_t *, _QWORD, _OWORD *, int, _QWORD))ProcAddress)(
                   L"Dnscache",
                   L"TargetPath",
                   L"SYSTEM\\CurrentControlSet\\Services\\dnscache",
                   0,
                   v12,
                   520,
                   0),
            v1 = RtlNtStatusToDosError(v8),
            (v2 = v1) != 0) )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 429;
          goto LABEL_8;
        }
      }
      else
      {
        if ( !(unsigned int)_o_wcscat_s(v12, 260, L"\\Parameters") )
        {
          FwRegDeleteValue(-2147483646, v12, L"ShortnameProxyDefault");
          goto LABEL_24;
        }
        v2 = 87;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 430;
          v5 = 87;
          goto LABEL_9;
        }
      }
    }
  }
  if ( v11 )
  {
    FwBaseFree(v11);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v3 + 2), 431, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x1800483a0  push    rbp
0x1800483a2  push    rbx
0x1800483a3  push    rsi
0x1800483a4  push    rdi
0x1800483a5  lea     rbp, [rsp-1A8h]
0x1800483ad  sub     rsp, 2A8h
0x1800483b4  mov     rax, cs:__security_cookie
0x1800483bb  xor     rax, rsp
0x1800483be  mov     [rbp+1C0h+var_30], rax
0x1800483c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483cc  lea     rdi, WPP_GLOBAL_Control
0x1800483d3  lea     rsi, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800483da  cmp     rcx, rdi
0x1800483dd  jz      short loc_1800483F6
0x1800483df  test    byte ptr [rcx+1Ch], 8
0x1800483e3  jz      short loc_1800483F6
0x1800483e5  mov     rcx, [rcx+10h]
0x1800483e9  mov     edx, 1AAh
0x1800483ee  mov     r8, rsi
0x1800483f1  call    WPP_SF_
0x1800483f6  xor     edx, edx; Val
0x1800483f8  lea     rcx, [rsp+2C0h+var_280]; void *
0x1800483fd  lea     r8d, [rdx+40h]; Size
0x180048401  call    memset_0
0x180048406  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x18004840d  lea     rcx, [rbp+1C0h+var_1EA]; void *
0x180048411  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\dnscache"
0x180048418  xor     edx, edx; Val
0x18004841a  movaps  [rbp+1C0h+var_240], xmm0
0x18004841e  mov     r8d, 1B2h; Size
0x180048424  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\dnscache"
0x18004842b  movaps  [rbp+1C0h+var_230], xmm1
0x18004842f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\dnscache"
0x180048436  movaps  [rbp+1C0h+var_220], xmm0
0x18004843a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\dnscache"
0x180048441  movaps  [rbp+1C0h+var_210], xmm1
0x180048445  movsd   xmm1, qword ptr cs:aSystemCurrentc+4Eh; "che"
0x18004844d  movaps  xmmword ptr [rbp+1C0h+var_200], xmm0
0x180048451  movsd   qword ptr [rbp+1C0h+var_200+0Eh], xmm1
0x180048456  call    memset_0
0x18004845b  lea     rdx, [rsp+2C0h+var_250]
0x180048460  lea     rcx, aEdp; "EDP_"
0x180048467  call    cs:__imp_FwStringCopy
0x18004846d  mov     ecx, eax
0x18004846f  call    cs:__imp_FwHResultToWindowsError
0x180048475  mov     ebx, eax
0x180048477  test    eax, eax
0x180048479  jz      short loc_1800484AE
0x18004847b  mov     rcx, cs:WPP_GLOBAL_Control
0x180048482  cmp     rcx, rdi
0x180048485  jz      loc_1800485BF
0x18004848b  test    byte ptr [rcx+1Ch], 1
0x18004848f  jz      loc_1800485BF
0x180048495  mov     edx, 1ABh
0x18004849a  mov     r9d, eax
0x18004849d  mov     rcx, [rcx+10h]
0x1800484a1  mov     r8, rsi
0x1800484a4  call    WPP_SF_d
0x1800484a9  jmp     loc_1800485B8
0x1800484ae  lea     rcx, [rsp+2C0h+var_280]
0x1800484b3  call    RasRemoveNrptRules
0x1800484b8  mov     ebx, eax
0x1800484ba  test    eax, eax
0x1800484bc  jz      short loc_1800484DF
0x1800484be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484c5  cmp     rcx, rdi
0x1800484c8  jz      loc_1800485BF
0x1800484ce  test    byte ptr [rcx+1Ch], 1
0x1800484d2  jz      loc_1800485BF
0x1800484d8  mov     edx, 1ACh
0x1800484dd  jmp     short loc_18004849A
0x1800484df  lea     rcx, ModuleName; "ntdll.dll"
0x1800484e6  call    cs:__imp_GetModuleHandleW
0x1800484ec  mov     rcx, rax; hModule
0x1800484ef  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1800484f6  call    cs:__imp_GetProcAddress
0x1800484fc  test    rax, rax
0x1800484ff  jz      short loc_180048562
0x180048501  mov     [rsp+2C0h+var_290], 0
0x18004850a  lea     rcx, [rbp+1C0h+var_240]
0x18004850e  mov     [rsp+2C0h+var_298], 208h
0x180048516  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x18004851d  mov     [rsp+2C0h+var_2A0], rcx
0x180048522  lea     rdx, aTargetpath; "TargetPath"
0x180048529  lea     rcx, aDnscache; "Dnscache"
0x180048530  xor     r9d, r9d
0x180048533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048538  mov     ecx, eax; Status
0x18004853a  call    cs:__imp_RtlNtStatusToDosError
0x180048540  mov     ebx, eax
0x180048542  test    eax, eax
0x180048544  jz      short loc_180048562
0x180048546  mov     rcx, cs:WPP_GLOBAL_Control
0x18004854d  cmp     rcx, rdi
0x180048550  jz      short loc_1800485BF
0x180048552  test    byte ptr [rcx+1Ch], 1
0x180048556  jz      short loc_1800485BF
0x180048558  mov     edx, 1ADh
0x18004855d  jmp     loc_18004849A
0x180048562  lea     r8, aParameters; "\\Parameters"
0x180048569  mov     edx, 104h
0x18004856e  lea     rcx, [rbp+1C0h+var_240]
0x180048572  call    cs:__imp__o_wcscat_s
0x180048578  test    eax, eax
0x18004857a  jz      short loc_1800485A0
0x18004857c  mov     ebx, 57h ; 'W'
0x180048581  mov     rcx, cs:WPP_GLOBAL_Control
0x180048588  cmp     rcx, rdi
0x18004858b  jz      short loc_1800485BF
0x18004858d  test    byte ptr [rcx+1Ch], 1
0x180048591  jz      short loc_1800485BF
0x180048593  mov     edx, 1AEh
0x180048598  mov     r9d, ebx
0x18004859b  jmp     loc_18004849D
0x1800485a0  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x1800485a7  mov     rcx, 0FFFFFFFF80000002h
0x1800485ae  lea     rdx, [rbp+1C0h+var_240]
0x1800485b2  call    cs:__imp_FwRegDeleteValue
0x1800485b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800485bf  mov     rax, [rsp+2C0h+var_250]
0x1800485c4  test    rax, rax
0x1800485c7  jz      short loc_1800485D9
0x1800485c9  mov     rcx, rax
0x1800485cc  call    cs:__imp_FwBaseFree
0x1800485d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800485d9  cmp     rcx, rdi
0x1800485dc  jz      short loc_1800485F8
0x1800485de  test    byte ptr [rcx+1Ch], 8
0x1800485e2  jz      short loc_1800485F8
0x1800485e4  mov     rcx, [rcx+10h]
0x1800485e8  mov     edx, 1AFh
0x1800485ed  mov     r9d, ebx
0x1800485f0  mov     r8, rsi
0x1800485f3  call    WPP_SF_d
0x1800485f8  mov     eax, ebx
0x1800485fa  mov     rcx, [rbp+1C0h+var_30]
0x180048601  xor     rcx, rsp; StackCookie
0x180048604  call    __security_check_cookie
0x180048609  add     rsp, 2A8h
0x180048610  pop     rdi
0x180048611  pop     rsi
0x180048612  pop     rbx
0x180048613  pop     rbp
0x180048614  retn
```
