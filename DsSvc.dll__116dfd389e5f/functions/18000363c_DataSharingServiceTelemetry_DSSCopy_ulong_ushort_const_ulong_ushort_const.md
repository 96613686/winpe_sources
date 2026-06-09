# DataSharingServiceTelemetry::DSSCopy<ulong,ushort const *>(ulong &&,ushort const * &&)

- ea: `0x18000363c`
- end: `0x1800036c2`
- name: `??$DSSCopy@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007220`

## callees

- `0x180001010`
- `0x1800017ec`
- `0x18000363c`
- `0x180005c54`

## pseudocode

```c
int __fastcall DataSharingServiceTelemetry::DSSCopy<unsigned long,unsigned short const *>(int *a1, const WCHAR **a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const WCHAR *v7; // rcx
  const WCHAR *v9; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v4 = DataSharingServiceProvider::Provider((__int64)a1);
  if ( *(_DWORD *)v4 > 5u )
  {
    LODWORD(v4) = tlgKeywordOn(v4, 0x200000000000LL);
    if ( (_BYTE)v4 )
    {
      v7 = *a2;
      v10 = *a1;
      v9 = v7;
      v11 = 0x1000000;
      LODWORD(v4) = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                      v6,
                      (unsigned __int8 *)&dword_18002580C,
                      v5,
                      v6,
                      (__int64)&v10,
                      &v9,
                      (__int64)&v11);
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18000363c  mov     [rsp+arg_0], rbx
0x180003641  push    rdi
0x180003642  sub     rsp, 50h
0x180003646  mov     rbx, rdx
0x180003649  mov     rdi, rcx
0x18000364c  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x180003651  mov     r9, rax
0x180003654  mov     r8d, [rax]
0x180003657  cmp     r8d, 5
0x18000365b  jbe     short loc_1800036B7
0x18000365d  mov     rdx, 200000000000h
0x180003667  mov     rcx, rax
0x18000366a  call    _tlgKeywordOn
0x18000366f  test    al, al
0x180003671  jz      short loc_1800036B7
0x180003673  mov     eax, [rdi]
0x180003675  lea     rdx, dword_18002580C
0x18000367c  mov     rcx, [rbx]
0x18000367f  mov     [rsp+58h+arg_10], eax
0x180003683  lea     rax, [rsp+58h+arg_18]
0x180003688  mov     [rsp+58h+var_28], rax
0x18000368d  lea     rax, [rsp+58h+var_18]
0x180003692  mov     [rsp+58h+var_30], rax
0x180003697  lea     rax, [rsp+58h+arg_10]
0x18000369c  mov     [rsp+58h+var_18], rcx
0x1800036a1  mov     rcx, r9
0x1800036a4  mov     [rsp+58h+var_38], rax
0x1800036a9  mov     [rsp+58h+arg_18], 1000000h
0x1800036b2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800036b7  mov     rbx, [rsp+58h+arg_0]
0x1800036bc  add     rsp, 50h
0x1800036c0  pop     rdi
0x1800036c1  retn
```
