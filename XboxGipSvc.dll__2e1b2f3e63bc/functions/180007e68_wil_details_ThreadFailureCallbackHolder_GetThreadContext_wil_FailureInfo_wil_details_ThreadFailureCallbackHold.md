# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180007e68`
- end: `0x180007f44`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a90`
- `0x180007e68`

## callees

- `0x180007e68`
- `0x180009478`

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
0x180007e68  push    rbx
0x180007e6a  push    rbp
0x180007e6b  push    rsi
0x180007e6c  push    rdi
0x180007e6d  sub     rsp, 28h
0x180007e71  xor     al, al
0x180007e73  mov     byte ptr [r8], 0
0x180007e77  mov     rbp, r9
0x180007e7a  mov     rdi, r8
0x180007e7d  mov     rsi, rdx
0x180007e80  mov     rbx, rcx
0x180007e83  test    rdx, rdx
0x180007e86  jz      loc_180007F3B
0x180007e8c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180007e90  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007e95  mov     rdx, [rsi+20h]
0x180007e99  test    rdx, rdx
0x180007e9c  jz      loc_180007F3B
0x180007ea2  cmp     dword ptr [rdx], 0
0x180007ea5  jnz     short loc_180007EB8
0x180007ea7  mov     eax, 1
0x180007eac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180007eb4  inc     eax
0x180007eb6  mov     [rdx], eax
0x180007eb8  cmp     dword ptr [rbx+50h], 0
0x180007ebc  jnz     short loc_180007ECF
0x180007ebe  movups  xmm0, xmmword ptr [rdx]
0x180007ec1  movups  xmmword ptr [rbx+50h], xmm0
0x180007ec5  movsd   xmm1, qword ptr [rdx+10h]
0x180007eca  movsd   qword ptr [rbx+60h], xmm1
0x180007ecf  movups  xmm0, xmmword ptr [rdx]
0x180007ed2  lea     r10, [rdi+rbp]
0x180007ed6  movups  xmmword ptr [rbx+68h], xmm0
0x180007eda  movsd   xmm1, qword ptr [rdx+10h]
0x180007edf  movsd   qword ptr [rbx+78h], xmm1
0x180007ee4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007ee8  mov     rax, rbx
0x180007eeb  inc     rax
0x180007eee  cmp     byte ptr [rdi+rax], 0
0x180007ef2  jnz     short loc_180007EEB
0x180007ef4  lea     rcx, [rax+rdi]
0x180007ef8  mov     rax, r10
0x180007efb  sub     rax, rcx
0x180007efe  cmp     rax, 2
0x180007f02  jle     short loc_180007F39
0x180007f04  mov     byte ptr [rcx], 5Ch ; '\'
0x180007f07  lea     rdi, [rcx+1]
0x180007f0b  mov     r8, [rdx+8]; Source
0x180007f0f  inc     rbx
0x180007f12  cmp     byte ptr [r8+rbx], 0
0x180007f17  jnz     short loc_180007F0F
0x180007f19  sub     r10, rdi
0x180007f1c  inc     rbx
0x180007f1f  cmp     rbx, r10
0x180007f22  mov     rdx, r10; DestinationSize
0x180007f25  mov     rcx, rdi; Destination
0x180007f28  cmovnb  rbx, r10
0x180007f2c  mov     r9, rbx; SourceSize
0x180007f2f  call    memcpy_s
0x180007f34  mov     byte ptr [rbx+rdi-1], 0
0x180007f39  mov     al, 1
0x180007f3b  add     rsp, 28h
0x180007f3f  pop     rdi
0x180007f40  pop     rsi
0x180007f41  pop     rbp
0x180007f42  pop     rbx
0x180007f43  retn
```
