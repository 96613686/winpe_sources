# CAdapter::SendCompleteNbl(_NET_BUFFER_LIST *)

- ea: `0x140033c40`
- end: `0x140033fa8`
- name: `?SendCompleteNbl@CAdapter@@QEAAHPEAU_NET_BUFFER_LIST@@@Z`
- size: `872`
- prototype: `int(CAdapter *__hidden this, struct _NET_BUFFER_LIST *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14009dd40`

## callees

- `0x14002aa28`
- `0x1400330a0`
- `0x140033590`
- `0x140033730`
- `0x140033c40`
- `0x140034e04`
- `0x140034ec4`
- `0x14003b77c`
- `0x14008640c`

## import_xrefs

- `NDIS!NdisMSendNetBufferListsComplete` at `0x140033dad`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140033dad`

## pseudocode

```c
__int64 __fastcall CAdapter::SendCompleteNbl(CAdapter *this, struct _NET_BUFFER_LIST *a2, int a3, int a4)
{
  struct _NET_BUFFER_LIST *v4; // rbx
  struct _NET_BUFFER_LIST *v5; // r15
  CPort *v6; // rdi
  __int16 v8; // bp
  _WORD *v9; // r13
  struct _NET_BUFFER_LIST *Alignment; // r14
  __int16 v11; // si
  int v12; // edx
  int v13; // r8d
  unsigned int i; // ecx
  int v16; // [rsp+20h] [rbp-48h]
  __int64 v17; // [rsp+28h] [rbp-40h]
  unsigned __int8 v18; // [rsp+78h] [rbp+10h] BYREF

  v4 = a2;
  v5 = 0;
  v6 = 0;
  v8 = -1;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      161,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  if ( !v4 )
    goto LABEL_23;
  do
  {
    v9 = v4->MiniportReserved[0];
    Alignment = (struct _NET_BUFFER_LIST *)v4->Link.Alignment;
    v4->Link.Alignment = 0;
    v4->Status = 0;
    v11 = v9[16];
    if ( v8 != v11 )
    {
      if ( v5 && v6 )
        CPort::SendCompleteNetBufferLists(v6, v5);
      v5 = 0;
      for ( i = 0; i < 5; ++i )
      {
        v6 = this->m_pPortList[i];
        if ( v6 && v6->m_WfcPortId == v11 )
          goto LABEL_6;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Dqq(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)a2, a3, a4, v16, v11, (char)v4, (char)v9);
      v6 = 0;
    }
LABEL_6:
    v4->Link.Alignment = (ULONGLONG)v5;
    v5 = v4;
    v4 = Alignment;
    v8 = v11;
  }
  while ( Alignment );
  if ( !v5 || !v6 )
    goto LABEL_23;
  v18 = 0;
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
        (char)v6,
        v6->m_WfcPortId);
    }
  }
  CPort::FreeTxWfcFrame(v6, v5, &v18);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_qDq(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      104,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      (char)v6,
      v6->m_WfcPortId,
      (char)v5);
  }
  NdisMSendNetBufferListsComplete(v6->m_pAdapter->m_MiniportAdapterHandle, v5, 0);
  if ( v18 )
    CPort::CompletePendingCancelSendsOrHaltJobs(v6);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v17) = 0;
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        105,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        v17);
    }
