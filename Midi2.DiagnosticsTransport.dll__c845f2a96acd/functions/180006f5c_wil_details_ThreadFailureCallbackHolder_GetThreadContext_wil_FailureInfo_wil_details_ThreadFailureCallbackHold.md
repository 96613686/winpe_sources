# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006f5c`
- end: `0x180007038`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006860`
- `0x180006f5c`

## callees

- `0x180006f5c`
- `0x18000a328`

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
0x180006f5c  push    rbx
0x180006f5e  push    rbp
0x180006f5f  push    rsi
0x180006f60  push    rdi
0x180006f61  sub     rsp, 28h
0x180006f65  xor     al, al
0x180006f67  mov     byte ptr [r8], 0
0x180006f6b  mov     rbp, r9
0x180006f6e  mov     rdi, r8
0x180006f71  mov     rsi, rdx
0x180006f74  mov     rbx, rcx
0x180006f77  test    rdx, rdx
0x180006f7a  jz      loc_18000702F
0x180006f80  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006f84  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006f89  mov     rdx, [rsi+20h]
0x180006f8d  test    rdx, rdx
0x180006f90  jz      loc_18000702F
0x180006f96  cmp     dword ptr [rdx], 0
0x180006f99  jnz     short loc_180006FAC
0x180006f9b  mov     eax, 1
0x180006fa0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006fa8  inc     eax
0x180006faa  mov     [rdx], eax
0x180006fac  cmp     dword ptr [rbx+50h], 0
0x180006fb0  jnz     short loc_180006FC3
0x180006fb2  movups  xmm0, xmmword ptr [rdx]
0x180006fb5  movups  xmmword ptr [rbx+50h], xmm0
0x180006fb9  movsd   xmm1, qword ptr [rdx+10h]
0x180006fbe  movsd   qword ptr [rbx+60h], xmm1
0x180006fc3  movups  xmm0, xmmword ptr [rdx]
0x180006fc6  lea     r10, [rdi+rbp]
0x180006fca  movups  xmmword ptr [rbx+68h], xmm0
0x180006fce  movsd   xmm1, qword ptr [rdx+10h]
0x180006fd3  movsd   qword ptr [rbx+78h], xmm1
0x180006fd8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006fdc  mov     rax, rbx
0x180006fdf  inc     rax
0x180006fe2  cmp     byte ptr [rdi+rax], 0
0x180006fe6  jnz     short loc_180006FDF
0x180006fe8  lea     rcx, [rax+rdi]
0x180006fec  mov     rax, r10
0x180006fef  sub     rax, rcx
0x180006ff2  cmp     rax, 2
0x180006ff6  jle     short loc_18000702D
0x180006ff8  mov     byte ptr [rcx], 5Ch ; '\'
0x180006ffb  lea     rdi, [rcx+1]
0x180006fff  mov     r8, [rdx+8]; Source
0x180007003  inc     rbx
0x180007006  cmp     byte ptr [r8+rbx], 0
0x18000700b  jnz     short loc_180007003
0x18000700d  sub     r10, rdi
0x180007010  inc     rbx
0x180007013  cmp     rbx, r10
0x180007016  mov     rdx, r10; DestinationSize
0x180007019  mov     rcx, rdi; Destination
0x18000701c  cmovnb  rbx, r10
0x180007020  mov     r9, rbx; SourceSize
0x180007023  call    memcpy_s
0x180007028  mov     byte ptr [rbx+rdi-1], 0
0x18000702d  mov     al, 1
0x18000702f  add     rsp, 28h
0x180007033  pop     rdi
0x180007034  pop     rsi
0x180007035  pop     rbp
0x180007036  pop     rbx
0x180007037  retn
```
