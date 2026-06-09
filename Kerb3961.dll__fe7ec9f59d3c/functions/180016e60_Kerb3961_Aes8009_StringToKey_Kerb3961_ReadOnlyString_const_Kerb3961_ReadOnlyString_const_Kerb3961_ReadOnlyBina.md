# Kerb3961::Aes8009::StringToKey(Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180016e60`
- end: `0x180017238`
- name: `?StringToKey@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyString@2@0AEBUReadOnlyBinary@2@@Z`
- size: `984`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000901c`
- `0x18000ec30`
- `0x180012ab8`
- `0x180016e60`
- `0x180017f44`
- `0x180018180`

## import_xrefs

- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180017154`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180017154`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::StringToKey(__int64 a1, __int64 a2, __int64 a3, unsigned __int64 *a4, __int64 a5)
{
  char *v7; // rcx
  unsigned __int32 v8; // r12d
  unsigned __int64 v9; // rcx
  const char *v10; // rdx
  unsigned __int64 v11; // r14
  const char *v12; // rdx
  const char *v13; // rdx
  char *v14; // rcx
  _WORD *v15; // rax
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // r13
  const char *v18; // rdx
  int v19; // r8d
  int v20; // r14d
  PUCHAR v21; // rcx
  ULONG v22; // r15d
  int v23; // r8d
  int v24; // r14d
  int v25; // r8d
  int v26; // r14d
  PUCHAR v27; // rcx
  PUCHAR v28; // r14
  ULONGLONG v29; // rcx
  PUCHAR v30; // r12
  PUCHAR v31; // r15
  NTSTATUS v32; // eax
  int v33; // r8d
  NTSTATUS v34; // r13d
  ULONG cbSalt; // [rsp+28h] [rbp-81h]
  ULONGLONG cIterations; // [rsp+30h] [rbp-79h]
  ULONG cbPassword[2]; // [rsp+58h] [rbp-51h] BYREF
  PUCHAR pbPassword; // [rsp+60h] [rbp-49h]
  char *v40; // [rsp+68h] [rbp-41h]
  ULONG v41[2]; // [rsp+70h] [rbp-39h] BYREF
  PUCHAR pbSalt; // [rsp+78h] [rbp-31h]
  char *v43; // [rsp+80h] [rbp-29h]
  ULONG cbDerivedKey; // [rsp+88h] [rbp-21h] BYREF
  PUCHAR pbDerivedKey; // [rsp+90h] [rbp-19h]
  char *v46; // [rsp+98h] [rbp-11h]
  void *v47; // [rsp+A0h] [rbp-9h] BYREF
  char *v48; // [rsp+A8h] [rbp-1h]
  _QWORD v49[9]; // [rsp+B0h] [rbp+7h] BYREF

  if ( *(_QWORD *)a5 != 4 )
  {
    v7 = "stringToKeyParameters.length == sizeof(uint32_t)";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  v8 = _byteswap_ulong(**(_DWORD **)(a5 + 8));
  if ( v8 > *(_DWORD *)(a1 + 136) )
  {
    v7 = "iterations <= m_maxIterationCount";
    goto LABEL_3;
  }
  if ( v8 < *(_DWORD *)(a1 + 140) )
  {
    v7 = "iterations >= m_minIterationCount";
    goto LABEL_3;
  }
  v9 = *a4;
  v47 = v49;
  LOWORD(v49[0]) = 0;
  v48 = (char *)v49;
  v10 = (const char *)(*(_QWORD *)(a1 + 112) + v9 + 1);
  if ( (unsigned __int64)v10 <= v9 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"saltpLength > salt.length", v10);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    goto LABEL_47;
  }
  v11 = 7;
  if ( (unsigned __int64)v10 > 7
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(&v47) )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"saltp.reserve(salt.length + m_encryptionTypeName.length() + 1)",
      v12);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    goto LABEL_47;
  }
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          &v47,
                          *(_QWORD *)(a1 + 104),
                          *(_QWORD *)(a1 + 112)) )
  {
    v15 = v47;
    v16 = (v48 - (_BYTE *)v47) >> 1;
    if ( v47 != v49 )
      v11 = (__int64)(v49[0] - (_QWORD)v47) >> 1;
    v17 = v16 + 1;
    if ( v16 < v16 + 1 )
    {
      if ( v17 <= v11 )
        goto LABEL_21;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(&v47) )
      {
        v15 = v47;
LABEL_21:
        v15[v16] = 0;
        v48 = (char *)v47 + 2 * v17;
        *(_WORD *)v48 = 0;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 &v47,
                                 a4[1],
                                 *a4) )
        {
          v14 = "saltp.append(salt.buffer, salt.length)";
          goto LABEL_46;
        }
        pbPassword = (PUCHAR)v47;
        *(_QWORD *)cbPassword = (v48 - (_BYTE *)v47) >> 1;
        Kerb3961::ConvertToUTF8(v41, cbPassword, 0);
        v20 = (int)v43;
        if ( (int)v43 >= 0 )
        {
          v22 = v41[0];
          if ( *(_QWORD *)v41 <= 0xFFFFFFFF )
          {
            Kerb3961::ConvertToUTF8(cbPassword, a3, 0);
            v24 = (int)v40;
            if ( (int)v40 >= 0 )
            {
              Kerb3961::MakeBuffer(&cbDerivedKey);
              v26 = (int)v46;
              if ( (int)v46 >= 0 )
              {
                v28 = pbSalt;
                v29 = v8;
                v30 = pbDerivedKey;
                cbSalt = v22;
                v31 = pbPassword;
                v32 = BCryptDeriveKeyPBKDF2(
                        *(BCRYPT_ALG_HANDLE *)(a1 + 152),
                        pbPassword,
                        cbPassword[0],
                        pbSalt,
                        cbSalt,
                        v29,
                        pbDerivedKey,
                        cbDerivedKey,
                        0);
                v34 = v32;
                if ( v32 >= 0 )
                {
                  *(_QWORD *)v41 = 8;
                  pbSalt = (PUCHAR)"kerberos";
                  cIterations = *(_QWORD *)(a1 + 64);
                  *(_QWORD *)cbPassword = 0;
                  pbPassword = 0;
                  Kerb3961::Aes8009::DeriveKey(
                    a1,
                    a2,
                    (unsigned int)&cbDerivedKey,
                    (unsigned int)v41,
                    (__int64)cbPassword,
                    cIterations);
                }
                else
                {
                  Kerb3961::Logging::Verify::StatusFailed(
                    (Kerb3961::Logging::Verify *)"BCryptDeriveKeyPBKDF2(m_checksumHandle, passwordUTF8.buffer, static_cas"
                                                 "t<uint32_t>(passwordUTF8.length), saltUTF8.buffer, static_cast<uint32_t"
                                                 ">(saltUTF8.length), iterations, tkey.buffer, static_cast<uint32_t>(tkey.length), 0)",
                    (const char *)(unsigned int)v32,
                    v33);
                  *(_QWORD *)a2 = 0;
                  *(_QWORD *)(a2 + 8) = 0;
                  *(_DWORD *)(a2 + 16) = v34;
                }
                if ( v30 )
                  operator delete(v30, 0);
                if ( v31 )
                  operator delete(v31, 0);
                if ( !v28 )
                  goto LABEL_47;
                v21 = v28;
LABEL_26:
                operator delete(v21, 0);
                goto LABEL_47;
              }
              Kerb3961::Logging::Verify::StatusFailed(
                (Kerb3961::Logging::Verify *)"tkey",
                (const char *)(unsigned int)v46,
                v25);
              v27 = pbDerivedKey;
              *(_QWORD *)a2 = 0;
              *(_QWORD *)(a2 + 8) = 0;
              *(_DWORD *)(a2 + 16) = v26;
              if ( v27 )
                operator delete(v27, 0);
            }
            else
            {
              Kerb3961::Logging::Verify::StatusFailed(
                (Kerb3961::Logging::Verify *)"passwordUTF8",
                (const char *)(unsigned int)v40,
                v23);
              *(_QWORD *)a2 = 0;
              *(_QWORD *)(a2 + 8) = 0;
              *(_DWORD *)(a2 + 16) = v24;
            }
            if ( pbPassword )
              operator delete(pbPassword, 0);
          }
          else
          {
            Kerb3961::Logging::Verify::ConditionFailed(
              (Kerb3961::Logging::Verify *)"static_cast<size_t>(saltUTF8.length) <= static_cast<size_t>(utl::numeric_limi"
                                           "ts<uint32_t>::max())",
              v18);
            *(_QWORD *)a2 = 0;
            *(_QWORD *)(a2 + 8) = 0;
            *(_DWORD *)(a2 + 16) = -1073741675;
          }
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"saltUTF8",
            (const char *)(unsigned int)v43,
            v19);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v20;
        }
        v21 = pbSalt;
        if ( !pbSalt )
          goto LABEL_47;
        goto LABEL_26;
      }
    }
    v14 = "saltp.append(1, L'\\x00')";
    goto LABEL_46;
  }
  v14 = "saltp.append(m_encryptionTypeName)";
LABEL_46:
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v14, v13);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741789;
LABEL_47:
  if ( v47 != v49 )
    operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
  return a2;
}

```

