# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002f430`
- end: `0x18002f640`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(wil::details *this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000fd20`
- `0x18002ee80`
- `0x18002f200`
- `0x18002f2d0`
- `0x18002f430`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002f462`
- `KERNEL32!GetCurrentThreadId` at `0x18002f51c`
- `KERNEL32!GetCurrentThreadId` at `0x18002f462`
- `KERNEL32!GetCurrentThreadId` at `0x18002f51c`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  DWORD v11; // eax
  bool v12; // dl
  wil::details_abi *v13; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v15; // r8
  struct wil::details_abi::ThreadLocalData *v16; // rbx
  int v17; // esi
  _WORD *v18; // rax
  _WORD *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned __int16 v23; // dx

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = *(wil::details **)(v7 + 8 * (CurrentThreadId % 0xA));
    if ( this )
    {
      while ( *(_DWORD *)this != (_DWORD)CurrentThreadId )
      {
        this = (wil::details *)*((_QWORD *)this + 1);
        if ( !this )
          goto LABEL_5;
      }
      v9 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)this + 16);
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v9, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v10 = *v9;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
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
  v11 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v11 )
  {
    v13 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v13 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v11;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v13, v12);
      v16 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v17 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v17 )
          {
            v18 = wil::details::ProcessHeapAlloc(8u, 0x190u, v15);
            *((_QWORD *)v16 + 3) = v18;
            if ( v18 )
            {
              *((_DWORD *)v16 + 8) = 5;
              v19 = v18 + 200;
              do
              {
                *v18 = 80;
                v18 += 40;
              }
              while ( v18 != v19 );
            }
          }
        }
        v20 = *((_QWORD *)v16 + 3);
        if ( v20 )
        {
          if ( !v17 || (v21 = *((_QWORD *)v16 + 3), v22 = v20 + 80LL * *((unsigned __int16 *)v16 + 16), v20 == v22) )
          {
LABEL_33:
            v23 = ((unsigned int)*((unsigned __int16 *)v16 + 17) + 1) % *((unsigned __int16 *)v16 + 16);
            *((_WORD *)v16 + 17) = v23;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v20 + 80LL * v23),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v16 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v21 + 4) <= *((_DWORD *)v16 + 4) || *(_DWORD *)(v21 + 8) != *((_DWORD *)v5 + 2) )
            {
              v21 += 80;
              if ( v21 == v22 )
                goto LABEL_33;
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
0x18002f430  mov     [rsp+arg_18], rbx
0x18002f435  push    rbp
0x18002f436  push    rsi
0x18002f437  push    rdi
0x18002f438  push    r14
0x18002f43a  push    r15
0x18002f43c  sub     rsp, 20h
0x18002f440  mov     rbp, r8
0x18002f443  mov     r14, rdx
0x18002f446  mov     rdi, rcx
0x18002f449  mov     byte ptr [rdx], 0
0x18002f44c  xor     sil, sil
0x18002f44f  xor     r15d, r15d
0x18002f452  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002f459  test    rbx, rbx
0x18002f45c  jz      loc_18002F4EF
0x18002f462  call    cs:__imp_GetCurrentThreadId
0x18002f468  mov     r9d, eax
0x18002f46b  mov     r8d, eax
0x18002f46e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002f478  mul     r9
0x18002f47b  shr     rdx, 3
0x18002f47f  lea     rcx, [rdx+rdx*4]
0x18002f483  add     rcx, rcx
0x18002f486  sub     r8, rcx
0x18002f489  mov     rcx, [rbx+r8*8]
0x18002f48d  test    rcx, rcx
0x18002f490  jz      short loc_18002F4A0
0x18002f492  cmp     [rcx], r9d
0x18002f495  jz      short loc_18002F50A
0x18002f497  mov     rcx, [rcx+8]
0x18002f49b  test    rcx, rcx
0x18002f49e  jnz     short loc_18002F492
0x18002f4a0  mov     rbx, r15
0x18002f4a3  test    rbx, rbx
0x18002f4a6  jz      short loc_18002F4EF
0x18002f4a8  cmp     [rbx], r15
0x18002f4ab  jz      short loc_18002F4EF
0x18002f4ad  mov     [r14], sil
0x18002f4b0  mov     r9, rbp; unsigned __int64
0x18002f4b3  mov     r8, r14; char *
0x18002f4b6  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002f4b9  mov     rcx, rdi; struct wil::FailureInfo *
0x18002f4bc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002f4c1  test    al, al
0x18002f4c3  jz      short loc_18002F4C9
0x18002f4c5  mov     [rdi+48h], r14
0x18002f4c9  mov     rbx, [rbx]
0x18002f4cc  nop     dword ptr [rax+00h]
0x18002f4d0  mov     rcx, [rbx+8]
0x18002f4d4  mov     rax, [rcx]
0x18002f4d7  mov     rdx, rdi
0x18002f4da  mov     rax, [rax]
0x18002f4dd  call    cs:__guard_dispatch_icall_fptr
0x18002f4e3  or      sil, al
0x18002f4e6  mov     rbx, [rbx+10h]
0x18002f4ea  test    rbx, rbx
0x18002f4ed  jnz     short loc_18002F4D0
0x18002f4ef  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002f4f6  test    rax, rax
0x18002f4f9  jz      short loc_18002F51C
0x18002f4fb  test    sil, sil
0x18002f4fe  jnz     short loc_18002F510
0x18002f500  test    byte ptr [rdi+4], 2
0x18002f504  jnz     short loc_18002F510
0x18002f506  xor     ecx, ecx
0x18002f508  jmp     short loc_18002F512
0x18002f50a  lea     rbx, [rcx+10h]
0x18002f50e  jmp     short loc_18002F4A3
0x18002f510  mov     cl, 1
0x18002f512  mov     rdx, rdi
0x18002f515  call    cs:__guard_dispatch_icall_fptr
0x18002f51b  nop
0x18002f51c  call    cs:__imp_GetCurrentThreadId
0x18002f522  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002f528  cmp     ecx, eax
0x18002f52a  jz      loc_18002F62F
0x18002f530  mov     ebp, 1
0x18002f535  mov     ecx, ebp
0x18002f537  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002f53f  inc     ecx; this
0x18002f541  cmp     ecx, 4
0x18002f544  jge     loc_18002F628
0x18002f54a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002f550  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18002f555  mov     rbx, rax
0x18002f558  test    rax, rax
0x18002f55b  jz      loc_18002F621
0x18002f561  mov     esi, [rax+10h]
0x18002f564  cmp     qword ptr [rax+18h], 0
0x18002f569  jnz     short loc_18002F5AE
0x18002f56b  test    esi, esi
0x18002f56d  jz      short loc_18002F5AE
0x18002f56f  mov     edx, 190h; dwBytes
0x18002f574  mov     ecx, 8; dwFlags
0x18002f579  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002f57e  mov     [rbx+18h], rax
0x18002f582  test    rax, rax
0x18002f585  jz      short loc_18002F5AE
0x18002f587  mov     dword ptr [rbx+20h], 5
0x18002f58e  lea     rcx, [rax+190h]
0x18002f595  cmp     rax, rcx
0x18002f598  jz      short loc_18002F5AE
0x18002f59a  nop     word ptr [rax+rax+00h]
0x18002f5a0  mov     word ptr [rax], 50h ; 'P'
0x18002f5a5  add     rax, 50h ; 'P'
0x18002f5a9  cmp     rax, rcx
0x18002f5ac  jnz     short loc_18002F5A0
0x18002f5ae  mov     r9, [rbx+18h]
0x18002f5b2  test    r9, r9
0x18002f5b5  jz      short loc_18002F621
0x18002f5b7  test    esi, esi
0x18002f5b9  jz      short loc_18002F5ED
0x18002f5bb  mov     rcx, r9
0x18002f5be  movzx   eax, word ptr [rbx+20h]
0x18002f5c2  lea     rdx, [rax+rax*4]
0x18002f5c6  shl     rdx, 4
0x18002f5ca  add     rdx, r9
0x18002f5cd  cmp     r9, rdx
0x18002f5d0  jz      short loc_18002F5ED
0x18002f5d2  mov     r8d, [rbx+10h]
0x18002f5d6  cmp     [rcx+4], r8d
0x18002f5da  jbe     short loc_18002F5E4
0x18002f5dc  mov     eax, [rdi+8]
0x18002f5df  cmp     [rcx+8], eax
0x18002f5e2  jz      short loc_18002F621
0x18002f5e4  add     rcx, 50h ; 'P'
0x18002f5e8  cmp     rcx, rdx
0x18002f5eb  jnz     short loc_18002F5D6
0x18002f5ed  movzx   ecx, word ptr [rbx+20h]
0x18002f5f1  movzx   eax, word ptr [rbx+22h]
0x18002f5f5  inc     eax
0x18002f5f7  xor     edx, edx
0x18002f5f9  div     ecx
0x18002f5fb  mov     [rbx+22h], dx
0x18002f5ff  mov     rax, [rbx+8]
0x18002f603  lock xadd [rax], ebp
0x18002f607  lea     r8d, [rbp+1]; unsigned int
0x18002f60b  movzx   eax, dx
0x18002f60e  lea     rcx, [rax+rax*4]
0x18002f612  shl     rcx, 4
0x18002f616  add     rcx, r9; this
0x18002f619  mov     rdx, rdi; struct wil::FailureInfo *
0x18002f61c  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18002f621  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002f628  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002f62f  mov     rbx, [rsp+48h+arg_18]
0x18002f634  add     rsp, 20h
0x18002f638  pop     r15
0x18002f63a  pop     r14
0x18002f63c  pop     rdi
0x18002f63d  pop     rsi
0x18002f63e  pop     rbp
0x18002f63f  retn
```
