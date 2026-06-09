# BoxContainerVerify

- ea: `0x14005482c`
- end: `0x140054ac2`
- name: `BoxContainerVerify`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400195dc`
- `0x140019db4`
- `0x14001a41c`

## callees

- `0x14005482c`
- `0x140080c50`
- `0x140080d36`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140054a8b`
- `KERNEL32!HeapFree` at `0x140054a8b`
- `KERNEL32!HeapAlloc` at `0x140054886`
- `KERNEL32!HeapAlloc` at `0x140054886`
- `KERNEL32!GetProcessHeap` at `0x14005486c`
- `KERNEL32!GetProcessHeap` at `0x140054a77`
- `KERNEL32!GetProcessHeap` at `0x14005486c`
- `KERNEL32!GetProcessHeap` at `0x140054a77`
- `KERNEL32!GetLastError` at `0x140054a31`
- `KERNEL32!GetLastError` at `0x140054a31`
- `KERNEL32!ReadFile` at `0x14005498c`
- `KERNEL32!ReadFile` at `0x14005498c`
- `bcrypt!BCryptFinishHash` at `0x1400549e5`
- `bcrypt!BCryptFinishHash` at `0x1400549e5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400548f9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400548f9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400548cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400548cd`
- `bcrypt!BCryptDestroyHash` at `0x1400549fe`
- `bcrypt!BCryptDestroyHash` at `0x140054a5e`
- `bcrypt!BCryptDestroyHash` at `0x1400549fe`
- `bcrypt!BCryptDestroyHash` at `0x140054a5e`
- `bcrypt!BCryptHashData` at `0x1400549ae`
- `bcrypt!BCryptHashData` at `0x1400549ae`
- `bcrypt!BCryptCreateHash` at `0x14005492f`
- `bcrypt!BCryptCreateHash` at `0x14005492f`

## pseudocode

