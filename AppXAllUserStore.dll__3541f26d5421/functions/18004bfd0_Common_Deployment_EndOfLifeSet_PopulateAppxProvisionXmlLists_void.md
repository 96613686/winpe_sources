# Common::Deployment::EndOfLifeSet::PopulateAppxProvisionXmlLists(void)

- ea: `0x18004bfd0`
- end: `0x18004c35a`
- name: `?PopulateAppxProvisionXmlLists@EndOfLifeSet@Deployment@Common@@CAJXZ`
- size: `906`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004be74`

## callees

- `0x180004920`
- `0x180010384`
- `0x180018248`
- `0x18001a324`
- `0x18001a464`
- `0x18001ca24`
- `0x18004682c`
- `0x18004875c`
- `0x18004bb2c`
- `0x18004bfd0`
- `0x18004c73c`
- `0x18004c98a`
- `0x18004c9d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004c058`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004c058`

## string_xrefs

- `0x18004c025`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c069`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c0b4`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c113`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c16a`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c1ce`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c315`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c337`: `onecore\admin\appmodel\common\endoflifeset.cpp`
- `0x18004c101`: `appxProvision XML file not found`
- `0x18004c08d`: `AppxProvisioning.xml`

## pseudocode

```c
__int64 Common::Deployment::EndOfLifeSet::PopulateAppxProvisionXmlLists(void)
{
  int v0; // eax
  unsigned int LastError; // ebx
  const char *v2; // r9
  int v3; // eax
  bool *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, Common *, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  int inserted; // eax
  StringSet *v16; // rcx
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h]
  const char *v20; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  Common *v28[2]; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v27 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v27);
  v0 = CreateAppxProvisionFactory(&v27);
  LastError = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
      (const char *)(unsigned int)v0,
      v19);
    goto LABEL_27;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5B,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
                  v2);
    goto LABEL_27;
  }
  v29 = 0;
  *(_OWORD *)v28 = 0;
  v3 = Common::PathHelpers::CombinePaths(Buffer, L"AppxProvisioning.xml", (struct Common::StringBuffer *)v28);
  LastError = v3;
  if ( v3 < 0 )
  {
    v5 = 94;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
      (const char *)(unsigned int)v3,
      v19);
LABEL_8:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
    goto LABEL_27;
  }
  LOBYTE(v21) = 0;
  v3 = Common::FileExists(v28[1], &v21, v4);
  LastError = v3;
  if ( v3 < 0 )
  {
    v5 = 99;
    goto LABEL_7;
  }
  if ( (_BYTE)v21 )
  {
    v6 = v27;
    v24 = 0;
    v7 = *(__int64 (__fastcall **)(__int64, Common *, __int64 *))(*(_QWORD *)v27 + 24LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
    v8 = v7(v6, v28[1], &v24);
    LastError = v8;
    if ( v8 >= 0 )
    {
      v9 = v24;
      v22 = 0;
      v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 24LL);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v22);
      v11 = v10(v9, 1, &v22);
      LastError = v11;
      if ( v11 >= 0 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 40LL))(v22, &v23);
        while ( 1 )
        {
          if ( !v23 )
          {
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v22);
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
            goto LABEL_26;
          }
          v12 = v22;
          v25 = 0;
          v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 32LL);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
          v14 = v13(v12, &v25);
          LastError = v14;
          if ( v14 < 0 )
            break;
          v26 = 0;
          inserted = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v25 + 32LL))(v25, &v26);
          LastError = inserted;
          if ( inserted < 0 )
          {
            v18 = 119;
            goto LABEL_30;
          }
          inserted = StringSet::InsertIgnoreDuplicates(v16, v26);
          LastError = inserted;
          if ( inserted < 0 )
          {
            v18 = 120;
LABEL_30:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v18,
              (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
              (const char *)(unsigned int)inserted,
              v19);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v26);
            goto LABEL_32;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v26);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 48LL))(v22, &v23);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
          (const char *)(unsigned int)v14,
          v19);
LABEL_32:
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E,
          (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
          (const char *)(unsigned int)v11,
          v19);
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v22);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
        (const char *)(unsigned int)v8,
        v19);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
    goto LABEL_8;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x66,
    (unsigned int)"onecore\\admin\\appmodel\\common\\endoflifeset.cpp",
    (const char *)0x80070002LL,
    (int)"appxProvision XML file not found",
    v20);
LABEL_26:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
  LastError = 0;
LABEL_27:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v27);
  return LastError;
}

