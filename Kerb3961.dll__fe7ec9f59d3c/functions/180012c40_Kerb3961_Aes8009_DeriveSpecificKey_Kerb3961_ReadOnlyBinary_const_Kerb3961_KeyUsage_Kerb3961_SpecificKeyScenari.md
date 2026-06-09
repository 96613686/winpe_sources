# Kerb3961::Aes8009::DeriveSpecificKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::KeyUsage,Kerb3961::SpecificKeyScenario)

- ea: `0x180012c40`
- end: `0x180012f36`
- name: `?DeriveSpecificKey@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@W4KeyUsage@2@W4SpecificKeyScenario@2@@Z`
- size: `758`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18001023c`
- `0x180012ab8`
- `0x180012c40`

## string_xrefs

- `0x180012d50`: `specificKey->Kc = DeriveKey(protocolKey, {5, constant.data}, {}, m_micLength)`
- `0x180012e48`: `specificKey->Ke = DeriveKey(protocolKey, {5, constant.data}, {}, m_keySize)`
- `0x180012edf`: `specificKey->Ki = DeriveKey(protocolKey, {5, constant.data}, {}, m_micLength)`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::DeriveSpecificKey(__int64 a1, __int64 a2, int a3, unsigned int a4, int a5)
{
  const char *v8; // rdx
  void *v9; // rbx
  __int64 v10; // rax
  int v11; // r8d
  void *v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rax
  int v15; // esi
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  void *v21; // rcx
  __int64 v22; // rsi
  __int64 v23; // rax
  int v24; // esi
  char *v25; // rcx
  __int64 v26; // rax
  void *v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v31; // [rsp+28h] [rbp-58h]
  __int64 v32; // [rsp+28h] [rbp-58h]
  __int64 v33; // [rsp+28h] [rbp-58h]
  void *v34; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v35; // [rsp+38h] [rbp-48h]
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v37; // [rsp+48h] [rbp-38h]
  char v38; // [rsp+50h] [rbp-30h] BYREF
  void *v39; // [rsp+58h] [rbp-28h]
  __int64 v40; // [rsp+68h] [rbp-18h] BYREF

  v40 = _byteswap_ulong(a4);
  utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(&v34);
  v9 = v34;
  if ( !v34 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"specificKey", v8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    return a2;
  }
  if ( (unsigned int)(a5 - 2) > 1 )
    goto LABEL_17;
  BYTE4(v40) = -103;
  v37 = &v40;
  v31 = *(_QWORD *)(a1 + 88);
  v34 = 0;
  v35 = 0;
  v36 = 5;
  v10 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)&v38, a3, (unsigned int)&v36, (__int64)&v34, v31);
  v12 = (void *)*((_QWORD *)v9 + 1);
  v13 = v10;
  if ( v12 )
    operator delete(v12, 0);
  *(_QWORD *)v9 = *(_QWORD *)v13;
  v14 = *(_QWORD *)(v13 + 8);
  *(_QWORD *)v13 = 0;
  *((_QWORD *)v9 + 1) = v14;
  LODWORD(v14) = *(_DWORD *)(v13 + 16);
  *(_QWORD *)(v13 + 8) = 0;
  *((_DWORD *)v9 + 4) = v14;
  *(_DWORD *)(v13 + 16) = -1073741823;
  v15 = *((_DWORD *)v9 + 4);
  if ( v39 )
    operator delete(v39, 0);
  if ( v15 >= 0 )
  {
LABEL_17:
    if ( ((a5 - 1) & 0xFFFFFFFD) == 0 )
    {
      BYTE4(v40) = -86;
      v35 = &v40;
      v32 = *(_QWORD *)(a1 + 64);
      v36 = 0;
      v37 = 0;
      v34 = (void *)5;
      v19 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)&v38, a3, (unsigned int)&v34, (__int64)&v36, v32);
      v21 = (void *)*((_QWORD *)v9 + 4);
      v22 = v19;
      if ( v21 )
        operator delete(v21, 0);
      *((_QWORD *)v9 + 3) = *(_QWORD *)v22;
      v23 = *(_QWORD *)(v22 + 8);
      *(_QWORD *)v22 = 0;
      *((_QWORD *)v9 + 4) = v23;
      LODWORD(v23) = *(_DWORD *)(v22 + 16);
      *(_QWORD *)(v22 + 8) = 0;
      *((_DWORD *)v9 + 10) = v23;
      *(_DWORD *)(v22 + 16) = -1073741823;
      v24 = *((_DWORD *)v9 + 10);
      if ( v39 )
        operator delete(v39, 0);
      if ( v24 < 0 )
      {
        v25 = "specificKey->Ke = DeriveKey(protocolKey, {5, constant.data}, {}, m_keySize)";
        goto LABEL_30;
      }
      BYTE4(v40) = 85;
      v35 = &v40;
      v33 = *(_QWORD *)(a1 + 88);
      v36 = 0;
      v37 = 0;
      v34 = (void *)5;
      v26 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)&v38, a3, (unsigned int)&v34, (__int64)&v36, v33);
      v27 = (void *)*((_QWORD *)v9 + 7);
      v28 = v26;
      if ( v27 )
        operator delete(v27, 0);
      *((_QWORD *)v9 + 6) = *(_QWORD *)v28;
      v29 = *(_QWORD *)(v28 + 8);
      *(_QWORD *)v28 = 0;
      *((_QWORD *)v9 + 7) = v29;
      LODWORD(v29) = *(_DWORD *)(v28 + 16);
      *(_QWORD *)(v28 + 8) = 0;
      *((_DWORD *)v9 + 16) = v29;
      *(_DWORD *)(v28 + 16) = -1073741823;
      v24 = *((_DWORD *)v9 + 16);
      if ( v39 )
        operator delete(v39, 0);
      if ( v24 < 0 )
      {
        v25 = "specificKey->Ki = DeriveKey(protocolKey, {5, constant.data}, {}, m_micLength)";
LABEL_30:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v25, (const char *)(unsigned int)v24, v20);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v24;
        if ( !v9 )
          return a2;
        goto LABEL_10;
      }
    }
    *(_QWORD *)a2 = a1;
    *(_QWORD *)(a2 + 8) = v9;
    *(_DWORD *)(a2 + 16) = 0;
    return a2;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey->Kc = DeriveKey(protocolKey, {5, constant.data}, {}, m_micLength)",
    (const char *)(unsigned int)v15,
    v11);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v15;
LABEL_10:
  v16 = (void *)*((_QWORD *)v9 + 7);
  if ( v16 )
    operator delete(v16, 0);
  v17 = (void *)*((_QWORD *)v9 + 4);
  if ( v17 )
    operator delete(v17, 0);
  v18 = (void *)*((_QWORD *)v9 + 1);
  if ( v18 )
    operator delete(v18, 0);
  operator delete(v9, (const struct std::nothrow_t *)0x48);
  return a2;
}

```

