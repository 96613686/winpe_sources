# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004e8c`
- end: `0x180004f68`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004790`
- `0x180004e8c`

## callees

- `0x180004e8c`
- `0x180008998`

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
0x180004e8c  push    rbx
0x180004e8e  push    rbp
0x180004e8f  push    rsi
0x180004e90  push    rdi
0x180004e91  sub     rsp, 28h
0x180004e95  xor     al, al
0x180004e97  mov     byte ptr [r8], 0
0x180004e9b  mov     rbp, r9
0x180004e9e  mov     rdi, r8
0x180004ea1  mov     rsi, rdx
0x180004ea4  mov     rbx, rcx
0x180004ea7  test    rdx, rdx
0x180004eaa  jz      loc_180004F5F
0x180004eb0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004eb4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004eb9  mov     rdx, [rsi+20h]
0x180004ebd  test    rdx, rdx
0x180004ec0  jz      loc_180004F5F
0x180004ec6  cmp     dword ptr [rdx], 0
0x180004ec9  jnz     short loc_180004EDC
0x180004ecb  mov     eax, 1
0x180004ed0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004ed8  inc     eax
0x180004eda  mov     [rdx], eax
0x180004edc  cmp     dword ptr [rbx+50h], 0
0x180004ee0  jnz     short loc_180004EF3
0x180004ee2  movups  xmm0, xmmword ptr [rdx]
0x180004ee5  movups  xmmword ptr [rbx+50h], xmm0
0x180004ee9  movsd   xmm1, qword ptr [rdx+10h]
0x180004eee  movsd   qword ptr [rbx+60h], xmm1
0x180004ef3  movups  xmm0, xmmword ptr [rdx]
0x180004ef6  lea     r10, [rdi+rbp]
0x180004efa  movups  xmmword ptr [rbx+68h], xmm0
0x180004efe  movsd   xmm1, qword ptr [rdx+10h]
0x180004f03  movsd   qword ptr [rbx+78h], xmm1
0x180004f08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004f0c  mov     rax, rbx
0x180004f0f  inc     rax
0x180004f12  cmp     byte ptr [rdi+rax], 0
0x180004f16  jnz     short loc_180004F0F
0x180004f18  lea     rcx, [rax+rdi]
0x180004f1c  mov     rax, r10
0x180004f1f  sub     rax, rcx
0x180004f22  cmp     rax, 2
0x180004f26  jle     short loc_180004F5D
0x180004f28  mov     byte ptr [rcx], 5Ch ; '\'
0x180004f2b  lea     rdi, [rcx+1]
0x180004f2f  mov     r8, [rdx+8]; Source
0x180004f33  inc     rbx
0x180004f36  cmp     byte ptr [r8+rbx], 0
0x180004f3b  jnz     short loc_180004F33
0x180004f3d  sub     r10, rdi
0x180004f40  inc     rbx
0x180004f43  cmp     rbx, r10
0x180004f46  mov     rdx, r10; DestinationSize
0x180004f49  mov     rcx, rdi; Destination
0x180004f4c  cmovnb  rbx, r10
0x180004f50  mov     r9, rbx; SourceSize
0x180004f53  call    memcpy_s
0x180004f58  mov     byte ptr [rbx+rdi-1], 0
0x180004f5d  mov     al, 1
0x180004f5f  add     rsp, 28h
0x180004f63  pop     rdi
0x180004f64  pop     rsi
0x180004f65  pop     rbp
0x180004f66  pop     rbx
0x180004f67  retn
```
