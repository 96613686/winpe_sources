# HelperClass::CreateParameterXmlFile(DSKeyValuePair *,int)

- ea: `0x18001b3ac`
- end: `0x18001b7e2`
- name: `?CreateParameterXmlFile@HelperClass@@SAJPEAUDSKeyValuePair@@H@Z`
- size: `1078`
- prototype: `__int64 __fastcall(struct DSKeyValuePair *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800068e0`
- `0x180006e30`

## callees

- `0x180003fc0`
- `0x180004b78`
- `0x18000517c`
- `0x1800112d0`
- `0x18001b3ac`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b483`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b483`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001b673`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001b673`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001b6b5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001b6b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001b6a4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001b6a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b40f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b41f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b42f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b441`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b540`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b570`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b718`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b40f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b41f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b42f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b441`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b540`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b570`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b718`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b642`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b76b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b779`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b78c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b79a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b642`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b76b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b779`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b78c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b79a`
- `OLEAUT32!__imp_VariantInit` at `0x18001b55d`
- `OLEAUT32!__imp_VariantInit` at `0x18001b704`
- `OLEAUT32!__imp_VariantInit` at `0x18001b55d`
- `OLEAUT32!__imp_VariantInit` at `0x18001b704`
- `OLEAUT32!__imp_VariantClear` at `0x18001b64d`
- `OLEAUT32!__imp_VariantClear` at `0x18001b756`
- `OLEAUT32!__imp_VariantClear` at `0x18001b64d`
- `OLEAUT32!__imp_VariantClear` at `0x18001b756`

## string_xrefs

- `0x18001b408`: `<?xml version="1.0" encoding="utf-8"?><Objects><Object></Object></Objects>`
- `0x18001b6da`: `\input.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HelperClass::CreateParameterXmlFile(struct DSKeyValuePair *a1, int a2)
{
  struct DSKeyValuePair *v3; // r14
  int v4; // edi
  OLECHAR *v5; // r15
  OLECHAR *v6; // r12
  OLECHAR *v7; // r13
  HRESULT v8; // ebx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, OLECHAR *, __int64 *); // rbx
  const OLECHAR *v11; // rbx
  OLECHAR *v12; // r14
  unsigned __int64 v13; // rdx
  DWORD FileAttributesW; // eax
  unsigned __int64 v15; // rdx
  BOOL DirectoryW; // eax
  __int16 v18; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h]
  struct DSKeyValuePair *v25; // [rsp+78h] [rbp-88h]
  VARIANTARG v26; // [rsp+80h] [rbp-80h] BYREF
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = a1;
  v25 = a1;
  v18 = -1;
  v4 = 0;
  if ( !a1 || a2 < 0 )
    return 2147942487LL;
  ppv = 0;
  v22 = 0;
  v5 = SysAllocString(L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Objects><Object></Object></Objects>");
  v6 = SysAllocString(L"/Objects/Object");
  bstrString = SysAllocString(L"Property");
  v7 = SysAllocString(L"Name");
  memset_0(FileName, 0, 0x208u);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppv);
  v8 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v5, &v18);
      if ( v8 >= 0 )
      {
        if ( v18 )
        {
          v9 = ppv;
          v10 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 296LL);
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v22);
          v8 = v10(v9, v6, &v22);
          v4 = 0;
        }
        else
        {
          v8 = -2147467259;
        }
      }
    }
  }
  if ( a2 > 0 )
  {
    while ( v8 >= 0 )
    {
      v21 = 0;
      v23 = 0;
      v11 = (const OLECHAR *)((char *)v3 + 1020 * (unsigned int)v4);
      v12 = SysAllocString(v11 + 255);
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(v11);
      v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 376LL))(ppv, bstrString, &v21);
      if ( v8 >= 0 )
      {
        v26 = pvarg;
        v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v21 + 360LL))(v21, v7, &v26);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 392LL))(ppv, v12, &v23);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v21 + 168LL))(v21, v23, 0);
            if ( v8 >= 0 )
              v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v22 + 168LL))(v22, v21, 0);
          }
        }
      }
      if ( v12 )
        SysFreeString(v12);
      VariantClear(&pvarg);
      ++v4;
      v3 = v25;
      if ( v4 >= a2 )
        goto LABEL_19;
    }
    goto LABEL_29;
  }
