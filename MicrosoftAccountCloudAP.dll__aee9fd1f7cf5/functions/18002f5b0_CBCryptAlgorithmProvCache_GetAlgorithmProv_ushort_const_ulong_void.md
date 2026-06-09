# CBCryptAlgorithmProvCache::GetAlgorithmProv(ushort const *,ulong,void * &)

- ea: `0x18002f5b0`
- end: `0x18002f6c5`
- name: `?GetAlgorithmProv@CBCryptAlgorithmProvCache@@QEAAJPEBGKAEAPEAX@Z`
- size: `277`
- prototype: `__int64 __fastcall(CBCryptAlgorithmProvCache *this, const unsigned __int16 *, ULONG, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002f3d4`
- `0x18002f6cc`

## callees

- `0x18002f024`
- `0x18002f5b0`
- `0x18002fa3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f5fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f5fb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f65a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f65a`

## pseudocode

```c
__int64 __fastcall CBCryptAlgorithmProvCache::GetAlgorithmProv(
        CBCryptAlgorithmProvCache *this,
        const unsigned __int16 *a2,
        ULONG a3,
        void **a4)
{
  unsigned int i; // edi
  _QWORD *v7; // rax
  __int64 v8; // rax
  volatile signed __int64 *v9; // rdi
  void *v10; // rax
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+28h] [rbp-30h]

  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int64)qword_18004DA38 )
      return (unsigned int)-2147024809;
    if ( *(_DWORD *)(ATL::CAtlArray<_bcryptAlgorithmHandle,ATL::CElementTraits<_bcryptAlgorithmHandle>>::operator[](
                       &Block,
                       i)
                   + 8) == a3 )
    {
      v7 = (_QWORD *)ATL::CAtlArray<_bcryptAlgorithmHandle,ATL::CElementTraits<_bcryptAlgorithmHandle>>::operator[](
                       &Block,
                       i);
      if ( !(unsigned int)_o__wcsicmp(*v7, L"SHA256") )
        break;
    }
  }
  v8 = ATL::CAtlArray<_bcryptAlgorithmHandle,ATL::CElementTraits<_bcryptAlgorithmHandle>>::operator[](&Block, i);
  v9 = (volatile signed __int64 *)(v8 + 16);
  if ( v8 == -16 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v10 = (void *)*v9;
    if ( *v9 )
    {
      v11 = 0;
LABEL_9:
      *a4 = v10;
      return v11;
    }
    phAlgorithm = 0;
    v15 = 0;
    v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, a3);
    v11 = v12;
    if ( v12 > 0 )
      v11 = (unsigned __int16)v12 | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
    {
      v15 = 1;
      if ( !_InterlockedCompareExchange64(v9, (signed __int64)phAlgorithm, 0) )
      {
        phAlgorithm = 0;
        v15 = 0;
      }
      CBCryptAlgorithmProv::Release((CBCryptAlgorithmProv *)&phAlgorithm);
      v10 = (void *)*v9;
      goto LABEL_9;
    }
    CBCryptAlgorithmProv::Release((CBCryptAlgorithmProv *)&phAlgorithm);
  }
  return v11;
}

```

## disassembly

