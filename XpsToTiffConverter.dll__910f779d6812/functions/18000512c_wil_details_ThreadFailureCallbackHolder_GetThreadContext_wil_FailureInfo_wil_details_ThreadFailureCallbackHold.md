# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000512c`
- end: `0x180005208`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a30`
- `0x18000512c`

## callees

- `0x18000512c`
- `0x180008f08`

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
0x18000512c  push    rbx
0x18000512e  push    rbp
0x18000512f  push    rsi
0x180005130  push    rdi
0x180005131  sub     rsp, 28h
0x180005135  xor     al, al
0x180005137  mov     byte ptr [r8], 0
0x18000513b  mov     rbp, r9
0x18000513e  mov     rdi, r8
0x180005141  mov     rsi, rdx
0x180005144  mov     rbx, rcx
0x180005147  test    rdx, rdx
0x18000514a  jz      loc_1800051FF
0x180005150  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005154  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005159  mov     rdx, [rsi+20h]
0x18000515d  test    rdx, rdx
0x180005160  jz      loc_1800051FF
0x180005166  cmp     dword ptr [rdx], 0
0x180005169  jnz     short loc_18000517C
0x18000516b  mov     eax, 1
0x180005170  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005178  inc     eax
0x18000517a  mov     [rdx], eax
0x18000517c  cmp     dword ptr [rbx+50h], 0
0x180005180  jnz     short loc_180005193
0x180005182  movups  xmm0, xmmword ptr [rdx]
0x180005185  movups  xmmword ptr [rbx+50h], xmm0
0x180005189  movsd   xmm1, qword ptr [rdx+10h]
0x18000518e  movsd   qword ptr [rbx+60h], xmm1
0x180005193  movups  xmm0, xmmword ptr [rdx]
0x180005196  lea     r10, [rdi+rbp]
0x18000519a  movups  xmmword ptr [rbx+68h], xmm0
0x18000519e  movsd   xmm1, qword ptr [rdx+10h]
0x1800051a3  movsd   qword ptr [rbx+78h], xmm1
0x1800051a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800051ac  mov     rax, rbx
0x1800051af  inc     rax
0x1800051b2  cmp     byte ptr [rdi+rax], 0
0x1800051b6  jnz     short loc_1800051AF
0x1800051b8  lea     rcx, [rax+rdi]
0x1800051bc  mov     rax, r10
0x1800051bf  sub     rax, rcx
0x1800051c2  cmp     rax, 2
0x1800051c6  jle     short loc_1800051FD
0x1800051c8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800051cb  lea     rdi, [rcx+1]
0x1800051cf  mov     r8, [rdx+8]; Source
0x1800051d3  inc     rbx
0x1800051d6  cmp     byte ptr [r8+rbx], 0
0x1800051db  jnz     short loc_1800051D3
0x1800051dd  sub     r10, rdi
0x1800051e0  inc     rbx
0x1800051e3  cmp     rbx, r10
0x1800051e6  mov     rdx, r10; DestinationSize
0x1800051e9  mov     rcx, rdi; Destination
0x1800051ec  cmovnb  rbx, r10
0x1800051f0  mov     r9, rbx; SourceSize
0x1800051f3  call    memcpy_s
0x1800051f8  mov     byte ptr [rbx+rdi-1], 0
0x1800051fd  mov     al, 1
0x1800051ff  add     rsp, 28h
0x180005203  pop     rdi
0x180005204  pop     rsi
0x180005205  pop     rbp
0x180005206  pop     rbx
0x180005207  retn
```
