# BrCreateBrokeredEvent

- ea: `0x180016b50`
- end: `0x180016c3b`
- name: `BrCreateBrokeredEvent`
- size: `235`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, void *, unsigned int, int, unsigned __int8 *, struct _BROKERED_EVENT **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x180014f50`
- `0x180016b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrCreateBrokeredEvent(
        const void *a1,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        int a5,
        unsigned __int8 *a6,
        struct _BROKERED_EVENT **a7)
{
  unsigned int v10; // ebx
  size_t Size; // [rsp+20h] [rbp-58h]
  Broker::Win32Error *v13; // [rsp+40h] [rbp-38h] BYREF
  Broker::BrokerBase *v14; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v15; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+80h] [rbp+8h]
  int v18; // [rsp+80h] [rbp+8h]
  int v19; // [rsp+80h] [rbp+8h]

  if ( !a1 || !a3 || (v10 = 0, !a7) )
  {
    v10 = 87;
LABEL_12:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v10);
    return v10;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v14, a1);
    LODWORD(Size) = a5;
    Broker::BrokerBase::CreateBrokeredEventBI(v14, a2, a3, a4, Size, a6, a7);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
  }
  catch ( std::bad_alloc )
  {
    v17 = 14;
    v10 = v17;
    goto LABEL_12;
  }
  catch ( Broker::InvalidParameter )
  {
    v18 = 87;
    v10 = v18;
    goto LABEL_12;
  }
  catch ( Broker::Win32Error *v13 )
  {
    v10 = *((_DWORD *)v13 + 8);
    if ( !v10 )
      return v10;
    goto LABEL_12;
  }
  catch ( ... )
  {
    v19 = 1287;
    v10 = v19;
    goto LABEL_12;
  }
  return v10;
}

```

## disassembly

```asm
0x180016b50  mov     [rsp+arg_8], rbx
0x180016b55  mov     [rsp+arg_10], rsi
0x180016b5a  push    rdi
0x180016b5b  push    r14
0x180016b5d  push    r15
0x180016b5f  sub     rsp, 60h
0x180016b63  mov     r14d, r9d
0x180016b66  mov     rsi, r8
0x180016b69  mov     r15, rdx
0x180016b6c  test    rcx, rcx
0x180016b6f  jz      short loc_180016BF0
0x180016b71  test    r8, r8
0x180016b74  jz      short loc_180016BF0
0x180016b76  xor     ebx, ebx
0x180016b78  mov     rdi, [rsp+78h+arg_30]
0x180016b80  test    rdi, rdi
0x180016b83  jz      short loc_180016BF0
0x180016b85  mov     rdx, rcx
0x180016b88  lea     rcx, [rsp+78h+var_30]
0x180016b8d  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x180016b92  nop
0x180016b93  mov     [rsp+78h+var_48], rdi; struct _BROKERED_EVENT **
0x180016b98  mov     rax, [rsp+78h+arg_28]
0x180016ba0  mov     [rsp+78h+var_50], rax; unsigned __int8 *
0x180016ba5  mov     eax, dword ptr [rsp+78h+arg_20]
0x180016bac  mov     dword ptr [rsp+78h+Size], eax; Size
0x180016bb0  mov     r9d, r14d; unsigned int
0x180016bb3  mov     r8, rsi; void *
0x180016bb6  mov     rdx, r15; unsigned __int16 *
0x180016bb9  mov     rcx, [rsp+78h+var_30]; this
0x180016bbe  call    ?CreateBrokeredEventBI@BrokerBase@Broker@@QEAAXPEBGPEAXKKPEAEPEAPEAU_BROKERED_EVENT@@@Z; Broker::BrokerBase::CreateBrokeredEventBI(ushort const *,void *,ulong,ulong,uchar *,_BROKERED_EVENT * *)
0x180016bc3  nop
0x180016bc4  mov     rcx, [rsp+78h+var_28]; this
0x180016bc9  test    rcx, rcx
0x180016bcc  jz      short loc_180016BD4
0x180016bce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016bd3  nop
0x180016bd4  jmp     short loc_180016C23
0x180016bd6  mov     ebx, [rsp+78h+arg_0]
0x180016bdd  jmp     short loc_180016BF5
0x180016bdf  jmp     short loc_180016BD6
0x180016be1  mov     ebx, [rsp+78h+arg_0]
0x180016be8  test    ebx, ebx
0x180016bea  jz      short loc_180016C23
0x180016bec  jmp     short loc_180016BF5
0x180016bee  jmp     short loc_180016BD6
0x180016bf0  mov     ebx, 57h ; 'W'
0x180016bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bfc  test    dword ptr [rcx+1Ch], 800h
0x180016c03  jz      short loc_180016C23
0x180016c05  cmp     byte ptr [rcx+19h], 2
0x180016c09  jb      short loc_180016C23
0x180016c0b  mov     edx, 14h
0x180016c10  mov     r9d, ebx
0x180016c13  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x180016c1a  mov     rcx, [rcx+10h]
0x180016c1e  call    WPP_SF_d
0x180016c23  mov     eax, ebx
0x180016c25  lea     r11, [rsp+78h+var_18]
0x180016c2a  mov     rbx, [r11+28h]
0x180016c2e  mov     rsi, [r11+30h]
0x180016c32  mov     rsp, r11
0x180016c35  pop     r15
0x180016c37  pop     r14
0x180016c39  pop     rdi
0x180016c3a  retn
```
