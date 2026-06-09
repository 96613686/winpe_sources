# CClassContainer::CClassContainer(CServerContext *,ushort const *,long *)

- ea: `0x18001e8ac`
- end: `0x18001ec3a`
- name: `??0CClassContainer@@QEAA@PEAVCServerContext@@PEBGPEAJ@Z`
- size: `910`
- prototype: `CClassContainer *__fastcall(CClassContainer *this, const unsigned __int16 **, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config`

## callers

- `0x180020430`

## callees

- `0x180002b14`
- `0x18001d130`
- `0x18001e8ac`
- `0x1800223b4`
- `0x18002350c`
- `0x180024218`
- `0x180024458`
- `0x180024b90`

## import_xrefs

- `adsldpc!ADSIGetObjectAttributes` at `0x18001ea52`
- `adsldpc!ADSIGetObjectAttributes` at `0x18001ea52`
- `adsldpc!BuildADsPathFromParent` at `0x18001eba4`
- `adsldpc!BuildADsPathFromParent` at `0x18001eba4`
- `adsldpc!ADSISetSearchPreference` at `0x18001ebf1`
- `adsldpc!ADSISetSearchPreference` at `0x18001ebf1`
- `adsldpc!BuildADsParentPath` at `0x18001eafb`
- `adsldpc!BuildADsParentPath` at `0x18001eafb`
- `adsldpc!FreeADsMem` at `0x18001eb5a`
- `adsldpc!FreeADsMem` at `0x18001eb69`
- `adsldpc!FreeADsMem` at `0x18001eb7f`
- `adsldpc!FreeADsMem` at `0x18001eb5a`
- `adsldpc!FreeADsMem` at `0x18001eb69`
- `adsldpc!FreeADsMem` at `0x18001eb7f`

## pseudocode

