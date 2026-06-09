# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006ef0`
- end: `0x1800070f7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006ef0`
- `0x1800075ec`
- `0x1800076d0`
- `0x1800083fc`
- `0x180009810`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006ef0  push    rbx
0x180006ef2  push    rbp
0x180006ef3  push    rsi
0x180006ef4  push    rdi
0x180006ef5  push    r14
0x180006ef7  sub     rsp, 20h
0x180006efb  mov     r14, r8
0x180006efe  mov     rsi, rdx
0x180006f01  mov     rdi, rcx
0x180006f04  mov     byte ptr [rdx], 0
0x180006f07  xor     bpl, bpl
0x180006f0a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006f11  test    rbx, rbx
0x180006f14  jz      loc_180006FB0
0x180006f1a  call    cs:__imp_GetCurrentThreadId
0x180006f20  mov     r9d, eax
0x180006f23  mov     r8d, eax
0x180006f26  shr     r8, 2
0x180006f2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006f34  mul     r8
0x180006f37  shr     rdx, 3
0x180006f3b  lea     rcx, [rdx+rdx*4]
0x180006f3f  add     rcx, rcx
0x180006f42  sub     r8, rcx
0x180006f45  mov     rbx, [rbx+r8*8]
0x180006f49  jmp     short loc_180006F54
0x180006f4b  cmp     [rbx], r9d
0x180006f4e  jz      short loc_180006FCB
0x180006f50  mov     rbx, [rbx+8]
0x180006f54  test    rbx, rbx
0x180006f57  jnz     short loc_180006F4B
0x180006f59  test    rbx, rbx
0x180006f5c  jz      short loc_180006FB0
0x180006f5e  cmp     qword ptr [rbx], 0
0x180006f62  jz      short loc_180006FB0
0x180006f64  mov     [rsi], bpl
0x180006f67  mov     r9, r14; unsigned __int64
0x180006f6a  mov     r8, rsi; char *
0x180006f6d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006f70  mov     rcx, rdi; struct wil::FailureInfo *
0x180006f73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006f78  test    al, al
0x180006f7a  jz      short loc_180006F80
0x180006f7c  mov     [rdi+48h], rsi
0x180006f80  mov     rbx, [rbx]
0x180006f83  mov     al, [rbx+28h]
0x180006f86  mov     byte ptr [rbx+28h], 1
0x180006f8a  test    al, al
0x180006f8c  jnz     short loc_180006FA7
0x180006f8e  mov     rcx, [rbx+8]
0x180006f92  mov     rax, [rcx]
0x180006f95  mov     rdx, rdi
0x180006f98  mov     rax, [rax]
0x180006f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa0  or      bpl, al
0x180006fa3  mov     byte ptr [rbx+28h], 0
0x180006fa7  mov     rbx, [rbx+10h]
0x180006fab  test    rbx, rbx
0x180006fae  jnz     short loc_180006F83
0x180006fb0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006fb7  test    rax, rax
0x180006fba  jz      short loc_180006FDC
0x180006fbc  test    bpl, bpl
0x180006fbf  jnz     short loc_180006FD1
0x180006fc1  test    byte ptr [rdi+4], 2
0x180006fc5  jnz     short loc_180006FD1
0x180006fc7  xor     ecx, ecx
0x180006fc9  jmp     short loc_180006FD3
0x180006fcb  add     rbx, 10h
0x180006fcf  jmp     short loc_180006F59
0x180006fd1  mov     cl, 1
0x180006fd3  mov     rdx, rdi
0x180006fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fdb  nop
0x180006fdc  call    cs:__imp_GetCurrentThreadId
0x180006fe2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006fe8  cmp     ecx, eax
0x180006fea  jz      loc_1800070EC
0x180006ff0  mov     ecx, 1
0x180006ff5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006ffd  inc     ecx; this
0x180006fff  cmp     ecx, 4
0x180007002  jge     loc_1800070E5
0x180007008  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000700e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007013  mov     rbx, rax
0x180007016  test    rax, rax
0x180007019  jz      loc_1800070DB
0x18000701f  mov     esi, [rax+10h]
0x180007022  mov     ebp, 50h ; 'P'
0x180007027  cmp     qword ptr [rax+18h], 0
0x18000702c  jnz     short loc_180007063
0x18000702e  test    esi, esi
0x180007030  jz      short loc_180007063
0x180007032  mov     edx, 190h; dwBytes
0x180007037  lea     ecx, [rbp-48h]; dwFlags
0x18000703a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000703f  mov     [rbx+18h], rax
0x180007043  test    rax, rax
0x180007046  jz      short loc_180007063
0x180007048  mov     dword ptr [rbx+20h], 5
0x18000704f  lea     rcx, [rax+190h]
0x180007056  jmp     short loc_18000705E
0x180007058  mov     [rax], bp
0x18000705b  add     rax, rbp
0x18000705e  cmp     rax, rcx
0x180007061  jnz     short loc_180007058
0x180007063  mov     r9, [rbx+18h]
0x180007067  test    r9, r9
0x18000706a  jz      short loc_1800070DB
0x18000706c  test    esi, esi
0x18000706e  jz      short loc_1800070A1
0x180007070  mov     rcx, r9
0x180007073  movzx   eax, word ptr [rbx+20h]
0x180007077  lea     rdx, [rax+rax*4]
0x18000707b  shl     rdx, 4
0x18000707f  add     rdx, r9
0x180007082  cmp     r9, rdx
0x180007085  jz      short loc_1800070A1
0x180007087  mov     r8d, [rbx+10h]
0x18000708b  cmp     [rcx+4], r8d
0x18000708f  jbe     short loc_180007099
0x180007091  mov     eax, [rdi+8]
0x180007094  cmp     [rcx+8], eax
0x180007097  jz      short loc_1800070DB
0x180007099  add     rcx, rbp
0x18000709c  cmp     rcx, rdx
0x18000709f  jnz     short loc_18000708B
0x1800070a1  movzx   eax, word ptr [rbx+22h]
0x1800070a5  inc     eax
0x1800070a7  movzx   ecx, word ptr [rbx+20h]
0x1800070ab  xor     edx, edx
0x1800070ad  div     ecx
0x1800070af  mov     [rbx+22h], dx
0x1800070b3  mov     rax, [rbx+8]
0x1800070b7  mov     r8d, 1
0x1800070bd  lock xadd [rax], r8d
0x1800070c2  inc     r8d; unsigned int
0x1800070c5  movzx   eax, dx
0x1800070c8  lea     rcx, [rax+rax*4]
0x1800070cc  shl     rcx, 4
0x1800070d0  add     rcx, r9; this
0x1800070d3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800070d6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800070db  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800070e5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800070ec  add     rsp, 20h
0x1800070f0  pop     r14
0x1800070f2  pop     rdi
0x1800070f3  pop     rsi
0x1800070f4  pop     rbp
0x1800070f5  pop     rbx
0x1800070f6  retn
```
