# ProtectedSystemState::RefreshSysUIEnabled(void)

- ea: `0x18002378c`
- end: `0x180023a5e`
- name: `?RefreshSysUIEnabled@ProtectedSystemState@@AEAAXXZ`
- size: `722`
- prototype: `void __fastcall(ProtectedSystemState *__hidden this)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x18001f530`
- `0x180020d50`
- `0x180023270`
- `0x1800232b8`
- `0x18002336c`
- `0x1800233a4`
- `0x180023a64`
- `0x180023ab0`
- `0x180023af0`

## callees

- `0x1800020fc`
- `0x18000219c`
- `0x180002ec0`
- `0x180003d50`
- `0x180009350`
- `0x18000d2a0`
- `0x18002378c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x1800239c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x1800239c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800238ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800238ad`

## pseudocode

```c
void __fastcall ProtectedSystemState::RefreshSysUIEnabled(ProtectedSystemState *this)
{
  char v2; // si
  __int64 v3; // r9
  __int64 v4; // rcx
  ULONGLONG TickCount64; // r14
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  struct _TP_TIMER *v9; // rcx
  struct _FILETIME *v10; // rdx
  int v11; // ecx
  __int64 v12; // r8
  int v13; // r9d
  int v14; // ecx
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+40h] [rbp-38h] BYREF
  ULONGLONG v18; // [rsp+48h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 11) == 2 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids);
    v2 = 0;
    *((_DWORD *)this + 18) = 0;
  }
  else
  {
    v3 = *((unsigned int *)this + 10);
    if ( !(_DWORD)v3 || *((_BYTE *)this + 105) )
    {
      if ( *((_DWORD *)this + 15) || !*((_BYTE *)this + 48) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids);
        v2 = 1;
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids);
        v2 = 0;
        *((_DWORD *)this + 18) = 2;
      }
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids, v3);
      v2 = 0;
      *((_DWORD *)this + 18) = 1;
    }
  }
  TickCount64 = GetTickCount64();
  if ( *((_BYTE *)this + 49) == v2 )
  {
    if ( *((_BYTE *)this + 104) )
    {
      if ( (unsigned int)dword_180037050 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
      {
        v17 = *((_DWORD *)this + 18);
        v18 = TickCount64 - v15;
        v19 = (__int64)this + 76;
        v20 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)&byte_1800301A7,
          v15,
          v16,
          (__int64)&v20,
          (__int64)&v18,
          (__int64)&v19,
          (__int64)&v17);
      }
      *((_BYTE *)this + 104) = 0;
    }
  }
  else if ( v2 )
  {
    if ( (unsigned int)dword_180037050 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
    {
      v17 = *((_DWORD *)this + 18);
      v18 = TickCount64 - v12;
      v20 = (__int64)this + 76;
      v19 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&byte_18003020F,
        v12,
        v13,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&v17);
    }
    v9 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 8) = 0;
    if ( v9 )
    {
      v10 = 0;
      goto LABEL_34;
    }
  }
  else
  {
    if ( (unsigned int)dword_180037050 > 5
      && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180037050, 0x400000000000LL) )
    {
      v17 = *((_DWORD *)this + 18);
      v20 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)word_18003026A,
        v7,
        v8,
        (__int64)&v20,
        (__int64)&v17);
    }
    v9 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 8) = TickCount64;
    if ( v9 )
    {
      v20 = -300000000;
      v10 = (struct _FILETIME *)&v20;
LABEL_34:
      SetThreadpoolTimerEx(v9, v10, 0, 0);
    }
  }
  *((_BYTE *)this + 49) = v2;
}

```

## disassembly

