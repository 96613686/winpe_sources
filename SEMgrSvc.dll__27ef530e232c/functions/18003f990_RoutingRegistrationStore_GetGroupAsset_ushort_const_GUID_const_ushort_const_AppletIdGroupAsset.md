# RoutingRegistrationStore::GetGroupAsset(ushort const *,_GUID const &,ushort const *,_AppletIdGroupAsset *)

- ea: `0x18003f990`
- end: `0x18003fbd5`
- name: `?GetGroupAsset@RoutingRegistrationStore@@QEAAJPEBGAEBU_GUID@@0PEAU_AppletIdGroupAsset@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(RoutingRegistrationStore *this, unsigned __int16 *, struct _GUID *, unsigned __int16 *, struct _AppletIdGroupAsset *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010d40`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x180013274`
- `0x180038e30`
- `0x180039954`
- `0x18003c35c`
- `0x18003f990`
- `0x18007a1a0`
- `0x18007a4b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fbaa`

## string_xrefs

- `0x18003fa0e`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x18003faaf`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistryhelper.cpp`
- `0x18003fb1a`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistrationstore.cpp`

## pseudocode

```c
__int64 __fastcall RoutingRegistrationStore::GetGroupAsset(
        RoutingRegistrationStore *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        struct _AppletIdGroupAsset *a5)
{
  int v6; // esi
  void *v7; // rdi
  int AppletIdGroupAssetDataPath; // eax
  int v9; // ebx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  LPVOID v15; // rax
  __int128 v16; // xmm1
  void *v17; // rcx
  LPVOID v18; // [rsp+20h] [rbp-61h] BYREF
  int v19; // [rsp+28h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-51h] BYREF
  __int128 v21; // [rsp+38h] [rbp-49h] BYREF
  __int64 v22; // [rsp+48h] [rbp-39h]
  LPVOID *p_pv; // [rsp+50h] [rbp-31h]
  void *v24; // [rsp+58h] [rbp-29h] BYREF
  char v25; // [rsp+60h] [rbp-21h]
  LPVOID *v26; // [rsp+68h] [rbp-19h]
  __int64 v27; // [rsp+70h] [rbp-11h]
  char v28; // [rsp+78h] [rbp-9h]
  _OWORD Src[2]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v6 = 0;
  v18 = 0;
  v26 = &v18;
  v7 = 0;
  v27 = 0;
  v28 = 1;
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  AppletIdGroupAssetDataPath = RoutingRegistryHelper::GetAppletIdGroupAssetDataPath(a2, a3);
  v9 = AppletIdGroupAssetDataPath;
  if ( AppletIdGroupAssetDataPath >= 0 )
  {
    std::wstring::append(Src, (void *)L"\\");
    std::wstring::append(Src, a4);
    v19 = 0;
    pv = 0;
    p_pv = &pv;
    v24 = 0;
    v25 = 1;
    v9 = RoutingRegistryHelper::ReadAppletIdGroupAssetData(Src, &v19, &v24);
    if ( v25 )
    {
      v10 = *p_pv;
      *p_pv = v24;
      if ( v10 )
        CoTaskMemFree(v10);
    }
    if ( v9 >= 0 )
    {
      v6 = v19;
      v7 = pv;
      pv = 0;
      v9 = 0;
    }
    else
    {
      if ( v9 == -2147024894 )
        v9 = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x487,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
        (const char *)(unsigned int)v9,
        (int)v18);
      v11 = pv;
      pv = 0;
      if ( v11 )
        CoTaskMemFree(v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47C,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistryhelper.cpp",
      (const char *)(unsigned int)AppletIdGroupAssetDataPath,
      (int)v18);
  }
  std::wstring::~wstring(Src);
  v12 = v18;
  v18 = v7;
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v9 >= 0 )
  {
    v21 = 0;
    v22 = 0;
    *(_QWORD *)&v21 = MakeHSTRING(a4);
    DWORD2(v21) = v6;
    v15 = v18;
    v18 = 0;
    v16 = v21;
    v21 = 0;
    v22 = 0;
    *(_OWORD *)a5 = v16;
    *((_QWORD *)a5 + 2) = v15;
    FreeAppletIdGroupAsset((struct _AppletIdGroupAsset *)&v21);
    v17 = v18;
    v18 = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38A,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistrationstore.cpp",
      (const char *)(unsigned int)v9,
      (int)v18);
    v13 = v18;
    v18 = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x18003f990  mov     [rsp-8+arg_0], rbx
0x18003f995  push    rbp
0x18003f996  push    rsi
0x18003f997  push    rdi
0x18003f998  push    r14
0x18003f99a  push    r15
0x18003f99c  lea     rbp, [rsp-2Fh]
0x18003f9a1  sub     rsp, 0B0h
0x18003f9a8  mov     rax, cs:__security_cookie
0x18003f9af  xor     rax, rsp
0x18003f9b2  mov     [rbp+4Fh+var_30], rax
0x18003f9b6  mov     r14, r9
0x18003f9b9  mov     r10, r8
0x18003f9bc  mov     rcx, rdx; void *
0x18003f9bf  mov     r15, [rbp+4Fh+arg_20]
0x18003f9c3  xor     esi, esi
0x18003f9c5  mov     [rbp+4Fh+var_B0], rsi
0x18003f9c9  lea     rax, [rbp+4Fh+var_B0]
0x18003f9cd  mov     [rbp+4Fh+var_68], rax
0x18003f9d1  xor     edi, edi
0x18003f9d3  mov     [rbp+4Fh+var_60], rdi
0x18003f9d7  mov     [rbp+4Fh+var_58], 1
0x18003f9db  xorps   xmm0, xmm0
0x18003f9de  movups  [rbp+4Fh+Src], xmm0
0x18003f9e2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003f9ea  movdqu  [rbp+4Fh+var_40], xmm1
0x18003f9ef  xor     eax, eax
0x18003f9f1  mov     word ptr [rbp+4Fh+Src], ax
0x18003f9f5  lea     r8, [rbp+4Fh+Src]
0x18003f9f9  mov     rdx, r10; rguid
0x18003f9fc  call    ?GetAppletIdGroupAssetDataPath@RoutingRegistryHelper@@CAJPEBGAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RoutingRegistryHelper::GetAppletIdGroupAssetDataPath(ushort const *,_GUID const &,std::wstring *)
0x18003fa01  mov     ebx, eax
0x18003fa03  test    eax, eax
0x18003fa05  jns     short loc_18003FA25
0x18003fa07  mov     rcx, [rbp+57h]; this
0x18003fa0b  mov     r9d, eax; char *
0x18003fa0e  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003fa15  mov     edx, 47Ch; void *
0x18003fa1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa1f  nop
0x18003fa20  jmp     loc_18003FAF2
0x18003fa25  lea     rdx, StringValue; "\\"
0x18003fa2c  lea     rcx, [rbp+4Fh+Src]; Src
0x18003fa30  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003fa35  mov     rdx, r14; void *
0x18003fa38  lea     rcx, [rbp+4Fh+Src]; Src
0x18003fa3c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003fa41  mov     [rbp+4Fh+var_A8], 0
0x18003fa48  mov     [rbp+4Fh+pv], 0
0x18003fa50  lea     rax, [rbp+4Fh+pv]
0x18003fa54  mov     [rbp+4Fh+var_80], rax
0x18003fa58  mov     [rbp+4Fh+var_78], 0
0x18003fa60  mov     [rbp+4Fh+var_70], 1
0x18003fa64  lea     r8, [rbp+4Fh+var_78]
0x18003fa68  lea     rdx, [rbp+4Fh+var_A8]
0x18003fa6c  lea     rcx, [rbp+4Fh+Src]
0x18003fa70  call    ?ReadAppletIdGroupAssetData@RoutingRegistryHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAIPEAPEAE@Z; RoutingRegistryHelper::ReadAppletIdGroupAssetData(std::wstring const &,uint *,uchar * *)
0x18003fa75  mov     ebx, eax
0x18003fa77  cmp     [rbp+4Fh+var_70], 0
0x18003fa7b  jz      short loc_18003FA96
0x18003fa7d  mov     rdx, [rbp+4Fh+var_80]
0x18003fa81  mov     rcx, [rdx]; pv
0x18003fa84  mov     rax, [rbp+4Fh+var_78]
0x18003fa88  mov     [rdx], rax
0x18003fa8b  test    rcx, rcx
0x18003fa8e  jz      short loc_18003FA96
0x18003fa90  call    cs:__imp_CoTaskMemFree
0x18003fa96  test    ebx, ebx
0x18003fa98  jns     short loc_18003FAE1
0x18003fa9a  mov     eax, 80070490h
0x18003fa9f  cmp     ebx, 80070002h
0x18003faa5  cmovz   ebx, eax
0x18003faa8  mov     rcx, [rbp+57h]; this
0x18003faac  mov     r9d, ebx; char *
0x18003faaf  lea     r8, aOnecoreuapDsNf_45; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003fab6  mov     edx, 487h; void *
0x18003fabb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fac0  nop
0x18003fac1  mov     rcx, [rbp+4Fh+pv]; pv
0x18003fac5  mov     [rbp+4Fh+pv], 0
0x18003facd  test    rcx, rcx
0x18003fad0  jz      loc_18003FA20
0x18003fad6  call    cs:__imp_CoTaskMemFree
0x18003fadc  jmp     loc_18003FA20
0x18003fae1  mov     esi, [rbp+4Fh+var_A8]
0x18003fae4  mov     rdi, [rbp+4Fh+pv]
0x18003fae8  mov     [rbp+4Fh+pv], 0
0x18003faf0  xor     ebx, ebx
0x18003faf2  lea     rcx, [rbp+4Fh+Src]
0x18003faf6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003fafb  nop
0x18003fafc  mov     rcx, [rbp+4Fh+var_B0]; pv
0x18003fb00  mov     [rbp+4Fh+var_B0], rdi
0x18003fb04  test    rcx, rcx
0x18003fb07  jz      short loc_18003FB0F
0x18003fb09  call    cs:__imp_CoTaskMemFree
0x18003fb0f  test    ebx, ebx
0x18003fb11  jns     short loc_18003FB47
0x18003fb13  mov     rcx, [rbp+57h]; this
0x18003fb17  mov     r9d, ebx; char *
0x18003fb1a  lea     r8, aOnecoreuapDsNf_23; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003fb21  mov     edx, 38Ah; void *
0x18003fb26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb2b  nop
0x18003fb2c  mov     rcx, [rbp+4Fh+var_B0]; pv
0x18003fb30  mov     [rbp+4Fh+var_B0], 0
0x18003fb38  test    rcx, rcx
0x18003fb3b  jz      short loc_18003FB43
0x18003fb3d  call    cs:__imp_CoTaskMemFree
0x18003fb43  mov     eax, ebx
0x18003fb45  jmp     short loc_18003FBB2
0x18003fb47  xorps   xmm0, xmm0
0x18003fb4a  xor     eax, eax
0x18003fb4c  movups  [rbp+4Fh+var_98], xmm0
0x18003fb50  mov     [rbp+4Fh+var_88], rax
0x18003fb54  mov     rcx, r14; sourceString
0x18003fb57  call    ?MakeHSTRING@@YAPEAUHSTRING__@@PEBG@Z; MakeHSTRING(ushort const *)
0x18003fb5c  mov     qword ptr [rbp+4Fh+var_98], rax
0x18003fb60  mov     dword ptr [rbp+4Fh+var_98+8], esi
0x18003fb63  mov     rax, [rbp+4Fh+var_B0]
0x18003fb67  mov     [rbp+4Fh+var_B0], 0
0x18003fb6f  movups  xmm1, [rbp+4Fh+var_98]
0x18003fb73  movq    xmm2, rax
0x18003fb78  xorps   xmm0, xmm0
0x18003fb7b  xor     eax, eax
0x18003fb7d  movups  [rbp+4Fh+var_98], xmm0
0x18003fb81  mov     [rbp+4Fh+var_88], rax
0x18003fb85  movups  xmmword ptr [r15], xmm1
0x18003fb89  movsd   qword ptr [r15+10h], xmm2
0x18003fb8f  lea     rcx, [rbp+4Fh+var_98]; struct _AppletIdGroupAsset *
0x18003fb93  call    ?FreeAppletIdGroupAsset@@YAXPEAU_AppletIdGroupAsset@@@Z; FreeAppletIdGroupAsset(_AppletIdGroupAsset *)
0x18003fb98  nop
0x18003fb99  mov     rcx, [rbp+4Fh+var_B0]; pv
0x18003fb9d  mov     [rbp+4Fh+var_B0], 0
0x18003fba5  test    rcx, rcx
0x18003fba8  jz      short loc_18003FBB0
0x18003fbaa  call    cs:__imp_CoTaskMemFree
0x18003fbb0  xor     eax, eax
0x18003fbb2  mov     rcx, [rbp+4Fh+var_30]
0x18003fbb6  xor     rcx, rsp; StackCookie
0x18003fbb9  call    __security_check_cookie
0x18003fbbe  mov     rbx, [rsp+0D0h+arg_0]
0x18003fbc6  add     rsp, 0B0h
0x18003fbcd  pop     r15
0x18003fbcf  pop     r14
0x18003fbd1  pop     rdi
0x18003fbd2  pop     rsi
0x18003fbd3  pop     rbp
0x18003fbd4  retn
```
