# _lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5_::operator()

- ea: `0x18002cb84`
- end: `0x18002ce7e`
- name: `_lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5_::operator()`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002c15c`

## callees

- `0x1800034a0`
- `0x180010cac`
- `0x1800110fc`
- `0x180011194`
- `0x18002cb84`
- `0x18002f2a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cc27`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cc27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc05`
- `deviceassociation!DafCloseAssociationContext` at `0x18002cbfd`
- `deviceassociation!DafCloseAssociationContext` at `0x18002ccd8`
- `deviceassociation!DafCloseAssociationContext` at `0x18002cbfd`
- `deviceassociation!DafCloseAssociationContext` at `0x18002ccd8`
- `deviceassociation!DafStartRemoveAssociation` at `0x18002cc43`
- `deviceassociation!DafStartRemoveAssociation` at `0x18002cc43`
- `deviceassociation!DafCreateAssociationContext` at `0x18002cbd1`
- `deviceassociation!DafCreateAssociationContext` at `0x18002cbd1`

## string_xrefs

- `0x18002cd60`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002cde6`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002ce6c`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_UNKNOWN **__fastcall lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5_::operator()(unsigned int **a1)
{
  char v2; // di
  _DWORD *v3; // rbx
  __int64 v4; // r8
  __int64 v5; // rdx
  _DWORD *v6; // rbx
  __int64 v7; // r8
  _DWORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  _UNKNOWN **result; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-88h]
  int v17; // [rsp+28h] [rbp-80h]
  __int64 v18; // [rsp+58h] [rbp-50h] BYREF
  char v19; // [rsp+60h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  __int64 v21; // [rsp+B0h] [rbp+8h]

  v21 = 0;
  v18 = 0;
  v2 = 1;
  v19 = 1;
  v3 = *a1;
  *v3 = DafCreateAssociationContext(*(_QWORD *)a1[1], 0, 0, 0, &v18);
  if ( v19 )
    v21 = v18;
  v5 = **a1;
  if ( (int)v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v2 = 0;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = v2;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        59,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v14 = wil::verify_hresult<long>(**a1, v5, v4);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x247,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v14,
      v16);
  }
  ResetEvent(*((HANDLE *)a1[2] + 256));
  v6 = *a1;
  *v6 = DafStartRemoveAssociation(
          v21,
          Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_RemoveAssociationCallback,
          a1[2]);
  v9 = **a1;
  if ( (int)v9 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v2 = 0;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v2;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        v7,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        60,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v15 = wil::verify_hresult<long>(**a1, v9, v7);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v15,
      v16);
  }
  v8 = *a1;
  *v8 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)a1[2]);
  v11 = **a1;
  if ( (int)v11 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v2 = 0;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = v2;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        61,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v13 = wil::verify_hresult<long>(**a1, v11, v10);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v13,
      v16);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v2 = 0;
  result = &WPP_RECORDER_INITIALIZED;
  LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    result = (_UNKNOWN **)WPP_RECORDER_AND_TRACE_SF_s(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v2,
                            v10,
                            *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( v21 )
    return (_UNKNOWN **)DafCloseAssociationContext(v21, v11, v10);
  return result;
}

