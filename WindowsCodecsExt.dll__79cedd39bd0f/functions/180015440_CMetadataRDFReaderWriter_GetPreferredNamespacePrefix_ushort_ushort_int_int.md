# CMetadataRDFReaderWriter::GetPreferredNamespacePrefix(ushort *,ushort * *,int,int *)

- ea: `0x180015440`
- end: `0x18001564d`
- name: `?GetPreferredNamespacePrefix@CMetadataRDFReaderWriter@@MEAAJPEAGPEAPEAGHPEAH@Z`
- size: `525`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, unsigned __int16 *, unsigned __int16 **, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800151b0`

## callees

- `0x180004500`
- `0x180009290`
- `0x18000efc0`
- `0x180015124`
- `0x180015440`
- `0x1800171c4`
- `0x180021a30`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800154ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800155e3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800154ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800155e3`
- `WindowsCodecs!WICMapSchemaToName` at `0x1800154a1`
- `WindowsCodecs!WICMapSchemaToName` at `0x1800155c5`
- `WindowsCodecs!WICMapSchemaToName` at `0x1800154a1`
- `WindowsCodecs!WICMapSchemaToName` at `0x1800155c5`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetPreferredNamespacePrefix(
        CMetadataRDFReaderWriter *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        int a4,
        int *a5)
{
  HRESULT v9; // ebx
  int v10; // eax
  int v11; // ecx
  unsigned __int16 *v12; // rdi
  int v13; // ecx
  int v14; // eax
  UINT cchName; // [rsp+30h] [rbp-A1h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-99h] BYREF
  OLECHAR psz[4]; // [rsp+40h] [rbp-91h] BYREF
  _BYTE *v19; // [rsp+48h] [rbp-89h]
  int v20; // [rsp+50h] [rbp-81h]
  __int64 v21; // [rsp+54h] [rbp-7Dh]
  _BYTE v22[128]; // [rsp+60h] [rbp-71h] BYREF

  v17 = 0;
  cchName = 0;
  *a5 = 0;
  v9 = WICMapSchemaToName(&GUID_MetadataFormatXMP, a2, 0, 0, &cchName);
  if ( v9 != -2003292352 || !a4 )
  {
    v20 = 64;
    *(_QWORD *)psz = v22;
    v19 = v22;
    v21 = 64;
    if ( v9 < 0 )
    {
LABEL_12:
      if ( !g_doStackCaptures )
      {
LABEL_15:
        DynArrayImpl<0>::~DynArrayImpl<0>(psz);
        goto LABEL_26;
      }
      v13 = v9;
LABEL_14:
      DoStackCapture(v13);
      goto LABEL_15;
    }
    v14 = DynArrayImpl<0>::Grow(psz, 2u, cchName, 0, 0);
    v9 = v14;
    if ( v14 >= 0 )
    {
      v14 = WICMapSchemaToName(&GUID_MetadataFormatXMP, a2, cchName, *(WCHAR **)psz, &cchName);
      v9 = v14;
      if ( v14 >= 0 )
      {
        v17 = SysAllocString(*(const OLECHAR **)psz);
        v12 = v17;
        if ( v17 )
        {
          DynArrayImpl<0>::~DynArrayImpl<0>(psz);
          goto LABEL_25;
        }
        v9 = -2147024882;
        goto LABEL_12;
      }
      if ( !g_doStackCaptures )
        goto LABEL_15;
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_15;
    }
    v13 = v14;
    goto LABEL_14;
  }
  ++*((_QWORD *)this + 30);
  v10 = StringCchPrintfW(psz, 0x40u, L"prefix%I64u");
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_26;
    v11 = v10;
    goto LABEL_10;
  }
  v17 = SysAllocString(psz);
  v12 = v17;
  if ( v17 )
  {
LABEL_25:
    *a3 = v12;
    *a5 = 1;
    v17 = 0;
    goto LABEL_26;
  }
  v9 = -2147024882;
  if ( g_doStackCaptures )
  {
    v11 = -2147024882;
LABEL_10:
    DoStackCapture(v11);
  }
