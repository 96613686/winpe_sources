# Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector(bool)

- ea: `0x180094fa4`
- end: `0x1800955cd`
- name: `?UpdateAllAttributesVector@CAttributeValueCollection@Implementation@Rtl@Identity@Windows@@AEAAJ_N@Z`
- size: `1577`
- prototype: `__int64 __fastcall(Windows::Identity::Rtl::Implementation::CAttributeValueCollection *__hidden this, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1800948bc`

## callees

- `0x18000f0ec`
- `0x1800105c4`
- `0x18001f554`
- `0x18001fd10`
- `0x1800293a0`
- `0x1800661b0`
- `0x180091474`
- `0x180093d30`
- `0x180093dbc`
- `0x180094784`
- `0x180094fa4`
- `0x180095c30`
- `0x180099334`
- `0x180099838`

## string_xrefs

- `0x18009506e`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x180095208`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x1800952e7`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x1800953ca`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x180095472`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x1800952f2`: `Pool.Allocate(&PublicKeyTokenInString)`

## pseudocode

```c
__int64 __fastcall Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector(
        Windows::Identity::Rtl::Implementation::CAttributeValueCollection *this,
        char a2)
{
  bool v2; // zf
  char v3; // si
  __int64 v5; // rcx
  char *v6; // r13
  unsigned __int64 valid; // r12
  __int64 v8; // rax
  int v9; // esi
  const char **v10; // rdx
  __int64 *v11; // r8
  __int64 v12; // r15
  unsigned __int64 v13; // rdi
  __int64 *v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // ecx
  __int64 *v30; // rcx
  __int64 v31; // r12
  __int64 v33; // rax
  __int64 v34; // rax
  __int128 v35; // xmm0
  __int64 v37; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v38; // [rsp+30h] [rbp-D0h] BYREF
  const char *v39; // [rsp+40h] [rbp-C0h] BYREF
  const char *v40; // [rsp+48h] [rbp-B8h]
  __int64 v41; // [rsp+50h] [rbp-B0h]
  const char *v42; // [rsp+58h] [rbp-A8h]
  _QWORD v43[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v44[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v45[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v46[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v47; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v48[4]; // [rsp+E8h] [rbp-18h] BYREF

  v2 = (*(_BYTE *)this & 8) == 0;
  v47 = 0;
  v3 = a2;
  if ( !v2 )
    return 0;
  v5 = *((unsigned int *)this + 4);
  v48[0] = v48;
  v48[1] = v48;
  v48[2] = v48;
  v48[3] = 0;
  v38 = 0u;
  v6 = (char *)this + 12;
  valid = CountValidAttributes(v5);
  if ( v3 )
  {
    v8 = CountValidAttributes(*(unsigned int *)v6);
    if ( v8 + valid < valid )
    {
      v9 = -1073741675;
LABEL_79:
      Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v38);
      Windows::WCP::Implementation::CAllocationPool::~CAllocationPool((Windows::WCP::Implementation::CAllocationPool *)v48);
      return (unsigned int)v9;
    }
    valid += v8;
  }
  if ( !Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(
          &v38,
          valid) )
  {
    v41 = 232;
    v39 = "onecore\\base\\wcp\\identity\\attribute_value_collection.cpp";
    v10 = &v39;
    v40 = "Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector";
    v42 = "AllAttributes.Allocate(cTotalAttributes)";
LABEL_8:
    v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v47,
           v10);
    goto LABEL_79;
  }
  v11 = g_LUNICODE_STRING_Neutral;
  v12 = v38;
  v13 = 0;
  if ( (*((_BYTE *)this + 16) & 1) != 0 )
  {
    v14 = (__int64 *)((char *)this + 88);
    if ( this == (Windows::Identity::Rtl::Implementation::CAttributeValueCollection *)-88LL )
      goto LABEL_17;
  }
  else
  {
    if ( !v3 || (*v6 & 1) == 0 )
      goto LABEL_17;
    v14 = g_LUNICODE_STRING_Neutral;
  }
  if ( !valid )
    goto LABEL_87;
  *(_QWORD *)v38 = 0;
  *(_QWORD *)(v12 + 8) = g_LUNICODE_STRING_Name;
  v13 = 1;
  *(_QWORD *)(v12 + 16) = v14;
LABEL_17:
  if ( (*((_BYTE *)this + 16) & 8) != 0 )
  {
    v15 = (__int64 *)((char *)this + 136);
    if ( this == (Windows::Identity::Rtl::Implementation::CAttributeValueCollection *)-136LL )
      goto LABEL_25;
  }
  else
  {
    if ( !v3 || (*v6 & 8) == 0 )
      goto LABEL_25;
    v15 = g_LUNICODE_STRING_neutral;
  }
  if ( v13 >= valid )
    goto LABEL_87;
  v16 = 3 * v13++;
  *(_QWORD *)(v12 + 8 * v16) = 0;
  *(_QWORD *)(v12 + 8 * v16 + 8) = g_LUNICODE_STRING_Culture;
  *(_QWORD *)(v12 + 8 * v16 + 16) = v15;
LABEL_25:
  if ( *((char *)this + 16) >= 0 )
  {
    if ( !v3 || *v6 >= 0 )
      goto LABEL_33;
    v17 = g_LUNICODE_STRING_Neutral;
  }
  else
  {
    v17 = (__int64 *)((char *)this + 184);
    if ( this == (Windows::Identity::Rtl::Implementation::CAttributeValueCollection *)-184LL )
      goto LABEL_33;
  }
  if ( v13 >= valid )
    goto LABEL_87;
  v18 = 3 * v13++;
  *(_QWORD *)(v12 + 8 * v18) = 0;
  *(_QWORD *)(v12 + 8 * v18 + 8) = g_LUNICODE_STRING_TypeName;
  *(_QWORD *)(v12 + 8 * v18 + 16) = v17;
LABEL_33:
  if ( (*((_BYTE *)this + 16) & 0x20) != 0 )
  {
    v19 = (__int64 *)((char *)this + 160);
    if ( this == (Windows::Identity::Rtl::Implementation::CAttributeValueCollection *)-160LL )
      goto LABEL_41;
  }
  else
  {
    if ( !v3 || (*v6 & 0x20) == 0 )
      goto LABEL_41;
    v19 = g_LUNICODE_STRING_Neutral;
  }
  if ( v13 >= valid )
    goto LABEL_87;
  v20 = 3 * v13++;
  *(_QWORD *)(v12 + 8 * v20) = 0;
  *(_QWORD *)(v12 + 8 * v20 + 8) = g_LUNICODE_STRING_Type;
  *(_QWORD *)(v12 + 8 * v20 + 16) = v19;
LABEL_41:
  if ( (*((_BYTE *)this + 16) & 4) != 0 )
  {
    v37 = 0;
    if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(
            v48,
            &v37,
            g_LUNICODE_STRING_Neutral) )
    {
      v43[2] = 303;
      v43[0] = "onecore\\base\\wcp\\identity\\attribute_value_collection.cpp";
      v10 = (const char **)v43;
      v43[1] = "Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector";
      v43[3] = "Pool.Allocate(&VersionInString)";
      goto LABEL_8;
    }
    v9 = Windows::WCP::Implementation::Rtl::FormatFourPartVersion(v21, (char *)this + 40, v37);
    if ( v9 < 0 )
      goto LABEL_79;
    if ( v13 >= valid )
      goto LABEL_87;
    v3 = a2;
    v22 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v22) = 0;
    *(_QWORD *)(v12 + 8 * v22 + 8) = g_LUNICODE_STRING_Version;
    v11 = g_LUNICODE_STRING_Neutral;
    *(_QWORD *)(v12 + 8 * v22 + 16) = v37;
    goto LABEL_51;
  }
  if ( v3 && (*v6 & 4) != 0 )
  {
    if ( v13 >= valid )
      goto LABEL_87;
    v23 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v23) = 0;
    *(_QWORD *)(v12 + 8 * v23 + 8) = g_LUNICODE_STRING_Version;
    *(_QWORD *)(v12 + 8 * v23 + 16) = g_LUNICODE_STRING_Neutral;
LABEL_51:
    ++v13;
  }
  if ( (*((_BYTE *)this + 16) & 2) != 0 )
  {
    v37 = 0;
    if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(
            v48,
            &v37,
            g_LUNICODE_STRING_Neutral) )
    {
      v44[2] = 325;
      v44[0] = "onecore\\base\\wcp\\identity\\attribute_value_collection.cpp";
      v10 = (const char **)v44;
      v44[1] = "Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector";
      v44[3] = "Pool.Allocate(&PublicKeyTokenInString)";
      goto LABEL_8;
    }
    v39 = (const char *)*((_QWORD *)this + 16);
    v40 = (const char *)*((_QWORD *)this + 14);
    v9 = Windows::WCP::Implementation::Rtl::FormatBytesIntoStringWithAllocate<_LUNICODE_STRING>(v24, &v39, v37);
    if ( v9 < 0 )
      goto LABEL_79;
    v3 = a2;
    v25 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v25) = 0;
    *(_QWORD *)(v12 + 8 * v25 + 8) = g_LUNICODE_STRING_PublicKeyToken;
    *(_QWORD *)(v12 + 8 * v25 + 16) = v37;
