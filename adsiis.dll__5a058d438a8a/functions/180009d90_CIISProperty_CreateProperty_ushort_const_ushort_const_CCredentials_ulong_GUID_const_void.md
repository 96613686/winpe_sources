# CIISProperty::CreateProperty(ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)

- ea: `0x180009d90`
- end: `0x18000a0a1`
- name: `?CreateProperty@CIISProperty@@SAJPEBG0AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z`
- size: `785`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, struct CCredentials *@<r8>, unsigned int@<r9d>, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008340`
- `0x18000d1a8`
- `0x180015b1c`

## callees

- `0x1800094a8`
- `0x180009624`
- `0x180009d90`
- `0x18001364c`
- `0x180013e08`
- `0x1800148a0`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001a25c`
- `0x18001bbc8`
- `0x18001beb8`
- `0x18001d66a`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x180009e76`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009ee3`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009e76`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009ee3`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009eae`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009eae`

## pseudocode

```c
__int64 __fastcall CIISProperty::CreateProperty(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct CCredentials *a3,
        unsigned int a4,
        const struct _GUID *a5,
        void **a6)
{
  struct _objectinfo *v9; // r12
  int v10; // eax
  unsigned int v11; // edx
  CCoreADsObject *v12; // rdi
  int inited; // ebx
  LPWSTR v14; // rax
  struct _objectinfo *v15; // rcx
  LPWSTR v17; // rax
  const struct _PropertyInfo *PropertyInfo; // rax
  const struct _PropertyInfo *v19; // rsi
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  unsigned __int16 *v22; // rcx
  int v23; // eax
  const unsigned __int16 *v24; // [rsp+20h] [rbp-E0h]
  CCoreADsObject *v26; // [rsp+48h] [rbp-B8h] BYREF
  const struct _GUID *v27; // [rsp+50h] [rbp-B0h]
  _BYTE v28[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR v29; // [rsp+60h] [rbp-A0h]
  _BYTE v30[8]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR pStr; // [rsp+88h] [rbp-78h]

  v27 = a5;
  v26 = 0;
  memset_0(v30, 0, 0x230u);
  v9 = 0;
  CLexer::CLexer((CLexer *)v28, a1);
  v10 = CIISProperty::AllocatePropertyObject(&v26, a3);
  v12 = v26;
  inited = v10;
  if ( v10 < 0 )
    goto LABEL_6;
  v9 = (struct _objectinfo *)v30;
  memset_0(v30, 0, 0x230u);
  inited = ADsObject((struct CLexer *)v28, (struct _objectinfo *)v30);
  if ( inited < 0 )
    goto LABEL_6;
  inited = InitServerInfo(
             (CCoreADsObject *)((char *)v12 + 176),
             pStr,
             (struct IMSAdminBaseW **)v12 + 26,
             (struct IIsSchema **)v12 + 25);
  if ( inited < 0 )
    goto LABEL_6;
  v14 = AllocADsStr(pStr);
  *((_QWORD *)v12 + 27) = v14;
  if ( v14 && (v17 = AllocADsStr(a2), (*((_QWORD *)v12 + 28) = v17) != 0) )
  {
    PropertyInfo = IIsSchema::GetPropertyInfo(*((IIsSchema **)v12 + 25), a2);
    v19 = PropertyInfo;
    if ( PropertyInfo )
    {
      *((_DWORD *)v12 + 58) = 1;
      inited = ADsAllocString(*((_QWORD *)PropertyInfo + 1), (char *)v12 + 96);
      if ( inited < 0 )
        goto LABEL_6;
      *((_DWORD *)v12 + 28) = *((_DWORD *)v19 + 6);
      *((_DWORD *)v12 + 29) = *((_DWORD *)v19 + 7);
      *((_WORD *)v12 + 60) = -(*((_DWORD *)v19 + 8) != 0);
      *((_DWORD *)v12 + 31) = *((_DWORD *)v19 + 12);
      *((_DWORD *)v12 + 32) = *((_DWORD *)v19 + 16);
      *((_DWORD *)v12 + 33) = *((_DWORD *)v19 + 15);
      *((_DWORD *)v12 + 40) = *((_DWORD *)v19 + 11);
      *((_DWORD *)v12 + 42) = *((_DWORD *)v19 + 9);
      *((_DWORD *)v12 + 41) = *((_DWORD *)v19 + 14);
      *((_DWORD *)v12 + 43) = *((_DWORD *)v19 + 13);
      v20 = SyntaxIdToString(*((_DWORD *)v12 + 40));
      inited = ADsAllocString(v20, v21);
      if ( inited < 0 )
        goto LABEL_6;
      v22 = (unsigned __int16 *)*((unsigned int *)v19 + 11);
      if ( (unsigned int)v22 <= 0xA && (v23 = 1570, _bittest(&v23, (unsigned int)v22)) )
      {
        *((_WORD *)v12 + 68) = 3;
        *((_DWORD *)v12 + 36) = *((_DWORD *)v19 + 17);
      }
      else if ( (unsigned int)((_DWORD)v22 - 6) <= 1 )
      {
        *((_WORD *)v12 + 68) = 11;
        *((_WORD *)v12 + 72) = -(*((_DWORD *)v19 + 17) != 0);
      }
      else if ( (((_DWORD)v22 - 4) & 0xFFFFFFFB) != 0 )
      {
        *((_WORD *)v12 + 68) = 8;
        inited = ADsAllocString(*((_QWORD *)v19 + 9), (char *)v12 + 144);
        if ( inited < 0 )
          goto LABEL_6;
      }
      else
      {
        inited = MakeVariantFromStringArray(
                   v22,
                   *((unsigned __int16 **)v19 + 9),
                   (struct tagVARIANT *)((char *)v12 + 136));
        if ( inited < 0 )
          goto LABEL_6;
      }
    }
    inited = CCoreADsObject::InitializeCoreObject(v12, a1, a2, L"Property", v24, &CLSID_IISProperty, a4);
    if ( inited >= 0 )
    {
      inited = (**((__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v12 + 8))(
                 (__int64)v12 + 64,
                 v27,
                 a6);
      if ( inited >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v12 + 8) + 16LL))((__int64)v12 + 64);
        v15 = (struct _objectinfo *)v30;
        goto LABEL_9;
      }
    }
  }
  else
  {
    inited = -2147024882;
  }
LABEL_6:
  *a6 = 0;
  if ( v12 )
    CIISProperty::`scalar deleting destructor'(v12, v11);
  v15 = v9;