## disassembly

```asm
0x180016e60  mov     rax, rsp
0x180016e63  mov     [rax+8], rbx
0x180016e67  mov     [rax+20h], r9
0x180016e6b  mov     [rax+18h], r8
0x180016e6f  push    rbp
0x180016e70  push    rsi
0x180016e71  push    rdi
0x180016e72  push    r12
0x180016e74  push    r13
0x180016e76  push    r14
0x180016e78  push    r15
0x180016e7a  lea     rbp, [rax-57h]
0x180016e7e  sub     rsp, 0C0h
0x180016e85  mov     rax, [rbp+4Fh+arg_20]
0x180016e89  mov     rdi, rdx
0x180016e8c  mov     rsi, rcx
0x180016e8f  cmp     qword ptr [rax], 4
0x180016e93  jz      short loc_180016EB6
0x180016e95  lea     rcx, aStringtokeypar; "stringToKeyParameters.length == sizeof("...
0x180016e9c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180016ea1  xor     ebx, ebx
0x180016ea3  mov     [rdi], rbx
0x180016ea6  mov     [rdi+8], rbx
0x180016eaa  mov     dword ptr [rdi+10h], 0C000000Dh
0x180016eb1  jmp     loc_18001721A
0x180016eb6  mov     rax, [rax+8]
0x180016eba  mov     r12d, [rax]
0x180016ebd  bswap   r12d
0x180016ec0  cmp     r12d, [rcx+88h]
0x180016ec7  jbe     short loc_180016ED2
0x180016ec9  lea     rcx, aIterationsMMax; "iterations <= m_maxIterationCount"
0x180016ed0  jmp     short loc_180016E9C
0x180016ed2  cmp     r12d, [rcx+8Ch]
0x180016ed9  jnb     short loc_180016EE4
0x180016edb  lea     rcx, aIterationsMMin; "iterations >= m_minIterationCount"
0x180016ee2  jmp     short loc_180016E9C
0x180016ee4  mov     rcx, [r9]
0x180016ee7  lea     rax, [rbp+4Fh+var_48]
0x180016eeb  xor     ebx, ebx
0x180016eed  mov     [rbp+4Fh+var_58], rax
0x180016ef1  lea     rax, [rbp+4Fh+var_48]
0x180016ef5  mov     word ptr [rbp+4Fh+var_48], bx
0x180016ef9  mov     [rbp+4Fh+var_50], rax
0x180016efd  lea     rdx, [rcx+1]
0x180016f01  add     rdx, [rsi+70h]; char *
0x180016f05  cmp     rdx, rcx
0x180016f08  ja      short loc_180016F29
0x180016f0a  lea     rcx, aSaltplengthSal; "saltpLength > salt.length"
0x180016f11  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180016f16  mov     [rdi], rbx
0x180016f19  mov     [rdi+8], rbx
0x180016f1d  mov     dword ptr [rdi+10h], 0C0000095h
0x180016f24  jmp     loc_180017201
0x180016f29  mov     r14d, 7
0x180016f2f  cmp     rdx, r14
0x180016f32  jbe     short loc_180016F60
0x180016f34  lea     rcx, [rbp+4Fh+var_58]
0x180016f38  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x180016f3d  test    al, al
0x180016f3f  jnz     short loc_180016F60
0x180016f41  lea     rcx, aSaltpReserveSa; "saltp.reserve(salt.length + m_encryptio"...
0x180016f48  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180016f4d  mov     [rdi], rbx
0x180016f50  mov     [rdi+8], rbx
0x180016f54  mov     dword ptr [rdi+10h], 0C0000017h
0x180016f5b  jmp     loc_180017201
0x180016f60  mov     r8, [rsi+70h]
0x180016f64  lea     rcx, [rbp+4Fh+var_58]
0x180016f68  mov     rdx, [rsi+68h]
0x180016f6c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180016f71  test    al, al
0x180016f73  jnz     short loc_180016F81
0x180016f75  lea     rcx, aSaltpAppendMEn; "saltp.append(m_encryptionTypeName)"
0x180016f7c  jmp     loc_1800171EE
0x180016f81  mov     rax, [rbp+4Fh+var_58]
0x180016f85  lea     rcx, [rbp+4Fh+var_48]
0x180016f89  mov     r15, [rbp+4Fh+var_50]
0x180016f8d  sub     r15, rax
0x180016f90  sar     r15, 1
0x180016f93  cmp     rax, rcx
0x180016f96  jz      short loc_180016FA2
0x180016f98  mov     r14, [rbp+4Fh+var_48]
0x180016f9c  sub     r14, rax
0x180016f9f  sar     r14, 1
0x180016fa2  lea     r13, [r15+1]
0x180016fa6  cmp     r15, r13
0x180016fa9  ja      loc_1800171E7
0x180016faf  cmp     r13, r14
0x180016fb2  jbe     short loc_180016FCC
0x180016fb4  mov     rdx, r13
0x180016fb7  lea     rcx, [rbp+4Fh+var_58]
0x180016fbb  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x180016fc0  test    al, al
0x180016fc2  jz      loc_1800171E7
0x180016fc8  mov     rax, [rbp+4Fh+var_58]
0x180016fcc  mov     rdx, [rbp+4Fh+arg_18]
0x180016fd0  mov     [rax+r15*2], bx
0x180016fd5  mov     rax, [rbp+4Fh+var_58]
0x180016fd9  lea     rcx, [rax+r13*2]
0x180016fdd  mov     [rbp+4Fh+var_50], rcx
0x180016fe1  mov     [rcx], bx
0x180016fe4  lea     rcx, [rbp+4Fh+var_58]
0x180016fe8  mov     r8, [rdx]
0x180016feb  mov     rdx, [rdx+8]
0x180016fef  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180016ff4  test    al, al
0x180016ff6  jnz     short loc_180017004
0x180016ff8  lea     rcx, aSaltpAppendSal; "saltp.append(salt.buffer, salt.length)"
0x180016fff  jmp     loc_1800171EE
0x180017004  mov     rax, [rbp+4Fh+var_58]
0x180017008  lea     rdx, [rbp+4Fh+cbPassword]
0x18001700c  mov     rcx, [rbp+4Fh+var_50]
0x180017010  xor     r8d, r8d
0x180017013  sub     rcx, rax
0x180017016  mov     [rbp+4Fh+pbPassword], rax
0x18001701a  sar     rcx, 1
0x18001701d  mov     qword ptr [rbp+4Fh+cbPassword], rcx
0x180017021  lea     rcx, [rbp+4Fh+var_88]
0x180017025  call    ?ConvertToUTF8@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyString@1@_N@Z; Kerb3961::ConvertToUTF8(Kerb3961::ReadOnlyString const &,bool)
0x18001702a  mov     r14d, dword ptr [rbp+4Fh+var_78]
0x18001702e  test    r14d, r14d
0x180017031  jns     short loc_180017066
0x180017033  mov     edx, r14d; char *
0x180017036  lea     rcx, aSaltutf8; "saltUTF8"
0x18001703d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180017042  mov     [rdi], rbx
0x180017045  mov     [rdi+8], rbx
0x180017049  mov     [rdi+10h], r14d
0x18001704d  mov     rcx, [rbp+4Fh+pbSalt]; void *
0x180017051  test    rcx, rcx
0x180017054  jz      loc_180017201
0x18001705a  xor     edx, edx; struct std::nothrow_t *
0x18001705c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017061  jmp     loc_180017201
0x180017066  mov     r15, qword ptr [rbp+4Fh+var_88]
0x18001706a  mov     eax, 0FFFFFFFFh
0x18001706f  cmp     r15, rax
0x180017072  jbe     short loc_180017090
0x180017074  lea     rcx, aStaticCastSize_1; "static_cast<size_t>(saltUTF8.length) <="...
0x18001707b  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180017080  mov     [rdi], rbx
0x180017083  mov     [rdi+8], rbx
0x180017087  mov     dword ptr [rdi+10h], 0C0000095h
0x18001708e  jmp     short loc_18001704D
0x180017090  mov     rdx, [rbp+4Fh+arg_10]
0x180017094  lea     rcx, [rbp+4Fh+cbPassword]
0x180017098  xor     r8d, r8d
0x18001709b  call    ?ConvertToUTF8@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyString@1@_N@Z; Kerb3961::ConvertToUTF8(Kerb3961::ReadOnlyString const &,bool)
0x1800170a0  mov     r14d, dword ptr [rbp+4Fh+var_90]
0x1800170a4  test    r14d, r14d
0x1800170a7  jns     short loc_1800170D8
0x1800170a9  mov     edx, r14d; char *
0x1800170ac  lea     rcx, aPasswordutf8; "passwordUTF8"
0x1800170b3  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800170b8  mov     [rdi], rbx
0x1800170bb  mov     [rdi+8], rbx
0x1800170bf  mov     [rdi+10h], r14d
0x1800170c3  mov     rcx, [rbp+4Fh+pbPassword]; void *
0x1800170c7  test    rcx, rcx
0x1800170ca  jz      short loc_18001704D
0x1800170cc  xor     edx, edx; struct std::nothrow_t *
0x1800170ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800170d3  jmp     loc_18001704D
0x1800170d8  mov     rdx, [rsi+40h]
0x1800170dc  lea     rcx, [rbp+4Fh+var_70]
0x1800170e0  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x1800170e5  mov     r14d, dword ptr [rbp+4Fh+var_60]
0x1800170e9  test    r14d, r14d
0x1800170ec  jns     short loc_18001711A
0x1800170ee  mov     edx, r14d; char *
0x1800170f1  lea     rcx, aTkey; "tkey"
0x1800170f8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800170fd  mov     rcx, [rbp+4Fh+var_68]; void *
0x180017101  mov     [rdi], rbx
0x180017104  mov     [rdi+8], rbx
0x180017108  mov     [rdi+10h], r14d
0x18001710c  test    rcx, rcx
0x18001710f  jz      short loc_1800170C3
0x180017111  xor     edx, edx; struct std::nothrow_t *
0x180017113  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017118  jmp     short loc_1800170C3
0x18001711a  mov     eax, [rbp+4Fh+var_70]
0x18001711d  mov     r14, [rbp+4Fh+pbSalt]
0x180017121  mov     r8d, [rbp+4Fh+cbPassword]; cbPassword
0x180017125  mov     r9, r14; pbSalt
0x180017128  mov     [rsp+40h], ebx; dwFlags
0x18001712c  mov     [rsp+0F0h+cbDerivedKey], eax; cbDerivedKey
0x180017130  mov     ecx, r12d
0x180017133  mov     r12, [rbp+4Fh+var_68]
0x180017137  mov     [rsp+0F0h+pbDerivedKey], r12; pbDerivedKey
0x18001713c  mov     [rsp+0F0h+cIterations], rcx; cIterations
0x180017141  mov     rcx, [rsi+98h]; hPrf
0x180017148  mov     [rsp+0F0h+cbSalt], r15d; cbSalt
0x18001714d  mov     r15, [rbp+4Fh+pbPassword]
0x180017151  mov     rdx, r15; pbPassword
0x180017154  call    cs:__imp_BCryptDeriveKeyPBKDF2
0x18001715a  mov     r13d, eax
0x18001715d  test    eax, eax
0x18001715f  jns     short loc_1800171A5
0x180017161  mov     edx, eax; char *
0x180017163  lea     rcx, aBcryptderiveke; "BCryptDeriveKeyPBKDF2(m_checksumHandle,"...
0x18001716a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001716f  mov     [rdi], rbx
0x180017172  mov     [rdi+8], rbx
0x180017176  mov     [rdi+10h], r13d
0x18001717a  test    r12, r12
0x18001717d  jz      short loc_180017189
0x18001717f  xor     edx, edx; struct std::nothrow_t *
0x180017181  mov     rcx, r12; void *
0x180017184  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017189  test    r15, r15
0x18001718c  jz      short loc_180017198
0x18001718e  xor     edx, edx; struct std::nothrow_t *
0x180017190  mov     rcx, r15; void *
0x180017193  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017198  test    r14, r14
0x18001719b  jz      short loc_180017201
0x18001719d  mov     rcx, r14
0x1800171a0  jmp     loc_18001705A
0x1800171a5  lea     rax, aKerberos; "kerberos"
0x1800171ac  mov     qword ptr [rbp+4Fh+var_88], 8
0x1800171b4  mov     [rbp+4Fh+pbSalt], rax
0x1800171b8  lea     r9, [rbp+4Fh+var_88]
0x1800171bc  mov     rax, [rsi+40h]
0x1800171c0  lea     r8, [rbp+4Fh+var_70]
0x1800171c4  mov     [rsp+0F0h+cIterations], rax
0x1800171c9  mov     rdx, rdi
0x1800171cc  lea     rax, [rbp+4Fh+cbPassword]
0x1800171d0  mov     qword ptr [rbp+4Fh+cbPassword], rbx
0x1800171d4  mov     rcx, rsi
0x1800171d7  mov     qword ptr [rsp+0F0h+cbSalt], rax
0x1800171dc  mov     [rbp+4Fh+pbPassword], rbx
0x1800171e0  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800171e5  jmp     short loc_18001717A
0x1800171e7  lea     rcx, aSaltpAppend1LX; "saltp.append(1, L'\\x00')"
0x1800171ee  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800171f3  mov     [rdi], rbx
0x1800171f6  mov     [rdi+8], rbx
0x1800171fa  mov     dword ptr [rdi+10h], 0C0000023h
0x180017201  mov     rcx, [rbp+4Fh+var_58]; void *
0x180017205  lea     rax, [rbp+4Fh+var_48]
0x180017209  cmp     rcx, rax
0x18001720c  jz      short loc_18001721A
0x18001720e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017215  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001721a  mov     rbx, [rsp+0F0h+arg_0]
0x180017222  mov     rax, rdi
0x180017225  add     rsp, 0C0h
0x18001722c  pop     r15
0x18001722e  pop     r14
0x180017230  pop     r13
0x180017232  pop     r12
0x180017234  pop     rdi
0x180017235  pop     rsi
0x180017236  pop     rbp
0x180017237  retn
```
