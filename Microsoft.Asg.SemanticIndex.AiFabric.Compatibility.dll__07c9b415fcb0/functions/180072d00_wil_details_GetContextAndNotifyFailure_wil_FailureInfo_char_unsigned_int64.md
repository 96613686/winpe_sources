# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180072d00`
- end: `0x180072f28`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `552`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000c8b0`
- `0x1800726b0`
- `0x180072a30`
- `0x180072ba0`
- `0x180072d00`
- `0x180242120`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180072d3a`
- `KERNEL32!GetCurrentThreadId` at `0x180072dfc`
- `KERNEL32!GetCurrentThreadId` at `0x180072d3a`
- `KERNEL32!GetCurrentThreadId` at `0x180072dfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v14; // r8
  struct wil::details_abi::ThreadLocalData *v15; // rbx
  int v16; // esi
  _WORD *v17; // rax
  _WORD *v18; // rcx
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned __int16 v22; // dx

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
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v11;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(0, v12);
      v15 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v16 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v16 )
          {
            v17 = wil::details::ProcessHeapAlloc(8u, 0x190u, v14);
            *((_QWORD *)v15 + 3) = v17;
            if ( v17 )
            {
              *((_DWORD *)v15 + 8) = 5;
              v18 = v17 + 200;
              do
              {
                *v17 = 80;
                v17 += 40;
              }
              while ( v17 != v18 );
            }
          }
        }
        v19 = *((_QWORD *)v15 + 3);
        if ( v19 )
        {
          if ( !v16 || (v20 = *((_QWORD *)v15 + 3), v21 = v19 + 80LL * *((unsigned __int16 *)v15 + 16), v19 == v21) )
          {
LABEL_33:
            v22 = ((unsigned int)*((unsigned __int16 *)v15 + 17) + 1) % *((unsigned __int16 *)v15 + 16);
            *((_WORD *)v15 + 17) = v22;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v19 + 80LL * v22),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v15 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v20 + 4) <= *((_DWORD *)v15 + 4) || *(_DWORD *)(v20 + 8) != *((_DWORD *)v5 + 2) )
            {
              v20 += 80;
              if ( v20 == v21 )
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
0x180072d00  mov     [rsp+arg_0], rbx
0x180072d05  mov     [rsp+arg_8], rbp
0x180072d0a  mov     [rsp+arg_10], rsi
0x180072d0f  push    rdi
0x180072d10  push    r14
0x180072d12  push    r15
0x180072d14  sub     rsp, 20h
0x180072d18  mov     rbp, r8
0x180072d1b  mov     r14, rdx
0x180072d1e  mov     rdi, rcx
0x180072d21  mov     byte ptr [rdx], 0
0x180072d24  xor     sil, sil
0x180072d27  xor     r15d, r15d
0x180072d2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180072d31  test    rbx, rbx
0x180072d34  jz      loc_180072DCF
0x180072d3a  call    cs:__imp_GetCurrentThreadId
0x180072d40  mov     r9d, eax
0x180072d43  mov     r8d, eax
0x180072d46  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180072d50  mul     r9
0x180072d53  shr     rdx, 3
0x180072d57  lea     rcx, [rdx+rdx*4]
0x180072d5b  add     rcx, rcx
0x180072d5e  sub     r8, rcx
0x180072d61  mov     rcx, [rbx+r8*8]
0x180072d65  test    rcx, rcx
0x180072d68  jz      short loc_180072D7E
0x180072d6a  nop     word ptr [rax+rax+00h]
0x180072d70  cmp     [rcx], r9d
0x180072d73  jz      short loc_180072DEA
0x180072d75  mov     rcx, [rcx+8]
0x180072d79  test    rcx, rcx
0x180072d7c  jnz     short loc_180072D70
0x180072d7e  mov     rbx, r15
0x180072d81  test    rbx, rbx
0x180072d84  jz      short loc_180072DCF
0x180072d86  cmp     [rbx], r15
0x180072d89  jz      short loc_180072DCF
0x180072d8b  mov     [r14], sil
0x180072d8e  mov     r9, rbp; unsigned __int64
0x180072d91  mov     r8, r14; char *
0x180072d94  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180072d97  mov     rcx, rdi; struct wil::FailureInfo *
0x180072d9a  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180072d9f  test    al, al
0x180072da1  jz      short loc_180072DA7
0x180072da3  mov     [rdi+48h], r14
0x180072da7  mov     rbx, [rbx]
0x180072daa  nop     word ptr [rax+rax+00h]
0x180072db0  mov     rcx, [rbx+8]
0x180072db4  mov     rax, [rcx]
0x180072db7  mov     rdx, rdi
0x180072dba  mov     rax, [rax]
0x180072dbd  call    cs:__guard_dispatch_icall_fptr
0x180072dc3  or      sil, al
0x180072dc6  mov     rbx, [rbx+10h]
0x180072dca  test    rbx, rbx
0x180072dcd  jnz     short loc_180072DB0
0x180072dcf  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180072dd6  test    rax, rax
0x180072dd9  jz      short loc_180072DFC
0x180072ddb  test    sil, sil
0x180072dde  jnz     short loc_180072DF0
0x180072de0  test    byte ptr [rdi+4], 2
0x180072de4  jnz     short loc_180072DF0
0x180072de6  xor     ecx, ecx
0x180072de8  jmp     short loc_180072DF2
0x180072dea  lea     rbx, [rcx+10h]
0x180072dee  jmp     short loc_180072D81
0x180072df0  mov     cl, 1
0x180072df2  mov     rdx, rdi
0x180072df5  call    cs:__guard_dispatch_icall_fptr
0x180072dfb  nop
0x180072dfc  call    cs:__imp_GetCurrentThreadId
0x180072e02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180072e08  cmp     ecx, eax
0x180072e0a  jz      loc_180072F0F
0x180072e10  mov     ebp, 1
0x180072e15  mov     ecx, ebp
0x180072e17  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180072e1f  inc     ecx
0x180072e21  cmp     ecx, 4
0x180072e24  jge     loc_180072F08
0x180072e2a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180072e30  xor     ecx, ecx; this
0x180072e32  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180072e37  mov     rbx, rax
0x180072e3a  test    rax, rax
0x180072e3d  jz      loc_180072F01
0x180072e43  mov     esi, [rax+10h]
0x180072e46  cmp     qword ptr [rax+18h], 0
0x180072e4b  jnz     short loc_180072E8E
0x180072e4d  test    esi, esi
0x180072e4f  jz      short loc_180072E8E
0x180072e51  mov     edx, 190h; dwBytes
0x180072e56  mov     ecx, 8; dwFlags
0x180072e5b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180072e60  mov     [rbx+18h], rax
0x180072e64  test    rax, rax
0x180072e67  jz      short loc_180072E8E
0x180072e69  mov     dword ptr [rbx+20h], 5
0x180072e70  lea     rcx, [rax+190h]
0x180072e77  cmp     rax, rcx
0x180072e7a  jz      short loc_180072E8E
0x180072e7c  nop     dword ptr [rax+00h]
0x180072e80  mov     word ptr [rax], 50h ; 'P'
0x180072e85  add     rax, 50h ; 'P'
0x180072e89  cmp     rax, rcx
0x180072e8c  jnz     short loc_180072E80
0x180072e8e  mov     r9, [rbx+18h]
0x180072e92  test    r9, r9
0x180072e95  jz      short loc_180072F01
0x180072e97  test    esi, esi
0x180072e99  jz      short loc_180072ECD
0x180072e9b  mov     rcx, r9
0x180072e9e  movzx   eax, word ptr [rbx+20h]
0x180072ea2  lea     rdx, [rax+rax*4]
0x180072ea6  shl     rdx, 4
0x180072eaa  add     rdx, r9
0x180072ead  cmp     r9, rdx
0x180072eb0  jz      short loc_180072ECD
0x180072eb2  mov     r8d, [rbx+10h]
0x180072eb6  cmp     [rcx+4], r8d
0x180072eba  jbe     short loc_180072EC4
0x180072ebc  mov     eax, [rdi+8]
0x180072ebf  cmp     [rcx+8], eax
0x180072ec2  jz      short loc_180072F01
0x180072ec4  add     rcx, 50h ; 'P'
0x180072ec8  cmp     rcx, rdx
0x180072ecb  jnz     short loc_180072EB6
0x180072ecd  movzx   ecx, word ptr [rbx+20h]
0x180072ed1  movzx   eax, word ptr [rbx+22h]
0x180072ed5  inc     eax
0x180072ed7  xor     edx, edx
0x180072ed9  div     ecx
0x180072edb  mov     [rbx+22h], dx
0x180072edf  mov     rax, [rbx+8]
0x180072ee3  lock xadd [rax], ebp
0x180072ee7  lea     r8d, [rbp+1]; unsigned int
0x180072eeb  movzx   eax, dx
0x180072eee  lea     rcx, [rax+rax*4]
0x180072ef2  shl     rcx, 4
0x180072ef6  add     rcx, r9; this
0x180072ef9  mov     rdx, rdi; struct wil::FailureInfo *
0x180072efc  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180072f01  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180072f08  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180072f0f  mov     rbx, [rsp+38h+arg_0]
0x180072f14  mov     rbp, [rsp+38h+arg_8]
0x180072f19  mov     rsi, [rsp+38h+arg_10]
0x180072f1e  add     rsp, 20h
0x180072f22  pop     r15
0x180072f24  pop     r14
0x180072f26  pop     rdi
0x180072f27  retn
```
