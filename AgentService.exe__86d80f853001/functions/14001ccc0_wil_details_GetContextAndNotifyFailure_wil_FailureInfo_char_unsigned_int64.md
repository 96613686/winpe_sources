# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x14001ccc0`
- end: `0x14001cec7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14001ccc0`
- `0x14001d3c8`
- `0x14001d4ac`
- `0x14001dd18`
- `0x14001e080`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001ccea`
- `KERNEL32!GetCurrentThreadId` at `0x14001cdac`
- `KERNEL32!GetCurrentThreadId` at `0x14001ccea`
- `KERNEL32!GetCurrentThreadId` at `0x14001cdac`

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
0x14001ccc0  push    rbx
0x14001ccc2  push    rbp
0x14001ccc3  push    rsi
0x14001ccc4  push    rdi
0x14001ccc5  push    r14
0x14001ccc7  sub     rsp, 20h
0x14001cccb  mov     r14, r8
0x14001ccce  mov     rsi, rdx
0x14001ccd1  mov     rdi, rcx
0x14001ccd4  mov     byte ptr [rdx], 0
0x14001ccd7  xor     bpl, bpl
0x14001ccda  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14001cce1  test    rbx, rbx
0x14001cce4  jz      loc_14001CD80
0x14001ccea  call    cs:__imp_GetCurrentThreadId
0x14001ccf0  mov     r9d, eax
0x14001ccf3  mov     r8d, eax
0x14001ccf6  shr     r8, 2
0x14001ccfa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14001cd04  mul     r8
0x14001cd07  shr     rdx, 3
0x14001cd0b  lea     rcx, [rdx+rdx*4]
0x14001cd0f  add     rcx, rcx
0x14001cd12  sub     r8, rcx
0x14001cd15  mov     rbx, [rbx+r8*8]
0x14001cd19  jmp     short loc_14001CD24
0x14001cd1b  cmp     [rbx], r9d
0x14001cd1e  jz      short loc_14001CD9B
0x14001cd20  mov     rbx, [rbx+8]
0x14001cd24  test    rbx, rbx
0x14001cd27  jnz     short loc_14001CD1B
0x14001cd29  test    rbx, rbx
0x14001cd2c  jz      short loc_14001CD80
0x14001cd2e  cmp     qword ptr [rbx], 0
0x14001cd32  jz      short loc_14001CD80
0x14001cd34  mov     [rsi], bpl
0x14001cd37  mov     r9, r14; unsigned __int64
0x14001cd3a  mov     r8, rsi; char *
0x14001cd3d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14001cd40  mov     rcx, rdi; struct wil::FailureInfo *
0x14001cd43  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14001cd48  test    al, al
0x14001cd4a  jz      short loc_14001CD50
0x14001cd4c  mov     [rdi+48h], rsi
0x14001cd50  mov     rbx, [rbx]
0x14001cd53  mov     al, [rbx+28h]
0x14001cd56  mov     byte ptr [rbx+28h], 1
0x14001cd5a  test    al, al
0x14001cd5c  jnz     short loc_14001CD77
0x14001cd5e  mov     rcx, [rbx+8]
0x14001cd62  mov     rax, [rcx]
0x14001cd65  mov     rdx, rdi
0x14001cd68  mov     rax, [rax]
0x14001cd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cd70  or      bpl, al
0x14001cd73  mov     byte ptr [rbx+28h], 0
0x14001cd77  mov     rbx, [rbx+10h]
0x14001cd7b  test    rbx, rbx
0x14001cd7e  jnz     short loc_14001CD53
0x14001cd80  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14001cd87  test    rax, rax
0x14001cd8a  jz      short loc_14001CDAC
0x14001cd8c  test    bpl, bpl
0x14001cd8f  jnz     short loc_14001CDA1
0x14001cd91  test    byte ptr [rdi+4], 2
0x14001cd95  jnz     short loc_14001CDA1
0x14001cd97  xor     ecx, ecx
0x14001cd99  jmp     short loc_14001CDA3
0x14001cd9b  add     rbx, 10h
0x14001cd9f  jmp     short loc_14001CD29
0x14001cda1  mov     cl, 1
0x14001cda3  mov     rdx, rdi
0x14001cda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cdab  nop
0x14001cdac  call    cs:__imp_GetCurrentThreadId
0x14001cdb2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14001cdb8  cmp     ecx, eax
0x14001cdba  jz      loc_14001CEBC
0x14001cdc0  mov     ecx, 1
0x14001cdc5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14001cdcd  inc     ecx; this
0x14001cdcf  cmp     ecx, 4
0x14001cdd2  jge     loc_14001CEB5
0x14001cdd8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14001cdde  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14001cde3  mov     rbx, rax
0x14001cde6  test    rax, rax
0x14001cde9  jz      loc_14001CEAB
0x14001cdef  mov     esi, [rax+10h]
0x14001cdf2  mov     ebp, 50h ; 'P'
0x14001cdf7  cmp     qword ptr [rax+18h], 0
0x14001cdfc  jnz     short loc_14001CE33
0x14001cdfe  test    esi, esi
0x14001ce00  jz      short loc_14001CE33
0x14001ce02  mov     edx, 190h; dwBytes
0x14001ce07  lea     ecx, [rbp-48h]; dwFlags
0x14001ce0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001ce0f  mov     [rbx+18h], rax
0x14001ce13  test    rax, rax
0x14001ce16  jz      short loc_14001CE33
0x14001ce18  mov     dword ptr [rbx+20h], 5
0x14001ce1f  lea     rcx, [rax+190h]
0x14001ce26  jmp     short loc_14001CE2E
0x14001ce28  mov     [rax], bp
0x14001ce2b  add     rax, rbp
0x14001ce2e  cmp     rax, rcx
0x14001ce31  jnz     short loc_14001CE28
0x14001ce33  mov     r9, [rbx+18h]
0x14001ce37  test    r9, r9
0x14001ce3a  jz      short loc_14001CEAB
0x14001ce3c  test    esi, esi
0x14001ce3e  jz      short loc_14001CE71
0x14001ce40  mov     rcx, r9
0x14001ce43  movzx   eax, word ptr [rbx+20h]
0x14001ce47  lea     rdx, [rax+rax*4]
0x14001ce4b  shl     rdx, 4
0x14001ce4f  add     rdx, r9
0x14001ce52  cmp     r9, rdx
0x14001ce55  jz      short loc_14001CE71
0x14001ce57  mov     r8d, [rbx+10h]
0x14001ce5b  cmp     [rcx+4], r8d
0x14001ce5f  jbe     short loc_14001CE69
0x14001ce61  mov     eax, [rdi+8]
0x14001ce64  cmp     [rcx+8], eax
0x14001ce67  jz      short loc_14001CEAB
0x14001ce69  add     rcx, rbp
0x14001ce6c  cmp     rcx, rdx
0x14001ce6f  jnz     short loc_14001CE5B
0x14001ce71  movzx   eax, word ptr [rbx+22h]
0x14001ce75  inc     eax
0x14001ce77  movzx   ecx, word ptr [rbx+20h]
0x14001ce7b  xor     edx, edx
0x14001ce7d  div     ecx
0x14001ce7f  mov     [rbx+22h], dx
0x14001ce83  mov     rax, [rbx+8]
0x14001ce87  mov     r8d, 1
0x14001ce8d  lock xadd [rax], r8d
0x14001ce92  inc     r8d; unsigned int
0x14001ce95  movzx   eax, dx
0x14001ce98  lea     rcx, [rax+rax*4]
0x14001ce9c  shl     rcx, 4
0x14001cea0  add     rcx, r9; this
0x14001cea3  mov     rdx, rdi; struct wil::FailureInfo *
0x14001cea6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14001ceab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14001ceb5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14001cebc  add     rsp, 20h
0x14001cec0  pop     r14
0x14001cec2  pop     rdi
0x14001cec3  pop     rsi
0x14001cec4  pop     rbp
0x14001cec5  pop     rbx
0x14001cec6  retn
```
