# Kerb3961::Aes8009::DeriveSpecificKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::KeyUsage,Kerb3961::SpecificKeyScenario)

- ea: `0x180008020`
- end: `0x180008300`
- name: `?DeriveSpecificKey@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@W4KeyUsage@2@W4SpecificKeyScenario@2@@Z`
- size: `736`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000186c`
- `0x180007e9c`
- `0x180008020`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`

## string_xrefs

- `0x18000812c`: `specificKey->Kc = DeriveKey(protocolKey, {5, constant.data}, {}, m_micLength)`
- `0x180008215`: `specificKey->Ke = DeriveKey(protocolKey, {5, constant.data}, {}, m_keySize)`
- `0x1800082a8`: `specificKey->Ki = DeriveKey(protocolKey, {5, constant.data}, {}, m_micLength)`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::DeriveSpecificKey(__int64 a1, __int64 a2, int a3, unsigned int a4, int a5)
{
  const char *v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rax
  int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int64 v23; // rax
  int v24; // esi
  char *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v31; // [rsp+28h] [rbp-58h]
  __int64 v32; // [rsp+28h] [rbp-58h]
  __int64 v33; // [rsp+28h] [rbp-58h]
  __int64 v34; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v35; // [rsp+38h] [rbp-48h]
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v37; // [rsp+48h] [rbp-38h]
  char v38; // [rsp+50h] [rbp-30h] BYREF
  __int64 v39; // [rsp+58h] [rbp-28h]
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
  v12 = *(_QWORD *)(v9 + 8);
  v13 = v10;
  if ( v12 )
    Kerb3961Free(v12);
  *(_QWORD *)v9 = *(_QWORD *)v13;
  v14 = *(_QWORD *)(v13 + 8);
  *(_QWORD *)v13 = 0;
  *(_QWORD *)(v9 + 8) = v14;
  LODWORD(v14) = *(_DWORD *)(v13 + 16);
  *(_QWORD *)(v13 + 8) = 0;
  *(_DWORD *)(v9 + 16) = v14;
  *(_DWORD *)(v13 + 16) = -1073741823;
  v15 = *(_DWORD *)(v9 + 16);
  if ( v39 )
    Kerb3961Free(v39);
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
      v34 = 5;
      v19 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)&v38, a3, (unsigned int)&v34, (__int64)&v36, v32);
      v21 = *(_QWORD *)(v9 + 32);
      v22 = v19;
      if ( v21 )
        Kerb3961Free(v21);
      *(_QWORD *)(v9 + 24) = *(_QWORD *)v22;
      v23 = *(_QWORD *)(v22 + 8);
      *(_QWORD *)v22 = 0;
      *(_QWORD *)(v9 + 32) = v23;
      LODWORD(v23) = *(_DWORD *)(v22 + 16);
      *(_QWORD *)(v22 + 8) = 0;
      *(_DWORD *)(v9 + 40) = v23;
      *(_DWORD *)(v22 + 16) = -1073741823;
      v24 = *(_DWORD *)(v9 + 40);
      if ( v39 )
        Kerb3961Free(v39);
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
      v34 = 5;
      v26 = Kerb3961::Aes8009::DeriveKey(a1, (unsigned int)&v38, a3, (unsigned int)&v34, (__int64)&v36, v33);
      v27 = *(_QWORD *)(v9 + 56);
      v28 = v26;
      if ( v27 )
        Kerb3961Free(v27);
      *(_QWORD *)(v9 + 48) = *(_QWORD *)v28;
      v29 = *(_QWORD *)(v28 + 8);
      *(_QWORD *)v28 = 0;
      *(_QWORD *)(v9 + 56) = v29;
      LODWORD(v29) = *(_DWORD *)(v28 + 16);
      *(_QWORD *)(v28 + 8) = 0;
      *(_DWORD *)(v9 + 64) = v29;
      *(_DWORD *)(v28 + 16) = -1073741823;
      v24 = *(_DWORD *)(v9 + 64);
      if ( v39 )
        Kerb3961Free(v39);
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
  v16 = *(_QWORD *)(v9 + 56);
  if ( v16 )
    Kerb3961Free(v16);
  v17 = *(_QWORD *)(v9 + 32);
  if ( v17 )
    Kerb3961Free(v17);
  v18 = *(_QWORD *)(v9 + 8);
  if ( v18 )
    Kerb3961Free(v18);
  Kerb3961Free(v9);
  return a2;
}