LABEL_19:
  if ( v8 >= 0 )
  {
    if ( (unsigned int)GetTempPath2W(260, FileName) - 1 > 0x103 )
    {
LABEL_28:
      v8 = -2147467259;
      goto LABEL_29;
    }
    v8 = StringCchCatW(FileName, v13, L"Gethelp");
    if ( v8 >= 0 )
    {
      FileAttributesW = GetFileAttributesW(FileName);
      if ( FileAttributesW == -1 )
      {
        DirectoryW = CreateDirectoryW(FileName, 0);
        v8 = !DirectoryW ? 0x80004005 : 0;
        if ( !DirectoryW )
          goto LABEL_29;
LABEL_26:
        v8 = StringCchCatW(FileName, v15, L"\\input.xml");
        if ( v8 >= 0 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(FileName);
          v26 = pvarg;
          v8 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 528LL))(ppv, &v26);
          VariantClear(&pvarg);
        }
        goto LABEL_29;
      }
      if ( (FileAttributesW & 0x10) != 0 )
        goto LABEL_26;
      goto LABEL_28;
    }
  }
LABEL_29:
  if ( v5 )
    SysFreeString(v5);
  if ( v6 )
    SysFreeString(v6);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v7 )
    SysFreeString(v7);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b3ac  push    rbp
