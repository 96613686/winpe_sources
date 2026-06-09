# CServiceModule::Start(void)

- ea: `0x180026c8c`
- end: `0x180026e78`
- name: `?Start@CServiceModule@@QEAAHXZ`
- size: `492`
- prototype: `__int64 __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180025ae0`

## callees

- `0x180001ec0`
- `0x180012dc0`
- `0x180015630`
- `0x180026c8c`
- `0x18002b3a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026cdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026d22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026d62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026d9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026cdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026d22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026d62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026d9c`

## string_xrefs

- `0x180026ca8`: `PENSERVICE_CServiceModule::Start`

## pseudocode

```c
_BOOL8 __fastcall CServiceModule::Start(CServiceModule *this)
{
  int v1; // ebx
  struct _GUID *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  CServiceModule *v8; // [rsp+60h] [rbp+8h] BYREF

  v8 = this;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      78,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Start");
  qword_180041290 = CreateEventW(0, 0, 0, 0);
  if ( !qword_180041290 )
  {
    v1 = -2147467259;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
      goto LABEL_21;
    v3 = 79;
LABEL_20:
    WPP_SF_s(
      *(_QWORD *)&v2[1].Data1,
      v3,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Start");
LABEL_21:
    SH<void *,SH_HANDLE>::Reset(&qword_180041290);
    SH<void *,SH_HANDLE>::Reset(&hEvent);
    SH<void *,SH_HANDLE>::Reset(&qword_1800412C0);
    SH<void *,SH_HANDLE>::Reset(&qword_1800412B0);
    goto LABEL_22;
  }
  qword_1800412B0 = CreateEventW(0, 0, 0, 0);
  if ( !qword_1800412B0 )
  {
    v1 = -2147467259;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
      goto LABEL_21;
    v3 = 80;
    goto LABEL_20;
  }
  qword_1800412C0 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_1800412C0 )
  {
    v1 = -2147467259;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
      goto LABEL_21;
    v3 = 81;
    goto LABEL_20;
  }
  v1 = 0;
  hEvent = CreateEventW(0, 0, 0, 0);
  if ( !hEvent )
  {
    v1 = -2147467259;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
      goto LABEL_21;
    v3 = 82;
    goto LABEL_20;
  }
LABEL_22:
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    LODWORD(v8) = v1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (int)&dword_18003A064,
      v5,
      v6,
      (__int64)&v8);
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      83,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::Start");
  return v1 == 0;
}

```

## disassembly

