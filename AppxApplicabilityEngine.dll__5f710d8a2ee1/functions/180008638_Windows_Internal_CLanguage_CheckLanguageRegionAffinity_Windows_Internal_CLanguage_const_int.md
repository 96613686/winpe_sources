# Windows::Internal::CLanguage::CheckLanguageRegionAffinity(Windows::Internal::CLanguage const &,int *)

- ea: `0x180008638`
- end: `0x180008a7e`
- name: `?CheckLanguageRegionAffinity@CLanguage@Internal@Windows@@QEBAJAEBV123@PEAH@Z`
- size: `1094`
- prototype: `__int64 __fastcall(Windows::Internal::CLanguage *__hidden this, const struct Windows::Internal::CLanguage *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008330`

## callees

- `0x180005a40`
- `0x180008638`
- `0x180008c04`
- `0x180008c3c`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008840`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800087e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008840`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CLanguage::CheckLanguageRegionAffinity(
        Windows::Internal::CLanguage *this,
        const struct Windows::Internal::CLanguage *a2,
        int *a3)
{
  int v3; // ebx
  const struct Windows::Internal::CLanguage *v4; // r14
  int SubtagFields; // r12d
  unsigned __int16 v7; // si
  unsigned __int16 v8; // di
  bool v9; // zf
  bool v10; // zf
  unsigned int RegionId; // eax
  unsigned int v13; // r15d
  unsigned int v14; // r14d
  unsigned int v15; // edx
  unsigned int v16; // ecx
  double v17; // xmm0_8
  __int64 v18; // r10
  __int64 v19; // r11
  int v20; // r8d
  unsigned int CompositeRegionCode; // eax
  int v22; // r8d
  unsigned int v23; // eax
  WCHAR String2[88]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String1[88]; // [rsp+F0h] [rbp-10h] BYREF

  v3 = *a3;
  v4 = a2;
  SubtagFields = 0;
  if ( *a3 < 75 )
    goto LABEL_22;
  v7 = ((unsigned __int64)*((unsigned int *)this + 16) >> 7) & 0x1FF;
  v8 = ((unsigned __int64)*((unsigned int *)a2 + 16) >> 7) & 0x1FF;
  if ( v7 == v8 )
  {
    v3 = 90;
  }
  else if ( !v7 || !v8 || v7 == 312 || v8 == 312 )
  {
    v3 = 80;
  }
  if ( v7 > 0x138u || v8 > 0x138u )
  {
    SubtagFields = Windows::Internal::CLanguage::GetSubtagFields(this, 8, String1);
    if ( SubtagFields >= 0 )
    {
      SubtagFields = Windows::Internal::CLanguage::GetSubtagFields(v4, 8, String2);
      if ( SubtagFields >= 0 )
      {
        RegionId = Windows::Internal::CRegion::TryFindRegionId(String1);
        v13 = RegionId;
        if ( RegionId >= 0x118 )
        {
          v14 = 280;
        }
        else
        {
          v14 = RegionId;
          if ( !RegionId )
            goto LABEL_70;
        }
        do
        {
          if ( *((_DWORD *)&regionsTable + 2 * v14) <= RegionId )
            break;
          --v14;
        }
        while ( v14 );
        while ( v14 < 0x118 )
        {
LABEL_70:
          if ( *((_DWORD *)&regionsTable + 2 * v14) >= RegionId )
            break;
          ++v14;
        }
        v15 = Windows::Internal::CRegion::TryFindRegionId(String2);
        if ( v15 < 0x118 )
        {
          v16 = v15;
          if ( !v15 )
            goto LABEL_63;
        }
        else
        {
          v16 = 280;
        }
        do
        {
          if ( *((_DWORD *)&regionsTable + 2 * v16) <= v15 )
            break;
          --v16;
        }
        while ( v16 );
        while ( v16 < 0x118 )
        {
LABEL_63:
          if ( *((_DWORD *)&regionsTable + 2 * v16) >= v15 )
            break;
          ++v16;
        }
        if ( !v13 || !v15 )
          goto LABEL_62;
        if ( v13 != v15 )
        {
          v17 = DOUBLE_0_75;
          v18 = v16;
          v19 = v14;
          v20 = *((unsigned __int16 *)&regionsTable + 4 * v16 + 2);
          CompositeRegionCode = *((unsigned __int16 *)&regionsTable + 4 * v14 + 3);
          do
          {
            if ( v20 == CompositeRegionCode )
              break;
            v17 = v17 + -0.25;
            CompositeRegionCode = Windows::Internal::CRegion::GetCompositeRegionCode(CompositeRegionCode);
          }
          while ( v17 != 0.0 );
          if ( v17 == 0.0 )
          {
            v17 = DOUBLE_0_75;
            v22 = *((unsigned __int16 *)&regionsTable + 4 * v19 + 2);
            v23 = *((unsigned __int16 *)&regionsTable + 4 * v18 + 3);
            do
            {
              if ( v22 == v23 )
                break;
              v17 = v17 + -0.25;
              v23 = Windows::Internal::CRegion::GetCompositeRegionCode(v23);
            }
            while ( v17 != 0.0 );
          }
          if ( v17 <= 0.2 )
          {
LABEL_62:
            v4 = a2;
            goto LABEL_9;
          }
          if ( v17 <= 0.4 )
          {
            v3 = 84;
            goto LABEL_22;
          }
          if ( v17 <= 0.7 )
          {
            v3 = 86;
            goto LABEL_22;
          }
        }
        v3 = 88;
        goto LABEL_22;
      }
    }
  }
LABEL_9:
  if ( v3 < 80 && (*((_QWORD *)this + 8) & 0x3FFF000000LL) == 0x26000000 )
  {
    if ( v7 == 265 )
    {
      if ( v8 == 191 )
        goto LABEL_17;
      v10 = v8 == 144;
    }
    else
    {
      if ( v8 != 265 )
      {
        if ( v7 == 89 )
        {
          if ( v8 == 191 )
            goto LABEL_21;
          v9 = v8 == 144;
          goto LABEL_16;
        }
        if ( v8 == 89 )
        {
          if ( v7 == 191 )
            goto LABEL_21;
          v9 = v7 == 144;
LABEL_16:
          if ( !v9 )
          {
LABEL_17:
            v3 = 77;
            goto LABEL_22;
          }
LABEL_21:
          v3 = 76;
          goto LABEL_22;
        }
        goto LABEL_24;
      }
      if ( v7 == 191 )
        goto LABEL_17;
      v10 = v7 == 144;
    }
    if ( v10 )
      goto LABEL_17;
    goto LABEL_21;
  }
LABEL_24:
  if ( v3 < 76 )
  {
    if ( (int)Windows::Internal::CLanguage::GetSubtagFields(this, 127, String1) >= 0
      && (int)Windows::Internal::CLanguage::GetSubtagFields(v4, 1024, String2) >= 0
      && CompareStringOrdinal(String1, -1, String2, -1, 1) == 2 )
    {
      v3 = 76;
    }
    SubtagFields = Windows::Internal::CLanguage::GetSubtagFields(this, 1024, String1);
    if ( SubtagFields >= 0 )
    {
      SubtagFields = Windows::Internal::CLanguage::GetSubtagFields(v4, 127, String2);
      if ( SubtagFields >= 0 && CompareStringOrdinal(String1, -1, String2, -1, 1) == 2 )
        v3 = 76;
    }
  }
LABEL_22:
  *a3 = v3;
  return (unsigned int)SubtagFields;
}

