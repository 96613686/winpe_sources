# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140009f78`
- end: `0x14000a055`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400098f0`
- `0x140009f78`

## callees

- `0x140009f78`

## import_xrefs

- `ntdll!memcpy_s` at `0x14000a03f`
- `ntdll!memcpy_s` at `0x14000a03f`

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
0x140009f78  push    rbx
0x140009f7a  push    rbp
0x140009f7b  push    rsi
0x140009f7c  push    rdi
0x140009f7d  sub     rsp, 28h
0x140009f81  xor     al, al
0x140009f83  mov     byte ptr [r8], 0
0x140009f87  mov     rbp, r9
0x140009f8a  mov     rdi, r8
0x140009f8d  mov     rsi, rdx
0x140009f90  mov     rbx, rcx
0x140009f93  test    rdx, rdx
0x140009f96  jz      loc_14000A04C
0x140009f9c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140009fa0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140009fa5  mov     rdx, [rsi+20h]
0x140009fa9  test    rdx, rdx
0x140009fac  jz      loc_14000A04C
0x140009fb2  cmp     dword ptr [rdx], 0
0x140009fb5  jnz     short loc_140009FC8
0x140009fb7  mov     eax, 1
0x140009fbc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140009fc4  inc     eax
0x140009fc6  mov     [rdx], eax
0x140009fc8  cmp     dword ptr [rbx+50h], 0
0x140009fcc  jnz     short loc_140009FDF
0x140009fce  movups  xmm0, xmmword ptr [rdx]
0x140009fd1  movups  xmmword ptr [rbx+50h], xmm0
0x140009fd5  movsd   xmm1, qword ptr [rdx+10h]
0x140009fda  movsd   qword ptr [rbx+60h], xmm1
0x140009fdf  movups  xmm0, xmmword ptr [rdx]
0x140009fe2  lea     r10, [rdi+rbp]
0x140009fe6  movups  xmmword ptr [rbx+68h], xmm0
0x140009fea  movsd   xmm1, qword ptr [rdx+10h]
0x140009fef  movsd   qword ptr [rbx+78h], xmm1
0x140009ff4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140009ff8  mov     rax, rbx
0x140009ffb  inc     rax
0x140009ffe  cmp     byte ptr [rdi+rax], 0
0x14000a002  jnz     short loc_140009FFB
0x14000a004  lea     rcx, [rax+rdi]
0x14000a008  mov     rax, r10
0x14000a00b  sub     rax, rcx
0x14000a00e  cmp     rax, 2
0x14000a012  jle     short loc_14000A04A
0x14000a014  mov     byte ptr [rcx], 5Ch ; '\'
0x14000a017  lea     rdi, [rcx+1]
0x14000a01b  mov     r8, [rdx+8]; Source
0x14000a01f  inc     rbx
0x14000a022  cmp     byte ptr [r8+rbx], 0
0x14000a027  jnz     short loc_14000A01F
0x14000a029  sub     r10, rdi
0x14000a02c  inc     rbx
0x14000a02f  cmp     rbx, r10
0x14000a032  mov     rdx, r10; DestinationSize
0x14000a035  mov     rcx, rdi; Destination
0x14000a038  cmovnb  rbx, r10
0x14000a03c  mov     r9, rbx; SourceSize
0x14000a03f  call    cs:__imp_memcpy_s
0x14000a045  mov     byte ptr [rbx+rdi-1], 0
0x14000a04a  mov     al, 1
0x14000a04c  add     rsp, 28h
0x14000a050  pop     rdi
0x14000a051  pop     rsi
0x14000a052  pop     rbp
0x14000a053  pop     rbx
0x14000a054  retn
```
