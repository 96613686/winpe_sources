# asg::SemanticIndex::SemanticIndexStore::ValidateQueryEmbedding(asg::SemanticPipelines::QueryEmbeddings const &)

- ea: `0x180197dd0`
- end: `0x180198080`
- name: `?ValidateQueryEmbedding@SemanticIndexStore@SemanticIndex@asg@@AEBAXAEBUQueryEmbeddings@SemanticPipelines@3@@Z`
- size: `688`
- prototype: `void __fastcall(asg::SemanticIndex::SemanticIndexStore *__hidden this, const struct asg::SemanticPipelines::QueryEmbeddings *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180194520`

## callees

- `0x1800085c0`
- `0x18000ad40`
- `0x1800869f0`
- `0x180194d50`
- `0x180197d50`
- `0x180197dd0`
- `0x1801f97e0`

## string_xrefs

- `0x18019800b`: `Current embedding vector space id is incompatible with the current embedding store`
- `0x180198034`: `Current embedding element type is incompatible with the current embedding store`
- `0x18019805d`: `Previous embedding vector space id is incompatible with the previous embedding store`
- `0x180197fb9`: `Previous embedding element type is incompatible with the previous embedding store`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall asg::SemanticIndex::SemanticIndexStore::ValidateQueryEmbedding(
        asg::SemanticIndex::SemanticIndexStore *this,
        asg::SemanticPipelines **a2)
{
  char v4; // bl
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  char v10; // al
  __int64 v11; // rax
  int v12; // ebx
  asg::SemanticPipelines *v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  char v19; // bl
  int v20; // ebx
  _BYTE pExceptionObject[64]; // [rsp+20h] [rbp-E0h] BYREF
  void (__fastcall **v22)(_QWORD, _QWORD); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[160]; // [rsp+78h] [rbp-88h] BYREF
  char v26; // [rsp+118h] [rbp+18h]

  v4 = 0;
  if ( !*a2 )
  {
    asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
      pExceptionObject,
      "Current embedding is not provided.",
      13);
    throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
  }
  asg::SemanticIndex::ValidateEmbedding(*a2);
  v5 = (_QWORD *)(*(__int64 (__fastcall **)(asg::SemanticPipelines *))(*(_QWORD *)*a2 + 32LL))(*a2);
  v6 = v5;
  v7 = *((_QWORD *)this + 22);
  v8 = *(_QWORD *)(v7 + 200);
  v9 = *v5 - v8;
  if ( *v5 == v8 )
    v9 = v5[1] - _mm_srli_si128(*(__m128i *)(v7 + 200), 8).m128i_u64[0];
  if ( v9 )
  {
    v26 = 0;
    v10 = 0;
    if ( *(_BYTE *)(v7 + 400) )
    {
      asg::SemanticRegistry::VectorSpaceInfo::VectorSpaceInfo(
        (asg::SemanticRegistry::VectorSpaceInfo *)&v22,
        (const struct asg::SemanticRegistry::VectorSpaceInfo *)(v7 + 216));
      v26 = 1;
      v10 = 1;
    }
    if ( !v10 )
      goto LABEL_12;
    v11 = v23 - *v6;
    if ( v23 == *v6 )
      v11 = v24 - v6[1];
    if ( v11
      && !(unsigned __int8)std::_Hash<std::_Uset_traits<asg::Guid,std::_Uhash_compare<asg::Guid,std::hash<asg::Guid>,std::equal_to<asg::Guid>>,std::allocator<asg::Guid>,0>>::contains(
                             v25,
                             v6) )
    {
LABEL_12:
      v4 = 1;
    }
    if ( v26 )
      (*v22)(&v22, 0);
    if ( v4 )
    {
      asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
        pExceptionObject,
        "Current embedding vector space id is incompatible with the current embedding store",
        6);
      throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
    }
    v12 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 22) + 184LL) + 88LL);
    if ( (*(unsigned int (__fastcall **)(asg::SemanticPipelines *))(*(_QWORD *)*a2 + 16LL))(*a2) != v12 )
    {
      asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
        pExceptionObject,
        "Current embedding element type is incompatible with the current embedding store",
        8);
      throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
    }
  }
  v13 = a2[2];
  if ( v13 )
  {
    asg::SemanticIndex::ValidateEmbedding(v13);
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(asg::SemanticPipelines *))(*(_QWORD *)a2[2] + 32LL))(a2[2]);
    v15 = v14;
    v16 = *((_QWORD *)this + 24);
    v17 = *(_QWORD *)(v16 + 200);
    v18 = *v14 - v17;
    if ( *v14 == v17 )
      v18 = v14[1] - _mm_srli_si128(*(__m128i *)(v16 + 200), 8).m128i_u64[0];
    if ( v18 )
    {
      v26 = 0;
      if ( *(_BYTE *)(v16 + 400) )
      {
        asg::SemanticRegistry::VectorSpaceInfo::VectorSpaceInfo(
          (asg::SemanticRegistry::VectorSpaceInfo *)&v22,
          (const struct asg::SemanticRegistry::VectorSpaceInfo *)(v16 + 216));
        v26 = 1;
      }
      v19 = asg::SemanticIndex::MatchesIdOrAlias(&v22, v15);
      if ( v26 )
        (*v22)(&v22, 0);
      if ( !v19 )
      {
        asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
          pExceptionObject,
          "Previous embedding vector space id is incompatible with the previous embedding store",
          6);
        throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
      }
    }
    v20 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 24) + 184LL) + 88LL);
    if ( (*(unsigned int (__fastcall **)(asg::SemanticPipelines *))(*(_QWORD *)a2[2] + 16LL))(a2[2]) != v20 )
    {
      asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
        pExceptionObject,
        "Previous embedding element type is incompatible with the previous embedding store",
        8);
      throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180197dd0  mov     [rsp-8+arg_0], rbx