```

## disassembly

```asm
0x180008020  mov     [rsp-38h+arg_18], rbx
0x180008025  push    rbp
0x180008026  push    rsi
0x180008027  push    rdi
0x180008028  push    r12
0x18000802a  push    r13
0x18000802c  push    r14
0x18000802e  push    r15
0x180008030  mov     rbp, rsp
0x180008033  sub     rsp, 80h
0x18000803a  mov     rax, cs:__security_cookie
0x180008041  xor     rax, rsp
0x180008044  mov     [rbp+var_10], rax
0x180008048  mov     r14, rcx
0x18000804b  xor     r13d, r13d
0x18000804e  bswap   r9d
0x180008051  mov     [rbp+var_18], r13
0x180008055  lea     rcx, [rbp+var_50]
0x180008059  mov     dword ptr [rbp+var_18], r9d
0x18000805d  mov     r12, r8
0x180008060  mov     rdi, rdx
0x180008063  call    ??$make_unique@USimplifiedSpecificKey@Kerb3961@@$$V$0A@@utl@@YA?AV?$unique_ptr@USimplifiedSpecificKey@Kerb3961@@U?$default_delete@USimplifiedSpecificKey@Kerb3961@@@utl@@@0@XZ
0x180008068  mov     rbx, [rbp+var_50]
0x18000806c  test    rbx, rbx
0x18000806f  jnz     short loc_180008090
0x180008071  lea     rcx, aSpecifickey
0x180008078  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z
0x18000807d  mov     [rdi], r13
0x180008080  mov     [rdi+8], r13
0x180008084  mov     dword ptr [rdi+10h], 0C0000017h
0x18000808b  jmp     loc_1800082D5
0x180008090  mov     r15d, [rbp+arg_20]
0x180008094  lea     eax, [r15-2]
0x180008098  cmp     eax, 1
0x18000809b  ja      loc_180008179
0x1800080a1  lea     rax, [rbp+var_18]
0x1800080a5  mov     byte ptr [rbp+var_18+4], 99h
0x1800080a9  mov     [rbp+var_38], rax
0x1800080ad  lea     r9, [rbp+var_40]
0x1800080b1  mov     rax, [r14+58h]
0x1800080b5  lea     rdx, [rbp+var_30]
0x1800080b9  mov     [rsp+80h+var_58], rax
0x1800080be  mov     r8, r12
0x1800080c1  lea     rax, [rbp+var_50]
0x1800080c5  mov     [rbp+var_50], r13
0x1800080c9  mov     rcx, r14
0x1800080cc  mov     [rsp+80h+var_60], rax
0x1800080d1  mov     [rbp+var_48], r13
0x1800080d5  mov     [rbp+var_40], 5
0x1800080dd  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z
0x1800080e2  mov     rcx, [rbx+8]
0x1800080e6  mov     rsi, rax
0x1800080e9  test    rcx, rcx
0x1800080ec  jz      short loc_1800080F3
0x1800080ee  call    Kerb3961Free
0x1800080f3  mov     rcx, [rsi]
0x1800080f6  mov     [rbx], rcx
0x1800080f9  mov     rax, [rsi+8]
0x1800080fd  mov     [rsi], r13
0x180008100  mov     [rbx+8], rax
0x180008104  mov     eax, [rsi+10h]
0x180008107  mov     [rsi+8], r13
0x18000810b  mov     [rbx+10h], eax
0x18000810e  mov     dword ptr [rsi+10h], 0C0000001h
0x180008115  mov     rcx, [rbp+var_28]
0x180008119  mov     esi, [rbx+10h]
0x18000811c  test    rcx, rcx
0x18000811f  jz      short loc_180008126
0x180008121  call    Kerb3961Free
0x180008126  test    esi, esi
0x180008128  jns     short loc_180008179
0x18000812a  mov     edx, esi; char *
0x18000812c  lea     rcx, aSpecifickeyKcD
0x180008133  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z
0x180008138  mov     [rdi], r13
0x18000813b  mov     [rdi+8], r13
0x18000813f  mov     [rdi+10h], esi
0x180008142  mov     rcx, [rbx+38h]
0x180008146  test    rcx, rcx
0x180008149  jz      short loc_180008150
0x18000814b  call    Kerb3961Free
0x180008150  mov     rcx, [rbx+20h]
0x180008154  test    rcx, rcx
0x180008157  jz      short loc_18000815E
0x180008159  call    Kerb3961Free
0x18000815e  mov     rcx, [rbx+8]
0x180008162  test    rcx, rcx
0x180008165  jz      short loc_18000816C
0x180008167  call    Kerb3961Free
0x18000816c  mov     rcx, rbx
0x18000816f  call    Kerb3961Free
0x180008174  jmp     loc_1800082D5
0x180008179  lea     eax, [r15-1]
0x18000817d  test    eax, 0FFFFFFFDh
0x180008182  jnz     loc_1800082CA
0x180008188  lea     rax, [rbp+var_18]
0x18000818c  mov     byte ptr [rbp+var_18+4], 0AAh
0x180008190  mov     [rbp+var_48], rax
0x180008194  lea     r9, [rbp+var_50]
0x180008198  mov     rax, [r14+40h]
0x18000819c  lea     rdx, [rbp+var_30]
0x1800081a0  mov     [rsp+80h+var_58], rax
0x1800081a5  mov     r8, r12
0x1800081a8  lea     rax, [rbp+var_40]
0x1800081ac  mov     [rbp+var_40], r13
0x1800081b0  mov     rcx, r14
0x1800081b3  mov     [rsp+80h+var_60], rax
0x1800081b8  mov     [rbp+var_38], r13
0x1800081bc  mov     [rbp+var_50], 5
0x1800081c4  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z
0x1800081c9  mov     rcx, [rbx+20h]
0x1800081cd  mov     rsi, rax
0x1800081d0  test    rcx, rcx
0x1800081d3  jz      short loc_1800081DA
0x1800081d5  call    Kerb3961Free
0x1800081da  mov     rcx, [rsi]
0x1800081dd  mov     r15d, 0C0000001h
0x1800081e3  mov     [rbx+18h], rcx
0x1800081e7  mov     rax, [rsi+8]
0x1800081eb  mov     [rsi], r13
0x1800081ee  mov     [rbx+20h], rax
0x1800081f2  mov     eax, [rsi+10h]
0x1800081f5  mov     [rsi+8], r13
0x1800081f9  mov     [rbx+28h], eax
0x1800081fc  mov     [rsi+10h], r15d
0x180008200  mov     rcx, [rbp+var_28]
0x180008204  mov     esi, [rbx+28h]
0x180008207  test    rcx, rcx
0x18000820a  jz      short loc_180008211
0x18000820c  call    Kerb3961Free
0x180008211  test    esi, esi
0x180008213  jns     short loc_180008221
0x180008215  lea     rcx, aSpecifickeyKeD
0x18000821c  jmp     loc_1800082AF
0x180008221  lea     rax, [rbp+var_18]
0x180008225  mov     byte ptr [rbp+var_18+4], 55h ; 'U'
0x180008229  mov     [rbp+var_48], rax
0x18000822d  lea     r9, [rbp+var_50]
0x180008231  mov     rax, [r14+58h]
0x180008235  lea     rdx, [rbp+var_30]
0x180008239  mov     [rsp+80h+var_58], rax
0x18000823e  mov     r8, r12
0x180008241  lea     rax, [rbp+var_40]
0x180008245  mov     [rbp+var_40], r13
0x180008249  mov     rcx, r14
0x18000824c  mov     [rsp+80h+var_60], rax
0x180008251  mov     [rbp+var_38], r13
0x180008255  mov     [rbp+var_50], 5
0x18000825d  call    ?DeriveKey@Aes8009@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00_K@Z
0x180008262  mov     rcx, [rbx+38h]
0x180008266  mov     rsi, rax
0x180008269  test    rcx, rcx
0x18000826c  jz      short loc_180008273
0x18000826e  call    Kerb3961Free
0x180008273  mov     rcx, [rsi]
0x180008276  mov     [rbx+30h], rcx
0x18000827a  mov     rax, [rsi+8]
0x18000827e  mov     [rsi], r13
0x180008281  mov     [rbx+38h], rax
0x180008285  mov     eax, [rsi+10h]
0x180008288  mov     [rsi+8], r13
0x18000828c  mov     [rbx+40h], eax
0x18000828f  mov     [rsi+10h], r15d
0x180008293  mov     rcx, [rbp+var_28]
0x180008297  mov     esi, [rbx+40h]
0x18000829a  test    rcx, rcx
0x18000829d  jz      short loc_1800082A4
0x18000829f  call    Kerb3961Free
0x1800082a4  test    esi, esi
0x1800082a6  jns     short loc_1800082CA
0x1800082a8  lea     rcx, aSpecifickeyKiD
0x1800082af  mov     edx, esi; char *
0x1800082b1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z
0x1800082b6  mov     [rdi], r13
0x1800082b9  mov     [rdi+8], r13
0x1800082bd  mov     [rdi+10h], esi
0x1800082c0  test    rbx, rbx
0x1800082c3  jz      short loc_1800082D5
0x1800082c5  jmp     loc_180008142
0x1800082ca  mov     [rdi], r14
0x1800082cd  mov     [rdi+8], rbx
0x1800082d1  mov     [rdi+10h], r13d
0x1800082d5  mov     rax, rdi
0x1800082d8  mov     rcx, [rbp+var_10]
0x1800082dc  xor     rcx, rsp; StackCookie
0x1800082df  call    __security_check_cookie
0x1800082e4  mov     rbx, [rsp+80h+arg_18]
0x1800082ec  add     rsp, 80h
0x1800082f3  pop     r15
0x1800082f5  pop     r14
0x1800082f7  pop     r13
0x1800082f9  pop     r12
0x1800082fb  pop     rdi
0x1800082fc  pop     rsi
0x1800082fd  pop     rbp
0x1800082fe  retn
```
