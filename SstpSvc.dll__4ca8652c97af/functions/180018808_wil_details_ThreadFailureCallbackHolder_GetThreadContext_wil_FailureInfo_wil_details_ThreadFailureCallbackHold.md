# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180018808`
- end: `0x1800188e5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800180a4`
- `0x180018808`

## callees

- `0x180018808`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800188cf`
- `msvcrt!memcpy_s` at `0x1800188cf`

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
0x180018808  push    rbx
0x18001880a  push    rbp
0x18001880b  push    rsi
0x18001880c  push    rdi
0x18001880d  sub     rsp, 28h
0x180018811  xor     al, al
0x180018813  mov     byte ptr [r8], 0
0x180018817  mov     rbp, r9
0x18001881a  mov     rdi, r8
0x18001881d  mov     rsi, rdx
0x180018820  mov     rbx, rcx
0x180018823  test    rdx, rdx
0x180018826  jz      loc_1800188DC
0x18001882c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180018830  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180018835  mov     rdx, [rsi+20h]
0x180018839  test    rdx, rdx
0x18001883c  jz      loc_1800188DC
0x180018842  cmp     dword ptr [rdx], 0
0x180018845  jnz     short loc_180018858
0x180018847  mov     eax, 1
0x18001884c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180018854  inc     eax
0x180018856  mov     [rdx], eax
0x180018858  cmp     dword ptr [rbx+50h], 0
0x18001885c  jnz     short loc_18001886F
0x18001885e  movups  xmm0, xmmword ptr [rdx]
0x180018861  movups  xmmword ptr [rbx+50h], xmm0
0x180018865  movsd   xmm1, qword ptr [rdx+10h]
0x18001886a  movsd   qword ptr [rbx+60h], xmm1
0x18001886f  movups  xmm0, xmmword ptr [rdx]
0x180018872  lea     r10, [rdi+rbp]
0x180018876  movups  xmmword ptr [rbx+68h], xmm0
0x18001887a  movsd   xmm1, qword ptr [rdx+10h]
0x18001887f  movsd   qword ptr [rbx+78h], xmm1
0x180018884  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018888  mov     rax, rbx
0x18001888b  inc     rax
0x18001888e  cmp     byte ptr [rdi+rax], 0
0x180018892  jnz     short loc_18001888B
0x180018894  lea     rcx, [rax+rdi]
0x180018898  mov     rax, r10
0x18001889b  sub     rax, rcx
0x18001889e  cmp     rax, 2
0x1800188a2  jle     short loc_1800188DA
0x1800188a4  mov     byte ptr [rcx], 5Ch ; '\'
0x1800188a7  lea     rdi, [rcx+1]
0x1800188ab  mov     r8, [rdx+8]; Source
0x1800188af  inc     rbx
0x1800188b2  cmp     byte ptr [r8+rbx], 0
0x1800188b7  jnz     short loc_1800188AF
0x1800188b9  sub     r10, rdi
0x1800188bc  inc     rbx
0x1800188bf  cmp     rbx, r10
0x1800188c2  mov     rdx, r10; DestinationSize
0x1800188c5  mov     rcx, rdi; Destination
0x1800188c8  cmovnb  rbx, r10
0x1800188cc  mov     r9, rbx; SourceSize
0x1800188cf  call    cs:__imp_memcpy_s
0x1800188d5  mov     byte ptr [rbx+rdi-1], 0
0x1800188da  mov     al, 1
0x1800188dc  add     rsp, 28h
0x1800188e0  pop     rdi
0x1800188e1  pop     rsi
0x1800188e2  pop     rbp
0x1800188e3  pop     rbx
0x1800188e4  retn
```
