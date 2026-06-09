# RfbShellFolderBase::DetailsOfFromDetailsEx(IShellFolder2 *,_ITEMID_CHILD const *,COLUMN_INFO const *,_SHELLDETAILS *)

- ea: `0x1800150c0`
- end: `0x1800152d8`
- name: `?DetailsOfFromDetailsEx@RfbShellFolderBase@@IEAAXPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@PEBUCOLUMN_INFO@@PEAU_SHELLDETAILS@@@Z`
- size: `536`
- prototype: `void __fastcall(RfbShellFolderBase *__hidden this, struct IShellFolder2 *, const struct _ITEMID_CHILD *, const struct COLUMN_INFO *, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800155f0`

## callees

- `0x180002030`
- `0x1800056e0`
- `0x180007150`
- `0x1800150c0`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001526a`
- `OLEAUT32!__imp_VariantClear` at `0x18001526a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800151d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800151d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001525f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001525f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015252`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180015252`
- `PROPSYS!VariantToPropVariant` at `0x180015170`
- `PROPSYS!VariantToPropVariant` at `0x180015170`
- `PROPSYS!PropVariantToUInt64WithDefault` at `0x18001518d`
- `PROPSYS!PropVariantToUInt64WithDefault` at `0x18001518d`
- `SHLWAPI!StrFormatByteSizeW` at `0x1800151a0`
- `SHLWAPI!StrFormatByteSizeW` at `0x1800151a0`

## pseudocode

```c
void __fastcall RfbShellFolderBase::DetailsOfFromDetailsEx(
        RfbShellFolderBase *this,
        struct IShellFolder2 *a2,
        const struct _ITEMID_CHILD *a3,
        const struct COLUMN_INFO *a4,
        struct _SHELLDETAILS *a5)
{
  HRESULT v6; // ebx
  ULONGLONG v7; // rax
  LPVOID v8; // rcx
  unsigned int v9; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v11; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pPropVar; // [rsp+48h] [rbp-B8h] BYREF
  VARIANT pVar; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszBuf[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a4 || !a2 || !a5 )
  {
    v9 = wil::verify_hresult<long>(0x80070057);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x501,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)v9,
      ppv);
  }
  a5->str.uType = 2;
  a5->str.cStr[0] = 0;
  memset(&pVar, 0, sizeof(pVar));
  v6 = ((__int64 (__fastcall *)(struct IShellFolder2 *, const struct _ITEMID_CHILD *, _QWORD, VARIANT *))a2->lpVtbl->GetDetailsEx)(
         a2,
         a3,
         *(_QWORD *)a4,
         &pVar);
  if ( v6 < 0 )
LABEL_19:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52D,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  memset(&pPropVar, 0, sizeof(pPropVar));
  v6 = VariantToPropVariant(&pVar, &pPropVar);
  if ( v6 >= 0 )
  {
    if ( (*((_BYTE *)a4 + 20) & 2) != 0 )
    {
      v7 = PropVariantToUInt64WithDefault(&pPropVar, 0);
      StrFormatByteSizeW(v7, pszBuf, 0x104u);
    }
    else
    {
      v11 = 0;
      v6 = CoCreateInstance(&CLSID_PropertiesUI, 0, 1u, &GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66, &v11);
      if ( v6 >= 0 )
      {
        ppv = 0;
        v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)v11 + 72LL))(
               v11,
               *(_QWORD *)a4,
               *(unsigned int *)(*(_QWORD *)a4 + 16LL),
               &pPropVar);
      }
      v8 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      }
      if ( v6 < 0 )
        goto LABEL_15;
    }
    v6 = -2147024809;
    if ( a5 != (struct _SHELLDETAILS *)-8LL )
    {
      a5->str.uType = 0;
      v6 = SHStrDupW(pszBuf, &a5->str.pOleStr);
    }
LABEL_15:
    PropVariantClear(&pPropVar);
  }
  VariantClear(&pVar);
  if ( v6 < 0 )
    goto LABEL_19;
}

```

## disassembly

