# CINetEdge::GetPreviouslySubmittedCredential(ushort * *)

- ea: `0x1800e26b8`
- end: `0x1800e28bc`
- name: `?GetPreviouslySubmittedCredential@CINetEdge@@IEAAHPEAPEAG@Z`
- size: `516`
- prototype: `__int64 __fastcall(CINetEdge *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e13c8`

## callees

- `0x18000a110`
- `0x18000a270`
- `0x1800e26b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e27ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e27ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e275b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e27e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e275b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e27e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e289a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e289a`
- `WININET!InternetQueryOptionW` at `0x1800e272f`
- `WININET!InternetQueryOptionW` at `0x1800e278f`
- `WININET!InternetQueryOptionW` at `0x1800e27c2`
- `WININET!InternetQueryOptionW` at `0x1800e2812`
- `WININET!InternetQueryOptionW` at `0x1800e272f`
- `WININET!InternetQueryOptionW` at `0x1800e278f`
- `WININET!InternetQueryOptionW` at `0x1800e27c2`
- `WININET!InternetQueryOptionW` at `0x1800e2812`

## pseudocode

```c
__int64 __fastcall CINetEdge::GetPreviouslySubmittedCredential(CINetEdge *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  bool v6; // cf
  unsigned __int16 *v7; // rsi
  _WORD *v8; // rdi
  BOOL v9; // ebx
  DWORD LastError; // eax
  __int64 v11; // r15
  unsigned __int16 *v12; // rax
  void *v13; // rcx
  DWORD v14; // eax
  _WORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int16 *i; // rax
  __int64 v19; // rcx
  _BYTE *j; // rax
  CINetEdge *v22; // [rsp+20h] [rbp-18h] BYREF
  char v23; // [rsp+28h] [rbp-10h]
  DWORD dwBufferLength; // [rsp+88h] [rbp+50h] BYREF

  v4 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v22 = this;
    v23 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 300);
    if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v22) )
    {
LABEL_28:
      CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v22);
      return v4;
    }
    v5 = (void *)*((_QWORD *)this + 47);
    v6 = (*((_BYTE *)this + 976) & 1) != 0;
    dwBufferLength = 0;
    v7 = 0;
    v8 = 0;
    v9 = InternetQueryOptionW(v5, v6 ? 43 : 28, 0, &dwBufferLength);
    LastError = GetLastError();
    v11 = -1;
    if ( v9
      || LastError == 122
      && dwBufferLength
      && (v12 = (unsigned __int16 *)CoTaskMemAlloc(dwBufferLength), (v7 = v12) != 0)
      && InternetQueryOptionW(
           *((HINTERNET *)this + 47),
           (*((_BYTE *)this + 976) & 1) != 0 ? 43 : 28,
           v12,
           &dwBufferLength) )
    {
      v13 = (void *)*((_QWORD *)this + 47);
      v6 = (*((_BYTE *)this + 976) & 1) != 0;
      dwBufferLength = 0;
      v4 = InternetQueryOptionW(v13, v6 ? 44 : 29, 0, &dwBufferLength);
      v14 = GetLastError();
      if ( v4
        || v14 == 122
        && dwBufferLength
        && (v15 = CoTaskMemAlloc(dwBufferLength), (v8 = v15) != 0)
        && (v4 = InternetQueryOptionW(
                   *((HINTERNET *)this + 47),
                   (*((_BYTE *)this + 976) & 1) != 0 ? 44 : 29,
                   v15,
                   &dwBufferLength)) != 0 )
      {
        if ( !v7 )
          goto LABEL_23;
        if ( *v7 && v8 && *v8 )
        {
          *a2 = v7;
          goto LABEL_24;
        }
      }
    }
    if ( v7 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v7[v16] );
      v17 = 2 * v16;
      for ( i = v7; v17; --v17 )
      {
        *(_BYTE *)i = 0;
        i = (unsigned __int16 *)((char *)i + 1);
      }
    }
LABEL_23:
    CoTaskMemFree(v7);
    v4 = 0;
    if ( !v8 )
    {
LABEL_27:
      CoTaskMemFree(v8);
      goto LABEL_28;
    }
    do
LABEL_24:
      ++v11;
    while ( v8[v11] );
    v19 = 2 * v11;
    for ( j = v8; v19; --v19 )
      *j++ = 0;
    goto LABEL_27;
  }
  return v4;
}

```

