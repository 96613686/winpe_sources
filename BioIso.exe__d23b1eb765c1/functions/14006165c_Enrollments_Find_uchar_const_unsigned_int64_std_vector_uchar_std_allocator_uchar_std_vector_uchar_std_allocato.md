# Enrollments::Find(uchar const *,unsigned __int64,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x14006165c`
- end: `0x1400619cf`
- name: `?Find@Enrollments@@QEBAJPEBE_KPEAV?$vector@EV?$allocator@E@std@@@std@@222222@Z`
- size: `883`
- prototype: `__int64 __fastcall(__int64, const void *, size_t, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400619d8`

## callees

- `0x14000a420`
- `0x14000ae0c`
- `0x14000d990`
- `0x14001bd40`
- `0x14001c2dc`
- `0x14001cb6c`
- `0x14002ae40`
- `0x140040924`
- `0x140041194`
- `0x1400581e8`
- `0x14005f0fc`
- `0x14005f76c`
- `0x14006165c`
- `0x140061fb8`
- `0x1400620a0`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x1400617c3`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1400617c3`

## string_xrefs

- `0x1400618f8`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Enrollments::Find(__int64 a1, const void *a2, size_t a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r13
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  _QWORD *v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r13
  const void **v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rdx
  __int64 *j; // rcx
  __int64 *v19; // rdi
  __int64 *i; // rax
  __int128 v21; // kr00_16
  BioIsoProvider *v22; // rcx
  _QWORD *v24; // rdi
  _QWORD *v25; // r15
  const void *v26; // rcx
  int v27; // [rsp+20h] [rbp-E0h]
  USHORT Length; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v29[2]; // [rsp+32h] [rbp-CEh] BYREF
  __int16 v30; // [rsp+34h] [rbp-CCh] BYREF
  _WORD v31[9]; // [rsp+36h] [rbp-CAh] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[4]; // [rsp+54h] [rbp-ACh] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h]
  __int128 v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  char v41; // [rsp+98h] [rbp-68h] BYREF
  char v42; // [rsp+A0h] [rbp-60h] BYREF
  char v43; // [rsp+A8h] [rbp-58h] BYREF
  char v44; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v5 = a4;
  v39 = a4;
  v40 = a5;
  v8 = *(_QWORD **)(a1 + 32);
  v9 = (_QWORD *)(a1 + 40);
  if ( VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>() )
  {
    v37 = 0;
    v10 = operator new(0x40u);
    *v10 = v10;
    v10[1] = v10;
    v10[2] = v10;
    *((_WORD *)v10 + 12) = 257;
    *(_QWORD *)&v37 = v10;
    while ( v8 != (_QWORD *)*v9 )
    {
      v13 = v8[4];
      v14 = (const void **)(v8 + 1);
      if ( BioIsoProvider::IsEnabled(v12, v11) )
      {
        BioIsoProvider::Instance();
        BioIsoProvider::SecureEnrollmentDatabaseEntry_(v15, v8 + 1, v13, v8 + 7);
      }
      v16 = std::map<std::vector<unsigned char>,unsigned __int64>::_Try_emplace<std::vector<unsigned char> const &,>(
              &v37,
              &UnicodeString,
              v8 + 4);
      v12 = *(_QWORD *)v16;
      ++*(_QWORD *)(*(_QWORD *)v16 + 56LL);
      if ( v8[2] - (_QWORD)*v14 == a3 && !memcmp_0(*v14, a2, a3) )
        break;
      v8 += 16;
    }
    *(_OWORD *)&v31[1] = 0;
    v32 = 0;
    v30 = WORD4(v37);
    std::vector<unsigned char>::insert<unsigned char *,0>(
      (unsigned int)&v31[1],
      (unsigned int)&v33,
      0,
      (unsigned int)&v30,
      (__int64)v31);
    v19 = *(__int64 **)v37;
    while ( !*((_BYTE *)v19 + 25) )
    {
      *(_QWORD *)&UnicodeString.Length = 0x2000000;
      UnicodeString.Buffer = (PWSTR)&v44;
      RtlConvertSidToUnicodeString(&UnicodeString, (PSID)v19[4], 0);
      Length = UnicodeString.Length;
      std::vector<unsigned char>::insert<unsigned char *,0>(
        (unsigned int)&v31[1],
        (unsigned int)&v41,
        *(_DWORD *)&v31[5],
        (unsigned int)&Length,
        (__int64)v29);
      std::vector<unsigned char>::insert<unsigned char *,0>(
        (unsigned int)&v31[1],
        (unsigned int)&v42,
        *(_DWORD *)&v31[5],
        UnicodeString.Buffer,
        (__int64)UnicodeString.Buffer + Length);
      v33 = *((_DWORD *)v19 + 14);
      std::vector<unsigned char>::insert<unsigned char *,0>(
        (unsigned int)&v31[1],
        (unsigned int)&v43,
        *(_DWORD *)&v31[5],
        (unsigned int)&v33,
        (__int64)v34);
      j = (__int64 *)v19[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( i = (__int64 *)v19[1]; !*((_BYTE *)i + 25) && v19 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v19 = i;
        v19 = i;
      }
      else
      {
        v19 = (__int64 *)v19[2];
        for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v19 = j;
      }
    }
    v21 = *(_OWORD *)&v31[1];
    if ( BioIsoProvider::IsEnabled((unsigned __int8)j, v17) )
    {
      BioIsoProvider::Instance();
      BioIsoProvider::SecureEnrollmentDatabaseUserInfo_(v22, (const unsigned __int8 *)v21, *((_QWORD *)&v21 + 1) - v21);
    }
    std::vector<unsigned char>::_Tidy((__int64)&v31[1]);
    std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,unsigned __int64,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::vector<unsigned char>,unsigned __int64,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,unsigned __int64>>,0>>(&v37);
    v5 = v39;
  }
  else
  {
    v24 = v9;
    v25 = (_QWORD *)*v9;
    while ( 1 )
    {
      v9 = v24;
      if ( v8 == v25 )
        break;
      v26 = (const void *)v8[1];
      if ( v8[2] - (_QWORD)v26 == a3 && !memcmp_0(v26, a2, a3) )
        goto LABEL_30;
      v8 += 16;
    }
  }
  if ( v8 == (_QWORD *)*v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
      (const char *)0x8009801FLL,
      v27);
    return 2148106271LL;
  }
  else
  {
LABEL_30:
    UnicodeString = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    *(_OWORD *)&v31[1] = 0;
    v32 = 0;
    std::vector<unsigned char>::operator=(v5, v8 + 4);
    std::vector<unsigned char>::operator=(v40, v8 + 7);
    std::vector<unsigned char>::_Tidy((__int64)&v31[1]);
    std::vector<unsigned char>::_Tidy((__int64)&v37);
    std::vector<unsigned char>::_Tidy((__int64)&UnicodeString);
    return 0;
  }
}

