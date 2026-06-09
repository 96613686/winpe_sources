# ActiveJobsList::OnOperationCompleted(int,void *)

- ea: `0x140005b20`
- end: `0x140005eaa`
- name: `?OnOperationCompleted@ActiveJobsList@@UEAAXHPEAX@Z`
- size: `906`
- prototype: `void __fastcall(ActiveJobsList *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005b20`
- `0x140005eb0`
- `0x140005ec8`
- `0x1400067b0`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005ca8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ca8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c48`

## pseudocode

```c
void __fastcall ActiveJobsList::OnOperationCompleted(ActiveJobsList *this, ActiveJobsList *Flink, _QWORD *a3)
{
  int v4; // r14d
  int v6; // edi
  char *v7; // rbx
  ActiveJobsList_vtbl *v8; // rax
  ActiveJobsList_vtbl *v9; // rcx
  __int64 v10; // r8
  EventQueue *m_pEventQueue; // rdi
  CNdisSpinLock *m_pEventQueueLock; // rsi
  KIRQL v13; // al
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v15; // rax
  char v16; // bl
  KIRQL OldIrql; // dl
  __m128i si128; // xmm6
  __int64 i; // rsi
  _DWORD *CppObjectFromListEntry; // rax
  ActiveJobsList **v21; // rdx
  int v22; // r8d
  ActiveJobsList *v23; // r10
  int v24; // r11d
  __int64 j; // r9
  int v26; // ecx
  struct Event *v27; // [rsp+28h] [rbp-60h]
  __m128i v28; // [rsp+40h] [rbp-48h]
  int v29; // [rsp+A0h] [rbp+18h]

  v4 = (int)Flink;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(Flink) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Flink,
      1,
      15,
      (__int64)WPP_b165a5fed1903a28339a5652b438d090_Traceguids);
  }
  if ( !a3 )
  {
    v6 = -1073741436;
    goto LABEL_6;
  }
  v6 = 0;
  v7 = (char *)(a3 + 26);
  if ( a3 != (_QWORD *)-208LL )
  {
    v8 = (ActiveJobsList_vtbl *)(a3 + 53);
    v9 = (ActiveJobsList_vtbl *)a3[53];
    if ( (_QWORD *)v9[1].OnOperationCompleted == a3 + 53 )
    {
      Flink = (ActiveJobsList *)a3[54];
      if ( Flink->IOperationCompletionCallback::__vftable == v8 )
      {
        v10 = a3[56];
        Flink->IOperationCompletionCallback::__vftable = v9;
        v9[1].OnOperationCompleted = (void (__fastcall *)(struct ActiveJobsList *, int, void *))Flink;
        a3[54] = a3 + 53;
        v8->OnOperationCompleted = (void (__fastcall *)(struct ActiveJobsList *, int, void *))v8;
        m_pEventQueue = this->m_pEventQueue;
        if ( !m_pEventQueue )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(Flink) = 2;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)Flink,
              v10,
              10,
              (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
              (_BYTE)a3 - 48,
              *(_DWORD *)v7);
          }
          v29 = -1073741811;
          goto LABEL_20;
        }
        if ( *((_BYTE *)a3 + 253) )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(Flink) = 2;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)Flink,
              v10,
              11,
              (__int64)WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids,
              (_BYTE)a3 - 48,
              *(_DWORD *)v7);
          }
          v29 = -1073741436;
          goto LABEL_20;
        }
        *((_DWORD *)a3 + 56) = 1;
        a3[27] = m_pEventQueue;
        a3[30] = v10;
        a3[29] = a3;
        *((_DWORD *)a3 + 62) = v4;
        m_pEventQueueLock = m_pEventQueue->m_pEventQueueLock;
        v13 = KeAcquireSpinLockRaiseToDpc(&m_pEventQueueLock->m_SpinLock.SpinLock);
        m_pEventQueueLock->m_IsLocked = 1;
        m_pEventQueueLock->m_SpinLock.OldIrql = v13;
        v7[45] = 1;
        Blink = m_pEventQueue->m_EventQueue.Blink;
        if ( Blink->Flink == &m_pEventQueue->m_EventQueue )
        {
          v15 = (struct _LIST_ENTRY *)(v7 + 48);
          v16 = 0;
          v15->Flink = &m_pEventQueue->m_EventQueue;
          v15->Blink = Blink;
          Blink->Flink = v15;
          m_pEventQueue->m_EventQueue.Blink = v15;
          if ( !m_pEventQueue->m_IsBeingProcessed )
          {
            v16 = 1;
            m_pEventQueue->m_EventQueueThreadHandle = KeGetCurrentThread();
            m_pEventQueue->m_IsBeingProcessed = 1;
          }
          OldIrql = m_pEventQueueLock->m_SpinLock.OldIrql;
          m_pEventQueueLock->m_IsLocked = 0;
          KeReleaseSpinLock(&m_pEventQueueLock->m_SpinLock.SpinLock, OldIrql);
          if ( v16 )
            EventQueue::ProcessEventQueueUntilEmpty(m_pEventQueue);
          v29 = 0;
LABEL_20:
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          for ( i = 0; i != 5; ++i )
          {
            if ( this->m_ResetPortContext[i].IsResetPending )
            {
              Flink = (ActiveJobsList *)this->m_JobList.Flink;
              v28 = si128;
              if ( Flink == (ActiveJobsList *)&this->m_JobList )
                goto LABEL_29;
              do
              {
                CppObjectFromListEntry = GetCppObjectFromListEntry((struct _LIST_ENTRY *)Flink);
                if ( v24 == -1 || CppObjectFromListEntry[14] == v24 )
                {
                  for ( j = 0; j != 4; ++j )
                  {
                    v26 = v22 + 1;
                    if ( CppObjectFromListEntry[15] != v28.m128i_i32[j] )
                      v26 = v22;
                    v22 = v26;
                  }
                }
                Flink = *v21;
              }
              while ( Flink != v23 );
              if ( !v22 )
              {
LABEL_29:
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(Flink) = 4;
                  LODWORD(v27) = this->m_ResetPortContext[i].NdisPortNumber;
                  WPP_RECORDER_SF_D(
                    WPP_GLOBAL_Control->DeviceExtension,
                    (_DWORD)Flink,
                    1,
                    20,
                    (__int64)WPP_b165a5fed1903a28339a5652b438d090_Traceguids,
                    v27);
                }
                EventQueue::PopulateAndQueueDeferredCallback(
                  this->m_pEventQueue,
                  WiFiEventDeferredOperationCompletion,
                  (void *)this->m_ResetPortContext[i].pCompletionCallback,
                  0,
                  0,
                  0);
                this->m_ResetPortContext[i].IsResetPending = 0;
              }
            }
          }
          v6 = v29;
          goto LABEL_6;
        }
      }
    }
    __fastfail(3u);
  }
