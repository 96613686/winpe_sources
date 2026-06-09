# COpenSearchRowset::_ParseItem(IXmlReader *,ulong)

- ea: `0x180045774`
- end: `0x1800459e7`
- name: `?_ParseItem@COpenSearchRowset@@AEAAJPEAUIXmlReader@@K@Z`
- size: `627`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, struct IXmlReader *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800456a0`

## callees

- `0x180005460`
- `0x180006900`
- `0x18000eec0`
- `0x180011f3c`
- `0x18002850c`
- `0x18003d8ac`
- `0x180041520`
- `0x180043830`
- `0x180043b28`
- `0x180043cc4`
- `0x180043dd4`
- `0x180045774`
- `0x180045b58`
- `0x18004a530`
- `0x18004faa0`
- `0x180051010`

## import_xrefs

- `SHLWAPI!UrlHashW` at `0x180045921`
- `SHLWAPI!UrlHashW` at `0x180045921`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800457bf`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180045853`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800457bf`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180045853`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseItem(COpenSearchRowset *this, struct IXmlReader *a2, unsigned int a3)
{
  __int64 v4; // r14
  int v6; // ebx
  COpenSearchRowset *v7; // rcx
  int v8; // eax
  const unsigned __int16 *v9; // r8
  __int64 v10; // rsi
  __int64 v11; // r14
  unsigned int *v12; // r9
  int *v13; // rax
  int v14; // ecx
  __int64 v15; // r8
  int v16; // eax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  BYTE pbHash[8]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszUrl[2096]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = a3;
  ppv = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v6 >= 0 )
  {
    v6 = COpenSearchRowset::_ParseItemProperties(this, (struct IPropertyStore *)ppv, a2);
    if ( v6 < 0 )
      goto LABEL_28;
    v6 = COpenSearchRowset::_FillFallbackProps(this, (struct IPropertyStore *)ppv);
    if ( v6 < 0 )
      goto LABEL_28;
    v6 = COpenSearchRowset::_FillProps(this, (struct IPropertyStore *)ppv);
    if ( v6 >= 0 )
    {
LABEL_14:
      v10 = v4;
      v11 = 3 * v4;
      v12 = (unsigned int *)*((_QWORD *)this + v11 + 81);
      if ( v12 )
        v12 = (unsigned int *)*v12;
      v6 = StringCchPrintfW(
             pszUrl,
             0x82Fu,
             L"%010u@%s",
             v12,
             *(_QWORD *)((char *)this + (*((_QWORD *)this + 101) != 0 ? 8 : 0) + 776));
      if ( v6 >= 0 )
      {
        *(_DWORD *)pbHash = 0;
        v6 = UrlHashW(pszUrl, pbHash, 4u);
        if ( v6 >= 0 )
        {
          v6 = IPropertyStore_SetInt(ppv, &PKEY_ItemId, *(unsigned int *)pbHash);
          if ( v6 >= 0 )
          {
            v13 = (int *)*((_QWORD *)this + 3 * v10 + 81);
            if ( v13 )
              v14 = *v13;
            else
              v14 = 0;
            v15 = 0;
            v16 = 1000 - *((_DWORD *)this + 6 * v10 + 158) - v14;
            if ( v16 >= 0 )
              v15 = (unsigned int)v16;
            v6 = IPropertyStore_SetInt(ppv, &PKEY_Search_Rank, v15);
            if ( v6 >= 0 )
            {
              if ( DPA_InsertPtr(*((HDPA *)this + v11 + 81), 0x7FFFFFFF, ppv) == -1 )
              {
                v6 = -2147024882;
              }
              else
              {
                v6 = 0;
                ppv = 0;
              }
            }
          }
        }
      }
      goto LABEL_28;
    }
    *(_QWORD *)pbHash = 0;
    IPropertyStore_GetString(ppv, &PKEY_ItemUrl, pbHash);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
    {
      if ( v6 == -2147023600 )
      {
        v9 = &psz;
        if ( *(_QWORD *)pbHash )
          v9 = *(const unsigned __int16 **)pbHash;
        v8 = COpenSearchRowset::_FillBlockedItemProperties(v7, (struct IPropertyStore *)ppv, v9);
      }
      else
      {
        if ( !ATL::CComPtrBase<IResultSetManager>::operator!((_QWORD *)this + 101) )
          goto LABEL_13;
        v8 = COpenSearchRowset::_FillFailureProperties(this, (struct IPropertyStore *)ppv);
      }
      v6 = v8;
    }
LABEL_13:
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)pbHash);
    if ( v6 >= 0 )
      goto LABEL_14;
LABEL_28:
    SafeRelease<IShellItemArray>((__int64 *)&ppv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180045774  push    rbp
0x180045776  push    rbx
0x180045777  push    rsi
0x180045778  push    rdi
0x180045779  push    r14
0x18004577b  lea     rbp, [rsp-0FB0h]
0x180045783  mov     eax, 10B0h
0x180045788  call    _alloca_probe
0x18004578d  sub     rsp, rax
0x180045790  mov     rax, cs:__security_cookie
0x180045797  xor     rax, rsp
0x18004579a  mov     [rbp+0FD0h+var_30], rax
0x1800457a1  mov     rsi, rdx
0x1800457a4  mov     r14d, r8d
0x1800457a7  mov     rdi, rcx
0x1800457aa  mov     [rsp+10D0h+ppv], 0
0x1800457b3  lea     rdx, [rsp+10D0h+ppv]; ppv
0x1800457b8  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800457bf  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800457c5  mov     ebx, eax
0x1800457c7  test    eax, eax
0x1800457c9  js      loc_1800459C8
0x1800457cf  mov     rdx, [rsp+10D0h+ppv]; struct IPropertyStore *
0x1800457d4  mov     r8, rsi; struct IXmlReader *
0x1800457d7  mov     rcx, rdi; this
0x1800457da  call    ?_ParseItemProperties@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@PEAUIXmlReader@@@Z; COpenSearchRowset::_ParseItemProperties(IPropertyStore *,IXmlReader *)
0x1800457df  mov     ebx, eax
0x1800457e1  test    eax, eax
0x1800457e3  js      loc_1800459BE
0x1800457e9  mov     rdx, [rsp+10D0h+ppv]; struct IPropertyStore *
0x1800457ee  mov     rcx, rdi; this
0x1800457f1  call    ?_FillFallbackProps@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@@Z; COpenSearchRowset::_FillFallbackProps(IPropertyStore *)
0x1800457f6  mov     ebx, eax
0x1800457f8  test    eax, eax
0x1800457fa  js      loc_1800459BE
0x180045800  mov     rdx, [rsp+10D0h+ppv]; struct IPropertyStore *
0x180045805  mov     rcx, rdi; this
0x180045808  call    ?_FillProps@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@@Z; COpenSearchRowset::_FillProps(IPropertyStore *)
0x18004580d  mov     ebx, eax
0x18004580f  test    eax, eax
0x180045811  jns     loc_1800458B5
0x180045817  mov     rcx, [rsp+10D0h+ppv]
0x18004581c  lea     r8, [rsp+10D0h+pbHash]
0x180045821  lea     rdx, PKEY_ItemUrl
0x180045828  mov     qword ptr [rsp+10D0h+pbHash], 0
0x180045831  call    IPropertyStore_GetString
0x180045836  mov     rcx, [rsp+10D0h+ppv]
0x18004583b  mov     rax, [rcx]
0x18004583e  mov     rax, [rax+10h]
0x180045842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045847  lea     rdx, [rsp+10D0h+ppv]; ppv
0x18004584c  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180045853  call    cs:__imp_PSCreateMemoryPropertyStore
0x180045859  test    eax, eax
0x18004585b  js      short loc_1800458A3
0x18004585d  cmp     ebx, 80070510h
0x180045863  jz      short loc_180045884
0x180045865  lea     rcx, [rdi+328h]
0x18004586c  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x180045871  test    al, al
0x180045873  jz      short loc_1800458A3
0x180045875  mov     rdx, [rsp+10D0h+ppv]; struct IPropertyStore *
0x18004587a  mov     rcx, rdi; this
0x18004587d  call    ?_FillFailureProperties@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@@Z; COpenSearchRowset::_FillFailureProperties(IPropertyStore *)
0x180045882  jmp     short loc_1800458A1
0x180045884  mov     rax, qword ptr [rsp+10D0h+pbHash]
0x180045889  lea     r8, psz
0x180045890  mov     rdx, [rsp+10D0h+ppv]; struct IPropertyStore *
0x180045895  test    rax, rax
0x180045898  cmovnz  r8, rax; unsigned __int16 *
0x18004589c  call    ?_FillBlockedItemProperties@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@PEBG@Z; COpenSearchRowset::_FillBlockedItemProperties(IPropertyStore *,ushort const *)
0x1800458a1  mov     ebx, eax
0x1800458a3  lea     rcx, [rsp+10D0h+pbHash]; void *
0x1800458a8  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800458ad  test    ebx, ebx
0x1800458af  js      loc_1800459BE
0x1800458b5  mov     rax, [rdi+328h]
0x1800458bc  mov     rsi, r14
0x1800458bf  neg     rax
0x1800458c2  lea     r14, [r14+r14*2]
0x1800458c6  mov     r9, [rdi+r14*8+288h]
0x1800458ce  sbb     rcx, rcx
0x1800458d1  and     ecx, 8
0x1800458d4  mov     rax, [rcx+rdi+308h]
0x1800458dc  test    r9, r9
0x1800458df  jz      short loc_1800458E4
0x1800458e1  mov     r9d, [r9]
0x1800458e4  lea     r8, a010uS; "%010u@%s"
0x1800458eb  mov     [rsp+10D0h+var_10B0], rax
0x1800458f0  mov     edx, 82Fh; unsigned __int64
0x1800458f5  lea     rcx, [rsp+10D0h+pszUrl]; unsigned __int16 *
0x1800458fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800458ff  mov     ebx, eax
0x180045901  test    eax, eax
0x180045903  js      loc_1800459BE
0x180045909  mov     r8d, 4; cbHash
0x18004590f  mov     dword ptr [rsp+10D0h+pbHash], 0
0x180045917  lea     rdx, [rsp+10D0h+pbHash]; pbHash
0x18004591c  lea     rcx, [rsp+10D0h+pszUrl]; pszUrl
0x180045921  call    cs:__imp_UrlHashW
0x180045927  mov     ebx, eax
0x180045929  test    eax, eax
0x18004592b  js      loc_1800459BE
0x180045931  mov     r8d, dword ptr [rsp+10D0h+pbHash]
0x180045936  lea     rdx, PKEY_ItemId
0x18004593d  mov     rcx, [rsp+10D0h+ppv]
0x180045942  call    IPropertyStore_SetInt
0x180045947  mov     ebx, eax
0x180045949  test    eax, eax
0x18004594b  js      short loc_1800459BE
0x18004594d  lea     rdx, [rsi+rsi*2]
0x180045951  mov     rax, [rdi+rdx*8+288h]
0x180045959  test    rax, rax
0x18004595c  jz      short loc_180045962
0x18004595e  mov     ecx, [rax]
0x180045960  jmp     short loc_180045964
0x180045962  xor     ecx, ecx
0x180045964  mov     eax, 3E8h
0x180045969  mov     r8d, 0
0x18004596f  sub     eax, [rdi+rdx*8+278h]
0x180045976  lea     rdx, PKEY_Search_Rank
0x18004597d  sub     eax, ecx
0x18004597f  mov     rcx, [rsp+10D0h+ppv]
0x180045984  cmovns  r8d, eax
0x180045988  call    IPropertyStore_SetInt
0x18004598d  mov     ebx, eax
0x18004598f  test    eax, eax
0x180045991  js      short loc_1800459BE
0x180045993  mov     r8, [rsp+10D0h+ppv]; p
0x180045998  mov     edx, 7FFFFFFFh; i
0x18004599d  mov     rcx, [rdi+r14*8+288h]; hdpa
0x1800459a5  call    cs:__imp_DPA_InsertPtr
0x1800459ab  cmp     eax, 0FFFFFFFFh
0x1800459ae  jz      short loc_1800459B9
0x1800459b0  xor     ebx, ebx
0x1800459b2  mov     [rsp+10D0h+ppv], rbx
0x1800459b7  jmp     short loc_1800459BE
0x1800459b9  mov     ebx, 8007000Eh
0x1800459be  lea     rcx, [rsp+10D0h+ppv]
0x1800459c3  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1800459c8  mov     eax, ebx
0x1800459ca  mov     rcx, [rbp+0FD0h+var_30]
0x1800459d1  xor     rcx, rsp; StackCookie
0x1800459d4  call    __security_check_cookie
0x1800459d9  add     rsp, 10B0h
0x1800459e0  pop     r14
0x1800459e2  pop     rdi
0x1800459e3  pop     rsi
0x1800459e4  pop     rbx
0x1800459e5  pop     rbp
0x1800459e6  retn
```
