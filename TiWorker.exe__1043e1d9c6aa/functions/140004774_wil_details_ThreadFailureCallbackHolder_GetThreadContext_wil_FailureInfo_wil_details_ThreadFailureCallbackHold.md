# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004774`
- end: `0x140004850`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004114`
- `0x140004774`

## callees

- `0x140004774`
- `0x140005ef8`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  char *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rcx
  char *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx
  void *v18; // rcx

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( (__int64)(a4 - v12) > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        v18 = v13 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v18, v16, v15, v17);
        v14[v17 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004774  push    rbx
0x140004776  push    rbp
0x140004777  push    rsi
0x140004778  push    rdi
0x140004779  sub     rsp, 28h
0x14000477d  xor     al, al
0x14000477f  mov     byte ptr [r8], 0
0x140004783  mov     rbp, r9
0x140004786  mov     rdi, r8
0x140004789  mov     rsi, rdx
0x14000478c  mov     rbx, rcx
0x14000478f  test    rdx, rdx
0x140004792  jz      loc_140004847
0x140004798  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000479c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400047a1  mov     rdx, [rsi+20h]
0x1400047a5  test    rdx, rdx
0x1400047a8  jz      loc_140004847
0x1400047ae  cmp     dword ptr [rdx], 0
0x1400047b1  jnz     short loc_1400047C4
0x1400047b3  mov     eax, 1
0x1400047b8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400047c0  inc     eax
0x1400047c2  mov     [rdx], eax
0x1400047c4  cmp     dword ptr [rbx+50h], 0
0x1400047c8  jnz     short loc_1400047DB
0x1400047ca  movups  xmm0, xmmword ptr [rdx]
0x1400047cd  movups  xmmword ptr [rbx+50h], xmm0
0x1400047d1  movsd   xmm1, qword ptr [rdx+10h]
0x1400047d6  movsd   qword ptr [rbx+60h], xmm1
0x1400047db  movups  xmm0, xmmword ptr [rdx]
0x1400047de  lea     r10, [rdi+rbp]
0x1400047e2  movups  xmmword ptr [rbx+68h], xmm0
0x1400047e6  movsd   xmm1, qword ptr [rdx+10h]
0x1400047eb  movsd   qword ptr [rbx+78h], xmm1
0x1400047f0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400047f4  mov     rax, rbx
0x1400047f7  inc     rax
0x1400047fa  cmp     byte ptr [rdi+rax], 0
0x1400047fe  jnz     short loc_1400047F7
0x140004800  lea     rcx, [rax+rdi]
0x140004804  mov     rax, r10
0x140004807  sub     rax, rcx
0x14000480a  cmp     rax, 2
0x14000480e  jle     short loc_140004845
0x140004810  mov     byte ptr [rcx], 5Ch ; '\'
0x140004813  lea     rdi, [rcx+1]
0x140004817  mov     r8, [rdx+8]; Source
0x14000481b  inc     rbx
0x14000481e  cmp     byte ptr [r8+rbx], 0
0x140004823  jnz     short loc_14000481B
0x140004825  sub     r10, rdi
0x140004828  inc     rbx
0x14000482b  cmp     rbx, r10
0x14000482e  mov     rdx, r10; DestinationSize
0x140004831  mov     rcx, rdi; Destination
0x140004834  cmovnb  rbx, r10
0x140004838  mov     r9, rbx; SourceSize
0x14000483b  call    memcpy_s
0x140004840  mov     byte ptr [rbx+rdi-1], 0
0x140004845  mov     al, 1
0x140004847  add     rsp, 28h
0x14000484b  pop     rdi
0x14000484c  pop     rsi
0x14000484d  pop     rbp
0x14000484e  pop     rbx
0x14000484f  retn
```
