# VdbADO::OpenString(Vstring const *,VdbADOErrInfo *)

- ea: `0x18003ca20`
- end: `0x18003d158`
- name: `?OpenString@VdbADO@@QEAAFPEBVVstring@@PEAUVdbADOErrInfo@@@Z`
- size: `1848`
- prototype: `__int16 __fastcall(VdbADO *__hidden this, const struct Vstring *, struct VdbADOErrInfo *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003d560`

## callees

- `0x180002594`
- `0x180010888`
- `0x180038e20`
- `0x18003c5f0`
- `0x18003ca20`
- `0x18003d158`
- `0x180040fd0`
- `0x1800414c0`
- `0x1800838f0`
- `0x180133d30`
- `0x180133fd0`
- `0x180134070`
- `0x1801342d0`
- `0x180134920`
- `0x180134a20`
- `0x180135120`
- `0x18013f970`
- `0x1801519a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003cd93`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003d015`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003d043`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003d129`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003cd93`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003d015`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003d043`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003d129`
- `OLEAUT32!SysFreeString` at `0x18003ce0d`
- `OLEAUT32!SysFreeString` at `0x18003ce84`
- `OLEAUT32!SysFreeString` at `0x18003cfd8`
- `OLEAUT32!SysFreeString` at `0x18003ce0d`
- `OLEAUT32!SysFreeString` at `0x18003ce84`
- `OLEAUT32!SysFreeString` at `0x18003cfd8`
- `OLEAUT32!VariantInit` at `0x18003ceb3`
- `OLEAUT32!VariantInit` at `0x18003cecd`
- `OLEAUT32!VariantInit` at `0x18003cee3`
- `OLEAUT32!VariantInit` at `0x18003ceb3`
- `OLEAUT32!VariantInit` at `0x18003cecd`
- `OLEAUT32!VariantInit` at `0x18003cee3`

## string_xrefs

- `0x18003d058`: `Failed CoCreateInstance on ADOConnection.\n`
- `0x18003d0ac`: `Failed to create ADO Connection object.`
- `0x18003d0bc`: `FrontPage Server Extensions`
- `0x18003cd05`: `Microsoft Access Driver`
- `0x18003cd47`: `;Exclusive=1;ReadOnly=1`
- `0x18003ce21`: `Oracle`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall VdbADO::OpenString(VdbADO *this, const struct Vstring *a2, struct VdbADOErrInfo *a3)
{
  __int64 *v6; // r9
  int v7; // edi
  __int64 *v8; // rsi
  __int64 v9; // rbx
  int v10; // eax
  int v11; // r14d
  unsigned int v12; // edi
  const char *v13; // rdx
  const char *v14; // rcx
  int v17; // ebx
  int v18; // ebx
  const char *v19; // rcx
  __int64 v21; // r9
  __int64 v22; // r9
  __int64 v23; // r9
  __int64 v24; // r9
  __int64 v25; // r9
  const char *v26; // rcx
  __int64 v28; // rax
  int *v29; // rcx
  OLECHAR *v30; // rbx
  int v31; // eax
  int v32; // r14d
  const char *v33; // rcx
  int v35; // eax
  char v36; // cl
  unsigned __int16 v37; // bx
  OLECHAR *v38; // rbx
  Vstring *v39; // rcx
  int *v40; // rcx
  int *v41; // rcx
  char *v43; // rbx
  char *v44; // rcx
  int v45; // [rsp+20h] [rbp-E0h]
  char v46; // [rsp+40h] [rbp-C0h]
  LPVOID v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v50[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  RWCString *v54; // [rsp+80h] [rbp-80h]
  BSTR v55; // [rsp+88h] [rbp-78h] BYREF
  char *v56; // [rsp+90h] [rbp-70h] BYREF
  char *v57; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v58; // [rsp+A0h] [rbp-60h]
  int v59; // [rsp+A4h] [rbp-5Ch]
  char *v60; // [rsp+A8h] [rbp-58h] BYREF
  int v61; // [rsp+B0h] [rbp-50h]
  int v62; // [rsp+B4h] [rbp-4Ch]
  VARIANTARG v63; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v65; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v66; // [rsp+100h] [rbp+0h]
  _BYTE v67[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v68[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v69[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v70[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v71[24]; // [rsp+148h] [rbp+48h] BYREF
  VARIANTARG v72; // [rsp+160h] [rbp+60h] BYREF
  char v73; // [rsp+1C8h] [rbp+C8h]

  v66 = -2;
  if ( !VdbADO::IsADOInstalled() || *(_QWORD *)this || !a2 || !*(_DWORD *)(*(_QWORD *)a2 - 4LL) )
    return 0xFFFFFFFFLL;
  v47 = 0;
  v6 = qword_180182598;
  if ( dword_180275120 < 2 )
    v6 = (__int64 *)&qword_1801825A8;
  v7 = sub_180002594((int)&qword_1801825B8, 0, 1, (int)v6, &v47);
  if ( v7 >= 0 && v47 )
  {
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v47 + 104LL))(v47, 10);
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v47 + 248LL))(v47, 1);
    *(_QWORD *)this = v47;
    v8 = (__int64 *)((char *)this + 8);
    RWCString::operator=((char *)this + 8, a2);
    v46 = 0;
    RWCString::RWCString((RWCString *)&v51, "DRIVER=");
    v9 = v51;
    v10 = RWCString::index((char *)this + 8, v51, *(unsigned int *)(v51 - 4), 0, 1);
    if ( v10 == -1 )
    {
      v46 = 1;
    }
    else
    {
      v11 = v10;
      v12 = *(_DWORD *)(v9 - 4) + v10;
      if ( v12 < *(_DWORD *)(*v8 - 4) )
      {
        if ( *(_BYTE *)RWCString::operator[]((VdbADO *)((char *)this + 8)) == 123 )
        {
          v13 = "}";
          v14 = "}";
          while ( *v14++ )
            ;
        }
        else
        {
          v13 = ";";
          v14 = ";";
          while ( *v14++ )
            ;
        }
        v17 = RWCString::index((char *)this + 8, v13, (unsigned int)((_DWORD)v14 - (_DWORD)v13 - 1), v12, 0);
        if ( v17 == -1 || (v18 = v17 + 1, v18 == -1) )
          v18 = *(_DWORD *)(*v8 - 4);
        v57 = (char *)this + 8;
        v58 = v12;
        v59 = v18 - v12;
        Vstring::operator=((char *)this + 16, &v57);
        v19 = "DSN=";
        while ( *v19++ )
          ;
        if ( (unsigned int)RWCString::index(
                             (char *)this + 8,
                             "DSN=",
                             (unsigned int)v19 - (unsigned int)"DSN=" - 1,
                             0,
                             1) != -1 )
        {
          v60 = (char *)this + 8;
          v61 = v11;
          v62 = v18 - v11;
          RWCSubString::operator=(&v60, Class);
        }
        LOBYTE(v21) = 32;
        RWCString::strip((char *)this + 16, v67, 3, v21);
        Vstring::operator=((char *)this + 16, v67);
        LOBYTE(v22) = 123;
        RWCString::strip((char *)this + 16, v68, 1, v22);
        Vstring::operator=((char *)this + 16, v68);
        LOBYTE(v23) = 125;
        RWCString::strip((char *)this + 16, v69, 2, v23);
        Vstring::operator=((char *)this + 16, v69);
        LOBYTE(v24) = 32;
        RWCString::strip((char *)this + 16, v70, 3, v24);
        Vstring::operator=((char *)this + 16, v70);
        LOBYTE(v25) = 59;
        RWCString::strip((char *)this + 16, v71, 2, v25);
        Vstring::operator=((char *)this + 16, v71);
      }
    }
    v48 = *v8;
    _InterlockedAdd((volatile signed __int32 *)(v48 - 12), 1u);
    v73 = 0;
    v26 = "Microsoft Access Driver";
    while ( *v26++ )
      ;
    v54 = (VdbADO *)((char *)this + 16);
    if ( (unsigned int)RWCString::index(
                         (char *)this + 16,
                         "Microsoft Access Driver",
                         (unsigned int)v26 - (unsigned int)"Microsoft Access Driver" - 1,
                         0,
                         1) != -1 )
    {
      v28 = operator+(&v52, &v48, ";Exclusive=1;ReadOnly=1");
      RWCString::operator=(&v48, v28);
      v29 = (int *)(v52 - 12);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v52 - 12)) && v29 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v29);
        else
          free(v29);
      }
      v73 = 1;
    }
    sub_180010888(&bstrString, v48);
    v30 = bstrString;
    v31 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, int))(*(_QWORD *)v47 + 160LL))(
            v47,
            bstrString,
            0,
            0,
            -1);
    v32 = v31;
    if ( v31 < 0 )
    {
      sub_18003D158(this, a3, (unsigned int)v31);
      if ( !v73 )
      {
        RWCString::operator=(v54, (char *)Class);
        RWCString::operator=((VdbADO *)((char *)this + 8), (char *)Class);
        if ( v30 )
          SysFreeString(v30);
        v37 = -1;
        goto LABEL_64;
      }
      RWCString::operator=(&v48, (char *)this + 8);
    }
    if ( v30 )
      SysFreeString(v30);
    if ( *(_DWORD *)(*((_QWORD *)this + 2) - 4LL) )
    {
      v33 = "Oracle";
      while ( *v33++ )
        ;
      v35 = RWCString::index((char *)this + 16, "Oracle", (unsigned int)v33 - (unsigned int)"Oracle" - 1, 0, 1);
      v36 = v46;
      if ( v35 != -1 )
        v36 = 1;
    }
    else
    {
      v36 = v46;
    }
    if ( !v36 )
    {
LABEL_63:
      sub_18003D158(this, a3, (unsigned int)v32);
      v37 = 0;
LABEL_64:
      v40 = (int *)(v48 - 12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v48 - 12), 0xFFFFFFFF) == 1 && v40 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v40);
        else
          free(v40);
      }
      v41 = (int *)(v51 - 12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v51 - 12), 0xFFFFFFFF) == 1 && v41 != &dword_1802AFD50 )
      {
        if ( dword_1802B0018 )
          COWSAllocator::Free(v41);
        else
          free(v41);
      }
      return v37;
    }
    sub_180010888(&v55, "Select user from dual");
    VariantInit(&pvarg);
    pvarg.vt = 10;
    pvarg.lVal = -2147352572;
    VariantInit(&v63);
    v63.vt = 3;
    v63.lVal = 0;
    VariantInit(&v65);
    v49 = 0;
    v38 = v55;
    v32 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *, __int64, __int64 *))(*(_QWORD *)v47 + 128LL))(
            v47,
            v55,
            &pvarg,
            1,
            &v49);
    if ( v32 < 0 )
      goto LABEL_58;
    if ( !v49 )
    {
LABEL_61:
      if ( v38 )
        SysFreeString(v38);
      goto LABEL_63;
    }
    v32 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v49 + 160LL))(v49, v50);
    if ( v32 < 0
      || (v72 = v63,
          v32 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v49 + 504LL))(
                  v49,
                  &v72,
                  &v65),
          v32 < 0) )
    {
LABEL_58:
      sub_18003D158(this, a3, (unsigned int)v32);
    }
    else
    {
      v39 = (VdbADO *)((char *)this + 24);
      if ( v65.vt == 8 )
        Vstring::InitUnicode(v39, v65.bstrVal);
      else
        RWCString::operator=(v39, (char *)Class);
    }
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    goto LABEL_61;
  }
  LOWORD(v45) = 0;
  (*(void (__fastcall **)(void *, __int64, __int64, _QWORD, int, const char *))(off_1802AB3C8 + 80LL))(
    &off_1802AB3C8,
    946501430,
    117141511,
    0,
    v45,
    "Failed CoCreateInstance on ADOConnection.\n");
  if ( (unsigned __int8)sub_18003D158(this, a3, (unsigned int)v7) )
  {
    RWCString::RWCString((RWCString *)&v56, "(ADODB.Connection)");
    v43 = v56;
    RWCString::replace(
      (struct VdbADOErrInfo *)((char *)a3 + 8),
      *(_DWORD *)(*((_QWORD *)a3 + 1) - 4LL),
      0,
      v56,
      *((_DWORD *)v56 - 1));
    v44 = v43 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 - 3, 0xFFFFFFFF) == 1 && v44 != (char *)&dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v44);
      else
        free(v44);
    }
  }
  else if ( a3 )
  {
    RWCString::operator=((struct VdbADOErrInfo *)((char *)a3 + 8), "Failed to create ADO Connection object.");
    RWCString::operator=((struct VdbADOErrInfo *)((char *)a3 + 16), "FrontPage Server Extensions");
  }
  return 0xFFFF;
}

```

