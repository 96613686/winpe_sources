# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007920`
- end: `0x180007b27`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007920`
- `0x18000801c`
- `0x180008100`
- `0x180008e2c`
- `0x18000a0b0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000794a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000794a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a0c`

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
0x180007920  push    rbx
0x180007922  push    rbp
0x180007923  push    rsi
0x180007924  push    rdi
0x180007925  push    r14
0x180007927  sub     rsp, 20h
0x18000792b  mov     r14, r8
0x18000792e  mov     rsi, rdx
0x180007931  mov     rdi, rcx
0x180007934  mov     byte ptr [rdx], 0
0x180007937  xor     bpl, bpl
0x18000793a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007941  test    rbx, rbx
0x180007944  jz      loc_1800079E0
0x18000794a  call    cs:__imp_GetCurrentThreadId
0x180007950  mov     r9d, eax
0x180007953  mov     r8d, eax
0x180007956  shr     r8, 2
0x18000795a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007964  mul     r8
0x180007967  shr     rdx, 3
0x18000796b  lea     rcx, [rdx+rdx*4]
0x18000796f  add     rcx, rcx
0x180007972  sub     r8, rcx
0x180007975  mov     rbx, [rbx+r8*8]
0x180007979  jmp     short loc_180007984
0x18000797b  cmp     [rbx], r9d
0x18000797e  jz      short loc_1800079FB
0x180007980  mov     rbx, [rbx+8]
0x180007984  test    rbx, rbx
0x180007987  jnz     short loc_18000797B
0x180007989  test    rbx, rbx
0x18000798c  jz      short loc_1800079E0
0x18000798e  cmp     qword ptr [rbx], 0
0x180007992  jz      short loc_1800079E0
0x180007994  mov     [rsi], bpl
0x180007997  mov     r9, r14; unsigned __int64
0x18000799a  mov     r8, rsi; char *
0x18000799d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800079a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800079a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800079a8  test    al, al
0x1800079aa  jz      short loc_1800079B0
0x1800079ac  mov     [rdi+48h], rsi
0x1800079b0  mov     rbx, [rbx]
0x1800079b3  mov     al, [rbx+28h]
0x1800079b6  mov     byte ptr [rbx+28h], 1
0x1800079ba  test    al, al
0x1800079bc  jnz     short loc_1800079D7
0x1800079be  mov     rcx, [rbx+8]
0x1800079c2  mov     rax, [rcx]
0x1800079c5  mov     rdx, rdi
0x1800079c8  mov     rax, [rax]
0x1800079cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d0  or      bpl, al
0x1800079d3  mov     byte ptr [rbx+28h], 0
0x1800079d7  mov     rbx, [rbx+10h]
0x1800079db  test    rbx, rbx
0x1800079de  jnz     short loc_1800079B3
0x1800079e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800079e7  test    rax, rax
0x1800079ea  jz      short loc_180007A0C
0x1800079ec  test    bpl, bpl
0x1800079ef  jnz     short loc_180007A01
0x1800079f1  test    byte ptr [rdi+4], 2
0x1800079f5  jnz     short loc_180007A01
0x1800079f7  xor     ecx, ecx
0x1800079f9  jmp     short loc_180007A03
0x1800079fb  add     rbx, 10h
0x1800079ff  jmp     short loc_180007989
0x180007a01  mov     cl, 1
0x180007a03  mov     rdx, rdi
0x180007a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a0b  nop
0x180007a0c  call    cs:__imp_GetCurrentThreadId
0x180007a12  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007a18  cmp     ecx, eax
0x180007a1a  jz      loc_180007B1C
0x180007a20  mov     ecx, 1
0x180007a25  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007a2d  inc     ecx; this
0x180007a2f  cmp     ecx, 4
0x180007a32  jge     loc_180007B15
0x180007a38  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007a3e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007a43  mov     rbx, rax
0x180007a46  test    rax, rax
0x180007a49  jz      loc_180007B0B
0x180007a4f  mov     esi, [rax+10h]
0x180007a52  mov     ebp, 50h ; 'P'
0x180007a57  cmp     qword ptr [rax+18h], 0
0x180007a5c  jnz     short loc_180007A93
0x180007a5e  test    esi, esi
0x180007a60  jz      short loc_180007A93
0x180007a62  mov     edx, 190h; dwBytes
0x180007a67  lea     ecx, [rbp-48h]; dwFlags
0x180007a6a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007a6f  mov     [rbx+18h], rax
0x180007a73  test    rax, rax
0x180007a76  jz      short loc_180007A93
0x180007a78  mov     dword ptr [rbx+20h], 5
0x180007a7f  lea     rcx, [rax+190h]
0x180007a86  jmp     short loc_180007A8E
0x180007a88  mov     [rax], bp
0x180007a8b  add     rax, rbp
0x180007a8e  cmp     rax, rcx
0x180007a91  jnz     short loc_180007A88
0x180007a93  mov     r9, [rbx+18h]
0x180007a97  test    r9, r9
0x180007a9a  jz      short loc_180007B0B
0x180007a9c  test    esi, esi
0x180007a9e  jz      short loc_180007AD1
0x180007aa0  mov     rcx, r9
0x180007aa3  movzx   eax, word ptr [rbx+20h]
0x180007aa7  lea     rdx, [rax+rax*4]
0x180007aab  shl     rdx, 4
0x180007aaf  add     rdx, r9
0x180007ab2  cmp     r9, rdx
0x180007ab5  jz      short loc_180007AD1
0x180007ab7  mov     r8d, [rbx+10h]
0x180007abb  cmp     [rcx+4], r8d
0x180007abf  jbe     short loc_180007AC9
0x180007ac1  mov     eax, [rdi+8]
0x180007ac4  cmp     [rcx+8], eax
0x180007ac7  jz      short loc_180007B0B
0x180007ac9  add     rcx, rbp
0x180007acc  cmp     rcx, rdx
0x180007acf  jnz     short loc_180007ABB
0x180007ad1  movzx   eax, word ptr [rbx+22h]
0x180007ad5  inc     eax
0x180007ad7  movzx   ecx, word ptr [rbx+20h]
0x180007adb  xor     edx, edx
0x180007add  div     ecx
0x180007adf  mov     [rbx+22h], dx
0x180007ae3  mov     rax, [rbx+8]
0x180007ae7  mov     r8d, 1
0x180007aed  lock xadd [rax], r8d
0x180007af2  inc     r8d; unsigned int
0x180007af5  movzx   eax, dx
0x180007af8  lea     rcx, [rax+rax*4]
0x180007afc  shl     rcx, 4
0x180007b00  add     rcx, r9; this
0x180007b03  mov     rdx, rdi; struct wil::FailureInfo *
0x180007b06  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007b0b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007b15  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007b1c  add     rsp, 20h
0x180007b20  pop     r14
0x180007b22  pop     rdi
0x180007b23  pop     rsi
0x180007b24  pop     rbp
0x180007b25  pop     rbx
0x180007b26  retn
```
