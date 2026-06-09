# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000fba0`
- end: `0x18000fcc5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `293`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004cf0`
- `0x18000fba0`

## callees

- `0x18000deca`
- `0x18000df34`
- `0x18000df4c`
- `0x18000fba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fc65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fca4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fc65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fca4`

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
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rsi
  _BYTE *v14; // rsi
  __int64 v15; // rbp
  size_t v16; // rbx
  size_t v17; // rdi

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
      if ( v10 - v13 <= 2 )
        return 1;
      *v13 = 92;
      v14 = v13 + 1;
      v15 = *((_QWORD *)v9 + 1);
      do
        ++v11;
      while ( *(_BYTE *)(v11 + v15) );
      v16 = v11 + 1;
      v17 = v10 - v14;
      if ( v16 >= v17 )
        v16 = v17;
      if ( v16 )
      {
        if ( !v14 )
        {
LABEL_16:
          *(_DWORD *)_o__errno() = 22;
LABEL_23:
          invalid_parameter_noinfo();
          goto LABEL_24;
        }
        if ( v15 && v17 >= v16 )
        {
          memcpy_0(v14, *((const void **)v9 + 1), v16);
        }
        else
        {
          memset_0(v14, 0, v17);
          if ( !v15 )
            goto LABEL_16;
          if ( v17 < v16 )
          {
            *(_DWORD *)_o__errno() = 34;
            goto LABEL_23;
          }
        }
      }
LABEL_24:
      v14[v16 - 1] = 0;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fba0  push    rbx
0x18000fba2  push    rbp
0x18000fba3  push    rsi
0x18000fba4  push    rdi
0x18000fba5  sub     rsp, 28h
0x18000fba9  xor     al, al
0x18000fbab  mov     byte ptr [r8], 0
0x18000fbaf  mov     rbp, r9
0x18000fbb2  mov     rsi, r8
0x18000fbb5  mov     rdi, rdx
0x18000fbb8  mov     rbx, rcx
0x18000fbbb  test    rdx, rdx
0x18000fbbe  jz      loc_18000FCBC
0x18000fbc4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000fbc8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000fbcd  mov     rdx, [rdi+20h]
0x18000fbd1  test    rdx, rdx
0x18000fbd4  jz      loc_18000FCBC
0x18000fbda  cmp     dword ptr [rdx], 0
0x18000fbdd  jnz     short loc_18000FBF0
0x18000fbdf  mov     eax, 1
0x18000fbe4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000fbec  inc     eax
0x18000fbee  mov     [rdx], eax
0x18000fbf0  cmp     dword ptr [rbx+50h], 0
0x18000fbf4  jnz     short loc_18000FC07
0x18000fbf6  movups  xmm0, xmmword ptr [rdx]
0x18000fbf9  movups  xmmword ptr [rbx+50h], xmm0
0x18000fbfd  movsd   xmm1, qword ptr [rdx+10h]
0x18000fc02  movsd   qword ptr [rbx+60h], xmm1
0x18000fc07  movups  xmm0, xmmword ptr [rdx]
0x18000fc0a  lea     rdi, [rsi+rbp]
0x18000fc0e  movups  xmmword ptr [rbx+68h], xmm0
0x18000fc12  movsd   xmm1, qword ptr [rdx+10h]
0x18000fc17  movsd   qword ptr [rbx+78h], xmm1
0x18000fc1c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fc20  mov     rax, rbx
0x18000fc23  inc     rax
0x18000fc26  cmp     byte ptr [rsi+rax], 0
0x18000fc2a  jnz     short loc_18000FC23
0x18000fc2c  add     rsi, rax
0x18000fc2f  mov     rax, rdi
0x18000fc32  sub     rax, rsi
0x18000fc35  cmp     rax, 2
0x18000fc39  jle     short loc_18000FCBA
0x18000fc3b  mov     byte ptr [rsi], 5Ch ; '\'
0x18000fc3e  inc     rsi
0x18000fc41  mov     rbp, [rdx+8]
0x18000fc45  inc     rbx
0x18000fc48  cmp     byte ptr [rbx+rbp], 0
0x18000fc4c  jnz     short loc_18000FC45
0x18000fc4e  inc     rbx
0x18000fc51  sub     rdi, rsi
0x18000fc54  cmp     rbx, rdi
0x18000fc57  cmovnb  rbx, rdi
0x18000fc5b  test    rbx, rbx
0x18000fc5e  jz      short loc_18000FCB5
0x18000fc60  test    rsi, rsi
0x18000fc63  jnz     short loc_18000FC73
0x18000fc65  call    cs:__imp__o__errno
0x18000fc6b  mov     dword ptr [rax], 16h
0x18000fc71  jmp     short loc_18000FCB0
0x18000fc73  test    rbp, rbp
0x18000fc76  jz      short loc_18000FC8D
0x18000fc78  cmp     rdi, rbx
0x18000fc7b  jb      short loc_18000FC8D
0x18000fc7d  mov     r8, rbx; Size
0x18000fc80  mov     rdx, rbp; Src
0x18000fc83  mov     rcx, rsi; void *
0x18000fc86  call    memcpy_0
0x18000fc8b  jmp     short loc_18000FCB5
0x18000fc8d  mov     r8, rdi; Size
0x18000fc90  xor     edx, edx; Val
0x18000fc92  mov     rcx, rsi; void *
0x18000fc95  call    memset_0
0x18000fc9a  test    rbp, rbp
0x18000fc9d  jz      short loc_18000FC65
0x18000fc9f  cmp     rdi, rbx
0x18000fca2  jnb     short loc_18000FCB5
0x18000fca4  call    cs:__imp__o__errno
0x18000fcaa  mov     dword ptr [rax], 22h ; '"'
0x18000fcb0  call    _invalid_parameter_noinfo
0x18000fcb5  mov     byte ptr [rbx+rsi-1], 0
0x18000fcba  mov     al, 1
0x18000fcbc  add     rsp, 28h
0x18000fcc0  pop     rdi
0x18000fcc1  pop     rsi
0x18000fcc2  pop     rbp
0x18000fcc3  pop     rbx
0x18000fcc4  retn
```
