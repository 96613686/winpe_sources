# EdgeTransaction::OnINetCallback(int)

- ea: `0x180054430`
- end: `0x1800545fc`
- name: `?OnINetCallback@EdgeTransaction@@UEAAJH@Z`
- size: `460`
- prototype: `__int64 __fastcall(EdgeTransaction *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180053950`
- `0x180054430`
- `0x180054610`
- `0x18005481c`
- `0x1800e9320`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800544fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054550`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800545a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800544fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054550`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800545a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005446c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800544ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005453c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005446c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800544ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005453c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005457a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005457a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054583`

## pseudocode

```c
__int64 __fastcall EdgeTransaction::OnINetCallback(EdgeTransaction *this, int a2)
{
  unsigned int v2; // r14d
  int v4; // edi
  int v5; // r12d
  int v6; // r15d
  struct CTransPacket *NextCTransPacket; // rax
  struct CTransPacket *v8; // rbp
  void *v9; // rcx
  __int64 v11; // rcx

  v2 = 0;
  if ( a2 )
    _InterlockedDecrement((volatile signed __int32 *)this + 107);
  if ( *((_DWORD *)this + 94) == GetCurrentThreadId() )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
    v4 = *((_DWORD *)this + 94);
    if ( v4 == GetCurrentThreadId()
      && (*((_BYTE *)this + 440) & 4) == 0
      && (unsigned int)CTransaction::GotCTransPacket(this) )
    {
      *((_BYTE *)this + 440) |= 4u;
      v5 = *((_DWORD *)this + 108);
      if ( (v5 & 0xFFFFFFFD) != 0 )
        goto LABEL_21;
      v6 = 1;
      do
      {
        NextCTransPacket = CTransaction::GetNextCTransPacket(this);
        v8 = NextCTransPacket;
        if ( !NextCTransPacket )
          break;
        if ( *((_DWORD *)NextCTransPacket + 13) == 59 )
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 107);
          v11 = *((_QWORD *)this + 39);
          if ( v11 )
            (*(void (__fastcall **)(__int64, struct CTransPacket *))(*(_QWORD *)v11 + 32LL))(v11, NextCTransPacket);
        }
        else
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
          *((_QWORD *)this + 50) = v8;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
          v2 = CTransaction::DispatchReport(
                 this,
                 *((_DWORD *)v8 + 13),
                 *((_DWORD *)this + 95),
                 *((_DWORD *)v8 + 6),
                 *((_DWORD *)v8 + 7),
                 *((LPCWSTR *)v8 + 5),
                 *((_DWORD *)v8 + 8),
                 *((_DWORD *)v8 + 12));
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
          *((_QWORD *)this + 50) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
        }
        if ( !v5 && *((_DWORD *)this + 108) == 1 )
          v6 = 0;
        if ( v2 == -2146697192 )
        {
          CTransaction::SuspendDispatchingPackets(this, v8);
          v6 = 0;
        }
        v9 = (void *)*((_QWORD *)v8 + 5);
        if ( v9 )
          CoTaskMemFree(v9);
        CoTaskMemFree(v8);
      }
      while ( v6 );
      if ( v2 == -2146697192 )
        v2 = 0;
      else
LABEL_21:
        *((_BYTE *)this + 440) &= ~4u;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  }
  return v2;
}

