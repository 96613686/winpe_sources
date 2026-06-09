# LookUpApoProperties(IPropertyStore *,IPropertyStore *,_GUID const &,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,APO_REG_PROPERTIES *,ushort * *)

- ea: `0x1400476e8`
- end: `0x14004788d`
- name: `?LookUpApoProperties@@YAJPEAUIPropertyStore@@0AEBU_GUID@@W4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@PEAUAPO_REG_PROPERTIES@@PEAPEAG@Z`
- size: `421`
- prototype: `int __high(struct IPropertyStore *, struct IPropertyStore *, const struct _GUID *, enum __MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003, struct APO_REG_PROPERTIES *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140047448`

## callees

- `0x14000c33c`
- `0x140016f68`
- `0x140018d0c`
- `0x14001d790`
- `0x1400476e8`
- `0x140047894`
- `0x14004de70`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14004786a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14004786a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004785e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004785e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LookUpApoProperties(
        struct IPropertyStore *a1,
        __int64 a2,
        const struct _GUID *a3,
        int a4,
        struct APO_REG_PROPERTIES *a5,
        DEVINSTID_W *a6)
{
  int ApoPropertiesFromDeviceId; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  DEVINSTID_W v12; // rbx
  int APOPropertiesInternal; // eax
  int v14; // edi
  DEVINSTID_W pDeviceID; // [rsp+20h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h]
  struct _GUID v19; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  *a6 = 0;
  v19 = (struct _GUID)0LL;
  v19 = *a3;
  v20 = 100;
  *(_OWORD *)pvar = 0;
  v18 = 0;
  if ( !a2
    || (ApoPropertiesFromDeviceId = (*(__int64 (__fastcall **)(__int64, struct _GUID *, PROPVARIANT *))(*(_QWORD *)a2 + 40LL))(
                                      a2,
                                      &v19,
                                      pvar),
        v10 = ApoPropertiesFromDeviceId,
        ApoPropertiesFromDeviceId >= 0) )
  {
    if ( LOWORD(pvar[0]) == 31 )
    {
      ApoPropertiesFromDeviceId = GetApoPropertiesFromDeviceId((DEVINSTID_W)pvar[1], a3, a5);
      v10 = ApoPropertiesFromDeviceId;
      if ( ApoPropertiesFromDeviceId < 0 )
      {
        v11 = 591;
        goto LABEL_7;
      }
      *a6 = (DEVINSTID_W)pvar[1];
      pvar[1] = 0;
    }
    else
    {
      v12 = 0;
      pDeviceID = 0;
      if ( a4
        && (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              (void **)&pDeviceID,
              0),
            GetDeviceInstanceId(a1, &pDeviceID),
            (v12 = pDeviceID) != 0)
        && (int)GetApoPropertiesFromDeviceId(pDeviceID, a3, a5) >= 0 )
      {
        pDeviceID = 0;
        *a6 = v12;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pDeviceID);
      }
      else
      {
        APOPropertiesInternal = GetAPOPropertiesInternal(HKEY_CLASSES_ROOT, a3, a5);
        v14 = APOPropertiesInternal;
        if ( APOPropertiesInternal < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x268,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\processnode.cpp",
            (const char *)(unsigned int)APOPropertiesInternal,
            (int)pDeviceID);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pDeviceID);
          v10 = v14;
          goto LABEL_18;
        }
        if ( v12 )
          CoTaskMemFree(v12);
      }
    }
    v10 = 0;
    goto LABEL_18;
  }
  v11 = 585;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\processnode.cpp",
    (const char *)(unsigned int)ApoPropertiesFromDeviceId,
    (int)pDeviceID);
LABEL_18:
  PropVariantClear(pvar);
  return v10;
}