LABEL_61:
    ++v13;
    goto LABEL_62;
  }
  if ( v3 && (*v6 & 2) != 0 )
  {
    if ( v13 >= valid )
      goto LABEL_87;
    v26 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v26) = 0;
    *(_QWORD *)(v12 + 8 * v26 + 8) = g_LUNICODE_STRING_PublicKeyToken;
    *(_QWORD *)(v12 + 8 * v26 + 16) = g_LUNICODE_STRING_Neutral;
    goto LABEL_61;
  }
LABEL_62:
  if ( (*((_BYTE *)this + 16) & 0x10) != 0 )
  {
    v37 = 0;
    if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(v48, &v37, v11) )
    {
      v45[2] = 348;
      v45[0] = "onecore\\base\\wcp\\identity\\attribute_value_collection.cpp";
      v10 = (const char **)v45;
      v45[1] = "Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector";
      v45[3] = "Pool.Allocate(&ProcArchInString)";
      goto LABEL_8;
    }
    v9 = Windows::Identity::Rtl::Implementation::FormatProcessorArchitecture((char *)this + 56, v37);
    if ( v9 < 0 )
      goto LABEL_79;
    v3 = a2;
    v27 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v27) = 0;
    *(_QWORD *)(v12 + 8 * v27 + 8) = g_LUNICODE_STRING_ProcessorArchitecture;
    ++v13;
    *(_QWORD *)(v12 + 8 * v27 + 16) = v37;
  }
  else if ( v3 && (*v6 & 0x10) != 0 )
  {
    if ( v13 >= valid )
      goto LABEL_87;
    v28 = 3 * v13++;
    *(_QWORD *)(v12 + 8 * v28) = 0;
    *(_QWORD *)(v12 + 8 * v28 + 8) = g_LUNICODE_STRING_ProcessorArchitecture;
    *(_QWORD *)(v12 + 8 * v28 + 16) = g_LUNICODE_STRING_Neutral;
  }
  if ( (*((_DWORD *)this + 4) & 0x100) != 0 )
  {
    v37 = 0;
    if ( !Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(
            v48,
            &v37,
            g_LUNICODE_STRING_Neutral) )
    {
      v46[2] = 367;
      v46[0] = "onecore\\base\\wcp\\identity\\attribute_value_collection.cpp";
      v10 = (const char **)v46;
      v46[1] = "Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector";
      v46[3] = "Pool.Allocate(&ProcArchInString)";
      goto LABEL_8;
    }
    v29 = *((_DWORD *)this + 20);
    if ( !v29 )
    {
      v30 = g_LUNICODE_STRING_neutral;
      goto LABEL_78;
    }
    if ( v29 == 1 )
    {
      v30 = g_LUNICODE_STRING_NonSxS;
LABEL_78:
      v31 = v37;
      v9 = RtlDuplicateLUnicodeString(v30, v37);
      if ( v9 < 0 )
        goto LABEL_79;
      v33 = 3 * v13;
      *(_QWORD *)(v12 + 8 * v33) = 0;
      *(_QWORD *)(v12 + 8 * v33 + 8) = g_LUNICODE_STRING_VersionScope;
      *(_QWORD *)(v12 + 8 * v33 + 16) = v31;
      goto LABEL_85;
    }
LABEL_87:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800955CCLL);
  }
  if ( v3 && (*(_DWORD *)v6 & 0x100) != 0 )
  {
    if ( v13 >= valid )
      goto LABEL_87;
    v34 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v34) = 0;
    *(_QWORD *)(v12 + 8 * v34 + 8) = g_LUNICODE_STRING_VersionScope;
    *(_QWORD *)(v12 + 8 * v34 + 16) = g_LUNICODE_STRING_Neutral;
  }
