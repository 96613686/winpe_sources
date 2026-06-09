# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800056ac`
- end: `0x180005788`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fb0`
- `0x1800056ac`

## callees

- `0x1800056ac`
- `0x180008a78`

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
0x1800056ac  push    rbx
0x1800056ae  push    rbp
0x1800056af  push    rsi
0x1800056b0  push    rdi
0x1800056b1  sub     rsp, 28h
0x1800056b5  xor     al, al
0x1800056b7  mov     byte ptr [r8], 0
0x1800056bb  mov     rbp, r9
0x1800056be  mov     rdi, r8
0x1800056c1  mov     rsi, rdx
0x1800056c4  mov     rbx, rcx
0x1800056c7  test    rdx, rdx
0x1800056ca  jz      loc_18000577F
0x1800056d0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800056d4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800056d9  mov     rdx, [rsi+20h]
0x1800056dd  test    rdx, rdx
0x1800056e0  jz      loc_18000577F
0x1800056e6  cmp     dword ptr [rdx], 0
0x1800056e9  jnz     short loc_1800056FC
0x1800056eb  mov     eax, 1
0x1800056f0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800056f8  inc     eax
0x1800056fa  mov     [rdx], eax
0x1800056fc  cmp     dword ptr [rbx+50h], 0
0x180005700  jnz     short loc_180005713
0x180005702  movups  xmm0, xmmword ptr [rdx]
0x180005705  movups  xmmword ptr [rbx+50h], xmm0
0x180005709  movsd   xmm1, qword ptr [rdx+10h]
0x18000570e  movsd   qword ptr [rbx+60h], xmm1
0x180005713  movups  xmm0, xmmword ptr [rdx]
0x180005716  lea     r10, [rdi+rbp]
0x18000571a  movups  xmmword ptr [rbx+68h], xmm0
0x18000571e  movsd   xmm1, qword ptr [rdx+10h]
0x180005723  movsd   qword ptr [rbx+78h], xmm1
0x180005728  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000572c  mov     rax, rbx
0x18000572f  inc     rax
0x180005732  cmp     byte ptr [rdi+rax], 0
0x180005736  jnz     short loc_18000572F
0x180005738  lea     rcx, [rax+rdi]
0x18000573c  mov     rax, r10
0x18000573f  sub     rax, rcx
0x180005742  cmp     rax, 2
0x180005746  jle     short loc_18000577D
0x180005748  mov     byte ptr [rcx], 5Ch ; '\'
0x18000574b  lea     rdi, [rcx+1]
0x18000574f  mov     r8, [rdx+8]; Source
0x180005753  inc     rbx
0x180005756  cmp     byte ptr [r8+rbx], 0
0x18000575b  jnz     short loc_180005753
0x18000575d  sub     r10, rdi
0x180005760  inc     rbx
0x180005763  cmp     rbx, r10
0x180005766  mov     rdx, r10; DestinationSize
0x180005769  mov     rcx, rdi; Destination
0x18000576c  cmovnb  rbx, r10
0x180005770  mov     r9, rbx; SourceSize
0x180005773  call    memcpy_s
0x180005778  mov     byte ptr [rbx+rdi-1], 0
0x18000577d  mov     al, 1
0x18000577f  add     rsp, 28h
0x180005783  pop     rdi
0x180005784  pop     rsi
0x180005785  pop     rbp
0x180005786  pop     rbx
0x180005787  retn
```
