# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000584c`
- end: `0x180005928`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005150`
- `0x18000584c`

## callees

- `0x18000584c`
- `0x180008c28`

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
0x18000584c  push    rbx
0x18000584e  push    rbp
0x18000584f  push    rsi
0x180005850  push    rdi
0x180005851  sub     rsp, 28h
0x180005855  xor     al, al
0x180005857  mov     byte ptr [r8], 0
0x18000585b  mov     rbp, r9
0x18000585e  mov     rdi, r8
0x180005861  mov     rsi, rdx
0x180005864  mov     rbx, rcx
0x180005867  test    rdx, rdx
0x18000586a  jz      loc_18000591F
0x180005870  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005874  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005879  mov     rdx, [rsi+20h]
0x18000587d  test    rdx, rdx
0x180005880  jz      loc_18000591F
0x180005886  cmp     dword ptr [rdx], 0
0x180005889  jnz     short loc_18000589C
0x18000588b  mov     eax, 1
0x180005890  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005898  inc     eax
0x18000589a  mov     [rdx], eax
0x18000589c  cmp     dword ptr [rbx+50h], 0
0x1800058a0  jnz     short loc_1800058B3
0x1800058a2  movups  xmm0, xmmword ptr [rdx]
0x1800058a5  movups  xmmword ptr [rbx+50h], xmm0
0x1800058a9  movsd   xmm1, qword ptr [rdx+10h]
0x1800058ae  movsd   qword ptr [rbx+60h], xmm1
0x1800058b3  movups  xmm0, xmmword ptr [rdx]
0x1800058b6  lea     r10, [rdi+rbp]
0x1800058ba  movups  xmmword ptr [rbx+68h], xmm0
0x1800058be  movsd   xmm1, qword ptr [rdx+10h]
0x1800058c3  movsd   qword ptr [rbx+78h], xmm1
0x1800058c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800058cc  mov     rax, rbx
0x1800058cf  inc     rax
0x1800058d2  cmp     byte ptr [rdi+rax], 0
0x1800058d6  jnz     short loc_1800058CF
0x1800058d8  lea     rcx, [rax+rdi]
0x1800058dc  mov     rax, r10
0x1800058df  sub     rax, rcx
0x1800058e2  cmp     rax, 2
0x1800058e6  jle     short loc_18000591D
0x1800058e8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800058eb  lea     rdi, [rcx+1]
0x1800058ef  mov     r8, [rdx+8]; Source
0x1800058f3  inc     rbx
0x1800058f6  cmp     byte ptr [r8+rbx], 0
0x1800058fb  jnz     short loc_1800058F3
0x1800058fd  sub     r10, rdi
0x180005900  inc     rbx
0x180005903  cmp     rbx, r10
0x180005906  mov     rdx, r10; DestinationSize
0x180005909  mov     rcx, rdi; Destination
0x18000590c  cmovnb  rbx, r10
0x180005910  mov     r9, rbx; SourceSize
0x180005913  call    memcpy_s
0x180005918  mov     byte ptr [rbx+rdi-1], 0
0x18000591d  mov     al, 1
0x18000591f  add     rsp, 28h
0x180005923  pop     rdi
0x180005924  pop     rsi
0x180005925  pop     rbp
0x180005926  pop     rbx
0x180005927  retn
```
