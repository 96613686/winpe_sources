# Kerb3961::Aes8009::StringToKey(Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180009570`
- end: `0x180009752`
- name: `?StringToKey@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyString@2@0AEBUReadOnlyBinary@2@@Z`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009570`
- `0x180009890`
- `0x180009964`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::StringToKey(__int64 a1, __int64 a2, __int64 a3, unsigned __int64 *a4, __int64 a5)
{
  char *v8; // rcx
  unsigned __int32 v9; // ecx
  unsigned __int64 v10; // rcx
  const char *v11; // rdx
  unsigned __int64 v12; // rsi
  const char *v13; // rdx
  const char *v14; // rdx
  char *v15; // rcx
  char *v16; // rax
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // r15
  int v19; // r8d
  char *v21; // [rsp+20h] [rbp-20h] BYREF
  char *v22; // [rsp+28h] [rbp-18h]
  _QWORD v23[2]; // [rsp+30h] [rbp-10h] BYREF

  if ( *(_QWORD *)a5 != 4 )
  {
    v8 = "stringToKeyParameters.length == sizeof(uint32_t)";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v8, (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  v9 = _byteswap_ulong(**(_DWORD **)(a5 + 8));
  if ( v9 > *(_DWORD *)(a1 + 136) )
  {
    v8 = "iterations <= m_maxIterationCount";
    goto LABEL_3;
  }
  if ( v9 < *(_DWORD *)(a1 + 140) )
  {
    v8 = "iterations >= m_minIterationCount";
    goto LABEL_3;
  }
  v10 = *a4;
  v21 = (char *)v23;
  LOWORD(v23[0]) = 0;
  v22 = (char *)v23;
  v11 = (const char *)(*(_QWORD *)(a1 + 112) + v10 + 1);
  if ( (unsigned __int64)v11 <= v10 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"saltpLength > salt.length", v11);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    goto LABEL_26;
  }
  v12 = 7;
  if ( (unsigned __int64)v11 > 7
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(&v21) )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"saltp.reserve(salt.length + m_encryptionTypeName.length() + 1)",
      v13);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
    goto LABEL_26;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v21,
                           *(_QWORD *)(a1 + 104),
                           *(_QWORD *)(a1 + 112)) )
  {
    v15 = "saltp.append(m_encryptionTypeName)";
    goto LABEL_25;
  }
  v16 = v21;
  v17 = (v22 - v21) >> 1;
  if ( v21 != (char *)v23 )
    v12 = (__int64)(v23[0] - (_QWORD)v21) >> 1;
  v18 = v17 + 1;
  if ( v17 >= v17 + 1 )
    goto LABEL_24;
  if ( v18 > v12 )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(&v21) )
    {
      v16 = v21;
      goto LABEL_21;
    }
LABEL_24:
    v15 = "saltp.append(1, L'\\x00')";
    goto LABEL_25;
  }
LABEL_21:
  *(_WORD *)&v16[2 * v17] = 0;
  v22 = &v21[2 * v18];
  *(_WORD *)v22 = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          &v21,
                          a4[1],
                          *a4) )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"saltUTF8", (const char *)0xC0000001LL, v19);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741823;
    goto LABEL_26;
  }
  v15 = "saltp.append(salt.buffer, salt.length)";
LABEL_25:
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v15, v14);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741789;
LABEL_26:
  if ( v21 != (char *)v23 )
    Kerb3961Free(v21);
  return a2;
}

```

## disassembly

