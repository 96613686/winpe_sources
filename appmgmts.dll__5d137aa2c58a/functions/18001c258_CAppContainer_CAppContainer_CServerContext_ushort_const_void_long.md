# CAppContainer::CAppContainer(CServerContext *,ushort const *,void *,long *)

- ea: `0x18001c258`
- end: `0x18001c5e2`
- name: `??0CAppContainer@@QEAA@PEAVCServerContext@@PEBGPEAXPEAJ@Z`
- size: `906`
- prototype: `CAppContainer *__fastcall(CAppContainer *__hidden this, struct CServerContext *, const unsigned __int16 *, void *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001c84c`

## callees

- `0x1800016d0`
- `0x18001c258`
- `0x18001d130`
- `0x18002350c`
- `0x180023de4`
- `0x180024218`
- `0x180024458`
- `0x180024b90`

## import_xrefs

- `adsldpc!ADSIGetObjectAttributes` at `0x18001c3fd`
- `adsldpc!ADSIGetObjectAttributes` at `0x18001c3fd`
- `adsldpc!BuildADsPathFromParent` at `0x18001c529`
- `adsldpc!BuildADsPathFromParent` at `0x18001c529`
- `adsldpc!ADSISetSearchPreference` at `0x18001c571`
- `adsldpc!ADSISetSearchPreference` at `0x18001c571`
- `adsldpc!BuildADsParentPath` at `0x18001c4b1`
- `adsldpc!BuildADsParentPath` at `0x18001c4b1`
- `adsldpc!FreeADsMem` at `0x18001c4c1`
- `adsldpc!FreeADsMem` at `0x18001c4f6`
- `adsldpc!FreeADsMem` at `0x18001c506`
- `adsldpc!FreeADsMem` at `0x18001c4c1`
- `adsldpc!FreeADsMem` at `0x18001c4f6`
- `adsldpc!FreeADsMem` at `0x18001c506`

## pseudocode

