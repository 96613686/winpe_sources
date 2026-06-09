# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800209a4`
- end: `0x180020a96`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `242`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800209a4`
- `0x180020aa0`

## callees

- `0x1800209a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180020a74`
- `msvcrt!memcpy_s` at `0x180020a74`

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
  char *v13; // rdi
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
      if ( !*((_DWORD *)a1 + 18) )
      {
        *(_OWORD *)((char *)a1 + 72) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 11) = *((_QWORD *)v9 + 2);
      }
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *((_OWORD *)a1 + 6) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 14) = *((_QWORD *)v9 + 2);
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
0x1800209a4  mov     [rsp+arg_0], rbx
0x1800209a9  mov     [rsp+arg_8], rbp
0x1800209ae  mov     [rsp+arg_10], rsi
0x1800209b3  push    rdi
0x1800209b4  sub     rsp, 20h
0x1800209b8  xor     al, al
0x1800209ba  mov     byte ptr [r8], 0
0x1800209be  mov     rbp, r9
0x1800209c1  mov     rdi, r8
0x1800209c4  mov     rsi, rdx
0x1800209c7  mov     rbx, rcx
0x1800209ca  test    rdx, rdx
0x1800209cd  jz      loc_180020A81
0x1800209d3  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800209d7  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800209dc  mov     rdx, [rsi+20h]
0x1800209e0  xor     esi, esi
0x1800209e2  test    rdx, rdx
0x1800209e5  jz      loc_180020A81
0x1800209eb  cmp     [rdx], esi
0x1800209ed  jnz     short loc_1800209FE
0x1800209ef  lea     eax, [rsi+1]
0x1800209f2  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800209fa  inc     eax
0x1800209fc  mov     [rdx], eax
0x1800209fe  cmp     [rbx+48h], esi
0x180020a01  jnz     short loc_180020A14
0x180020a03  movups  xmm0, xmmword ptr [rdx]
0x180020a06  movups  xmmword ptr [rbx+48h], xmm0
0x180020a0a  movsd   xmm1, qword ptr [rdx+10h]
0x180020a0f  movsd   qword ptr [rbx+58h], xmm1
0x180020a14  movups  xmm0, xmmword ptr [rdx]
0x180020a17  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020a1b  lea     r10, [rdi+rbp]
0x180020a1f  mov     rax, rcx
0x180020a22  movups  xmmword ptr [rbx+60h], xmm0
0x180020a26  movsd   xmm1, qword ptr [rdx+10h]
0x180020a2b  movsd   qword ptr [rbx+70h], xmm1
0x180020a30  inc     rax
0x180020a33  cmp     [rdi+rax], sil
0x180020a37  jnz     short loc_180020A30
0x180020a39  add     rdi, rax
0x180020a3c  mov     rax, r10
0x180020a3f  sub     rax, rdi
0x180020a42  cmp     rax, 2
0x180020a46  jle     short loc_180020A7F
0x180020a48  mov     byte ptr [rdi], 5Ch ; '\'
0x180020a4b  inc     rdi
0x180020a4e  mov     r8, [rdx+8]; Source
0x180020a52  inc     rcx
0x180020a55  cmp     [r8+rcx], sil
0x180020a59  jnz     short loc_180020A52
0x180020a5b  inc     rcx
0x180020a5e  sub     r10, rdi
0x180020a61  cmp     rcx, r10
0x180020a64  mov     rbx, r10
0x180020a67  mov     rdx, r10; DestinationSize
0x180020a6a  cmovb   rbx, rcx
0x180020a6e  mov     rcx, rdi; Destination
0x180020a71  mov     r9, rbx; SourceSize
0x180020a74  call    cs:__imp_memcpy_s
0x180020a7a  mov     [rbx+rdi-1], sil
0x180020a7f  mov     al, 1
0x180020a81  mov     rbx, [rsp+28h+arg_0]
0x180020a86  mov     rbp, [rsp+28h+arg_8]
0x180020a8b  mov     rsi, [rsp+28h+arg_10]
0x180020a90  add     rsp, 20h
0x180020a94  pop     rdi
0x180020a95  retn
```
