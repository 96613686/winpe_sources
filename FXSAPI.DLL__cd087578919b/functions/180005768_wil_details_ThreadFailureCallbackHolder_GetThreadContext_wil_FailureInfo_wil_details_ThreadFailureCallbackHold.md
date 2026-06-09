# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005768`
- end: `0x18000584c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050f0`
- `0x180005768`

## callees

- `0x180005768`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000582f`
- `msvcrt!memcpy_s` at `0x18000582f`

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
0x180005768  push    rbx
0x18000576a  push    rbp
0x18000576b  push    rsi
0x18000576c  push    rdi
0x18000576d  sub     rsp, 28h
0x180005771  xor     al, al
0x180005773  mov     byte ptr [r8], 0
0x180005777  mov     rbp, r9
0x18000577a  mov     rdi, r8
0x18000577d  mov     rsi, rdx
0x180005780  mov     rbx, rcx
0x180005783  test    rdx, rdx
0x180005786  jz      loc_180005842
0x18000578c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005790  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005795  mov     rdx, [rsi+20h]
0x180005799  test    rdx, rdx
0x18000579c  jz      loc_180005842
0x1800057a2  cmp     dword ptr [rdx], 0
0x1800057a5  jnz     short loc_1800057B8
0x1800057a7  mov     eax, 1
0x1800057ac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800057b4  inc     eax
0x1800057b6  mov     [rdx], eax
0x1800057b8  cmp     dword ptr [rbx+50h], 0
0x1800057bc  jnz     short loc_1800057CF
0x1800057be  movups  xmm0, xmmword ptr [rdx]
0x1800057c1  movups  xmmword ptr [rbx+50h], xmm0
0x1800057c5  movsd   xmm1, qword ptr [rdx+10h]
0x1800057ca  movsd   qword ptr [rbx+60h], xmm1
0x1800057cf  movups  xmm0, xmmword ptr [rdx]
0x1800057d2  lea     r10, [rdi+rbp]
0x1800057d6  movups  xmmword ptr [rbx+68h], xmm0
0x1800057da  movsd   xmm1, qword ptr [rdx+10h]
0x1800057df  movsd   qword ptr [rbx+78h], xmm1
0x1800057e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800057e8  mov     rax, rbx
0x1800057eb  inc     rax
0x1800057ee  cmp     byte ptr [rdi+rax], 0
0x1800057f2  jnz     short loc_1800057EB
0x1800057f4  lea     rcx, [rax+rdi]
0x1800057f8  mov     rax, r10
0x1800057fb  sub     rax, rcx
0x1800057fe  cmp     rax, 2
0x180005802  jle     short loc_180005840
0x180005804  mov     byte ptr [rcx], 5Ch ; '\'
0x180005807  lea     rdi, [rcx+1]
0x18000580b  mov     r8, [rdx+8]; Source
0x18000580f  inc     rbx
0x180005812  cmp     byte ptr [r8+rbx], 0
0x180005817  jnz     short loc_18000580F
0x180005819  sub     r10, rdi
0x18000581c  inc     rbx
0x18000581f  cmp     rbx, r10
0x180005822  mov     rdx, r10; DestinationSize
0x180005825  mov     rcx, rdi; Destination
0x180005828  cmovnb  rbx, r10
0x18000582c  mov     r9, rbx; SourceSize
0x18000582f  call    cs:__imp_memcpy_s
0x180005836  nop     dword ptr [rax+rax+00h]
0x18000583b  mov     byte ptr [rbx+rdi-1], 0
0x180005840  mov     al, 1
0x180005842  add     rsp, 28h
0x180005846  pop     rdi
0x180005847  pop     rsi
0x180005848  pop     rbp
0x180005849  pop     rbx
0x18000584a  retn
```