0x18001b3ae  push    rbx
0x18001b3af  push    rsi
0x18001b3b0  push    rdi
0x18001b3b1  push    r12
0x18001b3b3  push    r13
0x18001b3b5  push    r14
0x18001b3b7  push    r15
0x18001b3b9  lea     rbp, [rsp-1C8h]
0x18001b3c1  sub     rsp, 2C8h
0x18001b3c8  mov     rax, cs:__security_cookie
0x18001b3cf  xor     rax, rsp
0x18001b3d2  mov     [rbp+200h+var_50], rax
0x18001b3d9  mov     esi, edx
0x18001b3db  mov     r14, rcx
0x18001b3de  mov     [rsp+300h+var_288], rcx
0x18001b3e3  or      eax, 0FFFFFFFFh
0x18001b3e6  mov     [rsp+300h+var_2D0], ax
0x18001b3eb  xor     edi, edi
0x18001b3ed  test    rcx, rcx
0x18001b3f0  jz      loc_18001B7BA
0x18001b3f6  test    edx, edx
0x18001b3f8  js      loc_18001B7BA
0x18001b3fe  mov     [rsp+300h+var_2C8], rdi
0x18001b403  mov     [rsp+300h+var_2A0], rdi
0x18001b408  lea     rcx, psz; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001b40f  call    cs:__imp_SysAllocString
0x18001b415  mov     r15, rax
0x18001b418  lea     rcx, aObjectsObject; "/Objects/Object"
0x18001b41f  call    cs:__imp_SysAllocString
0x18001b425  mov     r12, rax
0x18001b428  lea     rcx, aProperty; "Property"
0x18001b42f  call    cs:__imp_SysAllocString
0x18001b435  mov     [rsp+300h+bstrString], rax
0x18001b43a  lea     rcx, aName; "Name"
0x18001b441  call    cs:__imp_SysAllocString
0x18001b447  mov     r13, rax
0x18001b44a  xor     edx, edx; Val
0x18001b44c  mov     r8d, 208h; Size
0x18001b452  lea     rcx, [rbp+200h+FileName]; void *
0x18001b456  call    memset_0
0x18001b45b  lea     rcx, [rsp+300h+var_2C8]
0x18001b460  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b465  lea     rax, [rsp+300h+var_2C8]
0x18001b46a  mov     [rsp+300h+ppv], rax; ppv
0x18001b46f  lea     r9, IID_IXMLDOMDocument2; riid
0x18001b476  xor     edx, edx; pUnkOuter
0x18001b478  lea     r8d, [rdi+15h]; dwClsContext
0x18001b47c  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001b483  call    cs:__imp_CoCreateInstance
0x18001b489  mov     ebx, eax
0x18001b48b  test    eax, eax
0x18001b48d  js      short loc_18001B50B
0x18001b48f  mov     rcx, [rsp+300h+var_2C8]
0x18001b494  mov     rax, [rcx]
0x18001b497  xor     edx, edx
0x18001b499  mov     rax, [rax+1F8h]
0x18001b4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a5  mov     ebx, eax
0x18001b4a7  test    eax, eax
0x18001b4a9  js      short loc_18001B50B
0x18001b4ab  mov     rcx, [rsp+300h+var_2C8]
0x18001b4b0  mov     rax, [rcx]
0x18001b4b3  lea     r8, [rsp+300h+var_2D0]
0x18001b4b8  mov     rdx, r15
0x18001b4bb  mov     rax, [rax+208h]
0x18001b4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c7  mov     ebx, eax
0x18001b4c9  test    eax, eax
0x18001b4cb  js      short loc_18001B50B
0x18001b4cd  cmp     [rsp+300h+var_2D0], di
0x18001b4d2  jnz     short loc_18001B4DB
0x18001b4d4  mov     ebx, 80004005h
0x18001b4d9  jmp     short loc_18001B50B
0x18001b4db  mov     rdi, [rsp+300h+var_2C8]
0x18001b4e0  mov     rax, [rdi]
0x18001b4e3  mov     rbx, [rax+128h]
0x18001b4ea  lea     rcx, [rsp+300h+var_2A0]
0x18001b4ef  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b4f4  lea     r8, [rsp+300h+var_2A0]
0x18001b4f9  mov     rdx, r12
0x18001b4fc  mov     rcx, rdi
0x18001b4ff  mov     rax, rbx
0x18001b502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b507  mov     ebx, eax
0x18001b509  xor     edi, edi
0x18001b50b  test    esi, esi
0x18001b50d  jle     loc_18001B662
0x18001b513  test    ebx, ebx
0x18001b515  js      loc_18001B763
0x18001b51b  mov     [rsp+300h+var_2A8], 0
0x18001b524  mov     [rsp+300h+var_298], 0
0x18001b52d  mov     eax, edi
0x18001b52f  imul    rbx, rax, 3FCh
0x18001b536  add     rbx, r14
0x18001b539  lea     rcx, [rbx+1FEh]; psz
0x18001b540  call    cs:__imp_SysAllocString
0x18001b546  mov     r14, rax
0x18001b549  xorps   xmm0, xmm0
0x18001b54c  xor     eax, eax
0x18001b54e  movups  xmmword ptr [rsp+300h+pvarg], xmm0
0x18001b553  mov     qword ptr [rsp+300h+pvarg+10h], rax
0x18001b558  lea     rcx, [rsp+300h+pvarg]; pvarg
0x18001b55d  call    cs:__imp_VariantInit
0x18001b563  mov     eax, 8
0x18001b568  mov     word ptr [rsp+300h+pvarg], ax
0x18001b56d  mov     rcx, rbx; psz
0x18001b570  call    cs:__imp_SysAllocString
0x18001b576  mov     qword ptr [rsp+300h+pvarg+8], rax
0x18001b57b  mov     rcx, [rsp+300h+var_2C8]
0x18001b580  mov     rdx, [rcx]
0x18001b583  mov     rax, [rdx+178h]
0x18001b58a  lea     r8, [rsp+300h+var_2A8]
0x18001b58f  mov     rdx, [rsp+300h+bstrString]
0x18001b594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b599  mov     ebx, eax
0x18001b59b  test    eax, eax
0x18001b59d  js      loc_18001B63A
0x18001b5a3  movups  xmm0, xmmword ptr [rsp+300h+pvarg]
0x18001b5a8  movaps  [rbp+200h+var_280], xmm0
0x18001b5ac  movsd   xmm1, qword ptr [rsp+300h+pvarg+10h]
0x18001b5b2  movsd   [rbp+200h+var_270], xmm1
0x18001b5b7  mov     rcx, [rsp+300h+var_2A8]
0x18001b5bc  mov     rax, [rcx]
0x18001b5bf  lea     r8, [rbp+200h+var_280]
0x18001b5c3  mov     rdx, r13
0x18001b5c6  mov     rax, [rax+168h]
0x18001b5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5d2  mov     ebx, eax
0x18001b5d4  test    eax, eax
0x18001b5d6  js      short loc_18001B63A
0x18001b5d8  mov     rcx, [rsp+300h+var_2C8]
0x18001b5dd  mov     rax, [rcx]
0x18001b5e0  lea     r8, [rsp+300h+var_298]
0x18001b5e5  mov     rdx, r14
0x18001b5e8  mov     rax, [rax+188h]
0x18001b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5f4  mov     ebx, eax
0x18001b5f6  test    eax, eax
0x18001b5f8  js      short loc_18001B63A
0x18001b5fa  mov     rcx, [rsp+300h+var_2A8]
0x18001b5ff  mov     rax, [rcx]
0x18001b602  xor     r8d, r8d
0x18001b605  mov     rdx, [rsp+300h+var_298]
0x18001b60a  mov     rax, [rax+0A8h]
0x18001b611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b616  mov     ebx, eax
0x18001b618  test    eax, eax
0x18001b61a  js      short loc_18001B63A
0x18001b61c  mov     rcx, [rsp+300h+var_2A0]
0x18001b621  mov     rax, [rcx]
0x18001b624  xor     r8d, r8d
0x18001b627  mov     rdx, [rsp+300h+var_2A8]
0x18001b62c  mov     rax, [rax+0A8h]
0x18001b633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b638  mov     ebx, eax
0x18001b63a  test    r14, r14
0x18001b63d  jz      short loc_18001B648
0x18001b63f  mov     rcx, r14; bstrString
0x18001b642  call    cs:__imp_SysFreeString
0x18001b648  lea     rcx, [rsp+300h+pvarg]; pvarg
0x18001b64d  call    cs:__imp_VariantClear
0x18001b653  inc     edi
0x18001b655  cmp     edi, esi
0x18001b657  mov     r14, [rsp+300h+var_288]
0x18001b65c  jl      loc_18001B513
0x18001b662  test    ebx, ebx
0x18001b664  js      loc_18001B763
0x18001b66a  lea     rdx, [rbp+200h+FileName]
0x18001b66e  mov     ecx, 104h
0x18001b673  call    cs:__imp_GetTempPath2W
0x18001b679  dec     eax
0x18001b67b  cmp     eax, 103h
0x18001b680  ja      loc_18001B75E
0x18001b686  lea     r8, aGethelp; "Gethelp"
0x18001b68d  lea     rcx, [rbp+200h+FileName]; unsigned __int16 *
0x18001b691  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b696  mov     ebx, eax
0x18001b698  test    eax, eax
0x18001b69a  js      loc_18001B763
0x18001b6a0  lea     rcx, [rbp+200h+FileName]; lpFileName
0x18001b6a4  call    cs:__imp_GetFileAttributesW
0x18001b6aa  cmp     eax, 0FFFFFFFFh
0x18001b6ad  jnz     short loc_18001B6D2
0x18001b6af  xor     edx, edx; lpSecurityAttributes
0x18001b6b1  lea     rcx, [rbp+200h+FileName]; lpPathName
0x18001b6b5  call    cs:__imp_CreateDirectoryW
0x18001b6bb  mov     ecx, eax
0x18001b6bd  neg     ecx
0x18001b6bf  sbb     ebx, ebx
0x18001b6c1  not     ebx
0x18001b6c3  and     ebx, 80004005h
0x18001b6c9  test    eax, eax
0x18001b6cb  jnz     short loc_18001B6DA
0x18001b6cd  jmp     loc_18001B763
0x18001b6d2  test    al, 10h
0x18001b6d4  jz      loc_18001B75E
0x18001b6da  lea     r8, aInputXml; "\\input.xml"
0x18001b6e1  lea     rcx, [rbp+200h+FileName]; unsigned __int16 *
0x18001b6e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b6ea  mov     ebx, eax
0x18001b6ec  test    eax, eax
0x18001b6ee  js      short loc_18001B763
0x18001b6f0  xorps   xmm0, xmm0
0x18001b6f3  xor     eax, eax
0x18001b6f5  movups  xmmword ptr [rsp+300h+pvarg], xmm0
0x18001b6fa  mov     qword ptr [rsp+300h+pvarg+10h], rax
0x18001b6ff  lea     rcx, [rsp+300h+pvarg]; pvarg
0x18001b704  call    cs:__imp_VariantInit
0x18001b70a  mov     eax, 8
0x18001b70f  mov     word ptr [rsp+300h+pvarg], ax
0x18001b714  lea     rcx, [rbp+200h+FileName]; psz
0x18001b718  call    cs:__imp_SysAllocString
0x18001b71e  mov     qword ptr [rsp+300h+pvarg+8], rax
0x18001b723  mov     rcx, [rsp+300h+var_2C8]
0x18001b728  movups  xmm0, xmmword ptr [rsp+300h+pvarg]
0x18001b72d  movaps  [rbp+200h+var_280], xmm0
0x18001b731  movsd   xmm1, qword ptr [rsp+300h+pvarg+10h]
0x18001b737  movsd   [rbp+200h+var_270], xmm1
0x18001b73c  mov     rax, [rcx]
0x18001b73f  lea     rdx, [rbp+200h+var_280]
0x18001b743  mov     rax, [rax+210h]
0x18001b74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b74f  mov     ebx, eax
0x18001b751  lea     rcx, [rsp+300h+pvarg]; pvarg
0x18001b756  call    cs:__imp_VariantClear
0x18001b75c  jmp     short loc_18001B763
0x18001b75e  mov     ebx, 80004005h
0x18001b763  test    r15, r15
0x18001b766  jz      short loc_18001B771
0x18001b768  mov     rcx, r15; bstrString
0x18001b76b  call    cs:__imp_SysFreeString
0x18001b771  test    r12, r12
0x18001b774  jz      short loc_18001B77F
0x18001b776  mov     rcx, r12; bstrString
0x18001b779  call    cs:__imp_SysFreeString
0x18001b77f  mov     rax, [rsp+300h+bstrString]
0x18001b784  test    rax, rax
0x18001b787  jz      short loc_18001B792
0x18001b789  mov     rcx, rax; bstrString
0x18001b78c  call    cs:__imp_SysFreeString
0x18001b792  test    r13, r13
0x18001b795  jz      short loc_18001B7A1
0x18001b797  mov     rcx, r13; bstrString
0x18001b79a  call    cs:__imp_SysFreeString
0x18001b7a0  nop
0x18001b7a1  lea     rcx, [rsp+300h+var_2A0]
0x18001b7a6  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b7ab  nop
0x18001b7ac  lea     rcx, [rsp+300h+var_2C8]
0x18001b7b1  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b7b6  mov     eax, ebx
0x18001b7b8  jmp     short loc_18001B7BF
0x18001b7ba  mov     eax, 80070057h
0x18001b7bf  mov     rcx, [rbp+200h+var_50]
0x18001b7c6  xor     rcx, rsp; StackCookie
0x18001b7c9  call    __security_check_cookie
0x18001b7ce  add     rsp, 2C8h
0x18001b7d5  pop     r15
0x18001b7d7  pop     r14
0x18001b7d9  pop     r13
0x18001b7db  pop     r12
0x18001b7dd  pop     rdi
0x18001b7de  pop     rsi
0x18001b7df  pop     rbx
0x18001b7e0  pop     rbp
0x18001b7e1  retn
```