LABEL_9:
  FreeObjectInfo(v15);
  FreeADsStr(v29);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180009d90  mov     [rsp-8+arg_18], rbx
0x180009d95  push    rbp
0x180009d96  push    rsi
0x180009d97  push    rdi
0x180009d98  push    r12
0x180009d9a  push    r13
0x180009d9c  push    r14
0x180009d9e  push    r15
0x180009da0  lea     rbp, [rsp-1C0h]
0x180009da8  sub     rsp, 2C0h
0x180009daf  mov     rax, cs:__security_cookie
0x180009db6  xor     rax, rsp
0x180009db9  mov     [rbp+1F0h+var_40], rax
0x180009dc0  mov     rax, [rbp+1F0h+arg_20]
0x180009dc7  mov     rbx, r8
0x180009dca  mov     r15, [rbp+1F0h+arg_28]
0x180009dd1  mov     r14, rdx
0x180009dd4  mov     r13, rcx
0x180009dd7  mov     [rsp+2F0h+var_2B0], r9d
0x180009ddc  mov     esi, 230h
0x180009de1  mov     [rsp+2F0h+var_2A0], rax
0x180009de6  mov     r8d, esi; Size
0x180009de9  mov     [rsp+2F0h+var_2A8], 0
0x180009df2  xor     edx, edx; Val
0x180009df4  lea     rcx, [rbp+1F0h+var_270]; void *
0x180009df8  call    memset_0
0x180009dfd  mov     rdx, r13; unsigned __int16 *
0x180009e00  lea     rcx, [rsp+2F0h+var_298]; this
0x180009e05  xor     r12d, r12d
0x180009e08  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180009e0d  mov     rdx, rbx; struct CCredentials *
0x180009e10  lea     rcx, [rsp+2F0h+var_2A8]; struct CIISProperty **
0x180009e15  call    ?AllocatePropertyObject@CIISProperty@@SAJPEAPEAV1@AEAVCCredentials@@@Z; CIISProperty::AllocatePropertyObject(CIISProperty * *,CCredentials &)
0x180009e1a  mov     rdi, [rsp+2F0h+var_2A8]
0x180009e1f  mov     ebx, eax
0x180009e21  test    eax, eax
0x180009e23  js      short loc_180009E8D
0x180009e25  mov     r8d, esi; Size
0x180009e28  lea     rcx, [rbp+1F0h+var_270]; void *
0x180009e2c  xor     edx, edx; Val
0x180009e2e  lea     r12, [rbp+1F0h+var_270]
0x180009e32  call    memset_0
0x180009e37  lea     rdx, [rbp+1F0h+var_270]; struct _objectinfo *
0x180009e3b  lea     rcx, [rsp+2F0h+var_298]; struct CLexer *
0x180009e40  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180009e45  mov     ebx, eax
0x180009e47  test    eax, eax
0x180009e49  js      short loc_180009E8D
0x180009e4b  mov     rdx, [rbp+1F0h+pStr]; unsigned __int16 *
0x180009e4f  lea     rsi, [rdi+0C8h]
0x180009e56  mov     r9, rsi; struct IIsSchema **
0x180009e59  lea     r8, [rdi+0D0h]; struct IMSAdminBaseW **
0x180009e60  lea     rcx, [rdi+0B0h]; struct CCredentials *
0x180009e67  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x180009e6c  mov     ebx, eax
0x180009e6e  test    eax, eax
0x180009e70  js      short loc_180009E8D
0x180009e72  mov     rcx, [rbp+1F0h+pStr]; pStr
0x180009e76  call    cs:__imp_AllocADsStr
0x180009e7c  mov     [rdi+0D8h], rax
0x180009e83  test    rax, rax
0x180009e86  jnz     short loc_180009EE0
0x180009e88  mov     ebx, 8007000Eh
0x180009e8d  mov     qword ptr [r15], 0
0x180009e94  test    rdi, rdi
0x180009e97  jz      short loc_180009EA1
0x180009e99  mov     rcx, rdi; this
0x180009e9c  call    ??_GCIISProperty@@QEAAPEAXI@Z; CIISProperty::`scalar deleting destructor'(uint)
0x180009ea1  mov     rcx, r12; struct _objectinfo *
0x180009ea4  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180009ea9  mov     rcx, [rsp+2F0h+var_290]; pStr
0x180009eae  call    cs:__imp_FreeADsStr
0x180009eb4  mov     eax, ebx
0x180009eb6  mov     rcx, [rbp+1F0h+var_40]
0x180009ebd  xor     rcx, rsp; StackCookie
0x180009ec0  call    __security_check_cookie
0x180009ec5  mov     rbx, [rsp+2F0h+arg_18]
0x180009ecd  add     rsp, 2C0h
0x180009ed4  pop     r15
0x180009ed6  pop     r14
0x180009ed8  pop     r13
0x180009eda  pop     r12
0x180009edc  pop     rdi
0x180009edd  pop     rsi
0x180009ede  pop     rbp
0x180009edf  retn
0x180009ee0  mov     rcx, r14; pStr
0x180009ee3  call    cs:__imp_AllocADsStr
0x180009ee9  mov     [rdi+0E0h], rax
0x180009ef0  test    rax, rax
0x180009ef3  jz      short loc_180009E88
0x180009ef5  mov     rcx, [rsi]; this
0x180009ef8  mov     rdx, r14; unsigned __int16 *
0x180009efb  call    ?GetPropertyInfo@IIsSchema@@QEAAPEBU_PropertyInfo@@PEBG@Z; IIsSchema::GetPropertyInfo(ushort const *)
0x180009f00  mov     rsi, rax
0x180009f03  test    rax, rax
0x180009f06  jz      loc_18000A032
0x180009f0c  mov     dword ptr [rdi+0E8h], 1
0x180009f16  lea     rdx, [rdi+60h]
0x180009f1a  mov     rcx, [rax+8]
0x180009f1e  call    ADsAllocString
0x180009f23  mov     ebx, eax
0x180009f25  test    eax, eax
0x180009f27  js      loc_180009E8D
0x180009f2d  mov     ecx, [rsi+18h]
0x180009f30  lea     rdx, [rdi+68h]
0x180009f34  mov     [rdi+70h], ecx
0x180009f37  mov     eax, [rsi+1Ch]
0x180009f3a  mov     [rdi+74h], eax
0x180009f3d  mov     eax, [rsi+20h]
0x180009f40  neg     eax
0x180009f42  sbb     cx, cx
0x180009f45  mov     [rdi+78h], cx
0x180009f49  mov     eax, [rsi+30h]
0x180009f4c  mov     [rdi+7Ch], eax
0x180009f4f  mov     eax, [rsi+40h]
0x180009f52  mov     [rdi+80h], eax
0x180009f58  mov     eax, [rsi+3Ch]
0x180009f5b  mov     [rdi+84h], eax
0x180009f61  mov     eax, [rsi+2Ch]
0x180009f64  mov     [rdi+0A0h], eax
0x180009f6a  mov     eax, [rsi+24h]
0x180009f6d  mov     [rdi+0A8h], eax
0x180009f73  mov     eax, [rsi+38h]
0x180009f76  mov     [rdi+0A4h], eax
0x180009f7c  mov     eax, [rsi+34h]
0x180009f7f  mov     [rdi+0ACh], eax
0x180009f85  mov     ecx, [rdi+0A0h]; unsigned int
0x180009f8b  call    ?SyntaxIdToString@@YAPEBGK@Z; SyntaxIdToString(ulong)
0x180009f90  mov     rcx, rax
0x180009f93  call    ADsAllocString
0x180009f98  mov     ebx, eax
0x180009f9a  test    eax, eax
0x180009f9c  js      loc_180009E8D
0x180009fa2  mov     ecx, [rsi+2Ch]; unsigned __int16 *
0x180009fa5  cmp     ecx, 0Ah
0x180009fa8  ja      short loc_180009FC8
0x180009faa  mov     eax, 622h
0x180009faf  bt      eax, ecx
0x180009fb2  jnb     short loc_180009FC8
0x180009fb4  mov     word ptr [rdi+88h], 3
0x180009fbd  mov     eax, [rsi+44h]
0x180009fc0  mov     [rdi+90h], eax
0x180009fc6  jmp     short loc_18000A032
0x180009fc8  lea     eax, [rcx-6]
0x180009fcb  cmp     eax, 1
0x180009fce  jbe     short loc_18000A01A
0x180009fd0  lea     eax, [rcx-4]
0x180009fd3  test    eax, 0FFFFFFFBh
0x180009fd8  jz      short loc_180009FFE
0x180009fda  mov     word ptr [rdi+88h], 8
0x180009fe3  lea     rdx, [rdi+90h]
0x180009fea  mov     rcx, [rsi+48h]
0x180009fee  call    ADsAllocString
0x180009ff3  mov     ebx, eax
0x180009ff5  test    eax, eax
0x180009ff7  jns     short loc_18000A032
0x180009ff9  jmp     loc_180009E8D
0x180009ffe  mov     rdx, [rsi+48h]; unsigned __int16 *
0x18000a002  lea     r8, [rdi+88h]; struct tagVARIANT *
0x18000a009  call    ?MakeVariantFromStringArray@@YAJPEAG0PEAUtagVARIANT@@@Z; MakeVariantFromStringArray(ushort *,ushort *,tagVARIANT *)
0x18000a00e  mov     ebx, eax
0x18000a010  test    eax, eax
0x18000a012  js      loc_180009E8D
0x18000a018  jmp     short loc_18000A032
0x18000a01a  mov     word ptr [rdi+88h], 0Bh
0x18000a023  mov     eax, [rsi+44h]
0x18000a026  neg     eax
0x18000a028  sbb     cx, cx
0x18000a02b  mov     [rdi+90h], cx
0x18000a032  mov     eax, [rsp+2F0h+var_2B0]
0x18000a036  lea     r9, aProperty; "Property"
0x18000a03d  mov     [rsp+2F0h+var_2C0], eax; unsigned int
0x18000a041  mov     r8, r14; unsigned __int16 *
0x18000a044  lea     rax, CLSID_IISProperty
0x18000a04b  mov     rdx, r13; unsigned __int16 *
0x18000a04e  mov     rcx, rdi; this
0x18000a051  mov     [rsp+2F0h+var_2C8], rax; struct _GUID *
0x18000a056  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x18000a05b  mov     ebx, eax
0x18000a05d  test    eax, eax
0x18000a05f  js      loc_180009E8D
0x18000a065  mov     rdx, [rsp+2F0h+var_2A0]
0x18000a06a  lea     rsi, [rdi+40h]
0x18000a06e  mov     rax, [rsi]
0x18000a071  mov     r8, r15
0x18000a074  mov     rcx, rsi
0x18000a077  mov     rax, [rax]
0x18000a07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a07f  mov     ebx, eax
0x18000a081  test    eax, eax
0x18000a083  js      loc_180009E8D
0x18000a089  mov     rax, [rsi]
0x18000a08c  mov     rcx, rsi
0x18000a08f  mov     rax, [rax+10h]
0x18000a093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a098  lea     rcx, [rbp+1F0h+var_270]
0x18000a09c  jmp     loc_180009EA4
```
