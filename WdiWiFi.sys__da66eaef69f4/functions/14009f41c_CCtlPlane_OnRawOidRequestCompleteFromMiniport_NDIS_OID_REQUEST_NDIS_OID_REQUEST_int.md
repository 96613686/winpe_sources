# CCtlPlane::OnRawOidRequestCompleteFromMiniport(_NDIS_OID_REQUEST *,_NDIS_OID_REQUEST *,int)

- ea: `0x14009f41c`
- end: `0x14009f718`
- name: `?OnRawOidRequestCompleteFromMiniport@CCtlPlane@@AEAAXPEAU_NDIS_OID_REQUEST@@0H@Z`
- size: `764`
- prototype: `void __fastcall(CCtlPlane *__hidden this, struct _NDIS_OID_REQUEST *, struct _NDIS_OID_REQUEST *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001efc`
- `0x140001f30`
- `0x14009f1b0`

## callees

- `0x1400174e8`
- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x14009f41c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14009f5c1`
- `ntoskrnl!ExAllocatePool2` at `0x14009f5c1`

## pseudocode

```c
void __fastcall CCtlPlane::OnRawOidRequestCompleteFromMiniport(
        CCtlPlane *this,
        struct _NDIS_OID_REQUEST *a2,
        struct _NDIS_OID_REQUEST *a3,
        int a4)
{
  unsigned int m_PendingNonWdiOidTransactionId; // r15d
  struct _NDIS_OID_REQUEST *v6; // r14
  __int64 Pool2; // rax
  int v9; // edx
  _WFC_MESSAGE_METADATA *v10; // rbx
  int v11; // esi
  void *m_pCompletionContext; // rbp
  void (__fastcall *m_HungSendCmdCompletionRoutine)(void *, unsigned int, _WFC_MESSAGE_METADATA *, IWdiMessageMemoryManager *); // rax
  void (__fastcall *m_SendCmdCompletionRoutine)(void *, unsigned int, _WFC_MESSAGE_METADATA *, IWdiMessageMemoryManager *); // rax
  __int64 v15; // [rsp+28h] [rbp-50h]

  m_PendingNonWdiOidTransactionId = this->m_PendingNonWdiOidTransactionId;
  v6 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        42,
        (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        43,
        (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
        v6->DATA.Oid,
        a4);
    }
  }
  this->m_bRequestPending = 0;
  this->m_PendingNonWdiOidTransactionId = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      LODWORD(v15) = v6->DATA.Oid;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        44,
        (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
        v15);
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(a2) = 5;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          (_DWORD)a3,
          45,
          (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
          v6->PortNumber);
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(a2) = 5;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            (_DWORD)a3,
            46,
            (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
            m_PendingNonWdiOidTransactionId);
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LODWORD(v15) = a4;
          LOBYTE(a2) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            1,
            47,
            (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
            v15);
        }
      }
    }
  }
  Pool2 = ExAllocatePool2(64, 48, 1198089303);
  v10 = (_WFC_MESSAGE_METADATA *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 8) &= 0xFFFFFFF8;
    v11 = 0;
    *(_DWORD *)(Pool2 + 12) = 3;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_DWORD *)(Pool2 + 20) = a4;
    *(_DWORD *)(Pool2 + 4) = 16;
    *(_DWORD *)(Pool2 + 40) = m_PendingNonWdiOidTransactionId;
    m_pCompletionContext = this->m_pCompletionContext;
    if ( v6 == this->m_pHungOidRequest )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v15) = v6->DATA.Oid;
        LOBYTE(v9) = 4;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          49,
          (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
          v15);
      }
      m_HungSendCmdCompletionRoutine = this->m_HungSendCmdCompletionRoutine;
      this->m_HungSendCmdCompletionRoutine = 0;
      m_HungSendCmdCompletionRoutine(m_pCompletionContext, 48u, v10, this);
    }
    else
    {
      m_SendCmdCompletionRoutine = this->m_SendCmdCompletionRoutine;
      this->m_SendCmdCompletionRoutine = 0;
      m_SendCmdCompletionRoutine(m_pCompletionContext, 48u, v10, this);
    }
  }
  else
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        48,
        (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids);
    }
    v11 = -1073741670;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v15) = v11;
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      50,
      (__int64)WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids,
      v15);
  }
}

