# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400050a0`
- end: `0x1400052b0`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400050a0`
- `0x140005870`
- `0x140005954`
- `0x1400061e4`
- `0x140006560`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400050d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005195`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400050d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005195`

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
0x1400050a0  push    rbx
0x1400050a2  push    rbp
0x1400050a3  push    rsi
0x1400050a4  push    rdi
0x1400050a5  push    r14
0x1400050a7  sub     rsp, 30h
0x1400050ab  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1400050b4  mov     r14, r8
0x1400050b7  mov     rsi, rdx
0x1400050ba  mov     rdi, rcx
0x1400050bd  mov     byte ptr [rdx], 0
0x1400050c0  xor     bpl, bpl
0x1400050c3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400050ca  test    rbx, rbx
0x1400050cd  jz      loc_140005169
0x1400050d3  call    cs:__imp_GetCurrentThreadId
0x1400050d9  mov     r9d, eax
0x1400050dc  mov     r8d, eax
0x1400050df  shr     r8, 2
0x1400050e3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400050ed  mul     r8
0x1400050f0  shr     rdx, 3
0x1400050f4  lea     rcx, [rdx+rdx*4]
0x1400050f8  add     rcx, rcx
0x1400050fb  sub     r8, rcx
0x1400050fe  mov     rbx, [rbx+r8*8]
0x140005102  jmp     short loc_14000510D
0x140005104  cmp     [rbx], r9d
0x140005107  jz      short loc_140005184
0x140005109  mov     rbx, [rbx+8]
0x14000510d  test    rbx, rbx
0x140005110  jnz     short loc_140005104
0x140005112  test    rbx, rbx
0x140005115  jz      short loc_140005169
0x140005117  cmp     qword ptr [rbx], 0
0x14000511b  jz      short loc_140005169
0x14000511d  mov     [rsi], bpl
0x140005120  mov     r9, r14; unsigned __int64
0x140005123  mov     r8, rsi; char *
0x140005126  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140005129  mov     rcx, rdi; struct wil::FailureInfo *
0x14000512c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005131  test    al, al
0x140005133  jz      short loc_140005139
0x140005135  mov     [rdi+48h], rsi
0x140005139  mov     rbx, [rbx]
0x14000513c  mov     al, [rbx+28h]
0x14000513f  mov     byte ptr [rbx+28h], 1
0x140005143  test    al, al
0x140005145  jnz     short loc_140005160
0x140005147  mov     rcx, [rbx+8]
0x14000514b  mov     rax, [rcx]
0x14000514e  mov     rdx, rdi
0x140005151  mov     rax, [rax]
0x140005154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005159  or      bpl, al
0x14000515c  mov     byte ptr [rbx+28h], 0
0x140005160  mov     rbx, [rbx+10h]
0x140005164  test    rbx, rbx
0x140005167  jnz     short loc_14000513C
0x140005169  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005170  test    rax, rax
0x140005173  jz      short loc_140005195
0x140005175  test    bpl, bpl
0x140005178  jnz     short loc_14000518A
0x14000517a  test    byte ptr [rdi+4], 2
0x14000517e  jnz     short loc_14000518A
0x140005180  xor     ecx, ecx
0x140005182  jmp     short loc_14000518C
0x140005184  add     rbx, 10h
0x140005188  jmp     short loc_140005112
0x14000518a  mov     cl, 1
0x14000518c  mov     rdx, rdi
0x14000518f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005194  nop
0x140005195  call    cs:__imp_GetCurrentThreadId
0x14000519b  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400051a1  cmp     ecx, eax
0x1400051a3  jz      loc_1400052A5
0x1400051a9  mov     ecx, 1
0x1400051ae  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400051b6  inc     ecx; this
0x1400051b8  cmp     ecx, 4
0x1400051bb  jge     loc_14000529E
0x1400051c1  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400051c7  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400051cc  mov     rbx, rax
0x1400051cf  test    rax, rax
0x1400051d2  jz      loc_140005294
0x1400051d8  mov     esi, [rax+10h]
0x1400051db  mov     ebp, 50h ; 'P'
0x1400051e0  cmp     qword ptr [rax+18h], 0
0x1400051e5  jnz     short loc_14000521C
0x1400051e7  test    esi, esi
0x1400051e9  jz      short loc_14000521C
0x1400051eb  mov     edx, 190h; dwBytes
0x1400051f0  lea     ecx, [rbp-48h]; dwFlags
0x1400051f3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400051f8  mov     [rbx+18h], rax
0x1400051fc  test    rax, rax
0x1400051ff  jz      short loc_14000521C
0x140005201  mov     dword ptr [rbx+20h], 5
0x140005208  lea     rcx, [rax+190h]
0x14000520f  jmp     short loc_140005217
0x140005211  mov     [rax], bp
0x140005214  add     rax, rbp
0x140005217  cmp     rax, rcx
0x14000521a  jnz     short loc_140005211
0x14000521c  mov     r9, [rbx+18h]
0x140005220  test    r9, r9
0x140005223  jz      short loc_140005294
0x140005225  test    esi, esi
0x140005227  jz      short loc_14000525A
0x140005229  mov     rcx, r9
0x14000522c  movzx   eax, word ptr [rbx+20h]
0x140005230  lea     rdx, [rax+rax*4]
0x140005234  shl     rdx, 4
0x140005238  add     rdx, r9
0x14000523b  cmp     r9, rdx
0x14000523e  jz      short loc_14000525A
0x140005240  mov     r8d, [rbx+10h]
0x140005244  cmp     [rcx+4], r8d
0x140005248  jbe     short loc_140005252
0x14000524a  mov     eax, [rdi+8]
0x14000524d  cmp     [rcx+8], eax
0x140005250  jz      short loc_140005294
0x140005252  add     rcx, rbp
0x140005255  cmp     rcx, rdx
0x140005258  jnz     short loc_140005244
0x14000525a  movzx   eax, word ptr [rbx+22h]
0x14000525e  inc     eax
0x140005260  movzx   ecx, word ptr [rbx+20h]
0x140005264  xor     edx, edx
0x140005266  div     ecx
0x140005268  mov     [rbx+22h], dx
0x14000526c  mov     rax, [rbx+8]
0x140005270  mov     r8d, 1
0x140005276  lock xadd [rax], r8d
0x14000527b  inc     r8d; unsigned int
0x14000527e  movzx   eax, dx
0x140005281  lea     rcx, [rax+rax*4]
0x140005285  shl     rcx, 4
0x140005289  add     rcx, r9; this
0x14000528c  mov     rdx, rdi; struct wil::FailureInfo *
0x14000528f  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005294  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000529e  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400052a5  add     rsp, 30h
0x1400052a9  pop     r14
0x1400052ab  pop     rdi
0x1400052ac  pop     rsi
0x1400052ad  pop     rbp
0x1400052ae  pop     rbx
0x1400052af  retn
```