LABEL_6:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v27) = v6;
    LOBYTE(Flink) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Flink,
      1,
      16,
      (__int64)WPP_b165a5fed1903a28339a5652b438d090_Traceguids,
      v27);
  }
}

```

## disassembly

```asm
0x140005b20  mov     [rsp+arg_0], rbx
0x140005b25  mov     [rsp+arg_8], rbp
0x140005b2a  push    rsi
0x140005b2b  push    rdi
0x140005b2c  push    r13
0x140005b2e  push    r14
0x140005b30  push    r15
0x140005b32  sub     rsp, 60h
0x140005b36  movaps  [rsp+88h+var_38], xmm6
0x140005b3b  mov     rsi, r8
0x140005b3e  mov     r14d, edx
0x140005b41  mov     rbp, rcx
0x140005b44  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005b4b  xor     r15d, r15d
0x140005b4e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140005b55  lea     rbx, WPP_b165a5fed1903a28339a5652b438d090_Traceguids
0x140005b5c  jz      short loc_140005B7A
0x140005b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b65  cmp     byte ptr [rcx+29h], 5
0x140005b69  jnb     loc_140005E4D
0x140005b6f  cmp     [rcx+48h], r15w
0x140005b74  jnz     loc_140005E4D
0x140005b7a  test    rsi, rsi
0x140005b7d  jz      loc_140005E6C
0x140005b83  mov     edi, r15d
0x140005b86  lea     rbx, [rsi+0D0h]
0x140005b8d  test    rbx, rbx
0x140005b90  jnz     short loc_140005BDD
0x140005b92  lea     rbx, WPP_b165a5fed1903a28339a5652b438d090_Traceguids
0x140005b99  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140005ba0  jz      short loc_140005BBE
0x140005ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ba9  cmp     byte ptr [rcx+29h], 5
0x140005bad  jnb     loc_140005DC5
0x140005bb3  cmp     [rcx+48h], r15w
0x140005bb8  jnz     loc_140005DC5
0x140005bbe  movaps  xmm6, [rsp+88h+var_38]
0x140005bc3  lea     r11, [rsp+88h+var_28]
0x140005bc8  mov     rbx, [r11+30h]
0x140005bcc  mov     rbp, [r11+38h]
0x140005bd0  mov     rsp, r11
0x140005bd3  pop     r15
0x140005bd5  pop     r14
0x140005bd7  pop     r13
0x140005bd9  pop     rdi
0x140005bda  pop     rsi
0x140005bdb  retn
0x140005bdd  lea     rax, [rsi+1A8h]
0x140005be4  mov     rcx, [rax]
0x140005be7  cmp     [rcx+8], rax
0x140005beb  jnz     loc_140005DBE
0x140005bf1  mov     rdx, [rax+8]
0x140005bf5  cmp     [rdx], rax
0x140005bf8  jnz     loc_140005DBE
0x140005bfe  mov     r8, [rsi+1C0h]
0x140005c05  mov     [rdx], rcx
0x140005c08  mov     [rcx+8], rdx
0x140005c0c  mov     [rax+8], rax
0x140005c10  mov     [rax], rax
0x140005c13  mov     rdi, [rbp+10h]
0x140005c17  test    rdi, rdi
0x140005c1a  jz      loc_140005E05
0x140005c20  cmp     [rbx+2Dh], r15b
0x140005c24  jnz     loc_140005DE8
0x140005c2a  mov     dword ptr [rbx+10h], 1
0x140005c31  mov     [rbx+8], rdi
0x140005c35  mov     [rbx+20h], r8
0x140005c39  mov     [rbx+18h], rsi
0x140005c3d  mov     [rbx+28h], r14d
0x140005c41  mov     rsi, [rdi+20h]
0x140005c45  mov     rcx, rsi; SpinLock
0x140005c48  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c4f  nop     dword ptr [rax+rax+00h]
0x140005c54  mov     byte ptr [rsi+10h], 1
0x140005c58  lea     rcx, [rdi+40h]
0x140005c5c  mov     [rsi+8], al
0x140005c5f  mov     byte ptr [rbx+2Dh], 1
0x140005c63  mov     rdx, [rcx+8]
0x140005c67  cmp     [rdx], rcx
0x140005c6a  jnz     loc_140005DBE
0x140005c70  lea     rax, [rbx+30h]
0x140005c74  mov     bl, r15b
0x140005c77  mov     [rax], rcx
0x140005c7a  mov     [rax+8], rdx
0x140005c7e  mov     [rdx], rax
0x140005c81  mov     [rcx+8], rax
0x140005c85  cmp     [rdi+30h], r15b
0x140005c89  jnz     short loc_140005C9E
0x140005c8b  mov     rax, gs:188h
0x140005c94  mov     bl, 1
0x140005c96  mov     [rdi+50h], rax
0x140005c9a  mov     byte ptr [rdi+30h], 1
0x140005c9e  mov     dl, [rsi+8]; NewIrql
0x140005ca1  mov     rcx, rsi; SpinLock
0x140005ca4  mov     [rsi+10h], r15b
0x140005ca8  call    cs:__imp_KeReleaseSpinLock
0x140005caf  nop     dword ptr [rax+rax+00h]
0x140005cb4  test    bl, bl
0x140005cb6  jz      short loc_140005CC0
0x140005cb8  mov     rcx, rdi; this
0x140005cbb  call    ?ProcessEventQueueUntilEmpty@EventQueue@@IEAAXXZ; EventQueue::ProcessEventQueueUntilEmpty(void)
0x140005cc0  mov     [rsp+88h+arg_10], r15d
0x140005cc8  movdqa  xmm6, cs:__xmm@00000048000000a7000000a100000027
0x140005cd0  lea     rdi, WPP_b165a5fed1903a28339a5652b438d090_Traceguids
0x140005cd7  mov     rsi, r15
0x140005cda  lea     rbx, [rsi+3]
0x140005cde  add     rbx, rbx
0x140005ce1  cmp     byte ptr [rbp+rbx*8+0], 1
0x140005ce6  jz      short loc_140005CFD
0x140005ce8  inc     rsi
0x140005ceb  cmp     rsi, 5
0x140005cef  jnz     short loc_140005CDA
0x140005cf1  mov     edi, [rsp+88h+arg_10]
0x140005cf8  jmp     loc_140005B92
0x140005cfd  lea     r10, [rbp+20h]
0x140005d01  mov     rax, rsi
0x140005d04  mov     rdx, [r10]
0x140005d07  add     rax, rax
0x140005d0a  mov     r8d, r15d
0x140005d0d  movdqu  [rsp+88h+var_48], xmm6
0x140005d13  mov     r11d, [rbp+rax*8+34h]
0x140005d18  cmp     rdx, r10
0x140005d1b  jz      short loc_140005D3E
0x140005d1d  mov     rcx, rdx; struct _LIST_ENTRY *
0x140005d20  call    ?GetCppObjectFromListEntry@@YAPEAXPEAU_LIST_ENTRY@@@Z; GetCppObjectFromListEntry(_LIST_ENTRY *)
0x140005d25  cmp     r11d, 0FFFFFFFFh
0x140005d29  jz      short loc_140005D99
0x140005d2b  cmp     [rax+38h], r11d
0x140005d2f  jz      short loc_140005D99
0x140005d31  mov     rdx, [rdx]
0x140005d34  cmp     rdx, r10
0x140005d37  jnz     short loc_140005D1D
0x140005d39  test    r8d, r8d
0x140005d3c  jnz     short loc_140005CE8
0x140005d3e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140005d45  jz      short loc_140005D70
0x140005d47  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d4e  mov     r9d, 14h
0x140005d54  mov     eax, [rbp+rbx*8+4]
0x140005d58  mov     dl, 4
0x140005d5a  mov     dword ptr [rsp+88h+var_60], eax
0x140005d5e  mov     qword ptr [rsp+88h+var_68], rdi
0x140005d63  mov     rcx, [rcx+40h]
0x140005d67  lea     r8d, [r9-13h]
0x140005d6b  call    WPP_RECORDER_SF_D
0x140005d70  mov     r8, [rbp+rbx*8+8]; void *
0x140005d75  xor     r9d, r9d; void *
0x140005d78  mov     rcx, [rbp+10h]; this
0x140005d7c  mov     [rsp+88h+var_60], r15; struct Event *
0x140005d81  mov     [rsp+88h+var_68], r15d; int
0x140005d86  lea     edx, [r9+1]; enum _WFC_EVENT_TYPE
0x140005d8a  call    ?PopulateAndQueueDeferredCallback@EventQueue@@IEAAHW4_WFC_EVENT_TYPE@@PEAX1HPEAVEvent@@@Z; EventQueue::PopulateAndQueueDeferredCallback(_WFC_EVENT_TYPE,void *,void *,int,Event *)
0x140005d8f  mov     [rbp+rbx*8+0], r15b
0x140005d94  jmp     loc_140005CE8
0x140005d99  mov     r14d, [rax+3Ch]
0x140005d9d  mov     r9, r15
0x140005da0  cmp     r14d, dword ptr [rsp+r9*4+88h+var_48]
0x140005da5  lea     ecx, [r8+1]
0x140005da9  cmovnz  ecx, r8d
0x140005dad  inc     r9
0x140005db0  mov     r8d, ecx
0x140005db3  cmp     r9, 4
0x140005db7  jnz     short loc_140005DA0
0x140005db9  jmp     loc_140005D31
0x140005dbe  mov     ecx, 3
0x140005dc3  int     29h; Win8: RtlFailFast(ecx)
0x140005dc5  mov     rcx, [rcx+40h]
0x140005dc9  mov     r9d, 10h
0x140005dcf  mov     dword ptr [rsp+88h+var_60], edi
0x140005dd3  mov     dl, 5
0x140005dd5  mov     qword ptr [rsp+88h+var_68], rbx
0x140005dda  lea     r8d, [r9-0Fh]
0x140005dde  call    WPP_RECORDER_SF_D
0x140005de3  jmp     loc_140005BBE
0x140005de8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140005def  jnz     loc_140005E76
0x140005df5  mov     [rsp+88h+arg_10], 0C0000184h
0x140005e00  jmp     loc_140005CC8
0x140005e05  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140005e0c  jz      short loc_140005E3D
0x140005e0e  mov     eax, [rbx]
0x140005e10  mov     r9d, 0Ah
0x140005e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e1d  mov     dl, 2
0x140005e1f  mov     [rsp+88h+var_58], eax
0x140005e23  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140005e2a  mov     [rsp+88h+var_60], rbx
0x140005e2f  mov     qword ptr [rsp+88h+var_68], rax
0x140005e34  mov     rcx, [rcx+40h]
0x140005e38  call    WPP_RECORDER_SF_qD
0x140005e3d  mov     [rsp+88h+arg_10], 0C000000Dh
0x140005e48  jmp     loc_140005CC8
0x140005e4d  mov     rcx, [rcx+40h]
0x140005e51  mov     r9d, 0Fh
0x140005e57  mov     dl, 5
0x140005e59  mov     qword ptr [rsp+88h+var_68], rbx
0x140005e5e  lea     r8d, [r9-0Eh]
0x140005e62  call    WPP_RECORDER_SF_
0x140005e67  jmp     loc_140005B7A
0x140005e6c  mov     edi, 0C0000184h
0x140005e71  jmp     loc_140005B99
0x140005e76  mov     eax, [rbx]
0x140005e78  mov     r9d, 0Bh
0x140005e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e85  mov     dl, 2
0x140005e87  mov     [rsp+88h+var_58], eax
0x140005e8b  lea     rax, WPP_7830a616c67b3dfd0a49b337947532ed_Traceguids
0x140005e92  mov     [rsp+88h+var_60], rbx
0x140005e97  mov     qword ptr [rsp+88h+var_68], rax
0x140005e9c  mov     rcx, [rcx+40h]
0x140005ea0  call    WPP_RECORDER_SF_qD
0x140005ea5  jmp     loc_140005DF5
```
