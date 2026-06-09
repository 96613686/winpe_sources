# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000684c`
- end: `0x140006928`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005980`
- `0x14000684c`

## callees

- `0x14000684c`
- `0x14000c1a4`

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
0x14000684c  push    rbx
0x14000684e  push    rbp
0x14000684f  push    rsi
0x140006850  push    rdi
0x140006851  sub     rsp, 28h
0x140006855  xor     al, al
0x140006857  mov     byte ptr [r8], 0
0x14000685b  mov     rbp, r9
0x14000685e  mov     rdi, r8
0x140006861  mov     rsi, rdx
0x140006864  mov     rbx, rcx
0x140006867  test    rdx, rdx
0x14000686a  jz      loc_14000691F
0x140006870  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140006874  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006879  mov     rdx, [rsi+20h]
0x14000687d  test    rdx, rdx
0x140006880  jz      loc_14000691F
0x140006886  cmp     dword ptr [rdx], 0
0x140006889  jnz     short loc_14000689C
0x14000688b  mov     eax, 1
0x140006890  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140006898  inc     eax
0x14000689a  mov     [rdx], eax
0x14000689c  cmp     dword ptr [rbx+50h], 0
0x1400068a0  jnz     short loc_1400068B3
0x1400068a2  movups  xmm0, xmmword ptr [rdx]
0x1400068a5  movups  xmmword ptr [rbx+50h], xmm0
0x1400068a9  movsd   xmm1, qword ptr [rdx+10h]
0x1400068ae  movsd   qword ptr [rbx+60h], xmm1
0x1400068b3  movups  xmm0, xmmword ptr [rdx]
0x1400068b6  lea     r10, [rdi+rbp]
0x1400068ba  movups  xmmword ptr [rbx+68h], xmm0
0x1400068be  movsd   xmm1, qword ptr [rdx+10h]
0x1400068c3  movsd   qword ptr [rbx+78h], xmm1
0x1400068c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400068cc  mov     rax, rbx
0x1400068cf  inc     rax
0x1400068d2  cmp     byte ptr [rdi+rax], 0
0x1400068d6  jnz     short loc_1400068CF
0x1400068d8  lea     rcx, [rax+rdi]
0x1400068dc  mov     rax, r10
0x1400068df  sub     rax, rcx
0x1400068e2  cmp     rax, 2
0x1400068e6  jle     short loc_14000691D
0x1400068e8  mov     byte ptr [rcx], 5Ch ; '\'
0x1400068eb  lea     rdi, [rcx+1]
0x1400068ef  mov     r8, [rdx+8]; Source
0x1400068f3  inc     rbx
0x1400068f6  cmp     byte ptr [r8+rbx], 0
0x1400068fb  jnz     short loc_1400068F3
0x1400068fd  sub     r10, rdi
0x140006900  inc     rbx
0x140006903  cmp     rbx, r10
0x140006906  mov     rdx, r10; DestinationSize
0x140006909  mov     rcx, rdi; Destination
0x14000690c  cmovnb  rbx, r10
0x140006910  mov     r9, rbx; SourceSize
0x140006913  call    memcpy_s
0x140006918  mov     byte ptr [rbx+rdi-1], 0
0x14000691d  mov     al, 1
0x14000691f  add     rsp, 28h
0x140006923  pop     rdi
0x140006924  pop     rsi
0x140006925  pop     rbp
0x140006926  pop     rbx
0x140006927  retn
```