```

## disassembly

```asm
0x14009f41c  push    rbx
0x14009f41e  push    rbp
0x14009f41f  push    rsi
0x14009f420  push    rdi
0x14009f421  push    r12
0x14009f423  push    r14
0x14009f425  push    r15
0x14009f427  sub     rsp, 40h
0x14009f42b  mov     r15d, [rcx+24h]
0x14009f42f  mov     ebp, r9d
0x14009f432  mov     r14, rdx
0x14009f435  mov     rdi, rcx
0x14009f438  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009f43f  xor     r12d, r12d
0x14009f442  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14009f449  lea     rbx, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x14009f450  jz      short loc_14009F4B6
0x14009f452  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f459  cmp     byte ptr [rcx+29h], 5
0x14009f45d  jnb     short loc_14009F466
0x14009f45f  cmp     [rcx+48h], r12w
0x14009f464  jz      short loc_14009F480
0x14009f466  mov     rcx, [rcx+40h]
0x14009f46a  mov     r9d, 2Ah ; '*'
0x14009f470  mov     dl, 5
0x14009f472  mov     [rsp+78h+var_58], rbx
0x14009f477  lea     r8d, [r9-29h]
0x14009f47b  call    WPP_RECORDER_SF_
0x14009f480  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14009f487  jz      short loc_14009F4B6
0x14009f489  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f490  mov     r9d, 2Bh ; '+'
0x14009f496  mov     eax, [r14+20h]
0x14009f49a  mov     dl, 4
0x14009f49c  mov     [rsp+78h+var_48], ebp
0x14009f4a0  mov     dword ptr [rsp+78h+var_50], eax
0x14009f4a4  mov     rcx, [rcx+40h]
0x14009f4a8  lea     r8d, [r9-2Ah]
0x14009f4ac  mov     [rsp+78h+var_58], rbx
0x14009f4b1  call    WPP_RECORDER_SF_DD
0x14009f4b6  mov     [rdi+20h], r12b
0x14009f4ba  mov     [rdi+24h], r12d
0x14009f4be  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14009f4c5  jz      loc_14009F5B3
0x14009f4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f4d2  cmp     byte ptr [rcx+29h], 5
0x14009f4d6  jnb     short loc_14009F4DF
0x14009f4d8  cmp     [rcx+48h], r12w
0x14009f4dd  jz      short loc_14009F501
0x14009f4df  mov     eax, [r14+20h]
0x14009f4e3  mov     r9d, 2Ch ; ','
0x14009f4e9  mov     rcx, [rcx+40h]
0x14009f4ed  mov     dl, 5
0x14009f4ef  mov     dword ptr [rsp+78h+var_50], eax
0x14009f4f3  mov     [rsp+78h+var_58], rbx
0x14009f4f8  lea     r8d, [r9-2Bh]
0x14009f4fc  call    WPP_RECORDER_SF_D
0x14009f501  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14009f508  jz      loc_14009F5B3
0x14009f50e  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f515  cmp     byte ptr [rcx+29h], 5
0x14009f519  jnb     short loc_14009F522
0x14009f51b  cmp     [rcx+48h], r12w
0x14009f520  jz      short loc_14009F540
0x14009f522  mov     eax, [r14+8]
0x14009f526  mov     r9d, 2Dh ; '-'
0x14009f52c  mov     rcx, [rcx+40h]
0x14009f530  mov     dl, 5
0x14009f532  mov     dword ptr [rsp+78h+var_50], eax
0x14009f536  mov     [rsp+78h+var_58], rbx
0x14009f53b  call    WPP_RECORDER_SF_d
0x14009f540  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14009f547  jz      short loc_14009F5B3
0x14009f549  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f550  cmp     byte ptr [rcx+29h], 5
0x14009f554  jnb     short loc_14009F55D
0x14009f556  cmp     [rcx+48h], r12w
0x14009f55b  jz      short loc_14009F578
0x14009f55d  mov     rcx, [rcx+40h]
0x14009f561  mov     r9d, 2Eh ; '.'
0x14009f567  mov     dword ptr [rsp+78h+var_50], r15d
0x14009f56c  mov     dl, 5
0x14009f56e  mov     [rsp+78h+var_58], rbx
0x14009f573  call    WPP_RECORDER_SF_d
0x14009f578  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14009f57f  jz      short loc_14009F5B3
0x14009f581  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f588  cmp     byte ptr [rcx+29h], 5
0x14009f58c  jnb     short loc_14009F595
0x14009f58e  cmp     [rcx+48h], r12w
0x14009f593  jz      short loc_14009F5B3
0x14009f595  mov     rcx, [rcx+40h]
0x14009f599  mov     r9d, 2Fh ; '/'
0x14009f59f  mov     dword ptr [rsp+78h+var_50], ebp
0x14009f5a3  mov     dl, 5
0x14009f5a5  mov     [rsp+78h+var_58], rbx
0x14009f5aa  lea     r8d, [r9-2Eh]
0x14009f5ae  call    WPP_RECORDER_SF_D
0x14009f5b3  mov     edx, 30h ; '0'
0x14009f5b8  mov     r8d, 47696457h
0x14009f5be  lea     ecx, [rdx+10h]
0x14009f5c1  call    cs:__imp_ExAllocatePool2
0x14009f5c8  nop     dword ptr [rax+rax+00h]
0x14009f5cd  mov     rbx, rax
0x14009f5d0  test    rax, rax
0x14009f5d3  jnz     short loc_14009F615
0x14009f5d5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14009f5dc  lea     r14, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x14009f5e3  jz      short loc_14009F604
0x14009f5e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f5ec  lea     r9d, [rax+30h]
0x14009f5f0  lea     r8d, [rax+1]
0x14009f5f4  mov     [rsp+78h+var_58], r14
0x14009f5f9  mov     dl, 2
0x14009f5fb  mov     rcx, [rcx+40h]
0x14009f5ff  call    WPP_RECORDER_SF_
0x14009f604  mov     esi, 0C000009Ah
0x14009f609  lea     r15, WPP_RECORDER_INITIALIZED
0x14009f610  jmp     loc_14009F6CD
0x14009f615  and     dword ptr [rax+8], 0FFFFFFF8h
0x14009f619  mov     esi, r12d
0x14009f61c  mov     dword ptr [rax+0Ch], 3
0x14009f623  mov     [rax+18h], r12
0x14009f627  mov     [rax+14h], ebp
0x14009f62a  mov     dword ptr [rax+4], 10h
0x14009f631  mov     [rax+28h], r15d
0x14009f635  mov     rbp, [rdi+228h]
0x14009f63c  cmp     r14, [rdi+280h]
0x14009f643  jnz     short loc_14009F69E
0x14009f645  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009f64c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009f653  jz      short loc_14009F687
0x14009f655  mov     eax, [r14+20h]
0x14009f659  mov     r9d, 31h ; '1'
0x14009f65f  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f666  lea     r14, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x14009f66d  mov     dword ptr [rsp+78h+var_50], eax
0x14009f671  mov     dl, 4
0x14009f673  mov     [rsp+78h+var_58], r14
0x14009f678  lea     r8d, [r9-30h]
0x14009f67c  mov     rcx, [rcx+40h]
0x14009f680  call    WPP_RECORDER_SF_D
0x14009f685  jmp     short loc_14009F68E
0x14009f687  lea     r14, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x14009f68e  mov     rax, [rdi+288h]
0x14009f695  mov     [rdi+288h], r12
0x14009f69c  jmp     short loc_14009F6BA
0x14009f69e  mov     rax, [rdi+230h]
0x14009f6a5  lea     r15, WPP_RECORDER_INITIALIZED
0x14009f6ac  mov     [rdi+230h], r12
0x14009f6b3  lea     r14, WPP_f45970a6f4eb33a4b42e51fcb0cc11db_Traceguids
0x14009f6ba  mov     r9, rdi
0x14009f6bd  mov     r8, rbx
0x14009f6c0  mov     edx, 30h ; '0'
0x14009f6c5  mov     rcx, rbp
0x14009f6c8  call    _guard_dispatch_icall
0x14009f6cd  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14009f6d4  jz      short loc_14009F708
0x14009f6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14009f6dd  cmp     byte ptr [rcx+29h], 5
0x14009f6e1  jnb     short loc_14009F6EA
0x14009f6e3  cmp     [rcx+48h], r12w
0x14009f6e8  jz      short loc_14009F708
0x14009f6ea  mov     rcx, [rcx+40h]
0x14009f6ee  mov     r9d, 32h ; '2'
0x14009f6f4  mov     dword ptr [rsp+78h+var_50], esi
0x14009f6f8  mov     dl, 5
0x14009f6fa  mov     [rsp+78h+var_58], r14
0x14009f6ff  lea     r8d, [r9-31h]
0x14009f703  call    WPP_RECORDER_SF_D
0x14009f708  add     rsp, 40h
0x14009f70c  pop     r15
0x14009f70e  pop     r14
0x14009f710  pop     r12
0x14009f712  pop     rdi
0x14009f713  pop     rsi
0x14009f714  pop     rbp
0x14009f715  pop     rbx
0x14009f716  retn
```
