# BrRemoveBrokeredEvent

- ea: `0x180016e80`
- end: `0x180016f9b`
- name: `BrRemoveBrokeredEvent`
- size: `283`
- prototype: `__int64 __fastcall(std::_Ref_count_base *, void *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180004ae0`
- `0x1800058e0`
- `0x1800126e0`
- `0x180016e80`
- `0x1800187b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrRemoveBrokeredEvent(
        std::_Ref_count_base *a1,
        void *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4)
{
  unsigned int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  Broker::BrokerBase *v10; // rcx
  __int64 result; // rax
  unsigned int v12; // [rsp+40h] [rbp-68h] BYREF
  const unsigned __int16 *v13; // [rsp+48h] [rbp-60h] BYREF
  Broker::BrokerBase *v14; // [rsp+50h] [rbp-58h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-50h]
  const Broker::Win32Error *v16; // [rsp+60h] [rbp-48h] BYREF
  struct _GUID v17; // [rsp+70h] [rbp-38h] BYREF
  struct _GUID *v18; // [rsp+80h] [rbp-28h] BYREF
  std::_Ref_count_base *v19; // [rsp+B0h] [rbp+8h]

  v19 = a1;
  v13 = a3;
  v18 = a4;
  if ( !a1 || !a2 )
  {
    v7 = 87;
    goto LABEL_10;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v14, a1);
    v17 = *a4;
    Broker::BrokerBase::RemoveEvent(v14, a2, a3, &v17);
    a1 = v15;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
  }
  catch ( std::bad_alloc )
  {
    v7 = 14;
    goto LABEL_10;
  }
  catch ( Broker::AccessDenied )
  {
    v7 = 5;
    goto LABEL_10;
  }
  catch ( Broker::NotFound )
  {
    v7 = 1168;
    goto LABEL_10;
  }
  catch ( const Broker::Win32Error *v16 )
  {
    a1 = (std::_Ref_count_base *)*((unsigned int *)v16 + 8);
    v12 = *((_DWORD *)v16 + 8);
    v7 = v12;
    if ( !v12 )
      goto LABEL_8;
LABEL_10:
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(a1, 8, a3, a4) )
    {
      v12 = v7;
      v10 = v19;
      if ( !v19 )
        v10 = (Broker::BrokerBase *)&BLP_TRACELOGGING_INVALID_GUID;
      v14 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v10,
        (unsigned int)&unk_180021D3D,
        v8,
        v9,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13,
        (__int64)&v18);
    }
    result = v7;
  }
  catch ( ... )
  {
    v7 = 1287;
    goto LABEL_10;
  }
LABEL_8:
  v7 = 0;
  goto LABEL_10;
}

```

## disassembly

```asm
0x180016e80  mov     [rsp+arg_0], rcx
0x180016e85  push    rbx
0x180016e86  push    rsi
0x180016e87  push    rdi
0x180016e88  sub     rsp, 90h
0x180016e8f  mov     rsi, r9
0x180016e92  mov     rdi, r8
0x180016e95  mov     rbx, rdx
0x180016e98  mov     [rsp+0A8h+var_60], r8
0x180016e9d  mov     [rsp+0A8h+var_28], r9
0x180016ea5  test    rcx, rcx
0x180016ea8  jz      short loc_180016F00
0x180016eaa  test    rdx, rdx
0x180016ead  jz      short loc_180016F00
0x180016eaf  mov     rdx, rcx
0x180016eb2  lea     rcx, [rsp+0A8h+var_58]
0x180016eb7  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x180016ebc  nop
0x180016ebd  movups  xmm0, xmmword ptr [rsi]
0x180016ec0  movdqu  xmmword ptr [rsp+0A8h+var_38.Data1], xmm0
0x180016ec6  lea     r9, [rsp+0A8h+var_38]; struct _GUID
0x180016ecb  mov     r8, rdi; unsigned __int16 *
0x180016ece  mov     rdx, rbx; void *
0x180016ed1  mov     rcx, [rsp+0A8h+var_58]; this
0x180016ed6  call    ?RemoveEvent@BrokerBase@Broker@@QEAAXPEAXPEBGU_GUID@@@Z; Broker::BrokerBase::RemoveEvent(void *,ushort const *,_GUID)
0x180016edb  nop
0x180016edc  mov     rcx, [rsp+0A8h+var_50]; this
0x180016ee1  test    rcx, rcx
0x180016ee4  jz      short loc_180016EEC
0x180016ee6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016eeb  nop
0x180016eec  jmp     short loc_180016EFC
0x180016eee  mov     ebx, [rsp+0A8h+var_68]
0x180016ef2  jmp     short loc_180016F05
0x180016ef4  mov     ebx, [rsp+0A8h+var_68]
0x180016ef8  test    ebx, ebx
0x180016efa  jnz     short loc_180016F05
0x180016efc  xor     ebx, ebx
0x180016efe  jmp     short loc_180016F05
0x180016f00  mov     ebx, 57h ; 'W'
0x180016f05  mov     eax, cs:dword_180028000
0x180016f0b  cmp     eax, 4
0x180016f0e  jbe     short loc_180016F8E
0x180016f10  mov     edx, 8
0x180016f15  call    _tlgKeywordOn
0x180016f1a  test    al, al
0x180016f1c  jz      short loc_180016F8E
0x180016f1e  mov     rax, [rsp+0A8h+var_28]
0x180016f26  mov     [rsp+0A8h+var_28], rax
0x180016f2e  mov     rax, [rsp+0A8h+var_60]
0x180016f33  mov     [rsp+0A8h+var_60], rax
0x180016f38  mov     [rsp+0A8h+var_68], ebx
0x180016f3c  mov     rcx, [rsp+0A8h+arg_0]
0x180016f44  lea     rax, BLP_TRACELOGGING_INVALID_GUID
0x180016f4b  test    rcx, rcx
0x180016f4e  cmovz   rcx, rax
0x180016f52  mov     [rsp+0A8h+var_58], rcx
0x180016f57  lea     rax, [rsp+0A8h+var_28]
0x180016f5f  mov     [rsp+0A8h+var_70], rax
0x180016f64  lea     rax, [rsp+0A8h+var_60]
0x180016f69  mov     [rsp+0A8h+var_78], rax
0x180016f6e  lea     rax, [rsp+0A8h+var_68]
0x180016f73  mov     [rsp+0A8h+var_80], rax
0x180016f78  lea     rax, [rsp+0A8h+var_58]
0x180016f7d  mov     [rsp+0A8h+var_88], rax
0x180016f82  lea     rdx, unk_180021D3D
0x180016f89  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x180016f8e  mov     eax, ebx
0x180016f90  add     rsp, 90h
0x180016f97  pop     rdi
0x180016f98  pop     rsi
0x180016f99  pop     rbx
0x180016f9a  retn
```
