# Broker::SystemEventsBrokerUserPresenceNotificationCallback(void *,ulong,void *)

- ea: `0x1800020c0`
- end: `0x18000229b`
- name: `?SystemEventsBrokerUserPresenceNotificationCallback@Broker@@YAKPEAXK0@Z`
- size: `475`
- prototype: `unsigned int __fastcall(Broker *__hidden this, void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800020c0`
- `0x180002680`
- `0x1800030e0`
- `0x180005a50`
- `0x1800060a0`
- `0x1800076a0`
- `0x180013aa0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002279`
- `ntdll!RtlFreeHeap` at `0x180002279`
- `ntdll!RtlAllocateHeap` at `0x1800021f3`
- `ntdll!RtlAllocateHeap` at `0x1800021f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002213`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002213`

## pseudocode

```c
__int64 __fastcall Broker::SystemEventsBrokerUserPresenceNotificationCallback(
        Broker *this,
        void *a2,
        __int64 a3,
        void *a4)
{
  _FILETIME *v6; // rdi
  _QWORD *v7; // rcx
  std::_Ref_count_base *v8; // rsi
  __int64 Instance; // rax
  Broker::SebBroker *v10; // rbp
  unsigned __int8 v11; // bl
  _OWORD *Heap; // rax
  int v13; // edx
  size_t Size; // [rsp+20h] [rbp-58h]
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v17; // [rsp+38h] [rbp-40h]
  _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    Instance = Broker::SebBroker::GetInstance(&v16);
    v10 = *(Broker::SebBroker **)Instance;
    v8 = *(std::_Ref_count_base **)(Instance + 8);
    *(_QWORD *)Instance = 0;
    *(_QWORD *)(Instance + 8) = 0;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v10 )
    {
      if ( *(_DWORD *)(a3 + 20) )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
            *((unsigned int *)this + 10));
        v11 = 0;
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
            *((unsigned int *)this + 10));
        v11 = 1;
      }
      Broker::SebBroker::OnSessionUserPresenceUpdate(v10, *((_DWORD *)this + 10), *(void **)this, v11);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1Bu);
      v6 = (_FILETIME *)Heap;
      if ( Heap )
      {
        *Heap = 0;
        *(_OWORD *)((char *)Heap + 11) = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v6[2] = SystemTimeAsFileTime;
        LOBYTE(v13) = v11;
        LODWORD(Size) = 27;
        PubSebLevelEvent(WNF_SEB_USER_PRESENCE_CHANGED, v13, *((_DWORD *)this + 10), (int)v6, Size);
      }
    }
    goto LABEL_22;
  }
  v8 = 0;
  if ( (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
  {
    WPP_SF_(v7[2], 45, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
LABEL_22:
    v7 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v7 + 28) & 0x10) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_(v7[2], 48, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  return 0;
}

```

## disassembly

```asm
0x1800020c0  mov     rax, rsp
0x1800020c3  push    rbx
0x1800020c4  push    rbp
0x1800020c5  push    rsi
0x1800020c6  push    rdi
0x1800020c7  push    r12
0x1800020c9  push    r14
0x1800020cb  sub     rsp, 48h
0x1800020cf  mov     rbx, r8
0x1800020d2  mov     qword ptr [rax+8], 0
0x1800020da  mov     r14, rcx
0x1800020dd  xor     edi, edi
0x1800020df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020e6  lea     r12, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800020ed  test    byte ptr [rcx+1Ch], 10h
0x1800020f1  jz      short loc_18000210F
0x1800020f3  cmp     byte ptr [rcx+19h], 4
0x1800020f7  jb      short loc_18000210F
0x1800020f9  mov     rcx, [rcx+10h]
0x1800020fd  lea     edx, [rdi+2Ch]
0x180002100  mov     r8, r12
0x180002103  call    WPP_SF_
0x180002108  mov     rcx, cs:WPP_GLOBAL_Control
0x18000210f  test    rbx, rbx
0x180002112  jnz     short loc_18000213F
0x180002114  xor     esi, esi
0x180002116  mov     bl, 1
0x180002118  test    [rcx+1Ch], bl
0x18000211b  jz      loc_180002245
0x180002121  cmp     byte ptr [rcx+19h], 2
0x180002125  jb      loc_180002245
0x18000212b  mov     rcx, [rcx+10h]
0x18000212f  lea     edx, [rsi+2Dh]
0x180002132  mov     r8, r12
0x180002135  call    WPP_SF_
0x18000213a  jmp     loc_18000223E
0x18000213f  lea     rcx, [rsp+78h+var_48]
0x180002144  call    ?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ; Broker::SebBroker::GetInstance(void)
0x180002149  mov     rbp, [rax]
0x18000214c  mov     rsi, [rax+8]
0x180002150  mov     [rax], rdi
0x180002153  mov     [rax+8], rdi
0x180002157  mov     rcx, [rsp+78h+var_40]; this
0x18000215c  test    rcx, rcx
0x18000215f  jz      short loc_180002166
0x180002161  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002166  test    rbp, rbp
0x180002169  jz      loc_18000223E
0x18000216f  cmp     [rbx+14h], edi
0x180002172  jnz     short loc_1800021A0
0x180002174  mov     rcx, cs:WPP_GLOBAL_Control
0x18000217b  test    byte ptr [rcx+1Ch], 10h
0x18000217f  jz      short loc_18000219C
0x180002181  cmp     byte ptr [rcx+19h], 4
0x180002185  jb      short loc_18000219C
0x180002187  mov     r9d, [r14+28h]
0x18000218b  mov     edx, 2Eh ; '.'
0x180002190  mov     rcx, [rcx+10h]
0x180002194  mov     r8, r12
0x180002197  call    WPP_SF_d
0x18000219c  mov     bl, 1
0x18000219e  jmp     short loc_1800021CA
0x1800021a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021a7  test    byte ptr [rcx+1Ch], 10h
0x1800021ab  jz      short loc_1800021C8
0x1800021ad  cmp     byte ptr [rcx+19h], 4
0x1800021b1  jb      short loc_1800021C8
0x1800021b3  mov     r9d, [r14+28h]
0x1800021b7  mov     edx, 2Fh ; '/'
0x1800021bc  mov     rcx, [rcx+10h]
0x1800021c0  mov     r8, r12
0x1800021c3  call    WPP_SF_d
0x1800021c8  xor     bl, bl
0x1800021ca  mov     r8, [r14]; void *
0x1800021cd  mov     r9b, bl; bool
0x1800021d0  mov     edx, [r14+28h]; unsigned int
0x1800021d4  mov     rcx, rbp; this
0x1800021d7  call    ?OnSessionUserPresenceUpdate@SebBroker@Broker@@QEAAXKPEAX_N@Z; Broker::SebBroker::OnSessionUserPresenceUpdate(ulong,void *,bool)
0x1800021dc  mov     rcx, gs:60h
0x1800021e5  mov     ebp, 1Bh
0x1800021ea  mov     r8d, ebp; Size
0x1800021ed  xor     edx, edx; Flags
0x1800021ef  mov     rcx, [rcx+30h]; HeapHandle
0x1800021f3  call    cs:__imp_RtlAllocateHeap
0x1800021f9  mov     rdi, rax
0x1800021fc  test    rax, rax
0x1800021ff  jz      short loc_18000223E
0x180002201  xorps   xmm0, xmm0
0x180002204  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000220c  movups  xmmword ptr [rax], xmm0
0x18000220f  movups  xmmword ptr [rax+0Bh], xmm0
0x180002213  call    cs:__imp_GetSystemTimeAsFileTime
0x180002219  mov     rcx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180002221  mov     r9, rdi; int
0x180002224  mov     [rdi+10h], rcx
0x180002228  mov     dl, bl; int
0x18000222a  mov     r8d, [r14+28h]; int
0x18000222e  mov     rcx, cs:WNF_SEB_USER_PRESENCE_CHANGED; int
0x180002235  mov     dword ptr [rsp+78h+Size], ebp; Size
0x180002239  call    PubSebLevelEvent
0x18000223e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002245  test    byte ptr [rcx+1Ch], 10h
0x180002249  jz      short loc_180002262
0x18000224b  cmp     byte ptr [rcx+19h], 4
0x18000224f  jb      short loc_180002262
0x180002251  mov     rcx, [rcx+10h]
0x180002255  mov     edx, 30h ; '0'
0x18000225a  mov     r8, r12
0x18000225d  call    WPP_SF_
0x180002262  test    rdi, rdi
0x180002265  jz      short loc_18000227F
0x180002267  mov     rcx, gs:60h
0x180002270  mov     r8, rdi; P
0x180002273  xor     edx, edx; Flags
0x180002275  mov     rcx, [rcx+30h]; HeapHandle
0x180002279  call    cs:__imp_RtlFreeHeap
0x18000227f  test    rsi, rsi
0x180002282  jz      short loc_18000228C
0x180002284  mov     rcx, rsi; this
0x180002287  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000228c  xor     eax, eax
0x18000228e  add     rsp, 48h
0x180002292  pop     r14
0x180002294  pop     r12
0x180002296  pop     rdi
0x180002297  pop     rsi
0x180002298  pop     rbp
0x180002299  pop     rbx
0x18000229a  retn
```
