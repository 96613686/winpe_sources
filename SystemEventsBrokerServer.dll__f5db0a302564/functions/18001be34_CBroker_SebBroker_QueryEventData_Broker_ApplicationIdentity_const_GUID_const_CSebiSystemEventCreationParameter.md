# CBroker::SebBroker::QueryEventData(Broker::ApplicationIdentity const &,_GUID const &,_CSebiSystemEventCreationParameter &)

- ea: `0x18001be34`
- end: `0x18001c003`
- name: `?QueryEventData@SebBroker@CBroker@@QEAAXAEBUApplicationIdentity@Broker@@AEBU_GUID@@AEAU_CSebiSystemEventCreationParameter@@@Z`
- size: `463`
- prototype: `void __fastcall(CBroker::SebBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _GUID *, struct _CSebiSystemEventCreationParameter *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bb90`

## callees

- `0x1800076a0`
- `0x180008c00`
- `0x18000cb50`
- `0x180013820`
- `0x180013860`
- `0x180013920`
- `0x18001be34`
- `0x18001c00c`
- `0x18001d9ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CBroker::SebBroker::QueryEventData(
        CBroker::SebBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _GUID *a3,
        struct _CSebiSystemEventCreationParameter *a4)
{
  __int64 v8; // rbx
  const wchar_t *v9; // rax
  __int64 v10; // [rsp+30h] [rbp-68h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-60h]
  _BYTE v12[16]; // [rsp+40h] [rbp-58h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-48h] BYREF
  __int128 v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+68h] [rbp-30h]
  __int64 v16; // [rsp+A0h] [rbp+8h]

  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v12, (struct _RTL_SRWLOCK *)this + 1, 1);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, a3);
  Broker::BrokerEventTable<CBroker::SebEvent>::Find((__int64 **)this + 2, &v10, a3);
  v8 = v10;
  if ( Broker::ApplicationIdentity::operator!=(v10 + 8, (__int64)a2) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = (const wchar_t *)((char *)a2 + 56);
      if ( *((_QWORD *)a2 + 10) > 7u )
        v9 = *(const wchar_t **)v9;
      WPP_SF__guid__sid_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x28u,
        &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids,
        (__int64)a3,
        *(char **)a2,
        v9);
    }
    v14 = 0;
    v15 = 5;
    pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&pExceptionObject;
  }
  v16 = *(_QWORD *)(v8 + 104);
  *((_DWORD *)a4 + 2) = *(_DWORD *)(v8 + 96);
  *((_DWORD *)a4 + 3) = *(_DWORD *)(v8 + 100);
  *((_DWORD *)a4 + 6) = *(_DWORD *)(v8 + 156);
  *((_DWORD *)a4 + 5) = *(_DWORD *)(v8 + 248);
  *((_DWORD *)a4 + 4) = *(_DWORD *)(v8 + 208);
  *((_DWORD *)a4 + 7) = *(_DWORD *)(v8 + 212);
  *((_DWORD *)a4 + 8) = *(_DWORD *)(v8 + 216);
  *((_DWORD *)a4 + 9) = *(_DWORD *)(v8 + 220);
  *((_DWORD *)a4 + 10) = *(_DWORD *)(v8 + 224);
  *((_DWORD *)a4 + 11) = *(_DWORD *)(v8 + 228);
  *((_DWORD *)a4 + 12) = *(_DWORD *)(v8 + 232);
  *((_DWORD *)a4 + 13) = *(_DWORD *)(v8 + 236);
  *(_QWORD *)a4 = v16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, a3);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v12);
}

```

## disassembly

