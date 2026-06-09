# CAvEndpointBuilder::MigrateEpPropertiesInternal(IPnpInterface *,IMMDevice *,_GUID const &,int,_tagpropertykey const *,uint)

- ea: `0x180028390`
- end: `0x1800285fd`
- name: `?MigrateEpPropertiesInternal@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@PEAUIMMDevice@@AEBU_GUID@@HPEBU_tagpropertykey@@I@Z`
- size: `621`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *this, struct IPnpInterface *, struct IMMDevice *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x1800280e8`
- `0x180028390`
- `0x18003e920`
- `0x18003f780`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800284bf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800284bf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028421`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028553`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028586`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800285c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028421`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028553`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028586`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800285c1`

## string_xrefs

- `0x18002840b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800285ac`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAvEndpointBuilder::MigrateEpPropertiesInternal(
        CAvEndpointBuilder *this,
        struct IPnpInterface *a2,
        struct IMMDevice *a3,
        const struct _GUID *a4,
        int a5)
{
  unsigned int i; // edi
  __int64 v9; // rax
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rax
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  struct IPropertyStore *v14; // rcx
  __int64 v15; // rdx
  int v17; // [rsp+20h] [rbp-50h]
  struct IPropertyStore *v18; // [rsp+30h] [rbp-40h] BYREF
  struct IPropertyStore *v19; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-20h]
  GUID pclsid; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  for ( i = 0; ; ++i )
  {
    v19 = 0;
    pclsid = 0;
    *(_OWORD *)pvar = 0;
    v21 = 0;
    v9 = *(_QWORD *)a2;
    if ( a5 )
      break;
    v18 = 0;
    v11 = (*(__int64 (__fastcall **)(struct IPnpInterface *, _QWORD, _QWORD, struct IPropertyStore **))(v9 + 64))(
            a2,
            i,
            0,
            &v18);
    if ( v11 < 0 )
    {
      v15 = 8785;
      goto LABEL_27;
    }
LABEL_10:
    if ( !v18 )
    {
      PropVariantClear(pvar);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      return 0;
    }
    if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v18->lpVtbl->GetValue)(
           v18,
           &PKEY_AudioEndpoint_Association,
           pvar) >= 0
      && LOWORD(pvar[0]) == 31
      && CLSIDFromString((LPCOLESTR)pvar[1], &pclsid) >= 0 )
    {
      v12 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a4->Data1;
      if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a4->Data1 )
        v12 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a4->Data4;
      if ( !v12 || !memcmp_0(&pclsid, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        OpenPropertyStore = a3->lpVtbl->OpenPropertyStore;
        v14 = v19;
        v19 = 0;
        if ( v14 )
          ((void (__fastcall *)(struct IPropertyStore *))v14->lpVtbl->Release)(v14);
        v11 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, struct IPropertyStore **))OpenPropertyStore)(
                a3,
                1,
                &v19);
        if ( v11 < 0 )
        {
          v15 = 8813;
          goto LABEL_27;
        }
        v11 = CopyProperties(v19, v18);
        if ( v11 < 0 )
        {
          v15 = 8815;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v11,
            v17);
          PropVariantClear(pvar);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
          return (unsigned int)v11;
        }
      }
    }
    PropVariantClear(pvar);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  }
  v18 = 0;
  v10 = (*(__int64 (__fastcall **)(struct IPnpInterface *, _QWORD, _QWORD, struct IPropertyStore **))(v9 + 72))(
          a2,
          i,
          0,
          &v18);
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_10;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x224D,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v10,
    v17);
  PropVariantClear(pvar);
  if ( v18 )
    ((void (__fastcall *)(struct IPropertyStore *))v18->lpVtbl->Release)(v18);
  if ( v19 )
    ((void (__fastcall *)(struct IPropertyStore *))v19->lpVtbl->Release)(v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180028390  mov     [rsp-28h+arg_0], rbx
0x180028395  push    rbp
0x180028396  push    rsi
0x180028397  push    rdi
0x180028398  push    r14
0x18002839a  push    r15
0x18002839c  mov     rbp, rsp
0x18002839f  sub     rsp, 70h
0x1800283a3  mov     rax, cs:__security_cookie
0x1800283aa  xor     rax, rsp
0x1800283ad  mov     [rbp+var_8], rax
0x1800283b1  mov     rsi, r9
0x1800283b4  mov     r15, r8
0x1800283b7  mov     r14, rdx
0x1800283ba  xor     edi, edi
0x1800283bc  mov     [rbp+var_38], 0
0x1800283c4  xorps   xmm0, xmm0
0x1800283c7  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800283cb  xorps   xmm1, xmm1
0x1800283ce  xor     eax, eax
0x1800283d0  movups  xmmword ptr [rbp+pvar], xmm1
0x1800283d4  mov     [rbp+var_20], rax
0x1800283d8  mov     rax, [r14]
0x1800283db  cmp     [rbp+arg_20], 0
0x1800283df  jz      short loc_180028459
0x1800283e1  mov     [rbp+var_40], 0
0x1800283e9  lea     r9, [rbp+var_40]
0x1800283ed  xor     r8d, r8d
0x1800283f0  mov     edx, edi
0x1800283f2  mov     rcx, r14
0x1800283f5  mov     rax, [rax+48h]
0x1800283f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283fe  mov     ebx, eax
0x180028400  test    eax, eax
0x180028402  jns     short loc_180028480
0x180028404  mov     rcx, [rbp+28h]; this
0x180028408  mov     r9d, eax; char *
0x18002840b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180028412  mov     edx, 224Dh; void *
0x180028417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002841c  nop
0x18002841d  lea     rcx, [rbp+pvar]; pvar
0x180028421  call    cs:__imp_PropVariantClear
0x180028427  nop
0x180028428  mov     rcx, [rbp+var_40]
0x18002842c  test    rcx, rcx
0x18002842f  jz      short loc_18002843E
0x180028431  mov     rax, [rcx]
0x180028434  mov     rax, [rax+10h]
0x180028438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002843d  nop
0x18002843e  mov     rcx, [rbp+var_38]
0x180028442  test    rcx, rcx
0x180028445  jz      short loc_180028454
0x180028447  mov     rax, [rcx]
0x18002844a  mov     rax, [rax+10h]
0x18002844e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028453  nop
0x180028454  jmp     loc_1800285DB
0x180028459  mov     [rbp+var_40], 0
0x180028461  lea     r9, [rbp+var_40]
0x180028465  xor     r8d, r8d
0x180028468  mov     edx, edi
0x18002846a  mov     rcx, r14
0x18002846d  mov     rax, [rax+40h]
0x180028471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028476  mov     ebx, eax
0x180028478  test    eax, eax
0x18002847a  js      loc_1800285A4
0x180028480  mov     rcx, [rbp+var_40]
0x180028484  test    rcx, rcx
0x180028487  jz      loc_180028582
0x18002848d  mov     rax, [rcx]
0x180028490  lea     r8, [rbp+pvar]
0x180028494  lea     rdx, PKEY_AudioEndpoint_Association
0x18002849b  mov     rax, [rax+28h]
0x18002849f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284a4  test    eax, eax
0x1800284a6  js      loc_18002854F
0x1800284ac  cmp     word ptr [rbp+pvar], 1Fh
0x1800284b1  jnz     loc_18002854F
0x1800284b7  lea     rdx, [rbp+pclsid]; pclsid
0x1800284bb  mov     rcx, [rbp+pvar+8]; lpsz
0x1800284bf  call    cs:__imp_CLSIDFromString
0x1800284c5  test    eax, eax
0x1800284c7  js      loc_18002854F
0x1800284cd  mov     rax, qword ptr [rbp+pclsid.Data1]
0x1800284d1  sub     rax, [rsi]
0x1800284d4  jnz     short loc_1800284DE
0x1800284d6  mov     rax, qword ptr [rbp+pclsid.Data4]
0x1800284da  sub     rax, [rsi+8]
0x1800284de  test    rax, rax
0x1800284e1  jz      short loc_1800284FD
0x1800284e3  mov     r8d, 10h; Size
0x1800284e9  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800284f0  lea     rcx, [rbp+pclsid]; Buf1
0x1800284f4  call    memcmp_0
0x1800284f9  test    eax, eax
0x1800284fb  jnz     short loc_18002854F
0x1800284fd  mov     rax, [r15]
0x180028500  mov     rbx, [rax+20h]
0x180028504  mov     rcx, [rbp+var_38]
0x180028508  mov     [rbp+var_38], 0
0x180028510  test    rcx, rcx
0x180028513  jz      short loc_180028522
0x180028515  mov     rdx, [rcx]
0x180028518  mov     rax, [rdx+10h]
0x18002851c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028521  nop
0x180028522  lea     r8, [rbp+var_38]
0x180028526  mov     edx, 1
0x18002852b  mov     rcx, r15
0x18002852e  mov     rax, rbx
0x180028531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028536  mov     ebx, eax
0x180028538  test    eax, eax
0x18002853a  js      short loc_18002857B
0x18002853c  mov     rdx, [rbp+var_40]; struct IPropertyStore *
0x180028540  mov     rcx, [rbp+var_38]; struct IPropertyStore *
0x180028544  call    ?CopyProperties@@YAJPEAUIPropertyStore@@0@Z; CopyProperties(IPropertyStore *,IPropertyStore *)
0x180028549  mov     ebx, eax
0x18002854b  test    eax, eax
0x18002854d  js      short loc_180028574
0x18002854f  lea     rcx, [rbp+pvar]; pvar
0x180028553  call    cs:__imp_PropVariantClear
0x180028559  nop
0x18002855a  lea     rcx, [rbp+var_40]
0x18002855e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028563  nop
0x180028564  lea     rcx, [rbp+var_38]
0x180028568  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002856d  inc     edi
0x18002856f  jmp     loc_1800283BC
0x180028574  mov     edx, 226Fh
0x180028579  jmp     short loc_1800285A9
0x18002857b  mov     edx, 226Dh
0x180028580  jmp     short loc_1800285A9
0x180028582  lea     rcx, [rbp+pvar]; pvar
0x180028586  call    cs:__imp_PropVariantClear
0x18002858c  nop
0x18002858d  lea     rcx, [rbp+var_40]
0x180028591  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028596  nop
0x180028597  lea     rcx, [rbp+var_38]
0x18002859b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800285a0  xor     eax, eax
0x1800285a2  jmp     short loc_1800285DD
0x1800285a4  mov     edx, 2251h; void *
0x1800285a9  mov     r9d, ebx; char *
0x1800285ac  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800285b3  mov     rcx, [rbp+28h]; this
0x1800285b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285bc  nop
0x1800285bd  lea     rcx, [rbp+pvar]; pvar
0x1800285c1  call    cs:__imp_PropVariantClear
0x1800285c7  nop
0x1800285c8  lea     rcx, [rbp+var_40]
0x1800285cc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800285d1  nop
0x1800285d2  lea     rcx, [rbp+var_38]
0x1800285d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800285db  mov     eax, ebx
0x1800285dd  mov     rcx, [rbp+var_8]
0x1800285e1  xor     rcx, rsp; StackCookie
0x1800285e4  call    __security_check_cookie
0x1800285e9  mov     rbx, [rsp+70h+arg_0]
0x1800285f1  add     rsp, 70h
0x1800285f5  pop     r15
0x1800285f7  pop     r14
0x1800285f9  pop     rdi
0x1800285fa  pop     rsi
0x1800285fb  pop     rbp
0x1800285fc  retn
```
