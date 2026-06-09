# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000ce0c`
- end: `0x18000cee8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c1f0`
- `0x18000ce0c`

## callees

- `0x180005920`
- `0x18000ce0c`

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
0x18000ce0c  push    rbx
0x18000ce0e  push    rbp
0x18000ce0f  push    rsi
0x18000ce10  push    rdi
0x18000ce11  sub     rsp, 28h
0x18000ce15  xor     al, al
0x18000ce17  mov     byte ptr [r8], 0
0x18000ce1b  mov     rbp, r9
0x18000ce1e  mov     rdi, r8
0x18000ce21  mov     rsi, rdx
0x18000ce24  mov     rbx, rcx
0x18000ce27  test    rdx, rdx
0x18000ce2a  jz      loc_18000CEDF
0x18000ce30  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000ce34  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000ce39  mov     rdx, [rsi+20h]
0x18000ce3d  test    rdx, rdx
0x18000ce40  jz      loc_18000CEDF
0x18000ce46  cmp     dword ptr [rdx], 0
0x18000ce49  jnz     short loc_18000CE5C
0x18000ce4b  mov     eax, 1
0x18000ce50  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000ce58  inc     eax
0x18000ce5a  mov     [rdx], eax
0x18000ce5c  cmp     dword ptr [rbx+50h], 0
0x18000ce60  jnz     short loc_18000CE73
0x18000ce62  movups  xmm0, xmmword ptr [rdx]
0x18000ce65  movups  xmmword ptr [rbx+50h], xmm0
0x18000ce69  movsd   xmm1, qword ptr [rdx+10h]
0x18000ce6e  movsd   qword ptr [rbx+60h], xmm1
0x18000ce73  movups  xmm0, xmmword ptr [rdx]
0x18000ce76  lea     r10, [rdi+rbp]
0x18000ce7a  movups  xmmword ptr [rbx+68h], xmm0
0x18000ce7e  movsd   xmm1, qword ptr [rdx+10h]
0x18000ce83  movsd   qword ptr [rbx+78h], xmm1
0x18000ce88  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ce8c  mov     rax, rbx
0x18000ce8f  inc     rax
0x18000ce92  cmp     byte ptr [rdi+rax], 0
0x18000ce96  jnz     short loc_18000CE8F
0x18000ce98  lea     rcx, [rax+rdi]
0x18000ce9c  mov     rax, r10
0x18000ce9f  sub     rax, rcx
0x18000cea2  cmp     rax, 2
0x18000cea6  jle     short loc_18000CEDD
0x18000cea8  mov     byte ptr [rcx], 5Ch ; '\'
0x18000ceab  lea     rdi, [rcx+1]
0x18000ceaf  mov     r8, [rdx+8]; Source
0x18000ceb3  inc     rbx
0x18000ceb6  cmp     byte ptr [r8+rbx], 0
0x18000cebb  jnz     short loc_18000CEB3
0x18000cebd  sub     r10, rdi
0x18000cec0  inc     rbx
0x18000cec3  cmp     rbx, r10
0x18000cec6  mov     rdx, r10; DestinationSize
0x18000cec9  mov     rcx, rdi; Destination
0x18000cecc  cmovnb  rbx, r10
0x18000ced0  mov     r9, rbx; SourceSize
0x18000ced3  call    memcpy_s
0x18000ced8  mov     byte ptr [rbx+rdi-1], 0
0x18000cedd  mov     al, 1
0x18000cedf  add     rsp, 28h
0x18000cee3  pop     rdi
0x18000cee4  pop     rsi
0x18000cee5  pop     rbp
0x18000cee6  pop     rbx
0x18000cee7  retn
```
