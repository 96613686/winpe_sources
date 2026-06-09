# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000481c`
- end: `0x1400048f8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004120`
- `0x14000481c`

## callees

- `0x14000481c`
- `0x1400064c8`

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
0x14000481c  push    rbx
0x14000481e  push    rbp
0x14000481f  push    rsi
0x140004820  push    rdi
0x140004821  sub     rsp, 28h
0x140004825  xor     al, al
0x140004827  mov     byte ptr [r8], 0
0x14000482b  mov     rbp, r9
0x14000482e  mov     rdi, r8
0x140004831  mov     rsi, rdx
0x140004834  mov     rbx, rcx
0x140004837  test    rdx, rdx
0x14000483a  jz      loc_1400048EF
0x140004840  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004844  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004849  mov     rdx, [rsi+20h]
0x14000484d  test    rdx, rdx
0x140004850  jz      loc_1400048EF
0x140004856  cmp     dword ptr [rdx], 0
0x140004859  jnz     short loc_14000486C
0x14000485b  mov     eax, 1
0x140004860  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004868  inc     eax
0x14000486a  mov     [rdx], eax
0x14000486c  cmp     dword ptr [rbx+50h], 0
0x140004870  jnz     short loc_140004883
0x140004872  movups  xmm0, xmmword ptr [rdx]
0x140004875  movups  xmmword ptr [rbx+50h], xmm0
0x140004879  movsd   xmm1, qword ptr [rdx+10h]
0x14000487e  movsd   qword ptr [rbx+60h], xmm1
0x140004883  movups  xmm0, xmmword ptr [rdx]
0x140004886  lea     r10, [rdi+rbp]
0x14000488a  movups  xmmword ptr [rbx+68h], xmm0
0x14000488e  movsd   xmm1, qword ptr [rdx+10h]
0x140004893  movsd   qword ptr [rbx+78h], xmm1
0x140004898  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000489c  mov     rax, rbx
0x14000489f  inc     rax
0x1400048a2  cmp     byte ptr [rdi+rax], 0
0x1400048a6  jnz     short loc_14000489F
0x1400048a8  lea     rcx, [rax+rdi]
0x1400048ac  mov     rax, r10
0x1400048af  sub     rax, rcx
0x1400048b2  cmp     rax, 2
0x1400048b6  jle     short loc_1400048ED
0x1400048b8  mov     byte ptr [rcx], 5Ch ; '\'
0x1400048bb  lea     rdi, [rcx+1]
0x1400048bf  mov     r8, [rdx+8]; Source
0x1400048c3  inc     rbx
0x1400048c6  cmp     byte ptr [r8+rbx], 0
0x1400048cb  jnz     short loc_1400048C3
0x1400048cd  sub     r10, rdi
0x1400048d0  inc     rbx
0x1400048d3  cmp     rbx, r10
0x1400048d6  mov     rdx, r10; DestinationSize
0x1400048d9  mov     rcx, rdi; Destination
0x1400048dc  cmovnb  rbx, r10
0x1400048e0  mov     r9, rbx; SourceSize
0x1400048e3  call    memcpy_s
0x1400048e8  mov     byte ptr [rbx+rdi-1], 0
0x1400048ed  mov     al, 1
0x1400048ef  add     rsp, 28h
0x1400048f3  pop     rdi
0x1400048f4  pop     rsi
0x1400048f5  pop     rbp
0x1400048f6  pop     rbx
0x1400048f7  retn
```
