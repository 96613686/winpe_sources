# ATL::CDacl::Copy(_ACL const &)

- ea: `0x180010fb0`
- end: `0x180011693`
- name: `?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z`
- size: `1763`
- prototype: `void(ATL::CDacl *__hidden this, const struct _ACL *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x180010fb0`
- `0x18001169c`
- `0x180011970`
- `0x180011a30`
- `0x180011c70`
- `0x180011d78`
- `0x180011f18`
- `0x18002bd78`
- `0x18002bd9c`
- `0x18002c714`
- `0x18002ccf0`
- `0x180031960`
- `0x180032736`
- `0x1800327ec`
- `0x1800475d0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800112b8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180011582`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800112b8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180011582`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800110c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011546`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800110c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011546`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800112e4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800112e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001121e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800113cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001121e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800113cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001120d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001120d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113bc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001116e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001116e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800110e6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800115b5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800110e6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800115b5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800111f4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800113a3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800114f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800111f4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800113a3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800114f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800111d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001137f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800114e1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800111d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001137f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800114e1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800111bc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001136e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800114cb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800111bc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001136e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800114cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ATL::CDacl::Copy(ATL::CDacl *this, struct _ACL *a2)
{
  ATL::CDacl *v3; // r14
  unsigned int v4; // r15d
  unsigned int v5; // edx
  char *v6; // rbx
  DWORD v7; // eax
  HANDLE v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rcx
  DWORD v13; // edi
  size_t v14; // rbx
  size_t v15; // rdx
  void *v16; // rax
  void *v17; // r13
  size_t v18; // r8
  const void *v19; // rdx
  int v20; // ecx
  char *v21; // rbx
  int v22; // r8d
  const struct _GUID *v23; // rsi
  const struct _GUID *v24; // r13
  DWORD LengthSid; // eax
  HANDLE ProcessHeap; // rax
  ATL::CDacl::CAccessObjectAce *v27; // rax
  __int64 v28; // r15
  unsigned __int64 v29; // r13
  bool v30; // r13
  DWORD v31; // eax
  void *v32; // rax
  __int64 v33; // r13
  int Error; // eax
  int v35; // eax
  int v36; // eax
  char v37; // [rsp+40h] [rbp-118h]
  __int64 v38; // [rsp+48h] [rbp-110h]
  int v39; // [rsp+50h] [rbp-108h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-100h] BYREF
  ATL::CDacl *v41; // [rsp+60h] [rbp-F8h]
  PACL pAcl; // [rsp+68h] [rbp-F0h]
  ATL::CDacl::CAccessObjectAce *v43; // [rsp+70h] [rbp-E8h]
  _QWORD *v44; // [rsp+78h] [rbp-E0h]
  char *v45; // [rsp+80h] [rbp-D8h]
  __int64 pAclInformation; // [rsp+88h] [rbp-D0h] BYREF
  int v47; // [rsp+90h] [rbp-C8h]
  void **v48; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE pDestinationSid[68]; // [rsp+A8h] [rbp-B0h] BYREF
  char v50; // [rsp+ECh] [rbp-6Ch]
  int v51; // [rsp+F0h] [rbp-68h]
  __int64 v52; // [rsp+F8h] [rbp-60h]
  __int64 v53; // [rsp+100h] [rbp-58h]
  __int64 v54; // [rsp+108h] [rbp-50h]
  __int64 v55; // [rsp+110h] [rbp-48h]

  v3 = this;
  v41 = this;
  if ( !a2 )
  {
    ATL::CAcl::SetNull(this);
    return;
  }
  pAcl = a2;
  pAclInformation = 0;
  v47 = 0;
  v39 = 0;
  pAce = 0;
  v48 = &ATL::CSid::`vftable';
  v50 = 0;
  v51 = 7;
  v52 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v53 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v54 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v55 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  free(*((void **)v3 + 1));
  *((_QWORD *)v3 + 1) = 0;
  if ( !GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation)
    || !GetAclInformation(a2, &v39, 4u, AclRevisionInformation) )
  {
LABEL_3:
    ATL::AtlThrowLastWin32();
  }
  *((_DWORD *)v3 + 5) = v39;
  v13 = 0;
  while ( v13 < (unsigned int)pAclInformation )
  {
    if ( !GetAce(pAcl, v13, &pAce) )
      goto LABEL_3;
    v4 = *((_DWORD *)pAce + 1);
    v5 = *(unsigned __int8 *)pAce;
    if ( v5 > 1 )
    {
      if ( v5 - 5 > 1 )
        goto LABEL_21;
      v21 = (char *)pAce + 44;
      v22 = *((_DWORD *)pAce + 2);
      v23 = (const struct _GUID *)((char *)pAce + 12);
      if ( (v22 & 1) == 0 )
      {
        v23 = 0;
        v21 = (char *)pAce + 28;
      }
      if ( (v22 & 2) != 0 )
      {
        v33 = 28;
        if ( !v23 )
          v33 = 12;
        v24 = (const struct _GUID *)((char *)pAce + v33);
      }
      else
      {
        v24 = 0;
        v21 -= 16;
      }
      if ( !v50 || pDestinationSid != v21 )
      {
        ATL::CSid::Clear((ATL::CSid *)&v48);
        if ( !IsValidSid(v21) || (LengthSid = GetLengthSid(v21), LengthSid > 0x44) )
LABEL_12:
          ATL::AtlThrowImpl(-2147024809);
        v50 = 1;
        if ( !CopySid(LengthSid, pDestinationSid, v21) )
        {
          Error = ATL::AtlHresultFromLastError();
          v50 = 0;
          ATL::AtlThrowImpl(Error);
        }
        v51 = 8;
      }
      try
      {
        ProcessHeap = GetProcessHeap();
        v27 = (ATL::CDacl::CAccessObjectAce *)HeapAlloc(ProcessHeap, 0, 0xA8u);
        v43 = v27;
        if ( v27 )
          v28 = ATL::CDacl::CAccessObjectAce::CAccessObjectAce(
                  v27,
                  (const struct ATL::CSid *)&v48,
                  v4,
                  *((_BYTE *)pAce + 1),
                  *(_BYTE *)pAce == 5,
                  v23,
                  v24);
        else
          v28 = 0;
        v38 = v28;
      }
      catch ( ... )
      {
        v28 = v38;
        v3 = v41;
      }
      if ( !v28
        || (v29 = *((_QWORD *)v3 + 4), v29 >= *((_QWORD *)v3 + 5))
        && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                               (char *)v3 + 24,
                               v29 + 1) )
      {
LABEL_22:
        ATL::AtlThrowImpl(-2147024882);
      }
      *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v29) = v28;
      ++*((_QWORD *)v3 + 4);
      ++v13;
    }
    else
    {
      v6 = (char *)pAce + 8;
      if ( !v50 || pDestinationSid != v6 )
      {
        ATL::CSid::Clear((ATL::CSid *)&v48);
        if ( !IsValidSid(v6) )
          goto LABEL_12;
        v7 = GetLengthSid(v6);
        if ( v7 > 0x44 )
          goto LABEL_12;
        v50 = 1;
        if ( !CopySid(v7, pDestinationSid, v6) )
        {
          v35 = ATL::AtlHresultFromLastError();
          v50 = 0;
          ATL::AtlThrowImpl(v35);
        }
        v51 = 8;
      }
      v8 = GetProcessHeap();
      v9 = HeapAlloc(v8, 0, 0x98u);
      v10 = v9;
      v44 = v9;
      if ( v9 )
      {
        try
        {
          v30 = *(_BYTE *)pAce == 0;
          v37 = *((_BYTE *)pAce + 1);
          *v9 = &ATL::CAcl::CAce::`vftable';
          v45 = (char *)(v9 + 1);
          v9[1] = &ATL::CSid::`vftable';
          *((_BYTE *)v9 + 84) = v50;
          *((_DWORD *)v9 + 22) = v51;
          v9[12] = ATL::CSimpleStringT<unsigned short,0>::CloneData(v52 - 24) + 24;
          v10[13] = ATL::CSimpleStringT<unsigned short,0>::CloneData(v53 - 24) + 24;
          v10[14] = ATL::CSimpleStringT<unsigned short,0>::CloneData(v54 - 24) + 24;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v10 + 15);
          if ( v50 )
          {
            if ( !IsValidSid(pDestinationSid) )
              ATL::AtlThrowImpl(-2147024809);
            v31 = GetLengthSid(pDestinationSid);
            if ( !CopySid(v31, v10 + 2, pDestinationSid) )
            {
              v36 = ATL::AtlHresultFromLastError();
              ATL::AtlThrowImpl(v36);
            }
          }
          *((_DWORD *)v10 + 32) = v4;
          *((_BYTE *)v10 + 132) = v37;
          v10[17] = 0;
          *v10 = &ATL::CDacl::CAccessAce::`vftable';
          *((_BYTE *)v10 + 144) = v30;
        }
        catch ( ... )
        {
          v10 = 0;
          v3 = v41;
        }
      }
      else
      {
        v10 = 0;
      }
      if ( !v10 )
        goto LABEL_22;
      v11 = *((_QWORD *)v3 + 4);
      v12 = *((_QWORD *)v3 + 5);
      if ( v11 >= v12 )
      {
        v14 = v11 + 1;
        if ( v11 + 1 > v12 )
        {
          v15 = *((int *)v3 + 12);
          if ( *((_QWORD *)v3 + 3) )
          {
            if ( !*((_DWORD *)v3 + 12) )
            {
              v15 = v12 >> 1;
              if ( v14 - v12 > v12 >> 1 )
                v15 = v14 - v12;
            }
            if ( v14 < v12 + v15 )
              v14 = v12 + v15;
            v16 = calloc(v14, 8u);
            v17 = v16;
            if ( !v16 )
              goto LABEL_22;
            v18 = 8LL * *((_QWORD *)v3 + 4);
            if ( v18 )
            {
              v19 = (const void *)*((_QWORD *)v3 + 3);
              if ( v19 )
              {
                memmove_0(v16, v19, v18);
                v20 = 0;
              }
              else
              {
                *(_DWORD *)_o__errno() = 22;
                invalid_parameter_noinfo();
                v20 = 22;
              }
            }
            else
            {
              v20 = 0;
            }
            ATL::AtlCrtErrorCheck(v20);
            free(*((void **)v3 + 3));
            *((_QWORD *)v3 + 3) = v17;
          }
          else
          {
            if ( v15 > v14 )
              v14 = *((int *)v3 + 12);
            v32 = calloc(v14, 8u);
            *((_QWORD *)v3 + 3) = v32;
            if ( !v32 )
              goto LABEL_22;
          }
          *((_QWORD *)v3 + 5) = v14;
        }
      }
      *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v11) = v10;
      ++*((_QWORD *)v3 + 4);
LABEL_21:
      ++v13;
    }
  }
  ATL::CSid::~CSid((ATL::CSid *)&v48);
}

```

## disassembly

```asm
0x180010fb0  mov     r11, rsp
0x180010fb3  mov     [r11+18h], rbx
0x180010fb7  mov     [r11+20h], rsi
0x180010fbb  push    rdi
0x180010fbc  push    r12
0x180010fbe  push    r13
0x180010fc0  push    r14
0x180010fc2  push    r15
0x180010fc4  sub     rsp, 130h
0x180010fcb  mov     rax, cs:__security_cookie
0x180010fd2  xor     rax, rsp
0x180010fd5  mov     [rsp+158h+var_38], rax
0x180010fdd  mov     rdi, rdx
0x180010fe0  mov     r14, rcx
0x180010fe3  mov     [rsp+158h+var_F8], rcx
0x180010fe8  test    rdx, rdx
0x180010feb  jz      loc_1800110FA
0x180010ff1  mov     [rsp+158h+pAcl], rdx
0x180010ff6  xor     eax, eax
0x180010ff8  mov     [r11-0D0h], rax
0x180010fff  mov     [rsp+158h+var_C8], eax
0x180011006  xor     r12d, r12d
0x180011009  mov     [rsp+158h+var_108], r12d
0x18001100e  mov     [rsp+158h+pAce], r12
0x180011013  lea     r13, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18001101a  mov     [r11-0B8h], r13
0x180011021  mov     [r11-6Ch], al
0x180011025  mov     dword ptr [r11-68h], 7
0x18001102d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011034  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001103b  mov     rax, [rax+18h]
0x18001103f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011044  add     rax, 18h
0x180011048  mov     [rsp+158h+var_60], rax
0x180011050  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011057  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001105e  mov     rax, [rax+18h]
0x180011062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011067  add     rax, 18h
0x18001106b  mov     [rsp+158h+var_58], rax
0x180011073  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001107a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011081  mov     rax, [rax+18h]
0x180011085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001108a  add     rax, 18h
0x18001108e  mov     [rsp+158h+var_50], rax
0x180011096  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001109d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800110a4  mov     rax, [rax+18h]
0x1800110a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ad  add     rax, 18h
0x1800110b1  mov     [rsp+158h+var_48], rax
0x1800110b9  mov     ebx, r12d
0x1800110bc  mov     [rsp+158h+var_110], rbx
0x1800110c1  mov     rcx, [r14+8]; Block
0x1800110c5  call    cs:__imp_free
0x1800110cb  mov     [r14+8], r12
0x1800110cf  mov     r9d, 2; dwAclInformationClass
0x1800110d5  mov     r8d, 0Ch; nAclInformationLength
0x1800110db  lea     rdx, [rsp+158h+pAclInformation]; pAclInformation
0x1800110e3  mov     rcx, rdi; pAcl
0x1800110e6  call    cs:__imp_GetAclInformation
0x1800110ec  test    eax, eax
0x1800110ee  jnz     loc_1800115A1
0x1800110f4  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800110fa  call    ?SetNull@CAcl@ATL@@QEAAXXZ; ATL::CAcl::SetNull(void)
0x1800110ff  jmp     short loc_180011113
0x180011101  test    rbx, rbx
0x180011104  jnz     short loc_180011140
0x180011106  lea     rcx, [rsp+158h+var_B8]; this
0x18001110e  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180011113  mov     rcx, [rsp+158h+var_38]
0x18001111b  xor     rcx, rsp; StackCookie
0x18001111e  call    __security_check_cookie
0x180011123  lea     r11, [rsp+158h+var_28]
0x18001112b  mov     rbx, [r11+40h]
0x18001112f  mov     rsi, [r11+48h]
0x180011133  mov     rsp, r11
0x180011136  pop     r15
0x180011138  pop     r14
0x18001113a  pop     r13
0x18001113c  pop     r12
0x18001113e  pop     rdi
0x18001113f  retn
0x180011140  mov     rax, [rbx]
0x180011143  mov     edx, 1
0x180011148  mov     rcx, rbx
0x18001114b  mov     rax, [rax]
0x18001114e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011153  jmp     short loc_180011106
0x180011155  mov     [rsp+158h+var_114], edi
0x180011159  cmp     edi, dword ptr [rsp+158h+pAclInformation]
0x180011160  jnb     short loc_180011101
0x180011162  lea     r8, [rsp+158h+pAce]; pAce
0x180011167  mov     edx, edi; dwAceIndex
0x180011169  mov     rcx, [rsp+158h+pAcl]; pAcl
0x18001116e  call    cs:__imp_GetAce
0x180011174  test    eax, eax
0x180011176  jz      loc_1800110F4
0x18001117c  mov     rcx, [rsp+158h+pAce]
0x180011181  mov     r15d, [rcx+4]
0x180011185  movzx   edx, byte ptr [rcx]
0x180011188  cmp     edx, 1
0x18001118b  jnz     loc_1800112FF
0x180011191  lea     rbx, [rcx+8]
0x180011195  cmp     [rsp+158h+var_6C], 0
0x18001119d  jz      short loc_1800111AC
0x18001119f  lea     rax, [rsp+158h+pDestinationSid]
0x1800111a7  cmp     rax, rbx
0x1800111aa  jz      short loc_18001120D
0x1800111ac  lea     rcx, [rsp+158h+var_B8]; this
0x1800111b4  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x1800111b9  mov     rcx, rbx; pSid
0x1800111bc  call    cs:__imp_IsValidSid
0x1800111c2  test    eax, eax
0x1800111c4  jnz     short loc_1800111D1
0x1800111c6  mov     ecx, 80070057h; int
0x1800111cb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800111d1  mov     rcx, rbx; pSid
0x1800111d4  call    cs:__imp_GetLengthSid
0x1800111da  cmp     eax, 44h ; 'D'
0x1800111dd  ja      short loc_1800111C6
0x1800111df  mov     [rsp+158h+var_6C], 1
0x1800111e7  mov     r8, rbx; pSourceSid
0x1800111ea  lea     rdx, [rsp+158h+pDestinationSid]; pDestinationSid
0x1800111f2  mov     ecx, eax; nDestinationSidLength
0x1800111f4  call    cs:__imp_CopySid
0x1800111fa  test    eax, eax
0x1800111fc  jz      loc_180011652
0x180011202  mov     [rsp+158h+var_68], 8
0x18001120d  call    cs:__imp_GetProcessHeap
0x180011213  mov     rcx, rax; hHeap
0x180011216  xor     edx, edx; dwFlags
0x180011218  mov     r8d, 98h; dwBytes
0x18001121e  call    cs:__imp_HeapAlloc
0x180011224  mov     rsi, rax
0x180011227  mov     [rsp+158h+var_E0], rax
0x18001122c  test    rax, rax
0x18001122f  jnz     loc_18001141B
0x180011235  mov     rsi, r12
0x180011238  mov     [rsp+158h+var_110], rsi
0x18001123d  test    rsi, rsi
0x180011240  jz      short loc_18001126A
0x180011242  mov     r15, [r14+20h]
0x180011246  mov     rcx, [r14+28h]
0x18001124a  cmp     r15, rcx
0x18001124d  jnb     short loc_180011275
0x18001124f  mov     rax, [r14+18h]
0x180011253  mov     [rax+r15*8], rsi
0x180011257  mov     rbx, r12
0x18001125a  inc     qword ptr [r14+20h]
0x18001125e  mov     [rsp+158h+var_110], rbx
0x180011263  inc     edi
0x180011265  jmp     loc_180011155
0x18001126a  mov     ecx, 8007000Eh; int
0x18001126f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011275  lea     rbx, [r15+1]
0x180011279  cmp     rbx, rcx
0x18001127c  jbe     short loc_18001124F
0x18001127e  movsxd  rdx, dword ptr [r14+30h]
0x180011282  cmp     qword ptr [r14+18h], 0
0x180011287  jz      loc_180011573
0x18001128d  test    rdx, rdx
0x180011290  jnz     short loc_1800112A5
0x180011292  mov     rdx, rcx
0x180011295  shr     rdx, 1
0x180011298  mov     rax, rbx
0x18001129b  sub     rax, rcx
0x18001129e  cmp     rax, rdx
0x1800112a1  cmova   rdx, rax
0x1800112a5  lea     rax, [rcx+rdx]
0x1800112a9  cmp     rbx, rax
0x1800112ac  cmovb   rbx, rax
0x1800112b0  mov     edx, 8; Size
0x1800112b5  mov     rcx, rbx; Count
0x1800112b8  call    cs:__imp_calloc
0x1800112be  mov     r13, rax
0x1800112c1  test    rax, rax
0x1800112c4  jz      short loc_18001126A
0x1800112c6  mov     r8, [r14+20h]
0x1800112ca  shl     r8, 3; Size
0x1800112ce  test    r8, r8
0x1800112d1  jz      loc_18001168A
0x1800112d7  mov     rdx, [r14+18h]; Src
0x1800112db  test    rdx, rdx
0x1800112de  jnz     loc_180011532
0x1800112e4  call    cs:__imp__o__errno
0x1800112ea  mov     dword ptr [rax], 16h
0x1800112f0  call    _invalid_parameter_noinfo
0x1800112f5  mov     ecx, 16h
0x1800112fa  jmp     loc_18001153D
0x1800112ff  test    edx, edx
0x180011301  jz      loc_180011191
0x180011307  sub     edx, 5
0x18001130a  jz      short loc_180011315
0x18001130c  cmp     edx, 1
0x18001130f  jnz     loc_180011263
0x180011315  lea     rbx, [rcx+2Ch]
0x180011319  mov     r8d, [rcx+8]
0x18001131d  mov     edx, r8d
0x180011320  and     edx, 1
0x180011323  lea     rsi, [rcx+0Ch]
0x180011327  jnz     short loc_18001132C
0x180011329  mov     rsi, r12
0x18001132c  lea     rax, [rbx-10h]
0x180011330  test    edx, edx
0x180011332  cmovz   rbx, rax
0x180011336  test    r8b, 2
0x18001133a  jnz     loc_1800115D3
0x180011340  mov     r13, r12
0x180011343  add     rbx, 0FFFFFFFFFFFFFFF0h
0x180011347  cmp     [rsp+158h+var_6C], 0
0x18001134f  jz      short loc_18001135E
0x180011351  lea     rax, [rsp+158h+pDestinationSid]
0x180011359  cmp     rax, rbx
0x18001135c  jz      short loc_1800113BC
0x18001135e  lea     rcx, [rsp+158h+var_B8]; this
0x180011366  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18001136b  mov     rcx, rbx; pSid
0x18001136e  call    cs:__imp_IsValidSid
0x180011374  test    eax, eax
0x180011376  jz      loc_1800111C6
0x18001137c  mov     rcx, rbx; pSid
0x18001137f  call    cs:__imp_GetLengthSid
0x180011385  cmp     eax, 44h ; 'D'
0x180011388  ja      loc_1800111C6
0x18001138e  mov     [rsp+158h+var_6C], 1
0x180011396  mov     r8, rbx; pSourceSid
0x180011399  lea     rdx, [rsp+158h+pDestinationSid]; pDestinationSid
0x1800113a1  mov     ecx, eax; nDestinationSidLength
0x1800113a3  call    cs:__imp_CopySid
0x1800113a9  test    eax, eax
0x1800113ab  jz      loc_1800115ED
0x1800113b1  mov     [rsp+158h+var_68], 8
0x1800113bc  call    cs:__imp_GetProcessHeap
0x1800113c2  mov     rcx, rax; hHeap
0x1800113c5  xor     edx, edx; dwFlags
0x1800113c7  mov     r8d, 0A8h; dwBytes
0x1800113cd  call    cs:__imp_HeapAlloc
0x1800113d3  mov     [rsp+158h+var_E8], rax
0x1800113d8  test    rax, rax
0x1800113db  jnz     loc_180011602
0x1800113e1  mov     r15, r12
0x1800113e4  mov     [rsp+158h+var_110], r15
0x1800113e9  test    r15, r15
0x1800113ec  jz      loc_18001126A
0x1800113f2  mov     r13, [r14+20h]
0x1800113f6  cmp     r13, [r14+28h]
0x1800113fa  jnb     loc_180011559
0x180011400  mov     rax, [r14+18h]
0x180011404  mov     [rax+r13*8], r15
0x180011408  mov     rbx, r12
0x18001140b  inc     qword ptr [r14+20h]
0x18001140f  mov     [rsp+158h+var_110], rbx
0x180011414  inc     edi
0x180011416  jmp     loc_180011155
0x18001141b  mov     rcx, [rsp+158h+pAce]
0x180011420  cmp     byte ptr [rcx], 0
0x180011423  setz    r13b
0x180011427  movzx   eax, byte ptr [rcx+1]
0x18001142b  mov     [rsp+158h+var_118], al
0x18001142f  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x180011436  mov     [rsi], rax
0x180011439  lea     rbx, [rsi+8]
0x18001143d  mov     [rsp+158h+var_D8], rbx
0x180011445  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18001144c  mov     [rbx], rax
0x18001144f  movzx   eax, [rsp+158h+var_6C]
0x180011457  mov     [rbx+4Ch], al
0x18001145a  mov     eax, [rsp+158h+var_68]
0x180011461  mov     [rbx+50h], eax
0x180011464  mov     rcx, [rsp+158h+var_60]
0x18001146c  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180011470  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180011475  add     rax, 18h
0x180011479  mov     [rbx+58h], rax
0x18001147d  mov     rcx, [rsp+158h+var_58]
0x180011485  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180011489  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001148e  add     rax, 18h
0x180011492  mov     [rbx+60h], rax
0x180011496  mov     rcx, [rsp+158h+var_50]
0x18001149e  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800114a2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800114a7  add     rax, 18h
0x1800114ab  mov     [rbx+68h], rax
0x1800114af  lea     rcx, [rbx+70h]
0x1800114b3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800114b8  nop
0x1800114b9  cmp     [rsp+158h+var_6C], 0
0x1800114c1  jz      short loc_180011503
0x1800114c3  lea     rcx, [rsp+158h+pDestinationSid]; pSid
0x1800114cb  call    cs:__imp_IsValidSid
0x1800114d1  test    eax, eax
0x1800114d3  jz      loc_180011596
0x1800114d9  lea     rcx, [rsp+158h+pDestinationSid]; pSid
0x1800114e1  call    cs:__imp_GetLengthSid
0x1800114e7  lea     rdx, [rbx+8]; pDestinationSid
0x1800114eb  lea     r8, [rsp+158h+pDestinationSid]; pSourceSid
0x1800114f3  mov     ecx, eax; nDestinationSidLength
  ... truncated ...
```
