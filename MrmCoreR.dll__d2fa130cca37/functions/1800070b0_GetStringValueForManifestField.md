# GetStringValueForManifestField

- ea: `0x1800070b0`
- end: `0x180007456`
- name: `GetStringValueForManifestField`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800070b0`
- `0x18000745c`
- `0x1800076e8`
- `0x180007f30`
- `0x180007f54`
- `0x180008174`
- `0x18000822c`
- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180036fb8`
- `0x180056988`
- `0x180083978`
- `0x1800862f0`
- `0x18008679c`

## import_xrefs

- `KERNELBASE!GetCurrentPackageResourcesContext` at `0x180007264`
- `KERNELBASE!GetCurrentPackageResourcesContext` at `0x180007264`
- `KERNELBASE!GetCurrentPackageApplicationResourcesContext` at `0x18000711d`
- `KERNELBASE!GetCurrentPackageApplicationResourcesContext` at `0x18000711d`
- `KERNELBASE!GetPackageResourcesProperty` at `0x18000717a`
- `KERNELBASE!GetPackageResourcesProperty` at `0x1800073fa`
- `KERNELBASE!GetPackageResourcesProperty` at `0x18000717a`
- `KERNELBASE!GetPackageResourcesProperty` at `0x1800073fa`

## string_xrefs

- `0x18000723d`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtresourcemanager.cpp`
- `0x180007279`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtresourcemanager.cpp`
- `0x18000729e`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtresourcemanager.cpp`
- `0x180007337`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtresourcemanager.cpp`
- `0x1800073c4`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtresourcemanager.cpp`

## pseudocode

```c
signed int __fastcall GetStringValueForManifestField(
        int a1,
        unsigned int a2,
        unsigned __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  signed int result; // eax
  unsigned int PackageResourcesProperty; // eax
  void *v10; // rdi
  _BYTE *v11; // rsi
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  Microsoft::Resources *v15; // rcx
  Microsoft::Resources *v16; // rcx
  int ResourceManagerForCurrentApplicationInternal; // eax
  int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // esi
  const struct std::nothrow_t *v21; // rdx
  unsigned int CurrentPackageResourcesContext; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  _QWORD *unique; // rax
  const struct std::nothrow_t *v27; // rdx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v28; // rcx
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  Microsoft::Resources::Runtime::CResourceManagerInternal *v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v34; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v35[24]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  _BYTE v39[272]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *a5 = 0;
  if ( a4 && a3 )
    *a4 = 0;
  v33 = 0;
  if ( a1 == 1 )
  {
    CurrentPackageResourcesContext = GetCurrentPackageResourcesContext(0, 0, &v33);
    if ( CurrentPackageResourcesContext )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x21E,
               (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtresourcemanager.cpp",
               (const char *)CurrentPackageResourcesContext,
               v29);
LABEL_4:
    v36 = 0;
    v38 = 0;
    v37 = 0;
    DefStringResult_InitBuf(v35);
    LODWORD(v31) = 260;
    v34 = v35;
    PackageResourcesProperty = GetPackageResourcesProperty(v33, a2, &v31, v39);
    if ( PackageResourcesProperty == 122 )
    {
      unique = (_QWORD *)wil::make_unique_nothrow<unsigned char [0]>(&v32, (unsigned int)v31);
      v11 = (_BYTE *)*unique;
      *unique = 0;
      v28 = v32;
      v32 = 0;
      if ( v28 )
        operator delete(v28, v27);
      if ( !v11 )
      {
        v13 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtresourcemanager.cpp",
          (const char *)0x8007000ELL,
          0);
LABEL_23:
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v34);
        return v13;
      }
      PackageResourcesProperty = GetPackageResourcesProperty(v33, a2, &v31, v11);
      v10 = v11;
    }
    else
    {
      v10 = 0;
      v11 = v39;
    }
    if ( PackageResourcesProperty )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x23A,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtresourcemanager.cpp",
              (const char *)PackageResourcesProperty,
              0);
