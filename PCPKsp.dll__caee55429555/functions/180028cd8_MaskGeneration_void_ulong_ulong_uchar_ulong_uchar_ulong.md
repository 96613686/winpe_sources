# MaskGeneration(void *,ulong,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180028cd8`
- end: `0x180028f1d`
- name: `?MaskGeneration@@YAJPEAXKKPEAEK1K@Z`
- size: `581`
- prototype: `int(void *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18005b2d4`

## callees

- `0x180014a60`
- `0x1800157c0`
- `0x180028cd8`
- `0x180029a20`
- `0x180031760`
- `0x18005305c`
- `0x18005437c`
- `0x180061bac`
- `0x180061f40`
- `0x1800768a0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180028e34`
- `bcrypt!BCryptFinishHash` at `0x180028e67`
- `bcrypt!BCryptFinishHash` at `0x180028e34`
- `bcrypt!BCryptFinishHash` at `0x180028e67`
- `bcrypt!BCryptCreateHash` at `0x180028da0`
- `bcrypt!BCryptCreateHash` at `0x180028da0`
- `bcrypt!BCryptHashData` at `0x180028dc3`
- `bcrypt!BCryptHashData` at `0x180028e0e`
- `bcrypt!BCryptHashData` at `0x180028dc3`
- `bcrypt!BCryptHashData` at `0x180028e0e`
- `bcrypt!BCryptDestroyHash` at `0x180028d6a`
- `bcrypt!BCryptDestroyHash` at `0x180028d6a`

## pseudocode

