# TimeUpdate::DoApplySettings(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &,std::shared_ptr<Settings> const &)

- ea: `0x1800061ac`
- end: `0x18000634a`
- name: `?DoApplySettings@TimeUpdate@@AEAAXAEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@AEBV?$shared_ptr@VSettings@@@std@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(TimeUpdate *this, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000891c`

## callees

- `0x180001010`
- `0x180001054`
- `0x1800012f0`
- `0x180002a70`
- `0x180005620`
- `0x1800061ac`
- `0x180007220`
- `0x1800098d4`
- `0x180009934`
- `0x18000ad28`
- `0x180010068`
- `0x180010800`

## pseudocode

```c
__int64 __fastcall TimeUpdate::DoApplySettings(TimeUpdate *this, _DWORD *a2, __int64 *a3)
{
  int started; // esi
  __int64 v6; // rcx
  int *v7; // r9
  __int64 v8; // rax
  char v9; // bl
  char v11; // [rsp+30h] [rbp-59h] BYREF
  char v12; // [rsp+31h] [rbp-58h] BYREF
  int v13; // [rsp+34h] [rbp-55h] BYREF
  int v14; // [rsp+38h] [rbp-51h] BYREF
  char v15; // [rsp+3Ch] [rbp-4Dh]
  _BYTE v16[16]; // [rsp+40h] [rbp-49h] BYREF
  int v17; // [rsp+50h] [rbp-39h] BYREF
  int v18; // [rsp+54h] [rbp-35h]
  int v19; // [rsp+58h] [rbp-31h]
  int v20; // [rsp+5Ch] [rbp-2Dh]
  char *v21; // [rsp+80h] [rbp-9h]
  __int64 v22; // [rsp+88h] [rbp-1h]
  char *v23; // [rsp+90h] [rbp+7h]
  __int64 v24; // [rsp+98h] [rbp+Fh]
  int *v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+A8h] [rbp+1Fh]

  v17 = a2[2];
  v18 = a2[3];
  started = 0;
  v19 = a2[4];
  v20 = a2[5];
  v14 = 0;
  v15 = 1;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(&v14);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    if ( v15 && (v17 || v18 || v19 || v20) )
      v7 = &v17;
    else
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&dword_1800166C4,
      (__int64)v16,
      (__int64)v7);
  }
  v8 = *a3;
  v9 = *(_BYTE *)(*a3 + 6);
  if ( *(_BYTE *)(v8 + 5) )
  {
    if ( v9 )
    {
      started = WpW32TimeSetServiceStartType(3u);
      if ( TimeUpdate::HasNetwork(this) )
        TimeUpdate::StartNtp(this);
    }
    else
    {
      LOBYTE(v6) = 1;
      started = WpW32TimeStopService(v6);
      TimeUpdate::StopNtp(this, 1);
    }
  }
  v14 = 2;
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    v13 = started;
    v25 = &v13;
    v11 = v9;
    v23 = &v11;
    v12 = v9;
    v21 = &v12;
    v26 = 4;
    v24 = 1;
    v22 = 1;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, byte_1800163CB, v16, 0);
  }
  return _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(&v14);
}

```

## disassembly

