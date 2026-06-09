# CEtwLogCollector::UpdateProviderProperties(ushort const *,int)

- ea: `0x18000ed34`
- end: `0x18000ee7f`
- name: `?UpdateProviderProperties@CEtwLogCollector@@AEAAJPEBGH@Z`
- size: `331`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, LPCWSTR lpSubKey, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18000e4cc`
- `0x18000e664`
- `0x18000ee88`

## callees

- `0x180001250`
- `0x180001b60`
- `0x180001bc8`
- `0x18000d290`
- `0x18000d998`
- `0x18000dd98`
- `0x18000ed34`
- `0x180014004`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::UpdateProviderProperties(
        CEtwLogCollector *this,
        LPCWSTR lpSubKey,
        __int64 a3,
        __int64 a4)
{
  GUID *v4; // rdi
  int v5; // r15d
  const WCHAR *v6; // rsi
  signed int TraceStatus; // ebx
  int v9; // eax
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-BCh] BYREF
  LPCGUID ProviderId; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR InstanceName[1032]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = 0;
  v11 = 0;
  ProviderId = 0;
  v5 = a3;
  v12 = 1025;
  v6 = lpSubKey;
  if ( lpSubKey )
  {
    TraceStatus = CEtwLogCollector::GetTraceStatus(this, &v11);
    if ( TraceStatus >= 0 && v11 == 1 )
    {
      v9 = CEtwLogCollector::ConstructProviderProperties(this, v6, (struct _EVENT_PROVIDER_PROPERTIES **)&ProviderId);
      v4 = (GUID *)ProviderId;
      TraceStatus = v9;
      if ( v9 >= 0 )
      {
        if ( v5 || *(_DWORD *)&ProviderId[1].Data4[4] )
        {
          TraceStatus = CEtwLogCollector::GetCollectorSessionName(this, InstanceName, &v12);
          if ( TraceStatus >= 0 )
            TraceStatus = CEtwLogHelper::UpdateProviderInTraceSession(InstanceName, v4);
        }
        else
        {
          TraceStatus = 0;
        }
      }
    }
  }
  else
  {
    TraceStatus = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v12 = TraceStatus;
    v11 = v5;
    if ( !v6 )
      v6 = &String2;
    ProviderId = (LPCGUID)v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&word_18003F25E,
      a3,
      a4,
      (const WCHAR **)&ProviderId,
      (__int64)&v11,
      (__int64)&v12);
  }
  if ( v4 )
    operator delete(v4);
  return (unsigned int)TraceStatus;
}

```

## disassembly

