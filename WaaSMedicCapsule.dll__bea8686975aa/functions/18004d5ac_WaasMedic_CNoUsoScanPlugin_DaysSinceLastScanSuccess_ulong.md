# WaasMedic::CNoUsoScanPlugin::DaysSinceLastScanSuccess(ulong *)

- ea: `0x18004d5ac`
- end: `0x18004d7ae`
- name: `?DaysSinceLastScanSuccess@CNoUsoScanPlugin@WaasMedic@@AEAAJPEAK@Z`
- size: `514`
- prototype: `__int64 __fastcall(WaasMedic::CNoUsoScanPlugin *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18004d7c0`

## callees

- `0x1800024a4`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x180030954`
- `0x18004d5ac`
- `0x180055fb8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004d75f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004d75f`

## string_xrefs

- `0x18004d5cf`: `onecore\enduser\waasmedic\lib\plugins\nousoscanplugin.cpp`
- `0x18004d622`: `onecore\enduser\waasmedic\lib\plugins\nousoscanplugin.cpp`
- `0x18004d6aa`: `Error when attempting to retrieve last USO scan time. hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CNoUsoScanPlugin::DaysSinceLastScanSuccess(
        WaasMedic::CNoUsoScanPlugin *this,
        unsigned int *a2)
{
  unsigned int v3; // ebx
  int v5; // eax
  int v6; // eax
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  int v9; // r9d
  int v10; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+40h] [rbp-20h] BYREF
  __int128 v12; // [rsp+48h] [rbp-18h] BYREF
  __int64 v13; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  WaasMedic::CNoUsoScanPlugin *v15; // [rsp+80h] [rbp+20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+28h] BYREF
  struct _FILETIME v17; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 *v18; // [rsp+98h] [rbp+38h] BYREF

  v15 = this;
  if ( !a2 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\nousoscanplugin.cpp",
      (const char *)0x80004003LL,
      v10);
    return v3;
  }
  v17 = 0;
  SystemTimeAsFileTime = 0;
  LOBYTE(v15) = 0;
  v13 = 0;
  v12 = 0;
  v5 = WaasMedic::UsoHelper::Initialize((WaasMedic::UsoHelper *)&v12);
  v3 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\nousoscanplugin.cpp",
      (const char *)(unsigned int)v5,
      v10);
    if ( *((_QWORD *)&v12 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v12 + 1) + 16LL))(*((_QWORD *)&v12 + 1));
    if ( (_QWORD)v12 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 16LL))(v12);
    return v3;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, struct _FILETIME *))(*(_QWORD *)v12 + 64LL))(v12, &v17);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\usohelper.cpp",
      (const char *)(unsigned int)v6,
      v10);
    if ( v3 != -2145083107 )
    {
      LogLevelW(2u, L"Error when attempting to retrieve last USO scan time. hr=0x%08X", v3);
      v7 = WaasMedic::TelemetryProvider::Provider();
      if ( *(_DWORD *)v7 > 5u )
      {
        v8 = *((_QWORD *)v7 + 3);
        if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
        {
          LODWORD(v15) = v3;
          v18 = &gc_pszVersionString;
          v11 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v7,
            (unsigned int)&word_18008A18E,
            0,
            v9,
            (__int64)&v11,
            (__int64)&v18,
            (__int64)&v15);
        }
      }
      if ( *((_QWORD *)&v12 + 1) )
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)&v12 + 1) + 16LL))(*((_QWORD *)&v12 + 1), v8);
      if ( (_QWORD)v12 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v12 + 16LL))(v12, v8);
      return v3;
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *a2 = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(v17, SystemTimeAsFileTime, (bool *)&v15);
  if ( *((_QWORD *)&v12 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v12 + 1) + 16LL))(*((_QWORD *)&v12 + 1));
  if ( (_QWORD)v12 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x18004d5ac  mov     [rsp-18h+arg_0], rcx
0x18004d5b1  push    rbp
0x18004d5b2  push    rbx
0x18004d5b3  push    rdi
0x18004d5b4  mov     rbp, rsp
0x18004d5b7  sub     rsp, 60h
0x18004d5bb  mov     rdi, rdx
0x18004d5be  test    rdx, rdx
0x18004d5c1  jnz     short loc_18004D5E7
0x18004d5c3  mov     rcx, [rbp+18h]; this
0x18004d5c7  mov     ebx, 80004003h
0x18004d5cc  mov     r9d, ebx; char *
0x18004d5cf  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004d5d6  mov     edx, 0E1h; void *
0x18004d5db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5e0  mov     eax, ebx
0x18004d5e2  jmp     loc_18004D7A6
0x18004d5e7  mov     qword ptr [rbp+arg_10.dwLowDateTime], 0
0x18004d5ef  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004d5f7  mov     byte ptr [rbp+arg_0], 0
0x18004d5fb  xor     eax, eax
0x18004d5fd  mov     [rbp+var_8], rax
0x18004d601  xorps   xmm1, xmm1
0x18004d604  movdqu  [rbp+var_18], xmm1
0x18004d609  mov     byte ptr [rbp+var_8], al
0x18004d60c  lea     rcx, [rbp+var_18]; this
0x18004d610  call    ?Initialize@UsoHelper@WaasMedic@@QEAAJXZ; WaasMedic::UsoHelper::Initialize(void)
0x18004d615  mov     ebx, eax
0x18004d617  test    eax, eax
0x18004d619  jns     short loc_18004D665
0x18004d61b  mov     rcx, [rbp+18h]; this
0x18004d61f  mov     r9d, eax; char *
0x18004d622  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004d629  mov     edx, 0EAh; void *
0x18004d62e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d633  nop
0x18004d634  mov     rcx, qword ptr [rbp+var_18+8]
0x18004d638  test    rcx, rcx
0x18004d63b  jz      short loc_18004D64A
0x18004d63d  mov     rax, [rcx]
0x18004d640  mov     rax, [rax+10h]
0x18004d644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d649  nop
0x18004d64a  mov     rcx, qword ptr [rbp+var_18]
0x18004d64e  test    rcx, rcx
0x18004d651  jz      short loc_18004D660
0x18004d653  mov     rax, [rcx]
0x18004d656  mov     rax, [rax+10h]
0x18004d65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d65f  nop
0x18004d660  jmp     loc_18004D5E0
0x18004d665  mov     rcx, qword ptr [rbp+var_18]
0x18004d669  mov     rax, [rcx]
0x18004d66c  lea     rdx, [rbp+arg_10]
0x18004d670  mov     rax, [rax+40h]
0x18004d674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d679  mov     ebx, eax
0x18004d67b  test    eax, eax
0x18004d67d  jns     loc_18004D75B
0x18004d683  mov     rcx, [rbp+18h]; this
0x18004d687  mov     r9d, eax; char *
0x18004d68a  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18004d691  mov     edx, 119h; void *
0x18004d696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d69b  cmp     ebx, 8024A11Dh
0x18004d6a1  jz      loc_18004D75B
0x18004d6a7  mov     r8d, ebx
0x18004d6aa  lea     rdx, aErrorWhenAttem; "Error when attempting to retrieve last "...
0x18004d6b1  mov     ecx, 2; unsigned __int8
0x18004d6b6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004d6bb  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004d6c0  mov     ecx, [rax]
0x18004d6c2  cmp     ecx, 5
0x18004d6c5  jbe     short loc_18004D72A
0x18004d6c7  mov     rdx, [rax+18h]
0x18004d6cb  mov     rcx, [rax+10h]
0x18004d6cf  mov     r8, 400000000000h
0x18004d6d9  test    r8, rcx
0x18004d6dc  jz      short loc_18004D72A
0x18004d6de  mov     rcx, rdx
0x18004d6e1  and     rcx, r8
0x18004d6e4  cmp     rcx, rdx
0x18004d6e7  jnz     short loc_18004D72A
0x18004d6e9  mov     dword ptr [rbp+arg_0], ebx
0x18004d6ec  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18004d6f3  mov     [rbp+arg_18], rcx
0x18004d6f7  mov     [rbp+var_20], 1000000h
0x18004d6ff  lea     rcx, [rbp+arg_0]
0x18004d703  mov     [rsp+60h+var_30], rcx
0x18004d708  lea     rcx, [rbp+arg_18]
0x18004d70c  mov     [rsp+60h+var_38], rcx
0x18004d711  lea     rcx, [rbp+var_20]
0x18004d715  mov     [rsp+60h+var_40], rcx
0x18004d71a  lea     rdx, word_18008A18E
0x18004d721  mov     rcx, rax
0x18004d724  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18004d729  nop
0x18004d72a  mov     rcx, qword ptr [rbp+var_18+8]
0x18004d72e  test    rcx, rcx
0x18004d731  jz      short loc_18004D740
0x18004d733  mov     rax, [rcx]
0x18004d736  mov     rax, [rax+10h]
0x18004d73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d73f  nop
0x18004d740  mov     rcx, qword ptr [rbp+var_18]
0x18004d744  test    rcx, rcx
0x18004d747  jz      short loc_18004D756
0x18004d749  mov     rax, [rcx]
0x18004d74c  mov     rax, [rax+10h]
0x18004d750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d755  nop
0x18004d756  jmp     loc_18004D5E0
0x18004d75b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004d75f  call    cs:__imp_GetSystemTimeAsFileTime
0x18004d765  lea     r8, [rbp+arg_0]; bool *
0x18004d769  mov     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x18004d76d  mov     rcx, qword ptr [rbp+arg_10.dwLowDateTime]; struct _FILETIME
0x18004d771  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x18004d776  mov     [rdi], eax
0x18004d778  mov     rcx, qword ptr [rbp+var_18+8]
0x18004d77c  test    rcx, rcx
0x18004d77f  jz      short loc_18004D78E
0x18004d781  mov     rax, [rcx]
0x18004d784  mov     rax, [rax+10h]
0x18004d788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d78d  nop
0x18004d78e  mov     rcx, qword ptr [rbp+var_18]
0x18004d792  test    rcx, rcx
0x18004d795  jz      short loc_18004D7A4
0x18004d797  mov     rax, [rcx]
0x18004d79a  mov     rax, [rax+10h]
0x18004d79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7a3  nop
0x18004d7a4  xor     eax, eax
0x18004d7a6  add     rsp, 60h
0x18004d7aa  pop     rdi
0x18004d7ab  pop     rbx
0x18004d7ac  pop     rbp
0x18004d7ad  retn
```
