# CPort::SendCompleteNetBufferLists(_NET_BUFFER_LIST *)

- ea: `0x140033590`
- end: `0x140033722`
- name: `?SendCompleteNetBufferLists@CPort@@QEAAXPEAU_NET_BUFFER_LIST@@@Z`
- size: `402`
- prototype: `void __fastcall(CPort *__hidden this, struct _NET_BUFFER_LIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140033c40`
- `0x140039a60`

## callees

- `0x14002aa28`
- `0x1400330a0`
- `0x140033590`
- `0x140033730`
- `0x140034e04`
- `0x140034ec4`
- `0x14003b77c`

## import_xrefs

- `NDIS!NdisMSendNetBufferListsComplete` at `0x140033644`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140033644`

## pseudocode

```c
void __fastcall CPort::SendCompleteNetBufferLists(CPort *this, struct _NET_BUFFER_LIST *a2, int a3)
{
  struct _NET_BUFFER_LIST *v3; // rdi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // [rsp+28h] [rbp-40h]
  unsigned __int8 v8; // [rsp+78h] [rbp+10h] BYREF

  v3 = a2;
  v8 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        102,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        103,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId);
    }
  }
  CPort::FreeTxWfcFrame(this, v3, &v8);
  if ( v3 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_qDq(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        v6,
        104,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        (char)v3);
    }
    NdisMSendNetBufferListsComplete(this->m_pAdapter->m_MiniportAdapterHandle, v3, 0);
  }
  if ( v8 )
    CPort::CompletePendingCancelSendsOrHaltJobs(this);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v7) = 0;
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      105,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v7);
  }
}

```

## disassembly

```asm
0x140033590  push    rbx
0x140033592  push    rbp
0x140033593  push    rsi
0x140033594  push    rdi
0x140033595  sub     rsp, 48h
0x140033599  mov     rdi, rdx
0x14003359c  mov     [rsp+68h+arg_8], 0
0x1400335a1  mov     rbx, rcx
0x1400335a4  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400335ab  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400335b2  lea     rbp, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400335b9  jz      short loc_1400335FC
0x1400335bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335c2  cmp     byte ptr [rcx+29h], 5
0x1400335c6  jnb     loc_140033686
0x1400335cc  cmp     word ptr [rcx+48h], 0
0x1400335d1  jnz     loc_140033686
0x1400335d7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400335de  jz      short loc_1400335FC
0x1400335e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335e7  cmp     byte ptr [rcx+29h], 5
0x1400335eb  jnb     loc_1400336CD
0x1400335f1  cmp     word ptr [rcx+48h], 0
0x1400335f6  jnz     loc_1400336CD
0x1400335fc  lea     r8, [rsp+68h+arg_8]; unsigned __int8 *
0x140033601  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x140033604  mov     rcx, rbx; this
0x140033607  call    ?FreeTxWfcFrame@CPort@@AEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CPort::FreeTxWfcFrame(_NET_BUFFER_LIST *,uchar *)
0x14003360c  test    rdi, rdi
0x14003360f  jz      short loc_140033650
0x140033611  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140033618  jz      short loc_140033636
0x14003361a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033621  cmp     byte ptr [rcx+29h], 5
0x140033625  jnb     loc_1400336F5
0x14003362b  cmp     word ptr [rcx+48h], 0
0x140033630  jnz     loc_1400336F5
0x140033636  mov     rcx, [rbx+58h]
0x14003363a  xor     r8d, r8d; SendCompleteFlags
0x14003363d  mov     rdx, rdi; NetBufferList
0x140033640  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x140033644  call    cs:__imp_NdisMSendNetBufferListsComplete
0x14003364b  nop     dword ptr [rax+rax+00h]
0x140033650  cmp     [rsp+68h+arg_8], 0
0x140033655  jz      short loc_14003365F
0x140033657  mov     rcx, rbx; this
0x14003365a  call    ?CompletePendingCancelSendsOrHaltJobs@CPort@@AEAAXXZ; CPort::CompletePendingCancelSendsOrHaltJobs(void)
0x14003365f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140033666  jz      short loc_14003367C
0x140033668  mov     rcx, cs:WPP_GLOBAL_Control
0x14003366f  cmp     byte ptr [rcx+29h], 5
0x140033673  jnb     short loc_1400336A7
0x140033675  cmp     word ptr [rcx+48h], 0
0x14003367a  jnz     short loc_1400336A7
0x14003367c  add     rsp, 48h
0x140033680  pop     rdi
0x140033681  pop     rsi
0x140033682  pop     rbp
0x140033683  pop     rbx
0x140033684  retn
0x140033686  mov     rcx, [rcx+40h]
0x14003368a  mov     r9d, 66h ; 'f'
0x140033690  mov     r8d, 1
0x140033696  mov     [rsp+68h+var_48], rbp
0x14003369b  mov     dl, 5
0x14003369d  call    WPP_RECORDER_SF_
0x1400336a2  jmp     loc_1400335D7
0x1400336a7  mov     rcx, [rcx+40h]
0x1400336ab  mov     r9d, 69h ; 'i'
0x1400336b1  mov     dword ptr [rsp+68h+var_40], 0
0x1400336b9  mov     r8d, 1
0x1400336bf  mov     dl, 5
0x1400336c1  mov     [rsp+68h+var_48], rbp
0x1400336c6  call    WPP_RECORDER_SF_D
0x1400336cb  jmp     short loc_14003367C
0x1400336cd  movzx   eax, word ptr [rbx+64h]
0x1400336d1  mov     r9d, 67h ; 'g'
0x1400336d7  mov     rcx, [rcx+40h]
0x1400336db  mov     dl, 5
0x1400336dd  mov     [rsp+68h+var_38], eax
0x1400336e1  mov     [rsp+68h+var_40], rbx
0x1400336e6  mov     [rsp+68h+var_48], rbp
0x1400336eb  call    WPP_RECORDER_SF_qD
0x1400336f0  jmp     loc_1400335FC
0x1400336f5  movzx   eax, word ptr [rbx+64h]
0x1400336f9  mov     r9d, 68h ; 'h'
0x1400336ff  mov     rcx, [rcx+40h]
0x140033703  mov     dl, 5
0x140033705  mov     [rsp+68h+var_30], rdi
0x14003370a  mov     [rsp+68h+var_38], eax
0x14003370e  mov     [rsp+68h+var_40], rbx
0x140033713  mov     [rsp+68h+var_48], rbp
0x140033718  call    WPP_RECORDER_SF_qDq
0x14003371d  jmp     loc_140033636
```
