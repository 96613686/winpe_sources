# CPubFolderEnum::_CreateItemIDFromAppInfo(int,_AppInfoData *,_tagSlowAppInfo *,_MANAGEDAPPLICATION *,_PubAppInfo *,uint,_ITEMID_CHILD * *)

- ea: `0x1800440dc`
- end: `0x180044304`
- name: `?_CreateItemIDFromAppInfo@CPubFolderEnum@@AEAAJHPEAU_AppInfoData@@PEAU_tagSlowAppInfo@@PEAU_MANAGEDAPPLICATION@@PEAU_PubAppInfo@@IPEAPEAU_ITEMID_CHILD@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(CPubFolderEnum *__hidden this, int, struct _AppInfoData *, struct _tagSlowAppInfo *, struct _MANAGEDAPPLICATION *, struct _PubAppInfo *, unsigned int, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004430c`

## callees

- `0x18000791c`
- `0x180008cf8`
- `0x1800440dc`
- `0x180044730`
- `0x18005165c`
- `0x18005169c`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004414c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18004414c`
- `SHLWAPI!PathParseIconLocationW` at `0x180044197`
- `SHLWAPI!PathParseIconLocationW` at `0x1800441b4`
- `SHLWAPI!PathParseIconLocationW` at `0x180044197`
- `SHLWAPI!PathParseIconLocationW` at `0x1800441b4`

## pseudocode

```c
__int64 __fastcall CPubFolderEnum::_CreateItemIDFromAppInfo(
        CPubFolderEnum *this,
        __int64 a2,
        struct _AppInfoData *a3,
        struct _tagSlowAppInfo *a4,
        struct _MANAGEDAPPLICATION *a5,
        struct _PubAppInfo *a6,
        unsigned int a7,
        struct _ITEMID_CHILD **a8)
{
  CPubFolderEnum *v8; // r14
  HRESULT v11; // ebx
  LPWSTR pszDisplayName; // r8
  WCHAR *pszImage; // rcx
  LPWSTR v14; // r8
  LPWSTR v15; // rcx
  LPWSTR pszVersion; // r8
  LPWSTR pszPublisher; // r8
  LPWSTR pszSupportUrl; // r8
  LPWSTR pszSource; // r8
  GUID GpoId; // xmm0
  const unsigned __int16 *pszPackageName; // r8
  __int64 v22; // r9
  void *ppv; // [rsp+20h] [rbp-E0h] BYREF
  CPubFolderEnum *v25; // [rsp+28h] [rbp-D8h]
  GUID v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v27[260]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwPathType; // [rsp+248h] [rbp+148h]
  unsigned int v29; // [rsp+24Ch] [rbp+14Ch]

