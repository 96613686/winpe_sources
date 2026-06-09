# MdmGetServiceTarget(ushort * *)

- ea: `0x1800036d0`
- end: `0x18000392c`
- name: `?MdmGetServiceTarget@@YAJPEAPEAG@Z`
- size: `604`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180002de8`
- `0x1800036d0`
- `0x180006174`
- `0x180006560`
- `0x1800065c0`
- `0x18001d4f4`

## string_xrefs

- `0x18000375f`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800038b4`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003803`: `CHR(MdmSettings::GetServiceTarget(strServiceTarget))`
- `0x1800038a0`: `CHR(StringCchPrintfW(pwszBuffer, strServiceTarget.length() + 1, strServiceTarget.c_str()))`
- `0x1800037ad`: `Software\Microsoft\MdmCommon\Internal`
- `0x1800037a6`: `CcpServiceTarget`
- `0x1800037e7`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800037d3`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszServiceTargetValueName, strServiceTarget))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MdmGetServiceTarget(unsigned __int16 **a1, int a2, __int64 a3)
{
  __int64 v4; // r8
  int StringValue; // ebx
  int v6; // edx
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // r8
  unsigned __int64 v11; // rdx
  char v13; // [rsp+20h] [rbp-29h]
  const char *v14; // [rsp+28h] [rbp-21h]
  int v15; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int16 *v16[2]; // [rsp+38h] [rbp-11h] BYREF
  __m128i si128; // [rsp+48h] [rbp-1h]
  _BYTE v18[16]; // [rsp+58h] [rbp+Fh] BYREF
  int *v19; // [rsp+68h] [rbp+1Fh]
  __int64 v20; // [rsp+70h] [rbp+27h]

  *(_OWORD *)v16 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16[0]) = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_GET_SERVICE_TARGET, a3, 1, v18);
  if ( !a1 )
  {
    v4 = 2147942487LL;
    StringValue = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_28;
    v14 = "CPR(ppwszBuffer)";
    v13 = 20;
    goto LABEL_6;
  }
  if ( *a1 )
  {
    v4 = 2147942487LL;
    StringValue = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        21,
        "CBR(*ppwszBuffer == nullptr)");
    goto LABEL_28;
  }
  StringValue = MdmRegistry::GetStringValue(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\MdmCommon\\Internal",
                  L"CcpServiceTarget",
                  v16);
  if ( StringValue < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_28;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      v6,
      StringValue,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      79,
      "CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszServiceTargetValueName, strServiceTarget))");
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_28;
    v14 = "CHR(MdmSettings::GetServiceTarget(strServiceTarget))";
    v13 = 23;
LABEL_15:
    LODWORD(v4) = StringValue;
LABEL_6:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      v4,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      v13,
      v14);
    goto LABEL_28;
  }
  v7 = 2 * (si128.m128i_i64[0] + 1);
  if ( !is_mul_ok(si128.m128i_i64[0] + 1, 2u) )
    v7 = -1;
  v8 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    StringValue = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_28;
    v14 = "CPR(pwszBuffer)";
    v13 = 26;
    goto LABEL_15;
  }
  v10 = (const unsigned __int16 *)v16;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = v16[0];
  StringValue = StringCchPrintfW(v8, si128.m128i_i64[0] + 1, v10);
  if ( StringValue >= 0 )
  {
    *a1 = v9;
  }
  else
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        v11,
        StringValue,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        27,
        "CHR(StringCchPrintfW(pwszBuffer, strServiceTarget.length() + 1, strServiceTarget.c_str()))");
    operator delete(v9, v11);
  }
LABEL_28:
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v15 = StringValue;
    v19 = &v15;
    v20 = 4;
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_GET_SERVICE_TARGET_RESULT, v4, 2, v18);
  }
  std::wstring::~wstring(v16);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x1800036d0  push    rbp
