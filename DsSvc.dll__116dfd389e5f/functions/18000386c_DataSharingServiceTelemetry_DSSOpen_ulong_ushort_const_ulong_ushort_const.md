# DataSharingServiceTelemetry::DSSOpen<ulong,ushort const *>(ulong &&,ushort const * &&)

- ea: `0x18000386c`
- end: `0x1800038f2`
- name: `??$DSSOpen@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800076f0`

## callees

- `0x180001010`
- `0x1800017ec`
- `0x18000386c`
- `0x180005c54`

## pseudocode

```c
int __fastcall DataSharingServiceTelemetry::DSSOpen<unsigned long,unsigned short const *>(int *a1, const WCHAR **a2)
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
                      (unsigned __int8 *)&word_18002587E,
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
0x18000386c  mov     [rsp+arg_0], rbx
0x180003871  push    rdi
0x180003872  sub     rsp, 50h
0x180003876  mov     rbx, rdx
0x180003879  mov     rdi, rcx
0x18000387c  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x180003881  mov     r9, rax
0x180003884  mov     r8d, [rax]
0x180003887  cmp     r8d, 5
0x18000388b  jbe     short loc_1800038E7
0x18000388d  mov     rdx, 200000000000h
0x180003897  mov     rcx, rax
0x18000389a  call    _tlgKeywordOn
0x18000389f  test    al, al
0x1800038a1  jz      short loc_1800038E7
0x1800038a3  mov     eax, [rdi]
0x1800038a5  lea     rdx, word_18002587E
0x1800038ac  mov     rcx, [rbx]
0x1800038af  mov     [rsp+58h+arg_10], eax
0x1800038b3  lea     rax, [rsp+58h+arg_18]
0x1800038b8  mov     [rsp+58h+var_28], rax
0x1800038bd  lea     rax, [rsp+58h+var_18]
0x1800038c2  mov     [rsp+58h+var_30], rax
0x1800038c7  lea     rax, [rsp+58h+arg_10]
0x1800038cc  mov     [rsp+58h+var_18], rcx
0x1800038d1  mov     rcx, r9
0x1800038d4  mov     [rsp+58h+var_38], rax
0x1800038d9  mov     [rsp+58h+arg_18], 1000000h
0x1800038e2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800038e7  mov     rbx, [rsp+58h+arg_0]
0x1800038ec  add     rsp, 50h
0x1800038f0  pop     rdi
0x1800038f1  retn
```
