# NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180018a9c`
- end: `0x180018c3e`
- name: `?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `418`
- prototype: `__int64 __fastcall(NgcUtils *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026e6c`
- `0x180027648`
- `0x18005b1a0`
- `0x18005bd7c`
- `0x18005be8c`
- `0x18005c028`
- `0x18005c788`

## callees

- `0x180018a9c`
- `0x18001a77c`
- `0x180021f78`
- `0x180023278`
- `0x1800232a0`
- `0x1800264b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018bfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018bfa`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018ad0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018b4e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018ad0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018b4e`

## string_xrefs

- `0x180018b62`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180018baf`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180018c1d`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NgcUtils::GetNgcStateSeparatedRegistryLocation(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  _BYTE *v11; // rax
  void *v12; // rbx
  _BYTE *i; // rcx
  unsigned int v14; // eax
  unsigned int v15; // edi
  const unsigned __int16 *v16; // rdx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-20h]
  SIZE_T uBytes; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v21[4]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  LODWORD(uBytes) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(this, a2, 0, 0);
  v9 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    v11 = LocalAlloc(0, (unsigned int)uBytes);
    v12 = v11;
    if ( !v11 )
    {
      v9 = -2147024882;
      v10 = 185;
      goto LABEL_19;
    }
    for ( i = &v11[(unsigned int)uBytes]; v11 != i; ++v11 )
      *v11 = 0;
    v14 = GetPersistedRegistryLocationW(this, a2, v12, (unsigned int)uBytes);
    if ( v14 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xC0,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
              (const char *)v14,
              (unsigned int)&uBytes);
LABEL_14:
      LocalFree(v12);
      return v15;
    }
    if ( a3 )
    {
      *(_QWORD *)v21 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v21,
        0);
      v17 = NgcUtils::CombineSeparateStrings((NgcUtils *)v12, v16, a3, v21, (unsigned __int16 **)&uBytes);
      v15 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
          (const char *)(unsigned int)v17,
          v19);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
        goto LABEL_14;
      }
      *(_QWORD *)a4 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
      LocalFree(v12);
    }
    else
    {
      *(_QWORD *)a4 = v12;
    }
    return 0;
  }
  if ( PersistedRegistryLocationW > 0 )
    v9 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
    return v9;
  v10 = 182;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
    (const char *)v9,
    (int)&uBytes);
  return v9;
}