## disassembly

```asm
0x1800e26b8  push    rbp
0x1800e26ba  push    rbx
0x1800e26bb  push    rsi
0x1800e26bc  push    rdi
0x1800e26bd  push    r12
0x1800e26bf  push    r13
0x1800e26c1  push    r14
0x1800e26c3  push    r15
0x1800e26c5  mov     rbp, rsp
0x1800e26c8  sub     rsp, 38h
0x1800e26cc  xor     r13d, r13d
0x1800e26cf  mov     r12, rdx
0x1800e26d2  mov     r14, rcx
0x1800e26d5  mov     ebx, r13d
0x1800e26d8  test    rdx, rdx
0x1800e26db  jz      loc_1800E28A9
0x1800e26e1  mov     [rdx], r13
0x1800e26e4  mov     [rbp+var_18], rcx
0x1800e26e8  mov     [rbp+var_10], r13b
0x1800e26ec  lock inc dword ptr [rcx+4B0h]
0x1800e26f3  lea     rcx, [rbp+var_18]; this
0x1800e26f7  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x1800e26fc  test    al, al
0x1800e26fe  jz      loc_1800E28A0
0x1800e2704  mov     al, [r14+3D0h]
0x1800e270b  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800e270f  mov     rcx, [r14+178h]; hInternet
0x1800e2716  and     al, 1
0x1800e2718  neg     al
0x1800e271a  mov     [rbp+dwBufferLength], r13d
0x1800e271e  mov     esi, r13d
0x1800e2721  mov     edi, r13d
0x1800e2724  sbb     edx, edx
0x1800e2726  xor     r8d, r8d; lpBuffer
0x1800e2729  and     edx, 0Fh
0x1800e272c  add     edx, 1Ch; dwOption
0x1800e272f  call    cs:__imp_InternetQueryOptionW
0x1800e2735  mov     ebx, eax
0x1800e2737  call    cs:__imp_GetLastError
0x1800e273d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800e2741  test    ebx, ebx
0x1800e2743  jnz     short loc_1800E279D
0x1800e2745  cmp     eax, 7Ah ; 'z'
0x1800e2748  jnz     loc_1800E283A
0x1800e274e  mov     eax, [rbp+dwBufferLength]
0x1800e2751  test    eax, eax
0x1800e2753  jz      loc_1800E283A
0x1800e2759  mov     ecx, eax; cb
0x1800e275b  call    cs:__imp_CoTaskMemAlloc
0x1800e2761  mov     rsi, rax
0x1800e2764  test    rax, rax
0x1800e2767  jz      loc_1800E283A
0x1800e276d  mov     cl, [r14+3D0h]
0x1800e2774  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800e2778  and     cl, 1
0x1800e277b  mov     r8, rax; lpBuffer
0x1800e277e  neg     cl
0x1800e2780  mov     rcx, [r14+178h]; hInternet
0x1800e2787  sbb     edx, edx
0x1800e2789  and     edx, 0Fh
0x1800e278c  add     edx, 1Ch; dwOption
0x1800e278f  call    cs:__imp_InternetQueryOptionW
0x1800e2795  test    eax, eax
0x1800e2797  jz      loc_1800E283A
0x1800e279d  mov     al, [r14+3D0h]
0x1800e27a4  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800e27a8  mov     rcx, [r14+178h]; hInternet
0x1800e27af  and     al, 1
0x1800e27b1  neg     al
0x1800e27b3  mov     [rbp+dwBufferLength], r13d
0x1800e27b7  sbb     edx, edx
0x1800e27b9  xor     r8d, r8d; lpBuffer
0x1800e27bc  and     edx, 0Fh
0x1800e27bf  add     edx, 1Dh; dwOption
0x1800e27c2  call    cs:__imp_InternetQueryOptionW
0x1800e27c8  mov     ebx, eax
0x1800e27ca  call    cs:__imp_GetLastError
0x1800e27d0  test    ebx, ebx
0x1800e27d2  jnz     short loc_1800E281E
0x1800e27d4  cmp     eax, 7Ah ; 'z'
0x1800e27d7  jnz     short loc_1800E283A
0x1800e27d9  mov     eax, [rbp+dwBufferLength]
0x1800e27dc  test    eax, eax
0x1800e27de  jz      short loc_1800E283A
0x1800e27e0  mov     ecx, eax; cb
0x1800e27e2  call    cs:__imp_CoTaskMemAlloc
0x1800e27e8  mov     rdi, rax
0x1800e27eb  test    rax, rax
0x1800e27ee  jz      short loc_1800E283A
0x1800e27f0  mov     cl, [r14+3D0h]
0x1800e27f7  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800e27fb  and     cl, 1
0x1800e27fe  mov     r8, rax; lpBuffer
0x1800e2801  neg     cl
0x1800e2803  mov     rcx, [r14+178h]; hInternet
0x1800e280a  sbb     edx, edx
0x1800e280c  and     edx, 0Fh
0x1800e280f  add     edx, 1Dh; dwOption
0x1800e2812  call    cs:__imp_InternetQueryOptionW
0x1800e2818  mov     ebx, eax
0x1800e281a  test    eax, eax
0x1800e281c  jz      short loc_1800E283A
0x1800e281e  test    rsi, rsi
0x1800e2821  jz      short loc_1800E2864
0x1800e2823  cmp     [rsi], r13w
0x1800e2827  jz      short loc_1800E283A
0x1800e2829  test    rdi, rdi
0x1800e282c  jz      short loc_1800E283A
0x1800e282e  cmp     [rdi], r13w
0x1800e2832  jz      short loc_1800E283A
0x1800e2834  mov     [r12], rsi
0x1800e2838  jmp     short loc_1800E2875
0x1800e283a  test    rsi, rsi
0x1800e283d  jz      short loc_1800E2864
0x1800e283f  mov     rax, r15
0x1800e2842  inc     rax
0x1800e2845  cmp     [rsi+rax*2], r13w
0x1800e284a  jnz     short loc_1800E2842
0x1800e284c  lea     rcx, [rax+rax]
0x1800e2850  mov     rax, rsi
0x1800e2853  test    rcx, rcx
0x1800e2856  jz      short loc_1800E2864
0x1800e2858  mov     [rax], r13b
0x1800e285b  inc     rax
0x1800e285e  sub     rcx, 1
0x1800e2862  jnz     short loc_1800E2858
0x1800e2864  mov     rcx, rsi; pv
0x1800e2867  call    cs:__imp_CoTaskMemFree
0x1800e286d  mov     ebx, r13d
0x1800e2870  test    rdi, rdi
0x1800e2873  jz      short loc_1800E2897
0x1800e2875  inc     r15
0x1800e2878  cmp     [rdi+r15*2], r13w
0x1800e287d  jnz     short loc_1800E2875
0x1800e287f  lea     rcx, [r15+r15]
0x1800e2883  mov     rax, rdi
0x1800e2886  test    rcx, rcx
0x1800e2889  jz      short loc_1800E2897
0x1800e288b  mov     [rax], r13b
0x1800e288e  inc     rax
0x1800e2891  sub     rcx, 1
0x1800e2895  jnz     short loc_1800E288B
0x1800e2897  mov     rcx, rdi; pv
0x1800e289a  call    cs:__imp_CoTaskMemFree
0x1800e28a0  lea     rcx, [rbp+var_18]; this
0x1800e28a4  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x1800e28a9  mov     eax, ebx
0x1800e28ab  add     rsp, 38h
0x1800e28af  pop     r15
0x1800e28b1  pop     r14
0x1800e28b3  pop     r13
0x1800e28b5  pop     r12
0x1800e28b7  pop     rdi
0x1800e28b8  pop     rsi
0x1800e28b9  pop     rbx
0x1800e28ba  pop     rbp
0x1800e28bb  retn
```
