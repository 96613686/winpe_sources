# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400088b0`
- end: `0x140008ab7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400088b0`
- `0x140008cf0`
- `0x140008dd4`
- `0x140009228`
- `0x14000a5c4`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400088da`
- `KERNEL32!GetCurrentThreadId` at `0x14000899c`
- `KERNEL32!GetCurrentThreadId` at `0x1400088da`
- `KERNEL32!GetCurrentThreadId` at `0x14000899c`

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
0x1400088b0  push    rbx
0x1400088b2  push    rbp
0x1400088b3  push    rsi
0x1400088b4  push    rdi
0x1400088b5  push    r14
0x1400088b7  sub     rsp, 20h
0x1400088bb  mov     r14, r8
0x1400088be  mov     rsi, rdx
0x1400088c1  mov     rdi, rcx
0x1400088c4  mov     byte ptr [rdx], 0
0x1400088c7  xor     bpl, bpl
0x1400088ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400088d1  test    rbx, rbx
0x1400088d4  jz      loc_140008970
0x1400088da  call    cs:__imp_GetCurrentThreadId
0x1400088e0  mov     r9d, eax
0x1400088e3  mov     r8d, eax
0x1400088e6  shr     r8, 2
0x1400088ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400088f4  mul     r8
0x1400088f7  shr     rdx, 3
0x1400088fb  lea     rcx, [rdx+rdx*4]
0x1400088ff  add     rcx, rcx
0x140008902  sub     r8, rcx
0x140008905  mov     rbx, [rbx+r8*8]
0x140008909  jmp     short loc_140008914
0x14000890b  cmp     [rbx], r9d
0x14000890e  jz      short loc_14000898B
0x140008910  mov     rbx, [rbx+8]
0x140008914  test    rbx, rbx
0x140008917  jnz     short loc_14000890B
0x140008919  test    rbx, rbx
0x14000891c  jz      short loc_140008970
0x14000891e  cmp     qword ptr [rbx], 0
0x140008922  jz      short loc_140008970
0x140008924  mov     [rsi], bpl
0x140008927  mov     r9, r14; unsigned __int64
0x14000892a  mov     r8, rsi; char *
0x14000892d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140008930  mov     rcx, rdi; struct wil::FailureInfo *
0x140008933  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140008938  test    al, al
0x14000893a  jz      short loc_140008940
0x14000893c  mov     [rdi+48h], rsi
0x140008940  mov     rbx, [rbx]
0x140008943  mov     al, [rbx+28h]
0x140008946  mov     byte ptr [rbx+28h], 1
0x14000894a  test    al, al
0x14000894c  jnz     short loc_140008967
0x14000894e  mov     rcx, [rbx+8]
0x140008952  mov     rax, [rcx]
0x140008955  mov     rdx, rdi
0x140008958  mov     rax, [rax]
0x14000895b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008960  or      bpl, al
0x140008963  mov     byte ptr [rbx+28h], 0
0x140008967  mov     rbx, [rbx+10h]
0x14000896b  test    rbx, rbx
0x14000896e  jnz     short loc_140008943
0x140008970  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140008977  test    rax, rax
0x14000897a  jz      short loc_14000899C
0x14000897c  test    bpl, bpl
0x14000897f  jnz     short loc_140008991
0x140008981  test    byte ptr [rdi+4], 2
0x140008985  jnz     short loc_140008991
0x140008987  xor     ecx, ecx
0x140008989  jmp     short loc_140008993
0x14000898b  add     rbx, 10h
0x14000898f  jmp     short loc_140008919
0x140008991  mov     cl, 1
0x140008993  mov     rdx, rdi
0x140008996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000899b  nop
0x14000899c  call    cs:__imp_GetCurrentThreadId
0x1400089a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400089a8  cmp     ecx, eax
0x1400089aa  jz      loc_140008AAC
0x1400089b0  mov     ecx, 1
0x1400089b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400089bd  inc     ecx; this
0x1400089bf  cmp     ecx, 4
0x1400089c2  jge     loc_140008AA5
0x1400089c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400089ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400089d3  mov     rbx, rax
0x1400089d6  test    rax, rax
0x1400089d9  jz      loc_140008A9B
0x1400089df  mov     esi, [rax+10h]
0x1400089e2  mov     ebp, 50h ; 'P'
0x1400089e7  cmp     qword ptr [rax+18h], 0
0x1400089ec  jnz     short loc_140008A23
0x1400089ee  test    esi, esi
0x1400089f0  jz      short loc_140008A23
0x1400089f2  mov     edx, 190h; dwBytes
0x1400089f7  lea     ecx, [rbp-48h]; dwFlags
0x1400089fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400089ff  mov     [rbx+18h], rax
0x140008a03  test    rax, rax
0x140008a06  jz      short loc_140008A23
0x140008a08  mov     dword ptr [rbx+20h], 5
0x140008a0f  lea     rcx, [rax+190h]
0x140008a16  jmp     short loc_140008A1E
0x140008a18  mov     [rax], bp
0x140008a1b  add     rax, rbp
0x140008a1e  cmp     rax, rcx
0x140008a21  jnz     short loc_140008A18
0x140008a23  mov     r9, [rbx+18h]
0x140008a27  test    r9, r9
0x140008a2a  jz      short loc_140008A9B
0x140008a2c  test    esi, esi
0x140008a2e  jz      short loc_140008A61
0x140008a30  mov     rcx, r9
0x140008a33  movzx   eax, word ptr [rbx+20h]
0x140008a37  lea     rdx, [rax+rax*4]
0x140008a3b  shl     rdx, 4
0x140008a3f  add     rdx, r9
0x140008a42  cmp     r9, rdx
0x140008a45  jz      short loc_140008A61
0x140008a47  mov     r8d, [rbx+10h]
0x140008a4b  cmp     [rcx+4], r8d
0x140008a4f  jbe     short loc_140008A59
0x140008a51  mov     eax, [rdi+8]
0x140008a54  cmp     [rcx+8], eax
0x140008a57  jz      short loc_140008A9B
0x140008a59  add     rcx, rbp
0x140008a5c  cmp     rcx, rdx
0x140008a5f  jnz     short loc_140008A4B
0x140008a61  movzx   eax, word ptr [rbx+22h]
0x140008a65  inc     eax
0x140008a67  movzx   ecx, word ptr [rbx+20h]
0x140008a6b  xor     edx, edx
0x140008a6d  div     ecx
0x140008a6f  mov     [rbx+22h], dx
0x140008a73  mov     rax, [rbx+8]
0x140008a77  mov     r8d, 1
0x140008a7d  lock xadd [rax], r8d
0x140008a82  inc     r8d; unsigned int
0x140008a85  movzx   eax, dx
0x140008a88  lea     rcx, [rax+rax*4]
0x140008a8c  shl     rcx, 4
0x140008a90  add     rcx, r9; this
0x140008a93  mov     rdx, rdi; struct wil::FailureInfo *
0x140008a96  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140008a9b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140008aa5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140008aac  add     rsp, 20h
0x140008ab0  pop     r14
0x140008ab2  pop     rdi
0x140008ab3  pop     rsi
0x140008ab4  pop     rbp
0x140008ab5  pop     rbx
0x140008ab6  retn
```
