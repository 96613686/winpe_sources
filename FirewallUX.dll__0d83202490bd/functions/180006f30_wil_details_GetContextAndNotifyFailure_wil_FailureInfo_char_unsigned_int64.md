# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006f30`
- end: `0x180007137`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006f30`
- `0x180007b24`
- `0x180007c08`
- `0x18000877c`
- `0x180009634`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000701c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000701c`

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
0x180006f30  push    rbx
0x180006f32  push    rbp
0x180006f33  push    rsi
0x180006f34  push    rdi
0x180006f35  push    r14
0x180006f37  sub     rsp, 20h
0x180006f3b  mov     r14, r8
0x180006f3e  mov     rsi, rdx
0x180006f41  mov     rdi, rcx
0x180006f44  mov     byte ptr [rdx], 0
0x180006f47  xor     bpl, bpl
0x180006f4a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006f51  test    rbx, rbx
0x180006f54  jz      loc_180006FF0
0x180006f5a  call    cs:__imp_GetCurrentThreadId
0x180006f60  mov     r9d, eax
0x180006f63  mov     r8d, eax
0x180006f66  shr     r8, 2
0x180006f6a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006f74  mul     r8
0x180006f77  shr     rdx, 3
0x180006f7b  lea     rcx, [rdx+rdx*4]
0x180006f7f  add     rcx, rcx
0x180006f82  sub     r8, rcx
0x180006f85  mov     rbx, [rbx+r8*8]
0x180006f89  jmp     short loc_180006F94
0x180006f8b  cmp     [rbx], r9d
0x180006f8e  jz      short loc_18000700B
0x180006f90  mov     rbx, [rbx+8]
0x180006f94  test    rbx, rbx
0x180006f97  jnz     short loc_180006F8B
0x180006f99  test    rbx, rbx
0x180006f9c  jz      short loc_180006FF0
0x180006f9e  cmp     qword ptr [rbx], 0
0x180006fa2  jz      short loc_180006FF0
0x180006fa4  mov     [rsi], bpl
0x180006fa7  mov     r9, r14; unsigned __int64
0x180006faa  mov     r8, rsi; char *
0x180006fad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006fb0  mov     rcx, rdi; struct wil::FailureInfo *
0x180006fb3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006fb8  test    al, al
0x180006fba  jz      short loc_180006FC0
0x180006fbc  mov     [rdi+48h], rsi
0x180006fc0  mov     rbx, [rbx]
0x180006fc3  mov     al, [rbx+28h]
0x180006fc6  mov     byte ptr [rbx+28h], 1
0x180006fca  test    al, al
0x180006fcc  jnz     short loc_180006FE7
0x180006fce  mov     rcx, [rbx+8]
0x180006fd2  mov     rax, [rcx]
0x180006fd5  mov     rdx, rdi
0x180006fd8  mov     rax, [rax]
0x180006fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe0  or      bpl, al
0x180006fe3  mov     byte ptr [rbx+28h], 0
0x180006fe7  mov     rbx, [rbx+10h]
0x180006feb  test    rbx, rbx
0x180006fee  jnz     short loc_180006FC3
0x180006ff0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006ff7  test    rax, rax
0x180006ffa  jz      short loc_18000701C
0x180006ffc  test    bpl, bpl
0x180006fff  jnz     short loc_180007011
0x180007001  test    byte ptr [rdi+4], 2
0x180007005  jnz     short loc_180007011
0x180007007  xor     ecx, ecx
0x180007009  jmp     short loc_180007013
0x18000700b  add     rbx, 10h
0x18000700f  jmp     short loc_180006F99
0x180007011  mov     cl, 1
0x180007013  mov     rdx, rdi
0x180007016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701b  nop
0x18000701c  call    cs:__imp_GetCurrentThreadId
0x180007022  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007028  cmp     ecx, eax
0x18000702a  jz      loc_18000712C
0x180007030  mov     ecx, 1
0x180007035  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000703d  inc     ecx; this
0x18000703f  cmp     ecx, 4
0x180007042  jge     loc_180007125
0x180007048  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000704e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007053  mov     rbx, rax
0x180007056  test    rax, rax
0x180007059  jz      loc_18000711B
0x18000705f  mov     esi, [rax+10h]
0x180007062  mov     ebp, 50h ; 'P'
0x180007067  cmp     qword ptr [rax+18h], 0
0x18000706c  jnz     short loc_1800070A3
0x18000706e  test    esi, esi
0x180007070  jz      short loc_1800070A3
0x180007072  mov     edx, 190h; dwBytes
0x180007077  lea     ecx, [rbp-48h]; dwFlags
0x18000707a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000707f  mov     [rbx+18h], rax
0x180007083  test    rax, rax
0x180007086  jz      short loc_1800070A3
0x180007088  mov     dword ptr [rbx+20h], 5
0x18000708f  lea     rcx, [rax+190h]
0x180007096  jmp     short loc_18000709E
0x180007098  mov     [rax], bp
0x18000709b  add     rax, rbp
0x18000709e  cmp     rax, rcx
0x1800070a1  jnz     short loc_180007098
0x1800070a3  mov     r9, [rbx+18h]
0x1800070a7  test    r9, r9
0x1800070aa  jz      short loc_18000711B
0x1800070ac  test    esi, esi
0x1800070ae  jz      short loc_1800070E1
0x1800070b0  mov     rcx, r9
0x1800070b3  movzx   eax, word ptr [rbx+20h]
0x1800070b7  lea     rdx, [rax+rax*4]
0x1800070bb  shl     rdx, 4
0x1800070bf  add     rdx, r9
0x1800070c2  cmp     r9, rdx
0x1800070c5  jz      short loc_1800070E1
0x1800070c7  mov     r8d, [rbx+10h]
0x1800070cb  cmp     [rcx+4], r8d
0x1800070cf  jbe     short loc_1800070D9
0x1800070d1  mov     eax, [rdi+8]
0x1800070d4  cmp     [rcx+8], eax
0x1800070d7  jz      short loc_18000711B
0x1800070d9  add     rcx, rbp
0x1800070dc  cmp     rcx, rdx
0x1800070df  jnz     short loc_1800070CB
0x1800070e1  movzx   eax, word ptr [rbx+22h]
0x1800070e5  inc     eax
0x1800070e7  movzx   ecx, word ptr [rbx+20h]
0x1800070eb  xor     edx, edx
0x1800070ed  div     ecx
0x1800070ef  mov     [rbx+22h], dx
0x1800070f3  mov     rax, [rbx+8]
0x1800070f7  mov     r8d, 1
0x1800070fd  lock xadd [rax], r8d
0x180007102  inc     r8d; unsigned int
0x180007105  movzx   eax, dx
0x180007108  lea     rcx, [rax+rax*4]
0x18000710c  shl     rcx, 4
0x180007110  add     rcx, r9; this
0x180007113  mov     rdx, rdi; struct wil::FailureInfo *
0x180007116  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000711b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007125  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000712c  add     rsp, 20h
0x180007130  pop     r14
0x180007132  pop     rdi
0x180007133  pop     rsi
0x180007134  pop     rbp
0x180007135  pop     rbx
0x180007136  retn
```
