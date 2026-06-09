# SvcSetStartTriggerRpc(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &)

- ea: `0x14000ba28`
- end: `0x14000bbb4`
- name: `?SvcSetStartTriggerRpc@@YAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x14000b60c`

## callees

- `0x140001008`
- `0x140001094`
- `0x1400054c0`
- `0x14000984c`
- `0x140009984`
- `0x14000ba28`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14000bb2b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x14000bb2b`

## string_xrefs

- `0x14000bb40`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bb39`: `Changing service trigger to RPC call failed.`
- `0x14000bb61`: `Changing service trigger to RPC call failed.`

## pseudocode

```c
__int64 __fastcall SvcSetStartTriggerRpc(SC_HANDLE *a1)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rax
  SC_HANDLE v6; // rcx
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v11; // [rsp+20h] [rbp-99h]
  char v12[8]; // [rsp+30h] [rbp-89h] BYREF
  const char *v13; // [rsp+38h] [rbp-81h] BYREF
  _DWORD v14[2]; // [rsp+40h] [rbp-79h] BYREF
  _OWORD *v15; // [rsp+48h] [rbp-71h]
  _DWORD v16[2]; // [rsp+50h] [rbp-69h] BYREF
  const GUID *v17; // [rsp+58h] [rbp-61h]
  __int64 v18; // [rsp+60h] [rbp-59h]
  _DWORD *v19; // [rsp+68h] [rbp-51h]
  _QWORD Info[4]; // [rsp+70h] [rbp-49h] BYREF
  _OWORD v21[3]; // [rsp+90h] [rbp-29h] BYREF
  _OWORD v22[2]; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    *(_QWORD *)v12 = "SvcSetStartTriggerRpc";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)v2,
      (__int64)&word_140086EDE,
      v3,
      v4,
      v12);
  }
  v5 = -1;
  v21[0] = *(_OWORD *)L"64839251-9daf-4e79-aa4e-9771c86ffbc1";
  v21[2] = *(_OWORD *)L"79-aa4e-9771c86ffbc1";
  v14[0] = 2;
  v21[1] = *(_OWORD *)L"-9daf-4e79-aa4e-9771c86ffbc1";
  v22[0] = *(_OWORD *)L"9771c86ffbc1";
  *(_OWORD *)((char *)v22 + 10) = *(_OWORD *)L"86ffbc1";
  do
    ++v5;
  while ( *((_WORD *)v21 + v5) );
  v6 = *a1;
  v14[1] = 2 * v5 + 2;
  v16[0] = 6;
  v15 = v21;
  v16[1] = 1;
  v17 = &RPC_INTERFACE_EVENT_GUID;
  v19 = v14;
  Info[1] = v16;
  v18 = 1;
  Info[0] = 1;
  Info[2] = 0;
  if ( ChangeServiceConfig2W(v6, 8u, Info) )
    return 1;
  wil::details::in1diag3::Log_GetLastErrorMsg(
    retaddr,
    (void *)0xA7,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
    "Changing service trigger to RPC call failed.",
    v11);
  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 2u )
  {
    v13 = "SvcSetStartTriggerRpc";
    *(_QWORD *)v12 = L"Changing service trigger to RPC call failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)&word_140086F2E,
      v8,
      v9,
      &v13,
      v12);
  }
  return 0;
}

```

## disassembly