```asm
0x18002f5b0  push    rbx
0x18002f5b2  push    rbp
0x18002f5b3  push    rsi
0x18002f5b4  push    rdi
0x18002f5b5  sub     rsp, 38h
0x18002f5b9  mov     rsi, r9
0x18002f5bc  mov     ebp, r8d
0x18002f5bf  xor     edi, edi
0x18002f5c1  mov     ebx, edi
0x18002f5c3  cmp     rbx, cs:qword_18004DA38
0x18002f5ca  jnb     loc_18002F6B5
0x18002f5d0  mov     edx, ebx
0x18002f5d2  lea     rcx, Block
0x18002f5d9  call    ??A?$CAtlArray@U_bcryptAlgorithmHandle@@V?$CElementTraits@U_bcryptAlgorithmHandle@@@ATL@@@ATL@@QEAAAEAU_bcryptAlgorithmHandle@@_K@Z; ATL::CAtlArray<_bcryptAlgorithmHandle,ATL::CElementTraits<_bcryptAlgorithmHandle>>::operator[](unsigned __int64)
0x18002f5de  cmp     [rax+8], ebp
0x18002f5e1  jnz     short loc_18002F605
0x18002f5e3  mov     edx, ebx
0x18002f5e5  lea     rcx, Block
0x18002f5ec  call    ??A?$CAtlArray@U_bcryptAlgorithmHandle@@V?$CElementTraits@U_bcryptAlgorithmHandle@@@ATL@@@ATL@@QEAAAEAU_bcryptAlgorithmHandle@@_K@Z; ATL::CAtlArray<_bcryptAlgorithmHandle,ATL::CElementTraits<_bcryptAlgorithmHandle>>::operator[](unsigned __int64)
0x18002f5f1  lea     rdx, aSha256_0; "SHA256"
0x18002f5f8  mov     rcx, [rax]
0x18002f5fb  call    cs:__imp__o__wcsicmp
0x18002f601  test    eax, eax
0x18002f603  jz      short loc_18002F609
0x18002f605  inc     edi
0x18002f607  jmp     short loc_18002F5C1
0x18002f609  mov     rdx, rbx
0x18002f60c  lea     rcx, Block
0x18002f613  call    ??A?$CAtlArray@U_bcryptAlgorithmHandle@@V?$CElementTraits@U_bcryptAlgorithmHandle@@@ATL@@@ATL@@QEAAAEAU_bcryptAlgorithmHandle@@_K@Z; ATL::CAtlArray<_bcryptAlgorithmHandle,ATL::CElementTraits<_bcryptAlgorithmHandle>>::operator[](unsigned __int64)
0x18002f618  lea     rdi, [rax+10h]
0x18002f61c  test    rdi, rdi
0x18002f61f  jz      loc_18002F6B5
0x18002f625  mov     rax, [rdi]
0x18002f628  test    rax, rax
0x18002f62b  jz      short loc_18002F637
0x18002f62d  xor     ebx, ebx
0x18002f62f  mov     [rsi], rax
0x18002f632  jmp     loc_18002F6BA
0x18002f637  mov     r9d, ebp; dwFlags
0x18002f63a  mov     [rsp+58h+phAlgorithm], 0
0x18002f643  xor     r8d, r8d; pszImplementation
0x18002f646  mov     [rsp+58h+var_30], 0
0x18002f64e  lea     rdx, aSha256_0; "SHA256"
0x18002f655  lea     rcx, [rsp+58h+phAlgorithm]; phAlgorithm
0x18002f65a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002f660  mov     ebx, eax
0x18002f662  test    eax, eax
0x18002f664  jle     short loc_18002F66F
0x18002f666  movzx   ebx, ax
0x18002f669  or      ebx, 80070000h
0x18002f66f  test    ebx, ebx
0x18002f671  js      short loc_18002F6A9
0x18002f673  mov     rcx, [rsp+58h+phAlgorithm]
0x18002f678  xor     eax, eax
0x18002f67a  mov     [rsp+58h+var_30], 1
0x18002f682  lock cmpxchg [rdi], rcx
0x18002f687  jnz     short loc_18002F69A
0x18002f689  mov     [rsp+58h+phAlgorithm], 0
0x18002f692  mov     [rsp+58h+var_30], 0
0x18002f69a  lea     rcx, [rsp+58h+phAlgorithm]; this
0x18002f69f  call    ?Release@CBCryptAlgorithmProv@@QEAAJXZ; CBCryptAlgorithmProv::Release(void)
0x18002f6a4  mov     rax, [rdi]
0x18002f6a7  jmp     short loc_18002F62F
0x18002f6a9  lea     rcx, [rsp+58h+phAlgorithm]; this
0x18002f6ae  call    ?Release@CBCryptAlgorithmProv@@QEAAJXZ; CBCryptAlgorithmProv::Release(void)
0x18002f6b3  jmp     short loc_18002F6BA
0x18002f6b5  mov     ebx, 80070057h
0x18002f6ba  mov     eax, ebx
0x18002f6bc  add     rsp, 38h
0x18002f6c0  pop     rdi
0x18002f6c1  pop     rsi
0x18002f6c2  pop     rbp
0x18002f6c3  pop     rbx
0x18002f6c4  retn
```