0x180197dd5  mov     [rsp-8+arg_10], rsi
0x180197dda  push    rbp
0x180197ddb  push    rdi
0x180197ddc  push    r14
0x180197dde  lea     rbp, [rsp-20h]
0x180197de3  sub     rsp, 120h
0x180197dea  mov     rdi, rdx
0x180197ded  mov     r14, rcx
0x180197df0  xor     ebx, ebx
0x180197df2  mov     rcx, [rdx]; this
0x180197df5  test    rcx, rcx
0x180197df8  jz      loc_180197FDC
0x180197dfe  call    asg__SemanticIndex__ValidateEmbedding
0x180197e03  mov     rcx, [rdi]
0x180197e06  mov     rax, [rcx]
0x180197e09  call    qword ptr [rax+20h]
0x180197e0c  mov     rsi, rax
0x180197e0f  mov     r8, [r14+0B0h]
0x180197e16  movups  xmm0, xmmword ptr [r8+0C8h]
0x180197e1e  mov     rdx, [rax]
0x180197e21  movq    rcx, xmm0
0x180197e26  sub     rdx, rcx
0x180197e29  jnz     short loc_180197E3C
0x180197e2b  mov     rdx, [rax+8]
0x180197e2f  psrldq  xmm0, 8
0x180197e34  movq    rax, xmm0
0x180197e39  sub     rdx, rax
0x180197e3c  test    rdx, rdx
0x180197e3f  jz      loc_180197ED9
0x180197e45  lea     rdx, [r8+0D8h]; struct asg::SemanticRegistry::VectorSpaceInfo *
0x180197e4c  mov     [rbp+30h+var_18], bl
0x180197e4f  xor     al, al
0x180197e51  cmp     [rdx+0B8h], al
0x180197e57  jz      short loc_180197E69
0x180197e59  lea     rcx, [rsp+130h+var_D0]; this
0x180197e5e  call    ??0VectorSpaceInfo@SemanticRegistry@asg@@QEAA@AEBV012@@Z; asg::SemanticRegistry::VectorSpaceInfo::VectorSpaceInfo(asg::SemanticRegistry::VectorSpaceInfo const &)
0x180197e63  mov     [rbp+30h+var_18], 1
0x180197e67  mov     al, 1
0x180197e69  test    al, al
0x180197e6b  jz      short loc_180197E96
0x180197e6d  mov     rax, [rsp+130h+var_C8]
0x180197e72  sub     rax, [rsi]
0x180197e75  jnz     short loc_180197E80
0x180197e77  mov     rax, [rsp+130h+var_C0]
0x180197e7c  sub     rax, [rsi+8]
0x180197e80  test    rax, rax
0x180197e83  jz      short loc_180197E9B
0x180197e85  mov     rdx, rsi
0x180197e88  lea     rcx, [rsp+130h+var_B8]
0x180197e8d  call    ?contains@?$_Hash@V?$_Uset_traits@UGuid@asg@@V?$_Uhash_compare@UGuid@asg@@U?$hash@UGuid@asg@@@std@@U?$equal_to@UGuid@asg@@@4@@std@@V?$allocator@UGuid@asg@@@4@$0A@@std@@@std@@QEBA_NAEBUGuid@asg@@@Z; std::_Hash<std::_Uset_traits<asg::Guid,std::_Uhash_compare<asg::Guid,std::hash<asg::Guid>,std::equal_to<asg::Guid>>,std::allocator<asg::Guid>,0>>::contains(asg::Guid const &)
0x180197e92  test    al, al
0x180197e94  jnz     short loc_180197E9B
0x180197e96  mov     ebx, 1
0x180197e9b  cmp     [rbp+30h+var_18], 0
0x180197e9f  jz      short loc_180197EAF
0x180197ea1  mov     rax, [rsp+130h+var_D0]
0x180197ea6  xor     edx, edx
0x180197ea8  lea     rcx, [rsp+130h+var_D0]
0x180197ead  call    qword ptr [rax]
0x180197eaf  test    bl, bl
0x180197eb1  jnz     loc_180198005
0x180197eb7  mov     rcx, [rdi]
0x180197eba  mov     rax, [r14+0B0h]
0x180197ec1  mov     rdx, [rax+0B8h]
0x180197ec8  mov     ebx, [rdx+58h]
0x180197ecb  mov     rax, [rcx]
0x180197ece  call    qword ptr [rax+10h]
0x180197ed1  cmp     eax, ebx
0x180197ed3  jnz     loc_18019802E
0x180197ed9  mov     rcx, [rdi+10h]; this
0x180197edd  test    rcx, rcx
0x180197ee0  jz      loc_180197F9B
0x180197ee6  call    asg__SemanticIndex__ValidateEmbedding
0x180197eeb  mov     rcx, [rdi+10h]
0x180197eef  mov     rax, [rcx]
0x180197ef2  call    qword ptr [rax+20h]
0x180197ef5  mov     rbx, rax
0x180197ef8  mov     r8, [r14+0C0h]
0x180197eff  movups  xmm0, xmmword ptr [r8+0C8h]
0x180197f07  mov     rdx, [rax]
0x180197f0a  movq    rcx, xmm0
0x180197f0f  sub     rdx, rcx
0x180197f12  jnz     short loc_180197F25
0x180197f14  mov     rdx, [rax+8]
0x180197f18  psrldq  xmm0, 8
0x180197f1d  movq    rax, xmm0
0x180197f22  sub     rdx, rax
0x180197f25  test    rdx, rdx
0x180197f28  jz      short loc_180197F7C
0x180197f2a  lea     rdx, [r8+0D8h]; struct asg::SemanticRegistry::VectorSpaceInfo *
0x180197f31  mov     [rbp+30h+var_18], 0
0x180197f35  cmp     byte ptr [rdx+0B8h], 0
0x180197f3c  jz      short loc_180197F4C
0x180197f3e  lea     rcx, [rsp+130h+var_D0]; this
0x180197f43  call    ??0VectorSpaceInfo@SemanticRegistry@asg@@QEAA@AEBV012@@Z; asg::SemanticRegistry::VectorSpaceInfo::VectorSpaceInfo(asg::SemanticRegistry::VectorSpaceInfo const &)
0x180197f48  mov     [rbp+30h+var_18], 1
0x180197f4c  mov     rdx, rbx
0x180197f4f  lea     rcx, [rsp+130h+var_D0]
0x180197f54  call    asg__SemanticIndex__MatchesIdOrAlias
0x180197f59  movzx   ebx, al
0x180197f5c  cmp     [rbp+30h+var_18], 0
0x180197f60  jz      short loc_180197F74
0x180197f62  mov     rcx, [rsp+130h+var_D0]
0x180197f67  mov     r8, [rcx]
0x180197f6a  xor     edx, edx
0x180197f6c  lea     rcx, [rsp+130h+var_D0]
0x180197f71  call    r8
0x180197f74  test    bl, bl
0x180197f76  jz      loc_180198057
0x180197f7c  mov     rcx, [rdi+10h]
0x180197f80  mov     rax, [r14+0C0h]
0x180197f87  mov     rdx, [rax+0B8h]
0x180197f8e  mov     ebx, [rdx+58h]
0x180197f91  mov     rax, [rcx]
0x180197f94  call    qword ptr [rax+10h]
0x180197f97  cmp     eax, ebx
0x180197f99  jnz     short loc_180197FB3
0x180197f9b  lea     r11, [rsp+130h+var_10]
0x180197fa3  mov     rbx, [r11+20h]
0x180197fa7  mov     rsi, [r11+30h]
0x180197fab  mov     rsp, r11
0x180197fae  pop     r14
0x180197fb0  pop     rdi
0x180197fb1  pop     rbp
0x180197fb2  retn
0x180197fb3  mov     r8d, 8
0x180197fb9  lea     rdx, aPreviousEmbedd_0; "Previous embedding element type is inco"...
0x180197fc0  lea     rcx, [rsp+130h+pExceptionObject]
0x180197fc5  call    ??0SemanticIndexException@SemanticIndex@asg@@QEAA@PEBDW4SemanticIndexErrorCode@12@@Z; asg::SemanticIndex::SemanticIndexException::SemanticIndexException(char const *,asg::SemanticIndex::SemanticIndexErrorCode)
0x180197fca  lea     rdx, _TI4?AVSemanticIndexException@SemanticIndex@asg@@; pThrowInfo
0x180197fd1  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180197fd6  call    _CxxThrowException
0x180197fdc  mov     r8d, 0Dh
0x180197fe2  lea     rdx, aCurrentEmbeddi; "Current embedding is not provided."
0x180197fe9  lea     rcx, [rsp+130h+pExceptionObject]
0x180197fee  call    ??0SemanticIndexException@SemanticIndex@asg@@QEAA@PEBDW4SemanticIndexErrorCode@12@@Z; asg::SemanticIndex::SemanticIndexException::SemanticIndexException(char const *,asg::SemanticIndex::SemanticIndexErrorCode)
0x180197ff3  lea     rdx, _TI4?AVSemanticIndexException@SemanticIndex@asg@@; pThrowInfo
0x180197ffa  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180197fff  call    _CxxThrowException
0x180198005  mov     r8d, 6
0x18019800b  lea     rdx, aCurrentEmbeddi_1; "Current embedding vector space id is in"...
0x180198012  lea     rcx, [rsp+130h+pExceptionObject]
0x180198017  call    ??0SemanticIndexException@SemanticIndex@asg@@QEAA@PEBDW4SemanticIndexErrorCode@12@@Z; asg::SemanticIndex::SemanticIndexException::SemanticIndexException(char const *,asg::SemanticIndex::SemanticIndexErrorCode)
0x18019801c  lea     rdx, _TI4?AVSemanticIndexException@SemanticIndex@asg@@; pThrowInfo
0x180198023  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180198028  call    _CxxThrowException
0x18019802e  mov     r8d, 8
0x180198034  lea     rdx, aCurrentEmbeddi_0; "Current embedding element type is incom"...
0x18019803b  lea     rcx, [rsp+130h+pExceptionObject]
0x180198040  call    ??0SemanticIndexException@SemanticIndex@asg@@QEAA@PEBDW4SemanticIndexErrorCode@12@@Z; asg::SemanticIndex::SemanticIndexException::SemanticIndexException(char const *,asg::SemanticIndex::SemanticIndexErrorCode)
0x180198045  lea     rdx, _TI4?AVSemanticIndexException@SemanticIndex@asg@@; pThrowInfo
0x18019804c  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180198051  call    _CxxThrowException
0x180198057  mov     r8d, 6
0x18019805d  lea     rdx, aPreviousEmbedd; "Previous embedding vector space id is i"...
0x180198064  lea     rcx, [rsp+130h+pExceptionObject]
0x180198069  call    ??0SemanticIndexException@SemanticIndex@asg@@QEAA@PEBDW4SemanticIndexErrorCode@12@@Z; asg::SemanticIndex::SemanticIndexException::SemanticIndexException(char const *,asg::SemanticIndex::SemanticIndexErrorCode)
0x18019806e  lea     rdx, _TI4?AVSemanticIndexException@SemanticIndex@asg@@; pThrowInfo
0x180198075  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18019807a  call    _CxxThrowException
```