```

## disassembly

```asm
0x18002cb84  mov     r11, rsp
0x18002cb87  push    rbx
0x18002cb88  push    rbp
0x18002cb89  push    rsi
0x18002cb8a  push    rdi
0x18002cb8b  push    r14
0x18002cb8d  push    r15
0x18002cb8f  sub     rsp, 78h
0x18002cb93  mov     rsi, rcx
0x18002cb96  mov     qword ptr [r11+8], 0
0x18002cb9e  lea     rax, [r11+8]
0x18002cba2  mov     [r11-58h], rax
0x18002cba6  mov     qword ptr [r11-50h], 0
0x18002cbae  mov     dil, 1
0x18002cbb1  mov     [rsp+0A8h+var_48], dil
0x18002cbb6  mov     rbx, [rcx]
0x18002cbb9  mov     rcx, [rcx+8]
0x18002cbbd  lea     rax, [r11-50h]
0x18002cbc1  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18002cbc6  xor     r9d, r9d
0x18002cbc9  xor     r8d, r8d
0x18002cbcc  xor     edx, edx
0x18002cbce  mov     rcx, [rcx]
0x18002cbd1  call    cs:__imp_DafCreateAssociationContext
0x18002cbd7  mov     [rbx], eax
0x18002cbd9  cmp     [rsp+0A8h+var_48], 0
0x18002cbde  jz      short loc_18002CC0F
0x18002cbe0  mov     r15, [rsp+0A8h+var_50]
0x18002cbe5  mov     r14, [rsp+0A8h+var_58]
0x18002cbea  mov     rbp, [r14]
0x18002cbed  test    rbp, rbp
0x18002cbf0  jz      short loc_18002CC0C
0x18002cbf2  call    cs:__imp_GetLastError
0x18002cbf8  mov     ebx, eax
0x18002cbfa  mov     rcx, rbp
0x18002cbfd  call    cs:__imp_DafCloseAssociationContext
0x18002cc03  mov     ecx, ebx; dwErrCode
0x18002cc05  call    cs:__imp_SetLastError
0x18002cc0b  nop
0x18002cc0c  mov     [r14], r15
0x18002cc0f  mov     rax, [rsi]
0x18002cc12  mov     edx, [rax]
0x18002cc14  test    edx, edx
0x18002cc16  js      loc_18002CD72
0x18002cc1c  mov     rcx, [rsi+10h]
0x18002cc20  mov     rcx, [rcx+800h]; hEvent
0x18002cc27  call    cs:__imp_ResetEvent
0x18002cc2d  mov     rbx, [rsi]
0x18002cc30  mov     r8, [rsi+10h]
0x18002cc34  lea     rdx, ?s_RemoveAssociationCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAXJ@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_RemoveAssociationCallback(void *,long)
0x18002cc3b  mov     rcx, [rsp+0A8h+arg_0]
0x18002cc43  call    cs:__imp_DafStartRemoveAssociation
0x18002cc49  mov     [rbx], eax
0x18002cc4b  mov     rax, [rsi]
0x18002cc4e  mov     edx, [rax]
0x18002cc50  test    edx, edx
0x18002cc52  js      loc_18002CDF8
0x18002cc58  mov     rbx, rax
0x18002cc5b  mov     rcx, [rsi+10h]; this
0x18002cc5f  call    ?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)
0x18002cc64  mov     [rbx], eax
0x18002cc66  mov     rax, [rsi]
0x18002cc69  mov     edx, [rax]
0x18002cc6b  test    edx, edx
0x18002cc6d  js      short loc_18002CCEC
0x18002cc6f  lea     rax, WPP_GLOBAL_Control
0x18002cc76  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc7d  cmp     rcx, rax
0x18002cc80  jz      short loc_18002CC88
0x18002cc82  cmp     byte ptr [rcx+19h], 4
0x18002cc86  jnb     short loc_18002CC8B
0x18002cc88  xor     dil, dil
0x18002cc8b  lea     rax, WPP_RECORDER_INITIALIZED
0x18002cc92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002cc99  setnz   r8b
0x18002cc9d  test    dil, dil
0x18002cca0  jnz     short loc_18002CCA7
0x18002cca2  test    r8b, r8b
0x18002cca5  jz      short loc_18002CCCB
0x18002cca7  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ccae  mov     [rsp+0A8h+var_70], rax
0x18002ccb3  mov     [rsp+0A8h+var_78], 3Eh ; '>'
0x18002ccba  mov     r9, [rcx+28h]
0x18002ccbe  mov     dl, dil
0x18002ccc1  mov     rcx, [rcx+10h]
0x18002ccc5  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002ccca  nop
0x18002cccb  mov     rcx, [rsp+0A8h+arg_0]
0x18002ccd3  test    rcx, rcx
0x18002ccd6  jz      short loc_18002CCDF
0x18002ccd8  call    cs:__imp_DafCloseAssociationContext
0x18002ccde  nop
0x18002ccdf  add     rsp, 78h
0x18002cce3  pop     r15
0x18002cce5  pop     r14
0x18002cce7  pop     rdi
0x18002cce8  pop     rsi
0x18002cce9  pop     rbp
0x18002ccea  pop     rbx
0x18002cceb  retn
0x18002ccec  lea     rax, WPP_GLOBAL_Control
0x18002ccf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccfa  cmp     rcx, rax
0x18002ccfd  jz      short loc_18002CD05
0x18002ccff  cmp     byte ptr [rcx+19h], 2
0x18002cd03  jnb     short loc_18002CD08
0x18002cd05  xor     dil, dil
0x18002cd08  lea     rax, WPP_RECORDER_INITIALIZED
0x18002cd0f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002cd16  setnz   r8b
0x18002cd1a  test    dil, dil
0x18002cd1d  jnz     short loc_18002CD24
0x18002cd1f  test    r8b, r8b
0x18002cd22  jz      short loc_18002CD4B
0x18002cd24  mov     [rsp+0A8h+var_60], edx
0x18002cd28  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002cd2f  mov     [rsp+0A8h+var_70], rax
0x18002cd34  mov     [rsp+0A8h+var_78], 3Dh ; '='
0x18002cd3b  mov     r9, [rcx+28h]
0x18002cd3f  mov     dl, dil
0x18002cd42  mov     rcx, [rcx+10h]
0x18002cd46  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002cd4b  mov     rcx, [rsi]
0x18002cd4e  mov     ecx, [rcx]
0x18002cd50  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002cd55  mov     r9d, eax; char *
0x18002cd58  mov     rcx, [rsp+0A8h]; this
0x18002cd60  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002cd67  mov     edx, 257h; void *
0x18002cd6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cd72  lea     rax, WPP_GLOBAL_Control
0x18002cd79  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd80  cmp     rcx, rax
0x18002cd83  jz      short loc_18002CD8B
0x18002cd85  cmp     byte ptr [rcx+19h], 2
0x18002cd89  jnb     short loc_18002CD8E
0x18002cd8b  xor     dil, dil
0x18002cd8e  lea     rax, WPP_RECORDER_INITIALIZED
0x18002cd95  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002cd9c  setnz   r8b
0x18002cda0  test    dil, dil
0x18002cda3  jnz     short loc_18002CDAA
0x18002cda5  test    r8b, r8b
0x18002cda8  jz      short loc_18002CDD1
0x18002cdaa  mov     [rsp+0A8h+var_60], edx
0x18002cdae  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002cdb5  mov     [rsp+0A8h+var_70], rax
0x18002cdba  mov     [rsp+0A8h+var_78], 3Bh ; ';'
0x18002cdc1  mov     r9, [rcx+28h]
0x18002cdc5  mov     dl, dil
0x18002cdc8  mov     rcx, [rcx+10h]
0x18002cdcc  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002cdd1  mov     rcx, [rsi]
0x18002cdd4  mov     ecx, [rcx]
0x18002cdd6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002cddb  mov     r9d, eax; char *
0x18002cdde  mov     rcx, [rsp+0A8h]; this
0x18002cde6  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002cded  mov     edx, 247h; void *
0x18002cdf2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cdf8  lea     rax, WPP_GLOBAL_Control
0x18002cdff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce06  cmp     rcx, rax
0x18002ce09  jz      short loc_18002CE11
0x18002ce0b  cmp     byte ptr [rcx+19h], 2
0x18002ce0f  jnb     short loc_18002CE14
0x18002ce11  xor     dil, dil
0x18002ce14  lea     rax, WPP_RECORDER_INITIALIZED
0x18002ce1b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002ce22  setnz   r8b
0x18002ce26  test    dil, dil
0x18002ce29  jnz     short loc_18002CE30
0x18002ce2b  test    r8b, r8b
0x18002ce2e  jz      short loc_18002CE57
0x18002ce30  mov     [rsp+0A8h+var_60], edx
0x18002ce34  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ce3b  mov     [rsp+0A8h+var_70], rax
0x18002ce40  mov     [rsp+0A8h+var_78], 3Ch ; '<'
0x18002ce47  mov     r9, [rcx+28h]
0x18002ce4b  mov     dl, dil
0x18002ce4e  mov     rcx, [rcx+10h]
0x18002ce52  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002ce57  mov     rcx, [rsi]
0x18002ce5a  mov     ecx, [rcx]
0x18002ce5c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002ce61  mov     r9d, eax; char *
0x18002ce64  mov     rcx, [rsp+0A8h]; this
0x18002ce6c  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002ce73  mov     edx, 250h; void *
0x18002ce78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
