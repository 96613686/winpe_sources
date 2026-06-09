# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180011688`
- end: `0x180011764`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010ff4`
- `0x180011688`

## callees

- `0x18000dbd8`
- `0x180011688`

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
0x180011688  push    rbx
0x18001168a  push    rbp
0x18001168b  push    rsi
0x18001168c  push    rdi
0x18001168d  sub     rsp, 28h
0x180011691  xor     al, al
0x180011693  mov     byte ptr [r8], 0
0x180011697  mov     rbp, r9
0x18001169a  mov     rdi, r8
0x18001169d  mov     rsi, rdx
0x1800116a0  mov     rbx, rcx
0x1800116a3  test    rdx, rdx
0x1800116a6  jz      loc_18001175B
0x1800116ac  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800116b0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800116b5  mov     rdx, [rsi+20h]
0x1800116b9  test    rdx, rdx
0x1800116bc  jz      loc_18001175B
0x1800116c2  cmp     dword ptr [rdx], 0
0x1800116c5  jnz     short loc_1800116D8
0x1800116c7  mov     eax, 1
0x1800116cc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800116d4  inc     eax
0x1800116d6  mov     [rdx], eax
0x1800116d8  cmp     dword ptr [rbx+50h], 0
0x1800116dc  jnz     short loc_1800116EF
0x1800116de  movups  xmm0, xmmword ptr [rdx]
0x1800116e1  movups  xmmword ptr [rbx+50h], xmm0
0x1800116e5  movsd   xmm1, qword ptr [rdx+10h]
0x1800116ea  movsd   qword ptr [rbx+60h], xmm1
0x1800116ef  movups  xmm0, xmmword ptr [rdx]
0x1800116f2  lea     r10, [rdi+rbp]
0x1800116f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800116fa  movsd   xmm1, qword ptr [rdx+10h]
0x1800116ff  movsd   qword ptr [rbx+78h], xmm1
0x180011704  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011708  mov     rax, rbx
0x18001170b  inc     rax
0x18001170e  cmp     byte ptr [rdi+rax], 0
0x180011712  jnz     short loc_18001170B
0x180011714  lea     rcx, [rax+rdi]
0x180011718  mov     rax, r10
0x18001171b  sub     rax, rcx
0x18001171e  cmp     rax, 2
0x180011722  jle     short loc_180011759
0x180011724  mov     byte ptr [rcx], 5Ch ; '\'
0x180011727  lea     rdi, [rcx+1]
0x18001172b  mov     r8, [rdx+8]; Source
0x18001172f  inc     rbx
0x180011732  cmp     byte ptr [r8+rbx], 0
0x180011737  jnz     short loc_18001172F
0x180011739  sub     r10, rdi
0x18001173c  inc     rbx
0x18001173f  cmp     rbx, r10
0x180011742  mov     rdx, r10; DestinationSize
0x180011745  mov     rcx, rdi; Destination
0x180011748  cmovnb  rbx, r10
0x18001174c  mov     r9, rbx; SourceSize
0x18001174f  call    memcpy_s
0x180011754  mov     byte ptr [rbx+rdi-1], 0
0x180011759  mov     al, 1
0x18001175b  add     rsp, 28h
0x18001175f  pop     rdi
0x180011760  pop     rsi
0x180011761  pop     rbp
0x180011762  pop     rbx
0x180011763  retn
```
