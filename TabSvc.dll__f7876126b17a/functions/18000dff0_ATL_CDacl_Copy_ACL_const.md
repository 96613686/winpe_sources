# ATL::CDacl::Copy(_ACL const &)

- ea: `0x18000dff0`
- end: `0x18000e48b`
- name: `?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z`
- size: `1179`
- prototype: `void __fastcall(ATL::CDacl *this, struct _ACL *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002bda4`

## callees

- `0x18000dff0`
- `0x18000e4a0`
- `0x18000e6f0`
- `0x18000e724`
- `0x180013ac4`
- `0x1800140b4`
- `0x180019ddc`
- `0x180019e00`
- `0x18001bbe0`
- `0x18001c058`
- `0x18002bca0`
- `0x18002c334`
- `0x18002dc3c`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000e2f6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000e445`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000e2f6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000e445`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e32a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e32a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000e119`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000e119`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000e0c6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000e0e4`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000e0c6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000e0e4`

## pseudocode

```c
void __fastcall ATL::CDacl::Copy(ATL::CDacl *this, struct _ACL *a2, __int64 a3)
{
  ATL::CDacl *v4; // r14
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  DWORD i; // edi
  int v12; // r15d
  unsigned int v13; // edx
  const struct _SID *v14; // rbx
  ATL::CDacl::CAccessObjectAce *v15; // rsi
  bool v16; // bl
  char v17; // r12
  const struct _SID *v18; // rbx
  int v19; // r8d
  const struct _GUID *v20; // r12
  const struct _GUID *v21; // rsi
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // rcx
  size_t v24; // rbx
  size_t v25; // rdx
  void *v26; // rax
  void *v27; // r12
  errno_t v28; // ecx
  __int64 v29; // rsi
  void *v30; // rax
  ATL::CDacl::CAccessObjectAce *v31; // [rsp+48h] [rbp-100h]
  ATL::CDacl::CAccessObjectAce *v32; // [rsp+48h] [rbp-100h]
  int v33; // [rsp+50h] [rbp-F8h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-F0h] BYREF
  ATL::CDacl *v35; // [rsp+60h] [rbp-E8h]
  PACL pAcl; // [rsp+68h] [rbp-E0h]
  ATL::CDacl::CAccessObjectAce *v37; // [rsp+70h] [rbp-D8h]
  __int64 pAclInformation; // [rsp+78h] [rbp-D0h] BYREF
  int v39; // [rsp+80h] [rbp-C8h]
  void **v40; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v41[68]; // [rsp+98h] [rbp-B0h] BYREF
  char v42; // [rsp+DCh] [rbp-6Ch]
  int v43; // [rsp+E0h] [rbp-68h]
  __int64 v44; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-50h] BYREF
  _QWORD v47[2]; // [rsp+100h] [rbp-48h] BYREF

  v4 = this;
  v35 = this;
  if ( a2 )
  {
    pAcl = a2;
    pAclInformation = 0;
    v39 = 0;
    v33 = 0;
    pAce = 0;
    v40 = &ATL::CSid::`vftable';
    v42 = 0;
    v43 = 7;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v44,
      a2,
      a3);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v45,
      v5,
      v6);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v46,
      v7,
      v8);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v47,
      v9,
      v10);
    free(*((void **)v4 + 1));
    *((_QWORD *)v4 + 1) = 0;
    if ( !GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation)
      || !GetAclInformation(a2, &v33, 4u, AclRevisionInformation) )
    {
LABEL_4:
      ATL::AtlThrowLastWin32();
    }
    *((_DWORD *)v4 + 5) = v33;
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned int)pAclInformation )
      {
        v40 = &ATL::CSid::`vftable';
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v47);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v46);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v45);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v44);
        return;
      }
      if ( !GetAce(pAcl, i, &pAce) )
        goto LABEL_4;
      v12 = *((_DWORD *)pAce + 1);
      v13 = *(unsigned __int8 *)pAce;
      if ( v13 > 1 )
      {
        if ( v13 - 5 > 1 )
          continue;
        v18 = (const struct _SID *)((char *)pAce + 44);
        v19 = *((_DWORD *)pAce + 2);
        v20 = (const struct _GUID *)((char *)pAce + 12);
        if ( (v19 & 1) == 0 )
        {
          v20 = 0;
          v18 = (const struct _SID *)((char *)pAce + 28);
        }
        if ( (v19 & 2) != 0 )
        {
          v29 = 28;
          if ( !v20 )
            v29 = 12;
          v21 = (const struct _GUID *)((char *)pAce + v29);
        }
        else
        {
          v21 = 0;
          v18 = (const struct _SID *)((char *)v18 - 16);
        }
        if ( !v42 || v41 != (_BYTE *)v18 )
        {
          ATL::CSid::Clear((ATL::CSid *)&v40);
          ATL::CSid::Copy((ATL::CSid *)&v40, v18);
          v43 = 8;
        }
        try
        {
          v37 = (ATL::CDacl::CAccessObjectAce *)operator new(0xA8u);
          v15 = ATL::CDacl::CAccessObjectAce::CAccessObjectAce(
                  v37,
                  (const struct ATL::CSid *)&v40,
                  v12,
                  *((_BYTE *)pAce + 1),
                  *(_BYTE *)pAce == 5,
                  v20,
                  v21);
          v32 = v15;
        }
        catch ( ... )
        {
          v15 = v32;
          v4 = v35;
        }
      }
      else
      {
        v14 = (const struct _SID *)((char *)pAce + 8);
        if ( !v42 || v41 != (_BYTE *)v14 )
        {
          ATL::CSid::Clear((ATL::CSid *)&v40);
          ATL::CSid::Copy((ATL::CSid *)&v40, v14);
          v43 = 8;
        }
        try
        {
          v15 = (ATL::CDacl::CAccessObjectAce *)operator new(0x98u);
          v37 = v15;
          v16 = *(_BYTE *)pAce == 0;
          v17 = *((_BYTE *)pAce + 1);
          *(_QWORD *)v15 = &ATL::CAcl::CAce::`vftable';
          ATL::CSid::CSid((ATL::CDacl::CAccessObjectAce *)((char *)v15 + 8), (const struct ATL::CSid *)&v40);
          *((_DWORD *)v15 + 32) = v12;
          *((_BYTE *)v15 + 132) = v17;
          *((_QWORD *)v15 + 17) = 0;
          *(_QWORD *)v15 = &ATL::CDacl::CAccessAce::`vftable';
          *((_BYTE *)v15 + 144) = v16;
          v31 = v15;
        }
        catch ( ... )
        {
          v15 = v31;
          v4 = v35;
        }
      }
      if ( !v15 )
        goto LABEL_13;
      v22 = *((_QWORD *)v4 + 4);
      v23 = *((_QWORD *)v4 + 5);
      if ( v22 >= v23 )
      {
        v24 = v22 + 1;
        if ( v22 + 1 > v23 )
        {
          v25 = *((int *)v4 + 12);
          if ( *((_QWORD *)v4 + 3) )
          {
            if ( !*((_DWORD *)v4 + 12) )
            {
              v25 = v23 >> 1;
              if ( v24 - v23 > v23 >> 1 )
                v25 = v24 - v23;
            }
            if ( v24 < v23 + v25 )
              v24 = v23 + v25;
            v26 = calloc(v24, 8u);
            v27 = v26;
            if ( !v26 )
              goto LABEL_13;
            v28 = memmove_s(v26, 8LL * *((_QWORD *)v4 + 4), *((const void *const *)v4 + 3), 8LL * *((_QWORD *)v4 + 4));
            ATL::AtlCrtErrorCheck(v28);
            free(*((void **)v4 + 3));
            *((_QWORD *)v4 + 3) = v27;
          }
          else
          {
            if ( v25 > v24 )
              v24 = *((int *)v4 + 12);
            v30 = calloc(v24, 8u);
            *((_QWORD *)v4 + 3) = v30;
            if ( !v30 )
LABEL_13:
              ATL::AtlThrowImpl(-2147024882);
          }
          *((_QWORD *)v4 + 5) = v24;
        }
      }
      *(_QWORD *)(*((_QWORD *)v4 + 3) + 8 * v22) = v15;
      ++*((_QWORD *)v4 + 4);
    }
  }
  (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)this + 16LL))(this);
  *((_BYTE *)v4 + 16) = 1;
}

```

## disassembly

```asm
0x18000dff0  mov     r11, rsp
0x18000dff3  mov     [r11+18h], rbx
0x18000dff7  mov     [r11+20h], rsi
0x18000dffb  push    rdi
0x18000dffc  push    r12
0x18000dffe  push    r13
0x18000e000  push    r14
0x18000e002  push    r15
0x18000e004  sub     rsp, 120h
0x18000e00b  mov     rax, cs:__security_cookie
0x18000e012  xor     rax, rsp
0x18000e015  mov     [rsp+148h+var_38], rax
0x18000e01d  mov     rdi, rdx
0x18000e020  mov     r14, rcx
0x18000e023  mov     [rsp+148h+var_E8], rcx
0x18000e028  test    rdx, rdx
0x18000e02b  jz      loc_18000E3C6
0x18000e031  mov     [rsp+148h+pAcl], rdx
0x18000e036  xor     eax, eax
0x18000e038  mov     [rsp+148h+pAclInformation], rax
0x18000e03d  mov     [rsp+148h+var_C8], eax
0x18000e044  xor     r13d, r13d
0x18000e047  mov     [rsp+148h+var_F8], r13d
0x18000e04c  mov     [rsp+148h+pAce], r13
0x18000e051  lea     rsi, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000e058  mov     [r11-0B8h], rsi
0x18000e05f  mov     [r11-6Ch], al
0x18000e063  mov     dword ptr [r11-68h], 7
0x18000e06b  lea     rcx, [r11-60h]
0x18000e06f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e074  lea     rcx, [rsp+148h+var_58]
0x18000e07c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e081  lea     rcx, [rsp+148h+var_50]
0x18000e089  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e08e  lea     rcx, [rsp+148h+var_48]
0x18000e096  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e09b  nop
0x18000e09c  mov     ebx, r13d
0x18000e09f  mov     [rsp+148h+var_100], rbx
0x18000e0a4  mov     rcx, [r14+8]; Block
0x18000e0a8  call    cs:__imp_free
0x18000e0ae  mov     [r14+8], r13
0x18000e0b2  mov     r9d, 2; dwAclInformationClass
0x18000e0b8  mov     r8d, 0Ch; nAclInformationLength
0x18000e0be  lea     rdx, [rsp+148h+pAclInformation]; pAclInformation
0x18000e0c3  mov     rcx, rdi; pAcl
0x18000e0c6  call    cs:__imp_GetAclInformation
0x18000e0cc  test    eax, eax
0x18000e0ce  jz      short loc_18000E0EE
0x18000e0d0  mov     r9d, 1; dwAclInformationClass
0x18000e0d6  mov     r8d, 4; nAclInformationLength
0x18000e0dc  lea     rdx, [rsp+148h+var_F8]; pAclInformation
0x18000e0e1  mov     rcx, rdi; pAcl
0x18000e0e4  call    cs:__imp_GetAclInformation
0x18000e0ea  test    eax, eax
0x18000e0ec  jnz     short loc_18000E0F4
0x18000e0ee  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18000e0f4  mov     eax, [rsp+148h+var_F8]
0x18000e0f8  mov     [r14+14h], eax
0x18000e0fc  mov     edi, r13d
0x18000e0ff  mov     [rsp+148h+var_108], edi
0x18000e103  cmp     edi, dword ptr [rsp+148h+pAclInformation]
0x18000e107  jnb     loc_18000E33D
0x18000e10d  lea     r8, [rsp+148h+pAce]; pAce
0x18000e112  mov     edx, edi; dwAceIndex
0x18000e114  mov     rcx, [rsp+148h+pAcl]; pAcl
0x18000e119  call    cs:__imp_GetAce
0x18000e11f  test    eax, eax
0x18000e121  jz      short loc_18000E0EE
0x18000e123  mov     rcx, [rsp+148h+pAce]
0x18000e128  mov     r15d, [rcx+4]
0x18000e12c  movzx   edx, byte ptr [rcx]
0x18000e12f  cmp     edx, 1
0x18000e132  jnz     loc_18000E1D6
0x18000e138  lea     rbx, [rcx+8]
0x18000e13c  cmp     [rsp+148h+var_6C], 0
0x18000e144  jz      loc_18000E45D
0x18000e14a  lea     rax, [rsp+148h+var_B0]
0x18000e152  cmp     rax, rbx
0x18000e155  jnz     loc_18000E45D
0x18000e15b  mov     ecx, 98h; Size
0x18000e160  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e165  mov     rsi, rax
0x18000e168  mov     [rsp+148h+var_D8], rax
0x18000e16d  mov     rcx, [rsp+148h+pAce]
0x18000e172  cmp     byte ptr [rcx], 0
0x18000e175  setz    bl
0x18000e178  movzx   r12d, byte ptr [rcx+1]
0x18000e17d  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x18000e184  mov     [rsi], rax
0x18000e187  lea     rcx, [rsi+8]; this
0x18000e18b  lea     rdx, [rsp+148h+var_B8]; struct ATL::CSid *
0x18000e193  call    ??0CSid@ATL@@QEAA@AEBV01@@Z; ATL::CSid::CSid(ATL::CSid const &)
0x18000e198  mov     [rsi+80h], r15d
0x18000e19f  mov     [rsi+84h], r12b
0x18000e1a6  mov     [rsi+88h], r13
0x18000e1ad  lea     r12, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x18000e1b4  mov     [rsi], r12
0x18000e1b7  mov     [rsi+90h], bl
0x18000e1bd  mov     [rsp+148h+var_100], rsi
0x18000e1c2  test    rsi, rsi
0x18000e1c5  jnz     loc_18000E28B
0x18000e1cb  mov     ecx, 8007000Eh; int
0x18000e1d0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e1d6  test    edx, edx
0x18000e1d8  jz      loc_18000E138
0x18000e1de  sub     edx, 5
0x18000e1e1  jz      short loc_18000E1EC
0x18000e1e3  cmp     edx, 1
0x18000e1e6  jnz     loc_18000E2AC
0x18000e1ec  lea     rbx, [rcx+2Ch]
0x18000e1f0  mov     r8d, [rcx+8]
0x18000e1f4  mov     edx, r8d
0x18000e1f7  and     edx, 1
0x18000e1fa  lea     r12, [rcx+0Ch]
0x18000e1fe  jnz     short loc_18000E203
0x18000e200  mov     r12, r13
0x18000e203  lea     rax, [rbx-10h]
0x18000e207  test    edx, edx
0x18000e209  cmovz   rbx, rax
0x18000e20d  test    r8b, 2
0x18000e211  jnz     loc_18000E3D9
0x18000e217  mov     rsi, r13
0x18000e21a  add     rbx, 0FFFFFFFFFFFFFFF0h
0x18000e21e  cmp     [rsp+148h+var_6C], 0
0x18000e226  jz      loc_18000E3F1
0x18000e22c  lea     rax, [rsp+148h+var_B0]
0x18000e234  cmp     rax, rbx
0x18000e237  jnz     loc_18000E3F1
0x18000e23d  mov     ecx, 0A8h; Size
0x18000e242  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e247  mov     [rsp+148h+var_D8], rax
0x18000e24c  mov     r9, [rsp+148h+pAce]
0x18000e251  cmp     byte ptr [r9], 5
0x18000e255  setz    cl
0x18000e258  mov     [rsp+148h+var_118], rsi; struct _GUID *
0x18000e25d  mov     [rsp+148h+var_120], r12; struct _GUID *
0x18000e262  mov     [rsp+148h+var_128], cl; bool
0x18000e266  movzx   r9d, byte ptr [r9+1]; unsigned __int8
0x18000e26b  mov     r8d, r15d; unsigned int
0x18000e26e  lea     rdx, [rsp+148h+var_B8]; struct ATL::CSid *
0x18000e276  mov     rcx, rax; this
0x18000e279  call    ??0CAccessObjectAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_NPEBU_GUID@@2@Z; ATL::CDacl::CAccessObjectAce::CAccessObjectAce(ATL::CSid const &,ulong,uchar,bool,_GUID const *,_GUID const *)
0x18000e27e  mov     rsi, rax
0x18000e281  mov     [rsp+148h+var_100], rax
0x18000e286  jmp     loc_18000E1C2
0x18000e28b  mov     r15, [r14+20h]
0x18000e28f  mov     rcx, [r14+28h]
0x18000e293  cmp     r15, rcx
0x18000e296  jnb     short loc_18000E2B3
0x18000e298  mov     rax, [r14+18h]
0x18000e29c  mov     [rax+r15*8], rsi
0x18000e2a0  mov     rbx, r13
0x18000e2a3  inc     qword ptr [r14+20h]
0x18000e2a7  mov     [rsp+148h+var_100], rbx
0x18000e2ac  inc     edi
0x18000e2ae  jmp     loc_18000E0FF
0x18000e2b3  lea     rbx, [r15+1]
0x18000e2b7  cmp     rbx, rcx
0x18000e2ba  jbe     short loc_18000E298
0x18000e2bc  movsxd  rdx, dword ptr [r14+30h]
0x18000e2c0  cmp     qword ptr [r14+18h], 0
0x18000e2c5  jz      loc_18000E436
0x18000e2cb  test    rdx, rdx
0x18000e2ce  jnz     short loc_18000E2E3
0x18000e2d0  mov     rdx, rcx
0x18000e2d3  mov     rax, rbx
0x18000e2d6  shr     rdx, 1
0x18000e2d9  sub     rax, rcx
0x18000e2dc  cmp     rax, rdx
0x18000e2df  cmova   rdx, rax
0x18000e2e3  lea     rax, [rcx+rdx]
0x18000e2e7  cmp     rbx, rax
0x18000e2ea  cmovb   rbx, rax
0x18000e2ee  mov     edx, 8; Size
0x18000e2f3  mov     rcx, rbx; Count
0x18000e2f6  call    cs:__imp_calloc
0x18000e2fc  test    rax, rax
0x18000e2ff  mov     r12, rax
0x18000e302  jz      loc_18000E1CB
0x18000e308  mov     rdx, [r14+20h]
0x18000e30c  shl     rdx, 3; DestinationSize
0x18000e310  mov     r9, rdx; SourceSize
0x18000e313  mov     r8, [r14+18h]; Source
0x18000e317  mov     rcx, rax; Destination
0x18000e31a  call    memmove_s
0x18000e31f  mov     ecx, eax; int
0x18000e321  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000e326  mov     rcx, [r14+18h]; Block
0x18000e32a  call    cs:__imp_free
0x18000e330  mov     [r14+18h], r12
0x18000e334  mov     [r14+28h], rbx
0x18000e338  jmp     loc_18000E298
0x18000e33d  test    rbx, rbx
0x18000e340  jz      short loc_18000E356
0x18000e342  mov     rax, [rbx]
0x18000e345  mov     edx, 1
0x18000e34a  mov     rcx, rbx
0x18000e34d  mov     rax, [rax]
0x18000e350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e355  nop
0x18000e356  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000e35d  mov     [rsp+148h+var_B8], rax
0x18000e365  lea     rcx, [rsp+148h+var_48]
0x18000e36d  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e372  lea     rcx, [rsp+148h+var_50]
0x18000e37a  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e37f  lea     rcx, [rsp+148h+var_58]
0x18000e387  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e38c  lea     rcx, [rsp+148h+var_60]
0x18000e394  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000e399  mov     rcx, [rsp+148h+var_38]
0x18000e3a1  xor     rcx, rsp; StackCookie
0x18000e3a4  call    __security_check_cookie
0x18000e3a9  lea     r11, [rsp+148h+var_28]
0x18000e3b1  mov     rbx, [r11+40h]
0x18000e3b5  mov     rsi, [r11+48h]
0x18000e3b9  mov     rsp, r11
0x18000e3bc  pop     r15
0x18000e3be  pop     r14
0x18000e3c0  pop     r13
0x18000e3c2  pop     r12
0x18000e3c4  pop     rdi
0x18000e3c5  retn
0x18000e3c6  mov     rax, [rcx]
0x18000e3c9  mov     rax, [rax+10h]
0x18000e3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3d2  mov     byte ptr [r14+10h], 1
0x18000e3d7  jmp     short loc_18000E399
0x18000e3d9  mov     esi, 1Ch
0x18000e3de  test    r12, r12
0x18000e3e1  mov     eax, 0Ch
0x18000e3e6  cmovz   esi, eax
0x18000e3e9  add     rsi, rcx
0x18000e3ec  jmp     loc_18000E21E
0x18000e3f1  lea     rcx, [rsp+148h+var_B8]; this
0x18000e3f9  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18000e3fe  mov     rdx, rbx; struct _SID *
0x18000e401  lea     rcx, [rsp+148h+var_B8]; this
0x18000e409  call    ?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z; ATL::CSid::Copy(_SID const &)
0x18000e40e  mov     [rsp+148h+var_68], 8
0x18000e419  jmp     loc_18000E23D
0x18000e41e  jmp     short $+2
0x18000e420  xor     r13d, r13d
0x18000e423  mov     rsi, [rsp+148h+var_100]
0x18000e428  mov     edi, [rsp+148h+var_108]
0x18000e42c  mov     r14, [rsp+148h+var_E8]
0x18000e431  jmp     loc_18000E1C2
0x18000e436  cmp     rdx, rbx
0x18000e439  cmova   rbx, rdx
0x18000e43d  mov     edx, 8; Size
0x18000e442  mov     rcx, rbx; Count
0x18000e445  call    cs:__imp_calloc
0x18000e44b  mov     [r14+18h], rax
0x18000e44f  test    rax, rax
0x18000e452  jz      loc_18000E1CB
0x18000e458  jmp     loc_18000E334
0x18000e45d  lea     rcx, [rsp+148h+var_B8]; this
0x18000e465  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x18000e46a  mov     rdx, rbx; struct _SID *
0x18000e46d  lea     rcx, [rsp+148h+var_B8]; this
0x18000e475  call    ?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z; ATL::CSid::Copy(_SID const &)
0x18000e47a  mov     [rsp+148h+var_68], 8
0x18000e485  jmp     loc_18000E15B
```