  v8 = this;
  v25 = this;
  *a8 = 0;
  ppv = 0;
  v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v11 >= 0 )
  {
    pszDisplayName = a3->pszDisplayName;
    if ( !pszDisplayName )
    {
      v11 = -2147467259;
      goto LABEL_27;
    }
    v11 = IPropertyStore_SetString(ppv, &PKEY_ItemNameDisplay, pszDisplayName);
    if ( v11 >= 0 )
    {
      pszImage = a3->pszImage;
      if ( pszImage && *pszImage )
      {
        PathParseIconLocationW(pszImage);
        v14 = a3->pszImage;
      }
      else
      {
        v15 = a4->pszImage;
        if ( !v15 || !*v15 )
        {
LABEL_14:
          pszVersion = a3->pszVersion;
          if ( pszVersion )
            IPropertyStore_SetString(ppv, PKEY_Software_ProductVersion, pszVersion);
          pszPublisher = a3->pszPublisher;
          if ( pszPublisher )
            IPropertyStore_SetString(ppv, PKEY_Software_Publisher, pszPublisher);
          pszSupportUrl = a3->pszSupportUrl;
          if ( pszSupportUrl )
            IPropertyStore_SetString(ppv, PKEY_Software_SupportUrl, pszSupportUrl);
          pszSource = a6->pszSource;
          if ( pszSource )
            IPropertyStore_SetString(ppv, PKEY_Software_InstallSource, pszSource);
          if ( a5 )
          {
            memset_0(&v26.Data2, 0, 0x21Cu);
            GpoId = a5->GpoId;
            pszPackageName = a5->pszPackageName;
            dwPathType = a5->dwPathType;
            v26 = GpoId;
            if ( pszPackageName )
              StringCchCopyW(v27, 0x104u, pszPackageName);
            v22 = *((_QWORD *)v8 + 4);
            v29 = a7;
            v11 = CItemIDFactory<tagPUBITEM,1279415632>::s_CreateItemID(&v26, ppv, a8, *(_QWORD *)(v22 + 80));
          }
          goto LABEL_27;
        }
        PathParseIconLocationW(v15);
        v14 = a4->pszImage;
      }
      if ( v14 )
      {
        v11 = IPropertyStore_SetString(ppv, PKEY_IconPath, v14);
        if ( v11 >= 0 )
          IPropertyStore_SetUInt32(ppv, PKEY_IconIndex);
      }
      v8 = v25;
      goto LABEL_14;
    }
  }
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800440dc  mov     [rsp-8+arg_8], rbx
0x1800440e1  push    rbp
0x1800440e2  push    rsi
0x1800440e3  push    rdi
0x1800440e4  push    r12
0x1800440e6  push    r13
0x1800440e8  push    r14
0x1800440ea  push    r15
0x1800440ec  lea     rbp, [rsp-160h]
0x1800440f4  sub     rsp, 260h
0x1800440fb  mov     rax, cs:__security_cookie
0x180044102  xor     rax, rsp
0x180044105  mov     [rbp+190h+var_40], rax
0x18004410c  mov     r12, [rbp+190h+arg_38]
0x180044113  lea     rdx, [rsp+290h+ppv]; ppv
0x180044118  mov     rsi, [rbp+190h+arg_20]
0x18004411f  mov     r14, rcx
0x180044122  mov     r13, [rbp+190h+arg_28]
0x180044129  mov     r15, r9
0x18004412c  mov     [rsp+290h+var_268], rcx
0x180044131  mov     rdi, r8
0x180044134  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18004413b  mov     qword ptr [r12], 0
0x180044143  mov     [rsp+290h+ppv], 0
0x18004414c  call    cs:__imp_PSCreateMemoryPropertyStore
0x180044152  mov     ebx, eax
0x180044154  test    eax, eax
0x180044156  js      loc_1800442CE
0x18004415c  mov     r8, [rdi+8]
0x180044160  test    r8, r8
0x180044163  jz      loc_1800442C9
0x180044169  mov     rcx, [rsp+290h+ppv]
0x18004416e  lea     rdx, PKEY_ItemNameDisplay
0x180044175  call    IPropertyStore_SetString
0x18004417a  mov     ebx, eax
0x18004417c  xor     eax, eax
0x18004417e  test    ebx, ebx
0x180044180  js      loc_1800442CE
0x180044186  mov     rcx, [rdi+80h]; pszIconFile
0x18004418d  test    rcx, rcx
0x180044190  jz      short loc_1800441A6
0x180044192  cmp     [rcx], ax
0x180044195  jz      short loc_1800441A6
0x180044197  call    cs:__imp_PathParseIconLocationW
0x18004419d  mov     r8, [rdi+80h]
0x1800441a4  jmp     short loc_1800441BE
0x1800441a6  mov     rcx, [r15+18h]; pszIconFile
0x1800441aa  test    rcx, rcx
0x1800441ad  jz      short loc_1800441F6
0x1800441af  cmp     [rcx], ax
0x1800441b2  jz      short loc_1800441F6
0x1800441b4  call    cs:__imp_PathParseIconLocationW
0x1800441ba  mov     r8, [r15+18h]
0x1800441be  mov     r14d, eax
0x1800441c1  test    r8, r8
0x1800441c4  jz      short loc_1800441F1
0x1800441c6  mov     rcx, [rsp+290h+ppv]
0x1800441cb  lea     rdx, PKEY_IconPath
0x1800441d2  call    IPropertyStore_SetString
0x1800441d7  mov     ebx, eax
0x1800441d9  test    eax, eax
0x1800441db  js      short loc_1800441F1
0x1800441dd  mov     rcx, [rsp+290h+ppv]
0x1800441e2  lea     rdx, PKEY_IconIndex
0x1800441e9  mov     r8d, r14d
0x1800441ec  call    IPropertyStore_SetUInt32
0x1800441f1  mov     r14, [rsp+290h+var_268]
0x1800441f6  mov     r8, [rdi+10h]
0x1800441fa  test    r8, r8
0x1800441fd  jz      short loc_180044210
0x1800441ff  mov     rcx, [rsp+290h+ppv]
0x180044204  lea     rdx, PKEY_Software_ProductVersion
0x18004420b  call    IPropertyStore_SetString
0x180044210  mov     r8, [rdi+18h]
0x180044214  test    r8, r8
0x180044217  jz      short loc_18004422A
0x180044219  mov     rcx, [rsp+290h+ppv]
0x18004421e  lea     rdx, PKEY_Software_Publisher
0x180044225  call    IPropertyStore_SetString
0x18004422a  mov     r8, [rdi+40h]
0x18004422e  test    r8, r8
0x180044231  jz      short loc_180044244
0x180044233  mov     rcx, [rsp+290h+ppv]
0x180044238  lea     rdx, PKEY_Software_SupportUrl
0x18004423f  call    IPropertyStore_SetString
0x180044244  mov     r8, [r13+8]
0x180044248  test    r8, r8
0x18004424b  jz      short loc_18004425E
0x18004424d  mov     rcx, [rsp+290h+ppv]
0x180044252  lea     rdx, PKEY_Software_InstallSource
0x180044259  call    IPropertyStore_SetString
0x18004425e  test    rsi, rsi
0x180044261  jz      short loc_1800442CE
0x180044263  xor     edx, edx; Val
0x180044265  lea     rcx, [rsp+290h+var_25C]; void *
0x18004426a  mov     r8d, 21Ch; Size
0x180044270  call    memset_0
0x180044275  movups  xmm0, xmmword ptr [rsi+1Ch]
0x180044279  mov     r8, [rsi]; unsigned __int16 *
0x18004427c  mov     eax, [rsi+78h]
0x18004427f  mov     [rbp+190h+var_48], eax
0x180044285  movdqu  xmmword ptr [rsp+30h], xmm0
0x18004428b  test    r8, r8
0x18004428e  jz      short loc_18004429F
0x180044290  mov     edx, 104h; unsigned __int64
0x180044295  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x18004429a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004429f  mov     r9, [r14+20h]
0x1800442a3  lea     rcx, [rsp+290h+var_260]
0x1800442a8  mov     eax, [rbp+190h+arg_30]
0x1800442ae  mov     r8, r12
0x1800442b1  mov     rdx, [rsp+290h+ppv]
0x1800442b6  mov     [rbp+190h+var_44], eax
0x1800442bc  mov     r9, [r9+50h]
0x1800442c0  call    ?s_CreateItemID@?$CItemIDFactory@UtagPUBITEM@@$0EMECFFFA@@@SAJPEFBUtagPUBITEM@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z; CItemIDFactory<tagPUBITEM,1279415632>::s_CreateItemID(tagPUBITEM const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)
0x1800442c5  mov     ebx, eax
0x1800442c7  jmp     short loc_1800442CE
0x1800442c9  mov     ebx, 80004005h
0x1800442ce  lea     rcx, [rsp+290h+ppv]
0x1800442d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800442d8  mov     eax, ebx
0x1800442da  mov     rcx, [rbp+190h+var_40]
0x1800442e1  xor     rcx, rsp; StackCookie
0x1800442e4  call    __security_check_cookie
0x1800442e9  mov     rbx, [rsp+290h+arg_8]
0x1800442f1  add     rsp, 260h
0x1800442f8  pop     r15
0x1800442fa  pop     r14
0x1800442fc  pop     r13
0x1800442fe  pop     r12
0x180044300  pop     rdi
0x180044301  pop     rsi
0x180044302  pop     rbp
0x180044303  retn
```
