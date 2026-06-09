# SvcUpdateDescription(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &)

- ea: `0x14000bf9c`
- end: `0x14000c0b1`
- name: `?SvcUpdateDescription@@YAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000b60c`

## callees

- `0x140001008`
- `0x140001094`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x140009984`
- `0x14000bf9c`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14000c02e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14000c02e`

## string_xrefs

- `0x14000c043`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bfbe`: `SvcUpdateDescription`
- `0x14000bfec`: `Microsoft Windows MIDI Services core service for MIDI 1.0 and MIDI 2.0 message routing and device discovery / enumeration`
- `0x14000c03c`: `Changing service description failed.`
- `0x14000c062`: `Changing service description failed.`

## pseudocode

```c
__int64 __fastcall SvcUpdateDescription(SC_HANDLE *a1)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int128 *v5; // rax
  SC_HANDLE v6; // rcx
  unsigned int v7; // ebx
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  char *v12; // [rsp+20h] [rbp-58h]
  char v13[8]; // [rsp+30h] [rbp-48h] BYREF
  __int128 *Info; // [rsp+38h] [rbp-40h] BYREF
  const char *v15; // [rsp+40h] [rbp-38h] BYREF
  __int128 v16; // [rsp+48h] [rbp-30h] BYREF
  __int128 v17; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    *(_QWORD *)v13 = "SvcUpdateDescription";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)v2,
      (__int64)&byte_14008710F,
      v3,
      v4,
      v13);
  }
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&v16,
    L"Microsoft Windows MIDI Services core service for MIDI 1.0 and MIDI 2.0 message routing and device discovery / enumeration",
    0x79u);
  v5 = &v16;
  v6 = *a1;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v5 = (__int128 *)v16;
  v7 = 1;
  Info = v5;
  if ( !ChangeServiceConfig2W(v6, 1u, &Info) )
  {
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0x7A,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      "Changing service description failed.",
      v12);
    v8 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v8 > 2u )
    {
      v15 = "SvcUpdateDescription";
      *(_QWORD *)v13 = L"Changing service description failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (__int64)v8,
        (__int64)&byte_14008700F,
        v9,
        v10,
        &v15,
        v13);
    }
    v7 = 0;
  }
  std::wstring::~wstring((char **)&v16);
  return v7;
}

```

## disassembly

```asm
0x14000bf9c  push    rbp
0x14000bf9e  push    rbx
0x14000bf9f  push    rsi
0x14000bfa0  push    rdi
0x14000bfa1  mov     rbp, rsp
0x14000bfa4  sub     rsp, 78h
0x14000bfa8  mov     rax, cs:__security_cookie
0x14000bfaf  xor     rax, rsp
0x14000bfb2  mov     [rbp+var_10], rax
0x14000bfb6  mov     rdi, rcx
0x14000bfb9  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bfbe  lea     rsi, aSvcupdatedescr; "SvcUpdateDescription"
0x14000bfc5  mov     rcx, [rax+8]
0x14000bfc9  mov     eax, [rcx]
0x14000bfcb  cmp     eax, 4
0x14000bfce  jbe     short loc_14000BFE9
0x14000bfd0  lea     rax, [rbp+var_48]
0x14000bfd4  mov     qword ptr [rbp+var_48], rsi
0x14000bfd8  lea     rdx, byte_14008710F
0x14000bfdf  mov     [rsp+78h+var_58], rax; char *
0x14000bfe4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000bfe9  xorps   xmm0, xmm0
0x14000bfec  lea     rdx, aMicrosoftWindo; "Microsoft Windows MIDI Services core se"...
0x14000bff3  xorps   xmm1, xmm1
0x14000bff6  lea     rcx, [rbp+var_30]
0x14000bffa  mov     r8d, 79h ; 'y'
0x14000c000  movups  [rbp+var_30], xmm0
0x14000c004  movdqu  [rbp+var_20], xmm1
0x14000c009  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000c00e  cmp     qword ptr [rbp+var_20+8], 7
0x14000c013  lea     rax, [rbp+var_30]
0x14000c017  mov     rcx, [rdi]; hService
0x14000c01a  lea     r8, [rbp+Info]; lpInfo
0x14000c01e  cmova   rax, qword ptr [rbp+var_30]
0x14000c023  mov     ebx, 1
0x14000c028  mov     edx, ebx; dwInfoLevel
0x14000c02a  mov     [rbp+Info], rax
0x14000c02e  call    cs:__imp_ChangeServiceConfig2W
0x14000c034  test    eax, eax
0x14000c036  jnz     short loc_14000C091
0x14000c038  mov     rcx, [rbp+20h]; this
0x14000c03c  lea     r9, aChangingServic_1; "Changing service description failed."
0x14000c043  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000c04a  lea     edx, [rbx+79h]; void *
0x14000c04d  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000c052  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000c057  mov     rcx, [rax+8]
0x14000c05b  mov     eax, [rcx]
0x14000c05d  cmp     eax, 2
0x14000c060  jbe     short loc_14000C08F
0x14000c062  lea     rax, aChangingServic_2; "Changing service description failed."
0x14000c069  mov     [rbp+var_38], rsi
0x14000c06d  mov     qword ptr [rbp+var_48], rax
0x14000c071  lea     rdx, byte_14008700F
0x14000c078  lea     rax, [rbp+var_48]
0x14000c07c  mov     [rsp+78h+var_50], rax
0x14000c081  lea     rax, [rbp+var_38]
0x14000c085  mov     [rsp+78h+var_58], rax
0x14000c08a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000c08f  xor     ebx, ebx
0x14000c091  lea     rcx, [rbp+var_30]; void *
0x14000c095  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c09a  mov     eax, ebx
0x14000c09c  mov     rcx, [rbp+var_10]
0x14000c0a0  xor     rcx, rsp; StackCookie
0x14000c0a3  call    __security_check_cookie
0x14000c0a8  add     rsp, 78h
0x14000c0ac  pop     rdi
0x14000c0ad  pop     rsi
0x14000c0ae  pop     rbx
0x14000c0af  pop     rbp
0x14000c0b0  retn
```
