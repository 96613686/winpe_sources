# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180010290`
- end: `0x18001036d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fc78`
- `0x180010290`

## callees

- `0x180010290`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010357`
- `msvcrt!memcpy_s` at `0x180010357`

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
0x180010290  push    rbx
0x180010292  push    rbp
0x180010293  push    rsi
0x180010294  push    rdi
0x180010295  sub     rsp, 28h
0x180010299  xor     al, al
0x18001029b  mov     byte ptr [r8], 0
0x18001029f  mov     rbp, r9
0x1800102a2  mov     rdi, r8
0x1800102a5  mov     rsi, rdx
0x1800102a8  mov     rbx, rcx
0x1800102ab  test    rdx, rdx
0x1800102ae  jz      loc_180010364
0x1800102b4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800102b8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800102bd  mov     rdx, [rsi+20h]
0x1800102c1  test    rdx, rdx
0x1800102c4  jz      loc_180010364
0x1800102ca  cmp     dword ptr [rdx], 0
0x1800102cd  jnz     short loc_1800102E0
0x1800102cf  mov     eax, 1
0x1800102d4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800102dc  inc     eax
0x1800102de  mov     [rdx], eax
0x1800102e0  cmp     dword ptr [rbx+50h], 0
0x1800102e4  jnz     short loc_1800102F7
0x1800102e6  movups  xmm0, xmmword ptr [rdx]
0x1800102e9  movups  xmmword ptr [rbx+50h], xmm0
0x1800102ed  movsd   xmm1, qword ptr [rdx+10h]
0x1800102f2  movsd   qword ptr [rbx+60h], xmm1
0x1800102f7  movups  xmm0, xmmword ptr [rdx]
0x1800102fa  lea     r10, [rdi+rbp]
0x1800102fe  movups  xmmword ptr [rbx+68h], xmm0
0x180010302  movsd   xmm1, qword ptr [rdx+10h]
0x180010307  movsd   qword ptr [rbx+78h], xmm1
0x18001030c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010310  mov     rax, rbx
0x180010313  inc     rax
0x180010316  cmp     byte ptr [rdi+rax], 0
0x18001031a  jnz     short loc_180010313
0x18001031c  lea     rcx, [rax+rdi]
0x180010320  mov     rax, r10
0x180010323  sub     rax, rcx
0x180010326  cmp     rax, 2
0x18001032a  jle     short loc_180010362
0x18001032c  mov     byte ptr [rcx], 5Ch ; '\'
0x18001032f  lea     rdi, [rcx+1]
0x180010333  mov     r8, [rdx+8]; Source
0x180010337  inc     rbx
0x18001033a  cmp     byte ptr [r8+rbx], 0
0x18001033f  jnz     short loc_180010337
0x180010341  sub     r10, rdi
0x180010344  inc     rbx
0x180010347  cmp     rbx, r10
0x18001034a  mov     rdx, r10; DestinationSize
0x18001034d  mov     rcx, rdi; Destination
0x180010350  cmovnb  rbx, r10
0x180010354  mov     r9, rbx; SourceSize
0x180010357  call    cs:__imp_memcpy_s
0x18001035d  mov     byte ptr [rbx+rdi-1], 0
0x180010362  mov     al, 1
0x180010364  add     rsp, 28h
0x180010368  pop     rdi
0x180010369  pop     rsi
0x18001036a  pop     rbp
0x18001036b  pop     rbx
0x18001036c  retn
```