```c
CAppContainer *__fastcall CAppContainer::CAppContainer(
        CAppContainer *this,
        struct CServerContext *a2,
        const unsigned __int16 *a3,
        void *a4,
        int *a5)
{
  void **v5; // r14
  void **v6; // r15
  struct _GUID *v7; // r13
  unsigned __int16 *v8; // r12
  __int64 v11; // rdx
  __int64 v12; // r8
  _WORD *v13; // rax
  _WORD *v14; // rcx
  unsigned int v15; // esi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  struct _ads_attr_info *v19; // rcx
  unsigned int PropertyFromAttr; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned __int16 *DNString; // rcx
  void *v25; // rcx
  __int64 v26; // rax
  bool v27; // zf
  int v28; // eax
  int v29; // eax
  unsigned __int16 *v30; // rax
  unsigned int v32; // [rsp+30h] [rbp-B1h] BYREF
  struct _ads_attr_info *v33; // [rsp+38h] [rbp-A9h] BYREF
  LPVOID v34; // [rsp+40h] [rbp-A1h] BYREF
  LPVOID pMem; // [rsp+48h] [rbp-99h] BYREF
  _QWORD v36[2]; // [rsp+50h] [rbp-91h] BYREF
  _DWORD v37[32]; // [rsp+60h] [rbp-81h] BYREF

  *(_QWORD *)this = &CAppContainer::`vftable';
  *((_QWORD *)this + 146) = 0;
  v36[0] = L"appSchemaVersion";
  v5 = (void **)((char *)this + 544);
  *((_DWORD *)this + 134) = 0;
  v36[1] = L"displayName";
  v6 = (void **)((char *)this + 552);
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  v7 = (struct _GUID *)((char *)this + 560);
  *((_QWORD *)this + 66) = 0;
  v8 = (unsigned __int16 *)((char *)this + 8);
  v37[2] = 7;
  *((_OWORD *)this + 35) = 0;
  v37[10] = 7;
  v37[12] = 7;
  v37[22] = 7;
  v11 = 260;
  v37[24] = 7;
  v12 = 2147483646;
  *(_QWORD *)((char *)this + 1140) = 0;
  v13 = (_WORD *)((char *)this + 8);
  *((_DWORD *)this + 284) = 0;
  *((_DWORD *)this + 294) = 1;
  *((_QWORD *)this + 144) = 0;
  *((_QWORD *)this + 145) = a4;
  v32 = 0;
  v33 = 0;
  *a5 = 0;
  v37[0] = 5;
  v37[4] = 1;
  v37[14] = 200;
  v37[20] = 16;
  do
  {
    if ( !v12 )
      break;
    if ( !*a3 )
      break;
    *v13++ = *a3++;
    --v12;
    --v11;
  }
  while ( v11 );
  v14 = v13 - 1;
  if ( v11 )
    v14 = v13;
  *v14 = 0;
  *a5 = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
  {
    v15 = 101;
    v16 = (gCsOptions & 1) != 0 ? GetADsOpenObjectFlags() | 0x21 : 101;
    v17 = DSServerOpenDSObject((CAppContainer *)((char *)this + 1168), v8, v16, v5);
    *a5 = v17;
    if ( v17 >= 0 )
    {
      v18 = ADSIGetObjectAttributes(*v5, v36, 2, &v33, &v32);
      *a5 = v18;
      if ( v18 >= 0 )
      {
        v11 = v32;
        v19 = v33;
        if ( !v32 )
        {
          *a5 = -2147221145;
          goto LABEL_33;
        }
        PropertyFromAttr = GetPropertyFromAttr(v33, v32, L"appSchemaVersion");
        v11 = v32;
        v19 = v33;
        if ( PropertyFromAttr >= v32
          || (v21 = PropertyFromAttr, v33[v21].dwADsType != ADSTYPE_INTEGER)
          || !v33[v21].dwNumValues
          || v33[v21].pADsValues->Boolean != 1740 )
        {
          *a5 = -2147221145;
        }
        if ( *a5 < 0 )
          goto LABEL_33;
        v22 = GetPropertyFromAttr(v19, v11, L"displayName");
        if ( v22 < v32 )
        {
          v23 = v22;
          pMem = 0;
          v34 = 0;
          if ( v33[v23].dwNumValues )
            DNString = v33[v23].pADsValues->DNString;
          else
            DNString = 0;
          BuildADsParentPath(DNString, (unsigned __int16 **)&pMem, (unsigned __int16 **)&v34);
          if ( pMem )
            FreeADsMem(pMem);
          v25 = v34;
          if ( v34 )
          {
            v26 = -1;
            do
              ++v26;
            while ( *((_WORD *)v34 + v26) );
            if ( v26 == 41 )
            {
              GUIDFromString((const unsigned __int16 *)v34 + 4, v7);
              v25 = v34;
            }
            FreeADsMem(v25);
          }
        }
      }
      v19 = v33;
LABEL_33:
      if ( v19 )
        FreeADsMem(v19);
      if ( *a5 >= 0 )
      {
        BuildADsPathFromParent(v8, L"CN=Packages", (unsigned __int16 **)this + 66);
        v27 = (gCsOptions & 1) == 0;
        *v6 = 0;
        if ( !v27 )
          v15 = GetADsOpenObjectFlags() | 0x21;
        v28 = DSServerOpenDSObject(
                (CAppContainer *)((char *)this + 1168),
                *((const unsigned __int16 **)this + 66),
                v15,
                v6);
        *a5 = v28;
        if ( v28 >= 0 )
        {
          v29 = ADSISetSearchPreference(*v6, v37, 3);
          *a5 = v29;
          if ( v29 >= 0 )
          {
            *((_DWORD *)this + 134) = 1;
            *((_DWORD *)this + 294) = 1;
            v30 = AllocGpoPathFromClassStorePath(v8);
            *((_QWORD *)this + 144) = v30;
            if ( !v30 )
              *a5 = -2147024882;
          }
        }
      }
    }
  }
  *a5 = RemapErrorCode(*a5, (const unsigned __int16 *)v11);
  return this;
}

