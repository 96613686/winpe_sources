# WaasMedic::CStackDataResetPlugin::EvaluateThresholdToResetDatastore(bool &)

- ea: `0x18003afc8`
- end: `0x18003b281`
- name: `?EvaluateThresholdToResetDatastore@CStackDataResetPlugin@WaasMedic@@QEAAJAEA_N@Z`
- size: `697`
- prototype: `int(WaasMedic::CStackDataResetPlugin *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x18003a650`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x180030954`
- `0x1800309a0`
- `0x18003a2fc`
- `0x18003afc8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b214`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b214`
- `OLEAUT32!__imp_VariantInit` at `0x18003b10f`
- `OLEAUT32!__imp_VariantInit` at `0x18003b10f`
- `OLEAUT32!__imp_VariantClear` at `0x18003b1f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003b237`
- `OLEAUT32!__imp_VariantClear` at `0x18003b1f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003b237`

## string_xrefs

- `0x18003b0a3`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003b0d8`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003b156`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003b1db`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CStackDataResetPlugin::EvaluateThresholdToResetDatastore(
        WaasMedic::CStackDataResetPlugin *this,
        bool *a2)
{
  __int64 (__fastcall ***v4)(_QWORD, _BYTE *, _OWORD *, unsigned int *); // rbx
  __int64 (__fastcall *v5)(_QWORD, _BYTE *, _OWORD *, unsigned int *); // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  WaasMedic::CStackDataResetPlugin *v9; // rcx
  const char *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // r14d
  __int64 v14; // rsi
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-59h]
  char *v17; // [rsp+28h] [rbp-51h]
  bool v18; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v19[2]; // [rsp+48h] [rbp-31h] BYREF
  char v20; // [rsp+50h] [rbp-29h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-21h] BYREF
  struct _FILETIME v22; // [rsp+60h] [rbp-19h] BYREF
  _BYTE pvarg[32]; // [rsp+68h] [rbp-11h] BYREF
  _OWORD v24[2]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v20 = 0;
  v19[0] = 30;
  v19[1] = 2;
  v4 = (__int64 (__fastcall ***)(_QWORD, _BYTE *, _OWORD *, unsigned int *))*((_QWORD *)this + 13);
  v5 = **v4;
  memset(v24, 0, sizeof(v24));
  std::wstring::_Construct<1,unsigned short const *>(v24, L"ThresholdToResetDS", 18);
  v6 = *((_QWORD *)this + 14);
  memset(pvarg, 0, sizeof(pvarg));
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  std::wstring::_Construct<1,unsigned short const *>(pvarg, v6, v7);
  v8 = v5(v4, pvarg, v24, v19);
  std::wstring::~wstring(pvarg);
  std::wstring::~wstring(v24);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)(unsigned int)v8,
      v16);
    return (unsigned int)v8;
  }
  v8 = WaasMedic::CStackDataResetPlugin::DatastoreCreationPassedThreshold(v9, v19[0], a2);
  if ( v8 < 0 )
  {
    v11 = "Failed to determine if creation threshold of datastore has been passed";
    v12 = 415;
LABEL_8:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)(unsigned int)v8,
      (int)v11,
      v17);
    return (unsigned int)v8;
  }
  if ( *a2 )
  {
    v13 = v19[0];
    v14 = *((_QWORD *)this + 14);
    VariantInit((VARIANTARG *)pvarg);
    *a2 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, _BYTE *))(**((_QWORD **)this + 12) + 16LL))(
           *((_QWORD *)this + 12),
           v14,
           L"LastRemediationRunTime",
           pvarg);
    if ( v8 < 0 )
    {
      v15 = 473;
LABEL_13:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
        (const char *)(unsigned int)v8,
        (int)"Failed to retrieve %ws for %ws from state provider",
        L"LastRemediationRunTime",
        v14);
LABEL_20:
      VariantClear((VARIANTARG *)pvarg);
      v11 = "Failed to determine if threshold to erase datastore has been passed";
      v12 = 426;
      goto LABEL_8;
    }
    if ( *(_WORD *)pvarg )
    {
      if ( *(_WORD *)pvarg != 8 )
      {
        v8 = -2147024292;
        v15 = 486;
        goto LABEL_13;
      }
      v22 = 0;
      v8 = WaasMedic::TimeHelper::StringToFileTime(*(const unsigned __int16 **)&pvarg[8], &v22);
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1ED,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
          (const char *)(unsigned int)v8,
          (int)"Failed to convert time string %ws to FILETIME",
          *(const char **)&pvarg[8]);
        goto LABEL_20;
      }
      SystemTimeAsFileTime = 0;
      v18 = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *a2 = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v22, SystemTimeAsFileTime, &v18) >= v13;
    }
    else
    {
      *a2 = 1;
      LogLevelW(4u, L"Variant for last remediation run time on StackDataReset is empty. Setting threshold as passed");
    }
    VariantClear((VARIANTARG *)pvarg);
    if ( !*a2 )
      LogLevelW(4u, L"It has been less than %d days since last datastore reset", v19[0]);
    return 0;
  }
  LogLevelW(4u, L"It has been less than %d days since creation of datastore", v19[0]);
  return 0;
}

```

