# FwMoneisUnPlumbCloudResourceNrpt(void)

- ea: `0x18004bd90`
- end: `0x18004c036`
- name: `?FwMoneisUnPlumbCloudResourceNrpt@@YAKXZ`
- size: `678`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18004b920`
- `0x180056b50`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x18004bd90`
- `0x18005eb98`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004bf80`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004bf80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004bee2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004bee2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bef8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bef8`
- `ntdll!RtlNtStatusToDosError` at `0x18004bf42`
- `ntdll!RtlNtStatusToDosError` at `0x18004bf42`
- `fwbase!FwRegDeleteValue` at `0x18004bfc6`
- `fwbase!FwRegDeleteValue` at `0x18004bfc6`
- `fwbase!FwBaseFree` at `0x18004bfe6`
- `fwbase!FwBaseFree` at `0x18004bfe6`
- `fwbase!FwHResultToWindowsError` at `0x18004be65`
- `fwbase!FwHResultToWindowsError` at `0x18004be65`
- `fwbase!FwStringCopy` at `0x18004be57`
- `fwbase!FwStringCopy` at `0x18004be57`

## string_xrefs

- `0x18004bedb`: `ntdll.dll`
- `0x18004bdf6`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x18004bf1e`: `SYSTEM\CurrentControlSet\Services\dnscache`
- `0x18004bf2a`: `TargetPath`
- `0x18004bf31`: `Dnscache`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 425, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
      v4 = 426;
LABEL_8:
      v5 = v1;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v5);
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
        v4 = 427;
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
          v4 = 428;
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
          v4 = 429;
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
    WPP_SF_d(*((_QWORD *)v3 + 2), 430, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18004bd90  push    rbp
0x18004bd92  push    rbx
0x18004bd93  push    rsi
0x18004bd94  push    rdi
0x18004bd95  lea     rbp, [rsp-1A8h]
0x18004bd9d  sub     rsp, 2A8h
0x18004bda4  mov     rax, cs:__security_cookie
0x18004bdab  xor     rax, rsp
0x18004bdae  mov     [rbp+1C0h+var_30], rax
0x18004bdb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bdbc  lea     rdi, WPP_GLOBAL_Control
0x18004bdc3  lea     rsi, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004bdca  cmp     rcx, rdi
0x18004bdcd  jz      short loc_18004BDE6
0x18004bdcf  test    byte ptr [rcx+1Ch], 8
0x18004bdd3  jz      short loc_18004BDE6
0x18004bdd5  mov     rcx, [rcx+10h]
0x18004bdd9  mov     edx, 1A9h
0x18004bdde  mov     r8, rsi
0x18004bde1  call    WPP_SF_
0x18004bde6  xor     edx, edx; Val
0x18004bde8  lea     rcx, [rsp+2C0h+var_280]; void *
0x18004bded  lea     r8d, [rdx+40h]; Size
0x18004bdf1  call    memset_0
0x18004bdf6  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x18004bdfd  lea     rcx, [rbp+1C0h+var_1EA]; void *
0x18004be01  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\dnscache"
0x18004be08  xor     edx, edx; Val
0x18004be0a  movaps  [rbp+1C0h+var_240], xmm0
0x18004be0e  mov     r8d, 1B2h; Size
0x18004be14  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\dnscache"
0x18004be1b  movaps  [rbp+1C0h+var_230], xmm1
0x18004be1f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\dnscache"
0x18004be26  movaps  [rbp+1C0h+var_220], xmm0
0x18004be2a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\dnscache"
0x18004be31  movaps  [rbp+1C0h+var_210], xmm1
0x18004be35  movsd   xmm1, qword ptr cs:aSystemCurrentc+4Eh; "che"
0x18004be3d  movaps  xmmword ptr [rbp+1C0h+var_200], xmm0
0x18004be41  movsd   qword ptr [rbp+1C0h+var_200+0Eh], xmm1
0x18004be46  call    memset_0
0x18004be4b  lea     rdx, [rsp+2C0h+var_250]
0x18004be50  lea     rcx, aEdp; "EDP_"
0x18004be57  call    cs:__imp_FwStringCopy
0x18004be5e  nop     dword ptr [rax+rax+00h]
0x18004be63  mov     ecx, eax
0x18004be65  call    cs:__imp_FwHResultToWindowsError
0x18004be6c  nop     dword ptr [rax+rax+00h]
0x18004be71  mov     ebx, eax
0x18004be73  test    eax, eax
0x18004be75  jz      short loc_18004BEAA
0x18004be77  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be7e  cmp     rcx, rdi
0x18004be81  jz      loc_18004BFD9
0x18004be87  test    byte ptr [rcx+1Ch], 1
0x18004be8b  jz      loc_18004BFD9
0x18004be91  mov     edx, 1AAh
0x18004be96  mov     r9d, eax
0x18004be99  mov     rcx, [rcx+10h]
0x18004be9d  mov     r8, rsi
0x18004bea0  call    WPP_SF_d
0x18004bea5  jmp     loc_18004BFD2
0x18004beaa  lea     rcx, [rsp+2C0h+var_280]
0x18004beaf  call    RasRemoveNrptRules
0x18004beb4  mov     ebx, eax
0x18004beb6  test    eax, eax
0x18004beb8  jz      short loc_18004BEDB
0x18004beba  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bec1  cmp     rcx, rdi
0x18004bec4  jz      loc_18004BFD9
0x18004beca  test    byte ptr [rcx+1Ch], 1
0x18004bece  jz      loc_18004BFD9
0x18004bed4  mov     edx, 1ABh
0x18004bed9  jmp     short loc_18004BE96
0x18004bedb  lea     rcx, ModuleName; "ntdll.dll"
0x18004bee2  call    cs:__imp_GetModuleHandleW
0x18004bee9  nop     dword ptr [rax+rax+00h]
0x18004beee  mov     rcx, rax; hModule
0x18004bef1  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18004bef8  call    cs:__imp_GetProcAddress
0x18004beff  nop     dword ptr [rax+rax+00h]
0x18004bf04  test    rax, rax
0x18004bf07  jz      short loc_18004BF70
0x18004bf09  mov     [rsp+2C0h+var_290], 0
0x18004bf12  lea     rcx, [rbp+1C0h+var_240]
0x18004bf16  mov     [rsp+2C0h+var_298], 208h
0x18004bf1e  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\dn"...
0x18004bf25  mov     [rsp+2C0h+var_2A0], rcx
0x18004bf2a  lea     rdx, aTargetpath; "TargetPath"
0x18004bf31  lea     rcx, aDnscache; "Dnscache"
0x18004bf38  xor     r9d, r9d
0x18004bf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf40  mov     ecx, eax; Status
0x18004bf42  call    cs:__imp_RtlNtStatusToDosError
0x18004bf49  nop     dword ptr [rax+rax+00h]
0x18004bf4e  mov     ebx, eax
0x18004bf50  test    eax, eax
0x18004bf52  jz      short loc_18004BF70
0x18004bf54  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bf5b  cmp     rcx, rdi
0x18004bf5e  jz      short loc_18004BFD9
0x18004bf60  test    byte ptr [rcx+1Ch], 1
0x18004bf64  jz      short loc_18004BFD9
0x18004bf66  mov     edx, 1ACh
0x18004bf6b  jmp     loc_18004BE96
0x18004bf70  lea     r8, aParameters; "\\Parameters"
0x18004bf77  mov     edx, 104h
0x18004bf7c  lea     rcx, [rbp+1C0h+var_240]
0x18004bf80  call    cs:__imp__o_wcscat_s
0x18004bf87  nop     dword ptr [rax+rax+00h]
0x18004bf8c  test    eax, eax
0x18004bf8e  jz      short loc_18004BFB4
0x18004bf90  mov     ebx, 57h ; 'W'
0x18004bf95  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bf9c  cmp     rcx, rdi
0x18004bf9f  jz      short loc_18004BFD9
0x18004bfa1  test    byte ptr [rcx+1Ch], 1
0x18004bfa5  jz      short loc_18004BFD9
0x18004bfa7  mov     edx, 1ADh
0x18004bfac  mov     r9d, ebx
0x18004bfaf  jmp     loc_18004BE99
0x18004bfb4  lea     r8, aShortnameproxy; "ShortnameProxyDefault"
0x18004bfbb  mov     rcx, 0FFFFFFFF80000002h
0x18004bfc2  lea     rdx, [rbp+1C0h+var_240]
0x18004bfc6  call    cs:__imp_FwRegDeleteValue
0x18004bfcd  nop     dword ptr [rax+rax+00h]
0x18004bfd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bfd9  mov     rax, [rsp+2C0h+var_250]
0x18004bfde  test    rax, rax
0x18004bfe1  jz      short loc_18004BFF9
0x18004bfe3  mov     rcx, rax
0x18004bfe6  call    cs:__imp_FwBaseFree
0x18004bfed  nop     dword ptr [rax+rax+00h]
0x18004bff2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bff9  cmp     rcx, rdi
0x18004bffc  jz      short loc_18004C018
0x18004bffe  test    byte ptr [rcx+1Ch], 8
0x18004c002  jz      short loc_18004C018
0x18004c004  mov     rcx, [rcx+10h]
0x18004c008  mov     edx, 1AEh
0x18004c00d  mov     r9d, ebx
0x18004c010  mov     r8, rsi
0x18004c013  call    WPP_SF_d
0x18004c018  mov     eax, ebx
0x18004c01a  mov     rcx, [rbp+1C0h+var_30]
0x18004c021  xor     rcx, rsp; StackCookie
0x18004c024  call    __security_check_cookie
0x18004c029  add     rsp, 2A8h
0x18004c030  pop     rdi
0x18004c031  pop     rsi
0x18004c032  pop     rbx
0x18004c033  pop     rbp
0x18004c034  retn
```