```

## disassembly

```asm
0x180008638  mov     [rsp-8+arg_18], rbx
0x18000863d  push    rbp
0x18000863e  push    rsi
0x18000863f  push    rdi
0x180008640  push    r12
0x180008642  push    r13
0x180008644  push    r14
0x180008646  push    r15
0x180008648  lea     rbp, [rsp-0B0h]
0x180008650  sub     rsp, 1B0h
0x180008657  mov     rax, cs:__security_cookie
0x18000865e  xor     rax, rsp
0x180008661  mov     [rbp+0E0h+var_40], rax
0x180008668  mov     ebx, [r8]
0x18000866b  xor     r15d, r15d
0x18000866e  mov     [rsp+1E0h+var_1A8], r8
0x180008673  mov     r14, rdx
0x180008676  mov     [rsp+1E0h+var_1B0], rdx
0x18000867b  mov     r13, rcx
0x18000867e  mov     r12d, r15d
0x180008681  cmp     ebx, 4Bh ; 'K'
0x180008684  jl      loc_18000875A
0x18000868a  mov     esi, [rcx+40h]
0x18000868d  mov     eax, 1FFh
0x180008692  mov     edi, [rdx+40h]
0x180008695  shr     rsi, 7
0x180008699  shr     rdi, 7
0x18000869d  and     si, ax
0x1800086a0  and     di, ax
0x1800086a3  mov     eax, 138h
0x1800086a8  cmp     si, di
0x1800086ab  jz      loc_180008851
0x1800086b1  test    si, si
0x1800086b4  jz      loc_180008876
0x1800086ba  test    di, di
0x1800086bd  jz      loc_180008876
0x1800086c3  cmp     si, ax
0x1800086c6  jz      loc_180008876
0x1800086cc  cmp     di, ax
0x1800086cf  jz      loc_180008876
0x1800086d5  cmp     si, ax
0x1800086d8  ja      loc_180008880
0x1800086de  cmp     di, ax
0x1800086e1  ja      loc_180008880
0x1800086e7  cmp     ebx, 50h ; 'P'
0x1800086ea  jge     loc_180008798
0x1800086f0  mov     rax, [r13+40h]
0x1800086f4  mov     rcx, 3FFF000000h
0x1800086fe  and     rax, rcx
0x180008701  cmp     rax, 26000000h
0x180008707  jnz     loc_180008798
0x18000870d  mov     eax, 109h
0x180008712  cmp     si, ax
0x180008715  jz      loc_18000885B
0x18000871b  cmp     di, ax
0x18000871e  jz      short loc_180008741
0x180008720  cmp     si, 59h ; 'Y'
0x180008724  jnz     short loc_18000878E
0x180008726  mov     eax, 0BFh
0x18000872b  cmp     di, ax
0x18000872e  jz      short loc_180008755
0x180008730  mov     eax, 90h
0x180008735  cmp     di, ax
0x180008738  jz      short loc_180008755
0x18000873a  mov     ebx, 4Dh ; 'M'
0x18000873f  jmp     short loc_18000875A
0x180008741  mov     eax, 0BFh
0x180008746  cmp     si, ax
0x180008749  jz      short loc_18000873A
0x18000874b  mov     eax, 90h
0x180008750  cmp     si, ax
0x180008753  jz      short loc_18000873A
0x180008755  mov     ebx, 4Ch ; 'L'
0x18000875a  mov     rax, [rsp+1E0h+var_1A8]
0x18000875f  mov     [rax], ebx
0x180008761  mov     eax, r12d
0x180008764  mov     rcx, [rbp+0E0h+var_40]
0x18000876b  xor     rcx, rsp; StackCookie
0x18000876e  call    __security_check_cookie
0x180008773  mov     rbx, [rsp+1E0h+arg_18]
0x18000877b  add     rsp, 1B0h
0x180008782  pop     r15
0x180008784  pop     r14
0x180008786  pop     r13
0x180008788  pop     r12
0x18000878a  pop     rdi
0x18000878b  pop     rsi
0x18000878c  pop     rbp
0x18000878d  retn
0x18000878e  cmp     di, 59h ; 'Y'
0x180008792  jz      loc_180008913
0x180008798  mov     edi, 4Ch ; 'L'
0x18000879d  cmp     ebx, edi
0x18000879f  jge     short loc_18000875A
0x1800087a1  lea     r8, [rbp+0E0h+String1]
0x1800087a5  mov     rcx, r13
0x1800087a8  lea     edx, [rdi+33h]
0x1800087ab  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@PEAG@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,ushort *)
0x1800087b0  or      esi, 0FFFFFFFFh
0x1800087b3  mov     r12d, 400h
0x1800087b9  test    eax, eax
0x1800087bb  js      short loc_1800087F3
0x1800087bd  lea     r8, [rsp+1E0h+String2]
0x1800087c2  mov     edx, r12d
0x1800087c5  mov     rcx, r14
0x1800087c8  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@PEAG@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,ushort *)
0x1800087cd  test    eax, eax
0x1800087cf  js      short loc_1800087F3
0x1800087d1  mov     r9d, esi; cchCount2
0x1800087d4  mov     [rsp+1E0h+bIgnoreCase], 1; bIgnoreCase
0x1800087dc  lea     r8, [rsp+1E0h+String2]; lpString2
0x1800087e1  mov     edx, esi; cchCount1
0x1800087e3  lea     rcx, [rbp+0E0h+String1]; lpString1
0x1800087e7  call    cs:__imp_CompareStringOrdinal
0x1800087ed  cmp     eax, 2
0x1800087f0  cmovz   ebx, edi
0x1800087f3  lea     r8, [rbp+0E0h+String1]
0x1800087f7  mov     edx, r12d
0x1800087fa  mov     rcx, r13
0x1800087fd  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@PEAG@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,ushort *)
0x180008802  mov     r12d, eax
0x180008805  test    eax, eax
0x180008807  js      loc_18000875A
0x18000880d  lea     r8, [rsp+1E0h+String2]
0x180008812  mov     edx, 7Fh
0x180008817  mov     rcx, r14
0x18000881a  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@PEAG@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,ushort *)
0x18000881f  mov     r12d, eax
0x180008822  test    eax, eax
0x180008824  js      loc_18000875A
0x18000882a  mov     r9d, esi; cchCount2
0x18000882d  mov     [rsp+1E0h+bIgnoreCase], 1; bIgnoreCase
0x180008835  lea     r8, [rsp+1E0h+String2]; lpString2
0x18000883a  mov     edx, esi; cchCount1
0x18000883c  lea     rcx, [rbp+0E0h+String1]; lpString1
0x180008840  call    cs:__imp_CompareStringOrdinal
0x180008846  cmp     eax, 2
0x180008849  cmovz   ebx, edi
0x18000884c  jmp     loc_18000875A
0x180008851  mov     ebx, 5Ah ; 'Z'
0x180008856  jmp     loc_1800086D5
0x18000885b  mov     eax, 0BFh
0x180008860  cmp     di, ax
0x180008863  jz      loc_18000873A
0x180008869  mov     eax, 90h
0x18000886e  cmp     di, ax
0x180008871  jmp     loc_180008753
0x180008876  mov     ebx, 50h ; 'P'
0x18000887b  jmp     loc_1800086D5
0x180008880  lea     r8, [rbp+0E0h+String1]
0x180008884  mov     edx, 8
0x180008889  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@PEAG@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,ushort *)
0x18000888e  mov     r12d, eax
0x180008891  test    eax, eax
0x180008893  js      loc_1800086E7
0x180008899  lea     r8, [rsp+1E0h+String2]
0x18000889e  mov     edx, 8
0x1800088a3  mov     rcx, r14
0x1800088a6  call    ?GetSubtagFields@CLanguage@Internal@Windows@@QEBAJW4BCP47_SUBTAG_FLAGS@23@PEAG@Z; Windows::Internal::CLanguage::GetSubtagFields(Windows::Internal::BCP47_SUBTAG_FLAGS,ushort *)
0x1800088ab  mov     r12d, eax
0x1800088ae  test    eax, eax
0x1800088b0  js      loc_1800086E7
0x1800088b6  lea     rcx, [rbp+0E0h+String1]; unsigned __int16 *
0x1800088ba  call    ?TryFindRegionId@CRegion@Internal@Windows@@CAIPEBG@Z; Windows::Internal::CRegion::TryFindRegionId(ushort const *)
0x1800088bf  mov     ecx, 118h
0x1800088c4  lea     rdx, ?regionsTable@@3QBURegionsTableEntry@@B; RegionsTableEntry const near * const regionsTable
0x1800088cb  mov     r15d, eax
0x1800088ce  cmp     eax, ecx
0x1800088d0  jnb     loc_180008A20
0x1800088d6  mov     r14d, eax
0x1800088d9  test    eax, eax
0x1800088db  jz      loc_180008A37
0x1800088e1  mov     eax, r14d
0x1800088e4  cmp     [rdx+rax*8], r15d
0x1800088e8  ja      loc_180008A28
0x1800088ee  cmp     r14d, ecx
0x1800088f1  jb      loc_180008A37
0x1800088f7  lea     rcx, [rsp+1E0h+String2]; unsigned __int16 *
0x1800088fc  call    ?TryFindRegionId@CRegion@Internal@Windows@@CAIPEBG@Z; Windows::Internal::CRegion::TryFindRegionId(ushort const *)
0x180008901  mov     r8d, 118h
0x180008907  mov     edx, eax
0x180008909  cmp     eax, r8d
0x18000890c  jb      short loc_18000892E
0x18000890e  mov     ecx, r8d
0x180008911  jmp     short loc_180008938
0x180008913  mov     eax, 0BFh
0x180008918  cmp     si, ax
0x18000891b  jz      loc_180008755
0x180008921  mov     eax, 90h
0x180008926  cmp     si, ax
0x180008929  jmp     loc_180008738
0x18000892e  mov     ecx, edx
0x180008930  test    edx, edx
0x180008932  jz      loc_1800089F8
0x180008938  lea     r9, ?regionsTable@@3QBURegionsTableEntry@@B; RegionsTableEntry const near * const regionsTable
0x18000893f  mov     eax, ecx
0x180008941  cmp     [r9+rax*8], edx
0x180008945  ja      loc_180008A12
0x18000894b  cmp     ecx, r8d
0x18000894e  jb      loc_1800089FF
0x180008954  test    r15d, r15d
0x180008957  jz      loc_1800089EE
0x18000895d  test    edx, edx
0x18000895f  jz      loc_1800089EE
0x180008965  cmp     r15d, edx
0x180008968  jz      loc_180008A74
0x18000896e  movsd   xmm3, cs:__real@3fe8000000000000
0x180008976  xorps   xmm1, xmm1
0x180008979  movsd   xmm2, cs:__real@bfd0000000000000
0x180008981  movaps  xmm0, xmm3
0x180008984  mov     r10d, ecx
0x180008987  mov     r11d, r14d
0x18000898a  movzx   r8d, word ptr [r9+r10*8+4]
0x180008990  movzx   eax, word ptr [r9+r11*8+6]
0x180008996  cmp     r8d, eax
0x180008999  jz      short loc_1800089AE
0x18000899b  mov     ecx, eax; unsigned int
0x18000899d  addsd   xmm0, xmm2
0x1800089a1  call    ?GetCompositeRegionCode@CRegion@Internal@Windows@@SAII@Z; Windows::Internal::CRegion::GetCompositeRegionCode(uint)
0x1800089a6  ucomisd xmm0, xmm1
0x1800089aa  jp      short loc_180008996
0x1800089ac  jnz     short loc_180008996
0x1800089ae  ucomisd xmm0, xmm1
0x1800089b2  jp      short loc_1800089E4
0x1800089b4  jnz     short loc_1800089E4
0x1800089b6  lea     rdx, ?regionsTable@@3QBURegionsTableEntry@@B; RegionsTableEntry const near * const regionsTable
0x1800089bd  movaps  xmm0, xmm3
0x1800089c0  movzx   r8d, word ptr [rdx+r11*8+4]
0x1800089c6  movzx   eax, word ptr [rdx+r10*8+6]
0x1800089cc  cmp     r8d, eax
0x1800089cf  jz      short loc_1800089E4
0x1800089d1  mov     ecx, eax; unsigned int
0x1800089d3  addsd   xmm0, xmm2
0x1800089d7  call    ?GetCompositeRegionCode@CRegion@Internal@Windows@@SAII@Z; Windows::Internal::CRegion::GetCompositeRegionCode(uint)
0x1800089dc  ucomisd xmm0, xmm1
0x1800089e0  jp      short loc_1800089CC
0x1800089e2  jnz     short loc_1800089CC
0x1800089e4  comisd  xmm0, cs:__real@3fc999999999999a
0x1800089ec  ja      short loc_180008A4C
0x1800089ee  mov     r14, [rsp+1E0h+var_1B0]
0x1800089f3  jmp     loc_1800086E7
0x1800089f8  lea     r9, ?regionsTable@@3QBURegionsTableEntry@@B; RegionsTableEntry const near * const regionsTable
0x1800089ff  mov     eax, ecx
0x180008a01  cmp     [r9+rax*8], edx
0x180008a05  jnb     loc_180008954
0x180008a0b  inc     ecx
0x180008a0d  jmp     loc_18000894B
0x180008a12  add     ecx, 0FFFFFFFFh
0x180008a15  jnz     loc_18000893F
0x180008a1b  jmp     loc_18000894B
0x180008a20  mov     r14d, ecx
0x180008a23  jmp     loc_1800088E1
0x180008a28  add     r14d, 0FFFFFFFFh
0x180008a2c  jnz     loc_1800088E1
0x180008a32  jmp     loc_1800088EE
0x180008a37  mov     eax, r14d
0x180008a3a  cmp     [rdx+rax*8], r15d
0x180008a3e  jnb     loc_1800088F7
0x180008a44  inc     r14d
0x180008a47  jmp     loc_1800088EE
0x180008a4c  comisd  xmm0, cs:__real@3fd999999999999a
0x180008a54  jbe     short loc_180008A6A
0x180008a56  comisd  xmm0, cs:__real@3fe6666666666666
0x180008a5e  ja      short loc_180008A74
0x180008a60  mov     ebx, 56h ; 'V'
0x180008a65  jmp     loc_18000875A
0x180008a6a  mov     ebx, 54h ; 'T'
0x180008a6f  jmp     loc_18000875A
0x180008a74  mov     ebx, 58h ; 'X'
0x180008a79  jmp     loc_18000875A
```