## disassembly

```asm
0x18003afc8  mov     [rsp-8+arg_10], rbx
0x18003afcd  mov     [rsp-8+arg_18], rsi
0x18003afd2  push    rbp
0x18003afd3  push    rdi
0x18003afd4  push    r12
0x18003afd6  push    r14
0x18003afd8  push    r15
0x18003afda  lea     rbp, [rsp-37h]
0x18003afdf  sub     rsp, 0B0h
0x18003afe6  mov     rax, cs:__security_cookie
0x18003afed  xor     rax, rsp
0x18003aff0  mov     [rbp+57h+var_28], rax
0x18003aff4  mov     rdi, rdx
0x18003aff7  mov     r15, rcx
0x18003affa  xor     r12d, r12d
0x18003affd  mov     [rdx], r12b
0x18003b000  mov     [rbp+57h+var_80], r12b
0x18003b004  mov     [rbp+57h+var_88], 1Eh
0x18003b00b  mov     [rbp+57h+var_84], 2
0x18003b012  mov     rbx, [rcx+68h]
0x18003b016  mov     rax, [rbx]
0x18003b019  mov     rsi, [rax]
0x18003b01c  xorps   xmm0, xmm0
0x18003b01f  movups  [rbp+57h+var_48], xmm0
0x18003b023  xorps   xmm1, xmm1
0x18003b026  movdqu  [rbp+57h+var_38], xmm1
0x18003b02b  lea     r8d, [r12+12h]
0x18003b030  lea     rdx, aThresholdtores_0; "ThresholdToResetDS"
0x18003b037  lea     rcx, [rbp+57h+var_48]
0x18003b03b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b040  nop
0x18003b041  mov     rdx, [r15+70h]
0x18003b045  xorps   xmm0, xmm0
0x18003b048  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003b04c  xorps   xmm1, xmm1
0x18003b04f  movdqu  xmmword ptr [rbp+57h+pvarg+10h], xmm1
0x18003b054  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b058  inc     r8
0x18003b05b  cmp     [rdx+r8*2], r12w
0x18003b060  jnz     short loc_18003B058
0x18003b062  lea     rcx, [rbp+57h+pvarg]
0x18003b066  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b06b  nop
0x18003b06c  lea     r9, [rbp+57h+var_88]
0x18003b070  lea     r8, [rbp+57h+var_48]
0x18003b074  lea     rdx, [rbp+57h+pvarg]
0x18003b078  mov     rcx, rbx
0x18003b07b  mov     rax, rsi
0x18003b07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b083  mov     ebx, eax
0x18003b085  lea     rcx, [rbp+57h+pvarg]; void *
0x18003b089  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b08e  nop
0x18003b08f  lea     rcx, [rbp+57h+var_48]; void *
0x18003b093  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b098  test    ebx, ebx
0x18003b09a  jns     short loc_18003B0BB
0x18003b09c  mov     rcx, [rbp+5Fh]; this
0x18003b0a0  mov     r9d, ebx; char *
0x18003b0a3  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003b0aa  mov     edx, 19Ah; void *
0x18003b0af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b0b4  mov     eax, ebx
0x18003b0b6  jmp     loc_18003B259
0x18003b0bb  mov     r8, rdi; bool *
0x18003b0be  mov     edx, [rbp+57h+var_88]; unsigned int
0x18003b0c1  call    ?DatastoreCreationPassedThreshold@CStackDataResetPlugin@WaasMedic@@AEAAJKAEA_N@Z; WaasMedic::CStackDataResetPlugin::DatastoreCreationPassedThreshold(ulong,bool &)
0x18003b0c6  mov     ebx, eax
0x18003b0c8  test    eax, eax
0x18003b0ca  jns     short loc_18003B0F2
0x18003b0cc  lea     rax, aFailedToDeterm_1; "Failed to determine if creation thresho"...
0x18003b0d3  mov     edx, 19Fh; void *
0x18003b0d8  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003b0df  mov     r9d, ebx; char *
0x18003b0e2  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003b0e7  mov     rcx, [rbp+5Fh]; this
0x18003b0eb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b0f0  jmp     short loc_18003B0B4
0x18003b0f2  cmp     [rdi], r12b
0x18003b0f5  jnz     short loc_18003B103
0x18003b0f7  lea     rdx, aItHasBeenLessT_0; "It has been less than %d days since cre"...
0x18003b0fe  jmp     loc_18003B249
0x18003b103  mov     r14d, [rbp+57h+var_88]
0x18003b107  mov     rsi, [r15+70h]
0x18003b10b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b10f  call    cs:__imp_VariantInit
0x18003b115  nop
0x18003b116  mov     [rdi], r12b
0x18003b119  mov     rcx, [r15+60h]
0x18003b11d  mov     rax, [rcx]
0x18003b120  lea     r9, [rbp+57h+pvarg]
0x18003b124  lea     r15, aLastremediatio; "LastRemediationRunTime"
0x18003b12b  mov     r8, r15
0x18003b12e  mov     rdx, rsi
0x18003b131  mov     rax, [rax+10h]
0x18003b135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b13a  mov     ebx, eax
0x18003b13c  test    eax, eax
0x18003b13e  jns     short loc_18003B170
0x18003b140  mov     edx, 1D9h; void *
0x18003b145  mov     [rsp+0D0h+var_A0], rsi
0x18003b14a  mov     [rsp+0D0h+var_A8], r15; char *
0x18003b14f  lea     rax, aFailedToRetrie_0; "Failed to retrieve %ws for %ws from sta"...
0x18003b156  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003b15d  mov     r9d, ebx; char *
0x18003b160  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003b165  mov     rcx, [rbp+5Fh]; this
0x18003b169  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b16e  jmp     short loc_18003B1ED
0x18003b170  movzx   eax, word ptr [rbp+57h+pvarg]
0x18003b174  test    ax, ax
0x18003b177  jnz     short loc_18003B192
0x18003b179  mov     byte ptr [rdi], 1
0x18003b17c  lea     rdx, aVariantForLast_0; "Variant for last remediation run time o"...
0x18003b183  mov     ecx, 4; unsigned __int8
0x18003b188  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003b18d  jmp     loc_18003B233
0x18003b192  mov     ecx, 8
0x18003b197  cmp     cx, ax
0x18003b19a  jz      short loc_18003B1A8
0x18003b19c  mov     ebx, 8007025Ch
0x18003b1a1  mov     edx, 1E6h
0x18003b1a6  jmp     short loc_18003B145
0x18003b1a8  mov     qword ptr [rbp+57h+var_70.dwLowDateTime], r12
0x18003b1ac  lea     rdx, [rbp+57h+var_70]; struct _FILETIME *
0x18003b1b0  mov     rcx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18003b1b4  call    ?StringToFileTime@TimeHelper@WaasMedic@@SAJPEBGPEAU_FILETIME@@@Z; WaasMedic::TimeHelper::StringToFileTime(ushort const *,_FILETIME *)
0x18003b1b9  mov     ebx, eax
0x18003b1bb  test    eax, eax
0x18003b1bd  jns     short loc_18003B208
0x18003b1bf  mov     rcx, [rbp+5Fh]; this
0x18003b1c3  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x18003b1c7  mov     [rsp+0D0h+var_A8], rax; char *
0x18003b1cc  lea     rax, aFailedToConver_3; "Failed to convert time string %ws to FI"...
0x18003b1d3  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003b1d8  mov     r9d, ebx; char *
0x18003b1db  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003b1e2  mov     edx, 1EDh; void *
0x18003b1e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b1ec  nop
0x18003b1ed  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b1f1  call    cs:__imp_VariantClear
0x18003b1f7  lea     rax, aFailedToDeterm_0; "Failed to determine if threshold to era"...
0x18003b1fe  mov     edx, 1AAh
0x18003b203  jmp     loc_18003B0D8
0x18003b208  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18003b20c  mov     [rbp+57h+var_90], r12b
0x18003b210  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b214  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b21a  lea     r8, [rbp+57h+var_90]; bool *
0x18003b21e  mov     rdx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18003b222  mov     rcx, qword ptr [rbp+57h+var_70.dwLowDateTime]; struct _FILETIME
0x18003b226  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x18003b22b  cmp     eax, r14d
0x18003b22e  setnb   al
0x18003b231  mov     [rdi], al
0x18003b233  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b237  call    cs:__imp_VariantClear
0x18003b23d  cmp     [rdi], r12b
0x18003b240  jnz     short loc_18003B257
0x18003b242  lea     rdx, aItHasBeenLessT; "It has been less than %d days since las"...
0x18003b249  mov     r8d, [rbp+57h+var_88]
0x18003b24d  mov     ecx, 4; unsigned __int8
0x18003b252  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003b257  xor     eax, eax
0x18003b259  mov     rcx, [rbp+57h+var_28]
0x18003b25d  xor     rcx, rsp; StackCookie
0x18003b260  call    __security_check_cookie
0x18003b265  lea     r11, [rsp+0D0h+var_20]
0x18003b26d  mov     rbx, [r11+40h]
0x18003b271  mov     rsi, [r11+48h]
0x18003b275  mov     rsp, r11
0x18003b278  pop     r15
0x18003b27a  pop     r14
0x18003b27c  pop     r12
0x18003b27e  pop     rdi
0x18003b27f  pop     rbp
0x18003b280  retn
```
