# CStartMenuChapteredRowset::_QueryUAData(IPropertyStoreCache *)

- ea: `0x180037a7c`
- end: `0x180037c98`
- name: `?_QueryUAData@CStartMenuChapteredRowset@@QEAAHPEAUIPropertyStoreCache@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(CStartMenuChapteredRowset *__hidden this, struct IPropertyStoreCache *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029368`

## callees

- `0x180005460`
- `0x1800054dc`
- `0x180006900`
- `0x18002ff6c`
- `0x180037a7c`
- `0x180041300`
- `0x180041520`
- `0x180041598`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037be6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037b04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037b04`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CStartMenuChapteredRowset::_QueryUAData(CStartMenuChapteredRowset *this, const struct _GUID *a2)
{
  unsigned int v3; // edi
  const struct _GUID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  int Item; // ebx
  void *v9; // rbx
  void *v10; // rcx
  void *v12; // [rsp+30h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-1h] BYREF
  int v14; // [rsp+40h] [rbp+7h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+Fh] BYREF
  void *v16; // [rsp+50h] [rbp+17h] BYREF
  _DWORD v17[2]; // [rsp+58h] [rbp+1Fh] BYREF
  __int128 v18; // [rsp+60h] [rbp+27h]
  __int64 v19; // [rsp+70h] [rbp+37h]
  int v20; // [rsp+78h] [rbp+3Fh]

  v3 = 0;
  v16 = 0;
  v4 = (const struct _GUID *)((char *)this + 160);
  if ( *(_OWORD *)v4 != *(_OWORD *)&GUID_NULL && SHGetUserAssist(v4, a2, &v16) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_de25675a_72de_44b4_9373_05170450c140, &ppv) >= 0 )
    {
      v14 = 0;
      if ( (int)IPropertyStore_GetUInt32(a2, v5, &v14) >= 0 )
      {
        pv = 0;
        v12 = 0;
        if ( (v14 & 0x10000) != 0 )
        {
          Item = IPropertyStore_GetItem(a2, v6, v7, &v12);
          if ( Item >= 0 )
            Item = (*(__int64 (__fastcall **)(LPVOID, void *, LPVOID *))(*(_QWORD *)ppv + 24LL))(ppv, v12, &pv);
          ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>((__int64 *)&v12);
        }
        else
        {
          if ( (int)IPropertyStore_GetString(a2, &PKEY_ParsingPath, &v12) >= 0
            || (Item = IPropertyStore_GetString(a2, &PKEY_ItemId, &v12), Item >= 0) )
          {
            Item = (*(__int64 (__fastcall **)(LPVOID, void *, _QWORD, LPVOID *))(*(_QWORD *)ppv + 72LL))(
                     ppv,
                     v12,
                     0,
                     &pv);
            if ( Item < 0 )
            {
              v9 = v12;
              v12 = 0;
              v10 = pv;
              pv = 0;
              CoTaskMemFree(v10);
              pv = v9;
              Item = 0;
            }
          }
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v12);
        }
        if ( Item >= 0 )
        {
          v18 = 0;
          v19 = 0;
          v20 = 0;
          v17[0] = 36;
          v17[1] = 16;
          if ( (*(int (__fastcall **)(void *, GUID *, LPVOID, _DWORD *))(*(_QWORD *)v16 + 32LL))(
                 v16,
                 &GUID_cebff5cd_ace2_4f4f_9178_9926f41749ea,
                 pv,
                 v17) >= 0 )
            v3 = (int)(float)(*(float *)&v18 * 1000.0);
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pv);
      }
    }
    ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>((__int64 *)&ppv);
  }
  ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>((__int64 *)&v16);
  return v3;
}

```

## disassembly

