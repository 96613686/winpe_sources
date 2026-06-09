# CTxMgr::CompleteNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *,bool)

- ea: `0x14003a200`
- end: `0x14003a309`
- name: `?CompleteNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0_N@Z`
- size: `265`
- prototype: `void __fastcall(PVOID WorkItemContext, struct _NET_BUFFER_LIST *, struct _NET_BUFFER_LIST *, bool)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003b888`
- `0x140058f84`
- `0x140064cfc`
- `0x140085278`
- `0x14009ce88`
- `0x14009cfa4`

## callees

- `0x140034e04`
- `0x140039a60`
- `0x14003a200`
- `0x14003b320`
- `0x14003b340`
- `0x14003ea84`
- `0x1400867b8`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x14003a27a`
- `NDIS!NdisSetEvent` at `0x14003a27a`

## pseudocode

```c
void __fastcall CTxMgr::CompleteNBLs(
        CTxMgr *WorkItemContext,
        struct _NET_BUFFER_LIST *a2,
        struct _NET_BUFFER_LIST *a3,
        unsigned __int8 a4)
{
  signed __int32 m_RefVal; // eax
  signed __int32 v8; // ett
  int v9; // edx
  struct _NET_BUFFER_LIST *v10; // r8
  struct _NET_BUFFER_LIST *v11; // r10

  m_RefVal = WorkItemContext->m_InlineCompletionRundown.m_RefVal;
  while ( (m_RefVal & 1) == 0 )
  {
    v8 = m_RefVal;
    m_RefVal = _InterlockedCompareExchange(&WorkItemContext->m_InlineCompletionRundown.m_RefVal, m_RefVal + 2, m_RefVal);
    if ( v8 == m_RefVal )
    {
      if ( a2 )
        CTxMgr::CompleteIhvNbl(WorkItemContext, a2);
      if ( a3 )
        CTxMgr::CompleteNdisNbl((char *)WorkItemContext, a3, a4);
      if ( (!a4 || !a3)
        && _InterlockedExchangeAdd(&WorkItemContext->m_InlineCompletionRundown.m_RefVal, 0xFFFFFFFE) == 3 )
      {
        NdisSetEvent(&WorkItemContext->m_InlineCompletionRundown.m_NdisEvent);
      }
      return;
    }
  }
  if ( CDispatchRundown::Acquire(&WorkItemContext->m_DivertCompletionRundown) )
  {
    CTxMgr::DivertNBLs(WorkItemContext, v11, v10);
    CDispatchRundown::Release(&WorkItemContext->m_DivertCompletionRundown);
  }
  else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      350,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
}

```

## disassembly

```asm
0x14003a200  mov     [rsp+arg_0], rbx
0x14003a205  mov     [rsp+arg_8], rsi
0x14003a20a  push    rdi
0x14003a20b  sub     rsp, 30h
0x14003a20f  mov     eax, [rcx+70h]
0x14003a212  movzx   esi, r9b
0x14003a216  mov     rdi, r8
0x14003a219  mov     r10, rdx
0x14003a21c  mov     rbx, rcx
0x14003a21f  test    al, 1
0x14003a221  jnz     short loc_14003A288
0x14003a223  lea     r9d, [rax+2]
0x14003a227  lock cmpxchg [rcx+70h], r9d
0x14003a22d  jnz     short loc_14003A21F
0x14003a22f  test    r10, r10
0x14003a232  jnz     loc_14003A2FF
0x14003a238  test    rdi, rdi
0x14003a23b  jz      short loc_14003A24C
0x14003a23d  movzx   r8d, sil; unsigned __int8
0x14003a241  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x14003a244  mov     rcx, rbx; WorkItemContext
0x14003a247  call    ?CompleteNdisNbl@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@E@Z; CTxMgr::CompleteNdisNbl(_NET_BUFFER_LIST *,uchar)
0x14003a24c  test    sil, sil
0x14003a24f  jz      short loc_14003A267
0x14003a251  test    rdi, rdi
0x14003a254  jz      short loc_14003A267
0x14003a256  mov     rbx, [rsp+38h+arg_0]
0x14003a25b  mov     rsi, [rsp+38h+arg_8]
0x14003a260  add     rsp, 30h
0x14003a264  pop     rdi
0x14003a265  retn
0x14003a267  mov     eax, 0FFFFFFFEh
0x14003a26c  lock xadd [rbx+70h], eax
0x14003a271  cmp     eax, 3
0x14003a274  jnz     short loc_14003A256
0x14003a276  lea     rcx, [rbx+78h]; Event
0x14003a27a  call    cs:__imp_NdisSetEvent
0x14003a281  nop     dword ptr [rax+rax+00h]
0x14003a286  jmp     short loc_14003A256
0x14003a288  add     rcx, 90h; this
0x14003a28f  call    ?Acquire@CDispatchRundown@@QEAA_NXZ; CDispatchRundown::Acquire(void)
0x14003a294  test    al, al
0x14003a296  jz      short loc_14003A2C0
0x14003a298  mov     rdx, r10; struct _NET_BUFFER_LIST *
0x14003a29b  mov     rcx, rbx; this
0x14003a29e  call    ?DivertNBLs@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@0@Z; CTxMgr::DivertNBLs(_NET_BUFFER_LIST *,_NET_BUFFER_LIST *)
0x14003a2a3  lea     rcx, [rbx+90h]; this
0x14003a2aa  call    ?Release@CDispatchRundown@@QEAAXXZ; CDispatchRundown::Release(void)
0x14003a2af  mov     rbx, [rsp+38h+arg_0]
0x14003a2b4  mov     rsi, [rsp+38h+arg_8]
0x14003a2b9  add     rsp, 30h
0x14003a2bd  pop     rdi
0x14003a2be  retn
0x14003a2c0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003a2c7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a2ce  jz      short loc_14003A256
0x14003a2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a2d7  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14003a2de  mov     r9d, 15Eh
0x14003a2e4  mov     [rsp+38h+var_18], rax
0x14003a2e9  mov     r8d, 1
0x14003a2ef  mov     dl, 2
0x14003a2f1  mov     rcx, [rcx+40h]
0x14003a2f5  call    WPP_RECORDER_SF_
0x14003a2fa  jmp     loc_14003A256
0x14003a2ff  call    ?CompleteIhvNbl@CTxMgr@@AEAAXPEAU_NET_BUFFER_LIST@@@Z; CTxMgr::CompleteIhvNbl(_NET_BUFFER_LIST *)
0x14003a304  jmp     loc_14003A238
```
