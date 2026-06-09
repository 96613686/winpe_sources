# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006e7c`
- end: `0x180006fa3`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `295`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006060`
- `0x180006e7c`

## callees

- `0x180001c0c`
- `0x180006e7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006f53`
- `msvcrt!memcpy_s` at `0x180006f53`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006f6e`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006f8b`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006f6e`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006f8b`

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
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  char *v12; // r10
  char *v13; // rdi
  _BYTE *v14; // r8
  _BYTE *v15; // rdi
  rsize_t v16; // rbx
  rsize_t v17; // r10
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

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
      v11 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v11;
      while ( a3[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        exception::exception((exception *)pExceptionObject);
        throw (exception *)pExceptionObject;
      }
      v12 = &a3[a4];
      v13 = &a3[(unsigned int)v11];
      if ( v12 - v13 > 2 )
      {
        *v13 = 92;
        v14 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v10;
        while ( v14[v10] );
        if ( v10 > 0xFFFFFFFF )
        {
          exception::exception((exception *)pExceptionObject);
          throw (exception *)pExceptionObject;
        }
        v15 = v13 + 1;
        v16 = (unsigned int)(v10 + 1);
        v17 = v12 - v15;
        if ( v16 >= v17 )
          v16 = v17;
        memcpy_s(v15, v17, v14, v16);
        v15[v16 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006e7c  push    rbx
0x180006e7e  push    rbp
0x180006e7f  push    rsi
0x180006e80  push    rdi
0x180006e81  sub     rsp, 48h
0x180006e85  xor     al, al
0x180006e87  mov     byte ptr [r8], 0
0x180006e8b  mov     rbp, r9
0x180006e8e  mov     rdi, r8
0x180006e91  mov     rsi, rdx
0x180006e94  mov     rbx, rcx
0x180006e97  test    rdx, rdx
0x180006e9a  jz      loc_180006F60
0x180006ea0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006ea4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006ea9  mov     rdx, [rsi+20h]
0x180006ead  test    rdx, rdx
0x180006eb0  jz      loc_180006F60
0x180006eb6  cmp     dword ptr [rdx], 0
0x180006eb9  jnz     short loc_180006ECC
0x180006ebb  mov     eax, 1
0x180006ec0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006ec8  inc     eax
0x180006eca  mov     [rdx], eax
0x180006ecc  cmp     dword ptr [rbx+50h], 0
0x180006ed0  jnz     short loc_180006EE3
0x180006ed2  movups  xmm0, xmmword ptr [rdx]
0x180006ed5  movups  xmmword ptr [rbx+50h], xmm0
0x180006ed9  movsd   xmm1, qword ptr [rdx+10h]
0x180006ede  movsd   qword ptr [rbx+60h], xmm1
0x180006ee3  movups  xmm0, xmmword ptr [rdx]
0x180006ee6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006eea  mov     rax, rcx
0x180006eed  movups  xmmword ptr [rbx+68h], xmm0
0x180006ef1  movsd   xmm1, qword ptr [rdx+10h]
0x180006ef6  movsd   qword ptr [rbx+78h], xmm1
0x180006efb  inc     rax
0x180006efe  cmp     byte ptr [rdi+rax], 0
0x180006f02  jnz     short loc_180006EFB
0x180006f04  mov     r9d, 0FFFFFFFFh
0x180006f0a  cmp     rax, r9
0x180006f0d  ja      short loc_180006F69
0x180006f0f  mov     eax, eax
0x180006f11  lea     r10, [rdi+rbp]
0x180006f15  add     rdi, rax
0x180006f18  mov     rax, r10
0x180006f1b  sub     rax, rdi
0x180006f1e  cmp     rax, 2
0x180006f22  jle     short loc_180006F5E
0x180006f24  mov     byte ptr [rdi], 5Ch ; '\'
0x180006f27  mov     r8, [rdx+8]; Source
0x180006f2b  inc     rcx
0x180006f2e  cmp     byte ptr [r8+rcx], 0
0x180006f33  jnz     short loc_180006F2B
0x180006f35  cmp     rcx, r9
0x180006f38  ja      short loc_180006F86
0x180006f3a  inc     rdi
0x180006f3d  lea     ebx, [rcx+1]
0x180006f40  sub     r10, rdi
0x180006f43  mov     rcx, rdi; Destination
0x180006f46  cmp     rbx, r10
0x180006f49  mov     rdx, r10; DestinationSize
0x180006f4c  cmovnb  rbx, r10
0x180006f50  mov     r9, rbx; SourceSize
0x180006f53  call    cs:__imp_memcpy_s
0x180006f59  mov     byte ptr [rbx+rdi-1], 0
0x180006f5e  mov     al, 1
0x180006f60  add     rsp, 48h
0x180006f64  pop     rdi
0x180006f65  pop     rsi
0x180006f66  pop     rbp
0x180006f67  pop     rbx
0x180006f68  retn
0x180006f69  lea     rcx, [rsp+68h+pExceptionObject]
0x180006f6e  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180006f74  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180006f7b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180006f80  call    _CxxThrowException_0
0x180006f86  lea     rcx, [rsp+68h+pExceptionObject]
0x180006f8b  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180006f91  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180006f98  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180006f9d  call    _CxxThrowException_0
```
