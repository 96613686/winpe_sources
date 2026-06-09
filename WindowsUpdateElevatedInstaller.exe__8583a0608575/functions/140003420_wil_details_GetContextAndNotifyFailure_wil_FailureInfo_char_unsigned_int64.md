# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003420`
- end: `0x140003627`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003420`
- `0x140003b1c`
- `0x140003c00`
- `0x140004478`
- `0x140004970`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000344a`
- `KERNEL32!GetCurrentThreadId` at `0x14000350c`
- `KERNEL32!GetCurrentThreadId` at `0x14000344a`
- `KERNEL32!GetCurrentThreadId` at `0x14000350c`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x140003420  push    rbx
0x140003422  push    rbp
0x140003423  push    rsi
0x140003424  push    rdi
0x140003425  push    r14
0x140003427  sub     rsp, 20h
0x14000342b  mov     r14, r8
0x14000342e  mov     rsi, rdx
0x140003431  mov     rdi, rcx
0x140003434  mov     byte ptr [rdx], 0
0x140003437  xor     bpl, bpl
0x14000343a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003441  test    rbx, rbx
0x140003444  jz      loc_1400034E0
0x14000344a  call    cs:__imp_GetCurrentThreadId
0x140003450  mov     r9d, eax
0x140003453  mov     r8d, eax
0x140003456  shr     r8, 2
0x14000345a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003464  mul     r8
0x140003467  shr     rdx, 3
0x14000346b  lea     rcx, [rdx+rdx*4]
0x14000346f  add     rcx, rcx
0x140003472  sub     r8, rcx
0x140003475  mov     rbx, [rbx+r8*8]
0x140003479  jmp     short loc_140003484
0x14000347b  cmp     [rbx], r9d
0x14000347e  jz      short loc_1400034FB
0x140003480  mov     rbx, [rbx+8]
0x140003484  test    rbx, rbx
0x140003487  jnz     short loc_14000347B
0x140003489  test    rbx, rbx
0x14000348c  jz      short loc_1400034E0
0x14000348e  cmp     qword ptr [rbx], 0
0x140003492  jz      short loc_1400034E0
0x140003494  mov     [rsi], bpl
0x140003497  mov     r9, r14; unsigned __int64
0x14000349a  mov     r8, rsi; char *
0x14000349d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400034a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400034a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400034a8  test    al, al
0x1400034aa  jz      short loc_1400034B0
0x1400034ac  mov     [rdi+48h], rsi
0x1400034b0  mov     rbx, [rbx]
0x1400034b3  mov     al, [rbx+28h]
0x1400034b6  mov     byte ptr [rbx+28h], 1
0x1400034ba  test    al, al
0x1400034bc  jnz     short loc_1400034D7
0x1400034be  mov     rcx, [rbx+8]
0x1400034c2  mov     rax, [rcx]
0x1400034c5  mov     rdx, rdi
0x1400034c8  mov     rax, [rax]
0x1400034cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034d0  or      bpl, al
0x1400034d3  mov     byte ptr [rbx+28h], 0
0x1400034d7  mov     rbx, [rbx+10h]
0x1400034db  test    rbx, rbx
0x1400034de  jnz     short loc_1400034B3
0x1400034e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400034e7  test    rax, rax
0x1400034ea  jz      short loc_14000350C
0x1400034ec  test    bpl, bpl
0x1400034ef  jnz     short loc_140003501
0x1400034f1  test    byte ptr [rdi+4], 2
0x1400034f5  jnz     short loc_140003501
0x1400034f7  xor     ecx, ecx
0x1400034f9  jmp     short loc_140003503
0x1400034fb  add     rbx, 10h
0x1400034ff  jmp     short loc_140003489
0x140003501  mov     cl, 1
0x140003503  mov     rdx, rdi
0x140003506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000350b  nop
0x14000350c  call    cs:__imp_GetCurrentThreadId
0x140003512  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003518  cmp     ecx, eax
0x14000351a  jz      loc_14000361C
0x140003520  mov     ecx, 1
0x140003525  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000352d  inc     ecx; this
0x14000352f  cmp     ecx, 4
0x140003532  jge     loc_140003615
0x140003538  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000353e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003543  mov     rbx, rax
0x140003546  test    rax, rax
0x140003549  jz      loc_14000360B
0x14000354f  mov     esi, [rax+10h]
0x140003552  mov     ebp, 50h ; 'P'
0x140003557  cmp     qword ptr [rax+18h], 0
0x14000355c  jnz     short loc_140003593
0x14000355e  test    esi, esi
0x140003560  jz      short loc_140003593
0x140003562  mov     edx, 190h; dwBytes
0x140003567  lea     ecx, [rbp-48h]; dwFlags
0x14000356a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000356f  mov     [rbx+18h], rax
0x140003573  test    rax, rax
0x140003576  jz      short loc_140003593
0x140003578  mov     dword ptr [rbx+20h], 5
0x14000357f  lea     rcx, [rax+190h]
0x140003586  jmp     short loc_14000358E
0x140003588  mov     [rax], bp
0x14000358b  add     rax, rbp
0x14000358e  cmp     rax, rcx
0x140003591  jnz     short loc_140003588
0x140003593  mov     r9, [rbx+18h]
0x140003597  test    r9, r9
0x14000359a  jz      short loc_14000360B
0x14000359c  test    esi, esi
0x14000359e  jz      short loc_1400035D1
0x1400035a0  mov     rcx, r9
0x1400035a3  movzx   eax, word ptr [rbx+20h]
0x1400035a7  lea     rdx, [rax+rax*4]
0x1400035ab  shl     rdx, 4
0x1400035af  add     rdx, r9
0x1400035b2  cmp     r9, rdx
0x1400035b5  jz      short loc_1400035D1
0x1400035b7  mov     r8d, [rbx+10h]
0x1400035bb  cmp     [rcx+4], r8d
0x1400035bf  jbe     short loc_1400035C9
0x1400035c1  mov     eax, [rdi+8]
0x1400035c4  cmp     [rcx+8], eax
0x1400035c7  jz      short loc_14000360B
0x1400035c9  add     rcx, rbp
0x1400035cc  cmp     rcx, rdx
0x1400035cf  jnz     short loc_1400035BB
0x1400035d1  movzx   eax, word ptr [rbx+22h]
0x1400035d5  inc     eax
0x1400035d7  movzx   ecx, word ptr [rbx+20h]
0x1400035db  xor     edx, edx
0x1400035dd  div     ecx
0x1400035df  mov     [rbx+22h], dx
0x1400035e3  mov     rax, [rbx+8]
0x1400035e7  mov     r8d, 1
0x1400035ed  lock xadd [rax], r8d
0x1400035f2  inc     r8d; unsigned int
0x1400035f5  movzx   eax, dx
0x1400035f8  lea     rcx, [rax+rax*4]
0x1400035fc  shl     rcx, 4
0x140003600  add     rcx, r9; this
0x140003603  mov     rdx, rdi; struct wil::FailureInfo *
0x140003606  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000360b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003615  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000361c  add     rsp, 20h
0x140003620  pop     r14
0x140003622  pop     rdi
0x140003623  pop     rsi
0x140003624  pop     rbp
0x140003625  pop     rbx
0x140003626  retn
```
