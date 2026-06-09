# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180009580`
- end: `0x180009675`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `245`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009580`
- `0x180009680`

## callees

- `0x180007c08`
- `0x180009580`

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
  __int64 v10; // rcx
  char *v11; // r10
  __int64 v12; // rax
  char *v13; // rbx
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // rcx
  rsize_t v17; // rbx

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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v11 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v10;
        while ( v15[v10] );
        v16 = v10 + 1;
        v17 = v11 - v14;
        if ( v16 < v11 - v14 )
          v17 = v16;
        memcpy_s(v14, v11 - v14, v15, v17);
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
0x180009580  mov     [rsp+arg_0], rbx
0x180009585  mov     [rsp+arg_8], rbp
0x18000958a  mov     [rsp+arg_10], rsi
0x18000958f  push    rdi
0x180009590  sub     rsp, 20h
0x180009594  xor     al, al
0x180009596  mov     byte ptr [r8], 0
0x18000959a  mov     rbp, r9
0x18000959d  mov     rbx, r8
0x1800095a0  mov     rsi, rdx
0x1800095a3  mov     rdi, rcx
0x1800095a6  test    rdx, rdx
0x1800095a9  jz      loc_180009660
0x1800095af  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800095b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800095b8  mov     rdx, [rsi+20h]
0x1800095bc  test    rdx, rdx
0x1800095bf  jz      loc_180009660
0x1800095c5  cmp     dword ptr [rdx], 0
0x1800095c8  jnz     short loc_1800095DB
0x1800095ca  mov     eax, 1
0x1800095cf  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800095d7  inc     eax
0x1800095d9  mov     [rdx], eax
0x1800095db  cmp     dword ptr [rdi+50h], 0
0x1800095df  jnz     short loc_1800095F2
0x1800095e1  movups  xmm0, xmmword ptr [rdx]
0x1800095e4  movups  xmmword ptr [rdi+50h], xmm0
0x1800095e8  movsd   xmm1, qword ptr [rdx+10h]
0x1800095ed  movsd   qword ptr [rdi+60h], xmm1
0x1800095f2  movups  xmm0, xmmword ptr [rdx]
0x1800095f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800095f9  lea     r10, [rbx+rbp]
0x1800095fd  mov     rax, rcx
0x180009600  movups  xmmword ptr [rdi+68h], xmm0
0x180009604  movsd   xmm1, qword ptr [rdx+10h]
0x180009609  movsd   qword ptr [rdi+78h], xmm1
0x18000960e  inc     rax
0x180009611  cmp     byte ptr [rbx+rax], 0
0x180009615  jnz     short loc_18000960E
0x180009617  add     rbx, rax
0x18000961a  mov     rax, r10
0x18000961d  sub     rax, rbx
0x180009620  cmp     rax, 2
0x180009624  jle     short loc_18000965E
0x180009626  mov     byte ptr [rbx], 5Ch ; '\'
0x180009629  lea     rdi, [rbx+1]
0x18000962d  mov     r8, [rdx+8]; Source
0x180009631  inc     rcx
0x180009634  cmp     byte ptr [r8+rcx], 0
0x180009639  jnz     short loc_180009631
0x18000963b  inc     rcx
0x18000963e  sub     r10, rdi
0x180009641  cmp     rcx, r10
0x180009644  mov     rbx, r10
0x180009647  mov     rdx, r10; DestinationSize
0x18000964a  cmovb   rbx, rcx
0x18000964e  mov     rcx, rdi; Destination
0x180009651  mov     r9, rbx; SourceSize
0x180009654  call    memcpy_s
0x180009659  mov     byte ptr [rbx+rdi-1], 0
0x18000965e  mov     al, 1
0x180009660  mov     rbx, [rsp+28h+arg_0]
0x180009665  mov     rbp, [rsp+28h+arg_8]
0x18000966a  mov     rsi, [rsp+28h+arg_10]
0x18000966f  add     rsp, 20h
0x180009673  pop     rdi
0x180009674  retn
```