## disassembly

```asm
0x18003ca20  mov     rax, rsp
0x18003ca23  push    rbp
0x18003ca24  push    r12
0x18003ca26  push    r13
0x18003ca28  push    r14
0x18003ca2a  push    r15
0x18003ca2c  lea     rbp, [rsp-80h]
0x18003ca31  sub     rsp, 180h
0x18003ca38  mov     [rbp+0A0h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18003ca40  mov     [rax+8], rbx
0x18003ca44  mov     [rax+10h], rsi
0x18003ca48  mov     [rax+18h], rdi
0x18003ca4c  mov     r13, r8
0x18003ca4f  mov     rbx, rdx
0x18003ca52  mov     r15, rcx
0x18003ca55  call    ?IsADOInstalled@VdbADO@@SADXZ; VdbADO::IsADOInstalled(void)
0x18003ca5a  xor     r12d, r12d
0x18003ca5d  test    al, al
0x18003ca5f  jz      loc_18003D134
0x18003ca65  cmp     [r15], r12
0x18003ca68  jnz     loc_18003D134
0x18003ca6e  test    rbx, rbx
0x18003ca71  jz      loc_18003D134
0x18003ca77  mov     rax, [rbx]
0x18003ca7a  cmp     [rax-4], r12d
0x18003ca7e  jz      loc_18003D134
0x18003ca84  mov     [rsp+1A0h+var_158], r12
0x18003ca89  lea     rax, qword_1801825A8
0x18003ca90  lea     r9, qword_180182598
0x18003ca97  cmp     cs:dword_180275120, 2
0x18003ca9e  cmovl   r9, rax; int
0x18003caa2  lea     rax, [rsp+1A0h+var_158]
0x18003caa7  mov     [rsp+1A0h+var_180], rax; LPVOID *
0x18003caac  lea     r14d, [r12+1]
0x18003cab1  mov     r8d, r14d; int
0x18003cab4  xor     edx, edx; int
0x18003cab6  lea     rcx, qword_1801825B8; int
0x18003cabd  call    sub_180002594
0x18003cac2  mov     edi, eax
0x18003cac4  test    eax, eax
0x18003cac6  js      loc_18003D051
0x18003cacc  mov     rcx, [rsp+1A0h+var_158]
0x18003cad1  test    rcx, rcx
0x18003cad4  jz      loc_18003D051
0x18003cada  mov     rax, [rcx]
0x18003cadd  lea     edx, [r12+0Ah]
0x18003cae2  mov     rax, [rax+68h]
0x18003cae6  call    cs:__guard_dispatch_icall_fptr
0x18003caec  mov     rcx, [rsp+1A0h+var_158]
0x18003caf1  mov     rax, [rcx]
0x18003caf4  mov     edx, r14d
0x18003caf7  mov     rax, [rax+0F8h]
0x18003cafe  call    cs:__guard_dispatch_icall_fptr
0x18003cb04  mov     rax, [rsp+1A0h+var_158]
0x18003cb09  mov     [r15], rax
0x18003cb0c  lea     rsi, [r15+8]
0x18003cb10  mov     rdx, rbx
0x18003cb13  mov     rcx, rsi
0x18003cb16  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18003cb1b  mov     al, r12b
0x18003cb1e  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003cb22  lea     rdx, aDriver; "DRIVER="
0x18003cb29  lea     rcx, [rsp+1A0h+var_138]; this
0x18003cb2e  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x18003cb33  nop
0x18003cb34  mov     rbx, [rsp+1A0h+var_138]
0x18003cb39  mov     dword ptr [rsp+1A0h+var_180], r14d
0x18003cb3e  xor     r9d, r9d
0x18003cb41  mov     r8d, [rbx-4]
0x18003cb45  mov     rdx, rbx
0x18003cb48  mov     rcx, rsi
0x18003cb4b  call    ?index@RWCString@@QEBAIPEBDIIW4caseCompare@1@@Z; RWCString::index(char const *,uint,uint,RWCString::caseCompare)
0x18003cb50  mov     edi, eax
0x18003cb52  cmp     eax, 0FFFFFFFFh
0x18003cb55  jz      loc_18003CCE2
0x18003cb5b  mov     r14d, eax
0x18003cb5e  add     edi, [rbx-4]
0x18003cb61  mov     rcx, [rsi]
0x18003cb64  cmp     edi, [rcx-4]
0x18003cb67  jnb     loc_18003CCEB
0x18003cb6d  mov     edx, edi
0x18003cb6f  mov     rcx, rsi; this
0x18003cb72  call    ??ARWCString@@QEAAAEADI@Z; RWCString::operator[](uint)
0x18003cb77  cmp     byte ptr [rax], 7Bh ; '{'
0x18003cb7a  jnz     short loc_18003CB91
0x18003cb7c  lea     rdx, asc_1801822D0; "}"
0x18003cb83  mov     rcx, rdx
0x18003cb86  mov     al, [rcx]
0x18003cb88  inc     rcx
0x18003cb8b  test    al, al
0x18003cb8d  jnz     short loc_18003CB86
0x18003cb8f  jmp     short loc_18003CBA4
0x18003cb91  lea     rdx, asc_180182144; ";"
0x18003cb98  mov     rcx, rdx
0x18003cb9b  mov     al, [rcx]
0x18003cb9d  inc     rcx
0x18003cba0  test    al, al
0x18003cba2  jnz     short loc_18003CB9B
0x18003cba4  sub     ecx, edx
0x18003cba6  lea     r8d, [rcx-1]
0x18003cbaa  mov     dword ptr [rsp+1A0h+var_180], r12d
0x18003cbaf  mov     r9d, edi
0x18003cbb2  mov     rcx, rsi
0x18003cbb5  call    ?index@RWCString@@QEBAIPEBDIIW4caseCompare@1@@Z; RWCString::index(char const *,uint,uint,RWCString::caseCompare)
0x18003cbba  mov     ebx, eax
0x18003cbbc  or      eax, 0FFFFFFFFh
0x18003cbbf  cmp     ebx, eax
0x18003cbc1  jz      short loc_18003CBC9
0x18003cbc3  inc     ebx
0x18003cbc5  cmp     ebx, eax
0x18003cbc7  jnz     short loc_18003CBCF
0x18003cbc9  mov     rax, [rsi]
0x18003cbcc  mov     ebx, [rax-4]
0x18003cbcf  mov     [rbp+0A0h+var_108], rsi
0x18003cbd3  mov     [rbp+0A0h+var_100], edi
0x18003cbd6  mov     eax, ebx
0x18003cbd8  sub     eax, edi
0x18003cbda  mov     [rbp+0A0h+var_FC], eax
0x18003cbdd  lea     rdi, [r15+10h]
0x18003cbe1  lea     rdx, [rbp+0A0h+var_108]
0x18003cbe5  mov     rcx, rdi
0x18003cbe8  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18003cbed  lea     rdx, aDsn; "DSN="
0x18003cbf4  mov     rcx, rdx
0x18003cbf7  mov     al, [rcx]
0x18003cbf9  inc     rcx
0x18003cbfc  test    al, al
0x18003cbfe  jnz     short loc_18003CBF7
0x18003cc00  sub     ecx, edx
0x18003cc02  lea     r8d, [rcx-1]
0x18003cc06  mov     dword ptr [rsp+1A0h+var_180], 1
0x18003cc0e  xor     r9d, r9d
0x18003cc11  mov     rcx, rsi
0x18003cc14  call    ?index@RWCString@@QEBAIPEBDIIW4caseCompare@1@@Z; RWCString::index(char const *,uint,uint,RWCString::caseCompare)
0x18003cc19  cmp     eax, 0FFFFFFFFh
0x18003cc1c  jz      short loc_18003CC3C
0x18003cc1e  mov     [rbp+0A0h+var_F8], rsi
0x18003cc22  mov     [rbp+0A0h+var_F0], r14d
0x18003cc26  sub     ebx, r14d
0x18003cc29  mov     [rbp+0A0h+var_EC], ebx
0x18003cc2c  lea     rdx, Class
0x18003cc33  lea     rcx, [rbp+0A0h+var_F8]
0x18003cc37  call    ??4RWCSubString@@QEAAAEAV0@PEBD@Z; RWCSubString::operator=(char const *)
0x18003cc3c  mov     r9b, 20h ; ' '
0x18003cc3f  mov     r8d, 3
0x18003cc45  lea     rdx, [rbp+0A0h+var_98]
0x18003cc49  mov     rcx, rdi
0x18003cc4c  call    ?strip@RWCString@@QEAA?AVRWCSubString@@W4stripType@1@D@Z; RWCString::strip(RWCString::stripType,char)
0x18003cc51  lea     rdx, [rbp+0A0h+var_98]
0x18003cc55  mov     rcx, rdi
0x18003cc58  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18003cc5d  mov     r9b, 7Bh ; '{'
0x18003cc60  mov     r14d, 1
0x18003cc66  mov     r8d, r14d
0x18003cc69  lea     rdx, [rbp+0A0h+var_88]
0x18003cc6d  mov     rcx, rdi
0x18003cc70  call    ?strip@RWCString@@QEAA?AVRWCSubString@@W4stripType@1@D@Z; RWCString::strip(RWCString::stripType,char)
0x18003cc75  lea     rdx, [rbp+0A0h+var_88]
0x18003cc79  mov     rcx, rdi
0x18003cc7c  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18003cc81  mov     r9b, 7Dh ; '}'
0x18003cc84  lea     ebx, [r14+1]
0x18003cc88  mov     r8d, ebx
0x18003cc8b  lea     rdx, [rbp+0A0h+var_78]
0x18003cc8f  mov     rcx, rdi
0x18003cc92  call    ?strip@RWCString@@QEAA?AVRWCSubString@@W4stripType@1@D@Z; RWCString::strip(RWCString::stripType,char)
0x18003cc97  lea     rdx, [rbp+0A0h+var_78]
0x18003cc9b  mov     rcx, rdi
0x18003cc9e  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18003cca3  mov     r9b, 20h ; ' '
0x18003cca6  lea     r8d, [r14+2]
0x18003ccaa  lea     rdx, [rbp+0A0h+var_68]
0x18003ccae  mov     rcx, rdi
0x18003ccb1  call    ?strip@RWCString@@QEAA?AVRWCSubString@@W4stripType@1@D@Z; RWCString::strip(RWCString::stripType,char)
0x18003ccb6  lea     rdx, [rbp+0A0h+var_68]
0x18003ccba  mov     rcx, rdi
0x18003ccbd  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18003ccc2  mov     r9b, 3Bh ; ';'
0x18003ccc5  mov     r8d, ebx
0x18003ccc8  lea     rdx, [rbp+0A0h+var_58]
0x18003cccc  mov     rcx, rdi
0x18003cccf  call    ?strip@RWCString@@QEAA?AVRWCSubString@@W4stripType@1@D@Z; RWCString::strip(RWCString::stripType,char)
0x18003ccd4  lea     rdx, [rbp+0A0h+var_58]
0x18003ccd8  mov     rcx, rdi
0x18003ccdb  call    ??4Vstring@@QEAAAEAV0@AEBVRWCSubString@@@Z; Vstring::operator=(RWCSubString const &)
0x18003cce0  jmp     short loc_18003CCF1
0x18003cce2  mov     al, r14b
0x18003cce5  mov     dword ptr [rsp+1A0h+var_160], eax
0x18003cce9  jmp     short loc_18003CCF1
0x18003cceb  mov     r14d, 1
0x18003ccf1  mov     rax, [rsi]
0x18003ccf4  mov     [rsp+1A0h+var_150], rax
0x18003ccf9  lock add [rax-0Ch], r14d
0x18003ccfe  mov     [rbp+0A0h+arg_18], r12b
0x18003cd05  lea     rdx, aMicrosoftAcces; "Microsoft Access Driver"
0x18003cd0c  mov     rcx, rdx
0x18003cd0f  mov     al, [rcx]
0x18003cd11  add     rcx, r14
0x18003cd14  test    al, al
0x18003cd16  jnz     short loc_18003CD0F
0x18003cd18  lea     rax, [r15+10h]
0x18003cd1c  mov     [rbp+0A0h+var_120], rax
0x18003cd20  sub     ecx, edx
0x18003cd22  sub     ecx, r14d
0x18003cd25  mov     dword ptr [rsp+1A0h+var_180], r14d
0x18003cd2a  xor     r9d, r9d
0x18003cd2d  mov     r8d, ecx
0x18003cd30  mov     rcx, rax
0x18003cd33  call    ?index@RWCString@@QEBAIPEBDIIW4caseCompare@1@@Z; RWCString::index(char const *,uint,uint,RWCString::caseCompare)
0x18003cd38  or      edi, 0FFFFFFFFh
0x18003cd3b  lea     r12, dword_1802AFD50
0x18003cd42  cmp     eax, 0FFFFFFFFh
0x18003cd45  jz      short loc_18003CDA0
0x18003cd47  lea     r8, aExclusive1Read; ";Exclusive=1;ReadOnly=1"
0x18003cd4e  lea     rdx, [rsp+1A0h+var_150]
0x18003cd53  lea     rcx, [rsp+1A0h+var_130]
0x18003cd58  call    ??H@YA?AVVstring@@AEBV0@PEBD@Z; operator+(Vstring const &,char const *)
0x18003cd5d  nop
0x18003cd5e  mov     rdx, rax
0x18003cd61  lea     rcx, [rsp+1A0h+var_150]
0x18003cd66  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18003cd6b  nop
0x18003cd6c  mov     rcx, [rsp+1A0h+var_130]
0x18003cd71  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18003cd75  mov     eax, edi
0x18003cd77  lock xadd [rcx], eax
0x18003cd7b  add     eax, edi
0x18003cd7d  jnz     short loc_18003CD99
0x18003cd7f  cmp     rcx, r12
0x18003cd82  jz      short loc_18003CD99
0x18003cd84  cmp     cs:dword_1802B0018, eax
0x18003cd8a  jz      short loc_18003CD93
0x18003cd8c  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18003cd91  jmp     short loc_18003CD99
0x18003cd93  call    cs:free
0x18003cd99  mov     [rbp+0A0h+arg_18], r14b
0x18003cda0  mov     rdx, [rsp+1A0h+var_150]
0x18003cda5  lea     rcx, [rsp+1A0h+bstrString]
0x18003cdaa  call    sub_180010888
0x18003cdaf  nop
0x18003cdb0  mov     rcx, [rsp+1A0h+var_158]
0x18003cdb5  mov     rax, [rcx]
0x18003cdb8  mov     dword ptr [rsp+1A0h+var_180], edi
0x18003cdbc  xor     r9d, r9d
0x18003cdbf  xor     r8d, r8d
0x18003cdc2  mov     rbx, [rsp+1A0h+bstrString]
0x18003cdc7  mov     rdx, rbx
0x18003cdca  mov     rax, [rax+0A0h]
0x18003cdd1  call    cs:__guard_dispatch_icall_fptr
0x18003cdd7  mov     r14d, eax
0x18003cdda  test    eax, eax
0x18003cddc  jns     short loc_18003CE03
0x18003cdde  mov     r8d, eax
0x18003cde1  mov     rdx, r13
0x18003cde4  mov     rcx, r15
0x18003cde7  call    sub_18003D158
0x18003cdec  cmp     [rbp+0A0h+arg_18], 0
0x18003cdf3  jz      short loc_18003CE5A
0x18003cdf5  mov     rdx, rsi
0x18003cdf8  lea     rcx, [rsp+1A0h+var_150]
0x18003cdfd  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18003ce02  nop
0x18003ce03  xor     esi, esi
0x18003ce05  test    rbx, rbx
0x18003ce08  jz      short loc_18003CE13
0x18003ce0a  mov     rcx, rbx; bstrString
0x18003ce0d  call    cs:SysFreeString
0x18003ce13  mov     rax, [r15+10h]
0x18003ce17  mov     ebx, 1
0x18003ce1c  cmp     [rax-4], esi
0x18003ce1f  jz      short loc_18003CE92
0x18003ce21  lea     rdx, aOracle; "Oracle"
0x18003ce28  mov     rcx, rdx
0x18003ce2b  mov     al, [rcx]
0x18003ce2d  add     rcx, rbx
0x18003ce30  test    al, al
0x18003ce32  jnz     short loc_18003CE2B
0x18003ce34  sub     ecx, edx
0x18003ce36  sub     ecx, ebx
0x18003ce38  mov     dword ptr [rsp+1A0h+var_180], ebx
0x18003ce3c  xor     r9d, r9d
0x18003ce3f  mov     r8d, ecx
0x18003ce42  lea     rcx, [r15+10h]
0x18003ce46  call    ?index@RWCString@@QEBAIPEBDIIW4caseCompare@1@@Z; RWCString::index(char const *,uint,uint,RWCString::caseCompare)
0x18003ce4b  mov     ecx, dword ptr [rsp+1A0h+var_160]
0x18003ce4f  movzx   ecx, cl
0x18003ce52  cmp     eax, 0FFFFFFFFh
0x18003ce55  cmovnz  ecx, ebx
0x18003ce58  jmp     short loc_18003CE96
0x18003ce5a  lea     rdx, Class; char *
0x18003ce61  mov     rcx, [rbp+0A0h+var_120]; this
0x18003ce65  call    ??4RWCString@@QEAAAEAV0@PEBD@Z; RWCString::operator=(char const *)
0x18003ce6a  lea     rdx, Class; char *
0x18003ce71  mov     rcx, rsi; this
0x18003ce74  call    ??4RWCString@@QEAAAEAV0@PEBD@Z; RWCString::operator=(char const *)
0x18003ce79  nop
0x18003ce7a  xor     esi, esi
0x18003ce7c  test    rbx, rbx
0x18003ce7f  jz      short loc_18003CE8A
0x18003ce81  mov     rcx, rbx; bstrString
  ... truncated ...
```