```

## disassembly

```asm
0x18001c258  push    rbp
0x18001c25a  push    rbx
0x18001c25b  push    rsi
0x18001c25c  push    rdi
0x18001c25d  push    r12
0x18001c25f  push    r13
0x18001c261  push    r14
0x18001c263  push    r15
0x18001c265  lea     rbp, [rsp-17h]
0x18001c26a  sub     rsp, 0F8h
0x18001c271  mov     rax, cs:__security_cookie
0x18001c278  xor     rax, rsp
0x18001c27b  mov     [rbp+4Fh+var_50], rax
0x18001c27f  mov     rbx, [rbp+4Fh+arg_20]
0x18001c283  lea     rax, ??_7CAppContainer@@6B@; const CAppContainer::`vftable'
0x18001c28a  xor     r11d, r11d
0x18001c28d  mov     [rcx], rax
0x18001c290  mov     [rcx+490h], r11
0x18001c297  lea     rax, aAppschemaversi; "appSchemaVersion"
0x18001c29e  mov     [rsp+130h+var_E0], rax
0x18001c2a3  lea     r14, [rcx+220h]
0x18001c2aa  lea     rax, aDisplayname; "displayName"
0x18001c2b1  mov     [rcx+218h], r11d
0x18001c2b8  mov     [rsp+130h+var_D8], rax
0x18001c2bd  lea     r15, [rcx+228h]
0x18001c2c4  lea     eax, [r11+7]
0x18001c2c8  mov     [r14], r11
0x18001c2cb  mov     [r15], r11
0x18001c2ce  lea     r13, [rcx+230h]
0x18001c2d5  mov     [rcx+210h], r11
0x18001c2dc  lea     r12, [rcx+8]
0x18001c2e0  xorps   xmm0, xmm0
0x18001c2e3  mov     [rbp+4Fh+var_C8], eax
0x18001c2e6  movups  xmmword ptr [r13+0], xmm0
0x18001c2eb  mov     [rbp+4Fh+var_A8], eax
0x18001c2ee  mov     r10, r8
0x18001c2f1  mov     [rbp+4Fh+var_A0], eax
0x18001c2f4  mov     rdi, rcx
0x18001c2f7  mov     [rbp+4Fh+var_78], eax
0x18001c2fa  mov     edx, 104h
0x18001c2ff  mov     [rbp+4Fh+var_70], eax
0x18001c302  mov     r8d, 7FFFFFFEh
0x18001c308  mov     [rcx+474h], r11
0x18001c30f  mov     rax, r12
0x18001c312  mov     [rcx+470h], r11d
0x18001c319  mov     dword ptr [rcx+498h], 1
0x18001c323  mov     [rcx+480h], r11
0x18001c32a  mov     [rcx+488h], r9
0x18001c331  mov     [rsp+130h+var_100], r11d
0x18001c336  mov     [rsp+130h+var_F8], r11
0x18001c33b  mov     [rbx], r11d
0x18001c33e  mov     [rsp+130h+var_D0], 5
0x18001c346  mov     [rbp+4Fh+var_C0], 1
0x18001c34d  mov     [rbp+4Fh+var_98], 0C8h
0x18001c354  mov     [rbp+4Fh+var_80], 10h
0x18001c35b  test    r8, r8
0x18001c35e  jz      short loc_18001C37D
0x18001c360  movzx   ecx, word ptr [r10]
0x18001c364  test    cx, cx
0x18001c367  jz      short loc_18001C37D
0x18001c369  mov     [rax], cx
0x18001c36c  add     r10, 2
0x18001c370  add     rax, 2
0x18001c374  dec     r8
0x18001c377  sub     rdx, 1
0x18001c37b  jnz     short loc_18001C35B
0x18001c37d  test    rdx, rdx
0x18001c380  lea     rcx, [rax-2]
0x18001c384  cmovnz  rcx, rax
0x18001c388  mov     rax, rdx
0x18001c38b  neg     rax
0x18001c38e  mov     [rcx], r11w
0x18001c392  sbb     ecx, ecx
0x18001c394  not     ecx
0x18001c396  and     ecx, 8007007Ah
0x18001c39c  mov     [rbx], ecx
0x18001c39e  test    rdx, rdx
0x18001c3a1  jz      loc_18001C5AB
0x18001c3a7  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001c3ae  mov     esi, 65h ; 'e'
0x18001c3b3  jz      short loc_18001C3BF
0x18001c3b5  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001c3ba  or      eax, 21h
0x18001c3bd  jmp     short loc_18001C3C1
0x18001c3bf  mov     eax, esi
0x18001c3c1  mov     r9, r14; void **
0x18001c3c4  lea     rcx, [rdi+490h]; struct CServerContext *
0x18001c3cb  mov     r8d, eax; int
0x18001c3ce  mov     rdx, r12; unsigned __int16 *
0x18001c3d1  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001c3d6  mov     [rbx], eax
0x18001c3d8  test    eax, eax
0x18001c3da  js      loc_18001C5AB
0x18001c3e0  mov     rcx, [r14]
0x18001c3e3  lea     rax, [rsp+130h+var_100]
0x18001c3e8  lea     r9, [rsp+130h+var_F8]
0x18001c3ed  mov     [rsp+130h+var_110], rax
0x18001c3f2  mov     r8d, 2
0x18001c3f8  lea     rdx, [rsp+130h+var_E0]
0x18001c3fd  call    cs:__imp_ADSIGetObjectAttributes
0x18001c403  xor     r14d, r14d
0x18001c406  mov     [rbx], eax
0x18001c408  test    eax, eax
0x18001c40a  js      loc_18001C4FC
0x18001c410  mov     edx, [rsp+130h+var_100]; unsigned int
0x18001c414  mov     rcx, [rsp+130h+var_F8]; struct _ads_attr_info *
0x18001c419  test    edx, edx
0x18001c41b  jz      loc_18001C5D7
0x18001c421  lea     r8, aAppschemaversi; "appSchemaVersion"
0x18001c428  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001c42d  mov     edx, [rsp+130h+var_100]; unsigned int
0x18001c431  mov     rcx, [rsp+130h+var_F8]; struct _ads_attr_info *
0x18001c436  cmp     eax, edx
0x18001c438  jnb     short loc_18001C45C
0x18001c43a  mov     eax, eax
0x18001c43c  shl     rax, 5
0x18001c440  cmp     dword ptr [rax+rcx+0Ch], 7
0x18001c445  jnz     short loc_18001C45C
0x18001c447  cmp     [rax+rcx+18h], r14d
0x18001c44c  jz      short loc_18001C45C
0x18001c44e  mov     rax, [rax+rcx+10h]
0x18001c453  cmp     dword ptr [rax+8], 6CCh
0x18001c45a  jz      short loc_18001C462
0x18001c45c  mov     dword ptr [rbx], 80040167h
0x18001c462  cmp     [rbx], r14d
0x18001c465  jl      loc_18001C501
0x18001c46b  lea     r8, aDisplayname; "displayName"
0x18001c472  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001c477  cmp     eax, [rsp+130h+var_100]
0x18001c47b  jnb     short loc_18001C4FC
0x18001c47d  mov     rcx, [rsp+130h+var_F8]
0x18001c482  mov     eax, eax
0x18001c484  shl     rax, 5
0x18001c488  mov     [rsp+130h+pMem], r14
0x18001c48d  mov     [rsp+130h+var_F0], r14
0x18001c492  cmp     [rax+rcx+18h], r14d
0x18001c497  jz      short loc_18001C4A4
0x18001c499  mov     rax, [rax+rcx+10h]
0x18001c49e  mov     rcx, [rax+8]
0x18001c4a2  jmp     short loc_18001C4A7
0x18001c4a4  mov     rcx, r14
0x18001c4a7  lea     r8, [rsp+130h+var_F0]
0x18001c4ac  lea     rdx, [rsp+130h+pMem]
0x18001c4b1  call    cs:__imp_?BuildADsParentPath@@YAJPEAGPEAPEAG1@Z; BuildADsParentPath(ushort *,ushort * *,ushort * *)
0x18001c4b7  mov     rcx, [rsp+130h+pMem]; pMem
0x18001c4bc  test    rcx, rcx
0x18001c4bf  jz      short loc_18001C4C7
0x18001c4c1  call    cs:__imp_FreeADsMem
0x18001c4c7  mov     rcx, [rsp+130h+var_F0]
0x18001c4cc  test    rcx, rcx
0x18001c4cf  jz      short loc_18001C4FC
0x18001c4d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c4d5  inc     rax
0x18001c4d8  cmp     [rcx+rax*2], r14w
0x18001c4dd  jnz     short loc_18001C4D5
0x18001c4df  cmp     rax, 29h ; ')'
0x18001c4e3  jnz     short loc_18001C4F6
0x18001c4e5  add     rcx, 8; unsigned __int16 *
0x18001c4e9  mov     rdx, r13; struct _GUID *
0x18001c4ec  call    ?GUIDFromString@@YAXPEBGPEAU_GUID@@@Z; GUIDFromString(ushort const *,_GUID *)
0x18001c4f1  mov     rcx, [rsp+130h+var_F0]; pMem
0x18001c4f6  call    cs:__imp_FreeADsMem
0x18001c4fc  mov     rcx, [rsp+130h+var_F8]; pMem
0x18001c501  test    rcx, rcx
0x18001c504  jz      short loc_18001C50C
0x18001c506  call    cs:__imp_FreeADsMem
0x18001c50c  cmp     [rbx], r14d
0x18001c50f  jl      loc_18001C5AB
0x18001c515  lea     r14, [rdi+210h]
0x18001c51c  mov     rcx, r12
0x18001c51f  mov     r8, r14
0x18001c522  lea     rdx, aCnPackages; "CN=Packages"
0x18001c529  call    cs:__imp_?BuildADsPathFromParent@@YAJPEAG0PEAPEAG@Z; BuildADsPathFromParent(ushort *,ushort *,ushort * *)
0x18001c52f  xor     r13d, r13d
0x18001c532  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001c539  mov     [r15], r13
0x18001c53c  jz      short loc_18001C548
0x18001c53e  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001c543  mov     esi, eax
0x18001c545  or      esi, 21h
0x18001c548  mov     rdx, [r14]; unsigned __int16 *
0x18001c54b  lea     rcx, [rdi+490h]; struct CServerContext *
0x18001c552  mov     r9, r15; void **
0x18001c555  mov     r8d, esi; int
0x18001c558  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001c55d  mov     [rbx], eax
0x18001c55f  test    eax, eax
0x18001c561  js      short loc_18001C5AB
0x18001c563  mov     rcx, [r15]
0x18001c566  lea     rdx, [rsp+130h+var_D0]
0x18001c56b  mov     r8d, 3
0x18001c571  call    cs:__imp_ADSISetSearchPreference
0x18001c577  mov     [rbx], eax
0x18001c579  test    eax, eax
0x18001c57b  js      short loc_18001C5AB
0x18001c57d  mov     rcx, r12; unsigned __int16 *
0x18001c580  mov     dword ptr [rdi+218h], 1
0x18001c58a  mov     dword ptr [rdi+498h], 1
0x18001c594  call    ?AllocGpoPathFromClassStorePath@@YAPEAGPEBG@Z; AllocGpoPathFromClassStorePath(ushort const *)
0x18001c599  mov     [rdi+480h], rax
0x18001c5a0  test    rax, rax
0x18001c5a3  jnz     short loc_18001C5AB
0x18001c5a5  mov     dword ptr [rbx], 8007000Eh
0x18001c5ab  mov     ecx, [rbx]; int
0x18001c5ad  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18001c5b2  mov     [rbx], eax
0x18001c5b4  mov     rax, rdi
0x18001c5b7  mov     rcx, [rbp+4Fh+var_50]
0x18001c5bb  xor     rcx, rsp; StackCookie
0x18001c5be  call    __security_check_cookie
0x18001c5c3  add     rsp, 0F8h
0x18001c5ca  pop     r15
0x18001c5cc  pop     r14
0x18001c5ce  pop     r13
0x18001c5d0  pop     r12
0x18001c5d2  pop     rdi
0x18001c5d3  pop     rsi
0x18001c5d4  pop     rbx
0x18001c5d5  pop     rbp
0x18001c5d6  retn
0x18001c5d7  mov     dword ptr [rbx], 80040167h
0x18001c5dd  jmp     loc_18001C501
```