```asm
0x180026c8c  mov     [rsp+arg_0], rcx
0x180026c91  push    rbx
0x180026c92  push    rbp
0x180026c93  push    rsi
0x180026c94  push    r14
0x180026c96  sub     rsp, 38h
0x180026c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ca1  lea     rsi, WPP_GLOBAL_Control
0x180026ca8  lea     rbp, aPenserviceCser_4; "PENSERVICE_CServiceModule::Start"
0x180026caf  lea     r14, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180026cb6  cmp     rcx, rsi
0x180026cb9  jz      short loc_180026CD5
0x180026cbb  test    byte ptr [rcx+1Ch], 10h
0x180026cbf  jz      short loc_180026CD5
0x180026cc1  mov     rcx, [rcx+10h]
0x180026cc5  mov     edx, 4Eh ; 'N'
0x180026cca  mov     r9, rbp
0x180026ccd  mov     r8, r14
0x180026cd0  call    WPP_SF_s
0x180026cd5  xor     r9d, r9d; lpName
0x180026cd8  xor     r8d, r8d; bInitialState
0x180026cdb  xor     edx, edx; bManualReset
0x180026cdd  xor     ecx, ecx; lpEventAttributes
0x180026cdf  call    cs:__imp_CreateEventW
0x180026ce5  mov     cs:qword_180041290, rax
0x180026cec  test    rax, rax
0x180026cef  jnz     short loc_180026D18
0x180026cf1  mov     ebx, 80004005h
0x180026cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cfd  cmp     rcx, rsi
0x180026d00  jz      loc_180026DD7
0x180026d06  test    byte ptr [rcx+1Ch], 10h
0x180026d0a  jz      loc_180026DD7
0x180026d10  lea     edx, [rax+4Fh]
0x180026d13  jmp     loc_180026DC8
0x180026d18  xor     r9d, r9d; lpName
0x180026d1b  xor     r8d, r8d; bInitialState
0x180026d1e  xor     edx, edx; bManualReset
0x180026d20  xor     ecx, ecx; lpEventAttributes
0x180026d22  call    cs:__imp_CreateEventW
0x180026d28  mov     cs:qword_1800412B0, rax
0x180026d2f  test    rax, rax
0x180026d32  jnz     short loc_180026D58
0x180026d34  mov     ebx, 80004005h
0x180026d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d40  cmp     rcx, rsi
0x180026d43  jz      loc_180026DD7
0x180026d49  test    byte ptr [rcx+1Ch], 10h
0x180026d4d  jz      loc_180026DD7
0x180026d53  lea     edx, [rax+50h]
0x180026d56  jmp     short loc_180026DC8
0x180026d58  xor     r9d, r9d; lpName
0x180026d5b  xor     r8d, r8d; bInitialState
0x180026d5e  xor     edx, edx; bManualReset
0x180026d60  xor     ecx, ecx; lpEventAttributes
0x180026d62  call    cs:__imp_CreateEventW
0x180026d68  mov     cs:qword_1800412C0, rax
0x180026d6f  test    rax, rax
0x180026d72  jnz     short loc_180026D90
0x180026d74  mov     ebx, 80004005h
0x180026d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d80  cmp     rcx, rsi
0x180026d83  jz      short loc_180026DD7
0x180026d85  test    byte ptr [rcx+1Ch], 10h
0x180026d89  jz      short loc_180026DD7
0x180026d8b  lea     edx, [rax+51h]
0x180026d8e  jmp     short loc_180026DC8
0x180026d90  xor     r9d, r9d; lpName
0x180026d93  xor     r8d, r8d; bInitialState
0x180026d96  xor     edx, edx; bManualReset
0x180026d98  xor     ecx, ecx; lpEventAttributes
0x180026d9a  xor     ebx, ebx
0x180026d9c  call    cs:__imp_CreateEventW
0x180026da2  mov     cs:hEvent, rax
0x180026da9  test    rax, rax
0x180026dac  jnz     short loc_180026E07
0x180026dae  mov     ebx, 80004005h
0x180026db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dba  cmp     rcx, rsi
0x180026dbd  jz      short loc_180026DD7
0x180026dbf  test    byte ptr [rcx+1Ch], 10h
0x180026dc3  jz      short loc_180026DD7
0x180026dc5  lea     edx, [rax+52h]
0x180026dc8  mov     rcx, [rcx+10h]
0x180026dcc  mov     r9, rbp
0x180026dcf  mov     r8, r14
0x180026dd2  call    WPP_SF_s
0x180026dd7  lea     rcx, qword_180041290
0x180026dde  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180026de3  lea     rcx, hEvent
0x180026dea  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180026def  lea     rcx, qword_1800412C0
0x180026df6  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180026dfb  lea     rcx, qword_1800412B0
0x180026e02  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180026e07  mov     eax, cs:dword_1800411A8
0x180026e0d  cmp     eax, 5
0x180026e10  jbe     short loc_180026E41
0x180026e12  mov     edx, 4000000h
0x180026e17  lea     rcx, dword_1800411A8
0x180026e1e  call    _tlgKeywordOn
0x180026e23  test    al, al
0x180026e25  jz      short loc_180026E41
0x180026e27  lea     rax, [rsp+58h+arg_0]
0x180026e2c  mov     dword ptr [rsp+58h+arg_0], ebx
0x180026e30  lea     rdx, dword_18003A064
0x180026e37  mov     [rsp+58h+var_38], rax
0x180026e3c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180026e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e48  cmp     rcx, rsi
0x180026e4b  jz      short loc_180026E67
0x180026e4d  test    byte ptr [rcx+1Ch], 10h
0x180026e51  jz      short loc_180026E67
0x180026e53  mov     rcx, [rcx+10h]
0x180026e57  mov     edx, 53h ; 'S'
0x180026e5c  mov     r9, rbp
0x180026e5f  mov     r8, r14
0x180026e62  call    WPP_SF_s
0x180026e67  xor     eax, eax
0x180026e69  test    ebx, ebx
0x180026e6b  setz    al
0x180026e6e  add     rsp, 38h
0x180026e72  pop     r14
0x180026e74  pop     rsi
0x180026e75  pop     rbp
0x180026e76  pop     rbx
0x180026e77  retn
```
