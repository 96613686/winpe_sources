# OBJECT_EXTENSION_TABLE::startElement(ushort const *,int,ushort const *,int,ushort const *,int,ISAXAttributes *)

- ea: `0x18000eb40`
- end: `0x18000efaa`
- name: `?startElement@OBJECT_EXTENSION_TABLE@@UEAAJPEBGH0H0HPEAUISAXAttributes@@@Z`
- size: `1130`
- prototype: `int(OBJECT_EXTENSION_TABLE *__hidden this, const unsigned __int16 *, int, const unsigned __int16 *, int, const unsigned __int16 *, int, struct ISAXAttributes *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x180005d74`
- `0x18000bee8`
- `0x18000e1fc`
- `0x18000e27c`
- `0x18000eb40`
- `0x180034cbe`
- `0x180034cd6`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18000ecdb`
- `msvcrt!_wcsupr` at `0x18000ee42`
- `msvcrt!_wcsupr` at `0x18000ee69`
- `msvcrt!_wcsupr` at `0x18000ecdb`
- `msvcrt!_wcsupr` at `0x18000ee42`
- `msvcrt!_wcsupr` at `0x18000ee69`

## string_xrefs

- `0x18000ece9`: `classId`
- `0x18000ee77`: `classId`

## pseudocode

```c
__int64 __fastcall OBJECT_EXTENSION_TABLE::startElement(
        OBJECT_EXTENSION_TABLE *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int MaxCount,
        const unsigned __int16 *a6,
        int a7,
        struct ISAXAttributes *a8)
{
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int AttributeValue; // ebx
  _DWORD *v14; // rax
  _QWORD *v15; // rsi
  _QWORD *v16; // rdi
  int Extension; // eax
  struct IObjectExtension *v18; // r14
  _DWORD *v19; // rax
  struct IObjectExtension *v21; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v22[32]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *String; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+50h] [rbp-B0h]
  __int16 v25; // [rsp+54h] [rbp-ACh]
  int v26; // [rsp+58h] [rbp-A8h]
  _BYTE v27[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  __int16 v30; // [rsp+8Ch] [rbp-74h]
  int v31; // [rsp+90h] [rbp-70h]
  _BYTE v32[32]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v33; // [rsp+B8h] [rbp-48h]
  int v34; // [rsp+C0h] [rbp-40h]
  __int16 v35; // [rsp+C4h] [rbp-3Ch]
  int v36; // [rsp+C8h] [rbp-38h]
  __int16 v37; // [rsp+D0h] [rbp-30h] BYREF
  char v38[510]; // [rsp+D2h] [rbp-2Eh] BYREF
  __int16 v39; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v40[510]; // [rsp+2D2h] [rbp+1D2h] BYREF
  __int16 v41; // [rsp+4D0h] [rbp+3D0h] BYREF
  char v42[510]; // [rsp+4D2h] [rbp+3D2h] BYREF

  v21 = 0;
  memset_0(v38, 0, sizeof(v38));
  v25 = 256;
  String = (wchar_t *)&v37;
  v24 = 512;
  v26 = 0;
  v37 = 0;
  memset_0(v40, 0, sizeof(v40));
  v34 = 512;
  v33 = (wchar_t *)&v39;
  v35 = 256;
  v36 = 0;
  v39 = 0;
  memset_0(v42, 0, sizeof(v42));
  ++*((_DWORD *)this + 14);
  v28 = (unsigned __int16 *)&v41;
  v10 = *((_DWORD *)this + 14);
  v29 = 512;
  v30 = 256;
  v31 = 0;
  v41 = 0;
  v11 = v10 - 1;
  if ( !v11 )
  {
    AttributeValue = 0;
    if ( !wcsncmp_0(a4, L"appcmd", MaxCount) )
      goto LABEL_36;
    goto LABEL_35;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( !wcsncmp_0(a4, L"object", MaxCount) )
    {
      v19 = operator new(0x98u);
      v16 = v19;
      if ( v19 )
      {
        v19[2] = 1;
        *(_QWORD *)v19 = &EXTENSION_OBJECT::`vftable';
        *((_QWORD *)v19 + 16) = 0;
        *((_QWORD *)v19 + 2) = 0;
        *((_QWORD *)v19 + 6) = v19 + 4;
        v19[14] = 32;
        *((_WORD *)v19 + 30) = 256;
        v19[16] = 0;
        *((_QWORD *)v19 + 9) = 0;
        *((_QWORD *)v19 + 13) = v19 + 18;
        v19[28] = 32;
        *((_WORD *)v19 + 58) = 256;
        v19[30] = 0;
        *((_QWORD *)v19 + 17) = 0;
        *((_QWORD *)v19 + 18) = 0;
        AttributeValue = OBJECT_EXTENSION_TABLE::GetAttributeValue(a8, L"name", (struct STRU *)v22);
        if ( AttributeValue < 0 )
          goto LABEL_33;
        _wcsupr(String);
        AttributeValue = OBJECT_EXTENSION_TABLE::GetAttributeValue(a8, L"alias", (struct STRU *)v32);
        if ( AttributeValue < 0 )
          goto LABEL_33;
        _wcsupr(v33);
        AttributeValue = OBJECT_EXTENSION_TABLE::GetAttributeValue(a8, L"classId", (struct STRU *)v27);
        if ( AttributeValue < 0 )
          goto LABEL_33;
        v15 = 0;
        AttributeValue = INTERNAL_EXTENSION_TABLE::GetExtension(
                           (OBJECT_EXTENSION_TABLE *)((char *)this + 32),
                           v28,
                           &v21);
        if ( AttributeValue < 0
          || (AttributeValue = STRU::Copy((STRU *)(v16 + 2), String), AttributeValue < 0)
          || (AttributeValue = STRU::Copy((STRU *)(v16 + 9), v33), AttributeValue < 0) )
        {
          v18 = v21;
        }
        else
        {
          v18 = v21;
          v16[16] = v21;
          (*(void (__fastcall **)(struct IObjectExtension *))(*(_QWORD *)v18 + 8LL))(v18);
          AttributeValue = ARRAY_LIST::AddEntry(
                             (OBJECT_EXTENSION_TABLE *)((char *)this + 16),
                             (struct IArrayListEntry *)v16,
                             0xFFFFFFFF);
          if ( AttributeValue >= 0 )
          {
            *((_QWORD *)this + 8) = v16;
            v16 = 0;
          }
        }
        goto LABEL_28;
      }
LABEL_16:
      AttributeValue = -2147024888;
      goto LABEL_36;
    }
LABEL_35:
    AttributeValue = -2147024883;
    goto LABEL_36;
  }
  if ( v12 != 1 || wcsncmp_0(a4, L"verb", MaxCount) )
    goto LABEL_35;
  if ( *((_QWORD *)this + 8) )
  {
    v14 = operator new(0x50u);
    v15 = v14;
    if ( v14 )
    {
      v14[2] = 1;
      *(_QWORD *)v14 = &EXTENSION_VERB::`vftable';
      *((_QWORD *)v14 + 9) = 0;
      *((_QWORD *)v14 + 2) = 0;
      *((_QWORD *)v14 + 6) = v14 + 4;
      v14[14] = 32;
      v16 = 0;
      *((_WORD *)v14 + 30) = 256;
      v14[16] = 0;
      AttributeValue = OBJECT_EXTENSION_TABLE::GetAttributeValue(a8, L"name", (struct STRU *)v22);
      if ( AttributeValue < 0 )
        goto LABEL_31;
      _wcsupr(String);
      AttributeValue = OBJECT_EXTENSION_TABLE::GetAttributeValue(a8, L"classId", (struct STRU *)v27);
      if ( AttributeValue < 0 )
        goto LABEL_31;
      Extension = INTERNAL_EXTENSION_TABLE::GetExtension((OBJECT_EXTENSION_TABLE *)((char *)this + 32), v28, &v21);
      v18 = v21;
      AttributeValue = Extension;
      if ( Extension >= 0 )
      {
        if ( v21 )
        {
          AttributeValue = STRU::Copy((STRU *)(v15 + 2), String);
          if ( AttributeValue >= 0 )
          {
            v15[9] = v18;
            (*(void (__fastcall **)(struct IObjectExtension *))(*(_QWORD *)v18 + 8LL))(v18);
            AttributeValue = ARRAY_LIST::AddEntry(
                               (ARRAY_LIST *)(*((_QWORD *)this + 8) + 136LL),
                               (struct IArrayListEntry *)v15,
                               0xFFFFFFFF);
            if ( AttributeValue >= 0 )
            {
              *((_QWORD *)this + 9) = v15;
              v15 = 0;
            }
          }
        }
        else
        {
          AttributeValue = -2147024809;
        }
      }
LABEL_28:
      if ( v18 )
        (*(void (__fastcall **)(struct IObjectExtension *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( !v15 )
      {
LABEL_32:
        if ( !v16 )
          goto LABEL_36;
LABEL_33:
        EXTENSION_OBJECT::Release((EXTENSION_OBJECT *)v16);
        goto LABEL_36;
      }
LABEL_31:
      EXTENSION_OBJECT::Release((EXTENSION_OBJECT *)v15);
      goto LABEL_32;
    }
    goto LABEL_16;
  }
  AttributeValue = -2147418113;
LABEL_36:
  BUFFER::~BUFFER((BUFFER *)v27);
  BUFFER::~BUFFER((BUFFER *)v32);
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)AttributeValue;
}

```

## disassembly

```asm
0x18000eb40  mov     [rsp-8+arg_8], rbx
0x18000eb45  mov     [rsp-8+arg_10], rsi
0x18000eb4a  push    rbp
0x18000eb4b  push    rdi
0x18000eb4c  push    r12
0x18000eb4e  push    r14
0x18000eb50  push    r15
0x18000eb52  lea     rbp, [rsp-5E0h]
0x18000eb5a  sub     rsp, 6E0h
0x18000eb61  mov     rax, cs:__security_cookie
0x18000eb68  xor     rax, rsp
0x18000eb6b  mov     [rbp+600h+var_30], rax
0x18000eb72  mov     r14, [rbp+600h+arg_38]
0x18000eb79  mov     r15, rcx
0x18000eb7c  mov     esi, 1FEh
0x18000eb81  lea     rcx, [rbp+600h+var_62E]; void *
0x18000eb85  xor     r12d, r12d
0x18000eb88  mov     r8d, esi; Size
0x18000eb8b  xor     edx, edx; Val
0x18000eb8d  mov     [rsp+700h+var_6E0], r12
0x18000eb92  mov     rdi, r9
0x18000eb95  call    memset_0
0x18000eb9a  lea     rax, [rbp+600h+var_630]
0x18000eb9e  mov     [rsp+700h+var_6AC], 100h
0x18000eba5  lea     ebx, [rsi+2]
0x18000eba8  mov     [rsp+700h+String], rax
0x18000ebad  mov     r8d, esi; Size
0x18000ebb0  mov     [rsp+700h+var_6B0], ebx
0x18000ebb4  xor     edx, edx; Val
0x18000ebb6  mov     [rsp+700h+var_6A8], r12d
0x18000ebbb  lea     rcx, [rbp+600h+var_42E]; void *
0x18000ebc2  mov     [rbp+600h+var_630], r12w
0x18000ebc7  call    memset_0
0x18000ebcc  lea     rax, [rbp+600h+var_430]
0x18000ebd3  mov     [rbp+600h+var_640], ebx
0x18000ebd6  mov     r8d, esi; Size
0x18000ebd9  mov     [rbp+600h+var_648], rax
0x18000ebdd  xor     edx, edx; Val
0x18000ebdf  mov     [rbp+600h+var_63C], 100h
0x18000ebe5  lea     rcx, [rbp+600h+var_22E]; void *
0x18000ebec  mov     [rbp+600h+var_638], r12d
0x18000ebf0  mov     [rbp+600h+var_430], r12w
0x18000ebf8  call    memset_0
0x18000ebfd  inc     dword ptr [r15+38h]
0x18000ec01  lea     rax, [rbp+600h+var_230]
0x18000ec08  mov     [rbp+600h+var_680], rax
0x18000ec0c  mov     eax, [r15+38h]
0x18000ec10  mov     [rbp+600h+var_678], ebx
0x18000ec13  mov     [rbp+600h+var_674], 100h
0x18000ec19  mov     [rbp+600h+var_670], r12d
0x18000ec1d  mov     [rbp+600h+var_230], r12w
0x18000ec25  sub     eax, 1
0x18000ec28  jz      loc_18000EF3E
0x18000ec2e  sub     eax, 1
0x18000ec31  jz      loc_18000ED91
0x18000ec37  cmp     eax, 1
0x18000ec3a  jnz     loc_18000EF5B
0x18000ec40  mov     r8d, dword ptr [rbp+600h+MaxCount]; MaxCount
0x18000ec47  lea     rdx, aVerb; "verb"
0x18000ec4e  mov     rcx, rdi; String1
0x18000ec51  call    wcsncmp_0
0x18000ec56  test    eax, eax
0x18000ec58  jnz     loc_18000EF5B
0x18000ec5e  cmp     [r15+40h], r12
0x18000ec62  jnz     short loc_18000EC6E
0x18000ec64  mov     ebx, 8000FFFFh
0x18000ec69  jmp     loc_18000EF60
0x18000ec6e  mov     ecx, 50h ; 'P'; Size
0x18000ec73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec78  mov     rsi, rax
0x18000ec7b  test    rax, rax
0x18000ec7e  jz      loc_18000ED87
0x18000ec84  lea     rax, ??_7EXTENSION_VERB@@6B@; const EXTENSION_VERB::`vftable'
0x18000ec8b  mov     dword ptr [rsi+8], 1
0x18000ec92  mov     [rsi], rax
0x18000ec95  lea     r8, [rsp+700h+var_6D8]; struct STRU *
0x18000ec9a  lea     rax, [rsi+10h]
0x18000ec9e  mov     [rsi+48h], r12
0x18000eca2  lea     rdx, aName_0; "name"
0x18000eca9  mov     [rax], r12
0x18000ecac  mov     rcx, r14; struct ISAXAttributes *
0x18000ecaf  mov     [rax+20h], rax
0x18000ecb3  mov     dword ptr [rax+28h], 20h ; ' '
0x18000ecba  mov     rdi, r12
0x18000ecbd  mov     word ptr [rax+2Ch], 100h
0x18000ecc3  mov     [rax+30h], r12d
0x18000ecc7  call    ?GetAttributeValue@OBJECT_EXTENSION_TABLE@@CAJPEAUISAXAttributes@@PEBGPEAVSTRU@@@Z; OBJECT_EXTENSION_TABLE::GetAttributeValue(ISAXAttributes *,ushort const *,STRU *)
0x18000eccc  mov     ebx, eax
0x18000ecce  test    eax, eax
0x18000ecd0  js      loc_18000EF27
0x18000ecd6  mov     rcx, [rsp+700h+String]; String
0x18000ecdb  call    cs:__imp__wcsupr
0x18000ece1  lea     r8, [rsp+700h+var_6A0]; struct STRU *
0x18000ece6  mov     rcx, r14; struct ISAXAttributes *
0x18000ece9  lea     rdx, aClassid; "classId"
0x18000ecf0  call    ?GetAttributeValue@OBJECT_EXTENSION_TABLE@@CAJPEAUISAXAttributes@@PEBGPEAVSTRU@@@Z; OBJECT_EXTENSION_TABLE::GetAttributeValue(ISAXAttributes *,ushort const *,STRU *)
0x18000ecf5  mov     ebx, eax
0x18000ecf7  test    eax, eax
0x18000ecf9  js      loc_18000EF27
0x18000ecff  mov     rdx, [rbp+600h+var_680]; unsigned __int16 *
0x18000ed03  lea     rcx, [r15+20h]; this
0x18000ed07  lea     r8, [rsp+700h+var_6E0]; struct IObjectExtension **
0x18000ed0c  call    ?GetExtension@INTERNAL_EXTENSION_TABLE@@QEAAJPEBGPEAPEAVIObjectExtension@@@Z; INTERNAL_EXTENSION_TABLE::GetExtension(ushort const *,IObjectExtension * *)
0x18000ed11  mov     r14, [rsp+700h+var_6E0]
0x18000ed16  mov     ebx, eax
0x18000ed18  test    eax, eax
0x18000ed1a  js      loc_18000EF0E
0x18000ed20  test    r14, r14
0x18000ed23  jnz     short loc_18000ED2F
0x18000ed25  mov     ebx, 80070057h
0x18000ed2a  jmp     loc_18000EF0E
0x18000ed2f  mov     rdx, [rsp+700h+String]; unsigned __int16 *
0x18000ed34  lea     rcx, [rsi+10h]; this
0x18000ed38  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ed3d  mov     ebx, eax
0x18000ed3f  test    eax, eax
0x18000ed41  js      loc_18000EF0E
0x18000ed47  mov     [rsi+48h], r14
0x18000ed4b  mov     rcx, r14
0x18000ed4e  mov     rax, [r14]
0x18000ed51  mov     rax, [rax+8]
0x18000ed55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed5a  mov     rcx, [r15+40h]
0x18000ed5e  or      r8d, 0FFFFFFFFh; unsigned int
0x18000ed62  add     rcx, 88h; this
0x18000ed69  mov     rdx, rsi; struct IArrayListEntry *
0x18000ed6c  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x18000ed71  mov     ebx, eax
0x18000ed73  test    eax, eax
0x18000ed75  js      loc_18000EF0E
0x18000ed7b  mov     [r15+48h], rsi
0x18000ed7f  mov     rsi, r12
0x18000ed82  jmp     loc_18000EF0E
0x18000ed87  mov     ebx, 80070008h
0x18000ed8c  jmp     loc_18000EF60
0x18000ed91  mov     r8d, dword ptr [rbp+600h+MaxCount]; MaxCount
0x18000ed98  lea     rdx, aObject; "object"
0x18000ed9f  mov     rcx, rdi; String1
0x18000eda2  call    wcsncmp_0
0x18000eda7  test    eax, eax
0x18000eda9  jnz     loc_18000EF5B
0x18000edaf  mov     ecx, 98h; Size
0x18000edb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000edb9  mov     rdi, rax
0x18000edbc  test    rax, rax
0x18000edbf  jz      short loc_18000ED87
0x18000edc1  lea     rax, ??_7EXTENSION_OBJECT@@6B@; const EXTENSION_OBJECT::`vftable'
0x18000edc8  mov     dword ptr [rdi+8], 1
0x18000edcf  mov     [rdi], rax
0x18000edd2  lea     r8, [rsp+700h+var_6D8]; struct STRU *
0x18000edd7  lea     rax, [rdi+10h]
0x18000eddb  mov     [rdi+80h], r12
0x18000ede2  mov     [rax], r12
0x18000ede5  lea     rdx, aName_0; "name"
0x18000edec  mov     [rax+20h], rax
0x18000edf0  mov     rcx, r14; struct ISAXAttributes *
0x18000edf3  mov     dword ptr [rax+28h], 20h ; ' '
0x18000edfa  mov     word ptr [rax+2Ch], 100h
0x18000ee00  mov     [rax+30h], r12d
0x18000ee04  lea     rax, [rdi+48h]
0x18000ee08  mov     [rax], r12
0x18000ee0b  mov     [rax+20h], rax
0x18000ee0f  mov     dword ptr [rax+28h], 20h ; ' '
0x18000ee16  mov     word ptr [rax+2Ch], 100h
0x18000ee1c  mov     [rax+30h], r12d
0x18000ee20  mov     [rdi+88h], r12
0x18000ee27  mov     [rdi+90h], r12
0x18000ee2e  call    ?GetAttributeValue@OBJECT_EXTENSION_TABLE@@CAJPEAUISAXAttributes@@PEBGPEAVSTRU@@@Z; OBJECT_EXTENSION_TABLE::GetAttributeValue(ISAXAttributes *,ushort const *,STRU *)
0x18000ee33  mov     ebx, eax
0x18000ee35  test    eax, eax
0x18000ee37  js      loc_18000EF34
0x18000ee3d  mov     rcx, [rsp+700h+String]; String
0x18000ee42  call    cs:__imp__wcsupr
0x18000ee48  lea     r8, [rbp+600h+var_668]; struct STRU *
0x18000ee4c  mov     rcx, r14; struct ISAXAttributes *
0x18000ee4f  lea     rdx, aAlias; "alias"
0x18000ee56  call    ?GetAttributeValue@OBJECT_EXTENSION_TABLE@@CAJPEAUISAXAttributes@@PEBGPEAVSTRU@@@Z; OBJECT_EXTENSION_TABLE::GetAttributeValue(ISAXAttributes *,ushort const *,STRU *)
0x18000ee5b  mov     ebx, eax
0x18000ee5d  test    eax, eax
0x18000ee5f  js      loc_18000EF34
0x18000ee65  mov     rcx, [rbp+600h+var_648]; String
0x18000ee69  call    cs:__imp__wcsupr
0x18000ee6f  lea     r8, [rsp+700h+var_6A0]; struct STRU *
0x18000ee74  mov     rcx, r14; struct ISAXAttributes *
0x18000ee77  lea     rdx, aClassid; "classId"
0x18000ee7e  call    ?GetAttributeValue@OBJECT_EXTENSION_TABLE@@CAJPEAUISAXAttributes@@PEBGPEAVSTRU@@@Z; OBJECT_EXTENSION_TABLE::GetAttributeValue(ISAXAttributes *,ushort const *,STRU *)
0x18000ee83  mov     ebx, eax
0x18000ee85  test    eax, eax
0x18000ee87  js      loc_18000EF34
0x18000ee8d  mov     rdx, [rbp+600h+var_680]; unsigned __int16 *
0x18000ee91  lea     rcx, [r15+20h]; this
0x18000ee95  lea     r8, [rsp+700h+var_6E0]; struct IObjectExtension **
0x18000ee9a  mov     rsi, r12
0x18000ee9d  call    ?GetExtension@INTERNAL_EXTENSION_TABLE@@QEAAJPEBGPEAPEAVIObjectExtension@@@Z; INTERNAL_EXTENSION_TABLE::GetExtension(ushort const *,IObjectExtension * *)
0x18000eea2  mov     ebx, eax
0x18000eea4  test    eax, eax
0x18000eea6  js      short loc_18000EF09
0x18000eea8  mov     rdx, [rsp+700h+String]; unsigned __int16 *
0x18000eead  lea     rcx, [rdi+10h]; this
0x18000eeb1  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000eeb6  mov     ebx, eax
0x18000eeb8  test    eax, eax
0x18000eeba  js      short loc_18000EF09
0x18000eebc  mov     rdx, [rbp+600h+var_648]; unsigned __int16 *
0x18000eec0  lea     rcx, [rdi+48h]; this
0x18000eec4  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000eec9  mov     ebx, eax
0x18000eecb  test    eax, eax
0x18000eecd  js      short loc_18000EF09
0x18000eecf  mov     r14, [rsp+700h+var_6E0]
0x18000eed4  mov     [rdi+80h], r14
0x18000eedb  mov     rcx, r14
0x18000eede  mov     rax, [r14]
0x18000eee1  mov     rax, [rax+8]
0x18000eee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeea  lea     rcx, [r15+10h]; this
0x18000eeee  or      r8d, 0FFFFFFFFh; unsigned int
0x18000eef2  mov     rdx, rdi; struct IArrayListEntry *
0x18000eef5  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x18000eefa  mov     ebx, eax
0x18000eefc  test    eax, eax
0x18000eefe  js      short loc_18000EF0E
0x18000ef00  mov     [r15+40h], rdi
0x18000ef04  mov     rdi, r12
0x18000ef07  jmp     short loc_18000EF0E
0x18000ef09  mov     r14, [rsp+700h+var_6E0]
0x18000ef0e  test    r14, r14
0x18000ef11  jz      short loc_18000EF22
0x18000ef13  mov     rax, [r14]
0x18000ef16  mov     rcx, r14
0x18000ef19  mov     rax, [rax+10h]
0x18000ef1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef22  test    rsi, rsi
0x18000ef25  jz      short loc_18000EF2F
0x18000ef27  mov     rcx, rsi; this
0x18000ef2a  call    ?Release@EXTENSION_OBJECT@@QEAAKXZ; EXTENSION_OBJECT::Release(void)
0x18000ef2f  test    rdi, rdi
0x18000ef32  jz      short loc_18000EF60
0x18000ef34  mov     rcx, rdi; this
0x18000ef37  call    ?Release@EXTENSION_OBJECT@@QEAAKXZ; EXTENSION_OBJECT::Release(void)
0x18000ef3c  jmp     short loc_18000EF60
0x18000ef3e  mov     r8d, dword ptr [rbp+600h+MaxCount]; MaxCount
0x18000ef45  lea     rdx, aAppcmd; "appcmd"
0x18000ef4c  mov     rcx, rdi; String1
0x18000ef4f  mov     ebx, r12d
0x18000ef52  call    wcsncmp_0
0x18000ef57  test    eax, eax
0x18000ef59  jz      short loc_18000EF60
0x18000ef5b  mov     ebx, 8007000Dh
0x18000ef60  lea     rcx, [rsp+700h+var_6A0]; this
0x18000ef65  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ef6a  lea     rcx, [rbp+600h+var_668]; this
0x18000ef6e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ef73  lea     rcx, [rsp+700h+var_6D8]; this
0x18000ef78  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ef7d  mov     eax, ebx
0x18000ef7f  mov     rcx, [rbp+600h+var_30]
0x18000ef86  xor     rcx, rsp; StackCookie
0x18000ef89  call    __security_check_cookie
0x18000ef8e  lea     r11, [rsp+700h+var_20]
0x18000ef96  mov     rbx, [r11+38h]
0x18000ef9a  mov     rsi, [r11+40h]
0x18000ef9e  mov     rsp, r11
0x18000efa1  pop     r15
0x18000efa3  pop     r14
0x18000efa5  pop     r12
0x18000efa7  pop     rdi
0x18000efa8  pop     rbp
0x18000efa9  retn
```