LABEL_26:
  FreeBSTR(&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015440  mov     [rsp-8+arg_18], rbx
0x180015445  push    rbp
0x180015446  push    rsi
0x180015447  push    rdi
0x180015448  push    r12
0x18001544a  push    r13
0x18001544c  push    r14
0x18001544e  push    r15
0x180015450  lea     rbp, [rsp-1Fh]
0x180015455  sub     rsp, 0F0h
0x18001545c  mov     rax, cs:__security_cookie
0x180015463  xor     rax, rsp
0x180015466  mov     [rbp+4Fh+var_40], rax
0x18001546a  mov     r14, [rbp+4Fh+arg_20]
0x18001546e  lea     rax, [rsp+120h+cchName]
0x180015473  xor     r13d, r13d
0x180015476  mov     [rsp+120h+pcchActual], rax; pcchActual
0x18001547b  mov     esi, r9d
0x18001547e  mov     [rsp+120h+var_E8], r13
0x180015483  mov     r12, r8
0x180015486  mov     [rsp+120h+cchName], r13d
0x18001548b  mov     rdi, rcx
0x18001548e  mov     [r14], r13d
0x180015491  xor     r9d, r9d; wzName
0x180015494  lea     rcx, GUID_MetadataFormatXMP; guidMetadataFormat
0x18001549b  xor     r8d, r8d; cchName
0x18001549e  mov     r15, rdx
0x1800154a1  call    cs:__imp_WICMapSchemaToName
0x1800154a7  mov     ebx, eax
0x1800154a9  cmp     eax, 88982F40h
0x1800154ae  jnz     loc_180015534
0x1800154b4  test    esi, esi
0x1800154b6  jz      short loc_180015534
0x1800154b8  mov     r9, [rdi+0F0h]
0x1800154bf  lea     r8, aPrefixI64u; "prefix%I64u"
0x1800154c6  lea     edx, [r13+40h]; unsigned __int64
0x1800154ca  lea     rcx, [rsp+120h+psz]; unsigned __int16 *
0x1800154cf  lea     rax, [r9+1]
0x1800154d3  mov     [rdi+0F0h], rax
0x1800154da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800154df  mov     ebx, eax
0x1800154e1  test    eax, eax
0x1800154e3  jns     short loc_1800154FA
0x1800154e5  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800154ec  jz      short loc_1800154F2
0x1800154ee  mov     ecx, eax
0x1800154f0  jmp     short loc_18001552A
0x1800154f2  test    eax, eax
0x1800154f4  js      loc_18001561A
0x1800154fa  lea     rcx, [rsp+120h+psz]; psz
0x1800154ff  call    cs:__imp_SysAllocString
0x180015505  mov     [rsp+120h+var_E8], rax
0x18001550a  mov     rdi, rax
0x18001550d  test    rax, rax
0x180015510  jnz     loc_18001560A
0x180015516  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18001551d  mov     ebx, 8007000Eh
0x180015522  jz      loc_18001561A
0x180015528  mov     ecx, ebx; int
0x18001552a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001552f  jmp     loc_18001561A
0x180015534  mov     [rsp+120h+var_D0], 40h ; '@'
0x18001553c  lea     rax, [rbp+4Fh+var_C0]
0x180015540  mov     qword ptr [rsp+120h+psz], rax
0x180015545  lea     rax, [rbp+4Fh+var_C0]
0x180015549  mov     [rsp+120h+var_D8], rax
0x18001554e  mov     [rbp+4Fh+var_CC], 40h ; '@'
0x180015556  test    ebx, ebx
0x180015558  jns     short loc_180015579
0x18001555a  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015561  jz      short loc_18001556A
0x180015563  mov     ecx, ebx; int
0x180015565  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001556a  lea     rcx, [rsp+120h+psz]
0x18001556f  call    ??1?$DynArrayImpl@$0A@@@IEAA@XZ; DynArrayImpl<0>::~DynArrayImpl<0>(void)
0x180015574  jmp     loc_18001561A
0x180015579  mov     r8d, [rsp+120h+cchName]
0x18001557e  lea     rcx, [rsp+120h+psz]
0x180015583  xor     r9d, r9d
0x180015586  mov     [rsp+120h+pcchActual], r13
0x18001558b  lea     edx, [r9+2]
0x18001558f  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x180015594  mov     ebx, eax
0x180015596  test    eax, eax
0x180015598  jns     short loc_1800155A7
0x18001559a  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800155a1  jz      short loc_18001556A
0x1800155a3  mov     ecx, eax
0x1800155a5  jmp     short loc_180015565
0x1800155a7  mov     r9, qword ptr [rsp+120h+psz]; wzName
0x1800155ac  lea     rax, [rsp+120h+cchName]
0x1800155b1  mov     r8d, [rsp+120h+cchName]; cchName
0x1800155b6  lea     rcx, GUID_MetadataFormatXMP; guidMetadataFormat
0x1800155bd  mov     rdx, r15; pwzSchema
0x1800155c0  mov     [rsp+120h+pcchActual], rax; pcchActual
0x1800155c5  call    cs:__imp_WICMapSchemaToName
0x1800155cb  mov     ebx, eax
0x1800155cd  test    eax, eax
0x1800155cf  jns     short loc_1800155DE
0x1800155d1  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800155d8  jnz     short loc_1800155A3
0x1800155da  test    eax, eax
0x1800155dc  js      short loc_18001556A
0x1800155de  mov     rcx, qword ptr [rsp+120h+psz]; psz
0x1800155e3  call    cs:__imp_SysAllocString
0x1800155e9  mov     [rsp+120h+var_E8], rax
0x1800155ee  mov     rdi, rax
0x1800155f1  test    rax, rax
0x1800155f4  jnz     short loc_180015600
0x1800155f6  mov     ebx, 8007000Eh
0x1800155fb  jmp     loc_18001555A
0x180015600  lea     rcx, [rsp+120h+psz]
0x180015605  call    ??1?$DynArrayImpl@$0A@@@IEAA@XZ; DynArrayImpl<0>::~DynArrayImpl<0>(void)
0x18001560a  mov     [r12], rdi
0x18001560e  mov     dword ptr [r14], 1
0x180015615  mov     [rsp+120h+var_E8], r13
0x18001561a  lea     rcx, [rsp+120h+var_E8]; unsigned __int16 **
0x18001561f  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180015624  mov     eax, ebx
0x180015626  mov     rcx, [rbp+4Fh+var_40]
0x18001562a  xor     rcx, rsp; StackCookie
0x18001562d  call    __security_check_cookie
0x180015632  mov     rbx, [rsp+120h+arg_18]
0x18001563a  add     rsp, 0F0h
0x180015641  pop     r15
0x180015643  pop     r14
0x180015645  pop     r13
0x180015647  pop     r12
0x180015649  pop     rdi
0x18001564a  pop     rsi
0x18001564b  pop     rbp
0x18001564c  retn
```
