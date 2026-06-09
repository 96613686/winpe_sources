# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006060`
- end: `0x180006267`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006060`
- `0x180006e7c`
- `0x180006fac`
- `0x180007dfc`
- `0x180009748`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000608a`
- `KERNEL32!GetCurrentThreadId` at `0x18000614c`
- `KERNEL32!GetCurrentThreadId` at `0x18000608a`
- `KERNEL32!GetCurrentThreadId` at `0x18000614c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180006060  push    rbx
0x180006062  push    rbp
0x180006063  push    rsi
0x180006064  push    rdi
0x180006065  push    r14
0x180006067  sub     rsp, 20h
0x18000606b  mov     r14, r8
0x18000606e  mov     rsi, rdx
0x180006071  mov     rdi, rcx
0x180006074  mov     byte ptr [rdx], 0
0x180006077  xor     bpl, bpl
0x18000607a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006081  test    rbx, rbx
0x180006084  jz      loc_180006120
0x18000608a  call    cs:__imp_GetCurrentThreadId
0x180006090  mov     r9d, eax
0x180006093  mov     r8d, eax
0x180006096  shr     r8, 2
0x18000609a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800060a4  mul     r8
0x1800060a7  shr     rdx, 3
0x1800060ab  lea     rcx, [rdx+rdx*4]
0x1800060af  add     rcx, rcx
0x1800060b2  sub     r8, rcx
0x1800060b5  mov     rbx, [rbx+r8*8]
0x1800060b9  jmp     short loc_1800060C4
0x1800060bb  cmp     [rbx], r9d
0x1800060be  jz      short loc_18000613B
0x1800060c0  mov     rbx, [rbx+8]
0x1800060c4  test    rbx, rbx
0x1800060c7  jnz     short loc_1800060BB
0x1800060c9  test    rbx, rbx
0x1800060cc  jz      short loc_180006120
0x1800060ce  cmp     qword ptr [rbx], 0
0x1800060d2  jz      short loc_180006120
0x1800060d4  mov     byte ptr [rsi], 0
0x1800060d7  mov     r9, r14; unsigned __int64
0x1800060da  mov     r8, rsi; char *
0x1800060dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800060e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800060e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800060e8  test    al, al
0x1800060ea  jz      short loc_1800060F0
0x1800060ec  mov     [rdi+48h], rsi
0x1800060f0  mov     rbx, [rbx]
0x1800060f3  mov     al, [rbx+28h]
0x1800060f6  mov     byte ptr [rbx+28h], 1
0x1800060fa  test    al, al
0x1800060fc  jnz     short loc_180006117
0x1800060fe  mov     rcx, [rbx+8]
0x180006102  mov     rax, [rcx]
0x180006105  mov     rdx, rdi
0x180006108  mov     rax, [rax]
0x18000610b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006110  or      bpl, al
0x180006113  mov     byte ptr [rbx+28h], 0
0x180006117  mov     rbx, [rbx+10h]
0x18000611b  test    rbx, rbx
0x18000611e  jnz     short loc_1800060F3
0x180006120  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006127  test    rax, rax
0x18000612a  jz      short loc_18000614C
0x18000612c  test    bpl, bpl
0x18000612f  jnz     short loc_180006141
0x180006131  test    byte ptr [rdi+4], 2
0x180006135  jnz     short loc_180006141
0x180006137  xor     ecx, ecx
0x180006139  jmp     short loc_180006143
0x18000613b  add     rbx, 10h
0x18000613f  jmp     short loc_1800060C9
0x180006141  mov     cl, 1
0x180006143  mov     rdx, rdi
0x180006146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614b  nop
0x18000614c  call    cs:__imp_GetCurrentThreadId
0x180006152  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006158  cmp     ecx, eax
0x18000615a  jz      loc_18000625C
0x180006160  mov     ecx, 1
0x180006165  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000616d  inc     ecx; this
0x18000616f  cmp     ecx, 4
0x180006172  jge     loc_180006255
0x180006178  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000617e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006183  mov     rbx, rax
0x180006186  test    rax, rax
0x180006189  jz      loc_18000624B
0x18000618f  mov     esi, [rax+10h]
0x180006192  mov     ebp, 50h ; 'P'
0x180006197  cmp     qword ptr [rax+18h], 0
0x18000619c  jnz     short loc_1800061D3
0x18000619e  test    esi, esi
0x1800061a0  jz      short loc_1800061D3
0x1800061a2  mov     edx, 190h; dwBytes
0x1800061a7  lea     ecx, [rbp-48h]; dwFlags
0x1800061aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800061af  mov     [rbx+18h], rax
0x1800061b3  test    rax, rax
0x1800061b6  jz      short loc_1800061D3
0x1800061b8  mov     dword ptr [rbx+20h], 5
0x1800061bf  lea     rcx, [rax+190h]
0x1800061c6  jmp     short loc_1800061CE
0x1800061c8  mov     [rax], bp
0x1800061cb  add     rax, rbp
0x1800061ce  cmp     rax, rcx
0x1800061d1  jnz     short loc_1800061C8
0x1800061d3  mov     r9, [rbx+18h]
0x1800061d7  test    r9, r9
0x1800061da  jz      short loc_18000624B
0x1800061dc  test    esi, esi
0x1800061de  jz      short loc_180006211
0x1800061e0  mov     rcx, r9
0x1800061e3  movzx   eax, word ptr [rbx+20h]
0x1800061e7  lea     rdx, [rax+rax*4]
0x1800061eb  shl     rdx, 4
0x1800061ef  add     rdx, r9
0x1800061f2  cmp     r9, rdx
0x1800061f5  jz      short loc_180006211
0x1800061f7  mov     r8d, [rbx+10h]
0x1800061fb  cmp     [rcx+4], r8d
0x1800061ff  jbe     short loc_180006209
0x180006201  mov     eax, [rdi+8]
0x180006204  cmp     [rcx+8], eax
0x180006207  jz      short loc_18000624B
0x180006209  add     rcx, rbp
0x18000620c  cmp     rcx, rdx
0x18000620f  jnz     short loc_1800061FB
0x180006211  movzx   eax, word ptr [rbx+22h]
0x180006215  inc     eax
0x180006217  movzx   ecx, word ptr [rbx+20h]
0x18000621b  xor     edx, edx
0x18000621d  div     ecx
0x18000621f  mov     [rbx+22h], dx
0x180006223  mov     rax, [rbx+8]
0x180006227  mov     r8d, 1
0x18000622d  lock xadd [rax], r8d
0x180006232  inc     r8d; unsigned int
0x180006235  movzx   eax, dx
0x180006238  lea     rcx, [rax+rax*4]
0x18000623c  shl     rcx, 4
0x180006240  add     rcx, r9; this
0x180006243  mov     rdx, rdi; struct wil::FailureInfo *
0x180006246  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000624b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006255  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000625c  add     rsp, 20h
0x180006260  pop     r14
0x180006262  pop     rdi
0x180006263  pop     rsi
0x180006264  pop     rbp
0x180006265  pop     rbx
0x180006266  retn
```
