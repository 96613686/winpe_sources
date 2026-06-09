# Broker::BrokerEvent::Signal(uchar const *,_GUID const *,uchar const *,ulong,_GUID const *)

- ea: `0x180005724`
- end: `0x1800058d7`
- name: `?Signal@BrokerEvent@Broker@@QEAAXPEBEPEBU_GUID@@0K1@Z`
- size: `435`
- prototype: `void(Broker::BrokerEvent *__hidden this, const unsigned __int8 *, const struct _GUID *, const unsigned __int8 *, unsigned int, const struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005580`
- `0x180018ec0`

## callees

- `0x180005724`
- `0x18000f888`
- `0x18001184c`
- `0x1800126e0`
- `0x1800142ac`
- `0x180014398`
- `0x1800165da`
- `0x18001a898`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180005877`
- `ntdll!RtlNtStatusToDosError` at `0x180005877`

## pseudocode

```c
void __fastcall Broker::BrokerEvent::Signal(
        Broker::BrokerEvent *this,
        const unsigned __int8 *a2,
        struct _GUID *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        const struct _GUID *a6)
{
  unsigned __int64 v7; // r15
  enum _BI_ACTIVATION_STATUS *v8; // rsi
  __int64 v10; // rcx
  __int64 v11; // r10
  __int64 v12; // rcx
  const struct _GUID *v13; // rdx
  Broker::BILayer *v14; // rcx
  int v15; // r9d
  char v16; // al
  NTSTATUS v17; // eax
  ULONG v18; // eax
  struct _GUID *v19; // [rsp+28h] [rbp-58h]
  struct _GUID *v20; // [rsp+30h] [rbp-50h]
  struct _GUID *v21; // [rsp+38h] [rbp-48h]
  struct _GUID v22; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-28h] BYREF

  v7 = (unsigned __int64)a4;
  *(_DWORD *)&v22.Data4[4] = 0;
  v8 = (enum _BI_ACTIVATION_STATUS *)a3;
  if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(this, 4, a3, a4) )
  {
    v22.Data1 = *((_DWORD *)this + 7);
    v23 = *((_QWORD *)this + 2);
    *(_DWORD *)v22.Data4 = a5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v10,
      byte_1800222AF,
      (__int64)a3,
      (__int64)a4,
      &v23,
      (__int64)&v22,
      (__int64)v22.Data4);
  }
  if ( a5 && !v7 )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, 0x57u);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  v11 = *((_QWORD *)this + 2);
  v12 = *(_QWORD *)(v11 + 16);
  v13 = (const struct _GUID *)(v7 & -(__int64)(a5 != 0));
  if ( v12 )
  {
    v15 = *(_DWORD *)(v11 + 40);
    v16 = 1;
    if ( (v15 & 1) != 0 )
    {
      if ( !a2 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, 0x57u);
        throw (Broker::Win32Error *)pExceptionObject;
      }
    }
    else
    {
      v16 = 0;
    }
    LOBYTE(a3) = 0;
    if ( a2 )
      LOBYTE(a3) = *a2;
    if ( (v15 & 2) != 0 )
    {
      v22.Data1 = 60000;
      v21 = &v22;
    }
    else
    {
      v21 = 0;
    }
    LOBYTE(v13) = v16;
    v17 = EaSignalEventImpl(
            v12,
            (_DWORD)v13,
            (_DWORD)a3,
            (_DWORD)a6,
            (__int64)v8,
            v7 & -(__int64)(a5 != 0),
            a5,
            (__int64)v21);
    if ( v17 < 0 )
    {
      v18 = RtlNtStatusToDosError(v17);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, v18);
      throw (Broker::Win32Error *)pExceptionObject;
    }
  }
  else
  {
    v14 = (Broker::BILayer *)*((_QWORD *)this + 2);
    if ( a2 )
    {
      LOBYTE(a4) = *a2;
      Broker::BILayer::SignalEventConditional(v14, v13, (const void *)a5, (unsigned int)a4, (unsigned __int8)v8, v19);
    }
    else
    {
      Broker::BILayer::SignalEventEx(v14, v13, (const void *)a5, (unsigned int)&v22.Data4[4], v8, a6, v20);
    }
  }
}

