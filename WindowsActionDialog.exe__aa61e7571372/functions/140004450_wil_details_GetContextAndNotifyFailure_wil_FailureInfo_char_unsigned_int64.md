# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004450`
- end: `0x140004657`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004450`
- `0x140004c00`
- `0x140004ce4`
- `0x140005f30`
- `0x140006514`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000447a`
- `KERNEL32!GetCurrentThreadId` at `0x14000453c`
- `KERNEL32!GetCurrentThreadId` at `0x14000447a`
- `KERNEL32!GetCurrentThreadId` at `0x14000453c`

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
0x140004450  push    rbx
0x140004452  push    rbp
0x140004453  push    rsi
0x140004454  push    rdi
0x140004455  push    r14
0x140004457  sub     rsp, 20h
0x14000445b  mov     r14, r8
0x14000445e  mov     rsi, rdx
0x140004461  mov     rdi, rcx
0x140004464  mov     byte ptr [rdx], 0
0x140004467  xor     bpl, bpl
0x14000446a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004471  test    rbx, rbx
0x140004474  jz      loc_140004510
0x14000447a  call    cs:__imp_GetCurrentThreadId
0x140004480  mov     r9d, eax
0x140004483  mov     r8d, eax
0x140004486  shr     r8, 2
0x14000448a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004494  mul     r8
0x140004497  shr     rdx, 3
0x14000449b  lea     rcx, [rdx+rdx*4]
0x14000449f  add     rcx, rcx
0x1400044a2  sub     r8, rcx
0x1400044a5  mov     rbx, [rbx+r8*8]
0x1400044a9  jmp     short loc_1400044B4
0x1400044ab  cmp     [rbx], r9d
0x1400044ae  jz      short loc_14000452B
0x1400044b0  mov     rbx, [rbx+8]
0x1400044b4  test    rbx, rbx
0x1400044b7  jnz     short loc_1400044AB
0x1400044b9  test    rbx, rbx
0x1400044bc  jz      short loc_140004510
0x1400044be  cmp     qword ptr [rbx], 0
0x1400044c2  jz      short loc_140004510
0x1400044c4  mov     [rsi], bpl
0x1400044c7  mov     r9, r14; unsigned __int64
0x1400044ca  mov     r8, rsi; char *
0x1400044cd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400044d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400044d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400044d8  test    al, al
0x1400044da  jz      short loc_1400044E0
0x1400044dc  mov     [rdi+48h], rsi
0x1400044e0  mov     rbx, [rbx]
0x1400044e3  mov     al, [rbx+28h]
0x1400044e6  mov     byte ptr [rbx+28h], 1
0x1400044ea  test    al, al
0x1400044ec  jnz     short loc_140004507
0x1400044ee  mov     rcx, [rbx+8]
0x1400044f2  mov     rax, [rcx]
0x1400044f5  mov     rdx, rdi
0x1400044f8  mov     rax, [rax]
0x1400044fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004500  or      bpl, al
0x140004503  mov     byte ptr [rbx+28h], 0
0x140004507  mov     rbx, [rbx+10h]
0x14000450b  test    rbx, rbx
0x14000450e  jnz     short loc_1400044E3
0x140004510  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004517  test    rax, rax
0x14000451a  jz      short loc_14000453C
0x14000451c  test    bpl, bpl
0x14000451f  jnz     short loc_140004531
0x140004521  test    byte ptr [rdi+4], 2
0x140004525  jnz     short loc_140004531
0x140004527  xor     ecx, ecx
0x140004529  jmp     short loc_140004533
0x14000452b  add     rbx, 10h
0x14000452f  jmp     short loc_1400044B9
0x140004531  mov     cl, 1
0x140004533  mov     rdx, rdi
0x140004536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000453b  nop
0x14000453c  call    cs:__imp_GetCurrentThreadId
0x140004542  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004548  cmp     ecx, eax
0x14000454a  jz      loc_14000464C
0x140004550  mov     ecx, 1
0x140004555  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000455d  inc     ecx; this
0x14000455f  cmp     ecx, 4
0x140004562  jge     loc_140004645
0x140004568  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000456e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004573  mov     rbx, rax
0x140004576  test    rax, rax
0x140004579  jz      loc_14000463B
0x14000457f  mov     esi, [rax+10h]
0x140004582  mov     ebp, 50h ; 'P'
0x140004587  cmp     qword ptr [rax+18h], 0
0x14000458c  jnz     short loc_1400045C3
0x14000458e  test    esi, esi
0x140004590  jz      short loc_1400045C3
0x140004592  mov     edx, 190h; dwBytes
0x140004597  lea     ecx, [rbp-48h]; dwFlags
0x14000459a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000459f  mov     [rbx+18h], rax
0x1400045a3  test    rax, rax
0x1400045a6  jz      short loc_1400045C3
0x1400045a8  mov     dword ptr [rbx+20h], 5
0x1400045af  lea     rcx, [rax+190h]
0x1400045b6  jmp     short loc_1400045BE
0x1400045b8  mov     [rax], bp
0x1400045bb  add     rax, rbp
0x1400045be  cmp     rax, rcx
0x1400045c1  jnz     short loc_1400045B8
0x1400045c3  mov     r9, [rbx+18h]
0x1400045c7  test    r9, r9
0x1400045ca  jz      short loc_14000463B
0x1400045cc  test    esi, esi
0x1400045ce  jz      short loc_140004601
0x1400045d0  mov     rcx, r9
0x1400045d3  movzx   eax, word ptr [rbx+20h]
0x1400045d7  lea     rdx, [rax+rax*4]
0x1400045db  shl     rdx, 4
0x1400045df  add     rdx, r9
0x1400045e2  cmp     r9, rdx
0x1400045e5  jz      short loc_140004601
0x1400045e7  mov     r8d, [rbx+10h]
0x1400045eb  cmp     [rcx+4], r8d
0x1400045ef  jbe     short loc_1400045F9
0x1400045f1  mov     eax, [rdi+8]
0x1400045f4  cmp     [rcx+8], eax
0x1400045f7  jz      short loc_14000463B
0x1400045f9  add     rcx, rbp
0x1400045fc  cmp     rcx, rdx
0x1400045ff  jnz     short loc_1400045EB
0x140004601  movzx   eax, word ptr [rbx+22h]
0x140004605  inc     eax
0x140004607  movzx   ecx, word ptr [rbx+20h]
0x14000460b  xor     edx, edx
0x14000460d  div     ecx
0x14000460f  mov     [rbx+22h], dx
0x140004613  mov     rax, [rbx+8]
0x140004617  mov     r8d, 1
0x14000461d  lock xadd [rax], r8d
0x140004622  inc     r8d; unsigned int
0x140004625  movzx   eax, dx
0x140004628  lea     rcx, [rax+rax*4]
0x14000462c  shl     rcx, 4
0x140004630  add     rcx, r9; this
0x140004633  mov     rdx, rdi; struct wil::FailureInfo *
0x140004636  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000463b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004645  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000464c  add     rsp, 20h
0x140004650  pop     r14
0x140004652  pop     rdi
0x140004653  pop     rsi
0x140004654  pop     rbp
0x140004655  pop     rbx
0x140004656  retn
```