```asm
0x18001be34  push    rbx
0x18001be36  push    rsi
0x18001be37  push    rdi
0x18001be38  push    r14
0x18001be3a  sub     rsp, 78h
0x18001be3e  mov     r14, r9
0x18001be41  mov     rdi, r8
0x18001be44  mov     rsi, rdx
0x18001be47  mov     rbx, rcx
0x18001be4a  lea     rdx, [rcx+8]; struct _RTL_SRWLOCK *
0x18001be4e  mov     r8b, 1; bool
0x18001be51  lea     rcx, [rsp+98h+var_58]; this
0x18001be56  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001be5b  nop
0x18001be5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be63  test    byte ptr [rcx+1Ch], 1
0x18001be67  jz      short loc_18001BE87
0x18001be69  cmp     byte ptr [rcx+19h], 4
0x18001be6d  jb      short loc_18001BE87
0x18001be6f  mov     edx, 27h ; '''
0x18001be74  mov     r9, rdi
0x18001be77  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001be7e  mov     rcx, [rcx+10h]
0x18001be82  call    WPP_SF__guid_
0x18001be87  lea     rcx, [rbx+10h]
0x18001be8b  mov     r8, rdi
0x18001be8e  lea     rdx, [rsp+98h+var_68]
0x18001be93  call    ?Find@?$BrokerEventTable@VSebEvent@CBroker@@@Broker@@QEAA?AV?$shared_ptr@VSebEvent@CBroker@@@std@@AEBU_GUID@@@Z; Broker::BrokerEventTable<CBroker::SebEvent>::Find(_GUID const &)
0x18001be98  nop
0x18001be99  mov     rbx, [rsp+98h+var_68]
0x18001be9e  lea     rcx, [rbx+8]
0x18001bea2  mov     rdx, rsi
0x18001bea5  call    ??9ApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator!=(Broker::ApplicationIdentity const &)
0x18001beaa  test    al, al
0x18001beac  jz      short loc_18001BF22
0x18001beae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beb5  test    byte ptr [rcx+1Ch], 20h
0x18001beb9  jz      short loc_18001BEF4
0x18001bebb  cmp     byte ptr [rcx+19h], 2
0x18001bebf  jb      short loc_18001BEF4
0x18001bec1  lea     rax, [rsi+38h]
0x18001bec5  cmp     qword ptr [rax+18h], 7
0x18001beca  jbe     short loc_18001BECF
0x18001becc  mov     rax, [rax]
0x18001becf  mov     edx, 28h ; '('
0x18001bed4  mov     [rsp+98h+var_70], rax; __int64
0x18001bed9  mov     rax, [rsi]
0x18001bedc  mov     [rsp+98h+pSid], rax; pSid
0x18001bee1  mov     r9, rdi
0x18001bee4  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001beeb  mov     rcx, [rcx+10h]; LoggerHandle
0x18001beef  call    WPP_SF__guid__sid_S
0x18001bef4  xorps   xmm0, xmm0
0x18001bef7  movups  [rsp+98h+var_40], xmm0
0x18001befc  mov     [rsp+98h+var_30], 5
0x18001bf04  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18001bf0b  mov     [rsp+98h+pExceptionObject], rax
0x18001bf10  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18001bf17  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001bf1c  call    _CxxThrowException_0
0x18001bf22  mov     eax, [rbx+68h]
0x18001bf25  mov     dword ptr [rsp+98h+arg_0], eax
0x18001bf2c  mov     eax, [rbx+6Ch]
0x18001bf2f  mov     dword ptr [rsp+98h+arg_0+4], eax
0x18001bf36  mov     eax, [rbx+60h]
0x18001bf39  mov     [r14+8], eax
0x18001bf3d  mov     eax, [rbx+64h]
0x18001bf40  mov     [r14+0Ch], eax
0x18001bf44  mov     eax, [rbx+9Ch]
0x18001bf4a  mov     [r14+18h], eax
0x18001bf4e  mov     eax, [rbx+0F8h]
0x18001bf54  mov     [r14+14h], eax
0x18001bf58  mov     eax, [rbx+0D0h]
0x18001bf5e  mov     [r14+10h], eax
0x18001bf62  mov     eax, [rbx+0D4h]
0x18001bf68  mov     [r14+1Ch], eax
0x18001bf6c  mov     eax, [rbx+0D8h]
0x18001bf72  mov     [r14+20h], eax
0x18001bf76  mov     eax, [rbx+0DCh]
0x18001bf7c  mov     [r14+24h], eax
0x18001bf80  mov     eax, [rbx+0E0h]
0x18001bf86  mov     [r14+28h], eax
0x18001bf8a  mov     eax, [rbx+0E4h]
0x18001bf90  mov     [r14+2Ch], eax
0x18001bf94  mov     eax, [rbx+0E8h]
0x18001bf9a  mov     [r14+30h], eax
0x18001bf9e  mov     eax, [rbx+0ECh]
0x18001bfa4  mov     [r14+34h], eax
0x18001bfa8  mov     rax, [rsp+98h+arg_0]
0x18001bfb0  mov     [r14], rax
0x18001bfb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfba  test    byte ptr [rcx+1Ch], 1
0x18001bfbe  jz      short loc_18001BFDF
0x18001bfc0  cmp     byte ptr [rcx+19h], 4
0x18001bfc4  jb      short loc_18001BFDF
0x18001bfc6  mov     edx, 29h ; ')'
0x18001bfcb  mov     r9, rdi
0x18001bfce  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001bfd5  mov     rcx, [rcx+10h]
0x18001bfd9  call    WPP_SF__guid_
0x18001bfde  nop
0x18001bfdf  mov     rcx, [rsp+98h+var_60]; this
0x18001bfe4  test    rcx, rcx
0x18001bfe7  jz      short loc_18001BFEF
0x18001bfe9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bfee  nop
0x18001bfef  lea     rcx, [rsp+98h+var_58]; this
0x18001bff4  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001bff9  add     rsp, 78h
0x18001bffd  pop     r14
0x18001bfff  pop     rdi
0x18001c000  pop     rsi
0x18001c001  pop     rbx
0x18001c002  retn
```
