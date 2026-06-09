# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004b20`
- end: `0x180004c76`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `342`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004b20`
- `0x180004c80`

## callees

- `0x180004b20`
- `0x18000b990`
- `0x18000bd50`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004c06`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004c48`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004c06`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004c48`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180004c54`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180004c54`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdi
  __int64 v10; // rcx
  char *v11; // rbp
  __int64 v12; // rax
  char *v13; // rbx
  _BYTE *v14; // rbx
  _BYTE *v15; // rdi
  size_t v17; // rbp
  size_t v18; // rsi

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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v11 - v13 <= 2 )
        return 1;
      *v13 = 92;
      v14 = v13 + 1;
      v15 = (_BYTE *)*((_QWORD *)v9 + 1);
      while ( v15[++v10] != 0 )
        ;
      v17 = v11 - v14;
      v18 = v17;
      if ( v10 + 1 < v17 )
        v18 = v10 + 1;
      if ( v18 )
      {
        if ( !v14 )
        {
LABEL_16:
          *_errno() = 22;
LABEL_23:
          _invalid_parameter_noinfo();
          goto LABEL_24;
        }
        if ( v15 && v17 >= v18 )
        {
          _mm_lfence();
          memmove(v14, v15, v18);
        }
        else
        {
          memset(v14, 0, v17);
          if ( !v15 )
            goto LABEL_16;
          if ( v17 < v18 )
          {
            *_errno() = 34;
            goto LABEL_23;
          }
        }
      }
LABEL_24:
      v14[v18 - 1] = 0;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004b20  mov     [rsp+arg_0], rbx
0x180004b25  mov     [rsp+arg_8], rbp
0x180004b2a  mov     [rsp+arg_10], rsi
0x180004b2f  push    rdi
0x180004b30  sub     rsp, 20h
0x180004b34  xor     al, al
0x180004b36  mov     byte ptr [r8], 0
0x180004b3a  mov     rbp, r9
0x180004b3d  mov     rbx, r8
0x180004b40  mov     rdi, rdx
0x180004b43  mov     rsi, rcx
0x180004b46  test    rdx, rdx
0x180004b49  jz      loc_180004C61
0x180004b4f  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004b53  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004b58  mov     rdi, [rdi+20h]
0x180004b5c  test    rdi, rdi
0x180004b5f  jz      loc_180004C61
0x180004b65  cmp     dword ptr [rdi], 0
0x180004b68  jnz     short loc_180004B7B
0x180004b6a  mov     eax, 1
0x180004b6f  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004b77  inc     eax
0x180004b79  mov     [rdi], eax
0x180004b7b  cmp     dword ptr [rsi+50h], 0
0x180004b7f  jnz     short loc_180004B92
0x180004b81  movups  xmm0, xmmword ptr [rdi]
0x180004b84  movups  xmmword ptr [rsi+50h], xmm0
0x180004b88  movsd   xmm1, qword ptr [rdi+10h]
0x180004b8d  movsd   qword ptr [rsi+60h], xmm1
0x180004b92  movups  xmm0, xmmword ptr [rdi]
0x180004b95  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004b9c  add     rbp, rbx
0x180004b9f  mov     rax, rcx
0x180004ba2  movups  xmmword ptr [rsi+68h], xmm0
0x180004ba6  movsd   xmm1, qword ptr [rdi+10h]
0x180004bab  movsd   qword ptr [rsi+78h], xmm1
0x180004bb0  inc     rax
0x180004bb3  cmp     byte ptr [rbx+rax], 0
0x180004bb7  jnz     short loc_180004BB0
0x180004bb9  add     rbx, rax
0x180004bbc  mov     rax, rbp
0x180004bbf  sub     rax, rbx
0x180004bc2  cmp     rax, 2
0x180004bc6  jle     loc_180004C5F
0x180004bcc  mov     byte ptr [rbx], 5Ch ; '\'
0x180004bcf  inc     rbx
0x180004bd2  mov     rdi, [rdi+8]
0x180004bd6  nop     word ptr [rax+rax+00000000h]
0x180004be0  cmp     byte ptr [rdi+rcx+1], 0
0x180004be5  lea     rcx, [rcx+1]
0x180004be9  jnz     short loc_180004BE0
0x180004beb  sub     rbp, rbx
0x180004bee  lea     rax, [rcx+1]
0x180004bf2  cmp     rax, rbp
0x180004bf5  mov     rsi, rbp
0x180004bf8  cmovb   rsi, rax
0x180004bfc  test    rsi, rsi
0x180004bff  jz      short loc_180004C5A
0x180004c01  test    rbx, rbx
0x180004c04  jnz     short loc_180004C14
0x180004c06  call    cs:__imp__errno
0x180004c0c  mov     dword ptr [rax], 16h
0x180004c12  jmp     short loc_180004C54
0x180004c14  test    rdi, rdi
0x180004c17  jz      short loc_180004C31
0x180004c19  cmp     rbp, rsi
0x180004c1c  jb      short loc_180004C31
0x180004c1e  lfence
0x180004c21  mov     r8, rsi; Size
0x180004c24  mov     rdx, rdi; Src
0x180004c27  mov     rcx, rbx; void *
0x180004c2a  call    memmove
0x180004c2f  jmp     short loc_180004C5A
0x180004c31  mov     r8, rbp; Size
0x180004c34  xor     edx, edx; Val
0x180004c36  mov     rcx, rbx; void *
0x180004c39  call    memset
0x180004c3e  test    rdi, rdi
0x180004c41  jz      short loc_180004C06
0x180004c43  cmp     rbp, rsi
0x180004c46  jnb     short loc_180004C5A
0x180004c48  call    cs:__imp__errno
0x180004c4e  mov     dword ptr [rax], 22h ; '"'
0x180004c54  call    cs:__imp__invalid_parameter_noinfo
0x180004c5a  mov     byte ptr [rsi+rbx-1], 0
0x180004c5f  mov     al, 1
0x180004c61  mov     rbx, [rsp+28h+arg_0]
0x180004c66  mov     rbp, [rsp+28h+arg_8]
0x180004c6b  mov     rsi, [rsp+28h+arg_10]
0x180004c70  add     rsp, 20h
0x180004c74  pop     rdi
0x180004c75  retn
```
