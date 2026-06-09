# GetSystemPreferredRngHandle

- ea: `0x180004800`
- end: `0x180004996`
- name: `GetSystemPreferredRngHandle`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005280`

## callees

- `0x18000466c`
- `0x180004800`
- `0x180005b00`
- `0x180007a7c`
- `0x18000e190`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180004852`
- `ntdll!RtlAcquireResourceShared` at `0x180004852`

## string_xrefs

- `0x1800048a8`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x18000492c`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall GetSystemPreferredRngHandle(BCRYPT_ALG_HANDLE *a1)
{
  BCRYPT_ALG_HANDLE v2; // rax
  BCRYPT_ALG_HANDLE *v3; // rbx
  int v5; // edx
  int v6; // esi
  int v7; // r8d
  int v8; // edx
  int v9; // r8d
  BCRYPT_ALG_HANDLE v10; // rcx
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  hAlgorithm = 0;
  if ( g_fLoadCNGDone )
  {
    v2 = ::hAlgorithm;
    v3 = &::hAlgorithm;
  }
  else
  {
    v2 = qword_180024AA8;
    v3 = &qword_180024AA8;
  }
  if ( v2 )
  {
    if ( !WaitHandle )
    {
      v6 = RegisterReopenWait();
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            v9,
            (unsigned int)"Status",
            v6,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
            244);
        return (unsigned int)v6;
      }
    }
    goto LABEL_5;
  }
  v6 = OpenSystemPreferredAlgorithmProvider(&hAlgorithm);
  if ( v6 >= 0 )
  {
    v10 = hAlgorithm;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v3, (signed __int64)hAlgorithm, 0) )
    {
      BCryptCloseAlgorithmProvider(v10, 0);
    }
    else if ( g_fLoadCNGDone )
    {
      dword_180024AA4 = 1;
    }
LABEL_5:
    RtlAcquireResourceShared(g_pCachedRngRWLock, 1u);
    *a1 = *v3;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v7,
      (unsigned int)"Status",
      v6,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
      186);
  if ( !hAlgorithm )
    return (unsigned int)v6;
  BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004800  mov     [rsp+arg_10], rbx
0x180004805  push    rdi
0x180004806  sub     rsp, 40h
0x18000480a  cmp     cs:g_fLoadCNGDone, 0
0x180004811  mov     rdi, rcx
0x180004814  mov     [rsp+48h+hAlgorithm], 0
0x18000481d  jz      loc_1800048ED
0x180004823  mov     rax, cs:hAlgorithm
0x18000482a  lea     rbx, hAlgorithm
0x180004831  mov     [rsp+48h+arg_0], rsi
0x180004836  test    rax, rax
0x180004839  jz      short loc_180004877
0x18000483b  cmp     cs:WaitHandle, 0
0x180004843  jz      loc_180004900
0x180004849  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180004850  mov     dl, 1; Wait
0x180004852  call    cs:__imp_RtlAcquireResourceShared
0x180004859  nop     dword ptr [rax+rax+00h]
0x18000485e  mov     rax, [rbx]
0x180004861  mov     [rdi], rax
0x180004864  xor     eax, eax
0x180004866  mov     rsi, [rsp+48h+arg_0]
0x18000486b  mov     rbx, [rsp+48h+arg_10]
0x180004870  add     rsp, 40h
0x180004874  pop     rdi
0x180004875  retn
0x180004877  lea     rcx, [rsp+48h+hAlgorithm]
0x18000487c  call    OpenSystemPreferredAlgorithmProvider
0x180004881  mov     esi, eax
0x180004883  test    eax, eax
0x180004885  jns     loc_180004952
0x18000488b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004892  lea     rax, WPP_GLOBAL_Control
0x180004899  cmp     rcx, rax
0x18000489c  jz      short loc_1800048CC
0x18000489e  test    byte ptr [rcx+1Ch], 1
0x1800048a2  jz      short loc_1800048CC
0x1800048a4  mov     rcx, [rcx+10h]
0x1800048a8  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800048af  mov     [rsp+48h+var_18], 1BAh
0x1800048b7  lea     r9, aStatus; "Status"
0x1800048be  mov     [rsp+48h+var_20], rax
0x1800048c3  mov     [rsp+48h+var_28], esi
0x1800048c7  call    WPP_SF_sDsd
0x1800048cc  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x1800048d1  test    rcx, rcx
0x1800048d4  jnz     loc_180004988
0x1800048da  mov     rbx, [rsp+48h+arg_10]
0x1800048df  mov     eax, esi
0x1800048e1  mov     rsi, [rsp+48h+arg_0]
0x1800048e6  add     rsp, 40h
0x1800048ea  pop     rdi
0x1800048eb  retn
0x1800048ed  mov     rax, cs:qword_180024AA8
0x1800048f4  lea     rbx, qword_180024AA8
0x1800048fb  jmp     loc_180004831
0x180004900  call    RegisterReopenWait
0x180004905  mov     esi, eax
0x180004907  test    eax, eax
0x180004909  jns     loc_180004849
0x18000490f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004916  lea     rax, WPP_GLOBAL_Control
0x18000491d  cmp     rcx, rax
0x180004920  jz      short loc_1800048DA
0x180004922  test    byte ptr [rcx+1Ch], 1
0x180004926  jz      short loc_1800048DA
0x180004928  mov     rcx, [rcx+10h]
0x18000492c  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004933  mov     [rsp+48h+var_18], 1F4h
0x18000493b  lea     r9, aStatus; "Status"
0x180004942  mov     [rsp+48h+var_20], rax
0x180004947  mov     [rsp+48h+var_28], esi
0x18000494b  call    WPP_SF_sDsd
0x180004950  jmp     short loc_1800048DA
0x180004952  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x180004957  xor     eax, eax
0x180004959  lock cmpxchg [rbx], rcx
0x18000495e  jnz     short loc_18000497C
0x180004960  cmp     cs:g_fLoadCNGDone, 0
0x180004967  jz      loc_180004849
0x18000496d  mov     cs:dword_180024AA4, 1
0x180004977  jmp     loc_180004849
0x18000497c  xor     edx, edx; dwFlags
0x18000497e  call    BCryptCloseAlgorithmProvider
0x180004983  jmp     loc_180004849
0x180004988  xor     edx, edx; dwFlags
0x18000498a  call    BCryptCloseAlgorithmProvider
0x18000498f  mov     eax, esi
0x180004991  jmp     loc_180004866
```
