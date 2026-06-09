# asg::SemanticRegistry::RegistrySchema::Validate(void)

- ea: `0x180092580`
- end: `0x180092ef2`
- name: `?Validate@RegistrySchema@SemanticRegistry@asg@@QEAAXXZ`
- size: `2418`
- prototype: `void __fastcall(asg::SemanticRegistry::RegistrySchema *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180088100`

## callees

- `0x180006220`
- `0x180007ce0`
- `0x18000d2a0`
- `0x18007d250`
- `0x1800864e0`
- `0x180089c30`
- `0x180090a20`
- `0x180090fc0`
- `0x180090ff0`
- `0x180091010`
- `0x180092580`
- `0x1801d1370`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`

## string_xrefs

- `0x180092d61`: `Text model must have a Tokenizer configuration`
- `0x180092d30`: `Tokenizer model must have a positive MaxTokenCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall asg::SemanticRegistry::RegistrySchema::Validate(asg::SemanticRegistry::RegistrySchema *this)
{
  asg::SemanticRegistry::RegistrySchema *v1; // rbx
  __int64 v2; // r10
  __int64 v3; // rsi
  __int64 ****v4; // r14
  __int64 *v5; // r9
  __int64 v6; // rbx
  __int64 v7; // r11
  unsigned __int64 v8; // r8
  __int64 ***v9; // rcx
  __int64 v10; // rax
  _OWORD *v11; // r8
  __int64 ***v12; // r8
  __int64 **v13; // rdx
  _QWORD *v14; // rcx
  char v15; // r14
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  _QWORD *v18; // rsi
  unsigned __int64 v19; // rbx
  __int64 v20; // r9
  _QWORD *v21; // r10
  _QWORD *v22; // r11
  __int64 v23; // r9
  _QWORD *v24; // r12
  _QWORD *v25; // r15
  __int64 v26; // r13
  _QWORD *v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rbx
  unsigned __int64 v31; // r10
  __int64 ***v32; // r8
  __int64 v33; // rdx
  _QWORD *v34; // rax
  __int64 ***v35; // r14
  __int64 **j; // rdi
  unsigned __int64 v37; // r8
  __int64 v38; // rax
  __int64 ***v39; // rsi
  __int64 ***v40; // rcx
  __int64 v41; // rax
  unsigned __int8 *v42; // rsi
  unsigned __int8 *k; // rbx
  _QWORD *v44; // rcx
  _QWORD *v45; // rax
  __int64 v46; // rdx
  int v47; // r8d
  _QWORD **v48; // rcx
  _QWORD *v49; // rcx
  _QWORD *v50; // rbx
  __int64 ***v51; // r8
  __int64 **v52; // rdx
  __int64 **v53; // rcx
  __int64 *m; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 ****v63; // [rsp+20h] [rbp-A9h] BYREF
  asg::SemanticRegistry::RegistrySchema *v64; // [rsp+28h] [rbp-A1h]
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-99h] BYREF
  __int64 i; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v67[32]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v68[32]; // [rsp+70h] [rbp-59h] BYREF
  void *Block[2]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v70; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v71; // [rsp+B0h] [rbp-19h]
  __int128 v72; // [rsp+C0h] [rbp-9h]
  _DWORD v73[2]; // [rsp+D0h] [rbp+7h] BYREF
  _OWORD v74[2]; // [rsp+D8h] [rbp+Fh] BYREF
  __int64 v75; // [rsp+F8h] [rbp+2Fh] BYREF

  v1 = this;
  v64 = this;
  v2 = *((_QWORD *)this + 16);
  v3 = *((_QWORD *)this + 17);
  v4 = (__int64 ****)((char *)this + 8);
  v63 = (__int64 ****)((char *)this + 8);
  if ( v2 == v3 )
  {
    v63 = (__int64 ****)((char *)this + 8);
  }
  else
  {
    do
    {
      v74[0] = *(_OWORD *)v2;
      v74[1] = *(_OWORD *)(v2 + 20);
      v5 = (__int64 *)v74;
      v6 = *((_QWORD *)v1 + 6);
      v7 = *((_QWORD *)v64 + 3);
      do
      {
        v8 = *v5;
        _mm_lfence();
        v9 = *(__int64 ****)(v7
                           + 16
                           * (v6
                            & (v8
                             ^ ((v8 << 6)
                              + (v8 >> 2)
                              + 0x100000001B3LL
                              * (*((unsigned __int8 *)v5 + 15)
                               ^ (0x100000001B3LL
                                * (*((unsigned __int8 *)v5 + 14)
                                 ^ (0x100000001B3LL
                                  * (*((unsigned __int8 *)v5 + 13)
                                   ^ (0x100000001B3LL
                                    * (*((unsigned __int8 *)v5 + 12)
                                     ^ (0x100000001B3LL
                                      * (*((unsigned __int8 *)v5 + 11)
                                       ^ (0x100000001B3LL
                                        * (*((unsigned __int8 *)v5 + 10)
                                         ^ (0x100000001B3LL
                                          * (*((unsigned __int8 *)v5 + 9)
                                           ^ (0x100000001B3LL * (*((unsigned __int8 *)v5 + 8) ^ 0xCBF29CE484222325uLL)))))))))))))))
                              + 2654435769u)))
                           + 8);
        if ( v9 == *v4 )
        {
LABEL_82:
          v56 = asg::GuidToString(v67, v5);
          v63 = (__int64 ****)std::string::c_str(v56);
          v57 = asg::format_unsafe<char const *>(
                  v68,
                  "Invalid ID %s in similarity score merge coefficients",
                  (const char *)&v63);
          asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v57);
          throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
        }
        while ( 1 )
        {
          v10 = *v5 - (_QWORD)v9[2];
          if ( (__int64 **)*v5 == v9[2] )
            v10 = v5[1] - (_QWORD)v9[3];
          if ( !v10 )
            break;
          if ( v9 == *(__int64 ****)(v7
                                   + 16
                                   * (v6
                                    & (v8
                                     ^ ((v8 << 6)
                                      + (v8 >> 2)
                                      + 0x100000001B3LL
                                      * (*((unsigned __int8 *)v5 + 15)
                                       ^ (0x100000001B3LL
                                        * (*((unsigned __int8 *)v5 + 14)
                                         ^ (0x100000001B3LL
                                          * (*((unsigned __int8 *)v5 + 13)
                                           ^ (0x100000001B3LL
                                            * (*((unsigned __int8 *)v5 + 12)
                                             ^ (0x100000001B3LL
                                              * (*((unsigned __int8 *)v5 + 11)
                                               ^ (0x100000001B3LL
                                                * (*((unsigned __int8 *)v5 + 10)
                                                 ^ (0x100000001B3LL
                                                  * (*((unsigned __int8 *)v5 + 9)
                                                   ^ (0x100000001B3LL
                                                    * (*((unsigned __int8 *)v5 + 8) ^ 0xCBF29CE484222325uLL)))))))))))))))
                                      + 2654435769u)))) )
            goto LABEL_82;
          v9 = (__int64 ***)v9[1];
        }
        v5 += 2;
      }
      while ( v5 != &v75 );
      v73[0] = *(_DWORD *)(v2 + 16);
      v73[1] = *(_DWORD *)(v2 + 36);
      v11 = v73;
      do
      {
        if ( *(float *)v11 <= 0.0 || *(float *)v11 > 1.0 )
        {
          v55 = asg::format_unsafe<float const &>(
                  v67,
                  "%f is an invalid merge coefficient",
                  COERCE_DOUBLE((unsigned __int64)LODWORD(FLOAT_1_0)));
          asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v55);
          throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
        }
        v11 = (_OWORD *)((char *)v11 + 4);
      }
      while ( v11 != v74 );
      v2 += 40;
      v1 = v64;
    }
    while ( v2 != v3 );
  }
  v12 = *v4;
  v13 = **v4;
  if ( v13 != (__int64 **)*v4 )
  {
    v14 = (_QWORD *)*((_QWORD *)v1 + 9);
    do
    {
      v15 = 0;
      v16 = (_QWORD *)*v14;
      if ( (_QWORD *)*v14 == v14 )
        goto LABEL_83;
      do
      {
        v17 = (_QWORD *)v16[3];
        v18 = (_QWORD *)v16[4];
        if ( v17 != v18 )
        {
          while ( 1 )
          {
            v19 = (unsigned __int64)v13[5];
            _mm_lfence();
            v20 = v17[11];
            v21 = *(_QWORD **)(v20
                             + 16
                             * (v17[14]
                              & (v19
                               ^ ((v19 << 6)
                                + (v19 >> 2)
                                + 0x100000001B3LL
                                * (*((unsigned __int8 *)v13 + 55)
                                 ^ (0x100000001B3LL
                                  * (*((unsigned __int8 *)v13 + 54)
                                   ^ (0x100000001B3LL
                                    * (*((unsigned __int8 *)v13 + 53)
                                     ^ (0x100000001B3LL
                                      * (*((unsigned __int8 *)v13 + 52)
                                       ^ (0x100000001B3LL
                                        * (*((unsigned __int8 *)v13 + 51)
                                         ^ (0x100000001B3LL
                                          * (*((unsigned __int8 *)v13 + 50)
                                           ^ (0x100000001B3LL
                                            * (*((unsigned __int8 *)v13 + 49)
                                             ^ (0x100000001B3LL
                                              * (*((unsigned __int8 *)v13 + 48) ^ 0xCBF29CE484222325uLL)))))))))))))))
                                + 2654435769u)))
                             + 8);
            if ( v21 != (_QWORD *)v17[9] )
              break;
LABEL_28:
            v17 += 24;
            if ( v17 == v18 )
              goto LABEL_31;
          }
          v22 = *(_QWORD **)(v20
                           + 16
                           * (v17[14]
                            & (v19
                             ^ ((v19 << 6)
                              + (v19 >> 2)
                              + 0x100000001B3LL
                              * (*((unsigned __int8 *)v13 + 55)
                               ^ (0x100000001B3LL
                                * (*((unsigned __int8 *)v13 + 54)
                                 ^ (0x100000001B3LL
                                  * (*((unsigned __int8 *)v13 + 53)
                                   ^ (0x100000001B3LL
                                    * (*((unsigned __int8 *)v13 + 52)
                                     ^ (0x100000001B3LL
                                      * (*((unsigned __int8 *)v13 + 51)
                                       ^ (0x100000001B3LL
                                        * (*((unsigned __int8 *)v13 + 50)
                                         ^ (0x100000001B3LL
                                          * (*((unsigned __int8 *)v13 + 49)
                                           ^ (0x100000001B3LL * (*((unsigned __int8 *)v13 + 48) ^ 0xCBF29CE484222325uLL)))))))))))))))
                              + 2654435769u))));
          while ( 1 )
          {
            v23 = (__int64)v13[5] - v21[2];
            if ( !v23 )
              v23 = (__int64)v13[6] - v21[3];
            if ( !v23 )
              break;
            if ( v21 == v22 )
              goto LABEL_28;
            v21 = (_QWORD *)v21[1];
          }
          v15 = 1;
        }
LABEL_31:
        v16 = (_QWORD *)*v16;
      }
      while ( v16 != v14 );
      if ( !v15 )
      {
LABEL_83:
        v58 = asg::GuidToString(v68, v13 + 5);
        v63 = (__int64 ****)std::string::c_str(v58);
        v59 = asg::format_unsafe<char const *>(
                v67,
                "Vector space %s is not referenced by any source",
                (const char *)&v63);
        asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v59);
        throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
      }
      v13 = (__int64 **)*v13;
    }
    while ( v13 != (__int64 **)v12 );
    v1 = v64;
    v4 = (__int64 ****)((char *)v64 + 8);
    v63 = (__int64 ****)((char *)v64 + 8);
  }
  v24 = (_QWORD *)*((_QWORD *)v1 + 9);
  v25 = (_QWORD *)*v24;
  if ( (_QWORD *)*v24 != v24 )
  {
    while ( 1 )
    {
      v26 = v25[3];
      for ( i = v25[4]; v26 != i; v1 = v64 )
      {
        v27 = *(_QWORD **)(v26 + 72);
        v28 = (_QWORD *)*v27;
        if ( (_QWORD *)*v27 != v27 )
        {
          v29 = *((_QWORD *)v1 + 6);
          v30 = *((_QWORD *)v1 + 3);
          do
          {
            v31 = v28[2];
            _mm_lfence();
            v32 = *(__int64 ****)(v30
                                + 16
                                * (v29
                                 & (v31
                                  ^ ((v31 << 6)
                                   + (v31 >> 2)
                                   + 0x100000001B3LL
                                   * (*((unsigned __int8 *)v28 + 31)
                                    ^ (0x100000001B3LL
                                     * (*((unsigned __int8 *)v28 + 30)
                                      ^ (0x100000001B3LL
                                       * (*((unsigned __int8 *)v28 + 29)
                                        ^ (0x100000001B3LL
                                         * (*((unsigned __int8 *)v28 + 28)
                                          ^ (0x100000001B3LL
                                           * (*((unsigned __int8 *)v28 + 27)
                                            ^ (0x100000001B3LL
                                             * (*((unsigned __int8 *)v28 + 26)
                                              ^ (0x100000001B3LL
                                               * (*((unsigned __int8 *)v28 + 25)
                                                ^ (0x100000001B3LL
                                                 * (*((unsigned __int8 *)v28 + 24) ^ 0xCBF29CE484222325uLL)))))))))))))))
                                   + 2654435769u)))
                                + 8);
            if ( v32 == *v4 )
            {
LABEL_84:
              v60 = asg::GuidToString(v68, v28 + 2);
              i = std::string::c_str(v60);
              v61 = asg::format_unsafe<char const *>(
                      v67,
                      "Source refers to vector space %s that doesn't exist",
                      (const char *)&i);
              asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v61);
              throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
            }
            while ( 1 )
            {
              v33 = v28[2] - (_QWORD)v32[2];
              if ( !v33 )
                v33 = v28[3] - (_QWORD)v32[3];
              if ( !v33 )
                break;
              if ( v32 == *(__int64 ****)(v30
                                        + 16
                                        * (v29
                                         & (v31
                                          ^ ((v31 << 6)
                                           + (v31 >> 2)
                                           + 0x100000001B3LL
                                           * (*((unsigned __int8 *)v28 + 31)
                                            ^ (0x100000001B3LL
                                             * (*((unsigned __int8 *)v28 + 30)
                                              ^ (0x100000001B3LL
                                               * (*((unsigned __int8 *)v28 + 29)
                                                ^ (0x100000001B3LL
                                                 * (*((unsigned __int8 *)v28 + 28)
                                                  ^ (0x100000001B3LL
                                                   * (*((unsigned __int8 *)v28 + 27)
                                                    ^ (0x100000001B3LL
                                                     * (*((unsigned __int8 *)v28 + 26)
                                                      ^ (0x100000001B3LL
                                                       * (*((unsigned __int8 *)v28 + 25)
                                                        ^ (0x100000001B3LL
                                                         * (*((unsigned __int8 *)v28 + 24) ^ 0xCBF29CE484222325uLL)))))))))))))))
                                           + 2654435769u)))) )
                goto LABEL_84;
              v32 = (__int64 ***)v32[1];
            }
            v28 = (_QWORD *)*v28;
          }
          while ( v28 != v27 );
          v1 = v64;
        }
        v71 = 0;
        v72 = 0;
        Block[0] = 0;
        Block[1] = 0;
        v70 = 0;
        v34 = operator new(0x18u);
        *v34 = v34;
        v34[1] = v34;
        Block[1] = v34;
        *((_QWORD *)&v70 + 1) = 0;
        v71 = 0;
        *(_QWORD *)&v72 = 7;
        *((_QWORD *)&v72 + 1) = 8;
        LODWORD(Block[0]) = 1065353216;
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(
          (char *)&v70 + 8,
          16,
          v34);
        v35 = *(__int64 ****)(v26 + 72);
        for ( j = *v35; j != (__int64 **)v35; v1 = v64 )
        {
          v37 = (unsigned __int64)j[2];
          _mm_lfence();
          v38 = *((_QWORD *)v1 + 3);
          v39 = *(__int64 ****)(v38
                              + 16
                              * (*((_QWORD *)v1 + 6)
                               & (v37
                                ^ ((v37 >> 2)
                                 + 0x100000001B3LL
                                 * (*((unsigned __int8 *)j + 31)
                                  ^ (0x100000001B3LL
                                   * (*((unsigned __int8 *)j + 30)
                                    ^ (0x100000001B3LL
                                     * (*((unsigned __int8 *)j + 29)
                                      ^ (0x100000001B3LL
                                       * (*((unsigned __int8 *)j + 28)
                                        ^ (0x100000001B3LL
                                         * (*((unsigned __int8 *)j + 27)
                                          ^ (0x100000001B3LL
                                           * (*((unsigned __int8 *)j + 26)
                                            ^ (0x100000001B3LL
                                             * (*((unsigned __int8 *)j + 25)
                                              ^ (0x100000001B3LL * (*((unsigned __int8 *)j + 24) ^ 0xCBF29CE484222325uLL)))))))))))))))
                                 + 2654435769u
                                 + (v37 << 6))))
                              + 8);
          if ( v39 == *v63 )
            goto LABEL_85;
          v40 = *(__int64 ****)(v38
                              + 16
                              * (*((_QWORD *)v1 + 6)
                               & (v37
                                ^ ((v37 >> 2)
                                 + 0x100000001B3LL
                                 * (*((unsigned __int8 *)j + 31)
                                  ^ (0x100000001B3LL
                                   * (*((unsigned __int8 *)j + 30)
                                    ^ (0x100000001B3LL
                                     * (*((unsigned __int8 *)j + 29)
                                      ^ (0x100000001B3LL
                                       * (*((unsigned __int8 *)j + 28)
                                        ^ (0x100000001B3LL
                                         * (*((unsigned __int8 *)j + 27)
                                          ^ (0x100000001B3LL
                                           * (*((unsigned __int8 *)j + 26)
                                            ^ (0x100000001B3LL
                                             * (*((unsigned __int8 *)j + 25)
                                              ^ (0x100000001B3LL * (*((unsigned __int8 *)j + 24) ^ 0xCBF29CE484222325uLL)))))))))))))))
                                 + 2654435769u
                                 + (v37 << 6)))));
          while ( 1 )
          {
            v41 = (char *)j[2] - (char *)v39[2];
            if ( !v41 )
              v41 = (char *)j[3] - (char *)v39[3];
            if ( !v41 )
              break;
            if ( v39 == v40 )
              goto LABEL_85;
            v39 = (__int64 ***)v39[1];
          }
          if ( !v39 )
LABEL_85:
            std::_Xout_of_range("invalid unordered_map<K, T> key");
          v42 = (unsigned __int8 *)v39[18];
          for ( k = *(unsigned __int8 **)v42; k != v42; k = *(unsigned __int8 **)k )
            std::_Hash<std::_Uset_traits<enum asg::SemanticRegistry::ModelClass,std::_Uhash_compare<enum asg::SemanticRegistry::ModelClass,std::hash<enum asg::SemanticRegistry::ModelClass>,std::equal_to<enum asg::SemanticRegistry::ModelClass>>,std::allocator<enum asg::SemanticRegistry::ModelClass>,0>>::emplace<enum asg::SemanticRegistry::ModelClass const &>(
              (__int64)Block,
              (__int64)pExceptionObject,
              k + 100);
          j = (__int64 **)*j;
        }
        v44 = *(_QWORD **)(v26 + 136);
        v45 = (_QWORD *)*v44;
        if ( (_QWORD *)*v44 != v44 )
        {
          while ( 1 )
          {
            _mm_lfence();
            v46 = *(_QWORD *)(*((_QWORD *)&v70 + 1)
                            + 16
                            * (v72
                             & (0x100000001B3LL
                              * (*((unsigned __int8 *)v45 + 19)
                               ^ (0x100000001B3LL
                                * (*((unsigned __int8 *)v45 + 18)
                                 ^ (0x100000001B3LL
                                  * (*((unsigned __int8 *)v45 + 17)
                                   ^ (0x100000001B3LL * (*((unsigned __int8 *)v45 + 16) ^ 0xCBF29CE484222325uLL)))))))))
                            + 8);
            if ( (void *)v46 == Block[1] )
              goto LABEL_86;
            v47 = *((_DWORD *)v45 + 4);
            if ( v47 != *(_DWORD *)(v46 + 16) )
              break;
LABEL_64:
            v45 = (_QWORD *)*v45;
            if ( v45 == v44 )
              goto LABEL_65;
          }
          while ( v46 != *(_QWORD *)(*((_QWORD *)&v70 + 1)
                                   + 16
                                   * (v72
                                    & (0x100000001B3LL
                                     * (*((unsigned __int8 *)v45 + 19)
                                      ^ (0x100000001B3LL
                                       * (*((unsigned __int8 *)v45 + 18)
                                        ^ (0x100000001B3LL
                                         * (*((unsigned __int8 *)v45 + 17)
                                          ^ (0x100000001B3LL * (*((unsigned __int8 *)v45 + 16) ^ 0xCBF29CE484222325uLL)))))))))) )
          {
            v46 = *(_QWORD *)(v46 + 8);
            if ( v47 == *(_DWORD *)(v46 + 16) )
              goto LABEL_64;
          }
LABEL_86:
          v62 = asg::format_unsafe<enum asg::SemanticRegistry::ModelClass const &>(
                  (__int64)v68,
                  (__int64)"Source refers to model class %d that is not supported by any of its vector spaces",
                  (unsigned int *)v45 + 4);
          asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v62);
          throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
        }
LABEL_65:
        std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v70 + 8);
        v48 = (_QWORD **)Block[1];
        **((_QWORD **)Block[1] + 1) = 0;
        v49 = *v48;
        if ( v49 )
        {
          do
          {
            v50 = (_QWORD *)*v49;
            operator delete(v49);
            v49 = v50;
          }
          while ( v50 );
        }
        operator delete(Block[1]);
        v26 += 192;
        v4 = v63;
      }
      v25 = (_QWORD *)*v25;
      if ( v25 == v24 )
        break;
      v4 = v63;
    }
    v4 = (__int64 ****)((char *)v1 + 8);
  }
  v51 = *v4;
  v52 = **v4;
  if ( v52 != (__int64 **)*v4 )
  {
    do
    {
      v53 = (__int64 **)v52[18];
      for ( m = *v53; m != (__int64 *)v53; m = (__int64 *)*m )
      {
        if ( *((_DWORD *)m + 25) == 1 )
        {
          if ( !*((_BYTE *)m + 120) )
          {
            std::string::string(v67, "Text model must have a Tokenizer configuration", v51);
            asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v67);
            throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
          }
          if ( !m[14] )
          {
            std::string::string(v67, "Tokenizer model must have a positive MaxTokenCount", v51);
            asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(pExceptionObject, v67);
            throw (asg::SemanticRegistry::InvalidRegistryException *)pExceptionObject;
          }
        }
      }
      v52 = (__int64 **)*v52;
    }
    while ( v52 != (__int64 **)v51 );
  }
}

