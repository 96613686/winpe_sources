# CEtwLogCollector::UpdateProviderProperties(ushort const *,int)

- ea: `0x18000f478`
- end: `0x18000f5c4`
- name: `?UpdateProviderProperties@CEtwLogCollector@@AEAAJPEBGH@Z`
- size: `332`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, LPCWSTR lpSubKey, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18000ebe8`
- `0x18000ed88`
- `0x18000f5cc`

## callees

- `0x180001258`
- `0x180001b90`
- `0x180001bf8`
- `0x18000d8f8`
- `0x18000e054`
- `0x18000e470`
- `0x18000f478`
- `0x180014ab4`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::UpdateProviderProperties(CEtwLogCollector *this, LPCWSTR lpSubKey, int a3, int a4)
{
  GUID *v4; // rdi
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
        if ( a3 || *(_DWORD *)&ProviderId[1].Data4[4] )
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v12 = TraceStatus;
    v11 = a3;
    if ( !v6 )
      v6 = &String2;
    ProviderId = (LPCGUID)v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&word_18004125E,
      a3,
      a4,
      (__int64)&ProviderId,
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
0x18000f478  mov     [rsp-8+arg_10], rbx
0x18000f47d  push    rbp
0x18000f47e  push    rsi
0x18000f47f  push    rdi
0x18000f480  push    r14
0x18000f482  push    r15
0x18000f484  lea     rbp, [rsp-770h]
0x18000f48c  sub     rsp, 870h
0x18000f493  mov     rax, cs:__security_cookie
0x18000f49a  xor     rax, rsp
0x18000f49d  mov     [rbp+790h+var_30], rax
0x18000f4a4  xor     edi, edi
0x18000f4a6  mov     [rsp+890h+var_850], 0
0x18000f4ae  mov     [rsp+890h+ProviderId], rdi
0x18000f4b3  mov     r15d, r8d
0x18000f4b6  mov     [rsp+890h+var_84C], 401h
0x18000f4be  mov     rsi, rdx
0x18000f4c1  mov     r14, rcx
0x18000f4c4  test    rdx, rdx
0x18000f4c7  jnz     short loc_18000F4D0
0x18000f4c9  mov     ebx, 80070057h
0x18000f4ce  jmp     short loc_18000F538
0x18000f4d0  lea     rdx, [rsp+890h+var_850]; int *
0x18000f4d5  call    ?GetTraceStatus@CEtwLogCollector@@QEAAJAEAJ@Z; CEtwLogCollector::GetTraceStatus(long &)
0x18000f4da  mov     ebx, eax
0x18000f4dc  test    eax, eax
0x18000f4de  js      short loc_18000F538
0x18000f4e0  cmp     [rsp+890h+var_850], 1
0x18000f4e5  jnz     short loc_18000F538
0x18000f4e7  lea     r8, [rsp+890h+ProviderId]; struct _EVENT_PROVIDER_PROPERTIES **
0x18000f4ec  mov     rdx, rsi; lpSubKey
0x18000f4ef  mov     rcx, r14; this
0x18000f4f2  call    ?ConstructProviderProperties@CEtwLogCollector@@AEAAJPEBGAEAPEAU_EVENT_PROVIDER_PROPERTIES@@@Z; CEtwLogCollector::ConstructProviderProperties(ushort const *,_EVENT_PROVIDER_PROPERTIES * &)
0x18000f4f7  mov     rdi, [rsp+890h+ProviderId]
0x18000f4fc  mov     ebx, eax
0x18000f4fe  test    eax, eax
0x18000f500  js      short loc_18000F538
0x18000f502  test    r15d, r15d
0x18000f505  jnz     short loc_18000F511
0x18000f507  cmp     [rdi+1Ch], r15d
0x18000f50b  jnz     short loc_18000F511
0x18000f50d  xor     ebx, ebx
0x18000f50f  jmp     short loc_18000F538
0x18000f511  lea     r8, [rsp+890h+var_84C]; unsigned int *
0x18000f516  mov     rcx, r14; this
0x18000f519  lea     rdx, [rsp+890h+InstanceName]; unsigned __int16 *
0x18000f51e  call    ?GetCollectorSessionName@CEtwLogCollector@@QEAAJPEAGAEAK@Z; CEtwLogCollector::GetCollectorSessionName(ushort *,ulong &)
0x18000f523  mov     ebx, eax
0x18000f525  test    eax, eax
0x18000f527  js      short loc_18000F538
0x18000f529  mov     rdx, rdi; ProviderId
0x18000f52c  lea     rcx, [rsp+890h+InstanceName]; InstanceName
0x18000f531  call    ?UpdateProviderInTraceSession@CEtwLogHelper@@SAJPEBGPEAU_EVENT_PROVIDER_PROPERTIES@@@Z; CEtwLogHelper::UpdateProviderInTraceSession(ushort const *,_EVENT_PROVIDER_PROPERTIES *)
0x18000f536  mov     ebx, eax
0x18000f538  mov     eax, cs:dword_18004AE90
0x18000f53e  cmp     eax, 5
0x18000f541  jbe     short loc_18000F589
0x18000f543  test    rsi, rsi
0x18000f546  mov     [rsp+890h+var_84C], ebx
0x18000f54a  lea     rax, String2
0x18000f551  mov     [rsp+890h+var_850], r15d
0x18000f556  cmovz   rsi, rax
0x18000f55a  lea     rdx, word_18004125E
0x18000f561  lea     rax, [rsp+890h+var_84C]
0x18000f566  mov     [rsp+890h+ProviderId], rsi
0x18000f56b  mov     [rsp+890h+var_860], rax
0x18000f570  lea     rax, [rsp+890h+var_850]
0x18000f575  mov     [rsp+890h+var_868], rax
0x18000f57a  lea     rax, [rsp+890h+ProviderId]
0x18000f57f  mov     [rsp+890h+var_870], rax
0x18000f584  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f589  test    rdi, rdi
0x18000f58c  jz      short loc_18000F59B
0x18000f58e  mov     edx, 20h ; ' '; unsigned __int64
0x18000f593  mov     rcx, rdi; void *
0x18000f596  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f59b  mov     eax, ebx
0x18000f59d  mov     rcx, [rbp+790h+var_30]
0x18000f5a4  xor     rcx, rsp; StackCookie
0x18000f5a7  call    __security_check_cookie
0x18000f5ac  mov     rbx, [rsp+890h+arg_10]
0x18000f5b4  add     rsp, 870h
0x18000f5bb  pop     r15
0x18000f5bd  pop     r14
0x18000f5bf  pop     rdi
0x18000f5c0  pop     rsi
0x18000f5c1  pop     rbp
0x18000f5c2  retn
```