```

## disassembly

```asm
0x14006165c  mov     [rsp-8+arg_8], rbx
0x140061661  push    rbp
0x140061662  push    rsi
0x140061663  push    rdi
0x140061664  push    r12
0x140061666  push    r13
0x140061668  push    r14
0x14006166a  push    r15
0x14006166c  lea     rbp, [rsp-1C0h]
0x140061674  sub     rsp, 2C0h
0x14006167b  mov     rax, cs:__security_cookie
0x140061682  xor     rax, rsp
0x140061685  mov     [rbp+1F0h+var_40], rax
0x14006168c  mov     r13, r9
0x14006168f  mov     [rbp+1F0h+var_268], r9
0x140061693  mov     r14, r8
0x140061696  mov     r12, rdx
0x140061699  mov     rax, [rbp+1F0h+arg_20]
0x1400616a0  mov     [rbp+1F0h+var_260], rax
0x1400616a4  mov     rbx, [rcx+20h]
0x1400616a8  lea     rsi, [rcx+28h]
0x1400616ac  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>>(void)
0x1400616b1  xor     r15d, r15d
0x1400616b4  test    al, al
0x1400616b6  jz      loc_140061910
0x1400616bc  xorps   xmm0, xmm0
0x1400616bf  movdqu  [rsp+2F0h+var_280], xmm0
0x1400616c5  lea     ecx, [r15+40h]; Size
0x1400616c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400616ce  mov     [rax], rax
0x1400616d1  mov     [rax+8], rax
0x1400616d5  mov     [rax+10h], rax
0x1400616d9  mov     word ptr [rax+18h], 101h
0x1400616df  mov     qword ptr [rsp+2F0h+var_280], rax
0x1400616e4  cmp     rbx, [rsi]
0x1400616e7  jz      short loc_140061751
0x1400616e9  mov     r13, [rbx+20h]
0x1400616ed  lea     rdi, [rbx+8]
0x1400616f1  call    ?IsEnabled@BioIsoProvider@@SA_NE_K@Z; BioIsoProvider::IsEnabled(uchar,unsigned __int64)
0x1400616f6  test    al, al
0x1400616f8  jz      short loc_14006170E
0x1400616fa  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400616ff  lea     r9, [rbx+38h]
0x140061703  mov     r8, r13
0x140061706  mov     rdx, rdi
0x140061709  call    ?SecureEnrollmentDatabaseEntry_@BioIsoProvider@@QEAAXPEBV?$vector@EV?$allocator@E@std@@@std@@PEBU_SID@@0@Z; BioIsoProvider::SecureEnrollmentDatabaseEntry_(std::vector<uchar> const *,_SID const *,std::vector<uchar> const *)
0x14006170e  lea     r8, [rbx+20h]
0x140061712  lea     rdx, [rsp+2F0h+UnicodeString]
0x140061717  lea     rcx, [rsp+2F0h+var_280]
0x14006171c  call    ??$_Try_emplace@AEBV?$vector@EV?$allocator@E@std@@@std@@$$V@?$map@V?$vector@EV?$allocator@E@std@@@std@@_KU?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@PEAX@std@@_N@1@AEBV?$vector@EV?$allocator@E@std@@@1@@Z; std::map<std::vector<uchar>,unsigned __int64>::_Try_emplace<std::vector<uchar> const &,>(std::vector<uchar> const &)
0x140061721  mov     rcx, [rax]
0x140061724  inc     qword ptr [rcx+38h]
0x140061728  mov     rax, [rbx+10h]
0x14006172c  sub     rax, [rdi]
0x14006172f  cmp     rax, r14
0x140061732  jnz     loc_140061859
0x140061738  mov     r8, r14; Size
0x14006173b  mov     rdx, r12; Buf2
0x14006173e  mov     rcx, [rdi]; Buf1
0x140061741  call    memcmp_0
0x140061746  xor     r15d, r15d
0x140061749  test    eax, eax
0x14006174b  jnz     loc_14006185C
0x140061751  xorps   xmm0, xmm0
0x140061754  movdqu  xmmword ptr [rsp+2F0h+var_2BA+2], xmm0
0x14006175a  mov     [rsp+2F0h+var_2A8], r15
0x14006175f  movzx   eax, word ptr [rsp+2F0h+var_280+8]
0x140061764  mov     [rsp+2F0h+var_2BC], ax
0x140061769  xor     r8d, r8d
0x14006176c  lea     rax, [rsp+2F0h+var_2BA]
0x140061771  mov     qword ptr [rsp+2F0h+var_2D0], rax; int
0x140061776  lea     r9, [rsp+2F0h+var_2BC]
0x14006177b  lea     rdx, [rsp+2F0h+var_2A0]
0x140061780  lea     rcx, [rsp+2F0h+var_2BA+2]
0x140061785  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x14006178a  mov     rdi, qword ptr [rsp+2F0h+var_280]
0x14006178f  mov     rdi, [rdi]
0x140061792  cmp     [rdi+19h], r15b
0x140061796  jnz     loc_1400618A4
0x14006179c  xorps   xmm0, xmm0
0x14006179f  movups  xmmword ptr [rsp+2F0h+UnicodeString.Length], xmm0
0x1400617a4  mov     eax, 200h
0x1400617a9  mov     [rsp+2F0h+UnicodeString.MaximumLength], ax
0x1400617ae  lea     rax, [rbp+1F0h+var_240]
0x1400617b2  mov     [rsp+2F0h+UnicodeString.Buffer], rax
0x1400617b7  xor     r8d, r8d; AllocateDestinationString
0x1400617ba  mov     rdx, [rdi+20h]; Sid
0x1400617be  lea     rcx, [rsp+2F0h+UnicodeString]; UnicodeString
0x1400617c3  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400617ca  nop     dword ptr [rax+rax+00h]
0x1400617cf  movzx   eax, [rsp+2F0h+UnicodeString.Length]
0x1400617d4  mov     [rsp+2F0h+var_2C0], ax
0x1400617d9  lea     rax, [rsp+2F0h+var_2BE]
0x1400617de  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x1400617e3  lea     r9, [rsp+2F0h+var_2C0]
0x1400617e8  mov     r8, qword ptr [rsp+2F0h+var_2BA+0Ah]
0x1400617ed  lea     rdx, [rbp+1F0h+var_258]
0x1400617f1  lea     rcx, [rsp+2F0h+var_2BA+2]
0x1400617f6  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x1400617fb  movzx   eax, [rsp+2F0h+var_2C0]
0x140061800  mov     r9, [rsp+2F0h+UnicodeString.Buffer]
0x140061805  add     rax, r9
0x140061808  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x14006180d  mov     r8, qword ptr [rsp+2F0h+var_2BA+0Ah]
0x140061812  lea     rdx, [rbp+1F0h+var_250]
0x140061816  lea     rcx, [rsp+2F0h+var_2BA+2]
0x14006181b  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x140061820  mov     eax, [rdi+38h]
0x140061823  mov     [rsp+2F0h+var_2A0], eax
0x140061827  lea     rax, [rsp+2F0h+var_29C]
0x14006182c  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x140061831  lea     r9, [rsp+2F0h+var_2A0]
0x140061836  mov     r8, qword ptr [rsp+2F0h+var_2BA+0Ah]
0x14006183b  lea     rdx, [rbp+1F0h+var_248]
0x14006183f  lea     rcx, [rsp+2F0h+var_2BA+2]
0x140061844  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x140061849  mov     rcx, [rdi+10h]
0x14006184d  cmp     [rcx+19h], r15b
0x140061851  jz      short loc_140061880
0x140061853  mov     rax, [rdi+8]
0x140061857  jmp     short loc_140061872
0x140061859  xor     r15d, r15d
0x14006185c  sub     rbx, 0FFFFFFFFFFFFFF80h
0x140061860  jmp     loc_1400616E4
0x140061865  cmp     rdi, [rax+10h]
0x140061869  jnz     short loc_140061878
0x14006186b  mov     rdi, rax
0x14006186e  mov     rax, [rax+8]
0x140061872  cmp     [rax+19h], r15b
0x140061876  jz      short loc_140061865
0x140061878  mov     rdi, rax
0x14006187b  jmp     loc_140061792
0x140061880  mov     rdi, rcx
0x140061883  mov     rcx, [rcx]
0x140061886  cmp     [rcx+19h], r15b
0x14006188a  jnz     loc_140061792
0x140061890  mov     rdi, rcx
0x140061893  mov     rax, [rcx]
0x140061896  mov     rcx, rax
0x140061899  cmp     [rax+19h], r15b
0x14006189d  jz      short loc_140061890
0x14006189f  jmp     loc_140061792
0x1400618a4  mov     r14, qword ptr [rsp+2F0h+var_2BA+2]
0x1400618a9  mov     rdi, qword ptr [rsp+2F0h+var_2BA+0Ah]
0x1400618ae  call    ?IsEnabled@BioIsoProvider@@SA_NE_K@Z; BioIsoProvider::IsEnabled(uchar,unsigned __int64)
0x1400618b3  test    al, al
0x1400618b5  jz      short loc_1400618CB
0x1400618b7  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400618bc  sub     rdi, r14
0x1400618bf  mov     r8, rdi; unsigned __int64
0x1400618c2  mov     rdx, r14; unsigned __int8 *
0x1400618c5  call    ?SecureEnrollmentDatabaseUserInfo_@BioIsoProvider@@QEAAXPEBE_K@Z; BioIsoProvider::SecureEnrollmentDatabaseUserInfo_(uchar const *,unsigned __int64)
0x1400618ca  nop
0x1400618cb  lea     rcx, [rsp+2F0h+var_2BA+2]
0x1400618d0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400618d5  nop
0x1400618d6  lea     rcx, [rsp+2F0h+var_280]
0x1400618db  call    ??1?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@_KU?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::vector<uchar>,unsigned __int64,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::vector<uchar>,unsigned __int64,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,unsigned __int64>>,0>>(void)
0x1400618e0  mov     r13, [rbp+1F0h+var_268]
0x1400618e4  cmp     rbx, [rsi]
0x1400618e7  jnz     short loc_140061943
0x1400618e9  mov     rcx, [rbp+1F8h]; this
0x1400618f0  mov     ebx, 8009801Fh
0x1400618f5  mov     r9d, ebx; char *
0x1400618f8  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x1400618ff  mov     edx, 329h; void *
0x140061904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140061909  mov     eax, ebx
0x14006190b  jmp     loc_1400619A4
0x140061910  mov     rdi, rsi
0x140061913  mov     r15, [rsi]
0x140061916  mov     rsi, rdi
0x140061919  cmp     rbx, r15
0x14006191c  jz      short loc_1400618E4
0x14006191e  mov     rcx, [rbx+8]; Buf1
0x140061922  mov     rax, [rbx+10h]
0x140061926  sub     rax, rcx
0x140061929  cmp     rax, r14
0x14006192c  jnz     short loc_14006193D
0x14006192e  mov     r8, r14; Size
0x140061931  mov     rdx, r12; Buf2
0x140061934  call    memcmp_0
0x140061939  test    eax, eax
0x14006193b  jz      short loc_140061943
0x14006193d  sub     rbx, 0FFFFFFFFFFFFFF80h
0x140061941  jmp     short loc_140061916
0x140061943  xorps   xmm0, xmm0
0x140061946  movdqu  xmmword ptr [rsp+2F0h+UnicodeString.Length], xmm0
0x14006194c  xor     eax, eax
0x14006194e  mov     [rsp+2F0h+var_288], rax
0x140061953  movdqu  [rsp+2F0h+var_280], xmm0
0x140061959  mov     [rbp+1F0h+var_270], rax
0x14006195d  movdqu  xmmword ptr [rsp+2F0h+var_2BA+2], xmm0
0x140061963  mov     [rsp+2F0h+var_2A8], rax
0x140061968  lea     rdx, [rbx+20h]
0x14006196c  mov     rcx, r13
0x14006196f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x140061974  lea     rdx, [rbx+38h]
0x140061978  mov     rcx, [rbp+1F0h+var_260]
0x14006197c  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x140061981  nop
0x140061982  lea     rcx, [rsp+2F0h+var_2BA+2]
0x140061987  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14006198c  nop
0x14006198d  lea     rcx, [rsp+2F0h+var_280]
0x140061992  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140061997  nop
0x140061998  lea     rcx, [rsp+2F0h+UnicodeString]
0x14006199d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400619a2  xor     eax, eax
0x1400619a4  mov     rcx, [rbp+1F0h+var_40]
0x1400619ab  xor     rcx, rsp; StackCookie
0x1400619ae  call    __security_check_cookie
0x1400619b3  mov     rbx, [rsp+2F0h+arg_8]
0x1400619bb  add     rsp, 2C0h
0x1400619c2  pop     r15
0x1400619c4  pop     r14
0x1400619c6  pop     r13
0x1400619c8  pop     r12
0x1400619ca  pop     rdi
0x1400619cb  pop     rsi
0x1400619cc  pop     rbp
0x1400619cd  retn
```