```

## disassembly

```asm
0x180054430  push    rbx
0x180054432  push    rbp
0x180054433  push    rsi
0x180054434  push    rdi
0x180054435  push    r12
0x180054437  push    r14
0x180054439  push    r15
0x18005443b  sub     rsp, 40h
0x18005443f  xor     r14d, r14d
0x180054442  mov     rsi, rcx
0x180054445  test    edx, edx
0x180054447  jz      short loc_180054450
0x180054449  lock dec dword ptr [rcx+1ACh]
0x180054450  call    cs:__imp_GetCurrentThreadId
0x180054456  cmp     [rsi+178h], eax
0x18005445c  jnz     loc_1800545AB
0x180054462  lea     rbx, [rsi+298h]
0x180054469  mov     rcx, rbx; lpCriticalSection
0x18005446c  call    cs:__imp_EnterCriticalSection
0x180054472  mov     edi, [rsi+178h]
0x180054478  call    cs:__imp_GetCurrentThreadId
0x18005447e  cmp     edi, eax
0x180054480  jnz     loc_1800545A2
0x180054486  test    byte ptr [rsi+1B8h], 4
0x18005448d  jnz     loc_1800545A2
0x180054493  mov     rcx, rsi; this
0x180054496  call    ?GotCTransPacket@CTransaction@@QEAAHXZ; CTransaction::GotCTransPacket(void)
0x18005449b  test    eax, eax
0x18005449d  jz      loc_1800545A2
0x1800544a3  or      byte ptr [rsi+1B8h], 4
0x1800544aa  mov     r12d, [rsi+1B0h]
0x1800544b1  test    r12d, 0FFFFFFFDh
0x1800544b8  jnz     loc_18005459B
0x1800544be  mov     r15d, 1
0x1800544c4  mov     rcx, rsi; this
0x1800544c7  call    ?GetNextCTransPacket@CTransaction@@QEAAPEAVCTransPacket@@XZ; CTransaction::GetNextCTransPacket(void)
0x1800544cc  mov     rbp, rax
0x1800544cf  test    rax, rax
0x1800544d2  jz      loc_180054592
0x1800544d8  cmp     dword ptr [rax+34h], 3Bh ; ';'
0x1800544dc  jz      loc_1800545BD
0x1800544e2  lea     rdi, [rsi+220h]
0x1800544e9  mov     rcx, rdi; lpCriticalSection
0x1800544ec  call    cs:__imp_EnterCriticalSection
0x1800544f2  mov     rcx, rdi; lpCriticalSection
0x1800544f5  mov     [rsi+190h], rbp
0x1800544fc  call    cs:__imp_LeaveCriticalSection
0x180054502  mov     eax, [rbp+30h]
0x180054505  mov     rcx, rsi; this
0x180054508  mov     r9d, [rbp+18h]; unsigned int
0x18005450c  mov     r8d, [rsi+17Ch]; unsigned int
0x180054513  mov     edx, [rbp+34h]; enum tagBINDSTATUS
0x180054516  mov     [rsp+78h+var_40], eax; int
0x18005451a  mov     eax, [rbp+20h]
0x18005451d  mov     [rsp+78h+var_48], eax; unsigned int
0x180054521  mov     rax, [rbp+28h]
0x180054525  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x18005452a  mov     eax, [rbp+1Ch]
0x18005452d  mov     [rsp+78h+var_58], eax; unsigned int
0x180054531  call    ?DispatchReport@CTransaction@@QEAAJW4tagBINDSTATUS@@KKKPEBGKJ@Z; CTransaction::DispatchReport(tagBINDSTATUS,ulong,ulong,ulong,ushort const *,ulong,long)
0x180054536  mov     rcx, rdi; lpCriticalSection
0x180054539  mov     r14d, eax
0x18005453c  call    cs:__imp_EnterCriticalSection
0x180054542  mov     rcx, rdi; lpCriticalSection
0x180054545  mov     qword ptr [rsi+190h], 0
0x180054550  call    cs:__imp_LeaveCriticalSection
0x180054556  test    r12d, r12d
0x180054559  jnz     short loc_180054568
0x18005455b  xor     eax, eax
0x18005455d  cmp     dword ptr [rsi+1B0h], 1
0x180054564  cmovz   r15d, eax
0x180054568  cmp     r14d, 800C0018h
0x18005456f  jz      short loc_1800545E9
0x180054571  mov     rcx, [rbp+28h]; pv
0x180054575  test    rcx, rcx
0x180054578  jz      short loc_180054580
0x18005457a  call    cs:__imp_CoTaskMemFree
0x180054580  mov     rcx, rbp; pv
0x180054583  call    cs:__imp_CoTaskMemFree
0x180054589  test    r15d, r15d
0x18005458c  jnz     loc_1800544C4
0x180054592  cmp     r14d, 800C0018h
0x180054599  jz      short loc_1800545E4
0x18005459b  and     byte ptr [rsi+1B8h], 0FBh
0x1800545a2  mov     rcx, rbx; lpCriticalSection
0x1800545a5  call    cs:__imp_LeaveCriticalSection
0x1800545ab  mov     eax, r14d
0x1800545ae  add     rsp, 40h
0x1800545b2  pop     r15
0x1800545b4  pop     r14
0x1800545b6  pop     r12
0x1800545b8  pop     rdi
0x1800545b9  pop     rsi
0x1800545ba  pop     rbp
0x1800545bb  pop     rbx
0x1800545bc  retn
0x1800545bd  lock dec dword ptr [rsi+1ACh]
0x1800545c4  mov     rcx, [rsi+138h]
0x1800545cb  test    rcx, rcx
0x1800545ce  jz      short loc_180054556
0x1800545d0  mov     rax, [rcx]
0x1800545d3  mov     rdx, rbp
0x1800545d6  mov     rax, [rax+20h]
0x1800545da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545df  jmp     loc_180054556
0x1800545e4  xor     r14d, r14d
0x1800545e7  jmp     short loc_1800545A2
0x1800545e9  mov     rdx, rbp; struct CTransPacket *
0x1800545ec  mov     rcx, rsi; this
0x1800545ef  call    ?SuspendDispatchingPackets@CTransaction@@QEAAXPEAVCTransPacket@@@Z; CTransaction::SuspendDispatchingPackets(CTransPacket *)
0x1800545f4  xor     r15d, r15d
0x1800545f7  jmp     loc_180054571
```