```

## disassembly

```asm
0x180005724  push    rbp
0x180005726  push    rbx
0x180005727  push    rsi
0x180005728  push    rdi
0x180005729  push    r12
0x18000572b  push    r14
0x18000572d  push    r15
0x18000572f  mov     rbp, rsp
0x180005732  sub     rsp, 80h
0x180005739  mov     eax, cs:dword_180028000
0x18000573f  mov     rdi, rdx
0x180005742  mov     r12, [rbp+arg_28]
0x180005746  mov     edx, 4
0x18000574b  mov     ebx, dword ptr [rbp+arg_20]
0x18000574e  mov     r15, r9
0x180005751  mov     dword ptr [rbp+var_40.Data4+4], 0
0x180005758  mov     rsi, r8
0x18000575b  mov     r14, rcx
0x18000575e  cmp     eax, edx
0x180005760  jbe     short loc_1800057A4
0x180005762  call    _tlgKeywordOn
0x180005767  test    al, al
0x180005769  jz      short loc_1800057A4
0x18000576b  mov     eax, [r14+1Ch]
0x18000576f  lea     rdx, byte_1800222AF
0x180005776  mov     [rbp+var_40.Data1], eax
0x180005779  mov     rax, [r14+10h]
0x18000577d  mov     [rbp+var_30], rax
0x180005781  lea     rax, [rbp+var_40.Data4]
0x180005785  mov     [rsp+80h+var_50], rax; struct _GUID *
0x18000578a  lea     rax, [rbp+var_40]
0x18000578e  mov     [rsp+80h+var_58], rax; struct _GUID *
0x180005793  lea     rax, [rbp+var_30]
0x180005797  mov     [rsp+80h+var_60], rax
0x18000579c  mov     dword ptr [rbp+var_40.Data4], ebx
0x18000579f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800057a4  test    ebx, ebx
0x1800057a6  jz      short loc_1800057B1
0x1800057a8  test    r15, r15
0x1800057ab  jz      loc_180005899
0x1800057b1  mov     r10, [r14+10h]
0x1800057b5  mov     eax, ebx
0x1800057b7  neg     eax
0x1800057b9  sbb     rdx, rdx
0x1800057bc  mov     rcx, [r10+10h]
0x1800057c0  and     rdx, r15; struct _GUID *
0x1800057c3  test    ecx, ecx
0x1800057c5  jnz     short loc_180005811
0x1800057c7  mov     rax, rcx
0x1800057ca  shr     rax, 20h
0x1800057ce  test    eax, eax
0x1800057d0  jnz     short loc_180005811
0x1800057d2  mov     r8d, ebx; void *
0x1800057d5  mov     rcx, r10; this
0x1800057d8  test    rdi, rdi
0x1800057db  jz      short loc_1800057FC
0x1800057dd  mov     r9b, [rdi]; unsigned int
0x1800057e0  mov     [rsp+80h+var_60], rsi; unsigned __int8
0x1800057e5  call    ?SignalEventConditional@BILayer@Broker@@YAXAEBU_GUID@@PEBXKEPEBU3@@Z; Broker::BILayer::SignalEventConditional(_GUID const &,void const *,ulong,uchar,_GUID const *)
0x1800057ea  add     rsp, 80h
0x1800057f1  pop     r15
0x1800057f3  pop     r14
0x1800057f5  pop     r12
0x1800057f7  pop     rdi
0x1800057f8  pop     rsi
0x1800057f9  pop     rbx
0x1800057fa  pop     rbp
0x1800057fb  retn
0x1800057fc  mov     [rsp+80h+var_58], r12; struct _GUID *
0x180005801  lea     r9, [rbp+var_40.Data4+4]; unsigned int
0x180005805  mov     [rsp+80h+var_60], rsi; enum _BI_ACTIVATION_STATUS *
0x18000580a  call    ?SignalEventEx@BILayer@Broker@@YAXAEBU_GUID@@PEBXKPEAW4_BI_ACTIVATION_STATUS@@PEBU3@3@Z; Broker::BILayer::SignalEventEx(_GUID const &,void const *,ulong,_BI_ACTIVATION_STATUS *,_GUID const *,_GUID const *)
0x18000580f  jmp     short loc_1800057EA
0x180005811  mov     r9d, [r10+28h]
0x180005815  mov     al, 1
0x180005817  test    al, r9b
0x18000581a  jz      short loc_180005827
0x18000581c  test    rdi, rdi
0x18000581f  jz      loc_1800058B8
0x180005825  jmp     short loc_180005829
0x180005827  xor     al, al
0x180005829  xor     r8b, r8b
0x18000582c  test    rdi, rdi
0x18000582f  jz      short loc_180005834
0x180005831  mov     r8b, [rdi]
0x180005834  test    r9b, 2
0x180005838  jz      short loc_18000584C
0x18000583a  lea     r9, [rbp+var_40]
0x18000583e  mov     [rbp+var_40.Data1], 0EA60h
0x180005845  mov     [rsp+80h+var_48], r9
0x18000584a  jmp     short loc_180005855
0x18000584c  mov     [rsp+80h+var_48], 0
0x180005855  mov     dword ptr [rsp+80h+var_50], ebx
0x180005859  mov     r9, r12
0x18000585c  mov     [rsp+80h+var_58], rdx
0x180005861  mov     dl, al
0x180005863  mov     [rsp+80h+var_60], rsi
0x180005868  call    EaSignalEventImpl
0x18000586d  test    eax, eax
0x18000586f  jns     loc_1800057EA
0x180005875  mov     ecx, eax; Status
0x180005877  call    cs:__imp_RtlNtStatusToDosError
0x18000587d  mov     edx, eax; unsigned int
0x18000587f  lea     rcx, [rbp+pExceptionObject]; this
0x180005883  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180005888  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000588f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180005893  call    _CxxThrowException_0
0x180005899  mov     edx, 57h ; 'W'; unsigned int
0x18000589e  lea     rcx, [rbp+pExceptionObject]; this
0x1800058a2  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x1800058a7  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800058ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800058b2  call    _CxxThrowException_0
0x1800058b8  mov     edx, 57h ; 'W'; unsigned int
0x1800058bd  lea     rcx, [rbp+pExceptionObject]; this
0x1800058c1  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x1800058c6  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800058cd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800058d1  call    _CxxThrowException_0
```