0x1800036d2  push    rbx
0x1800036d3  push    rsi
0x1800036d4  push    rdi
0x1800036d5  lea     rbp, [rsp-3Fh]
0x1800036da  sub     rsp, 88h
0x1800036e1  mov     rax, cs:__security_cookie
0x1800036e8  xor     rax, rsp
0x1800036eb  mov     [rbp+57h+var_28], rax
0x1800036ef  mov     rdi, rcx
0x1800036f2  xorps   xmm0, xmm0
0x1800036f5  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800036f9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180003701  movdqu  [rbp+57h+var_58], xmm1
0x180003706  xor     eax, eax
0x180003708  mov     word ptr [rbp+57h+var_68], ax
0x18000370c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003713  jz      short loc_180003730
0x180003715  lea     rax, [rbp+57h+var_48]
0x180003719  mov     [rsp+0A0h+var_80], rax
0x18000371e  mov     r9d, 1
0x180003724  lea     rdx, MDMCOMMON_TRACE_GET_SERVICE_TARGET
0x18000372b  call    McGenEventWrite_EventWriteTransfer
0x180003730  test    rdi, rdi
0x180003733  jnz     short loc_180003770
0x180003735  mov     r8d, 80070057h
0x18000373b  mov     ebx, r8d
0x18000373e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003745  jz      loc_1800038D0
0x18000374b  lea     rax, aCprPpwszbuffer; "CPR(ppwszBuffer)"
0x180003752  mov     [rsp+0A0h+var_78], rax
0x180003757  mov     dword ptr [rsp+0A0h+var_80], 214h
0x18000375f  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003766  call    McTemplateU0dsqs_EventWriteTransfer
0x18000376b  jmp     loc_1800038D0
0x180003770  cmp     qword ptr [rdi], 0
0x180003774  jz      short loc_1800037A2
0x180003776  mov     r8d, 80070057h
0x18000377c  mov     ebx, r8d
0x18000377f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003786  jz      loc_1800038D0
0x18000378c  lea     rax, aCbrPpwszbuffer; "CBR(*ppwszBuffer == nullptr)"
0x180003793  mov     [rsp+0A0h+var_78], rax
0x180003798  mov     dword ptr [rsp+0A0h+var_80], 215h
0x1800037a0  jmp     short loc_18000375F
0x1800037a2  lea     r9, [rbp+57h+var_68]
0x1800037a6  lea     r8, aCcpservicetarg; "CcpServiceTarget"
0x1800037ad  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x1800037b4  mov     rcx, 0FFFFFFFF80000002h
0x1800037bb  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x1800037c0  mov     ebx, eax
0x1800037c2  test    eax, eax
0x1800037c4  jns     short loc_18000381F
0x1800037c6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800037cd  jz      loc_1800038D0
0x1800037d3  lea     rax, aChrMdmregistry_3; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x1800037da  mov     [rsp+0A0h+var_78], rax
0x1800037df  mov     dword ptr [rsp+0A0h+var_80], 24Fh
0x1800037e7  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800037ee  mov     r8d, ebx
0x1800037f1  call    McTemplateU0dsqs_EventWriteTransfer
0x1800037f6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800037fd  jz      loc_1800038D0
0x180003803  lea     rax, aChrMdmsettings_16; "CHR(MdmSettings::GetServiceTarget(strSe"...
0x18000380a  mov     [rsp+0A0h+var_78], rax
0x18000380f  mov     dword ptr [rsp+0A0h+var_80], 217h
0x180003817  mov     r8d, ebx
0x18000381a  jmp     loc_18000375F
0x18000381f  mov     rcx, qword ptr [rbp+57h+var_58]
0x180003823  inc     rcx
0x180003826  mov     eax, 2
0x18000382b  mul     rcx
0x18000382e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003835  cmovb   rax, rcx
0x180003839  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003840  mov     rcx, rax; unsigned __int64
0x180003843  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003848  mov     rsi, rax
0x18000384b  test    rax, rax
0x18000384e  jnz     short loc_180003874
0x180003850  mov     ebx, 8007000Eh
0x180003855  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000385c  jz      short loc_1800038D0
0x18000385e  lea     rax, aCprPwszbuffer; "CPR(pwszBuffer)"
0x180003865  mov     [rsp+0A0h+var_78], rax
0x18000386a  mov     dword ptr [rsp+0A0h+var_80], 21Ah
0x180003872  jmp     short loc_180003817
0x180003874  lea     r8, [rbp+57h+var_68]
0x180003878  cmp     qword ptr [rbp+57h+var_58+8], 7
0x18000387d  cmova   r8, [rbp+57h+var_68]; unsigned __int16 *
0x180003882  mov     rdx, qword ptr [rbp+57h+var_58]
0x180003886  inc     rdx; unsigned __int64
0x180003889  mov     rcx, rsi; unsigned __int16 *
0x18000388c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003891  mov     ebx, eax
0x180003893  test    eax, eax
0x180003895  jns     short loc_1800038CD
0x180003897  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000389e  jz      short loc_1800038C3
0x1800038a0  lea     rax, aChrStringcchpr_2; "CHR(StringCchPrintfW(pwszBuffer, strSer"...
0x1800038a7  mov     [rsp+0A0h+var_78], rax
0x1800038ac  mov     dword ptr [rsp+0A0h+var_80], 21Bh
0x1800038b4  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800038bb  mov     r8d, ebx
0x1800038be  call    McTemplateU0dsqs_EventWriteTransfer
0x1800038c3  mov     rcx, rsi; void *
0x1800038c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800038cb  jmp     short loc_1800038D0
0x1800038cd  mov     [rdi], rsi
0x1800038d0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800038d7  jz      short loc_180003908
0x1800038d9  mov     [rbp+57h+var_70], ebx
0x1800038dc  lea     rax, [rbp+57h+var_70]
0x1800038e0  mov     [rbp+57h+var_38], rax
0x1800038e4  mov     [rbp+57h+var_30], 4
0x1800038ec  lea     rax, [rbp+57h+var_48]
0x1800038f0  mov     [rsp+0A0h+var_80], rax
0x1800038f5  mov     r9d, 2
0x1800038fb  lea     rdx, MDMCOMMON_TRACE_GET_SERVICE_TARGET_RESULT
0x180003902  call    McGenEventWrite_EventWriteTransfer
0x180003907  nop
0x180003908  lea     rcx, [rbp+57h+var_68]
0x18000390c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003911  mov     eax, ebx
0x180003913  mov     rcx, [rbp+57h+var_28]
0x180003917  xor     rcx, rsp; StackCookie
0x18000391a  call    __security_check_cookie
0x18000391f  add     rsp, 88h
0x180003926  pop     rdi
0x180003927  pop     rsi
0x180003928  pop     rbx
0x180003929  pop     rbp
0x18000392a  retn
```