LABEL_21:
      if ( v10 )
        operator delete(v10, v19);
      goto LABEL_23;
    }
    v12 = Microsoft::Resources::ResourceReference::Set(
            (Microsoft::Resources::ResourceReference *)&v36,
            (unsigned int)v31,
            v11);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( v12 == -2147467259 || v12 == -2147024809 )
        v13 = -2147024883;
      v24 = 579;
      goto LABEL_37;
    }
    v14 = Microsoft::Resources::ResourceReference::ResolveAsString(
            (Microsoft::Resources::ResourceReference *)&v36,
            0,
            0,
            (struct Microsoft::Resources::StringResult *)&v34);
    v13 = v14;
    if ( v14 >= 0 )
    {
      v25 = Microsoft::Resources::StringResult::CopyToOutParams((Microsoft::Resources::StringResult *)&v34, a3, a4, a5);
      v13 = v25;
      if ( v25 < 0 )
      {
        v23 = (unsigned int)v25;
        v24 = 586;
        goto LABEL_20;
      }
    }
    else
    {
      if ( v14 != -554692512 )
      {
        if ( v14 == -2147467259 || v14 == -2147024809 )
          v13 = -2147009769;
        v24 = 597;
        goto LABEL_37;
      }
      v32 = 0;
      if ( !Microsoft::Resources::IsPackagedAndAppContainer(v15) && !Microsoft::Resources::IsPackaged(v16) )
      {
        v13 = -2147009760;
        v24 = 615;
LABEL_37:
        v23 = v13;
        goto LABEL_20;
      }
      ResourceManagerForCurrentApplicationInternal = GetResourceManagerForCurrentApplicationInternal(&v32);
      v13 = ResourceManagerForCurrentApplicationInternal;
      if ( ResourceManagerForCurrentApplicationInternal < 0 )
      {
        v23 = (unsigned int)ResourceManagerForCurrentApplicationInternal;
        v24 = 608;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtresourcemanager.cpp",
          (const char *)v23,
          0);
        goto LABEL_21;
      }
      v18 = Microsoft::Resources::Runtime::CResourceManagerInternal::ResolveReferenceBlobAsString(
              v32,
              (unsigned int)v31,
              v11,
              a3,
              a4,
              a5);
      v20 = v18;
      if ( v18 < 0 )
      {
        v13 = -2147024774;
        if ( v18 != -2147024774 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x263,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtresourcemanager.cpp",
            (const char *)(unsigned int)v18,
            v30);
          if ( v10 )
            operator delete(v10, v21);
          v13 = v20;
          goto LABEL_23;
        }
        goto LABEL_21;
      }
    }
    if ( v10 )
      operator delete(v10, v19);
    v13 = 0;
    goto LABEL_23;
  }
  result = GetCurrentPackageApplicationResourcesContext(0, 0, &v33);
  if ( !result )
    goto LABEL_4;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800070b0  mov     [rsp-8+arg_0], rbx