## disassembly

```asm
0x180012c40  mov     [rsp-38h+arg_18], rbx
0x180012c45  push    rbp
0x180012c46  push    rsi
0x180012c47  push    rdi
0x180012c48  push    r12
0x180012c4a  push    r13
0x180012c4c  push    r14
0x180012c4e  push    r15
0x180012c50  mov     rbp, rsp
0x180012c53  sub     rsp, 80h
0x180012c5a  mov     rax, cs:__security_cookie
0x180012c61  xor     rax, rsp
0x180012c64  mov     [rbp+var_10], rax
0x180012c68  mov     r15, rcx
0x180012c6b  xor     r13d, r13d
0x180012c6e  bswap   r9d
0x180012c71  mov     [rbp+var_18], r13
0x180012c75  lea     rcx, [rbp+var_50]
0x180012c79  mov     dword ptr [rbp+var_18], r9d
0x180012c7d  mov     r12, r8
0x180012c80  mov     rdi, rdx
0x180012c83  call    ??$make_unique@USimplifiedSpecificKey@Kerb3961@@$$V$0A@@utl@@YA?AV?$unique_ptr@USimplifiedSpecificKey@Kerb3961@@U?$default_delete@USimplifiedSpecificKey@Kerb3961@@@utl@@@0@XZ; utl::make_unique<Kerb3961::SimplifiedSpecificKey,,0>(void)
0x180012c88  mov     rbx, [rbp+var_50]
0x180012c8c  test    rbx, rbx
0x180012c8f  jnz     short loc_180012CB0
0x180012c91  lea     rcx, aSpecifickey; "specificKey"
0x180012c98  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180012c9d  mov     [rdi], r13
0x180012ca0  mov     [rdi+8], r13
0x180012ca4  mov     dword ptr [rdi+10h], 0C0000017h
0x180012cab  jmp     loc_180012F0C
0x180012cb0  mov     r14d, [rbp+arg_20]
0x180012cb4  lea     eax, [r14-2]
0x180012cb8  cmp     eax, 1
0x180012cbb  ja      loc_180012DA8
0x180012cc1  lea     rax, [rbp+var_18]
0x180012cc5  mov     byte ptr [rbp+var_18+4], 99h
0x180012cc9  mov     [rbp+var_38], rax
0x180012ccd  lea     r9, [rbp+var_40]
0x180012cd1  mov     rax, [r15+58h]
0x180012cd5  lea     rdx, [rbp+var_30]
0x180012cd9  mov     [rsp+80h+var_58], rax
0x180012cde  mov     r8, r12
0x180012ce1  lea     rax, [rbp+var_50]
0x180012ce5  mov     [rbp+var_50], r13
0x180012ce9  mov     rcx, r15
0x180012cec  mov     [rsp+80h+var_60], rax
0x180012cf1  mov     [rbp+var_48], r13
0x180012cf5  mov     [rbp+var_40], 5
0x180012cfd  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180012d02  mov     rcx, [rbx+8]; void *
0x180012d06  mov     rsi, rax
0x180012d09  test    rcx, rcx
0x180012d0c  jz      short loc_180012D15
0x180012d0e  xor     edx, edx; struct std::nothrow_t *
0x180012d10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d15  mov     rcx, [rsi]
0x180012d18  mov     [rbx], rcx
0x180012d1b  mov     rax, [rsi+8]
0x180012d1f  mov     [rsi], r13
0x180012d22  mov     [rbx+8], rax
0x180012d26  mov     eax, [rsi+10h]
0x180012d29  mov     [rsi+8], r13
0x180012d2d  mov     [rbx+10h], eax
0x180012d30  mov     dword ptr [rsi+10h], 0C0000001h
0x180012d37  mov     rcx, [rbp+var_28]; void *
0x180012d3b  mov     esi, [rbx+10h]
0x180012d3e  test    rcx, rcx
0x180012d41  jz      short loc_180012D4A
0x180012d43  xor     edx, edx; struct std::nothrow_t *
0x180012d45  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d4a  test    esi, esi
0x180012d4c  jns     short loc_180012DA8
0x180012d4e  mov     edx, esi; char *
0x180012d50  lea     rcx, aSpecifickeyKcD; "specificKey->Kc = DeriveKey(protocolKey"...
0x180012d57  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012d5c  mov     [rdi], r13
0x180012d5f  mov     [rdi+8], r13
0x180012d63  mov     [rdi+10h], esi
0x180012d66  mov     rcx, [rbx+38h]; void *
0x180012d6a  test    rcx, rcx
0x180012d6d  jz      short loc_180012D76
0x180012d6f  xor     edx, edx; struct std::nothrow_t *
0x180012d71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d76  mov     rcx, [rbx+20h]; void *
0x180012d7a  test    rcx, rcx
0x180012d7d  jz      short loc_180012D86
0x180012d7f  xor     edx, edx; struct std::nothrow_t *
0x180012d81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d86  mov     rcx, [rbx+8]; void *
0x180012d8a  test    rcx, rcx
0x180012d8d  jz      short loc_180012D96
0x180012d8f  xor     edx, edx; struct std::nothrow_t *
0x180012d91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d96  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x180012d9b  mov     rcx, rbx; void *
0x180012d9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012da3  jmp     loc_180012F0C
0x180012da8  lea     eax, [r14-1]
0x180012dac  test    eax, 0FFFFFFFDh
0x180012db1  jnz     loc_180012F01
0x180012db7  lea     rax, [rbp+var_18]
0x180012dbb  mov     byte ptr [rbp+var_18+4], 0AAh
0x180012dbf  mov     [rbp+var_48], rax
0x180012dc3  lea     r9, [rbp+var_50]
0x180012dc7  mov     rax, [r15+40h]
0x180012dcb  lea     rdx, [rbp+var_30]
0x180012dcf  mov     [rsp+80h+var_58], rax
0x180012dd4  mov     r8, r12
0x180012dd7  lea     rax, [rbp+var_40]
0x180012ddb  mov     [rbp+var_40], r13
0x180012ddf  mov     rcx, r15
0x180012de2  mov     [rsp+80h+var_60], rax
0x180012de7  mov     [rbp+var_38], r13
0x180012deb  mov     [rbp+var_50], 5
0x180012df3  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180012df8  mov     rcx, [rbx+20h]; void *
0x180012dfc  mov     rsi, rax
0x180012dff  test    rcx, rcx
0x180012e02  jz      short loc_180012E0B
0x180012e04  xor     edx, edx; struct std::nothrow_t *
0x180012e06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012e0b  mov     rcx, [rsi]
0x180012e0e  mov     r14d, 0C0000001h
0x180012e14  mov     [rbx+18h], rcx
0x180012e18  mov     rax, [rsi+8]
0x180012e1c  mov     [rsi], r13
0x180012e1f  mov     [rbx+20h], rax
0x180012e23  mov     eax, [rsi+10h]
0x180012e26  mov     [rsi+8], r13
0x180012e2a  mov     [rbx+28h], eax
0x180012e2d  mov     [rsi+10h], r14d
0x180012e31  mov     rcx, [rbp+var_28]; void *
0x180012e35  mov     esi, [rbx+28h]
0x180012e38  test    rcx, rcx
0x180012e3b  jz      short loc_180012E44
0x180012e3d  xor     edx, edx; struct std::nothrow_t *
0x180012e3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012e44  test    esi, esi
0x180012e46  jns     short loc_180012E54
0x180012e48  lea     rcx, aSpecifickeyKeD; "specificKey->Ke = DeriveKey(protocolKey"...
0x180012e4f  jmp     loc_180012EE6
0x180012e54  lea     rax, [rbp+var_18]
0x180012e58  mov     byte ptr [rbp+var_18+4], 55h ; 'U'
0x180012e5c  mov     [rbp+var_48], rax
0x180012e60  lea     r9, [rbp+var_50]
0x180012e64  mov     rax, [r15+58h]
0x180012e68  lea     rdx, [rbp+var_30]
0x180012e6c  mov     [rsp+80h+var_58], rax
0x180012e71  mov     r8, r12
0x180012e74  lea     rax, [rbp+var_40]
0x180012e78  mov     [rbp+var_40], r13
0x180012e7c  mov     rcx, r15
0x180012e7f  mov     [rsp+80h+var_60], rax
0x180012e84  mov     [rbp+var_38], r13
0x180012e88  mov     [rbp+var_50], 5
0x180012e90  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z; Kerb3961::Aes8009::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180012e95  mov     rcx, [rbx+38h]; void *
0x180012e99  mov     rsi, rax
0x180012e9c  test    rcx, rcx
0x180012e9f  jz      short loc_180012EA8
0x180012ea1  xor     edx, edx; struct std::nothrow_t *
0x180012ea3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012ea8  mov     rcx, [rsi]
0x180012eab  mov     [rbx+30h], rcx
0x180012eaf  mov     rax, [rsi+8]
0x180012eb3  mov     [rsi], r13
0x180012eb6  mov     [rbx+38h], rax
0x180012eba  mov     eax, [rsi+10h]
0x180012ebd  mov     [rsi+8], r13
0x180012ec1  mov     [rbx+40h], eax
0x180012ec4  mov     [rsi+10h], r14d
0x180012ec8  mov     rcx, [rbp+var_28]; void *
0x180012ecc  mov     esi, [rbx+40h]
0x180012ecf  test    rcx, rcx
0x180012ed2  jz      short loc_180012EDB
0x180012ed4  xor     edx, edx; struct std::nothrow_t *
0x180012ed6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012edb  test    esi, esi
0x180012edd  jns     short loc_180012F01
0x180012edf  lea     rcx, aSpecifickeyKiD; "specificKey->Ki = DeriveKey(protocolKey"...
0x180012ee6  mov     edx, esi; char *
0x180012ee8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012eed  mov     [rdi], r13
0x180012ef0  mov     [rdi+8], r13
0x180012ef4  mov     [rdi+10h], esi
0x180012ef7  test    rbx, rbx
0x180012efa  jz      short loc_180012F0C
0x180012efc  jmp     loc_180012D66
0x180012f01  mov     [rdi], r15
0x180012f04  mov     [rdi+8], rbx
0x180012f08  mov     [rdi+10h], r13d
0x180012f0c  mov     rax, rdi
0x180012f0f  mov     rcx, [rbp+var_10]
0x180012f13  xor     rcx, rsp; StackCookie
0x180012f16  call    __security_check_cookie
0x180012f1b  mov     rbx, [rsp+80h+arg_18]
0x180012f23  add     rsp, 80h
0x180012f2a  pop     r15
0x180012f2c  pop     r14
0x180012f2e  pop     r13
0x180012f30  pop     r12
0x180012f32  pop     rdi
0x180012f33  pop     rsi
0x180012f34  pop     rbp
0x180012f35  retn
```
