# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003e7c`
- end: `0x180003f59`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003840`
- `0x180003e7c`

## callees

- `0x180003e7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003f43`
- `msvcrt!memcpy_s` at `0x180003f43`

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
0x180003e7c  push    rbx
0x180003e7e  push    rbp
0x180003e7f  push    rsi
0x180003e80  push    rdi
0x180003e81  sub     rsp, 28h
0x180003e85  xor     al, al
0x180003e87  mov     byte ptr [r8], 0
0x180003e8b  mov     rbp, r9
0x180003e8e  mov     rdi, r8
0x180003e91  mov     rsi, rdx
0x180003e94  mov     rbx, rcx
0x180003e97  test    rdx, rdx
0x180003e9a  jz      loc_180003F50
0x180003ea0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003ea4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003ea9  mov     rdx, [rsi+20h]
0x180003ead  test    rdx, rdx
0x180003eb0  jz      loc_180003F50
0x180003eb6  cmp     dword ptr [rdx], 0
0x180003eb9  jnz     short loc_180003ECC
0x180003ebb  mov     eax, 1
0x180003ec0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003ec8  inc     eax
0x180003eca  mov     [rdx], eax
0x180003ecc  cmp     dword ptr [rbx+50h], 0
0x180003ed0  jnz     short loc_180003EE3
0x180003ed2  movups  xmm0, xmmword ptr [rdx]
0x180003ed5  movups  xmmword ptr [rbx+50h], xmm0
0x180003ed9  movsd   xmm1, qword ptr [rdx+10h]
0x180003ede  movsd   qword ptr [rbx+60h], xmm1
0x180003ee3  movups  xmm0, xmmword ptr [rdx]
0x180003ee6  lea     r10, [rdi+rbp]
0x180003eea  movups  xmmword ptr [rbx+68h], xmm0
0x180003eee  movsd   xmm1, qword ptr [rdx+10h]
0x180003ef3  movsd   qword ptr [rbx+78h], xmm1
0x180003ef8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003efc  mov     rax, rbx
0x180003eff  inc     rax
0x180003f02  cmp     byte ptr [rdi+rax], 0
0x180003f06  jnz     short loc_180003EFF
0x180003f08  lea     rcx, [rax+rdi]
0x180003f0c  mov     rax, r10
0x180003f0f  sub     rax, rcx
0x180003f12  cmp     rax, 2
0x180003f16  jle     short loc_180003F4E
0x180003f18  mov     byte ptr [rcx], 5Ch ; '\'
0x180003f1b  lea     rdi, [rcx+1]
0x180003f1f  mov     r8, [rdx+8]; Source
0x180003f23  inc     rbx
0x180003f26  cmp     byte ptr [r8+rbx], 0
0x180003f2b  jnz     short loc_180003F23
0x180003f2d  sub     r10, rdi
0x180003f30  inc     rbx
0x180003f33  cmp     rbx, r10
0x180003f36  mov     rdx, r10; DestinationSize
0x180003f39  mov     rcx, rdi; Destination
0x180003f3c  cmovnb  rbx, r10
0x180003f40  mov     r9, rbx; SourceSize
0x180003f43  call    cs:__imp_memcpy_s
0x180003f49  mov     byte ptr [rbx+rdi-1], 0
0x180003f4e  mov     al, 1
0x180003f50  add     rsp, 28h
0x180003f54  pop     rdi
0x180003f55  pop     rsi
0x180003f56  pop     rbp
0x180003f57  pop     rbx
0x180003f58  retn
```
