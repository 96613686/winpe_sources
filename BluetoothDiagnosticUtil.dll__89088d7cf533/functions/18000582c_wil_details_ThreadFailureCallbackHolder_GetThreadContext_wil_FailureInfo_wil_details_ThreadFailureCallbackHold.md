# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000582c`
- end: `0x180005910`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005160`
- `0x18000582c`

## callees

- `0x18000582c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800058f3`
- `msvcrt!memcpy_s` at `0x1800058f3`

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
0x18000582c  push    rbx
0x18000582e  push    rbp
0x18000582f  push    rsi
0x180005830  push    rdi
0x180005831  sub     rsp, 28h
0x180005835  xor     al, al
0x180005837  mov     byte ptr [r8], 0
0x18000583b  mov     rbp, r9
0x18000583e  mov     rdi, r8
0x180005841  mov     rsi, rdx
0x180005844  mov     rbx, rcx
0x180005847  test    rdx, rdx
0x18000584a  jz      loc_180005906
0x180005850  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005854  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005859  mov     rdx, [rsi+20h]
0x18000585d  test    rdx, rdx
0x180005860  jz      loc_180005906
0x180005866  cmp     dword ptr [rdx], 0
0x180005869  jnz     short loc_18000587C
0x18000586b  mov     eax, 1
0x180005870  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005878  inc     eax
0x18000587a  mov     [rdx], eax
0x18000587c  cmp     dword ptr [rbx+50h], 0
0x180005880  jnz     short loc_180005893
0x180005882  movups  xmm0, xmmword ptr [rdx]
0x180005885  movups  xmmword ptr [rbx+50h], xmm0
0x180005889  movsd   xmm1, qword ptr [rdx+10h]
0x18000588e  movsd   qword ptr [rbx+60h], xmm1
0x180005893  movups  xmm0, xmmword ptr [rdx]
0x180005896  lea     r10, [rdi+rbp]
0x18000589a  movups  xmmword ptr [rbx+68h], xmm0
0x18000589e  movsd   xmm1, qword ptr [rdx+10h]
0x1800058a3  movsd   qword ptr [rbx+78h], xmm1
0x1800058a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800058ac  mov     rax, rbx
0x1800058af  inc     rax
0x1800058b2  cmp     byte ptr [rdi+rax], 0
0x1800058b6  jnz     short loc_1800058AF
0x1800058b8  lea     rcx, [rax+rdi]
0x1800058bc  mov     rax, r10
0x1800058bf  sub     rax, rcx
0x1800058c2  cmp     rax, 2
0x1800058c6  jle     short loc_180005904
0x1800058c8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800058cb  lea     rdi, [rcx+1]
0x1800058cf  mov     r8, [rdx+8]; Source
0x1800058d3  inc     rbx
0x1800058d6  cmp     byte ptr [r8+rbx], 0
0x1800058db  jnz     short loc_1800058D3
0x1800058dd  sub     r10, rdi
0x1800058e0  inc     rbx
0x1800058e3  cmp     rbx, r10
0x1800058e6  mov     rdx, r10; DestinationSize
0x1800058e9  mov     rcx, rdi; Destination
0x1800058ec  cmovnb  rbx, r10
0x1800058f0  mov     r9, rbx; SourceSize
0x1800058f3  call    cs:__imp_memcpy_s
0x1800058fa  nop     dword ptr [rax+rax+00h]
0x1800058ff  mov     byte ptr [rbx+rdi-1], 0
0x180005904  mov     al, 1
0x180005906  add     rsp, 28h
0x18000590a  pop     rdi
0x18000590b  pop     rsi
0x18000590c  pop     rbp
0x18000590d  pop     rbx
0x18000590e  retn
```