```c
__int64 __fastcall MaskGeneration(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        ULONG cbInput,
        PUCHAR pbOutput,
        rsize_t SourceSize)
{
  __int64 v7; // r13
  __int64 v8; // rdi
  UCHAR *v9; // rbx
  unsigned int v10; // r15d
  UCHAR *v11; // r12
  BCRYPT_HASH_HANDLE v12; // rsi
  unsigned int v13; // eax
  unsigned int v14; // r14d
  NTSTATUS v15; // eax
  __int64 i; // rcx
  __int64 v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  unsigned int v20; // edi
  const struct std::nothrow_t *v21; // rdx
  int pbSecret; // [rsp+20h] [rbp-58h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  PUCHAR pbHashObject; // [rsp+48h] [rbp-30h] BYREF
  int *v25[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  int v28; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v29; // [rsp+D0h] [rbp+58h]
  PUCHAR pbInput; // [rsp+D8h] [rbp+60h]

  pbInput = a4;
  v7 = a3;
  v8 = a2;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v25, L"MaskGeneration", 1);
  v28 = 0;
  wil::make_unique_nothrow<unsigned char [0]>(&pbHashObject, (unsigned int)(v8 + v7));
  v9 = pbHashObject;
  if ( pbHashObject )
  {
    v10 = SourceSize;
    v11 = pbOutput;
    v12 = 0;
    phHash = 0;
    v13 = ((int)v8 + (int)SourceSize - 1) / (unsigned int)v8;
    v14 = 0;
    v29 = v13;
    while ( 1 )
    {
      LODWORD(SourceSize) = v14;
      if ( v14 >= v13 )
        goto LABEL_20;
      if ( v12 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&pbOutput);
        BCryptDestroyHash(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&pbOutput);
      }
      phHash = 0;
      v15 = BCryptCreateHash(a1, &phHash, v9, v7, 0, 0, 0);
      if ( v15 < 0 )
      {
        v17 = 2133;
        goto LABEL_26;
      }
      v15 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( v15 < 0 )
      {
        v17 = 2138;
        goto LABEL_26;
      }
      if ( v29 >= 0x100 )
      {
        for ( i = 0; i != 4; ++i )
          *((_BYTE *)&v28 + i) = ((_BYTE *)&SourceSize - i)[3];
      }
      else
      {
        HIBYTE(v28) = v14;
      }
      v15 = BCryptHashData(phHash, (PUCHAR)&v28, 4u, 0);
      if ( v15 < 0 )
      {
        v17 = 2157;
        goto LABEL_26;
      }
      if ( v10 < (unsigned int)v8 )
        break;
      v15 = BCryptFinishHash(phHash, v11, v8, 0);
      if ( v15 < 0 )
      {
        v17 = 2165;
LABEL_26:
        v20 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v17,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
                (const char *)(unsigned int)v15,
                pbSecret);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
        if ( v9 )
          operator delete(v9, v21);
        KspFunctionLogger::~KspFunctionLogger(v25);
        return v20;
      }
      v12 = phHash;
      v10 -= v8;
      v13 = v29;
      v11 += v8;
      ++v14;
    }
    v15 = BCryptFinishHash(phHash, &v9[v7], v8, 0);
    if ( v15 < 0 )
    {
      v17 = 2174;
      goto LABEL_26;
    }
    memcpy_s_0(v11, v10, &v9[v7], v10);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    if ( v9 )
      operator delete(v9, v18);
    KspFunctionLogger::~KspFunctionLogger(v25);
    return 0;
  }
  else
  {
    KspFunctionLogger::~KspFunctionLogger(v25);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180028cd8  mov     [rsp-40h+pbInput], r9
0x180028cdd  mov     [rsp-40h+hAlgorithm], rcx
0x180028ce2  push    rbp
0x180028ce3  push    rbx
0x180028ce4  push    rsi
0x180028ce5  push    rdi
0x180028ce6  push    r12
0x180028ce8  push    r13
0x180028cea  push    r14
0x180028cec  push    r15
0x180028cee  mov     rbp, rsp
0x180028cf1  sub     rsp, 78h
0x180028cf5  mov     r13d, r8d
0x180028cf8  lea     rcx, [rbp+var_28]; this
0x180028cfc  mov     edi, edx
0x180028cfe  mov     r8b, 1; bool
0x180028d01  lea     rdx, aMaskgeneration; "MaskGeneration"
0x180028d08  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180028d0d  lea     edx, [rdi+r13]
0x180028d11  mov     [rbp+arg_8], 0
0x180028d18  lea     rcx, [rbp+pbHashObject]
0x180028d1c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180028d21  mov     rbx, [rbp+pbHashObject]
0x180028d25  test    rbx, rbx
0x180028d28  jz      loc_180028EFD
0x180028d2e  mov     r15d, dword ptr [rbp+SourceSize]
0x180028d32  xor     edx, edx
0x180028d34  mov     r12, [rbp+pbOutput]
0x180028d38  xor     esi, esi
0x180028d3a  mov     [rbp+phHash], rsi
0x180028d3e  lea     eax, [r15-1]
0x180028d42  add     eax, edi
0x180028d44  div     edi
0x180028d46  xor     r14d, r14d
0x180028d49  mov     [rbp+arg_10], eax
0x180028d4c  mov     dword ptr [rbp+SourceSize], r14d
0x180028d50  cmp     r14d, eax
0x180028d53  jnb     loc_180028E8F
0x180028d59  test    rsi, rsi
0x180028d5c  jz      short loc_180028D7F
0x180028d5e  lea     rcx, [rbp+pbOutput]; this
0x180028d62  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180028d67  mov     rcx, rsi; hHash
0x180028d6a  call    cs:__imp_BCryptDestroyHash
0x180028d71  nop     dword ptr [rax+rax+00h]
0x180028d76  lea     rcx, [rbp+pbOutput]; this
0x180028d7a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180028d7f  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x180028d83  lea     rdx, [rbp+phHash]; phHash
0x180028d87  xor     esi, esi
0x180028d89  mov     r9d, r13d; cbHashObject
0x180028d8c  mov     [rsp+78h+dwFlags], esi; dwFlags
0x180028d90  mov     r8, rbx; pbHashObject
0x180028d93  mov     [rsp+78h+cbSecret], esi; cbSecret
0x180028d97  mov     [rsp+78h+pbSecret], rsi; int
0x180028d9c  mov     [rbp+phHash], rsi
0x180028da0  call    cs:__imp_BCryptCreateHash
0x180028da7  nop     dword ptr [rax+rax+00h]
0x180028dac  test    eax, eax
0x180028dae  js      loc_180028EC0
0x180028db4  mov     r8d, [rbp+cbInput]; cbInput
0x180028db8  xor     r9d, r9d; dwFlags
0x180028dbb  mov     rdx, [rbp+pbInput]; pbInput
0x180028dbf  mov     rcx, [rbp+phHash]; hHash
0x180028dc3  call    cs:__imp_BCryptHashData
0x180028dca  nop     dword ptr [rax+rax+00h]
0x180028dcf  test    eax, eax
0x180028dd1  js      loc_180028EB9
0x180028dd7  cmp     [rbp+arg_10], 100h
0x180028dde  jnb     short loc_180028DE6
0x180028de0  mov     byte ptr [rbp+arg_8+3], r14b
0x180028de4  jmp     short loc_180028DFF
0x180028de6  mov     rcx, rsi
0x180028de9  lea     rax, [rbp+SourceSize+3]
0x180028ded  sub     rax, rcx
0x180028df0  mov     al, [rax]
0x180028df2  mov     byte ptr [rbp+rcx+arg_8], al
0x180028df6  inc     rcx
0x180028df9  cmp     rcx, 4
0x180028dfd  jnz     short loc_180028DE9
0x180028dff  mov     rcx, [rbp+phHash]; hHash
0x180028e03  lea     rdx, [rbp+arg_8]; pbInput
0x180028e07  xor     r9d, r9d; dwFlags
0x180028e0a  lea     r8d, [r9+4]; cbInput
0x180028e0e  call    cs:__imp_BCryptHashData
0x180028e15  nop     dword ptr [rax+rax+00h]
0x180028e1a  test    eax, eax
0x180028e1c  js      loc_180028EB2
0x180028e22  mov     rcx, [rbp+phHash]; hHash
0x180028e26  xor     r9d, r9d; dwFlags
0x180028e29  mov     r8d, edi; cbOutput
0x180028e2c  cmp     r15d, edi
0x180028e2f  jb      short loc_180028E60
0x180028e31  mov     rdx, r12; pbOutput
0x180028e34  call    cs:__imp_BCryptFinishHash
0x180028e3b  nop     dword ptr [rax+rax+00h]
0x180028e40  test    eax, eax
0x180028e42  js      short loc_180028E59
0x180028e44  mov     rsi, [rbp+phHash]
0x180028e48  sub     r15d, edi
0x180028e4b  mov     eax, [rbp+arg_10]
0x180028e4e  add     r12, rdi
0x180028e51  inc     r14d
0x180028e54  jmp     loc_180028D4C
0x180028e59  mov     edx, 875h
0x180028e5e  jmp     short loc_180028EC5
0x180028e60  lea     rsi, [rbx+r13]
0x180028e64  mov     rdx, rsi; pbOutput
0x180028e67  call    cs:__imp_BCryptFinishHash
0x180028e6e  nop     dword ptr [rax+rax+00h]
0x180028e73  test    eax, eax
0x180028e75  jns     short loc_180028E7E
0x180028e77  mov     edx, 87Eh
0x180028e7c  jmp     short loc_180028EC5
0x180028e7e  mov     edx, r15d; DestinationSize
0x180028e81  mov     r8, rsi; Source
0x180028e84  mov     r9d, r15d; SourceSize
0x180028e87  mov     rcx, r12; Destination
0x180028e8a  call    memcpy_s_0
0x180028e8f  lea     rcx, [rbp+phHash]
0x180028e93  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180028e98  test    rbx, rbx
0x180028e9b  jz      short loc_180028EA5
0x180028e9d  mov     rcx, rbx; void *
0x180028ea0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ea5  lea     rcx, [rbp+var_28]; this
0x180028ea9  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028eae  xor     eax, eax
0x180028eb0  jmp     short loc_180028F0B
0x180028eb2  mov     edx, 86Dh
0x180028eb7  jmp     short loc_180028EC5
0x180028eb9  mov     edx, 85Ah
0x180028ebe  jmp     short loc_180028EC5
0x180028ec0  mov     edx, 855h; void *
0x180028ec5  mov     rcx, [rbp+40h]; this
0x180028ec9  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180028ed0  mov     r9d, eax; char *
0x180028ed3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180028ed8  lea     rcx, [rbp+phHash]
0x180028edc  mov     edi, eax
0x180028ede  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180028ee3  test    rbx, rbx
0x180028ee6  jz      short loc_180028EF0
0x180028ee8  mov     rcx, rbx; void *
0x180028eeb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ef0  lea     rcx, [rbp+var_28]; this
0x180028ef4  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028ef9  mov     eax, edi
0x180028efb  jmp     short loc_180028F0B
0x180028efd  lea     rcx, [rbp+var_28]; this
0x180028f01  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180028f06  mov     eax, 80070008h
0x180028f0b  add     rsp, 78h
0x180028f0f  pop     r15
0x180028f11  pop     r14
0x180028f13  pop     r13
0x180028f15  pop     r12
0x180028f17  pop     rdi
0x180028f18  pop     rsi
0x180028f19  pop     rbx
0x180028f1a  pop     rbp
0x180028f1b  retn
```