```asm
0x18002378c  push    rbp
0x18002378e  push    rbx
0x18002378f  push    rsi
0x180023790  push    r14
0x180023792  mov     rbp, rsp
0x180023795  sub     rsp, 78h
0x180023799  mov     rax, cs:__security_cookie
0x1800237a0  xor     rax, rsp
0x1800237a3  mov     [rbp+var_18], rax
0x1800237a7  cmp     dword ptr [rcx+2Ch], 2
0x1800237ab  mov     rbx, rcx
0x1800237ae  jnz     short loc_1800237ED
0x1800237b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237b7  lea     rax, WPP_GLOBAL_Control
0x1800237be  cmp     rcx, rax
0x1800237c1  jz      short loc_1800237DE
0x1800237c3  test    byte ptr [rcx+1Ch], 4
0x1800237c7  jz      short loc_1800237DE
0x1800237c9  mov     rcx, [rcx+10h]
0x1800237cd  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x1800237d4  mov     edx, 13h
0x1800237d9  call    WPP_SF_
0x1800237de  xor     sil, sil
0x1800237e1  mov     dword ptr [rbx+48h], 0
0x1800237e8  jmp     loc_1800238AD
0x1800237ed  mov     r9d, [rcx+28h]
0x1800237f1  test    r9d, r9d
0x1800237f4  jz      short loc_180023836
0x1800237f6  cmp     byte ptr [rcx+69h], 0
0x1800237fa  jnz     short loc_180023836
0x1800237fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023803  lea     rax, WPP_GLOBAL_Control
0x18002380a  cmp     rcx, rax
0x18002380d  jz      short loc_18002382A
0x18002380f  test    byte ptr [rcx+1Ch], 4
0x180023813  jz      short loc_18002382A
0x180023815  mov     rcx, [rcx+10h]
0x180023819  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x180023820  mov     edx, 14h
0x180023825  call    WPP_SF_d
0x18002382a  xor     sil, sil
0x18002382d  mov     dword ptr [rbx+48h], 1
0x180023834  jmp     short loc_1800238AD
0x180023836  cmp     dword ptr [rcx+3Ch], 0
0x18002383a  jnz     short loc_18002387C
0x18002383c  cmp     byte ptr [rcx+30h], 0
0x180023840  jz      short loc_18002387C
0x180023842  mov     rcx, cs:WPP_GLOBAL_Control
0x180023849  lea     rax, WPP_GLOBAL_Control
0x180023850  cmp     rcx, rax
0x180023853  jz      short loc_180023870
0x180023855  test    byte ptr [rcx+1Ch], 4
0x180023859  jz      short loc_180023870
0x18002385b  mov     rcx, [rcx+10h]
0x18002385f  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x180023866  mov     edx, 15h
0x18002386b  call    WPP_SF_
0x180023870  xor     sil, sil
0x180023873  mov     dword ptr [rbx+48h], 2
0x18002387a  jmp     short loc_1800238AD
0x18002387c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023883  lea     rax, WPP_GLOBAL_Control
0x18002388a  cmp     rcx, rax
0x18002388d  jz      short loc_1800238AA
0x18002388f  test    byte ptr [rcx+1Ch], 4
0x180023893  jz      short loc_1800238AA
0x180023895  mov     rcx, [rcx+10h]
0x180023899  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x1800238a0  mov     edx, 16h
0x1800238a5  call    WPP_SF_
0x1800238aa  mov     sil, 1
0x1800238ad  call    cs:__imp_GetTickCount64
0x1800238b3  mov     r14, rax
0x1800238b6  cmp     [rbx+31h], sil
0x1800238ba  jz      loc_1800239CB
0x1800238c0  test    sil, sil
0x1800238c3  jnz     short loc_180023937
0x1800238c5  mov     ecx, cs:dword_180037050
0x1800238cb  cmp     ecx, 5
0x1800238ce  jbe     short loc_18002390F
0x1800238d0  mov     rdx, 400000000000h
0x1800238da  call    _tlgKeywordOn
0x1800238df  test    al, al
0x1800238e1  jz      short loc_18002390F
0x1800238e3  mov     eax, [rbx+48h]
0x1800238e6  lea     rdx, word_18003026A
0x1800238ed  mov     [rbp+var_38], eax
0x1800238f0  lea     rax, [rbp+var_38]
0x1800238f4  mov     [rsp+78h+var_50], rax
0x1800238f9  lea     rax, [rbp+var_20]
0x1800238fd  mov     [rsp+78h+var_58], rax
0x180023902  mov     [rbp+var_20], 800h
0x18002390a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002390f  mov     rcx, [rbx+60h]
0x180023913  mov     [rbx+40h], r14
0x180023917  test    rcx, rcx
0x18002391a  jz      loc_180023A44
0x180023920  xor     r9d, r9d
0x180023923  mov     [rbp+var_20], 0FFFFFFFFEE1E5D00h
0x18002392b  xor     r8d, r8d
0x18002392e  lea     rdx, [rbp+var_20]
0x180023932  jmp     loc_1800239C3
0x180023937  mov     eax, cs:dword_180037050
0x18002393d  mov     r8, [rbx+40h]
0x180023941  cmp     eax, 5
0x180023944  jbe     short loc_1800239A6
0x180023946  mov     rdx, 400000000000h
0x180023950  call    _tlgKeywordOn
0x180023955  test    al, al
0x180023957  jz      short loc_1800239A6
0x180023959  mov     eax, [rbx+48h]
0x18002395c  lea     rdx, byte_18003020F
0x180023963  mov     [rbp+var_38], eax
0x180023966  sub     r14, r8
0x180023969  lea     rax, [rbx+4Ch]
0x18002396d  mov     [rbp+var_30], r14
0x180023971  mov     [rbp+var_20], rax
0x180023975  lea     rax, [rbp+var_38]
0x180023979  mov     [rsp+78h+var_40], rax
0x18002397e  lea     rax, [rbp+var_20]
0x180023982  mov     [rsp+78h+var_48], rax
0x180023987  lea     rax, [rbp+var_30]
0x18002398b  mov     [rsp+78h+var_50], rax
0x180023990  lea     rax, [rbp+var_28]
0x180023994  mov     [rsp+78h+var_58], rax
0x180023999  mov     [rbp+var_28], 800h
0x1800239a1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800239a6  mov     rcx, [rbx+60h]; pti
0x1800239aa  mov     qword ptr [rbx+40h], 0
0x1800239b2  test    rcx, rcx
0x1800239b5  jz      loc_180023A44
0x1800239bb  xor     r9d, r9d; msWindowLength
0x1800239be  xor     r8d, r8d; msPeriod
0x1800239c1  xor     edx, edx; pftDueTime
0x1800239c3  call    cs:__imp_SetThreadpoolTimerEx
0x1800239c9  jmp     short loc_180023A44
0x1800239cb  cmp     byte ptr [rbx+68h], 0
0x1800239cf  jz      short loc_180023A44
0x1800239d1  mov     eax, cs:dword_180037050
0x1800239d7  mov     r8, [rbx+40h]
0x1800239db  cmp     eax, 5
0x1800239de  jbe     short loc_180023A40
0x1800239e0  mov     rdx, 400000000000h
0x1800239ea  call    _tlgKeywordOn
0x1800239ef  test    al, al
0x1800239f1  jz      short loc_180023A40
0x1800239f3  mov     eax, [rbx+48h]
0x1800239f6  lea     rdx, byte_1800301A7
0x1800239fd  mov     [rbp+var_38], eax
0x180023a00  sub     r14, r8
0x180023a03  lea     rax, [rbx+4Ch]
0x180023a07  mov     [rbp+var_30], r14
0x180023a0b  mov     [rbp+var_28], rax
0x180023a0f  lea     rax, [rbp+var_38]
0x180023a13  mov     [rsp+78h+var_40], rax
0x180023a18  lea     rax, [rbp+var_28]
0x180023a1c  mov     [rsp+78h+var_48], rax
0x180023a21  lea     rax, [rbp+var_30]
0x180023a25  mov     [rsp+78h+var_50], rax
0x180023a2a  lea     rax, [rbp+var_20]
0x180023a2e  mov     [rsp+78h+var_58], rax
0x180023a33  mov     [rbp+var_20], 800h
0x180023a3b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180023a40  mov     byte ptr [rbx+68h], 0
0x180023a44  mov     [rbx+31h], sil
0x180023a48  mov     rcx, [rbp+var_18]
0x180023a4c  xor     rcx, rsp; StackCookie
0x180023a4f  call    __security_check_cookie
0x180023a54  add     rsp, 78h
0x180023a58  pop     r14
0x180023a5a  pop     rsi
0x180023a5b  pop     rbx
0x180023a5c  pop     rbp
0x180023a5d  retn
```