LABEL_23:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LODWORD(v17) = 0;
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        163,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140033c40  mov     [rsp+arg_18], rbx
0x140033c45  push    rbp
0x140033c46  push    rsi
0x140033c47  push    rdi
0x140033c48  push    r12
0x140033c4a  push    r15
0x140033c4c  sub     rsp, 40h
0x140033c50  xor     eax, eax
0x140033c52  mov     rbx, rdx
0x140033c55  mov     r15d, eax
0x140033c58  mov     edi, eax
0x140033c5a  mov     r12, rcx
0x140033c5d  mov     ebp, 0FFFFh
0x140033c62  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033c69  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140033c70  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140033c77  jz      short loc_140033C94
0x140033c79  mov     rcx, cs:WPP_GLOBAL_Control
0x140033c80  cmp     byte ptr [rcx+29h], 5
0x140033c84  jnb     loc_140033E5F
0x140033c8a  cmp     [rcx+48h], ax
0x140033c8e  jnz     loc_140033E5F
0x140033c94  test    rbx, rbx
0x140033c97  jnz     short loc_140033CA5
0x140033c99  lea     rbx, WPP_RECORDER_INITIALIZED
0x140033ca0  jmp     loc_140033DF4
0x140033ca5  mov     [rsp+68h+arg_0], r13
0x140033caa  mov     [rsp+68h+arg_10], r14
0x140033cb2  nop     dword ptr [rax+00h]
0x140033cb6  nop     word ptr [rax+rax+00000000h]
0x140033cc0  mov     r13, [rbx+60h]
0x140033cc4  mov     r14, [rbx]
0x140033cc7  mov     [rbx], rax
0x140033cca  mov     [rbx+8Ch], eax
0x140033cd0  movzx   esi, word ptr [r13+20h]
0x140033cd5  cmp     bp, si
0x140033cd8  jnz     loc_140033E28
0x140033cde  mov     [rbx], r15
0x140033ce1  mov     r15, rbx
0x140033ce4  mov     rbx, r14
0x140033ce7  movzx   ebp, si
0x140033cea  test    r14, r14
0x140033ced  jnz     short loc_140033CC0
0x140033cef  mov     r14, [rsp+68h+arg_10]
0x140033cf7  mov     r13, [rsp+68h+arg_0]
0x140033cfc  test    r15, r15
0x140033cff  jz      loc_140033EAB
0x140033d05  test    rdi, rdi
0x140033d08  jz      loc_140033EAB
0x140033d0e  mov     [rsp+68h+arg_8], bl
0x140033d12  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033d19  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140033d20  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140033d27  jz      short loc_140033D6A
0x140033d29  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d30  cmp     byte ptr [rcx+29h], 5
0x140033d34  jnb     loc_140033EB7
0x140033d3a  cmp     word ptr [rcx+48h], 0
0x140033d3f  jnz     loc_140033EB7
0x140033d45  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140033d4c  jz      short loc_140033D6A
0x140033d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d55  cmp     byte ptr [rcx+29h], 5
0x140033d59  jnb     loc_140033F01
0x140033d5f  cmp     word ptr [rcx+48h], 0
0x140033d64  jnz     loc_140033F01
0x140033d6a  lea     r8, [rsp+68h+arg_8]; unsigned __int8 *
0x140033d6f  mov     rdx, r15; struct _NET_BUFFER_LIST *
0x140033d72  mov     rcx, rdi; this
0x140033d75  call    ?FreeTxWfcFrame@CPort@@AEAAHPEAU_NET_BUFFER_LIST@@PEAE@Z; CPort::FreeTxWfcFrame(_NET_BUFFER_LIST *,uchar *)
0x140033d7a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140033d81  jz      short loc_140033D9F
0x140033d83  mov     rcx, cs:WPP_GLOBAL_Control
0x140033d8a  cmp     byte ptr [rcx+29h], 5
0x140033d8e  jnb     loc_140033F29
0x140033d94  cmp     word ptr [rcx+48h], 0
0x140033d99  jnz     loc_140033F29
0x140033d9f  mov     rcx, [rdi+58h]
0x140033da3  xor     r8d, r8d; SendCompleteFlags
0x140033da6  mov     rdx, r15; NetBufferList
0x140033da9  mov     rcx, [rcx+58h]; MiniportAdapterHandle
0x140033dad  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140033db4  nop     dword ptr [rax+rax+00h]
0x140033db9  cmp     [rsp+68h+arg_8], 0
0x140033dbe  jz      short loc_140033DC8
0x140033dc0  mov     rcx, rdi; this
0x140033dc3  call    ?CompletePendingCancelSendsOrHaltJobs@CPort@@AEAAXXZ; CPort::CompletePendingCancelSendsOrHaltJobs(void)
0x140033dc8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140033dcf  jz      short loc_140033E11
0x140033dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140033dd8  cmp     byte ptr [rcx+29h], 5
0x140033ddc  jnb     loc_140033ED8
0x140033de2  cmp     word ptr [rcx+48h], 0
0x140033de7  jnz     loc_140033ED8
0x140033ded  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140033df4  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x140033dfb  jz      short loc_140033E11
0x140033dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140033e04  cmp     byte ptr [rcx+29h], 5
0x140033e08  jnb     short loc_140033E82
0x140033e0a  cmp     word ptr [rcx+48h], 0
0x140033e0f  jnz     short loc_140033E82
0x140033e11  mov     rbx, [rsp+68h+arg_18]
0x140033e19  xor     eax, eax
0x140033e1b  add     rsp, 40h
0x140033e1f  pop     r15
0x140033e21  pop     r12
0x140033e23  pop     rdi
0x140033e24  pop     rsi
0x140033e25  pop     rbp
0x140033e26  retn
0x140033e28  test    r15, r15
0x140033e2b  jnz     loc_140033F56
0x140033e31  mov     r15, rax
0x140033e34  mov     ecx, eax
0x140033e36  cmp     ecx, 5
0x140033e39  jnb     loc_140033F71
0x140033e3f  mov     eax, ecx
0x140033e41  mov     rdi, [r12+rax*8+1318h]
0x140033e49  test    rdi, rdi
0x140033e4c  jz      short loc_140033E5B
0x140033e4e  cmp     [rdi+64h], si
0x140033e52  jnz     short loc_140033E5B
0x140033e54  xor     eax, eax
0x140033e56  jmp     loc_140033CDE
0x140033e5b  inc     ecx
0x140033e5d  jmp     short loc_140033E36
0x140033e5f  mov     rcx, [rcx+40h]
0x140033e63  mov     r9d, 0A1h
0x140033e69  mov     r8d, 1
0x140033e6f  mov     [rsp+68h+var_48], rsi
0x140033e74  mov     dl, 5
0x140033e76  call    WPP_RECORDER_SF_
0x140033e7b  xor     eax, eax
0x140033e7d  jmp     loc_140033C94
0x140033e82  mov     rcx, [rcx+40h]
0x140033e86  mov     r9d, 0A3h
0x140033e8c  mov     dword ptr [rsp+68h+var_40], 0
0x140033e94  mov     r8d, 1
0x140033e9a  mov     dl, 5
0x140033e9c  mov     [rsp+68h+var_48], rsi
0x140033ea1  call    WPP_RECORDER_SF_D
0x140033ea6  jmp     loc_140033E11
0x140033eab  lea     rbx, WPP_RECORDER_INITIALIZED
0x140033eb2  jmp     loc_140033DED
0x140033eb7  mov     rcx, [rcx+40h]
0x140033ebb  mov     r9d, 66h ; 'f'
0x140033ec1  mov     r8d, 1
0x140033ec7  mov     [rsp+68h+var_48], rsi
0x140033ecc  mov     dl, 5
0x140033ece  call    WPP_RECORDER_SF_
0x140033ed3  jmp     loc_140033D45
0x140033ed8  mov     rcx, [rcx+40h]
0x140033edc  mov     r9d, 69h ; 'i'
0x140033ee2  mov     dword ptr [rsp+68h+var_40], 0
0x140033eea  mov     r8d, 1
0x140033ef0  mov     dl, 5
0x140033ef2  mov     [rsp+68h+var_48], rsi
0x140033ef7  call    WPP_RECORDER_SF_D
0x140033efc  jmp     loc_140033DED
0x140033f01  movzx   eax, word ptr [rdi+64h]
0x140033f05  mov     r9d, 67h ; 'g'
0x140033f0b  mov     rcx, [rcx+40h]
0x140033f0f  mov     dl, 5
0x140033f11  mov     dword ptr [rsp+68h+var_38], eax
0x140033f15  mov     [rsp+68h+var_40], rdi
0x140033f1a  mov     [rsp+68h+var_48], rsi
0x140033f1f  call    WPP_RECORDER_SF_qD
0x140033f24  jmp     loc_140033D6A
0x140033f29  movzx   eax, word ptr [rdi+64h]
0x140033f2d  mov     r9d, 68h ; 'h'
0x140033f33  mov     rcx, [rcx+40h]
0x140033f37  mov     dl, 5
0x140033f39  mov     [rsp+68h+var_30], r15
0x140033f3e  mov     dword ptr [rsp+68h+var_38], eax
0x140033f42  mov     [rsp+68h+var_40], rdi
0x140033f47  mov     [rsp+68h+var_48], rsi
0x140033f4c  call    WPP_RECORDER_SF_qDq
0x140033f51  jmp     loc_140033D9F
0x140033f56  test    rdi, rdi
0x140033f59  jz      loc_140033E31
0x140033f5f  mov     rdx, r15; struct _NET_BUFFER_LIST *
0x140033f62  mov     rcx, rdi; this
0x140033f65  call    ?SendCompleteNetBufferLists@CPort@@QEAAXPEAU_NET_BUFFER_LIST@@@Z; CPort::SendCompleteNetBufferLists(_NET_BUFFER_LIST *)
0x140033f6a  xor     eax, eax
0x140033f6c  jmp     loc_140033E31
0x140033f71  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033f78  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033f7f  jz      short loc_140033F9F
0x140033f81  mov     rcx, cs:WPP_GLOBAL_Control
0x140033f88  mov     [rsp+68h+var_30], r13
0x140033f8d  mov     [rsp+68h+var_38], rbx
0x140033f92  mov     dword ptr [rsp+68h+var_40], esi
0x140033f96  mov     rcx, [rcx+40h]
0x140033f9a  call    WPP_RECORDER_SF_Dqq
0x140033f9f  xor     eax, eax
0x140033fa1  mov     edi, eax
0x140033fa3  jmp     loc_140033CDE
```