LABEL_85:
  v35 = v38;
  v38 = *(_OWORD *)((char *)this + 360);
  *(_OWORD *)((char *)this + 360) = v35;
  Windows::WCP::Implementation::CAllocationPool::Swap(
    (Windows::Identity::Rtl::Implementation::CAttributeValueCollection *)((char *)this + 328),
    (struct Windows::WCP::Implementation::CAllocationPool *)v48);
  *(_DWORD *)this |= 8u;
  Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v38);
  Windows::WCP::Implementation::CAllocationPool::~CAllocationPool((Windows::WCP::Implementation::CAllocationPool *)v48);
  return 0;
}

```

## disassembly

```asm
0x180094fa4  push    rbp
0x180094fa6  push    rbx
0x180094fa7  push    rsi
0x180094fa8  push    rdi
0x180094fa9  push    r12
0x180094fab  push    r13
0x180094fad  push    r14
0x180094faf  push    r15
0x180094fb1  lea     rbp, [rsp-18h]
0x180094fb6  sub     rsp, 118h
0x180094fbd  mov     rax, cs:__security_cookie
0x180094fc4  xor     rax, rsp
0x180094fc7  mov     [rbp+50h+var_48], rax
0x180094fcb  xor     r9d, r9d
0x180094fce  mov     [rsp+150h+var_130], dl
0x180094fd2  test    byte ptr [rcx], 8
0x180094fd5  mov     ebx, r9d
0x180094fd8  mov     [rbp+50h+var_70], ebx
0x180094fdb  mov     sil, dl
0x180094fde  mov     r14, rcx
0x180094fe1  jnz     loc_18009559F
0x180094fe7  mov     ecx, [rcx+10h]
0x180094fea  lea     rax, [rbp+50h+var_68]
0x180094fee  mov     [rbp+50h+var_68], rax
0x180094ff2  lea     rax, [rbp+50h+var_68]
0x180094ff6  mov     [rbp+50h+var_60], rax
0x180094ffa  lea     rax, [rbp+50h+var_68]
0x180094ffe  mov     [rbp+50h+var_58], rax
0x180095002  mov     [rbp+50h+var_50], r9
0x180095006  mov     qword ptr [rsp+150h+var_120], r9
0x18009500b  mov     qword ptr [rsp+150h+var_120+8], r9
0x180095010  call    CountValidAttributes
0x180095015  lea     r13, [r14+0Ch]
0x180095019  mov     r12, rax
0x18009501c  test    sil, sil
0x18009501f  jz      short loc_180095040
0x180095021  mov     ecx, [r13+0]
0x180095025  call    CountValidAttributes
0x18009502a  lea     rcx, [rax+r12]
0x18009502e  cmp     rcx, r12
0x180095031  jnb     short loc_18009503D
0x180095033  mov     esi, 0C0000095h
0x180095038  jmp     loc_1800954FE
0x18009503d  mov     r12, rcx
0x180095040  mov     rdx, r12
0x180095043  lea     rcx, [rsp+150h+var_120]
0x180095048  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@V?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@2@@Windows@@QEAAPEAU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(unsigned __int64)
0x18009504d  xor     edx, edx
0x18009504f  test    rax, rax
0x180095052  jnz     short loc_180095096
0x180095054  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x18009505b  mov     [rsp+150h+var_100], 0E8h
0x180095064  mov     [rsp+150h+var_110], rax
0x180095069  lea     rdx, [rsp+150h+var_110]
0x18009506e  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x180095075  mov     [rsp+150h+var_108], rax
0x18009507a  lea     rax, aAllattributesA; "AllAttributes.Allocate(cTotalAttributes"...
0x180095081  mov     [rsp+150h+var_F8], rax
0x180095086  lea     rcx, [rbp+50h+var_70]
0x18009508a  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18009508f  mov     esi, eax
0x180095091  jmp     loc_1800954FE
0x180095096  test    byte ptr [r14+10h], 1
0x18009509b  lea     r8, g_LUNICODE_STRING_Neutral
0x1800950a2  mov     r15, qword ptr [rsp+150h+var_120]
0x1800950a7  mov     rdi, rdx
0x1800950aa  jz      short loc_1800950B7
0x1800950ac  lea     rax, [r14+58h]
0x1800950b0  test    rax, rax
0x1800950b3  jz      short loc_1800950E6
0x1800950b5  jmp     short loc_1800950C6
0x1800950b7  test    sil, sil
0x1800950ba  jz      short loc_1800950E6
0x1800950bc  test    byte ptr [r13+0], 1
0x1800950c1  jz      short loc_1800950E6
0x1800950c3  mov     rax, r8
0x1800950c6  test    r12, r12
0x1800950c9  jz      loc_1800955C2
0x1800950cf  mov     [r15], rdx
0x1800950d2  lea     rcx, g_LUNICODE_STRING_Name
0x1800950d9  mov     [r15+8], rcx
0x1800950dd  mov     edi, 1
0x1800950e2  mov     [r15+10h], rax
0x1800950e6  test    byte ptr [r14+10h], 8
0x1800950eb  jz      short loc_1800950FB
0x1800950ed  lea     rcx, [r14+88h]
0x1800950f4  test    rcx, rcx
0x1800950f7  jz      short loc_180095135
0x1800950f9  jmp     short loc_18009510E
0x1800950fb  test    sil, sil
0x1800950fe  jz      short loc_180095135
0x180095100  test    byte ptr [r13+0], 8
0x180095105  jz      short loc_180095135
0x180095107  lea     rcx, g_LUNICODE_STRING_neutral
0x18009510e  cmp     rdi, r12
0x180095111  jnb     loc_1800955C2
0x180095117  lea     rax, [rdi+rdi*2]
0x18009511b  inc     rdi
0x18009511e  mov     [r15+rax*8], rdx
0x180095122  lea     rdx, g_LUNICODE_STRING_Culture
0x180095129  mov     [r15+rax*8+8], rdx
0x18009512e  xor     edx, edx
0x180095130  mov     [r15+rax*8+10h], rcx
0x180095135  test    byte ptr [r14+10h], 80h
0x18009513a  jz      short loc_18009514A
0x18009513c  lea     rcx, [r14+0B8h]
0x180095143  test    rcx, rcx
0x180095146  jz      short loc_180095180
0x180095148  jmp     short loc_180095159
0x18009514a  test    sil, sil
0x18009514d  jz      short loc_180095180
0x18009514f  test    byte ptr [r13+0], 80h
0x180095154  jz      short loc_180095180
0x180095156  mov     rcx, r8
0x180095159  cmp     rdi, r12
0x18009515c  jnb     loc_1800955C2
0x180095162  lea     rax, [rdi+rdi*2]
0x180095166  inc     rdi
0x180095169  mov     [r15+rax*8], rdx
0x18009516d  lea     rdx, g_LUNICODE_STRING_TypeName
0x180095174  mov     [r15+rax*8+8], rdx
0x180095179  xor     edx, edx
0x18009517b  mov     [r15+rax*8+10h], rcx
0x180095180  test    byte ptr [r14+10h], 20h
0x180095185  jz      short loc_180095195
0x180095187  lea     rcx, [r14+0A0h]
0x18009518e  test    rcx, rcx
0x180095191  jz      short loc_1800951CB
0x180095193  jmp     short loc_1800951A4
0x180095195  test    sil, sil
0x180095198  jz      short loc_1800951CB
0x18009519a  test    byte ptr [r13+0], 20h
0x18009519f  jz      short loc_1800951CB
0x1800951a1  mov     rcx, r8
0x1800951a4  cmp     rdi, r12
0x1800951a7  jnb     loc_1800955C2
0x1800951ad  lea     rax, [rdi+rdi*2]
0x1800951b1  inc     rdi
0x1800951b4  mov     [r15+rax*8], rdx
0x1800951b8  lea     rdx, g_LUNICODE_STRING_Type
0x1800951bf  mov     [r15+rax*8+8], rdx
0x1800951c4  xor     edx, edx
0x1800951c6  mov     [r15+rax*8+10h], rcx
0x1800951cb  test    byte ptr [r14+10h], 4
0x1800951d0  jz      loc_18009527C
0x1800951d6  mov     [rsp+150h+var_128], rdx
0x1800951db  lea     rcx, [rbp+50h+var_68]
0x1800951df  lea     rdx, [rsp+150h+var_128]
0x1800951e4  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x1800951e9  test    rax, rax
0x1800951ec  jnz     short loc_180095225
0x1800951ee  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x1800951f5  mov     [rsp+150h+var_E0], 12Fh
0x1800951fe  mov     [rsp+150h+var_F0], rax
0x180095203  lea     rdx, [rsp+150h+var_F0]
0x180095208  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x18009520f  mov     [rsp+150h+var_E8], rax
0x180095214  lea     rax, aPoolAllocateVe; "Pool.Allocate(&VersionInString)"
0x18009521b  mov     [rsp+150h+var_D8], rax
0x180095220  jmp     loc_180095086
0x180095225  mov     rax, [rsp+150h+var_128]
0x18009522a  lea     rdx, [r14+28h]
0x18009522e  mov     r8, rax
0x180095231  mov     [rsp+150h+var_128], rax
0x180095236  call    ?FormatFourPartVersion@Rtl@Implementation@WCP@Windows@@YAJKPEBT_FOUR_PART_VERSION@@PEAV?$Auto@U_LUNICODE_STRING@@@4@@Z; Windows::WCP::Implementation::Rtl::FormatFourPartVersion(ulong,_FOUR_PART_VERSION const *,Windows::Auto<_LUNICODE_STRING> *)
0x18009523b  xor     edx, edx
0x18009523d  mov     esi, eax
0x18009523f  test    eax, eax
0x180095241  js      loc_1800954FE
0x180095247  cmp     rdi, r12
0x18009524a  jnb     loc_1800955C2
0x180095250  mov     sil, [rsp+150h+var_130]
0x180095255  lea     rax, [rdi+rdi*2]
0x180095259  mov     [r15+rax*8], rdx
0x18009525d  lea     rcx, g_LUNICODE_STRING_Version
0x180095264  mov     [r15+rax*8+8], rcx
0x180095269  lea     r8, g_LUNICODE_STRING_Neutral
0x180095270  mov     rcx, [rsp+150h+var_128]
0x180095275  mov     [r15+rax*8+10h], rcx
0x18009527a  jmp     short loc_1800952AA
0x18009527c  test    sil, sil
0x18009527f  jz      short loc_1800952AD
0x180095281  test    byte ptr [r13+0], 4
0x180095286  jz      short loc_1800952AD
0x180095288  cmp     rdi, r12
0x18009528b  jnb     loc_1800955C2
0x180095291  lea     rax, [rdi+rdi*2]
0x180095295  mov     [r15+rax*8], rdx
0x180095299  lea     rcx, g_LUNICODE_STRING_Version
0x1800952a0  mov     [r15+rax*8+8], rcx
0x1800952a5  mov     [r15+rax*8+10h], r8
0x1800952aa  inc     rdi
0x1800952ad  test    byte ptr [r14+10h], 2
0x1800952b2  jz      loc_18009535F
0x1800952b8  mov     [rsp+150h+var_128], rdx
0x1800952bd  lea     rcx, [rbp+50h+var_68]
0x1800952c1  lea     rdx, [rsp+150h+var_128]
0x1800952c6  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x1800952cb  test    rax, rax
0x1800952ce  jnz     short loc_180095302
0x1800952d0  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x1800952d7  mov     [rbp+50h+var_C0], 145h
0x1800952df  mov     [rbp+50h+var_D0], rax
0x1800952e3  lea     rdx, [rbp+50h+var_D0]
0x1800952e7  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x1800952ee  mov     [rbp+50h+var_C8], rax
0x1800952f2  lea     rax, aPoolAllocatePu; "Pool.Allocate(&PublicKeyTokenInString)"
0x1800952f9  mov     [rbp+50h+var_B8], rax
0x1800952fd  jmp     loc_180095086
0x180095302  mov     rax, [r14+80h]
0x180095309  lea     rdx, [rsp+150h+var_110]
0x18009530e  mov     [rsp+150h+var_110], rax
0x180095313  mov     rax, [r14+70h]
0x180095317  mov     [rsp+150h+var_108], rax
0x18009531c  mov     rax, [rsp+150h+var_128]
0x180095321  mov     r8, rax
0x180095324  mov     [rsp+150h+var_128], rax
0x180095329  call    ??$FormatBytesIntoStringWithAllocate@U_LUNICODE_STRING@@@Rtl@Implementation@WCP@Windows@@YAJKAEBU?$Vector@E@3@PEAV?$Auto@U_LUNICODE_STRING@@@3@@Z; Windows::WCP::Implementation::Rtl::FormatBytesIntoStringWithAllocate<_LUNICODE_STRING>(ulong,Windows::Vector<uchar> const &,Windows::Auto<_LUNICODE_STRING> *)
0x18009532e  xor     edx, edx
0x180095330  mov     esi, eax
0x180095332  test    eax, eax
0x180095334  js      loc_1800954FE
0x18009533a  mov     sil, [rsp+150h+var_130]
0x18009533f  lea     rax, [rdi+rdi*2]
0x180095343  mov     [r15+rax*8], rdx
0x180095347  lea     rcx, g_LUNICODE_STRING_PublicKeyToken
0x18009534e  mov     [r15+rax*8+8], rcx
0x180095353  mov     rcx, [rsp+150h+var_128]
0x180095358  mov     [r15+rax*8+10h], rcx
0x18009535d  jmp     short loc_18009538D
0x18009535f  test    sil, sil
0x180095362  jz      short loc_180095390
0x180095364  test    byte ptr [r13+0], 2
0x180095369  jz      short loc_180095390
0x18009536b  cmp     rdi, r12
0x18009536e  jnb     loc_1800955C2
0x180095374  lea     rax, [rdi+rdi*2]
0x180095378  mov     [r15+rax*8], rdx
0x18009537c  lea     rcx, g_LUNICODE_STRING_PublicKeyToken
0x180095383  mov     [r15+rax*8+8], rcx
0x180095388  mov     [r15+rax*8+10h], r8
0x18009538d  inc     rdi
0x180095390  test    byte ptr [r14+10h], 10h
0x180095395  jz      loc_18009548D
0x18009539b  mov     [rsp+150h+var_128], rdx
0x1800953a0  lea     rcx, [rbp+50h+var_68]
0x1800953a4  lea     rdx, [rsp+150h+var_128]
0x1800953a9  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x1800953ae  test    rax, rax
0x1800953b1  jnz     short loc_1800953E5
0x1800953b3  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x1800953ba  mov     [rbp+50h+var_A0], 15Ch
0x1800953c2  mov     [rbp+50h+var_B0], rax
0x1800953c6  lea     rdx, [rbp+50h+var_B0]
0x1800953ca  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x1800953d1  mov     [rbp+50h+var_A8], rax
0x1800953d5  lea     rax, aPoolAllocatePr; "Pool.Allocate(&ProcArchInString)"
0x1800953dc  mov     [rbp+50h+var_98], rax
0x1800953e0  jmp     loc_180095086
0x1800953e5  mov     rax, [rsp+150h+var_128]
0x1800953ea  lea     rcx, [r14+38h]
0x1800953ee  mov     rdx, rax
0x1800953f1  mov     [rsp+150h+var_128], rax
0x1800953f6  call    ?FormatProcessorArchitecture@Implementation@Rtl@Identity@Windows@@YAJAEBVPSEUDO_ARCH@234@PEAV?$Auto@U_LUNICODE_STRING@@@4@@Z; Windows::Identity::Rtl::Implementation::FormatProcessorArchitecture(Windows::Identity::Rtl::PSEUDO_ARCH const &,Windows::Auto<_LUNICODE_STRING> *)
0x1800953fb  xor     edx, edx
0x1800953fd  mov     esi, eax
0x1800953ff  test    eax, eax
0x180095401  js      loc_1800954FE
0x180095407  mov     sil, [rsp+150h+var_130]
0x18009540c  lea     rax, [rdi+rdi*2]
0x180095410  mov     [r15+rax*8], rdx
0x180095414  lea     rcx, g_LUNICODE_STRING_ProcessorArchitecture
0x18009541b  mov     [r15+rax*8+8], rcx
0x180095420  inc     rdi
0x180095423  mov     rcx, [rsp+150h+var_128]
0x180095428  mov     [r15+rax*8+10h], rcx
0x18009542d  lea     r8, g_LUNICODE_STRING_Neutral
0x180095434  mov     eax, 100h
0x180095439  test    [r14+10h], eax
0x18009543d  jz      loc_180095533
0x180095443  mov     [rsp+150h+var_128], rdx
0x180095448  lea     rcx, [rbp+50h+var_68]
0x18009544c  lea     rdx, [rsp+150h+var_128]
0x180095451  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x180095456  test    rax, rax
0x180095459  jnz     short loc_1800954CA
0x18009545b  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x180095462  mov     [rbp+50h+var_80], 16Fh
0x18009546a  mov     [rbp+50h+var_90], rax
0x18009546e  lea     rdx, [rbp+50h+var_90]
0x180095472  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x180095479  mov     [rbp+50h+var_88], rax
0x18009547d  lea     rax, aPoolAllocatePr; "Pool.Allocate(&ProcArchInString)"
0x180095484  mov     [rbp+50h+var_78], rax
0x180095488  jmp     loc_180095086
0x18009548d  test    sil, sil
0x180095490  jz      short loc_18009542D
0x180095492  test    byte ptr [r13+0], 10h
0x180095497  jz      short loc_18009542D
0x180095499  cmp     rdi, r12
  ... truncated ...
```