0x1800070b5  mov     [rsp-8+arg_10], rsi
0x1800070ba  push    rbp
0x1800070bb  push    rdi
0x1800070bc  push    r12
0x1800070be  push    r14
0x1800070c0  push    r15
0x1800070c2  lea     rbp, [rsp-0B0h]
0x1800070ca  sub     rsp, 1B0h
0x1800070d1  mov     rax, cs:__security_cookie
0x1800070d8  xor     rax, rsp
0x1800070db  mov     [rbp+0D0h+var_30], rax
0x1800070e2  mov     r12, [rbp+0D0h+arg_20]
0x1800070e9  mov     r14, r9
0x1800070ec  mov     r15, r8
0x1800070ef  mov     ebx, edx
0x1800070f1  mov     qword ptr [r12], 0
0x1800070f9  test    r9, r9
0x1800070fc  jnz     loc_1800072EE
0x180007102  xor     edx, edx
0x180007104  mov     [rsp+1D0h+var_190], 0
0x18000710d  lea     r8, [rsp+1D0h+var_190]
0x180007112  cmp     ecx, 1
0x180007115  jz      loc_180007262
0x18000711b  xor     ecx, ecx
0x18000711d  call    cs:__imp_GetCurrentPackageApplicationResourcesContext
0x180007123  test    eax, eax
0x180007125  jnz     loc_180007352
0x18000712b  xorps   xmm0, xmm0
0x18000712e  mov     [rsp+1D0h+var_168], 0
0x180007137  lea     rcx, [rsp+1D0h+var_180]
0x18000713c  mov     [rbp+0D0h+var_150], 0
0x180007144  movdqu  [rsp+1D0h+var_160], xmm0
0x18000714a  call    DefStringResult_InitBuf
0x18000714f  lea     rcx, [rsp+1D0h+var_180]
0x180007154  mov     dword ptr [rsp+1D0h+var_1A0], 104h
0x18000715c  mov     [rsp+1D0h+var_188], rcx
0x180007161  lea     r9, [rbp+0D0h+var_140]
0x180007165  mov     rcx, [rsp+1D0h+var_190]
0x18000716a  lea     r8, [rsp+1D0h+var_1A0]
0x18000716f  mov     edx, ebx
0x180007171  mov     [rsp+1D0h+var_1B0], 0; int
0x18000717a  call    cs:__imp_GetPackageResourcesProperty
0x180007180  cmp     eax, 7Ah ; 'z'
0x180007183  jz      loc_180007388
0x180007189  xor     edi, edi
0x18000718b  lea     rsi, [rbp+0D0h+var_140]
0x18000718f  test    eax, eax
0x180007191  jnz     loc_180007330
0x180007197  mov     edx, dword ptr [rsp+1D0h+var_1A0]; unsigned __int64
0x18000719b  lea     rcx, [rsp+1D0h+var_168]; this
0x1800071a0  mov     r8, rsi; void *
0x1800071a3  call    ?Set@ResourceReference@Resources@Microsoft@@QEAAJ_KPEBX@Z; Microsoft::Resources::ResourceReference::Set(unsigned __int64,void const *)
0x1800071a8  mov     ebx, eax
0x1800071aa  test    eax, eax
0x1800071ac  js      loc_180007365
0x1800071b2  lea     r9, [rsp+1D0h+var_188]; struct Microsoft::Resources::StringResult *
0x1800071b7  xor     r8d, r8d; struct Microsoft::Resources::IResolver *
0x1800071ba  xor     edx, edx; struct Microsoft::Resources::IUnifiedResourceView *
0x1800071bc  lea     rcx, [rsp+1D0h+var_168]; this
0x1800071c1  call    ?ResolveAsString@ResourceReference@Resources@Microsoft@@QEBAJPEAVIUnifiedResourceView@23@PEAVIResolver@23@PEAVStringResult@23@@Z; Microsoft::Resources::ResourceReference::ResolveAsString(Microsoft::Resources::IUnifiedResourceView *,Microsoft::Resources::IResolver *,Microsoft::Resources::StringResult *)
0x1800071c6  mov     ebx, eax
0x1800071c8  test    eax, eax
0x1800071ca  jns     loc_180007302
0x1800071d0  cmp     eax, 0DEF01060h
0x1800071d5  jnz     loc_18000741F
0x1800071db  mov     [rsp+1D0h+var_198], 0
0x1800071e4  call    ?IsPackagedAndAppContainer@Resources@Microsoft@@YA_NXZ; Microsoft::Resources::IsPackagedAndAppContainer(void)
0x1800071e9  test    al, al
0x1800071eb  jz      loc_18000743A
0x1800071f1  lea     rcx, [rsp+1D0h+var_198]
0x1800071f6  call    _GetResourceManagerForCurrentApplicationInternal
0x1800071fb  mov     ebx, eax
0x1800071fd  test    eax, eax
0x1800071ff  js      loc_18000728F
0x180007205  mov     edx, dword ptr [rsp+1D0h+var_1A0]; unsigned __int64
0x180007209  mov     r9, r15; unsigned __int64
0x18000720c  mov     rcx, [rsp+1D0h+var_198]; this
0x180007211  mov     r8, rsi; void *
0x180007214  mov     [rsp+1D0h+var_1A8], r12; unsigned __int64 *
0x180007219  mov     [rsp+1D0h+var_1B0], r14; int
0x18000721e  call    ?ResolveReferenceBlobAsString@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEBAJ_KPEBX0PEAGPEA_K@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::ResolveReferenceBlobAsString(unsigned __int64,void const *,unsigned __int64,ushort *,unsigned __int64 *)
0x180007223  mov     esi, eax
0x180007225  test    eax, eax
0x180007227  jns     loc_18000731F
0x18000722d  mov     ebx, 8007007Ah
0x180007232  cmp     eax, ebx
0x180007234  jz      short loc_1800072AA
0x180007236  mov     rcx, [rbp+0D8h]; this
0x18000723d  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x180007244  mov     r9d, eax; char *
0x180007247  mov     edx, 263h; void *
0x18000724c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007251  test    rdi, rdi
0x180007254  jz      short loc_18000725E
0x180007256  mov     rcx, rdi; void *
0x180007259  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000725e  mov     ebx, esi
0x180007260  jmp     short loc_1800072B7
0x180007262  xor     ecx, ecx
0x180007264  call    cs:__imp_GetCurrentPackageResourcesContext
0x18000726a  test    eax, eax
0x18000726c  jz      loc_18000712B
0x180007272  mov     rcx, [rbp+0D8h]; this
0x180007279  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x180007280  mov     r9d, eax; char *
0x180007283  mov     edx, 21Eh; void *
0x180007288  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000728d  jmp     short loc_1800072C3
0x18000728f  mov     r9d, eax; char *
0x180007292  mov     edx, 260h; void *
0x180007297  mov     rcx, [rbp+0D8h]; this
0x18000729e  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800072a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072aa  test    rdi, rdi
0x1800072ad  jz      short loc_1800072B7
0x1800072af  mov     rcx, rdi; void *
0x1800072b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800072b7  lea     rcx, [rsp+1D0h+var_188]; this
0x1800072bc  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800072c1  mov     eax, ebx
0x1800072c3  mov     rcx, [rbp+0D0h+var_30]
0x1800072ca  xor     rcx, rsp; StackCookie
0x1800072cd  call    __security_check_cookie
0x1800072d2  lea     r11, [rsp+1D0h+var_20]
0x1800072da  mov     rbx, [r11+30h]
0x1800072de  mov     rsi, [r11+40h]
0x1800072e2  mov     rsp, r11
0x1800072e5  pop     r15
0x1800072e7  pop     r14
0x1800072e9  pop     r12
0x1800072eb  pop     rdi
0x1800072ec  pop     rbp
0x1800072ed  retn
0x1800072ee  test    r15, r15
0x1800072f1  jz      loc_180007102
0x1800072f7  xor     eax, eax
0x1800072f9  mov     [r9], ax
0x1800072fd  jmp     loc_180007102
0x180007302  mov     r9, r12; unsigned __int64 *
0x180007305  lea     rcx, [rsp+1D0h+var_188]; this
0x18000730a  mov     r8, r14; unsigned __int16 *
0x18000730d  mov     rdx, r15; unsigned __int64
0x180007310  call    ?CopyToOutParams@StringResult@Resources@Microsoft@@QEBAJ_KPEAGPEA_K@Z; Microsoft::Resources::StringResult::CopyToOutParams(unsigned __int64,ushort *,unsigned __int64 *)
0x180007315  mov     ebx, eax
0x180007317  test    eax, eax
0x180007319  js      loc_180007412
0x18000731f  test    rdi, rdi
0x180007322  jz      short loc_18000732C
0x180007324  mov     rcx, rdi; void *
0x180007327  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000732c  xor     ebx, ebx
0x18000732e  jmp     short loc_1800072B7
0x180007330  mov     rcx, [rbp+0D8h]; this
0x180007337  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18000733e  mov     r9d, eax; char *
0x180007341  mov     edx, 23Ah; void *
0x180007346  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000734b  mov     ebx, eax
0x18000734d  jmp     loc_1800072AA
0x180007352  jle     loc_1800072C3
0x180007358  movzx   eax, ax
0x18000735b  or      eax, 80070000h
0x180007360  jmp     loc_1800072C3
0x180007365  cmp     eax, 80004005h
0x18000736a  jz      loc_180007408
0x180007370  cmp     eax, 80070057h
0x180007375  jz      loc_180007408
0x18000737b  mov     edx, 243h
0x180007380  mov     r9d, ebx
0x180007383  jmp     loc_180007297
0x180007388  mov     edx, dword ptr [rsp+1D0h+var_1A0]
0x18000738c  lea     rcx, [rsp+1D0h+var_198]
0x180007391  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180007396  mov     rsi, [rax]
0x180007399  mov     qword ptr [rax], 0
0x1800073a0  mov     rcx, [rsp+1D0h+var_198]; void *
0x1800073a5  mov     [rsp+1D0h+var_198], 0
0x1800073ae  test    rcx, rcx
0x1800073b1  jz      short loc_1800073B8
0x1800073b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800073b8  test    rsi, rsi
0x1800073bb  jnz     short loc_1800073E2
0x1800073bd  mov     rcx, [rbp+0D8h]; this
0x1800073c4  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800073cb  mov     ebx, 8007000Eh
0x1800073d0  mov     edx, 232h; void *
0x1800073d5  mov     r9d, ebx; char *
0x1800073d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073dd  jmp     loc_1800072B7
0x1800073e2  mov     rcx, [rsp+1D0h+var_190]
0x1800073e7  lea     r8, [rsp+1D0h+var_1A0]
0x1800073ec  mov     r9, rsi
0x1800073ef  mov     [rsp+1D0h+var_1B0], 0
0x1800073f8  mov     edx, ebx
0x1800073fa  call    cs:__imp_GetPackageResourcesProperty
0x180007400  mov     rdi, rsi
0x180007403  jmp     loc_18000718F
0x180007408  mov     ebx, 8007000Dh
0x18000740d  jmp     loc_18000737B
0x180007412  mov     r9d, eax
0x180007415  mov     edx, 24Ah
0x18000741a  jmp     loc_180007297
0x18000741f  cmp     eax, 80004005h
0x180007424  jz      loc_1800BFE2E
0x18000742a  cmp     eax, 80070057h
0x18000742f  jz      loc_1800BFE2E
0x180007435  jmp     loc_1800BFE33
0x18000743a  call    ?IsPackaged@Resources@Microsoft@@YA_NXZ; Microsoft::Resources::IsPackaged(void)
0x18000743f  test    al, al
0x180007441  jnz     loc_1800071F1
0x180007447  mov     ebx, 80073B20h
0x18000744c  mov     edx, 267h
0x180007451  jmp     loc_180007380
0x1800bfe2e  mov     ebx, 80073B17h
0x1800bfe33  mov     edx, 255h
0x1800bfe38  jmp     loc_180007380
```