```asm
0x1800061ac  push    rbp
0x1800061ae  push    rbx
0x1800061af  push    rsi
0x1800061b0  push    rdi
0x1800061b1  lea     rbp, [rsp-3Fh]
0x1800061b6  sub     rsp, 0C8h
0x1800061bd  mov     rax, cs:__security_cookie
0x1800061c4  xor     rax, rsp
0x1800061c7  mov     [rbp+57h+var_30], rax
0x1800061cb  mov     eax, [rdx+8]
0x1800061ce  mov     rdi, rcx
0x1800061d1  mov     [rbp+57h+var_90], eax
0x1800061d4  lea     rcx, [rbp+57h+var_A8]
0x1800061d8  mov     eax, [rdx+0Ch]
0x1800061db  mov     rbx, r8
0x1800061de  mov     [rbp+57h+var_8C], eax
0x1800061e1  xor     esi, esi
0x1800061e3  mov     eax, [rdx+10h]
0x1800061e6  mov     [rbp+57h+var_88], eax
0x1800061e9  mov     eax, [rdx+14h]
0x1800061ec  mov     [rbp+57h+var_84], eax
0x1800061ef  mov     [rbp+57h+var_A8], 0
0x1800061f6  mov     [rbp+57h+var_A4], 1
0x1800061fa  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ
0x1800061ff  mov     eax, cs:dword_18001C010
0x180006205  cmp     eax, 4
0x180006208  jbe     short loc_180006259
0x18000620a  mov     edx, 300h
0x18000620f  lea     rcx, dword_18001C010
0x180006216  call    _tlgKeywordOn
0x18000621b  test    al, al
0x18000621d  jz      short loc_180006259
0x18000621f  cmp     [rbp+57h+var_A4], sil
0x180006223  jz      short loc_18000623F
0x180006225  cmp     [rbp+57h+var_90], esi
0x180006228  jnz     short loc_180006239
0x18000622a  cmp     [rbp+57h+var_8C], esi
0x18000622d  jnz     short loc_180006239
0x18000622f  cmp     [rbp+57h+var_88], esi
0x180006232  jnz     short loc_180006239
0x180006234  cmp     [rbp+57h+var_84], esi
0x180006237  jz      short loc_18000623F
0x180006239  lea     r9, [rbp+57h+var_90]
0x18000623d  jmp     short loc_180006242
0x18000623f  xor     r9d, r9d
0x180006242  lea     r8, [rbp+57h+var_A0]
0x180006246  lea     rdx, dword_1800166C4
0x18000624d  lea     rcx, dword_18001C010
0x180006254  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z
0x180006259  mov     rax, [rbx]
0x18000625c  mov     bl, [rax+6]
0x18000625f  cmp     [rax+5], sil
0x180006263  jz      short loc_18000629E
0x180006265  test    bl, bl
0x180006267  jz      short loc_18000628B
0x180006269  mov     ecx, 3; dwStartType
0x18000626e  call    ?WpW32TimeSetServiceStartType@@YAJK@Z
0x180006273  mov     rcx, rdi; this
0x180006276  mov     esi, eax
0x180006278  call    ?HasNetwork@TimeUpdate@@AEBA_NXZ
0x18000627d  test    al, al
0x18000627f  jz      short loc_18000629E
0x180006281  mov     rcx, rdi; this
0x180006284  call    ?StartNtp@TimeUpdate@@AEAAXXZ
0x180006289  jmp     short loc_18000629E
0x18000628b  mov     cl, 1
0x18000628d  call    WpW32TimeStopService
0x180006292  mov     dl, 1; bool
0x180006294  mov     rcx, rdi; this
0x180006297  mov     esi, eax
0x180006299  call    ?StopNtp@TimeUpdate@@AEAAX_N@Z
0x18000629e  mov     eax, cs:dword_18001C010
0x1800062a4  mov     [rbp+57h+var_A8], 2
0x1800062ab  cmp     eax, 4
0x1800062ae  jbe     short loc_180006329
0x1800062b0  mov     edx, 300h
0x1800062b5  lea     rcx, dword_18001C010
0x1800062bc  call    _tlgKeywordOn
0x1800062c1  test    al, al
0x1800062c3  jz      short loc_180006329
0x1800062c5  lea     rax, [rbp+57h+var_AC]
0x1800062c9  mov     [rbp+57h+var_AC], esi
0x1800062cc  mov     [rbp+57h+var_40], rax
0x1800062d0  lea     r8, [rbp+57h+var_A0]
0x1800062d4  lea     rax, [rbp+57h+var_B0]
0x1800062d8  mov     [rbp+57h+var_B0], bl
0x1800062db  mov     [rbp+57h+var_50], rax
0x1800062df  lea     rdx, byte_1800163CB
0x1800062e6  lea     rax, [rbp+57h+var_AF]
0x1800062ea  mov     [rbp+57h+var_AF], bl
0x1800062ed  mov     [rbp+57h+var_60], rax
0x1800062f1  lea     rcx, dword_18001C010
0x1800062f8  lea     rax, [rbp+57h+var_80]
0x1800062fc  mov     [rbp+57h+var_38], 4
0x180006304  mov     [rsp+0E0h+var_B8], rax
0x180006309  xor     r9d, r9d
0x18000630c  mov     [rsp+0E0h+var_C0], 5
0x180006314  mov     [rbp+57h+var_48], 1
0x18000631c  mov     [rbp+57h+var_58], 1
0x180006324  call    _tlgWriteTransfer_EventWriteTransfer
0x180006329  lea     rcx, [rbp+57h+var_A8]
0x18000632d  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ
0x180006332  mov     rcx, [rbp+57h+var_30]
0x180006336  xor     rcx, rsp; StackCookie
0x180006339  call    __security_check_cookie
0x18000633e  add     rsp, 0C8h
0x180006345  pop     rdi
0x180006346  pop     rsi
0x180006347  pop     rbx
0x180006348  pop     rbp
0x180006349  retn
```