```asm
0x180037a7c  mov     [rsp-8+arg_10], rbx
0x180037a81  mov     [rsp-8+arg_18], rdi
0x180037a86  push    rbp
0x180037a87  lea     rbp, [rsp-57h]
0x180037a8c  sub     rsp, 90h
0x180037a93  mov     rax, cs:__security_cookie
0x180037a9a  xor     rax, rsp
0x180037a9d  mov     [rbp+57h+var_10], rax
0x180037aa1  mov     rbx, rdx
0x180037aa4  xor     edi, edi
0x180037aa6  mov     [rbp+57h+var_40], rdi
0x180037aaa  add     rcx, 0A0h; struct _GUID *
0x180037ab1  mov     rax, [rcx]
0x180037ab4  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180037abb  jnz     short loc_180037ACE
0x180037abd  mov     rax, [rcx+8]
0x180037ac1  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180037ac8  jz      loc_180037C6C
0x180037ace  lea     r8, [rbp+57h+var_40]; void **
0x180037ad2  call    ?SHGetUserAssist@@YAJAEBU_GUID@@0PEAPEAX@Z; SHGetUserAssist(_GUID const &,_GUID const &,void * *)
0x180037ad7  test    eax, eax
0x180037ad9  js      loc_180037C6C
0x180037adf  mov     [rbp+57h+var_48], 0
0x180037ae7  lea     rax, [rbp+57h+var_48]
0x180037aeb  mov     [rsp+90h+ppv], rax; ppv
0x180037af0  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180037af7  xor     edx, edx; pUnkOuter
0x180037af9  lea     r8d, [rdx+3]; dwClsContext
0x180037afd  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180037b04  call    cs:__imp_CoCreateInstance
0x180037b0a  test    eax, eax
0x180037b0c  js      loc_180037C62
0x180037b12  mov     [rbp+57h+var_50], 0
0x180037b19  lea     r8, [rbp+57h+var_50]
0x180037b1d  mov     rcx, rbx
0x180037b20  call    IPropertyStore_GetUInt32
0x180037b25  test    eax, eax
0x180037b27  js      loc_180037C62
0x180037b2d  mov     [rbp+57h+pv], 0
0x180037b35  mov     [rbp+57h+var_60], 0
0x180037b3d  test    [rbp+57h+var_50], 10000h
0x180037b44  jz      short loc_180037B7D
0x180037b46  lea     r9, [rbp+57h+var_60]
0x180037b4a  mov     rcx, rbx
0x180037b4d  call    IPropertyStore_GetItem
0x180037b52  mov     ebx, eax
0x180037b54  test    eax, eax
0x180037b56  js      short loc_180037B72
0x180037b58  mov     rcx, [rbp+57h+var_48]
0x180037b5c  mov     rax, [rcx]
0x180037b5f  lea     r8, [rbp+57h+pv]
0x180037b63  mov     rdx, [rbp+57h+var_60]
0x180037b67  mov     rax, [rax+18h]
0x180037b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b70  mov     ebx, eax
0x180037b72  lea     rcx, [rbp+57h+var_60]
0x180037b76  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180037b7b  jmp     short loc_180037BFB
0x180037b7d  lea     r8, [rbp+57h+var_60]
0x180037b81  lea     rdx, PKEY_ParsingPath
0x180037b88  mov     rcx, rbx
0x180037b8b  call    IPropertyStore_GetString
0x180037b90  test    eax, eax
0x180037b92  jns     short loc_180037BAD
0x180037b94  lea     r8, [rbp+57h+var_60]
0x180037b98  lea     rdx, PKEY_ItemId
0x180037b9f  mov     rcx, rbx
0x180037ba2  call    IPropertyStore_GetString
0x180037ba7  mov     ebx, eax
0x180037ba9  test    eax, eax
0x180037bab  js      short loc_180037BF2
0x180037bad  mov     rcx, [rbp+57h+var_48]
0x180037bb1  mov     rax, [rcx]
0x180037bb4  lea     r9, [rbp+57h+pv]
0x180037bb8  xor     r8d, r8d
0x180037bbb  mov     rdx, [rbp+57h+var_60]
0x180037bbf  mov     rax, [rax+48h]
0x180037bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bc8  mov     ebx, eax
0x180037bca  test    eax, eax
0x180037bcc  jns     short loc_180037BF2
0x180037bce  mov     rbx, [rbp+57h+var_60]
0x180037bd2  mov     [rbp+57h+var_60], 0
0x180037bda  mov     rcx, [rbp+57h+pv]; pv
0x180037bde  mov     [rbp+57h+pv], 0
0x180037be6  call    cs:__imp_CoTaskMemFree
0x180037bec  mov     [rbp+57h+pv], rbx
0x180037bf0  xor     ebx, ebx
0x180037bf2  lea     rcx, [rbp+57h+var_60]; void *
0x180037bf6  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180037bfb  test    ebx, ebx
0x180037bfd  js      short loc_180037C58
0x180037bff  xorps   xmm0, xmm0
0x180037c02  movdqu  [rbp+57h+var_30], xmm0
0x180037c07  mov     [rbp+57h+var_20], 0
0x180037c0f  mov     [rbp+57h+var_18], 0
0x180037c16  mov     [rbp+57h+var_38], 24h ; '$'
0x180037c1d  mov     [rbp+57h+var_34], 10h
0x180037c24  mov     rcx, [rbp+57h+var_40]
0x180037c28  mov     rax, [rcx]
0x180037c2b  lea     r9, [rbp+57h+var_38]
0x180037c2f  mov     r8, [rbp+57h+pv]
0x180037c33  lea     rdx, _GUID_cebff5cd_ace2_4f4f_9178_9926f41749ea
0x180037c3a  mov     rax, [rax+20h]
0x180037c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c43  test    eax, eax
0x180037c45  js      short loc_180037C58
0x180037c47  movss   xmm0, dword ptr [rbp+57h+var_30]
0x180037c4c  mulss   xmm0, cs:__real@447a0000
0x180037c54  cvttss2si edi, xmm0
0x180037c58  lea     rcx, [rbp+57h+pv]; void *
0x180037c5c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180037c61  nop
0x180037c62  lea     rcx, [rbp+57h+var_48]
0x180037c66  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180037c6b  nop
0x180037c6c  lea     rcx, [rbp+57h+var_40]
0x180037c70  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180037c75  mov     eax, edi
0x180037c77  mov     rcx, [rbp+57h+var_10]
0x180037c7b  xor     rcx, rsp; StackCookie
0x180037c7e  call    __security_check_cookie
0x180037c83  lea     r11, [rsp+90h+var_s0]
0x180037c8b  mov     rbx, [r11+20h]
0x180037c8f  mov     rdi, [r11+28h]
0x180037c93  mov     rsp, r11
0x180037c96  pop     rbp
0x180037c97  retn
```