```c
CClassContainer *__fastcall CClassContainer::CClassContainer(
        CClassContainer *this,
        const unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned __int16 **v4; // r14
  void **v5; // rsi
  void **v6; // r12
  struct _GUID *v7; // r13
  _WORD *v11; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  _WORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // r15d
  unsigned __int16 *v18; // rax
  unsigned int v19; // r14d
  int v20; // eax
  int v21; // eax
  int v22; // eax
  unsigned __int16 *v23; // rsi
  unsigned int PropertyFromAttr; // eax
  unsigned int v25; // edx
  struct _ads_attr_info *v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // eax
  __int64 v29; // rax
  unsigned __int16 *DNString; // rcx
  void *v31; // rcx
  void *v32; // rax
  __int64 v33; // rax
  int GPOName; // eax
  bool v35; // zf
  int v36; // eax
  int v37; // eax
  LPVOID v39; // [rsp+30h] [rbp-59h] BYREF
  LPVOID pMem; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v41; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v42[3]; // [rsp+48h] [rbp-41h] BYREF
  _DWORD v43[32]; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v44; // [rsp+F0h] [rbp+67h] BYREF
  struct _ads_attr_info *v45; // [rsp+108h] [rbp+7Fh] BYREF

  v43[0] = 5;
  *((_QWORD *)this + 67) = 0;
  *(_QWORD *)this = &CClassContainer::`vftable';
  v4 = (unsigned __int16 **)((char *)this + 592);
  *((_QWORD *)this + 74) = 0;
  v42[0] = L"appSchemaVersion";
  v5 = (void **)((char *)this + 552);
  *((_DWORD *)this + 136) = 0;
  v6 = (void **)((char *)this + 560);
  *((_QWORD *)this + 66) = 0;
  v7 = (struct _GUID *)((char *)this + 576);
  *((_QWORD *)this + 71) = 0;
  v42[1] = L"displayName";
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  v43[2] = 7;
  v43[10] = 7;
  v11 = (_WORD *)((char *)this + 8);
  v43[12] = 7;
  v45 = 0;
  v44 = 0;
  v13 = 2147483646;
  v43[4] = 1;
  v14 = 260;
  v43[14] = 200;
  *v7 = 0;
  do
  {
    if ( !v13 )
      break;
    if ( !*a3 )
      break;
    *v11++ = *a3++;
    --v13;
    --v14;
  }
  while ( v14 );
  v15 = v11 - 1;
  v16 = v14 == 0 ? 0x8007007A : 0;
  *a4 = v16;
  if ( v14 )
    v15 = v11;
  *v15 = 0;
  if ( v14 )
  {
    v17 = -2147024882;
    if ( !a2 )
      goto LABEL_13;
    if ( !*a2 || (v18 = StringDuplicate(*a2), *v4 = v18, v16 = 2147942414LL, v18) )
      v16 = 0;
    *a4 = v16;
    if ( (int)v16 >= 0 )
    {
LABEL_13:
      v19 = 101;
      v20 = (gCsOptions & 1) != 0 ? GetADsOpenObjectFlags() | 0x21 : 101;
      v21 = DSServerOpenDSObject((CClassContainer *)((char *)this + 592), (const unsigned __int16 *)this + 4, v20, v5);
      *a4 = v21;
      v16 = (unsigned int)v21;
      if ( v21 >= 0 )
      {
        v22 = ADSIGetObjectAttributes(*v5, v42, 2, &v45, &v44);
        v23 = 0;
        *a4 = v22;
        if ( v22 >= 0 && v44 )
        {
          PropertyFromAttr = GetPropertyFromAttr(v45, v44, L"appSchemaVersion");
          v25 = v44;
          v26 = v45;
          if ( PropertyFromAttr < v44 )
          {
            v27 = PropertyFromAttr;
            if ( !v45[v27].dwNumValues || v45[v27].pADsValues->Boolean != 1740 )
              *a4 = -2147221145;
          }
          if ( (*a4 & 0x80000000) != 0 )
            goto LABEL_41;
          v41 = 0;
          v28 = GetPropertyFromAttr(v26, v25, L"displayName");
          if ( v28 < v44 )
          {
            v29 = v28;
            pMem = 0;
            v39 = 0;
            if ( v45[v29].dwNumValues )
              DNString = v45[v29].pADsValues->DNString;
            else
              DNString = 0;
            BuildADsParentPath(DNString, (unsigned __int16 **)&pMem, (unsigned __int16 **)&v39);
            v31 = v39;
            v32 = pMem;
            if ( v39 && pMem )
            {
              v33 = -1;
              do
                ++v33;
              while ( *((_WORD *)v39 + v33) );
              if ( v33 == 41 )
                GUIDFromString((const unsigned __int16 *)v39 + 4, v7);
              GPOName = CClassContainer::GetGPOName(this, &v41);
              v23 = v41;
              v17 = GPOName;
              v32 = pMem;
              v31 = v39;
            }
            *a4 = v17;
            if ( v32 )
            {
              FreeADsMem(v32);
              v31 = v39;
            }
            if ( v31 )
              FreeADsMem(v31);
          }
          *((_QWORD *)this + 71) = v23;
        }
        v26 = v45;
LABEL_41:
        if ( v26 )
          FreeADsMem(v26);
        v16 = *a4;
        if ( (int)v16 >= 0 )
        {
          BuildADsPathFromParent((unsigned __int16 *)this + 4, L"CN=Packages", (unsigned __int16 **)this + 66);
          v35 = (gCsOptions & 1) == 0;
          *v6 = 0;
          if ( !v35 )
            v19 = GetADsOpenObjectFlags() | 0x21;
          v36 = DSServerOpenDSObject(
                  (CClassContainer *)((char *)this + 592),
                  *((const unsigned __int16 **)this + 66),
                  v19,
                  v6);
          *a4 = v36;
          v16 = (unsigned int)v36;
          if ( v36 >= 0 )
          {
            v37 = ADSISetSearchPreference(*v6, v43, 2);
            *a4 = v37;
            v16 = (unsigned int)v37;
            if ( v37 >= 0 )
            {
              *((_DWORD *)this + 136) = 1;
              *((_DWORD *)this + 150) = 1;
            }
          }
        }
      }
    }
  }
  *a4 = RemapErrorCode(v16, (const unsigned __int16 *)v16);
  return this;
}

