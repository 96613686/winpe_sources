# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004e90`
- end: `0x180004f6d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004800`
- `0x180004e90`

## callees

- `0x180004e90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004f57`
- `msvcrt!memcpy_s` at `0x180004f57`

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
0x180004e90  push    rbx
0x180004e92  push    rbp
0x180004e93  push    rsi
0x180004e94  push    rdi
0x180004e95  sub     rsp, 28h
0x180004e99  xor     al, al
0x180004e9b  mov     byte ptr [r8], 0
0x180004e9f  mov     rbp, r9
0x180004ea2  mov     rdi, r8
0x180004ea5  mov     rsi, rdx
0x180004ea8  mov     rbx, rcx
0x180004eab  test    rdx, rdx
0x180004eae  jz      loc_180004F64
0x180004eb4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004eb8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004ebd  mov     rdx, [rsi+20h]
0x180004ec1  test    rdx, rdx
0x180004ec4  jz      loc_180004F64
0x180004eca  cmp     dword ptr [rdx], 0
0x180004ecd  jnz     short loc_180004EE0
0x180004ecf  mov     eax, 1
0x180004ed4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004edc  inc     eax
0x180004ede  mov     [rdx], eax
0x180004ee0  cmp     dword ptr [rbx+50h], 0
0x180004ee4  jnz     short loc_180004EF7
0x180004ee6  movups  xmm0, xmmword ptr [rdx]
0x180004ee9  movups  xmmword ptr [rbx+50h], xmm0
0x180004eed  movsd   xmm1, qword ptr [rdx+10h]
0x180004ef2  movsd   qword ptr [rbx+60h], xmm1
0x180004ef7  movups  xmm0, xmmword ptr [rdx]
0x180004efa  lea     r10, [rdi+rbp]
0x180004efe  movups  xmmword ptr [rbx+68h], xmm0
0x180004f02  movsd   xmm1, qword ptr [rdx+10h]
0x180004f07  movsd   qword ptr [rbx+78h], xmm1
0x180004f0c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004f10  mov     rax, rbx
0x180004f13  inc     rax
0x180004f16  cmp     byte ptr [rdi+rax], 0
0x180004f1a  jnz     short loc_180004F13
0x180004f1c  lea     rcx, [rax+rdi]
0x180004f20  mov     rax, r10
0x180004f23  sub     rax, rcx
0x180004f26  cmp     rax, 2
0x180004f2a  jle     short loc_180004F62
0x180004f2c  mov     byte ptr [rcx], 5Ch ; '\'
0x180004f2f  lea     rdi, [rcx+1]
0x180004f33  mov     r8, [rdx+8]; Source
0x180004f37  inc     rbx
0x180004f3a  cmp     byte ptr [r8+rbx], 0
0x180004f3f  jnz     short loc_180004F37
0x180004f41  sub     r10, rdi
0x180004f44  inc     rbx
0x180004f47  cmp     rbx, r10
0x180004f4a  mov     rdx, r10; DestinationSize
0x180004f4d  mov     rcx, rdi; Destination
0x180004f50  cmovnb  rbx, r10
0x180004f54  mov     r9, rbx; SourceSize
0x180004f57  call    cs:__imp_memcpy_s
0x180004f5d  mov     byte ptr [rbx+rdi-1], 0
0x180004f62  mov     al, 1
0x180004f64  add     rsp, 28h
0x180004f68  pop     rdi
0x180004f69  pop     rsi
0x180004f6a  pop     rbp
0x180004f6b  pop     rbx
0x180004f6c  retn
```
