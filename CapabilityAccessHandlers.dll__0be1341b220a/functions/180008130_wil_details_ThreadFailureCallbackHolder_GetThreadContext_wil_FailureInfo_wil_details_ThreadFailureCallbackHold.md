# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180008130`
- end: `0x18000820c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007aa4`
- `0x180008130`

## callees

- `0x1800034d8`
- `0x180008130`

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
0x180008130  push    rbx
0x180008132  push    rbp
0x180008133  push    rsi
0x180008134  push    rdi
0x180008135  sub     rsp, 28h
0x180008139  xor     al, al
0x18000813b  mov     byte ptr [r8], 0
0x18000813f  mov     rbp, r9
0x180008142  mov     rdi, r8
0x180008145  mov     rsi, rdx
0x180008148  mov     rbx, rcx
0x18000814b  test    rdx, rdx
0x18000814e  jz      loc_180008203
0x180008154  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180008158  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000815d  mov     rdx, [rsi+20h]
0x180008161  test    rdx, rdx
0x180008164  jz      loc_180008203
0x18000816a  cmp     dword ptr [rdx], 0
0x18000816d  jnz     short loc_180008180
0x18000816f  mov     eax, 1
0x180008174  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000817c  inc     eax
0x18000817e  mov     [rdx], eax
0x180008180  cmp     dword ptr [rbx+50h], 0
0x180008184  jnz     short loc_180008197
0x180008186  movups  xmm0, xmmword ptr [rdx]
0x180008189  movups  xmmword ptr [rbx+50h], xmm0
0x18000818d  movsd   xmm1, qword ptr [rdx+10h]
0x180008192  movsd   qword ptr [rbx+60h], xmm1
0x180008197  movups  xmm0, xmmword ptr [rdx]
0x18000819a  lea     r10, [rdi+rbp]
0x18000819e  movups  xmmword ptr [rbx+68h], xmm0
0x1800081a2  movsd   xmm1, qword ptr [rdx+10h]
0x1800081a7  movsd   qword ptr [rbx+78h], xmm1
0x1800081ac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800081b0  mov     rax, rbx
0x1800081b3  inc     rax
0x1800081b6  cmp     byte ptr [rdi+rax], 0
0x1800081ba  jnz     short loc_1800081B3
0x1800081bc  lea     rcx, [rax+rdi]
0x1800081c0  mov     rax, r10
0x1800081c3  sub     rax, rcx
0x1800081c6  cmp     rax, 2
0x1800081ca  jle     short loc_180008201
0x1800081cc  mov     byte ptr [rcx], 5Ch ; '\'
0x1800081cf  lea     rdi, [rcx+1]
0x1800081d3  mov     r8, [rdx+8]; Source
0x1800081d7  inc     rbx
0x1800081da  cmp     byte ptr [r8+rbx], 0
0x1800081df  jnz     short loc_1800081D7
0x1800081e1  sub     r10, rdi
0x1800081e4  inc     rbx
0x1800081e7  cmp     rbx, r10
0x1800081ea  mov     rdx, r10; DestinationSize
0x1800081ed  mov     rcx, rdi; Destination
0x1800081f0  cmovnb  rbx, r10
0x1800081f4  mov     r9, rbx; SourceSize
0x1800081f7  call    memcpy_s
0x1800081fc  mov     byte ptr [rbx+rdi-1], 0
0x180008201  mov     al, 1
0x180008203  add     rsp, 28h
0x180008207  pop     rdi
0x180008208  pop     rsi
0x180008209  pop     rbp
0x18000820a  pop     rbx
0x18000820b  retn
```