```

## disassembly

```asm
0x18001e8ac  mov     [rsp-8+arg_8], rbx
0x18001e8b1  push    rbp
0x18001e8b2  push    rsi
0x18001e8b3  push    rdi
0x18001e8b4  push    r12
0x18001e8b6  push    r13
0x18001e8b8  push    r14
0x18001e8ba  push    r15
0x18001e8bc  lea     rbp, [rsp-27h]
0x18001e8c1  sub     rsp, 0B0h
0x18001e8c8  xor     r15d, r15d
0x18001e8cb  mov     [rbp+57h+var_80], 5
0x18001e8d2  lea     rax, ??_7CClassContainer@@6B@; const CClassContainer::`vftable'
0x18001e8d9  mov     [rcx+218h], r15
0x18001e8e0  mov     [rcx], rax
0x18001e8e3  lea     r14, [rcx+250h]
0x18001e8ea  mov     [r14], r15
0x18001e8ed  lea     rax, aAppschemaversi; "appSchemaVersion"
0x18001e8f4  mov     [rbp+57h+var_98], rax
0x18001e8f8  lea     rsi, [rcx+228h]
0x18001e8ff  lea     rax, aDisplayname; "displayName"
0x18001e906  mov     [rcx+220h], r15d
0x18001e90d  lea     r12, [rcx+230h]
0x18001e914  mov     [rcx+210h], r15
0x18001e91b  lea     r13, [rcx+240h]
0x18001e922  mov     [rcx+238h], r15
0x18001e929  mov     [rbp+57h+var_90], rax
0x18001e92d  mov     rbx, r9
0x18001e930  lea     eax, [r15+7]
0x18001e934  mov     [rsi], r15
0x18001e937  xorps   xmm0, xmm0
0x18001e93a  mov     [r12], r15
0x18001e93e  mov     r10, r8
0x18001e941  mov     [rbp+57h+var_78], eax
0x18001e944  mov     rdi, rcx
0x18001e947  mov     [rbp+57h+var_58], eax
0x18001e94a  lea     r9, [rcx+8]
0x18001e94e  mov     [rbp+57h+var_50], eax
0x18001e951  mov     r11, rdx
0x18001e954  mov     [rbp+57h+arg_18], r15
0x18001e958  mov     [rbp+57h+arg_0], r15d
0x18001e95c  mov     ecx, 7FFFFFFEh
0x18001e961  mov     [rbp+57h+var_70], 1
0x18001e968  mov     r8d, 104h
0x18001e96e  mov     [rbp+57h+var_48], 0C8h
0x18001e975  movups  xmmword ptr [r13+0], xmm0
0x18001e97a  test    rcx, rcx
0x18001e97d  jz      short loc_18001E99D
0x18001e97f  movzx   eax, word ptr [r10]
0x18001e983  test    ax, ax
0x18001e986  jz      short loc_18001E99D
0x18001e988  mov     [r9], ax
0x18001e98c  add     r10, 2
0x18001e990  add     r9, 2
0x18001e994  dec     rcx
0x18001e997  sub     r8, 1
0x18001e99b  jnz     short loc_18001E97A
0x18001e99d  mov     rax, r8
0x18001e9a0  lea     rcx, [r9-2]
0x18001e9a4  neg     rax
0x18001e9a7  sbb     edx, edx
0x18001e9a9  not     edx
0x18001e9ab  and     edx, 8007007Ah
0x18001e9b1  test    r8, r8
0x18001e9b4  mov     [rbx], edx
0x18001e9b6  cmovnz  rcx, r9
0x18001e9ba  mov     [rcx], r15w
0x18001e9be  jz      loc_18001EC13
0x18001e9c4  xor     r8d, r8d
0x18001e9c7  mov     r15d, 8007000Eh
0x18001e9cd  test    r11, r11
0x18001e9d0  jz      short loc_18001E9FA
0x18001e9d2  mov     rcx, [r11]; unsigned __int16 *
0x18001e9d5  test    rcx, rcx
0x18001e9d8  jz      short loc_18001E9ED
0x18001e9da  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18001e9df  xor     r8d, r8d
0x18001e9e2  mov     [r14], rax
0x18001e9e5  mov     edx, r15d
0x18001e9e8  test    rax, rax
0x18001e9eb  jz      short loc_18001E9F0
0x18001e9ed  mov     edx, r8d
0x18001e9f0  mov     [rbx], edx
0x18001e9f2  test    edx, edx
0x18001e9f4  js      loc_18001EC13
0x18001e9fa  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001ea01  mov     r14d, 65h ; 'e'
0x18001ea07  jz      short loc_18001EA13
0x18001ea09  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001ea0e  or      eax, 21h
0x18001ea11  jmp     short loc_18001EA16
0x18001ea13  mov     eax, r14d
0x18001ea16  mov     r9, rsi; void **
0x18001ea19  lea     rdx, [rdi+8]; unsigned __int16 *
0x18001ea1d  mov     r8d, eax; int
0x18001ea20  lea     rcx, [rdi+250h]; struct CServerContext *
0x18001ea27  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001ea2c  mov     [rbx], eax
0x18001ea2e  mov     edx, eax
0x18001ea30  test    eax, eax
0x18001ea32  js      loc_18001EC13
0x18001ea38  mov     rcx, [rsi]
0x18001ea3b  lea     rax, [rbp+57h+arg_0]
0x18001ea3f  lea     r9, [rbp+57h+arg_18]
0x18001ea43  mov     [rsp+0E0h+var_C0], rax
0x18001ea48  mov     r8d, 2
0x18001ea4e  lea     rdx, [rbp+57h+var_98]
0x18001ea52  call    cs:__imp_ADSIGetObjectAttributes
0x18001ea58  xor     esi, esi
0x18001ea5a  mov     [rbx], eax
0x18001ea5c  test    eax, eax
0x18001ea5e  js      loc_18001EB76
0x18001ea64  mov     edx, [rbp+57h+arg_0]; unsigned int
0x18001ea67  test    edx, edx
0x18001ea69  jz      loc_18001EB76
0x18001ea6f  mov     rcx, [rbp+57h+arg_18]; struct _ads_attr_info *
0x18001ea73  lea     r8, aAppschemaversi; "appSchemaVersion"
0x18001ea7a  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001ea7f  mov     edx, [rbp+57h+arg_0]; unsigned int
0x18001ea82  mov     rcx, [rbp+57h+arg_18]; struct _ads_attr_info *
0x18001ea86  cmp     eax, edx
0x18001ea88  jnb     short loc_18001EAAA
0x18001ea8a  mov     eax, eax
0x18001ea8c  shl     rax, 5
0x18001ea90  cmp     [rax+rcx+18h], esi
0x18001ea94  jz      short loc_18001EAA4
0x18001ea96  mov     rax, [rax+rcx+10h]
0x18001ea9b  cmp     dword ptr [rax+8], 6CCh
0x18001eaa2  jz      short loc_18001EAAA
0x18001eaa4  mov     dword ptr [rbx], 80040167h
0x18001eaaa  cmp     [rbx], esi
0x18001eaac  jl      loc_18001EB7A
0x18001eab2  lea     r8, aDisplayname; "displayName"
0x18001eab9  mov     [rbp+57h+var_A0], rsi
0x18001eabd  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001eac2  cmp     eax, [rbp+57h+arg_0]
0x18001eac5  jnb     loc_18001EB6F
0x18001eacb  mov     rcx, [rbp+57h+arg_18]
0x18001eacf  xor     edx, edx
0x18001ead1  mov     eax, eax
0x18001ead3  shl     rax, 5
0x18001ead7  mov     [rbp+57h+pMem], rdx
0x18001eadb  mov     [rbp+57h+var_B0], rdx
0x18001eadf  cmp     [rax+rcx+18h], edx
0x18001eae3  jz      short loc_18001EAF0
0x18001eae5  mov     rax, [rax+rcx+10h]
0x18001eaea  mov     rcx, [rax+8]
0x18001eaee  jmp     short loc_18001EAF3
0x18001eaf0  mov     rcx, rdx
0x18001eaf3  lea     r8, [rbp+57h+var_B0]
0x18001eaf7  lea     rdx, [rbp+57h+pMem]
0x18001eafb  call    cs:__imp_?BuildADsParentPath@@YAJPEAGPEAPEAG1@Z; BuildADsParentPath(ushort *,ushort * *,ushort * *)
0x18001eb01  mov     rcx, [rbp+57h+var_B0]
0x18001eb05  xor     edx, edx
0x18001eb07  mov     rax, [rbp+57h+pMem]
0x18001eb0b  test    rcx, rcx
0x18001eb0e  jz      short loc_18001EB4F
0x18001eb10  test    rax, rax
0x18001eb13  jz      short loc_18001EB4F
0x18001eb15  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eb19  inc     rax
0x18001eb1c  cmp     [rcx+rax*2], dx
0x18001eb20  jnz     short loc_18001EB19
0x18001eb22  cmp     rax, 29h ; ')'
0x18001eb26  jnz     short loc_18001EB34
0x18001eb28  add     rcx, 8; unsigned __int16 *
0x18001eb2c  mov     rdx, r13; struct _GUID *
0x18001eb2f  call    ?GUIDFromString@@YAXPEBGPEAU_GUID@@@Z; GUIDFromString(ushort const *,_GUID *)
0x18001eb34  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x18001eb38  mov     rcx, rdi; this
0x18001eb3b  call    ?GetGPOName@CClassContainer@@AEAAJPEAPEAG@Z; CClassContainer::GetGPOName(ushort * *)
0x18001eb40  mov     rsi, [rbp+57h+var_A0]
0x18001eb44  mov     r15d, eax
0x18001eb47  mov     rax, [rbp+57h+pMem]
0x18001eb4b  mov     rcx, [rbp+57h+var_B0]
0x18001eb4f  mov     [rbx], r15d
0x18001eb52  test    rax, rax
0x18001eb55  jz      short loc_18001EB64
0x18001eb57  mov     rcx, rax; pMem
0x18001eb5a  call    cs:__imp_FreeADsMem
0x18001eb60  mov     rcx, [rbp+57h+var_B0]; pMem
0x18001eb64  test    rcx, rcx
0x18001eb67  jz      short loc_18001EB6F
0x18001eb69  call    cs:__imp_FreeADsMem
0x18001eb6f  mov     [rdi+238h], rsi
0x18001eb76  mov     rcx, [rbp+57h+arg_18]; pMem
0x18001eb7a  test    rcx, rcx
0x18001eb7d  jz      short loc_18001EB85
0x18001eb7f  call    cs:__imp_FreeADsMem
0x18001eb85  mov     edx, [rbx]
0x18001eb87  test    edx, edx
0x18001eb89  js      loc_18001EC13
0x18001eb8f  lea     rsi, [rdi+210h]
0x18001eb96  mov     r8, rsi
0x18001eb99  lea     rdx, aCnPackages; "CN=Packages"
0x18001eba0  lea     rcx, [rdi+8]
0x18001eba4  call    cs:__imp_?BuildADsPathFromParent@@YAJPEAG0PEAPEAG@Z; BuildADsPathFromParent(ushort *,ushort *,ushort * *)
0x18001ebaa  xor     r15d, r15d
0x18001ebad  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001ebb4  mov     [r12], r15
0x18001ebb8  jz      short loc_18001EBC6
0x18001ebba  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001ebbf  mov     r14d, eax
0x18001ebc2  or      r14d, 21h
0x18001ebc6  mov     rdx, [rsi]; unsigned __int16 *
0x18001ebc9  lea     rcx, [rdi+250h]; struct CServerContext *
0x18001ebd0  mov     r9, r12; void **
0x18001ebd3  mov     r8d, r14d; int
0x18001ebd6  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001ebdb  mov     [rbx], eax
0x18001ebdd  mov     edx, eax
0x18001ebdf  test    eax, eax
0x18001ebe1  js      short loc_18001EC13
0x18001ebe3  mov     rcx, [r12]
0x18001ebe7  lea     rdx, [rbp+57h+var_80]
0x18001ebeb  mov     r8d, 2
0x18001ebf1  call    cs:__imp_ADSISetSearchPreference
0x18001ebf7  mov     [rbx], eax
0x18001ebf9  mov     edx, eax; unsigned __int16 *
0x18001ebfb  test    eax, eax
0x18001ebfd  js      short loc_18001EC13
0x18001ebff  mov     dword ptr [rdi+220h], 1
0x18001ec09  mov     dword ptr [rdi+258h], 1
0x18001ec13  mov     ecx, edx; int
0x18001ec15  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18001ec1a  mov     [rbx], eax
0x18001ec1c  mov     rax, rdi
0x18001ec1f  mov     rbx, [rsp+0E0h+arg_8]
0x18001ec27  add     rsp, 0B0h
0x18001ec2e  pop     r15
0x18001ec30  pop     r14
0x18001ec32  pop     r13
0x18001ec34  pop     r12
0x18001ec36  pop     rdi
0x18001ec37  pop     rsi
0x18001ec38  pop     rbp
0x18001ec39  retn
```