```asm
0x1800150c0  mov     [rsp-8+arg_0], rbx
0x1800150c5  push    rbp
0x1800150c6  push    rsi
0x1800150c7  push    rdi
0x1800150c8  lea     rbp, [rsp-1A0h]
0x1800150d0  sub     rsp, 2A0h
0x1800150d7  mov     rax, cs:__security_cookie
0x1800150de  xor     rax, rsp
0x1800150e1  mov     [rbp+1B0h+var_20], rax
0x1800150e8  mov     rsi, r9
0x1800150eb  mov     r11, r8
0x1800150ee  mov     r10, rdx
0x1800150f1  mov     rax, [rbp+1B0h+arg_20]
0x1800150f8  test    r9, r9
0x1800150fb  jz      loc_180015296
0x180015101  test    rdx, rdx
0x180015104  jz      loc_180015296
0x18001510a  test    rax, rax
0x18001510d  jz      loc_180015296
0x180015113  lea     rdi, [rax+8]
0x180015117  mov     dword ptr [rdi], 2
0x18001511d  mov     byte ptr [rax+10h], 0
0x180015121  xorps   xmm0, xmm0
0x180015124  xor     eax, eax
0x180015126  movups  xmmword ptr [rsp+2B0h+pVar], xmm0
0x18001512b  mov     qword ptr [rsp+2B0h+pVar+10h], rax
0x180015130  mov     rax, [rdx]
0x180015133  lea     r9, [rsp+2B0h+pVar]
0x180015138  mov     r8, [rsi]
0x18001513b  mov     rdx, r11
0x18001513e  mov     rcx, r10
0x180015141  mov     rax, [rax+88h]
0x180015148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001514d  mov     ebx, eax
0x18001514f  test    eax, eax
0x180015151  js      loc_1800152BC
0x180015157  xorps   xmm0, xmm0
0x18001515a  xor     eax, eax
0x18001515c  movups  xmmword ptr [rsp+2B0h+pPropVar], xmm0
0x180015161  mov     qword ptr [rsp+2B0h+pPropVar+10h], rax
0x180015166  lea     rdx, [rsp+2B0h+pPropVar]; pPropVar
0x18001516b  lea     rcx, [rsp+2B0h+pVar]; pVar
0x180015170  call    cs:__imp_VariantToPropVariant
0x180015176  mov     ebx, eax
0x180015178  test    eax, eax
0x18001517a  js      loc_180015265
0x180015180  test    byte ptr [rsi+14h], 2
0x180015184  jz      short loc_1800151AB
0x180015186  xor     edx, edx; ullDefault
0x180015188  lea     rcx, [rsp+2B0h+pPropVar]; propvarIn
0x18001518d  call    cs:__imp_PropVariantToUInt64WithDefault
0x180015193  mov     rcx, rax; qdw
0x180015196  mov     r8d, 104h; cchBuf
0x18001519c  lea     rdx, [rbp+1B0h+pszBuf]; pszBuf
0x1800151a0  call    cs:__imp_StrFormatByteSizeW
0x1800151a6  jmp     loc_18001523A
0x1800151ab  mov     [rsp+2B0h+var_270], 0
0x1800151b4  lea     rax, [rsp+2B0h+var_270]
0x1800151b9  mov     [rsp+2B0h+ppv], rax; ppv
0x1800151be  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x1800151c5  xor     edx, edx; pUnkOuter
0x1800151c7  lea     r8d, [rdx+1]; dwClsContext
0x1800151cb  lea     rcx, CLSID_PropertiesUI; rclsid
0x1800151d2  call    cs:__imp_CoCreateInstance
0x1800151d8  mov     ebx, eax
0x1800151da  test    eax, eax
0x1800151dc  js      short loc_180015216
0x1800151de  mov     rcx, [rsp+2B0h+var_270]
0x1800151e3  mov     rdx, [rsi]
0x1800151e6  mov     rax, [rcx]
0x1800151e9  mov     [rsp+2B0h+var_280], 104h
0x1800151f1  lea     r8, [rbp+1B0h+pszBuf]
0x1800151f5  mov     [rsp+2B0h+var_288], r8
0x1800151fa  mov     dword ptr [rsp+2B0h+ppv], 0
0x180015202  lea     r9, [rsp+2B0h+pPropVar]
0x180015207  mov     r8d, [rdx+10h]
0x18001520b  mov     rax, [rax+48h]
0x18001520f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015214  mov     ebx, eax
0x180015216  mov     rcx, [rsp+2B0h+var_270]
0x18001521b  test    rcx, rcx
0x18001521e  jz      short loc_180015236
0x180015220  mov     [rsp+2B0h+var_270], 0
0x180015229  mov     rax, [rcx]
0x18001522c  mov     rax, [rax+10h]
0x180015230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015235  nop
0x180015236  test    ebx, ebx
0x180015238  js      short loc_18001525A
0x18001523a  mov     ebx, 80070057h
0x18001523f  test    rdi, rdi
0x180015242  jz      short loc_18001525A
0x180015244  mov     dword ptr [rdi], 0
0x18001524a  lea     rdx, [rdi+8]; ppwsz
0x18001524e  lea     rcx, [rbp+1B0h+pszBuf]; psz
0x180015252  call    cs:__imp_SHStrDupW
0x180015258  mov     ebx, eax
0x18001525a  lea     rcx, [rsp+2B0h+pPropVar]; pvar
0x18001525f  call    cs:__imp_PropVariantClear
0x180015265  lea     rcx, [rsp+2B0h+pVar]; pvarg
0x18001526a  call    cs:__imp_VariantClear
0x180015270  test    ebx, ebx
0x180015272  js      short loc_1800152BC
0x180015274  mov     rcx, [rbp+1B0h+var_20]
0x18001527b  xor     rcx, rsp; StackCookie
0x18001527e  call    __security_check_cookie
0x180015283  mov     rbx, [rsp+2B0h+arg_0]
0x18001528b  add     rsp, 2A0h
0x180015292  pop     rdi
0x180015293  pop     rsi
0x180015294  pop     rbp
0x180015295  retn
0x180015296  mov     ecx, 80070057h
0x18001529b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800152a0  mov     r9d, eax; char *
0x1800152a3  mov     rcx, [rbp+1B8h]; this
0x1800152aa  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800152b1  mov     edx, 501h; void *
0x1800152b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800152bc  mov     rcx, [rbp+1B8h]; this
0x1800152c3  mov     r9d, ebx; char *
0x1800152c6  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800152cd  mov     edx, 52Dh; void *
0x1800152d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