```

## disassembly

```asm
0x180018a9c  push    rbp
0x180018a9e  push    rbx
0x180018a9f  push    rsi
0x180018aa0  push    rdi
0x180018aa1  push    r12
0x180018aa3  push    r14
0x180018aa5  push    r15
0x180018aa7  mov     rbp, rsp
0x180018aaa  sub     rsp, 40h
0x180018aae  mov     rsi, r9
0x180018ab1  mov     dword ptr [rbp+uBytes], 0
0x180018ab8  mov     r14, r8
0x180018abb  lea     rax, [rbp+uBytes]
0x180018abf  xor     r9d, r9d
0x180018ac2  mov     qword ptr [rsp+40h+var_20], rax; int
0x180018ac7  xor     r8d, r8d
0x180018aca  mov     r15, rdx
0x180018acd  mov     r12, rcx
0x180018ad0  call    cs:__imp_GetPersistedRegistryLocationW
0x180018ad7  nop     dword ptr [rax+rax+00h]
0x180018adc  mov     ebx, eax
0x180018ade  cmp     eax, 0EAh
0x180018ae3  jz      short loc_180018B04
0x180018ae5  test    eax, eax
0x180018ae7  jle     short loc_180018AF2
0x180018ae9  movzx   ebx, ax
0x180018aec  or      ebx, 80070000h
0x180018af2  test    ebx, ebx
0x180018af4  jns     loc_180018C2C
0x180018afa  mov     edx, 0B6h
0x180018aff  jmp     loc_180018C19
0x180018b04  mov     edi, dword ptr [rbp+uBytes]
0x180018b07  xor     ecx, ecx; uFlags
0x180018b09  mov     edx, edi; uBytes
0x180018b0b  call    cs:__imp_LocalAlloc
0x180018b12  nop     dword ptr [rax+rax+00h]
0x180018b17  mov     rbx, rax
0x180018b1a  test    rax, rax
0x180018b1d  jz      loc_180018C0F
0x180018b23  lea     rcx, [rdi+rax]
0x180018b27  cmp     rax, rcx
0x180018b2a  jz      short loc_180018B38
0x180018b2c  xor     edx, edx
0x180018b2e  mov     [rax], dl
0x180018b30  inc     rax
0x180018b33  cmp     rax, rcx
0x180018b36  jnz     short loc_180018B2C
0x180018b38  mov     r9d, dword ptr [rbp+uBytes]
0x180018b3c  lea     rax, [rbp+uBytes]
0x180018b40  mov     r8, rbx
0x180018b43  mov     qword ptr [rsp+40h+var_20], rax; int
0x180018b48  mov     rdx, r15
0x180018b4b  mov     rcx, r12
0x180018b4e  call    cs:__imp_GetPersistedRegistryLocationW
0x180018b55  nop     dword ptr [rax+rax+00h]
0x180018b5a  test    eax, eax
0x180018b5c  jz      short loc_180018B7A
0x180018b5e  mov     rcx, [rbp+38h]; this
0x180018b62  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018b69  mov     r9d, eax; char *
0x180018b6c  mov     edx, 0C0h; void *
0x180018b71  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018b76  mov     edi, eax
0x180018b78  jmp     short loc_180018BCC
0x180018b7a  test    r14, r14
0x180018b7d  jz      loc_180018C08
0x180018b83  xor     edx, edx
0x180018b85  mov     qword ptr [rbp+var_8], 0
0x180018b8d  lea     rcx, [rbp+var_8]
0x180018b91  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018b96  lea     r9, [rbp+var_8]; unsigned __int16 *
0x180018b9a  mov     r8, r14; unsigned __int16 *
0x180018b9d  mov     rcx, rbx; this
0x180018ba0  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180018ba5  mov     edi, eax
0x180018ba7  test    eax, eax
0x180018ba9  jns     short loc_180018BDF
0x180018bab  mov     rcx, [rbp+38h]; this
0x180018baf  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018bb6  mov     r9d, eax; char *
0x180018bb9  mov     edx, 0C9h; void *
0x180018bbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018bc3  lea     rcx, [rbp+var_8]
0x180018bc7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180018bcc  mov     rcx, rbx; hMem
0x180018bcf  call    cs:__imp_LocalFree
0x180018bd6  nop     dword ptr [rax+rax+00h]
0x180018bdb  mov     eax, edi
0x180018bdd  jmp     short loc_180018C2E
0x180018bdf  mov     rax, qword ptr [rbp+var_8]
0x180018be3  lea     rcx, [rbp+var_8]
0x180018be7  mov     [rsi], rax
0x180018bea  mov     qword ptr [rbp+var_8], 0
0x180018bf2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180018bf7  mov     rcx, rbx; hMem
0x180018bfa  call    cs:__imp_LocalFree
0x180018c01  nop     dword ptr [rax+rax+00h]
0x180018c06  jmp     short loc_180018C0B
0x180018c08  mov     [rsi], rbx
0x180018c0b  xor     eax, eax
0x180018c0d  jmp     short loc_180018C2E
0x180018c0f  mov     ebx, 8007000Eh
0x180018c14  mov     edx, 0B9h; void *
0x180018c19  mov     rcx, [rbp+38h]; this
0x180018c1d  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018c24  mov     r9d, ebx; char *
0x180018c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018c2c  mov     eax, ebx
0x180018c2e  add     rsp, 40h
0x180018c32  pop     r15
0x180018c34  pop     r14
0x180018c36  pop     r12
0x180018c38  pop     rdi
0x180018c39  pop     rsi
0x180018c3a  pop     rbx
0x180018c3b  pop     rbp
0x180018c3c  retn
```