```asm
0x180009570  push    rbp
0x180009572  push    rbx
0x180009573  push    rsi
0x180009574  push    rdi
0x180009575  push    r12
0x180009577  push    r14
0x180009579  push    r15
0x18000957b  mov     rbp, rsp
0x18000957e  sub     rsp, 40h
0x180009582  mov     rax, [rbp+arg_20]
0x180009586  mov     r12, r9
0x180009589  mov     rbx, rdx
0x18000958c  mov     r14, rcx
0x18000958f  cmp     qword ptr [rax], 4
0x180009593  jz      short loc_1800095B6
0x180009595  lea     rcx, aStringtokeypar; "stringToKeyParameters.length == sizeof("...
0x18000959c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800095a1  xor     edi, edi
0x1800095a3  mov     [rbx], rdi
0x1800095a6  mov     [rbx+8], rdi
0x1800095aa  mov     dword ptr [rbx+10h], 0C000000Dh
0x1800095b1  jmp     loc_18000973F
0x1800095b6  mov     rax, [rax+8]
0x1800095ba  mov     ecx, [rax]
0x1800095bc  bswap   ecx
0x1800095be  cmp     ecx, [r14+88h]
0x1800095c5  jbe     short loc_1800095D0
0x1800095c7  lea     rcx, aIterationsMMax; "iterations <= m_maxIterationCount"
0x1800095ce  jmp     short loc_18000959C
0x1800095d0  cmp     ecx, [r14+8Ch]
0x1800095d7  jnb     short loc_1800095E2
0x1800095d9  lea     rcx, aIterationsMMin; "iterations >= m_minIterationCount"
0x1800095e0  jmp     short loc_18000959C
0x1800095e2  mov     rcx, [r9]
0x1800095e5  lea     rax, [rbp+var_10]
0x1800095e9  xor     edi, edi
0x1800095eb  mov     [rbp+var_20], rax
0x1800095ef  lea     rax, [rbp+var_10]
0x1800095f3  mov     word ptr [rbp+var_10], di
0x1800095f7  mov     [rbp+var_18], rax
0x1800095fb  lea     rdx, [rcx+1]
0x1800095ff  add     rdx, [r14+70h]; char *
0x180009603  cmp     rdx, rcx
0x180009606  ja      short loc_180009627
0x180009608  lea     rcx, aSaltplengthSal; "saltpLength > salt.length"
0x18000960f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009614  mov     [rbx], rdi
0x180009617  mov     [rbx+8], rdi
0x18000961b  mov     dword ptr [rbx+10h], 0C0000095h
0x180009622  jmp     loc_18000972D
0x180009627  mov     esi, 7
0x18000962c  cmp     rdx, rsi
0x18000962f  jbe     short loc_18000965D
0x180009631  lea     rcx, [rbp+var_20]
0x180009635  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x18000963a  test    al, al
0x18000963c  jnz     short loc_18000965D
0x18000963e  lea     rcx, aSaltpReserveSa; "saltp.reserve(salt.length + m_encryptio"...
0x180009645  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000964a  mov     [rbx], rdi
0x18000964d  mov     [rbx+8], rdi
0x180009651  mov     dword ptr [rbx+10h], 0C0000017h
0x180009658  jmp     loc_18000972D
0x18000965d  mov     r8, [r14+70h]
0x180009661  lea     rcx, [rbp+var_20]
0x180009665  mov     rdx, [r14+68h]
0x180009669  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000966e  test    al, al
0x180009670  jnz     short loc_18000967E
0x180009672  lea     rcx, aSaltpAppendMEn; "saltp.append(m_encryptionTypeName)"
0x180009679  jmp     loc_18000971A
0x18000967e  mov     rax, [rbp+var_20]
0x180009682  lea     rcx, [rbp+var_10]
0x180009686  mov     r14, [rbp+var_18]
0x18000968a  sub     r14, rax
0x18000968d  sar     r14, 1
0x180009690  cmp     rax, rcx
0x180009693  jz      short loc_18000969F
0x180009695  mov     rsi, [rbp+var_10]
0x180009699  sub     rsi, rax
0x18000969c  sar     rsi, 1
0x18000969f  lea     r15, [r14+1]
0x1800096a3  cmp     r14, r15
0x1800096a6  ja      short loc_180009713
0x1800096a8  cmp     r15, rsi
0x1800096ab  jbe     short loc_1800096C1
0x1800096ad  mov     rdx, r15
0x1800096b0  lea     rcx, [rbp+var_20]
0x1800096b4  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x1800096b9  test    al, al
0x1800096bb  jz      short loc_180009713
0x1800096bd  mov     rax, [rbp+var_20]
0x1800096c1  mov     [rax+r14*2], di
0x1800096c6  mov     rax, [rbp+var_20]
0x1800096ca  lea     rcx, [rax+r15*2]
0x1800096ce  mov     [rbp+var_18], rcx
0x1800096d2  mov     [rcx], di
0x1800096d5  lea     rcx, [rbp+var_20]
0x1800096d9  mov     r8, [r12]
0x1800096dd  mov     rdx, [r12+8]
0x1800096e2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800096e7  test    al, al
0x1800096e9  jnz     short loc_1800096F4
0x1800096eb  lea     rcx, aSaltpAppendSal; "saltp.append(salt.buffer, salt.length)"
0x1800096f2  jmp     short loc_18000971A
0x1800096f4  mov     esi, 0C0000001h
0x1800096f9  lea     rcx, aSaltutf8; "saltUTF8"
0x180009700  mov     edx, esi; char *
0x180009702  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009707  mov     [rbx], rdi
0x18000970a  mov     [rbx+8], rdi
0x18000970e  mov     [rbx+10h], esi
0x180009711  jmp     short loc_18000972D
0x180009713  lea     rcx, aSaltpAppend1LX; "saltp.append(1, L'\\x00')"
0x18000971a  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000971f  mov     [rbx], rdi
0x180009722  mov     [rbx+8], rdi
0x180009726  mov     dword ptr [rbx+10h], 0C0000023h
0x18000972d  mov     rcx, [rbp+var_20]
0x180009731  lea     rax, [rbp+var_10]
0x180009735  cmp     rcx, rax
0x180009738  jz      short loc_18000973F
0x18000973a  call    Kerb3961Free
0x18000973f  mov     rax, rbx
0x180009742  add     rsp, 40h
0x180009746  pop     r15
0x180009748  pop     r14
0x18000974a  pop     r12
0x18000974c  pop     rdi
0x18000974d  pop     rsi
0x18000974e  pop     rbx
0x18000974f  pop     rbp
0x180009750  retn
```