```

## disassembly

```asm
0x1400476e8  push    rbp
0x1400476ea  push    rbx
0x1400476eb  push    rsi
0x1400476ec  push    rdi
0x1400476ed  push    r12
0x1400476ef  push    r14
0x1400476f1  push    r15
0x1400476f3  mov     rbp, rsp
0x1400476f6  sub     rsp, 60h
0x1400476fa  mov     rax, cs:__security_cookie
0x140047701  xor     rax, rsp
0x140047704  mov     [rbp+var_8], rax
0x140047708  mov     r15d, r9d
0x14004770b  mov     rdi, r8
0x14004770e  mov     r10, rdx
0x140047711  mov     r12, rcx
0x140047714  mov     rsi, [rbp+arg_20]
0x140047718  mov     r14, [rbp+arg_28]
0x14004771c  mov     qword ptr [r14], 0
0x140047723  mov     qword ptr [rbp+var_20], 0
0x14004772b  mov     qword ptr [rbp+var_20+8], 0
0x140047733  movups  xmm0, xmmword ptr [r8]
0x140047737  movups  [rbp+var_20], xmm0
0x14004773b  mov     [rbp+var_10], 64h ; 'd'
0x140047742  xorps   xmm0, xmm0
0x140047745  xor     eax, eax
0x140047747  movups  xmmword ptr [rbp+pvar], xmm0
0x14004774b  mov     [rbp+var_28], rax
0x14004774f  test    rdx, rdx
0x140047752  jz      short loc_140047778
0x140047754  mov     rax, [rdx]
0x140047757  lea     r8, [rbp+pvar]
0x14004775b  lea     rdx, [rbp+var_20]
0x14004775f  mov     rcx, r10
0x140047762  mov     rax, [rax+28h]
0x140047766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004776b  mov     ebx, eax
0x14004776d  test    eax, eax
0x14004776f  jns     short loc_140047778
0x140047771  mov     edx, 249h
0x140047776  jmp     short loc_140047799
0x140047778  cmp     word ptr [rbp+pvar], 1Fh
0x14004777d  jnz     short loc_1400477C5
0x14004777f  mov     r8, rsi; struct APO_REG_PROPERTIES *
0x140047782  mov     rdx, rdi; struct _GUID *
0x140047785  mov     rcx, [rbp+pvar+8]; pDeviceID
0x140047789  call    ?GetApoPropertiesFromDeviceId@@YAJQEAGAEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z; GetApoPropertiesFromDeviceId(ushort * const,_GUID const &,APO_REG_PROPERTIES *)
0x14004778e  mov     ebx, eax
0x140047790  test    eax, eax
0x140047792  jns     short loc_1400477B1
0x140047794  mov     edx, 24Fh; void *
0x140047799  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400477a0  mov     r9d, eax; char *
0x1400477a3  mov     rcx, [rbp+38h]; this
0x1400477a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400477ac  jmp     loc_140047866
0x1400477b1  mov     rax, [rbp+pvar+8]
0x1400477b5  mov     [r14], rax
0x1400477b8  mov     [rbp+pvar+8], 0
0x1400477c0  jmp     loc_140047864
0x1400477c5  xor     ebx, ebx
0x1400477c7  mov     [rbp+pDeviceID], rbx
0x1400477cb  test    r15d, r15d
0x1400477ce  jz      short loc_140047818
0x1400477d0  xor     edx, edx
0x1400477d2  lea     rcx, [rbp+pDeviceID]
0x1400477d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400477db  lea     rdx, [rbp+pDeviceID]; unsigned __int16 **
0x1400477df  mov     rcx, r12; struct IPropertyStore *
0x1400477e2  call    ?GetDeviceInstanceId@@YAJPEAUIPropertyStore@@PEAPEAG@Z; GetDeviceInstanceId(IPropertyStore *,ushort * *)
0x1400477e7  mov     rbx, [rbp+pDeviceID]
0x1400477eb  test    rbx, rbx
0x1400477ee  jz      short loc_140047818
0x1400477f0  mov     r8, rsi; struct APO_REG_PROPERTIES *
0x1400477f3  mov     rdx, rdi; struct _GUID *
0x1400477f6  mov     rcx, rbx; pDeviceID
0x1400477f9  call    ?GetApoPropertiesFromDeviceId@@YAJQEAGAEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z; GetApoPropertiesFromDeviceId(ushort * const,_GUID const &,APO_REG_PROPERTIES *)
0x1400477fe  test    eax, eax
0x140047800  js      short loc_140047818
0x140047802  mov     [rbp+pDeviceID], 0
0x14004780a  mov     [r14], rbx
0x14004780d  lea     rcx, [rbp+pDeviceID]
0x140047811  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140047816  jmp     short loc_140047864
0x140047818  mov     r8, rsi; struct APO_REG_PROPERTIES *
0x14004781b  mov     rdx, rdi; struct _GUID *
0x14004781e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140047825  call    ?GetAPOPropertiesInternal@@YAJPEAUHKEY__@@AEBU_GUID@@PEAUAPO_REG_PROPERTIES@@@Z; GetAPOPropertiesInternal(HKEY__ *,_GUID const &,APO_REG_PROPERTIES *)
0x14004782a  mov     edi, eax
0x14004782c  test    eax, eax
0x14004782e  jns     short loc_140047856
0x140047830  mov     rcx, [rbp+38h]; this
0x140047834  mov     r9d, eax; char *
0x140047837  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004783e  mov     edx, 268h; void *
0x140047843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047848  nop
0x140047849  lea     rcx, [rbp+pDeviceID]
0x14004784d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140047852  mov     ebx, edi
0x140047854  jmp     short loc_140047866
0x140047856  test    rbx, rbx
0x140047859  jz      short loc_140047864
0x14004785b  mov     rcx, rbx; pv
0x14004785e  call    cs:__imp_CoTaskMemFree
0x140047864  xor     ebx, ebx
0x140047866  lea     rcx, [rbp+pvar]; pvar
0x14004786a  call    cs:__imp_PropVariantClear
0x140047870  mov     eax, ebx
0x140047872  mov     rcx, [rbp+var_8]
0x140047876  xor     rcx, rsp; StackCookie
0x140047879  call    __security_check_cookie
0x14004787e  add     rsp, 60h
0x140047882  pop     r15
0x140047884  pop     r14
0x140047886  pop     r12
0x140047888  pop     rdi
0x140047889  pop     rsi
0x14004788a  pop     rbx
0x14004788b  pop     rbp
0x14004788c  retn
```