```asm
0x18000ed34  mov     [rsp-8+arg_10], rbx
0x18000ed39  push    rbp
0x18000ed3a  push    rsi
0x18000ed3b  push    rdi
0x18000ed3c  push    r14
0x18000ed3e  push    r15
0x18000ed40  lea     rbp, [rsp-770h]
0x18000ed48  sub     rsp, 870h
0x18000ed4f  mov     rax, cs:__security_cookie
0x18000ed56  xor     rax, rsp
0x18000ed59  mov     [rbp+790h+var_30], rax
0x18000ed60  xor     edi, edi
0x18000ed62  mov     [rsp+890h+var_850], 0
0x18000ed6a  mov     [rsp+890h+ProviderId], rdi
0x18000ed6f  mov     r15d, r8d
0x18000ed72  mov     [rsp+890h+var_84C], 401h
0x18000ed7a  mov     rsi, rdx
0x18000ed7d  mov     r14, rcx
0x18000ed80  test    rdx, rdx
0x18000ed83  jnz     short loc_18000ED8C
0x18000ed85  mov     ebx, 80070057h
0x18000ed8a  jmp     short loc_18000EDF4
0x18000ed8c  lea     rdx, [rsp+890h+var_850]; int *
0x18000ed91  call    ?GetTraceStatus@CEtwLogCollector@@QEAAJAEAJ@Z; CEtwLogCollector::GetTraceStatus(long &)
0x18000ed96  mov     ebx, eax
0x18000ed98  test    eax, eax
0x18000ed9a  js      short loc_18000EDF4
0x18000ed9c  cmp     [rsp+890h+var_850], 1
0x18000eda1  jnz     short loc_18000EDF4
0x18000eda3  lea     r8, [rsp+890h+ProviderId]; struct _EVENT_PROVIDER_PROPERTIES **
0x18000eda8  mov     rdx, rsi; lpSubKey
0x18000edab  mov     rcx, r14; this
0x18000edae  call    ?ConstructProviderProperties@CEtwLogCollector@@AEAAJPEBGAEAPEAU_EVENT_PROVIDER_PROPERTIES@@@Z; CEtwLogCollector::ConstructProviderProperties(ushort const *,_EVENT_PROVIDER_PROPERTIES * &)
0x18000edb3  mov     rdi, [rsp+890h+ProviderId]
0x18000edb8  mov     ebx, eax
0x18000edba  test    eax, eax
0x18000edbc  js      short loc_18000EDF4
0x18000edbe  test    r15d, r15d
0x18000edc1  jnz     short loc_18000EDCD
0x18000edc3  cmp     [rdi+1Ch], r15d
0x18000edc7  jnz     short loc_18000EDCD
0x18000edc9  xor     ebx, ebx
0x18000edcb  jmp     short loc_18000EDF4
0x18000edcd  lea     r8, [rsp+890h+var_84C]; unsigned int *
0x18000edd2  mov     rcx, r14; this
0x18000edd5  lea     rdx, [rsp+890h+InstanceName]; unsigned __int16 *
0x18000edda  call    ?GetCollectorSessionName@CEtwLogCollector@@QEAAJPEAGAEAK@Z; CEtwLogCollector::GetCollectorSessionName(ushort *,ulong &)
0x18000eddf  mov     ebx, eax
0x18000ede1  test    eax, eax
0x18000ede3  js      short loc_18000EDF4
0x18000ede5  mov     rdx, rdi; ProviderId
0x18000ede8  lea     rcx, [rsp+890h+InstanceName]; InstanceName
0x18000eded  call    ?UpdateProviderInTraceSession@CEtwLogHelper@@SAJPEBGPEAU_EVENT_PROVIDER_PROPERTIES@@@Z; CEtwLogHelper::UpdateProviderInTraceSession(ushort const *,_EVENT_PROVIDER_PROPERTIES *)
0x18000edf2  mov     ebx, eax
0x18000edf4  mov     eax, cs:dword_180048E90
0x18000edfa  cmp     eax, 5
0x18000edfd  jbe     short loc_18000EE45
0x18000edff  test    rsi, rsi
0x18000ee02  mov     [rsp+890h+var_84C], ebx
0x18000ee06  lea     rax, String2
0x18000ee0d  mov     [rsp+890h+var_850], r15d
0x18000ee12  cmovz   rsi, rax
0x18000ee16  lea     rdx, word_18003F25E
0x18000ee1d  lea     rax, [rsp+890h+var_84C]
0x18000ee22  mov     [rsp+890h+ProviderId], rsi
0x18000ee27  mov     [rsp+890h+var_860], rax
0x18000ee2c  lea     rax, [rsp+890h+var_850]
0x18000ee31  mov     [rsp+890h+var_868], rax
0x18000ee36  lea     rax, [rsp+890h+ProviderId]
0x18000ee3b  mov     [rsp+890h+var_870], rax
0x18000ee40  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ee45  test    rdi, rdi
0x18000ee48  jz      short loc_18000EE57
0x18000ee4a  mov     edx, 20h ; ' '; unsigned __int64
0x18000ee4f  mov     rcx, rdi; void *
0x18000ee52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ee57  mov     eax, ebx
0x18000ee59  mov     rcx, [rbp+790h+var_30]
0x18000ee60  xor     rcx, rsp; StackCookie
0x18000ee63  call    __security_check_cookie
0x18000ee68  mov     rbx, [rsp+890h+arg_10]
0x18000ee70  add     rsp, 870h
0x18000ee77  pop     r15
0x18000ee79  pop     r14
0x18000ee7b  pop     rdi
0x18000ee7c  pop     rsi
0x18000ee7d  pop     rbp
0x18000ee7e  retn
```
