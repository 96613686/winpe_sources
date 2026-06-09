# COpenSearchRowset::_ParseMappedProperty(IPropertyStore *,ushort const *,ushort const *,ushort const *)

- ea: `0x180045e30`
- end: `0x180045f98`
- name: `?_ParseMappedProperty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@PEBG11@Z`
- size: `360`
- prototype: `int(COpenSearchRowset *__hidden this, struct IPropertyStore *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800459f0`
- `0x180045b58`

## callees

- `0x180005c88`
- `0x180006900`
- `0x180045e30`
- `0x180045fa0`
- `0x18004944c`
- `0x180049c50`
- `0x180051010`

## import_xrefs

- `SHLWAPI!UrlCompareW` at `0x180045e70`
- `SHLWAPI!UrlCompareW` at `0x180045e70`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x180045e8d`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x180045e8d`

## string_xrefs

- `0x180045e5f`: `http://schemas.microsoft.com/windows/2008/propertynamespace`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseMappedProperty(
        COpenSearchRowset *this,
        struct IPropertyStore *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *pszName)
{
  int v8; // esi
  COpenSearchRowset *v10; // rcx
  COpenSearchPropertyMap *v11; // rcx
  CPropertyMapTable *v12; // rbx
  int PropertyKeys; // edi
  int v14; // ebx
  int v15; // edi
  COpenSearchRowset *v16; // rcx
  CPropertyMapTable *v18; // [rsp+30h] [rbp-40h] BYREF
  int v19; // [rsp+38h] [rbp-38h] BYREF
  struct IPropertyKeyStore *v20; // [rsp+40h] [rbp-30h] BYREF
  PROPERTYKEY ppropkey; // [rsp+48h] [rbp-28h] BYREF