```asm
0x14000ba28  push    rbp
0x14000ba2a  push    rbx
0x14000ba2b  push    rdi
0x14000ba2c  push    r14
0x14000ba2e  lea     rbp, [rsp-3Fh]
0x14000ba33  sub     rsp, 0F8h
0x14000ba3a  mov     rax, cs:__security_cookie
0x14000ba41  xor     rax, rsp
0x14000ba44  mov     [rbp+57h+var_30], rax
0x14000ba48  mov     rbx, rcx
0x14000ba4b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000ba50  lea     rdi, aSvcsetstarttri; "SvcSetStartTriggerRpc"
0x14000ba57  mov     rcx, [rax+8]
0x14000ba5b  mov     eax, [rcx]
0x14000ba5d  cmp     eax, 4
0x14000ba60  jbe     short loc_14000BA7D
0x14000ba62  lea     rax, [rsp+110h+var_E0]
0x14000ba67  mov     qword ptr [rsp+110h+var_E0], rdi
0x14000ba6c  lea     rdx, word_140086EDE
0x14000ba73  mov     [rsp+110h+var_F0], rax; char *
0x14000ba78  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000ba7d  movaps  xmm0, xmmword ptr cs:a648392519daf4e; "64839251-9daf-4e79-aa4e-9771c86ffbc1"
0x14000ba84  lea     rcx, [rbp+57h+var_80]
0x14000ba88  movaps  xmm1, xmmword ptr cs:a648392519daf4e+10h; "-9daf-4e79-aa4e-9771c86ffbc1"
0x14000ba8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ba93  movaps  [rbp+57h+var_80], xmm0
0x14000ba97  xor     r14d, r14d
0x14000ba9a  movaps  xmm0, xmmword ptr cs:a648392519daf4e+20h; "79-aa4e-9771c86ffbc1"
0x14000baa1  movaps  [rbp+57h+var_60], xmm0
0x14000baa5  movups  xmm0, xmmword ptr cs:a648392519daf4e+3Ah; "86ffbc1"
0x14000baac  mov     [rbp+57h+var_D0], 2
0x14000bab3  movaps  [rbp+57h+var_70], xmm1
0x14000bab7  movaps  xmm1, xmmword ptr cs:a648392519daf4e+30h; "9771c86ffbc1"
0x14000babe  movaps  xmmword ptr [rbp+57h+var_50], xmm1
0x14000bac2  movups  xmmword ptr [rbp+57h+var_50+0Ah], xmm0
0x14000bac6  inc     rax
0x14000bac9  cmp     [rcx+rax*2], r14w
0x14000bace  jnz     short loc_14000BAC6
0x14000bad0  mov     rcx, [rbx]; hService
0x14000bad3  lea     eax, ds:2[rax*2]
0x14000bada  mov     [rbp+57h+var_CC], eax
0x14000badd  lea     r8, [rbp+57h+Info]; lpInfo
0x14000bae1  lea     rax, [rbp+57h+var_80]
0x14000bae5  mov     [rbp+57h+var_C0], 6
0x14000baec  mov     [rbp+57h+var_C8], rax
0x14000baf0  mov     edx, 8; dwInfoLevel
0x14000baf5  lea     rax, RPC_INTERFACE_EVENT_GUID
0x14000bafc  mov     [rbp+57h+var_BC], 1
0x14000bb03  mov     [rbp+57h+var_B8], rax
0x14000bb07  lea     rax, [rbp+57h+var_D0]
0x14000bb0b  mov     [rbp+57h+var_A8], rax
0x14000bb0f  lea     rax, [rbp+57h+var_C0]
0x14000bb13  mov     [rbp+57h+var_98], rax
0x14000bb17  mov     [rbp+57h+var_B0], 1
0x14000bb1f  mov     [rbp+57h+Info], 1
0x14000bb27  mov     [rbp+57h+var_90], r14
0x14000bb2b  call    cs:__imp_ChangeServiceConfig2W
0x14000bb31  test    eax, eax
0x14000bb33  jnz     short loc_14000BB96
0x14000bb35  mov     rcx, [rbp+5Fh]; this
0x14000bb39  lea     r9, aChangingServic; "Changing service trigger to RPC call fa"...
0x14000bb40  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000bb47  mov     edx, 0A7h; void *
0x14000bb4c  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000bb51  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bb56  mov     rcx, [rax+8]
0x14000bb5a  mov     eax, [rcx]
0x14000bb5c  cmp     eax, 2
0x14000bb5f  jbe     short loc_14000BB92
0x14000bb61  lea     rax, aChangingServic_0; "Changing service trigger to RPC call fa"...
0x14000bb68  mov     [rsp+110h+var_D8], rdi
0x14000bb6d  mov     qword ptr [rsp+110h+var_E0], rax
0x14000bb72  lea     rdx, word_140086F2E
0x14000bb79  lea     rax, [rsp+110h+var_E0]
0x14000bb7e  mov     [rsp+110h+var_E8], rax
0x14000bb83  lea     rax, [rsp+110h+var_D8]
0x14000bb88  mov     [rsp+110h+var_F0], rax
0x14000bb8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000bb92  xor     eax, eax
0x14000bb94  jmp     short loc_14000BB9B
0x14000bb96  mov     eax, 1
0x14000bb9b  mov     rcx, [rbp+57h+var_30]
0x14000bb9f  xor     rcx, rsp; StackCookie
0x14000bba2  call    __security_check_cookie
0x14000bba7  add     rsp, 0F8h
0x14000bbae  pop     r14
0x14000bbb0  pop     rdi
0x14000bbb1  pop     rbx
0x14000bbb2  pop     rbp
0x14000bbb3  retn
```
