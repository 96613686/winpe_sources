# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005e50`
- end: `0x180006060`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005e50`
- `0x18000657c`
- `0x180006660`
- `0x1800070f4`
- `0x1800087e0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f45`

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
0x180005e50  push    rbx
0x180005e52  push    rbp
0x180005e53  push    rsi
0x180005e54  push    rdi
0x180005e55  push    r14
0x180005e57  sub     rsp, 30h
0x180005e5b  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180005e64  mov     r14, r8
0x180005e67  mov     rsi, rdx
0x180005e6a  mov     rdi, rcx
0x180005e6d  mov     byte ptr [rdx], 0
0x180005e70  xor     bpl, bpl
0x180005e73  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005e7a  test    rbx, rbx
0x180005e7d  jz      loc_180005F19
0x180005e83  call    cs:__imp_GetCurrentThreadId
0x180005e89  mov     r9d, eax
0x180005e8c  mov     r8d, eax
0x180005e8f  shr     r8, 2
0x180005e93  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005e9d  mul     r8
0x180005ea0  shr     rdx, 3
0x180005ea4  lea     rcx, [rdx+rdx*4]
0x180005ea8  add     rcx, rcx
0x180005eab  sub     r8, rcx
0x180005eae  mov     rbx, [rbx+r8*8]
0x180005eb2  jmp     short loc_180005EBD
0x180005eb4  cmp     [rbx], r9d
0x180005eb7  jz      short loc_180005F34
0x180005eb9  mov     rbx, [rbx+8]
0x180005ebd  test    rbx, rbx
0x180005ec0  jnz     short loc_180005EB4
0x180005ec2  test    rbx, rbx
0x180005ec5  jz      short loc_180005F19
0x180005ec7  cmp     qword ptr [rbx], 0
0x180005ecb  jz      short loc_180005F19
0x180005ecd  mov     [rsi], bpl
0x180005ed0  mov     r9, r14; unsigned __int64
0x180005ed3  mov     r8, rsi; char *
0x180005ed6  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005ed9  mov     rcx, rdi; struct wil::FailureInfo *
0x180005edc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005ee1  test    al, al
0x180005ee3  jz      short loc_180005EE9
0x180005ee5  mov     [rdi+48h], rsi
0x180005ee9  mov     rbx, [rbx]
0x180005eec  mov     al, [rbx+28h]
0x180005eef  mov     byte ptr [rbx+28h], 1
0x180005ef3  test    al, al
0x180005ef5  jnz     short loc_180005F10
0x180005ef7  mov     rcx, [rbx+8]
0x180005efb  mov     rax, [rcx]
0x180005efe  mov     rdx, rdi
0x180005f01  mov     rax, [rax]
0x180005f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f09  or      bpl, al
0x180005f0c  mov     byte ptr [rbx+28h], 0
0x180005f10  mov     rbx, [rbx+10h]
0x180005f14  test    rbx, rbx
0x180005f17  jnz     short loc_180005EEC
0x180005f19  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005f20  test    rax, rax
0x180005f23  jz      short loc_180005F45
0x180005f25  test    bpl, bpl
0x180005f28  jnz     short loc_180005F3A
0x180005f2a  test    byte ptr [rdi+4], 2
0x180005f2e  jnz     short loc_180005F3A
0x180005f30  xor     ecx, ecx
0x180005f32  jmp     short loc_180005F3C
0x180005f34  add     rbx, 10h
0x180005f38  jmp     short loc_180005EC2
0x180005f3a  mov     cl, 1
0x180005f3c  mov     rdx, rdi
0x180005f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f44  nop
0x180005f45  call    cs:__imp_GetCurrentThreadId
0x180005f4b  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f51  cmp     ecx, eax
0x180005f53  jz      loc_180006055
0x180005f59  mov     ecx, 1
0x180005f5e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005f66  inc     ecx; this
0x180005f68  cmp     ecx, 4
0x180005f6b  jge     loc_18000604E
0x180005f71  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f77  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005f7c  mov     rbx, rax
0x180005f7f  test    rax, rax
0x180005f82  jz      loc_180006044
0x180005f88  mov     esi, [rax+10h]
0x180005f8b  mov     ebp, 50h ; 'P'
0x180005f90  cmp     qword ptr [rax+18h], 0
0x180005f95  jnz     short loc_180005FCC
0x180005f97  test    esi, esi
0x180005f99  jz      short loc_180005FCC
0x180005f9b  mov     edx, 190h; dwBytes
0x180005fa0  lea     ecx, [rbp-48h]; dwFlags
0x180005fa3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005fa8  mov     [rbx+18h], rax
0x180005fac  test    rax, rax
0x180005faf  jz      short loc_180005FCC
0x180005fb1  mov     dword ptr [rbx+20h], 5
0x180005fb8  lea     rcx, [rax+190h]
0x180005fbf  jmp     short loc_180005FC7
0x180005fc1  mov     [rax], bp
0x180005fc4  add     rax, rbp
0x180005fc7  cmp     rax, rcx
0x180005fca  jnz     short loc_180005FC1
0x180005fcc  mov     r9, [rbx+18h]
0x180005fd0  test    r9, r9
0x180005fd3  jz      short loc_180006044
0x180005fd5  test    esi, esi
0x180005fd7  jz      short loc_18000600A
0x180005fd9  mov     rcx, r9
0x180005fdc  movzx   eax, word ptr [rbx+20h]
0x180005fe0  lea     rdx, [rax+rax*4]
0x180005fe4  shl     rdx, 4
0x180005fe8  add     rdx, r9
0x180005feb  cmp     r9, rdx
0x180005fee  jz      short loc_18000600A
0x180005ff0  mov     r8d, [rbx+10h]
0x180005ff4  cmp     [rcx+4], r8d
0x180005ff8  jbe     short loc_180006002
0x180005ffa  mov     eax, [rdi+8]
0x180005ffd  cmp     [rcx+8], eax
0x180006000  jz      short loc_180006044
0x180006002  add     rcx, rbp
0x180006005  cmp     rcx, rdx
0x180006008  jnz     short loc_180005FF4
0x18000600a  movzx   eax, word ptr [rbx+22h]
0x18000600e  inc     eax
0x180006010  movzx   ecx, word ptr [rbx+20h]
0x180006014  xor     edx, edx
0x180006016  div     ecx
0x180006018  mov     [rbx+22h], dx
0x18000601c  mov     rax, [rbx+8]
0x180006020  mov     r8d, 1
0x180006026  lock xadd [rax], r8d
0x18000602b  inc     r8d; unsigned int
0x18000602e  movzx   eax, dx
0x180006031  lea     rcx, [rax+rax*4]
0x180006035  shl     rcx, 4
0x180006039  add     rcx, r9; this
0x18000603c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000603f  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006044  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000604e  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006055  add     rsp, 30h
0x180006059  pop     r14
0x18000605b  pop     rdi
0x18000605c  pop     rsi
0x18000605d  pop     rbp
0x18000605e  pop     rbx
0x18000605f  retn
```