  v8 = 0;
  if ( UrlCompareW(a4, L"http://schemas.microsoft.com/windows/2008/propertynamespace", 1) )
  {
    v11 = (COpenSearchPropertyMap *)*((_QWORD *)this + 105);
    v19 = 0;
    v20 = 0;
    v18 = 0;
    if ( (int)COpenSearchPropertyMap::_GetPropertyMapTable(v11, a4, &v18) >= 0 )
    {
      v12 = v18;
      PropertyKeys = CPropertyMapTable::GetPropertyKeys(v18, pszName, &v20, &v19);
      (*(void (__fastcall **)(CPropertyMapTable *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( PropertyKeys >= 0 )
      {
        LODWORD(v18) = 0;
        v8 = (*(__int64 (__fastcall **)(struct IPropertyKeyStore *, CPropertyMapTable **))(*(_QWORD *)v20 + 24LL))(
               v20,
               &v18);
        if ( v8 >= 0 )
        {
          v14 = 0;
          if ( (int)v18 > 0 )
          {
            v15 = v19;
            do
            {
              memset(&ppropkey, 0, sizeof(ppropkey));
              v8 = (*(__int64 (__fastcall **)(struct IPropertyKeyStore *, _QWORD, PROPERTYKEY *))(*(_QWORD *)v20 + 32LL))(
                     v20,
                     (unsigned int)v14,
                     &ppropkey);
              if ( v8 >= 0 )
                COpenSearchRowset::_ParseProperty(v16, a2, &ppropkey, a3, v15);
              ++v14;
            }
            while ( v14 < (int)v18 );
          }
        }
      }
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v20);
  }
  else
  {
    memset(&ppropkey, 0, sizeof(ppropkey));
    if ( PSGetPropertyKeyFromName(pszName, &ppropkey) >= 0 )
      COpenSearchRowset::_ParseProperty(v10, a2, &ppropkey, a3, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045e30  push    rbp
0x180045e32  push    rbx
0x180045e33  push    rsi
0x180045e34  push    rdi
0x180045e35  push    r13
0x180045e37  push    r14
0x180045e39  push    r15
0x180045e3b  mov     rbp, rsp
0x180045e3e  sub     rsp, 70h
0x180045e42  mov     rax, cs:__security_cookie
0x180045e49  xor     rax, rsp
0x180045e4c  mov     [rbp+var_10], rax
0x180045e50  mov     rbx, [rbp+pszName]
0x180045e54  mov     r15, r8
0x180045e57  mov     r14, rdx
0x180045e5a  mov     r13, rcx
0x180045e5d  xor     esi, esi
0x180045e5f  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180045e66  mov     rcx, r9; psz1
0x180045e69  mov     rdi, r9
0x180045e6c  lea     r8d, [rsi+1]; fIgnoreSlash
0x180045e70  call    cs:__imp_UrlCompareW
0x180045e76  test    eax, eax
0x180045e78  jnz     short loc_180045EB7
0x180045e7a  xorps   xmm0, xmm0
0x180045e7d  lea     rdx, [rbp+ppropkey]; ppropkey
0x180045e81  xor     eax, eax
0x180045e83  mov     rcx, rbx; pszName
0x180045e86  movups  xmmword ptr [rbp+ppropkey.fmtid.Data1], xmm0
0x180045e8a  mov     [rbp+ppropkey.pid], eax
0x180045e8d  call    cs:__imp_PSGetPropertyKeyFromName
0x180045e93  test    eax, eax
0x180045e95  js      loc_180045F7B
0x180045e9b  mov     r9, r15; unsigned __int16 *
0x180045e9e  mov     [rsp+70h+var_50], 1; int
0x180045ea6  lea     r8, [rbp+ppropkey]; struct _tagpropertykey *
0x180045eaa  mov     rdx, r14; struct IPropertyStore *
0x180045ead  call    ?_ParseProperty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBGH@Z; COpenSearchRowset::_ParseProperty(IPropertyStore *,_tagpropertykey const &,ushort const *,int)
0x180045eb2  jmp     loc_180045F7B
0x180045eb7  mov     rcx, [r13+348h]; this
0x180045ebe  lea     r8, [rbp+var_40]; struct CPropertyMapTable **
0x180045ec2  mov     rdx, rdi; unsigned __int16 *
0x180045ec5  mov     [rbp+var_38], esi
0x180045ec8  mov     [rbp+var_30], rsi
0x180045ecc  mov     [rbp+var_40], rsi
0x180045ed0  call    ?_GetPropertyMapTable@COpenSearchPropertyMap@@AEAAJPEBGPEAPEAVCPropertyMapTable@@@Z; COpenSearchPropertyMap::_GetPropertyMapTable(ushort const *,CPropertyMapTable * *)
0x180045ed5  test    eax, eax
0x180045ed7  js      loc_180045F72
0x180045edd  mov     rdx, rbx; unsigned __int16 *
0x180045ee0  lea     r9, [rbp+var_38]; int *
0x180045ee4  mov     rbx, [rbp+var_40]
0x180045ee8  lea     r8, [rbp+var_30]; struct IPropertyKeyStore **
0x180045eec  mov     rcx, rbx; this
0x180045eef  call    ?GetPropertyKeys@CPropertyMapTable@@QEAAJPEBGPEAPEAUIPropertyKeyStore@@PEAH@Z; CPropertyMapTable::GetPropertyKeys(ushort const *,IPropertyKeyStore * *,int *)
0x180045ef4  mov     rdx, [rbx]
0x180045ef7  mov     edi, eax
0x180045ef9  mov     rcx, rbx
0x180045efc  mov     rax, [rdx+10h]
0x180045f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f05  test    edi, edi
0x180045f07  js      short loc_180045F72
0x180045f09  mov     rcx, [rbp+var_30]
0x180045f0d  lea     rdx, [rbp+var_40]
0x180045f11  mov     dword ptr [rbp+var_40], esi
0x180045f14  mov     rax, [rcx]
0x180045f17  mov     rax, [rax+18h]
0x180045f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f20  mov     esi, eax
0x180045f22  test    eax, eax
0x180045f24  js      short loc_180045F72
0x180045f26  xor     ebx, ebx
0x180045f28  cmp     dword ptr [rbp+var_40], ebx
0x180045f2b  jle     short loc_180045F72
0x180045f2d  mov     edi, [rbp+var_38]
0x180045f30  mov     rcx, [rbp+var_30]
0x180045f34  lea     r8, [rbp+ppropkey]
0x180045f38  xor     eax, eax
0x180045f3a  xorps   xmm0, xmm0
0x180045f3d  mov     [rbp+ppropkey.pid], eax
0x180045f40  mov     edx, ebx
0x180045f42  movups  xmmword ptr [rbp+ppropkey.fmtid.Data1], xmm0
0x180045f46  mov     rax, [rcx]
0x180045f49  mov     rax, [rax+20h]
0x180045f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f52  mov     esi, eax
0x180045f54  test    eax, eax
0x180045f56  js      short loc_180045F6B
0x180045f58  mov     r9, r15; unsigned __int16 *
0x180045f5b  mov     [rsp+70h+var_50], edi; int
0x180045f5f  lea     r8, [rbp+ppropkey]; struct _tagpropertykey *
0x180045f63  mov     rdx, r14; struct IPropertyStore *
0x180045f66  call    ?_ParseProperty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBGH@Z; COpenSearchRowset::_ParseProperty(IPropertyStore *,_tagpropertykey const &,ushort const *,int)
0x180045f6b  inc     ebx
0x180045f6d  cmp     ebx, dword ptr [rbp+var_40]
0x180045f70  jl      short loc_180045F30
0x180045f72  lea     rcx, [rbp+var_30]
0x180045f76  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180045f7b  mov     eax, esi
0x180045f7d  mov     rcx, [rbp+var_10]
0x180045f81  xor     rcx, rsp; StackCookie
0x180045f84  call    __security_check_cookie
0x180045f89  add     rsp, 70h
0x180045f8d  pop     r15
0x180045f8f  pop     r14
0x180045f91  pop     r13
0x180045f93  pop     rdi
0x180045f94  pop     rsi
0x180045f95  pop     rbx
0x180045f96  pop     rbp
0x180045f97  retn
```
