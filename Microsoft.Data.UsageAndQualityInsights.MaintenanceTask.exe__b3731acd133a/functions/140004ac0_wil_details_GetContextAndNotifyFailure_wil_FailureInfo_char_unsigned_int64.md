# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004ac0`
- end: `0x140004cc7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004ac0`
- `0x1400051bc`
- `0x1400052a0`
- `0x140005d18`
- `0x1400073d4`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004bac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004bac`

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
0x140004ac0  push    rbx
0x140004ac2  push    rbp
0x140004ac3  push    rsi
0x140004ac4  push    rdi
0x140004ac5  push    r14
0x140004ac7  sub     rsp, 20h
0x140004acb  mov     r14, r8
0x140004ace  mov     rsi, rdx
0x140004ad1  mov     rdi, rcx
0x140004ad4  mov     byte ptr [rdx], 0
0x140004ad7  xor     bpl, bpl
0x140004ada  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004ae1  test    rbx, rbx
0x140004ae4  jz      loc_140004B80
0x140004aea  call    cs:__imp_GetCurrentThreadId
0x140004af0  mov     r9d, eax
0x140004af3  mov     r8d, eax
0x140004af6  shr     r8, 2
0x140004afa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004b04  mul     r8
0x140004b07  shr     rdx, 3
0x140004b0b  lea     rcx, [rdx+rdx*4]
0x140004b0f  add     rcx, rcx
0x140004b12  sub     r8, rcx
0x140004b15  mov     rbx, [rbx+r8*8]
0x140004b19  jmp     short loc_140004B24
0x140004b1b  cmp     [rbx], r9d
0x140004b1e  jz      short loc_140004B9B
0x140004b20  mov     rbx, [rbx+8]
0x140004b24  test    rbx, rbx
0x140004b27  jnz     short loc_140004B1B
0x140004b29  test    rbx, rbx
0x140004b2c  jz      short loc_140004B80
0x140004b2e  cmp     qword ptr [rbx], 0
0x140004b32  jz      short loc_140004B80
0x140004b34  mov     [rsi], bpl
0x140004b37  mov     r9, r14; unsigned __int64
0x140004b3a  mov     r8, rsi; char *
0x140004b3d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004b40  mov     rcx, rdi; struct wil::FailureInfo *
0x140004b43  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004b48  test    al, al
0x140004b4a  jz      short loc_140004B50
0x140004b4c  mov     [rdi+48h], rsi
0x140004b50  mov     rbx, [rbx]
0x140004b53  mov     al, [rbx+28h]
0x140004b56  mov     byte ptr [rbx+28h], 1
0x140004b5a  test    al, al
0x140004b5c  jnz     short loc_140004B77
0x140004b5e  mov     rcx, [rbx+8]
0x140004b62  mov     rax, [rcx]
0x140004b65  mov     rdx, rdi
0x140004b68  mov     rax, [rax]
0x140004b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b70  or      bpl, al
0x140004b73  mov     byte ptr [rbx+28h], 0
0x140004b77  mov     rbx, [rbx+10h]
0x140004b7b  test    rbx, rbx
0x140004b7e  jnz     short loc_140004B53
0x140004b80  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004b87  test    rax, rax
0x140004b8a  jz      short loc_140004BAC
0x140004b8c  test    bpl, bpl
0x140004b8f  jnz     short loc_140004BA1
0x140004b91  test    byte ptr [rdi+4], 2
0x140004b95  jnz     short loc_140004BA1
0x140004b97  xor     ecx, ecx
0x140004b99  jmp     short loc_140004BA3
0x140004b9b  add     rbx, 10h
0x140004b9f  jmp     short loc_140004B29
0x140004ba1  mov     cl, 1
0x140004ba3  mov     rdx, rdi
0x140004ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bab  nop
0x140004bac  call    cs:__imp_GetCurrentThreadId
0x140004bb2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004bb8  cmp     ecx, eax
0x140004bba  jz      loc_140004CBC
0x140004bc0  mov     ecx, 1
0x140004bc5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004bcd  inc     ecx; this
0x140004bcf  cmp     ecx, 4
0x140004bd2  jge     loc_140004CB5
0x140004bd8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004bde  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004be3  mov     rbx, rax
0x140004be6  test    rax, rax
0x140004be9  jz      loc_140004CAB
0x140004bef  mov     esi, [rax+10h]
0x140004bf2  mov     ebp, 50h ; 'P'
0x140004bf7  cmp     qword ptr [rax+18h], 0
0x140004bfc  jnz     short loc_140004C33
0x140004bfe  test    esi, esi
0x140004c00  jz      short loc_140004C33
0x140004c02  mov     edx, 190h; dwBytes
0x140004c07  lea     ecx, [rbp-48h]; dwFlags
0x140004c0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004c0f  mov     [rbx+18h], rax
0x140004c13  test    rax, rax
0x140004c16  jz      short loc_140004C33
0x140004c18  mov     dword ptr [rbx+20h], 5
0x140004c1f  lea     rcx, [rax+190h]
0x140004c26  jmp     short loc_140004C2E
0x140004c28  mov     [rax], bp
0x140004c2b  add     rax, rbp
0x140004c2e  cmp     rax, rcx
0x140004c31  jnz     short loc_140004C28
0x140004c33  mov     r9, [rbx+18h]
0x140004c37  test    r9, r9
0x140004c3a  jz      short loc_140004CAB
0x140004c3c  test    esi, esi
0x140004c3e  jz      short loc_140004C71
0x140004c40  mov     rcx, r9
0x140004c43  movzx   eax, word ptr [rbx+20h]
0x140004c47  lea     rdx, [rax+rax*4]
0x140004c4b  shl     rdx, 4
0x140004c4f  add     rdx, r9
0x140004c52  cmp     r9, rdx
0x140004c55  jz      short loc_140004C71
0x140004c57  mov     r8d, [rbx+10h]
0x140004c5b  cmp     [rcx+4], r8d
0x140004c5f  jbe     short loc_140004C69
0x140004c61  mov     eax, [rdi+8]
0x140004c64  cmp     [rcx+8], eax
0x140004c67  jz      short loc_140004CAB
0x140004c69  add     rcx, rbp
0x140004c6c  cmp     rcx, rdx
0x140004c6f  jnz     short loc_140004C5B
0x140004c71  movzx   eax, word ptr [rbx+22h]
0x140004c75  inc     eax
0x140004c77  movzx   ecx, word ptr [rbx+20h]
0x140004c7b  xor     edx, edx
0x140004c7d  div     ecx
0x140004c7f  mov     [rbx+22h], dx
0x140004c83  mov     rax, [rbx+8]
0x140004c87  mov     r8d, 1
0x140004c8d  lock xadd [rax], r8d
0x140004c92  inc     r8d; unsigned int
0x140004c95  movzx   eax, dx
0x140004c98  lea     rcx, [rax+rax*4]
0x140004c9c  shl     rcx, 4
0x140004ca0  add     rcx, r9; this
0x140004ca3  mov     rdx, rdi; struct wil::FailureInfo *
0x140004ca6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140004cab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004cb5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004cbc  add     rsp, 20h
0x140004cc0  pop     r14
0x140004cc2  pop     rdi
0x140004cc3  pop     rsi
0x140004cc4  pop     rbp
0x140004cc5  pop     rbx
0x140004cc6  retn
```