```

## disassembly

```asm
0x180092580  mov     [rsp-8+arg_0], rbx
0x180092585  mov     [rsp-8+arg_8], rsi
0x18009258a  mov     [rsp-8+arg_10], rdi
0x18009258f  push    rbp
0x180092590  push    r12
0x180092592  push    r13
0x180092594  push    r14
0x180092596  push    r15
0x180092598  lea     rbp, [rsp-37h]
0x18009259d  sub     rsp, 100h
0x1800925a4  mov     rax, cs:__security_cookie
0x1800925ab  xor     rax, rsp
0x1800925ae  mov     [rbp+57h+var_28], rax
0x1800925b2  mov     rbx, rcx
0x1800925b5  mov     [rsp+120h+var_F8], rcx
0x1800925ba  mov     r10, [rcx+80h]
0x1800925c1  mov     rsi, [rcx+88h]
0x1800925c8  lea     r14, [rcx+8]
0x1800925cc  mov     [rsp+120h+var_100], r14
0x1800925d1  mov     r13, 0CBF29CE484222325h
0x1800925db  mov     r12, 100000001B3h
0x1800925e5  mov     r15d, 9E3779B9h
0x1800925eb  xorps   xmm3, xmm3
0x1800925ee  movss   xmm2, cs:__real@3f800000
0x1800925f6  cmp     r10, rsi
0x1800925f9  jz      loc_180092757
0x1800925ff  nop
0x180092600  movups  xmm0, xmmword ptr [r10]
0x180092604  movups  [rbp+57h+var_48], xmm0
0x180092608  movups  xmm1, xmmword ptr [r10+14h]
0x18009260d  movups  [rbp+57h+var_38], xmm1
0x180092611  lea     r9, [rbp+57h+var_48]
0x180092615  mov     rbx, [rbx+30h]
0x180092619  mov     r11, [rsp+120h+var_F8]
0x18009261e  mov     r11, [r11+18h]
0x180092622  mov     rdi, [r14]
0x180092625  nop     word ptr [rax+rax+00000000h]
0x180092630  mov     r8, [r9]
0x180092633  lfence
0x180092636  movzx   edx, byte ptr [r9+8]
0x18009263b  xor     rdx, r13
0x18009263e  imul    rdx, r12
0x180092642  movzx   eax, byte ptr [r9+9]
0x180092647  xor     rdx, rax
0x18009264a  imul    rdx, r12
0x18009264e  movzx   eax, byte ptr [r9+0Ah]
0x180092653  xor     rdx, rax
0x180092656  imul    rdx, r12
0x18009265a  movzx   eax, byte ptr [r9+0Bh]
0x18009265f  xor     rdx, rax
0x180092662  imul    rdx, r12
0x180092666  movzx   eax, byte ptr [r9+0Ch]
0x18009266b  xor     rdx, rax
0x18009266e  imul    rdx, r12
0x180092672  movzx   eax, byte ptr [r9+0Dh]
0x180092677  xor     rdx, rax
0x18009267a  imul    rdx, r12
0x18009267e  movzx   eax, byte ptr [r9+0Eh]
0x180092683  xor     rdx, rax
0x180092686  imul    rdx, r12
0x18009268a  movzx   eax, byte ptr [r9+0Fh]
0x18009268f  xor     rdx, rax
0x180092692  imul    rdx, r12
0x180092696  mov     rax, r8
0x180092699  shr     rax, 2
0x18009269d  add     rdx, rax
0x1800926a0  mov     rcx, r8
0x1800926a3  shl     rcx, 6
0x1800926a7  add     rdx, r15
0x1800926aa  add     rdx, rcx
0x1800926ad  xor     rdx, r8
0x1800926b0  and     rdx, rbx
0x1800926b3  add     rdx, rdx
0x1800926b6  mov     rcx, [r11+rdx*8+8]
0x1800926bb  cmp     rcx, rdi
0x1800926be  jz      loc_180092DC2
0x1800926c4  mov     rdx, [r11+rdx*8]
0x1800926c8  nop     dword ptr [rax+rax+00000000h]
0x1800926d0  mov     rax, [r9]
0x1800926d3  sub     rax, [rcx+10h]
0x1800926d7  jnz     short loc_1800926E1
0x1800926d9  mov     rax, [r9+8]
0x1800926dd  sub     rax, [rcx+18h]
0x1800926e1  test    rax, rax
0x1800926e4  jz      short loc_1800926F5
0x1800926e6  cmp     rcx, rdx
0x1800926e9  jz      loc_180092DC2
0x1800926ef  mov     rcx, [rcx+8]
0x1800926f3  jmp     short loc_1800926D0
0x1800926f5  add     r9, 10h
0x1800926f9  lea     rax, [rbp+57h+var_28]
0x1800926fd  cmp     r9, rax
0x180092700  jnz     loc_180092630
0x180092706  movss   xmm0, dword ptr [r10+10h]
0x18009270c  movss   [rbp+57h+var_50], xmm0
0x180092711  movss   xmm1, dword ptr [r10+24h]
0x180092717  movss   [rbp+57h+var_4C], xmm1
0x18009271c  lea     r8, [rbp+57h+var_50]
0x180092720  movss   xmm0, dword ptr [r8]
0x180092725  comiss  xmm3, xmm0
0x180092728  jnb     loc_180092D92
0x18009272e  comiss  xmm0, xmm2
0x180092731  ja      loc_180092D92
0x180092737  add     r8, 4
0x18009273b  lea     rax, [rbp+57h+var_48]
0x18009273f  cmp     r8, rax
0x180092742  jnz     short loc_180092720
0x180092744  add     r10, 28h ; '('
0x180092748  mov     rbx, [rsp+120h+var_F8]
0x18009274d  cmp     r10, rsi
0x180092750  jz      short loc_18009275C
0x180092752  jmp     loc_180092600
0x180092757  mov     [rsp+120h+var_100], r14
0x18009275c  mov     r8, [r14]
0x18009275f  mov     rdx, [r8]
0x180092762  cmp     rdx, r8
0x180092765  jz      loc_1800928A8
0x18009276b  mov     rcx, [rbx+48h]
0x18009276f  mov     r15, [rcx]
0x180092772  nop     dword ptr [rax+00h]
0x180092776  nop     word ptr [rax+rax+00000000h]
0x180092780  xor     r14b, r14b
0x180092783  mov     rax, r15
0x180092786  cmp     r15, rcx
0x180092789  jz      loc_180092E11
0x18009278f  nop
0x180092790  mov     rdi, [rax+18h]
0x180092794  mov     rsi, [rax+20h]
0x180092798  cmp     rdi, rsi
0x18009279b  jz      loc_180092879
0x1800927a1  mov     rbx, [rdx+28h]
0x1800927a5  lfence
0x1800927a8  movzx   r11d, byte ptr [rdx+30h]
0x1800927ad  xor     r11, r13
0x1800927b0  imul    r11, r12
0x1800927b4  movzx   r9d, byte ptr [rdx+31h]
0x1800927b9  xor     r11, r9
0x1800927bc  imul    r11, r12
0x1800927c0  movzx   r9d, byte ptr [rdx+32h]
0x1800927c5  xor     r11, r9
0x1800927c8  imul    r11, r12
0x1800927cc  movzx   r9d, byte ptr [rdx+33h]
0x1800927d1  xor     r11, r9
0x1800927d4  imul    r11, r12
0x1800927d8  movzx   r9d, byte ptr [rdx+34h]
0x1800927dd  xor     r11, r9
0x1800927e0  imul    r11, r12
0x1800927e4  movzx   r9d, byte ptr [rdx+35h]
0x1800927e9  xor     r11, r9
0x1800927ec  imul    r11, r12
0x1800927f0  movzx   r9d, byte ptr [rdx+36h]
0x1800927f5  xor     r11, r9
0x1800927f8  imul    r11, r12
0x1800927fc  movzx   r9d, byte ptr [rdx+37h]
0x180092801  xor     r11, r9
0x180092804  imul    r11, r12
0x180092808  mov     r9, rbx
0x18009280b  shr     r9, 2
0x18009280f  add     r11, r9
0x180092812  mov     r10, rbx
0x180092815  shl     r10, 6
0x180092819  mov     r9d, 9E3779B9h
0x18009281f  add     r11, r9
0x180092822  add     r11, r10
0x180092825  xor     r11, rbx
0x180092828  and     r11, [rdi+70h]
0x18009282c  add     r11, r11
0x18009282f  mov     r9, [rdi+58h]
0x180092833  mov     r10, [r9+r11*8+8]
0x180092838  cmp     r10, [rdi+48h]
0x18009283c  jz      short loc_180092864
0x18009283e  mov     r11, [r9+r11*8]
0x180092842  mov     r9, [rdx+28h]
0x180092846  sub     r9, [r10+10h]
0x18009284a  jnz     short loc_180092854
0x18009284c  mov     r9, [rdx+30h]
0x180092850  sub     r9, [r10+18h]
0x180092854  test    r9, r9
0x180092857  jz      short loc_180092876
0x180092859  cmp     r10, r11
0x18009285c  jz      short loc_180092864
0x18009285e  mov     r10, [r10+8]
0x180092862  jmp     short loc_180092842
0x180092864  add     rdi, 0C0h
0x18009286b  cmp     rdi, rsi
0x18009286e  jnz     loc_1800927A1
0x180092874  jmp     short loc_180092879
0x180092876  mov     r14b, 1
0x180092879  mov     rax, [rax]
0x18009287c  cmp     rax, rcx
0x18009287f  jnz     loc_180092790
0x180092885  test    r14b, r14b
0x180092888  jz      loc_180092E11
0x18009288e  mov     rdx, [rdx]
0x180092891  cmp     rdx, r8
0x180092894  jnz     loc_180092780
0x18009289a  mov     rbx, [rsp+120h+var_F8]
0x18009289f  lea     r14, [rbx+8]
0x1800928a3  mov     [rsp+120h+var_100], r14
0x1800928a8  mov     r12, [rbx+48h]
0x1800928ac  mov     r15, [r12]
0x1800928b0  cmp     r15, r12
0x1800928b3  jz      loc_180092CC6
0x1800928b9  mov     rsi, 100000001B3h
0x1800928c3  nop     dword ptr [rax+00h]
0x1800928c7  nop     word ptr [rax+rax+00000000h]
0x1800928d0  mov     r13, [r15+18h]
0x1800928d4  mov     rax, [r15+20h]
0x1800928d8  mov     [rsp+120h+var_D8], rax
0x1800928dd  cmp     r13, rax
0x1800928e0  jz      loc_180092CB0
0x1800928e6  nop     word ptr [rax+rax+00000000h]
0x1800928f0  mov     rcx, [r13+48h]
0x1800928f4  mov     rax, [rcx]
0x1800928f7  cmp     rax, rcx
0x1800928fa  jz      loc_180092A01
0x180092900  mov     rdi, [rbx+30h]
0x180092904  mov     rbx, [rbx+18h]
0x180092908  mov     rsi, [r14]
0x18009290b  nop     dword ptr [rax+rax+00h]
0x180092910  mov     r10, [rax+10h]
0x180092914  lfence
0x180092917  movzx   r9d, byte ptr [rax+18h]
0x18009291c  mov     rdx, 0CBF29CE484222325h
0x180092926  xor     r9, rdx
0x180092929  mov     r8, 100000001B3h
0x180092933  imul    r9, r8
0x180092937  movzx   edx, byte ptr [rax+19h]
0x18009293b  xor     r9, rdx
0x18009293e  imul    r9, r8
0x180092942  movzx   edx, byte ptr [rax+1Ah]
0x180092946  xor     r9, rdx
0x180092949  imul    r9, r8
0x18009294d  movzx   edx, byte ptr [rax+1Bh]
0x180092951  xor     r9, rdx
0x180092954  imul    r9, r8
0x180092958  movzx   edx, byte ptr [rax+1Ch]
0x18009295c  xor     r9, rdx
0x18009295f  imul    r9, r8
0x180092963  movzx   edx, byte ptr [rax+1Dh]
0x180092967  xor     r9, rdx
0x18009296a  imul    r9, r8
0x18009296e  movzx   edx, byte ptr [rax+1Eh]
0x180092972  xor     r9, rdx
0x180092975  imul    r9, r8
0x180092979  movzx   edx, byte ptr [rax+1Fh]
0x18009297d  xor     r9, rdx
0x180092980  imul    r9, r8
0x180092984  mov     rdx, r10
0x180092987  shr     rdx, 2
0x18009298b  add     r9, rdx
0x18009298e  mov     r8, r10
0x180092991  shl     r8, 6
0x180092995  mov     edx, 9E3779B9h
0x18009299a  add     r9, rdx
0x18009299d  add     r9, r8
0x1800929a0  xor     r9, r10
0x1800929a3  and     r9, rdi
0x1800929a6  add     r9, r9
0x1800929a9  mov     r8, [rbx+r9*8+8]
0x1800929ae  cmp     r8, rsi
0x1800929b1  jz      loc_180092E61
0x1800929b7  mov     r9, [rbx+r9*8]
0x1800929bb  nop     dword ptr [rax+rax+00h]
0x1800929c0  mov     rdx, [rax+10h]
0x1800929c4  sub     rdx, [r8+10h]
0x1800929c8  jnz     short loc_1800929D2
0x1800929ca  mov     rdx, [rax+18h]
0x1800929ce  sub     rdx, [r8+18h]
0x1800929d2  test    rdx, rdx
0x1800929d5  jz      short loc_1800929E6
0x1800929d7  cmp     r8, r9
0x1800929da  jz      loc_180092E61
0x1800929e0  mov     r8, [r8+8]
0x1800929e4  jmp     short loc_1800929C0
0x1800929e6  mov     rax, [rax]
0x1800929e9  cmp     rax, rcx
0x1800929ec  jnz     loc_180092910
0x1800929f2  mov     rbx, [rsp+120h+var_F8]
0x1800929f7  mov     rsi, 100000001B3h
0x180092a01  xorps   xmm0, xmm0
0x180092a04  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180092a08  movups  [rbp+57h+var_80], xmm0
0x180092a0c  movups  [rbp+57h+var_70], xmm0
0x180092a10  movups  [rbp+57h+var_60], xmm0
0x180092a14  mov     dword ptr [rbp+57h+Block], 0
0x180092a1b  mov     [rbp+57h+Block+8], 0
0x180092a23  mov     qword ptr [rbp+57h+var_80], 0
0x180092a2b  mov     ecx, 18h; Size
0x180092a30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180092a35  mov     [rax], rax
0x180092a38  mov     [rax+8], rax
0x180092a3c  mov     [rbp+57h+Block+8], rax
0x180092a40  mov     qword ptr [rbp+57h+var_80+8], 0
0x180092a48  xorps   xmm0, xmm0
0x180092a4b  movdqa  [rbp+57h+var_70], xmm0
0x180092a50  mov     qword ptr [rbp+57h+var_60], 7
0x180092a58  mov     qword ptr [rbp+57h+var_60+8], 8
0x180092a60  mov     dword ptr [rbp+57h+Block], 3F800000h
0x180092a67  mov     r8, rax
  ... truncated ...
```
