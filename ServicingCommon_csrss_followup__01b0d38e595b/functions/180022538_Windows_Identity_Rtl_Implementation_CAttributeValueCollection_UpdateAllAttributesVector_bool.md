# Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector(bool)

- ea: `0x180022538`
- end: `0x180022b64`
- name: `?UpdateAllAttributesVector@CAttributeValueCollection@Implementation@Rtl@Identity@Windows@@AEAAJ_N@Z`
- size: `1580`
- prototype: `__int64 __fastcall(Windows::Identity::Rtl::Implementation::CAttributeValueCollection *__hidden this, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x1800931e4`

## callees

- `0x1800052ac`
- `0x1800098bc`
- `0x1800217cc`
- `0x180022538`
- `0x180022b6c`
- `0x180022bd0`
- `0x18002d2b0`
- `0x180066860`
- `0x1800926b0`
- `0x18009273c`
- `0x180093de4`
- `0x180097498`
- `0x1800979a4`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180022ad8`
- `ntdll!RtlRaiseStatus` at `0x180022ad8`

## string_xrefs

- `0x180022602`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x18002279c`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x18002287b`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x18002295e`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x180022a06`: `Windows::Identity::Rtl::Implementation::CAttributeValueCollection::UpdateAllAttributesVector`
- `0x180022886`: `Pool.Allocate(&PublicKeyTokenInString)`

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
    goto LABEL_84;
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
    goto LABEL_84;
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
    goto LABEL_84;
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
    goto LABEL_84;
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
      goto LABEL_84;
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
      goto LABEL_84;
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
      goto LABEL_84;
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
      goto LABEL_84;
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
      goto LABEL_86;
    }
LABEL_84:
    RtlRaiseStatus(-1073741595);
  }
  if ( v3 && (*(_DWORD *)v6 & 0x100) != 0 )
  {
    if ( v13 >= valid )
      goto LABEL_84;
    v34 = 3 * v13;
    *(_QWORD *)(v12 + 8 * v34) = 0;
    *(_QWORD *)(v12 + 8 * v34 + 8) = g_LUNICODE_STRING_VersionScope;
    *(_QWORD *)(v12 + 8 * v34 + 16) = g_LUNICODE_STRING_Neutral;
  }
LABEL_86:
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
0x180022538  push    rbp
0x18002253a  push    rbx
0x18002253b  push    rsi
0x18002253c  push    rdi
0x18002253d  push    r12
0x18002253f  push    r13
0x180022541  push    r14
0x180022543  push    r15
0x180022545  lea     rbp, [rsp-18h]
0x18002254a  sub     rsp, 118h
0x180022551  mov     rax, cs:__security_cookie
0x180022558  xor     rax, rsp
0x18002255b  mov     [rbp+50h+var_48], rax
0x18002255f  xor     r9d, r9d
0x180022562  mov     [rsp+150h+var_130], dl
0x180022566  test    byte ptr [rcx], 8
0x180022569  mov     ebx, r9d
0x18002256c  mov     [rbp+50h+var_70], ebx
0x18002256f  mov     sil, dl
0x180022572  mov     r14, rcx
0x180022575  jnz     loc_180022B41
0x18002257b  mov     ecx, [rcx+10h]
0x18002257e  lea     rax, [rbp+50h+var_68]
0x180022582  mov     [rbp+50h+var_68], rax
0x180022586  lea     rax, [rbp+50h+var_68]
0x18002258a  mov     [rbp+50h+var_60], rax
0x18002258e  lea     rax, [rbp+50h+var_68]
0x180022592  mov     [rbp+50h+var_58], rax
0x180022596  mov     [rbp+50h+var_50], r9
0x18002259a  mov     qword ptr [rsp+150h+var_120], r9
0x18002259f  mov     qword ptr [rsp+150h+var_120+8], r9
0x1800225a4  call    CountValidAttributes
0x1800225a9  lea     r13, [r14+0Ch]
0x1800225ad  mov     r12, rax
0x1800225b0  test    sil, sil
0x1800225b3  jz      short loc_1800225D4
0x1800225b5  mov     ecx, [r13+0]
0x1800225b9  call    CountValidAttributes
0x1800225be  lea     rcx, [rax+r12]
0x1800225c2  cmp     rcx, r12
0x1800225c5  jnb     short loc_1800225D1
0x1800225c7  mov     esi, 0C0000095h
0x1800225cc  jmp     loc_180022A8E
0x1800225d1  mov     r12, rcx
0x1800225d4  mov     rdx, r12
0x1800225d7  lea     rcx, [rsp+150h+var_120]
0x1800225dc  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@V?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@2@@Windows@@QEAAPEAU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(unsigned __int64)
0x1800225e1  xor     edx, edx
0x1800225e3  test    rax, rax
0x1800225e6  jnz     short loc_18002262A
0x1800225e8  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x1800225ef  mov     [rsp+150h+var_100], 0E8h
0x1800225f8  mov     [rsp+150h+var_110], rax
0x1800225fd  lea     rdx, [rsp+150h+var_110]
0x180022602  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x180022609  mov     [rsp+150h+var_108], rax
0x18002260e  lea     rax, aAllattributesA; "AllAttributes.Allocate(cTotalAttributes"...
0x180022615  mov     [rsp+150h+var_F8], rax
0x18002261a  lea     rcx, [rbp+50h+var_70]
0x18002261e  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180022623  mov     esi, eax
0x180022625  jmp     loc_180022A8E
0x18002262a  test    byte ptr [r14+10h], 1
0x18002262f  lea     r8, g_LUNICODE_STRING_Neutral
0x180022636  mov     r15, qword ptr [rsp+150h+var_120]
0x18002263b  mov     rdi, rdx
0x18002263e  jz      short loc_18002264B
0x180022640  lea     rax, [r14+58h]
0x180022644  test    rax, rax
0x180022647  jz      short loc_18002267A
0x180022649  jmp     short loc_18002265A
0x18002264b  test    sil, sil
0x18002264e  jz      short loc_18002267A
0x180022650  test    byte ptr [r13+0], 1
0x180022655  jz      short loc_18002267A
0x180022657  mov     rax, r8
0x18002265a  test    r12, r12
0x18002265d  jz      loc_180022AD3
0x180022663  mov     [r15], rdx
0x180022666  lea     rcx, g_LUNICODE_STRING_Name
0x18002266d  mov     [r15+8], rcx
0x180022671  mov     edi, 1
0x180022676  mov     [r15+10h], rax
0x18002267a  test    byte ptr [r14+10h], 8
0x18002267f  jz      short loc_18002268F
0x180022681  lea     rcx, [r14+88h]
0x180022688  test    rcx, rcx
0x18002268b  jz      short loc_1800226C9
0x18002268d  jmp     short loc_1800226A2
0x18002268f  test    sil, sil
0x180022692  jz      short loc_1800226C9
0x180022694  test    byte ptr [r13+0], 8
0x180022699  jz      short loc_1800226C9
0x18002269b  lea     rcx, g_LUNICODE_STRING_neutral
0x1800226a2  cmp     rdi, r12
0x1800226a5  jnb     loc_180022AD3
0x1800226ab  lea     rax, [rdi+rdi*2]
0x1800226af  inc     rdi
0x1800226b2  mov     [r15+rax*8], rdx
0x1800226b6  lea     rdx, g_LUNICODE_STRING_Culture
0x1800226bd  mov     [r15+rax*8+8], rdx
0x1800226c2  xor     edx, edx
0x1800226c4  mov     [r15+rax*8+10h], rcx
0x1800226c9  test    byte ptr [r14+10h], 80h
0x1800226ce  jz      short loc_1800226DE
0x1800226d0  lea     rcx, [r14+0B8h]
0x1800226d7  test    rcx, rcx
0x1800226da  jz      short loc_180022714
0x1800226dc  jmp     short loc_1800226ED
0x1800226de  test    sil, sil
0x1800226e1  jz      short loc_180022714
0x1800226e3  test    byte ptr [r13+0], 80h
0x1800226e8  jz      short loc_180022714
0x1800226ea  mov     rcx, r8
0x1800226ed  cmp     rdi, r12
0x1800226f0  jnb     loc_180022AD3
0x1800226f6  lea     rax, [rdi+rdi*2]
0x1800226fa  inc     rdi
0x1800226fd  mov     [r15+rax*8], rdx
0x180022701  lea     rdx, g_LUNICODE_STRING_TypeName
0x180022708  mov     [r15+rax*8+8], rdx
0x18002270d  xor     edx, edx
0x18002270f  mov     [r15+rax*8+10h], rcx
0x180022714  test    byte ptr [r14+10h], 20h
0x180022719  jz      short loc_180022729
0x18002271b  lea     rcx, [r14+0A0h]
0x180022722  test    rcx, rcx
0x180022725  jz      short loc_18002275F
0x180022727  jmp     short loc_180022738
0x180022729  test    sil, sil
0x18002272c  jz      short loc_18002275F
0x18002272e  test    byte ptr [r13+0], 20h
0x180022733  jz      short loc_18002275F
0x180022735  mov     rcx, r8
0x180022738  cmp     rdi, r12
0x18002273b  jnb     loc_180022AD3
0x180022741  lea     rax, [rdi+rdi*2]
0x180022745  inc     rdi
0x180022748  mov     [r15+rax*8], rdx
0x18002274c  lea     rdx, g_LUNICODE_STRING_Type
0x180022753  mov     [r15+rax*8+8], rdx
0x180022758  xor     edx, edx
0x18002275a  mov     [r15+rax*8+10h], rcx
0x18002275f  test    byte ptr [r14+10h], 4
0x180022764  jz      loc_180022810
0x18002276a  mov     [rsp+150h+var_128], rdx
0x18002276f  lea     rcx, [rbp+50h+var_68]
0x180022773  lea     rdx, [rsp+150h+var_128]
0x180022778  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x18002277d  test    rax, rax
0x180022780  jnz     short loc_1800227B9
0x180022782  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x180022789  mov     [rsp+150h+var_E0], 12Fh
0x180022792  mov     [rsp+150h+var_F0], rax
0x180022797  lea     rdx, [rsp+150h+var_F0]
0x18002279c  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x1800227a3  mov     [rsp+150h+var_E8], rax
0x1800227a8  lea     rax, aPoolAllocateVe; "Pool.Allocate(&VersionInString)"
0x1800227af  mov     [rsp+150h+var_D8], rax
0x1800227b4  jmp     loc_18002261A
0x1800227b9  mov     rax, [rsp+150h+var_128]
0x1800227be  lea     rdx, [r14+28h]
0x1800227c2  mov     r8, rax
0x1800227c5  mov     [rsp+150h+var_128], rax
0x1800227ca  call    ?FormatFourPartVersion@Rtl@Implementation@WCP@Windows@@YAJKPEBT_FOUR_PART_VERSION@@PEAV?$Auto@U_LUNICODE_STRING@@@4@@Z; Windows::WCP::Implementation::Rtl::FormatFourPartVersion(ulong,_FOUR_PART_VERSION const *,Windows::Auto<_LUNICODE_STRING> *)
0x1800227cf  xor     edx, edx
0x1800227d1  mov     esi, eax
0x1800227d3  test    eax, eax
0x1800227d5  js      loc_180022A8E
0x1800227db  cmp     rdi, r12
0x1800227de  jnb     loc_180022AD3
0x1800227e4  mov     sil, [rsp+150h+var_130]
0x1800227e9  lea     rax, [rdi+rdi*2]
0x1800227ed  mov     [r15+rax*8], rdx
0x1800227f1  lea     rcx, g_LUNICODE_STRING_Version
0x1800227f8  mov     [r15+rax*8+8], rcx
0x1800227fd  lea     r8, g_LUNICODE_STRING_Neutral
0x180022804  mov     rcx, [rsp+150h+var_128]
0x180022809  mov     [r15+rax*8+10h], rcx
0x18002280e  jmp     short loc_18002283E
0x180022810  test    sil, sil
0x180022813  jz      short loc_180022841
0x180022815  test    byte ptr [r13+0], 4
0x18002281a  jz      short loc_180022841
0x18002281c  cmp     rdi, r12
0x18002281f  jnb     loc_180022AD3
0x180022825  lea     rax, [rdi+rdi*2]
0x180022829  mov     [r15+rax*8], rdx
0x18002282d  lea     rcx, g_LUNICODE_STRING_Version
0x180022834  mov     [r15+rax*8+8], rcx
0x180022839  mov     [r15+rax*8+10h], r8
0x18002283e  inc     rdi
0x180022841  test    byte ptr [r14+10h], 2
0x180022846  jz      loc_1800228F3
0x18002284c  mov     [rsp+150h+var_128], rdx
0x180022851  lea     rcx, [rbp+50h+var_68]
0x180022855  lea     rdx, [rsp+150h+var_128]
0x18002285a  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x18002285f  test    rax, rax
0x180022862  jnz     short loc_180022896
0x180022864  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x18002286b  mov     [rbp+50h+var_C0], 145h
0x180022873  mov     [rbp+50h+var_D0], rax
0x180022877  lea     rdx, [rbp+50h+var_D0]
0x18002287b  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x180022882  mov     [rbp+50h+var_C8], rax
0x180022886  lea     rax, aPoolAllocatePu; "Pool.Allocate(&PublicKeyTokenInString)"
0x18002288d  mov     [rbp+50h+var_B8], rax
0x180022891  jmp     loc_18002261A
0x180022896  mov     rax, [r14+80h]
0x18002289d  lea     rdx, [rsp+150h+var_110]
0x1800228a2  mov     [rsp+150h+var_110], rax
0x1800228a7  mov     rax, [r14+70h]
0x1800228ab  mov     [rsp+150h+var_108], rax
0x1800228b0  mov     rax, [rsp+150h+var_128]
0x1800228b5  mov     r8, rax
0x1800228b8  mov     [rsp+150h+var_128], rax
0x1800228bd  call    ??$FormatBytesIntoStringWithAllocate@U_LUNICODE_STRING@@@Rtl@Implementation@WCP@Windows@@YAJKAEBU?$Vector@E@3@PEAV?$Auto@U_LUNICODE_STRING@@@3@@Z; Windows::WCP::Implementation::Rtl::FormatBytesIntoStringWithAllocate<_LUNICODE_STRING>(ulong,Windows::Vector<uchar> const &,Windows::Auto<_LUNICODE_STRING> *)
0x1800228c2  xor     edx, edx
0x1800228c4  mov     esi, eax
0x1800228c6  test    eax, eax
0x1800228c8  js      loc_180022A8E
0x1800228ce  mov     sil, [rsp+150h+var_130]
0x1800228d3  lea     rax, [rdi+rdi*2]
0x1800228d7  mov     [r15+rax*8], rdx
0x1800228db  lea     rcx, g_LUNICODE_STRING_PublicKeyToken
0x1800228e2  mov     [r15+rax*8+8], rcx
0x1800228e7  mov     rcx, [rsp+150h+var_128]
0x1800228ec  mov     [r15+rax*8+10h], rcx
0x1800228f1  jmp     short loc_180022921
0x1800228f3  test    sil, sil
0x1800228f6  jz      short loc_180022924
0x1800228f8  test    byte ptr [r13+0], 2
0x1800228fd  jz      short loc_180022924
0x1800228ff  cmp     rdi, r12
0x180022902  jnb     loc_180022AD3
0x180022908  lea     rax, [rdi+rdi*2]
0x18002290c  mov     [r15+rax*8], rdx
0x180022910  lea     rcx, g_LUNICODE_STRING_PublicKeyToken
0x180022917  mov     [r15+rax*8+8], rcx
0x18002291c  mov     [r15+rax*8+10h], r8
0x180022921  inc     rdi
0x180022924  test    byte ptr [r14+10h], 10h
0x180022929  jz      loc_180022A21
0x18002292f  mov     [rsp+150h+var_128], rdx
0x180022934  lea     rcx, [rbp+50h+var_68]
0x180022938  lea     rdx, [rsp+150h+var_128]
0x18002293d  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x180022942  test    rax, rax
0x180022945  jnz     short loc_180022979
0x180022947  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x18002294e  mov     [rbp+50h+var_A0], 15Ch
0x180022956  mov     [rbp+50h+var_B0], rax
0x18002295a  lea     rdx, [rbp+50h+var_B0]
0x18002295e  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x180022965  mov     [rbp+50h+var_A8], rax
0x180022969  lea     rax, aPoolAllocatePr; "Pool.Allocate(&ProcArchInString)"
0x180022970  mov     [rbp+50h+var_98], rax
0x180022974  jmp     loc_18002261A
0x180022979  mov     rax, [rsp+150h+var_128]
0x18002297e  lea     rcx, [r14+38h]
0x180022982  mov     rdx, rax
0x180022985  mov     [rsp+150h+var_128], rax
0x18002298a  call    ?FormatProcessorArchitecture@Implementation@Rtl@Identity@Windows@@YAJAEBVPSEUDO_ARCH@234@PEAV?$Auto@U_LUNICODE_STRING@@@4@@Z; Windows::Identity::Rtl::Implementation::FormatProcessorArchitecture(Windows::Identity::Rtl::PSEUDO_ARCH const &,Windows::Auto<_LUNICODE_STRING> *)
0x18002298f  xor     edx, edx
0x180022991  mov     esi, eax
0x180022993  test    eax, eax
0x180022995  js      loc_180022A8E
0x18002299b  mov     sil, [rsp+150h+var_130]
0x1800229a0  lea     rax, [rdi+rdi*2]
0x1800229a4  mov     [r15+rax*8], rdx
0x1800229a8  lea     rcx, g_LUNICODE_STRING_ProcessorArchitecture
0x1800229af  mov     [r15+rax*8+8], rcx
0x1800229b4  inc     rdi
0x1800229b7  mov     rcx, [rsp+150h+var_128]
0x1800229bc  mov     [r15+rax*8+10h], rcx
0x1800229c1  lea     r8, g_LUNICODE_STRING_Neutral
0x1800229c8  mov     eax, 100h
0x1800229cd  test    [r14+10h], eax
0x1800229d1  jz      loc_180022AC3
0x1800229d7  mov     [rsp+150h+var_128], rdx
0x1800229dc  lea     rcx, [rbp+50h+var_68]
0x1800229e0  lea     rdx, [rsp+150h+var_128]
0x1800229e5  call    ??$Allocate@V?$Auto@U_LUNICODE_STRING@@@Windows@@@CAllocationPool@Implementation@WCP@Windows@@QEAAPEAV?$Auto@U_LUNICODE_STRING@@@3@PEAPEAV43@@Z; Windows::WCP::Implementation::CAllocationPool::Allocate<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> * *)
0x1800229ea  test    rax, rax
0x1800229ed  jnz     short loc_180022A5E
0x1800229ef  lea     rax, aOnecoreBaseWcp_9; "onecore\\base\\wcp\\identity\\attribute"...
0x1800229f6  mov     [rbp+50h+var_80], 16Fh
0x1800229fe  mov     [rbp+50h+var_90], rax
0x180022a02  lea     rdx, [rbp+50h+var_90]
0x180022a06  lea     rax, aWindowsIdentit_11; "Windows::Identity::Rtl::Implementation:"...
0x180022a0d  mov     [rbp+50h+var_88], rax
0x180022a11  lea     rax, aPoolAllocatePr; "Pool.Allocate(&ProcArchInString)"
0x180022a18  mov     [rbp+50h+var_78], rax
0x180022a1c  jmp     loc_18002261A
0x180022a21  test    sil, sil
0x180022a24  jz      short loc_1800229C1
0x180022a26  test    byte ptr [r13+0], 10h
0x180022a2b  jz      short loc_1800229C1
0x180022a2d  cmp     rdi, r12
  ... truncated ...
```