```

## disassembly

```asm
0x18004bfd0  mov     [rsp-8+arg_0], rbx
0x18004bfd5  mov     [rsp-8+arg_8], rdi
0x18004bfda  push    rbp
0x18004bfdb  lea     rbp, [rsp-1A0h]
0x18004bfe3  sub     rsp, 2A0h
0x18004bfea  mov     rax, cs:__security_cookie
0x18004bff1  xor     rax, rsp
0x18004bff4  mov     [rbp+1A0h+var_10], rax
0x18004bffb  lea     rcx, [rsp+2A0h+var_240]
0x18004c000  mov     [rsp+2A0h+var_240], 0
0x18004c009  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c00e  lea     rcx, [rsp+2A0h+var_240]
0x18004c013  call    CreateAppxProvisionFactory
0x18004c018  mov     ebx, eax
0x18004c01a  test    eax, eax
0x18004c01c  jns     short loc_18004C03E
0x18004c01e  mov     rcx, [rbp+1A8h]; this
0x18004c025  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c02c  mov     r9d, eax; char *
0x18004c02f  mov     edx, 57h ; 'W'; void *
0x18004c034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c039  jmp     loc_18004C2D2
0x18004c03e  xor     edx, edx; Val
0x18004c040  lea     rcx, [rbp+1A0h+Buffer]; void *
0x18004c044  mov     r8d, 208h; Size
0x18004c04a  call    memset_0
0x18004c04f  mov     edx, 104h; uSize
0x18004c054  lea     rcx, [rbp+1A0h+Buffer]; lpBuffer
0x18004c058  call    cs:__imp_GetSystemDirectoryW
0x18004c05e  test    eax, eax
0x18004c060  jnz     short loc_18004C07F
0x18004c062  mov     rcx, [rbp+1A8h]; this
0x18004c069  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c070  lea     edx, [rax+5Bh]; void *
0x18004c073  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c078  mov     ebx, eax
0x18004c07a  jmp     loc_18004C2D2
0x18004c07f  xor     eax, eax
0x18004c081  lea     r8, [rsp+2A0h+var_238]; this
0x18004c086  xorps   xmm0, xmm0
0x18004c089  mov     [rsp+2A0h+var_228], eax
0x18004c08d  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x18004c094  lea     rcx, [rbp+1A0h+Buffer]; Src
0x18004c098  movups  xmmword ptr [rsp+2A0h+var_238], xmm0
0x18004c09d  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18004c0a2  mov     ebx, eax
0x18004c0a4  test    eax, eax
0x18004c0a6  jns     short loc_18004C0D2
0x18004c0a8  mov     edx, 5Eh ; '^'; void *
0x18004c0ad  mov     rcx, [rbp+1A8h]; this
0x18004c0b4  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c0bb  mov     r9d, eax; char *
0x18004c0be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c0c3  lea     rcx, [rsp+2A0h+var_238]; this
0x18004c0c8  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004c0cd  jmp     loc_18004C2D2
0x18004c0d2  mov     rcx, [rsp+2A0h+var_238+8]; this
0x18004c0d7  lea     rdx, [rsp+2A0h+var_270]; unsigned __int16 *
0x18004c0dc  mov     byte ptr [rsp+2A0h+var_270], 0
0x18004c0e1  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x18004c0e6  mov     ebx, eax
0x18004c0e8  test    eax, eax
0x18004c0ea  jns     short loc_18004C0F3
0x18004c0ec  mov     edx, 63h ; 'c'
0x18004c0f1  jmp     short loc_18004C0AD
0x18004c0f3  cmp     byte ptr [rsp+2A0h+var_270], 0
0x18004c0f8  jnz     short loc_18004C129
0x18004c0fa  mov     rcx, [rbp+1A8h]; this
0x18004c101  lea     rax, aAppxprovisionX; "appxProvision XML file not found"
0x18004c108  mov     r9d, 80070002h; char *
0x18004c10e  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18004c113  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c11a  mov     edx, 66h ; 'f'; void *
0x18004c11f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c124  jmp     loc_18004C2C6
0x18004c129  mov     rdi, [rsp+2A0h+var_240]
0x18004c12e  lea     rcx, [rsp+2A0h+var_258]
0x18004c133  mov     [rsp+2A0h+var_258], 0
0x18004c13c  mov     rax, [rdi]
0x18004c13f  mov     rbx, [rax+18h]
0x18004c143  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c148  mov     rdx, [rsp+2A0h+var_238+8]
0x18004c14d  lea     r8, [rsp+2A0h+var_258]
0x18004c152  mov     rcx, rdi
0x18004c155  mov     rax, rbx
0x18004c158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c15d  mov     ebx, eax
0x18004c15f  test    eax, eax
0x18004c161  jns     short loc_18004C18D
0x18004c163  mov     rcx, [rbp+1A8h]; this
0x18004c16a  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c171  mov     r9d, eax; char *
0x18004c174  mov     edx, 6Bh ; 'k'; void *
0x18004c179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c17e  lea     rcx, [rsp+2A0h+var_258]
0x18004c183  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c188  jmp     loc_18004C0C3
0x18004c18d  mov     rdi, [rsp+2A0h+var_258]
0x18004c192  lea     rcx, [rsp+2A0h+var_268]
0x18004c197  mov     [rsp+2A0h+var_268], 0
0x18004c1a0  mov     rax, [rdi]
0x18004c1a3  mov     rbx, [rax+18h]
0x18004c1a7  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c1ac  lea     r8, [rsp+2A0h+var_268]
0x18004c1b1  mov     edx, 1
0x18004c1b6  mov     rcx, rdi
0x18004c1b9  mov     rax, rbx
0x18004c1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1c1  mov     ebx, eax
0x18004c1c3  test    eax, eax
0x18004c1c5  jns     short loc_18004C1EE
0x18004c1c7  mov     rcx, [rbp+1A8h]; this
0x18004c1ce  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c1d5  mov     r9d, eax; char *
0x18004c1d8  mov     edx, 6Eh ; 'n'; void *
0x18004c1dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c1e2  lea     rcx, [rsp+2A0h+var_268]
0x18004c1e7  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c1ec  jmp     short loc_18004C17E
0x18004c1ee  mov     rcx, [rsp+2A0h+var_268]
0x18004c1f3  mov     [rsp+2A0h+var_260], 0
0x18004c1fb  mov     rax, [rcx]
0x18004c1fe  mov     rax, [rax+28h]
0x18004c202  jmp     loc_18004C29D
0x18004c207  mov     rdi, [rsp+2A0h+var_268]
0x18004c20c  lea     rcx, [rsp+2A0h+var_250]
0x18004c211  mov     [rsp+2A0h+var_250], 0
0x18004c21a  mov     rax, [rdi]
0x18004c21d  mov     rbx, [rax+20h]
0x18004c221  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c226  lea     rdx, [rsp+2A0h+var_250]
0x18004c22b  mov     rcx, rdi
0x18004c22e  mov     rax, rbx
0x18004c231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c236  mov     ebx, eax
0x18004c238  test    eax, eax
0x18004c23a  js      loc_18004C330
0x18004c240  mov     rcx, [rsp+2A0h+var_250]
0x18004c245  lea     rdx, [rsp+2A0h+var_248]
0x18004c24a  mov     [rsp+2A0h+var_248], 0
0x18004c253  mov     rax, [rcx]
0x18004c256  mov     rax, [rax+20h]
0x18004c25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c25f  mov     ebx, eax
0x18004c261  test    eax, eax
0x18004c263  js      loc_18004C309
0x18004c269  mov     rdx, [rsp+2A0h+var_248]; unsigned __int16 *
0x18004c26e  call    ?InsertIgnoreDuplicates@StringSet@@QEAAJPEBG@Z; StringSet::InsertIgnoreDuplicates(ushort const *)
0x18004c273  mov     ebx, eax
0x18004c275  test    eax, eax
0x18004c277  js      loc_18004C302
0x18004c27d  lea     rcx, [rsp+2A0h+var_248]
0x18004c282  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004c287  lea     rcx, [rsp+2A0h+var_250]
0x18004c28c  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c291  mov     rcx, [rsp+2A0h+var_268]
0x18004c296  mov     rax, [rcx]
0x18004c299  mov     rax, [rax+30h]
0x18004c29d  lea     rdx, [rsp+2A0h+var_260]
0x18004c2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2a7  cmp     [rsp+2A0h+var_260], 0
0x18004c2ac  jnz     loc_18004C207
0x18004c2b2  lea     rcx, [rsp+2A0h+var_268]
0x18004c2b7  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c2bc  lea     rcx, [rsp+2A0h+var_258]
0x18004c2c1  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c2c6  lea     rcx, [rsp+2A0h+var_238]; this
0x18004c2cb  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004c2d0  xor     ebx, ebx
0x18004c2d2  lea     rcx, [rsp+2A0h+var_240]
0x18004c2d7  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c2dc  mov     eax, ebx
0x18004c2de  mov     rcx, [rbp+1A0h+var_10]
0x18004c2e5  xor     rcx, rsp; StackCookie
0x18004c2e8  call    __security_check_cookie
0x18004c2ed  lea     r11, [rsp+2A0h+var_s0]
0x18004c2f5  mov     rbx, [r11+10h]
0x18004c2f9  mov     rdi, [r11+18h]
0x18004c2fd  mov     rsp, r11
0x18004c300  pop     rbp
0x18004c301  retn
0x18004c302  mov     edx, 78h ; 'x'
0x18004c307  jmp     short loc_18004C30E
0x18004c309  mov     edx, 77h ; 'w'; void *
0x18004c30e  mov     rcx, [rbp+1A8h]; this
0x18004c315  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c31c  mov     r9d, eax; char *
0x18004c31f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c324  lea     rcx, [rsp+2A0h+var_248]
0x18004c329  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004c32e  jmp     short loc_18004C34B
0x18004c330  mov     rcx, [rbp+1A8h]; this
0x18004c337  lea     r8, aOnecoreAdminAp_26; "onecore\\admin\\appmodel\\common\\endof"...
0x18004c33e  mov     r9d, eax; char *
0x18004c341  mov     edx, 74h ; 't'; void *
0x18004c346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c34b  lea     rcx, [rsp+2A0h+var_250]
0x18004c350  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c355  jmp     loc_18004C1E2
```