```c
__int64 __fastcall BoxContainerVerify(_QWORD *a1)
{
  HANDLE ProcessHeap; // rax
  void *v3; // r14
  int v4; // ebx
  unsigned __int64 v5; // rdi
  void *v6; // rcx
  unsigned __int64 v7; // r8
  const void *v8; // rcx
  signed int LastError; // eax
  HANDLE v10; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbOutput[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v15; // [rsp+60h] [rbp-20h]

  phHash = 0;
  *(_OWORD *)pbOutput = 0;
  v15 = 0;
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0xA00000u);
  if ( v3 )
  {
    phAlgorithm = 0;
    if ( !g_hSha256Provider )
    {
      if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0) < 0 )
        __fastfail(7u);
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hSha256Provider, (signed __int64)phAlgorithm, 0) )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
    if ( BCryptCreateHash(g_hSha256Provider, &phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    v4 = FileSetPointer(*a1, *(_QWORD *)(a1[4] + 8LL));
    if ( v4 >= 0 )
    {
      v5 = 0;
      while ( 1 )
      {
        v6 = (void *)*a1;
        v7 = *(_QWORD *)(a1[4] + 16LL) - v5;
        LODWORD(phAlgorithm) = 0;
        if ( v7 > 0xA00000 )
          LODWORD(v7) = 10485760;
        if ( !ReadFile(v6, v3, v7, (LPDWORD)&phAlgorithm, 0) )
          break;
        if ( BCryptHashData(phHash, (PUCHAR)v3, (ULONG)phAlgorithm, 0) < 0 )
          __fastfail(7u);
        v5 += (unsigned int)phAlgorithm;
        if ( v5 >= *(_QWORD *)(a1[4] + 16LL) )
        {
          if ( BCryptFinishHash(phHash, pbOutput, 0x20u, 0) < 0 )
            __fastfail(7u);
          BCryptDestroyHash(phHash);
          v8 = (const void *)(a1[4] + 24LL);
          phHash = 0;
          if ( memcmp_0(v8, pbOutput, 0x20u) )
            v4 = -2147467259;
          goto LABEL_30;
        }
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      v4 = LastError;
    }
  }
  else
  {
    v4 = -2147024882;
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( v3 )
  {
LABEL_30:
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v3);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14005482c  mov     [rsp-28h+arg_8], rbx
0x140054831  mov     [rsp-28h+arg_10], rsi
0x140054836  push    rbp
0x140054837  push    rdi
0x140054838  push    r12
0x14005483a  push    r13
0x14005483c  push    r14
0x14005483e  mov     rbp, rsp
0x140054841  sub     rsp, 80h
0x140054848  mov     rax, cs:__security_cookie
0x14005484f  xor     rax, rsp
0x140054852  mov     [rbp+var_10], rax
0x140054856  xorps   xmm0, xmm0
0x140054859  mov     [rbp+phHash], 0
0x140054861  movups  xmmword ptr [rbp+pbOutput], xmm0
0x140054865  mov     rsi, rcx
0x140054868  movups  [rbp+var_20], xmm0
0x14005486c  call    cs:__imp_GetProcessHeap
0x140054873  nop     dword ptr [rax+rax+00h]
0x140054878  mov     r13d, 0A00000h
0x14005487e  xor     edx, edx; dwFlags
0x140054880  mov     rcx, rax; hHeap
0x140054883  mov     r8d, r13d; dwBytes
0x140054886  call    cs:__imp_HeapAlloc
0x14005488d  nop     dword ptr [rax+rax+00h]
0x140054892  mov     r14, rax
0x140054895  test    rax, rax
0x140054898  jnz     short loc_1400548A4
0x14005489a  mov     ebx, 8007000Eh
0x14005489f  jmp     loc_140054A55
0x1400548a4  cmp     cs:g_hSha256Provider, 0
0x1400548ac  mov     r12d, 7
0x1400548b2  mov     [rbp+phAlgorithm], 0
0x1400548ba  jnz     short loc_140054905
0x1400548bc  xor     r9d, r9d; dwFlags
0x1400548bf  lea     rdx, aSha256; "SHA256"
0x1400548c6  xor     r8d, r8d; pszImplementation
0x1400548c9  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400548cd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400548d4  nop     dword ptr [rax+rax+00h]
0x1400548d9  test    eax, eax
0x1400548db  jns     short loc_1400548E2
0x1400548dd  mov     ecx, r12d
0x1400548e0  int     29h; Win8: RtlFailFast(ecx)
0x1400548e2  mov     rcx, [rbp+phAlgorithm]
0x1400548e6  xor     eax, eax
0x1400548e8  lock cmpxchg cs:g_hSha256Provider, rcx
0x1400548f1  jz      short loc_140054905
0x1400548f3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1400548f7  xor     edx, edx; dwFlags
0x1400548f9  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140054900  nop     dword ptr [rax+rax+00h]
0x140054905  mov     rcx, cs:g_hSha256Provider; hAlgorithm
0x14005490c  lea     rdx, [rbp+phHash]; phHash
0x140054910  mov     [rsp+80h+dwFlags], 0; dwFlags
0x140054918  xor     r9d, r9d; cbHashObject
0x14005491b  mov     [rsp+80h+cbSecret], 0; cbSecret
0x140054923  xor     r8d, r8d; pbHashObject
0x140054926  mov     [rsp+80h+pbSecret], 0; pbSecret
0x14005492f  call    cs:__imp_BCryptCreateHash
0x140054936  nop     dword ptr [rax+rax+00h]
0x14005493b  test    eax, eax
0x14005493d  jns     short loc_140054944
0x14005493f  mov     rcx, r12
0x140054942  int     29h; Win8: RtlFailFast(ecx)
0x140054944  mov     rdx, [rsi+20h]
0x140054948  mov     rcx, [rsi]
0x14005494b  mov     rdx, [rdx+8]
0x14005494f  call    FileSetPointer
0x140054954  mov     ebx, eax
0x140054956  test    eax, eax
0x140054958  js      loc_140054A55
0x14005495e  xor     edi, edi
0x140054960  mov     rcx, [rsi+20h]
0x140054964  lea     r9, [rbp+phAlgorithm]; lpNumberOfBytesRead
0x140054968  mov     rdx, r14; lpBuffer
0x14005496b  mov     [rsp+80h+pbSecret], 0; lpOverlapped
0x140054974  mov     r8, [rcx+10h]
0x140054978  mov     rcx, [rsi]; hFile
0x14005497b  sub     r8, rdi
0x14005497e  cmp     r8, r13
0x140054981  mov     dword ptr [rbp+phAlgorithm], 0
0x140054988  cmova   r8d, r13d; nNumberOfBytesToRead
0x14005498c  call    cs:__imp_ReadFile
0x140054993  nop     dword ptr [rax+rax+00h]
0x140054998  test    eax, eax
0x14005499a  jz      loc_140054A31
0x1400549a0  mov     r8d, dword ptr [rbp+phAlgorithm]; cbInput
0x1400549a4  xor     r9d, r9d; dwFlags
0x1400549a7  mov     rcx, [rbp+phHash]; hHash
0x1400549ab  mov     rdx, r14; pbInput
0x1400549ae  call    cs:__imp_BCryptHashData
0x1400549b5  nop     dword ptr [rax+rax+00h]
0x1400549ba  test    eax, eax
0x1400549bc  jns     short loc_1400549C3
0x1400549be  mov     rcx, r12
0x1400549c1  int     29h; Win8: RtlFailFast(ecx)
0x1400549c3  mov     eax, dword ptr [rbp+phAlgorithm]
0x1400549c6  add     rdi, rax
0x1400549c9  mov     rax, [rsi+20h]
0x1400549cd  cmp     rdi, [rax+10h]
0x1400549d1  jb      short loc_140054960
0x1400549d3  mov     rcx, [rbp+phHash]; hHash
0x1400549d7  lea     rdx, [rbp+pbOutput]; pbOutput
0x1400549db  xor     r9d, r9d; dwFlags
0x1400549de  lea     edi, [r9+20h]
0x1400549e2  mov     r8d, edi; cbOutput
0x1400549e5  call    cs:__imp_BCryptFinishHash
0x1400549ec  nop     dword ptr [rax+rax+00h]
0x1400549f1  test    eax, eax
0x1400549f3  jns     short loc_1400549FA
0x1400549f5  mov     rcx, r12
0x1400549f8  int     29h; Win8: RtlFailFast(ecx)
0x1400549fa  mov     rcx, [rbp+phHash]; hHash
0x1400549fe  call    cs:__imp_BCryptDestroyHash
0x140054a05  nop     dword ptr [rax+rax+00h]
0x140054a0a  mov     rcx, [rsi+20h]
0x140054a0e  lea     rdx, [rbp+pbOutput]; Buf2
0x140054a12  add     rcx, 18h; Buf1
0x140054a16  mov     [rbp+phHash], 0
0x140054a1e  mov     r8, rdi; Size
0x140054a21  call    memcmp_0
0x140054a26  test    eax, eax
0x140054a28  jz      short loc_140054A77
0x140054a2a  mov     ebx, 80004005h
0x140054a2f  jmp     short loc_140054A77
0x140054a31  call    cs:__imp_GetLastError
0x140054a38  nop     dword ptr [rax+rax+00h]
0x140054a3d  test    eax, eax
0x140054a3f  jle     short loc_140054A49
0x140054a41  movzx   eax, ax
0x140054a44  or      eax, 80070000h
0x140054a49  mov     ebx, 80004005h
0x140054a4e  test    eax, eax
0x140054a50  cmovns  eax, ebx
0x140054a53  mov     ebx, eax
0x140054a55  mov     rcx, [rbp+phHash]; hHash
0x140054a59  test    rcx, rcx
0x140054a5c  jz      short loc_140054A72
0x140054a5e  call    cs:__imp_BCryptDestroyHash
0x140054a65  nop     dword ptr [rax+rax+00h]
0x140054a6a  mov     [rbp+phHash], 0
0x140054a72  test    r14, r14
0x140054a75  jz      short loc_140054A97
0x140054a77  call    cs:__imp_GetProcessHeap
0x140054a7e  nop     dword ptr [rax+rax+00h]
0x140054a83  mov     r8, r14; lpMem
0x140054a86  xor     edx, edx; dwFlags
0x140054a88  mov     rcx, rax; hHeap
0x140054a8b  call    cs:__imp_HeapFree
0x140054a92  nop     dword ptr [rax+rax+00h]
0x140054a97  mov     eax, ebx
0x140054a99  mov     rcx, [rbp+var_10]
0x140054a9d  xor     rcx, rsp; StackCookie
0x140054aa0  call    __security_check_cookie
0x140054aa5  lea     r11, [rsp+80h+var_s0]
0x140054aad  mov     rbx, [r11+38h]
0x140054ab1  mov     rsi, [r11+40h]
0x140054ab5  mov     rsp, r11
0x140054ab8  pop     r14
0x140054aba  pop     r13
0x140054abc  pop     r12
0x140054abe  pop     rdi
0x140054abf  pop     rbp
0x140054ac0  retn
```
