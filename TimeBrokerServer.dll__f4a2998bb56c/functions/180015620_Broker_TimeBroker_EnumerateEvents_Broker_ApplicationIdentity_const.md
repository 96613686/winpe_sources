# Broker::TimeBroker::EnumerateEvents(Broker::ApplicationIdentity const &)

- ea: `0x180015620`
- end: `0x180015793`
- name: `?EnumerateEvents@TimeBroker@Broker@@QEAA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEBUApplicationIdentity@2@@Z`
- size: `371`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800118e0`

## callees

- `0x180002400`
- `0x180003800`
- `0x180004488`
- `0x180005b90`
- `0x180013978`
- `0x180014cc4`
- `0x180015620`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x180015765`
- `BrokerLib!BrBufferFree` at `0x180015765`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x1800156b7`
- `BrokerLib!BrQueryBrokeredEvents2` at `0x1800156b7`

## pseudocode

```c
_QWORD *__fastcall Broker::TimeBroker::EnumerateEvents(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // rbx
  _QWORD *v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // edi
  __int64 i; // rdi
  _OWORD *v10; // r8
  _OWORD *v11; // rdx
  __int64 v13; // [rsp+38h] [rbp-70h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-68h] BYREF
  __int128 v15; // [rsp+48h] [rbp-60h]
  int v16; // [rsp+58h] [rbp-50h]
  unsigned int v17; // [rsp+60h] [rbp-48h]
  void **v18; // [rsp+68h] [rbp-40h] BYREF
  _DWORD v19[14]; // [rsp+70h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+B0h] [rbp+8h] BYREF
  _QWORD *v21; // [rsp+B8h] [rbp+10h]
  char v22; // [rsp+C8h] [rbp+20h] BYREF

  v21 = a2;
  v4 = a2;
  std::vector<_GUID>::vector<_GUID>(a2);
  if ( *(_QWORD *)(a1 + 192) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v20 = 0;
      v13 = 0;
      Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v22, 1);
      v6 = (_QWORD *)(a3 + 56);
      if ( *(_QWORD *)(a3 + 80) > 7u )
        v6 = (_QWORD *)*v6;
      v7 = BrQueryBrokeredEvents2(*(_QWORD *)(a1 + 192), 0, v6, 0xFFFFFFFFLL, &v20, &v13);
      v8 = v7;
      if ( v7 )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v7);
        v15 = 0;
        v16 = 1;
        pExceptionObject = &Broker::Win32Error::`vftable';
        v17 = v8;
        throw (Broker::Win32Error *)&pExceptionObject;
      }
      for ( i = 0; (unsigned int)i < v20; i = (unsigned int)(i + 1) )
      {
        v10 = *(_OWORD **)(v13 + 8 * i);
        v11 = (_OWORD *)v4[1];
        if ( v11 == (_OWORD *)v4[2] )
        {
          std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v4, v11, v10);
        }
        else
        {
          *v11 = *v10;
          v4[1] += 16LL;
        }
      }
      if ( v13 )
        BrBufferFree();
      Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v22);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', (Broker::Win32Error *)&v18) )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v19[6]);
        if ( v13 )
          BrBufferFree();
        v18 = &std::exception::`vftable';
        o___std_exception_destroy_0(v19);
        v4 = v21;
        __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_18001577C);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180015620  mov     [rsp+arg_8], rdx
0x180015625  push    rbx
0x180015626  push    rsi
0x180015627  push    rdi
0x180015628  sub     rsp, 90h
0x18001562f  mov     rdi, r8
0x180015632  mov     rbx, rdx
0x180015635  mov     rsi, rcx
0x180015638  mov     [rsp+0A8h+var_78], 0
0x180015640  mov     rcx, rdx
0x180015643  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180015648  mov     [rsp+0A8h+var_78], 1
0x180015650  cmp     qword ptr [rsi+0C0h], 0
0x180015658  jz      loc_180015784
0x18001565e  mov     [rsp+0A8h+arg_0], 0
0x180015669  mov     [rsp+0A8h+var_70], 0
0x180015672  mov     edx, 1; int
0x180015677  lea     rcx, [rsp+0A8h+arg_18]; this
0x18001567f  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180015684  nop
0x180015685  lea     r8, [rdi+38h]
0x180015689  cmp     qword ptr [r8+18h], 7
0x18001568e  jbe     short loc_180015693
0x180015690  mov     r8, [r8]
0x180015693  lea     rax, [rsp+0A8h+var_70]
0x180015698  mov     [rsp+0A8h+var_80], rax
0x18001569d  lea     rax, [rsp+0A8h+arg_0]
0x1800156a5  mov     [rsp+0A8h+var_88], rax
0x1800156aa  or      r9d, 0FFFFFFFFh
0x1800156ae  xor     edx, edx
0x1800156b0  mov     rcx, [rsi+0C0h]
0x1800156b7  call    cs:__imp_BrQueryBrokeredEvents2
0x1800156bd  mov     edi, eax
0x1800156bf  test    eax, eax
0x1800156c1  jz      short loc_180015722
0x1800156c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156ca  test    dword ptr [rcx+1Ch], 100h
0x1800156d1  jz      short loc_1800156F1
0x1800156d3  cmp     byte ptr [rcx+19h], 2
0x1800156d7  jb      short loc_1800156F1
0x1800156d9  mov     edx, 17h
0x1800156de  mov     r9d, eax
0x1800156e1  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800156e8  mov     rcx, [rcx+10h]
0x1800156ec  call    WPP_SF_d
0x1800156f1  xorps   xmm0, xmm0
0x1800156f4  movups  [rsp+0A8h+var_60], xmm0
0x1800156f9  mov     [rsp+0A8h+var_50], 1
0x180015701  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180015708  mov     [rsp+0A8h+pExceptionObject], rax
0x18001570d  mov     [rsp+0A8h+var_48], edi
0x180015711  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180015718  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18001571d  call    _CxxThrowException_0
0x180015722  xor     edi, edi
0x180015724  cmp     edi, [rsp+0A8h+arg_0]
0x18001572b  jnb     short loc_18001575B
0x18001572d  mov     rax, [rsp+0A8h+var_70]
0x180015732  mov     r8, [rax+rdi*8]
0x180015736  mov     rdx, [rbx+8]
0x18001573a  cmp     rdx, [rbx+10h]
0x18001573e  jz      short loc_18001574F
0x180015740  movups  xmm0, xmmword ptr [r8]
0x180015744  movdqu  xmmword ptr [rdx], xmm0
0x180015748  add     qword ptr [rbx+8], 10h
0x18001574d  jmp     short loc_180015757
0x18001574f  mov     rcx, rbx
0x180015752  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x180015757  inc     edi
0x180015759  jmp     short loc_180015724
0x18001575b  mov     rcx, [rsp+0A8h+var_70]
0x180015760  test    rcx, rcx
0x180015763  jz      short loc_18001576C
0x180015765  call    cs:__imp_BrBufferFree
0x18001576b  nop
0x18001576c  lea     rcx, [rsp+0A8h+arg_18]; this
0x180015774  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180015779  nop
0x18001577a  jmp     short loc_180015784
0x18001577c  mov     rbx, [rsp+0A8h+arg_8]
0x180015784  mov     rax, rbx
0x180015787  add     rsp, 90h
0x18001578e  pop     rdi
0x18001578f  pop     rsi
0x180015790  pop     rbx
0x180015791  retn
```
