# CIISClass::CreateClass(ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)

- ea: `0x180009a44`
- end: `0x180009d89`
- name: `?CreateClass@CIISClass@@SAJPEBG0AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z`
- size: `837`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct CCredentials *, unsigned int, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008340`
- `0x18000cf7c`
- `0x180015424`

## callees

- `0x180009480`
- `0x1800094f8`
- `0x180009a44`
- `0x18000b3b4`
- `0x18001364c`
- `0x1800148a0`
- `0x18001537c`
- `0x18001608c`
- `0x1800160d0`
- `0x18001a154`
- `0x18001beb8`
- `0x18001d66a`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ole32!StringFromCLSID` at `0x180009c05`
- `ole32!StringFromCLSID` at `0x180009c4f`
- `ole32!StringFromCLSID` at `0x180009c05`
- `ole32!StringFromCLSID` at `0x180009c4f`
- `ole32!CoTaskMemFree` at `0x180009b4b`
- `ole32!CoTaskMemFree` at `0x180009c32`
- `ole32!CoTaskMemFree` at `0x180009c7c`
- `ole32!CoTaskMemFree` at `0x180009b4b`
- `ole32!CoTaskMemFree` at `0x180009c32`
- `ole32!CoTaskMemFree` at `0x180009c7c`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009b2a`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009ba8`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009b2a`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009ba8`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009b73`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009b73`

## pseudocode

```c
__int64 __fastcall CIISClass::CreateClass(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct CCredentials *a3,
        unsigned int a4,
        const struct _GUID *a5,
        void **a6)
{
  int v10; // eax
  unsigned int v11; // edx
  CCoreADsObject *v12; // rdi
  HRESULT inited; // ebx
  LPWSTR v14; // rax
  LPWSTR v16; // rax
  struct _ClassInfo *ClassInfoW; // rax
  struct _ClassInfo *v18; // rsi
  const IID *v19; // rcx
  const IID *v20; // rcx
  const unsigned __int16 *v21; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  CCoreADsObject *v23; // [rsp+48h] [rbp-B8h] BYREF
  const struct _GUID *v24; // [rsp+50h] [rbp-B0h]
  _BYTE v25[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR v26; // [rsp+60h] [rbp-A0h]
  _BYTE v27[8]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR pStr; // [rsp+88h] [rbp-78h]

  v24 = a5;
  v23 = 0;
  pv = 0;
  memset_0(v27, 0, 0x230u);
  CLexer::CLexer((CLexer *)v25, a1);
  memset_0(v27, 0, 0x230u);
  v10 = CIISClass::AllocateClassObject(&v23, a3);
  v12 = v23;
  inited = v10;
  if ( v10 < 0 )
    goto LABEL_6;
  inited = ADsObject((struct CLexer *)v25, (struct _objectinfo *)v27);
  if ( inited < 0 )
    goto LABEL_6;
  inited = InitServerInfo(
             (CCoreADsObject *)((char *)v12 + 264),
             pStr,
             (struct IMSAdminBaseW **)v12 + 37,
             (struct IIsSchema **)v12 + 36);
  if ( inited < 0 )
    goto LABEL_6;
  v14 = AllocADsStr(pStr);
  *((_QWORD *)v12 + 30) = v14;
  if ( v14 && (v16 = AllocADsStr(a2), (*((_QWORD *)v12 + 31) = v16) != 0) )
  {
    ClassInfoW = IIsSchema::GetClassInfoW(*((IIsSchema **)v12 + 36), a2);
    v18 = ClassInfoW;
    if ( !ClassInfoW )
      goto LABEL_27;
    *((_DWORD *)v12 + 64) = 1;
    *((_DWORD *)v12 + 58) = *((_DWORD *)ClassInfoW + 22);
    *((_WORD *)v12 + 108) = *((_WORD *)ClassInfoW + 36);
    *((_WORD *)v12 + 56) = *((_WORD *)ClassInfoW + 16);
    v19 = (const IID *)*((_QWORD *)ClassInfoW + 2);
    if ( v19 )
    {
      inited = StringFromCLSID(v19, (LPOLESTR *)&pv);
      if ( inited < 0 )
        goto LABEL_6;
      inited = ADsAllocString(pv, (char *)v12 + 104);
      if ( inited < 0 )
        goto LABEL_6;
      CoTaskMemFree(pv);
      pv = 0;
    }
    v20 = (const IID *)*((_QWORD *)v18 + 1);
    if ( v20 )
    {
      inited = StringFromCLSID(v20, (LPOLESTR *)&pv);
      if ( inited < 0 )
        goto LABEL_6;
      inited = ADsAllocString(pv, (char *)v12 + 88);
      if ( inited < 0 )
        goto LABEL_6;
      CoTaskMemFree(pv);
      pv = 0;
    }
    inited = ADsAllocString(*((_QWORD *)v18 + 3), (char *)v12 + 96);
    if ( inited >= 0 )
    {
      inited = MakeVariantFromStringList(*((unsigned __int16 **)v18 + 5), (struct tagVARIANT *)v12 + 5);
      if ( inited >= 0 )
      {
        inited = MakeVariantFromStringList(*((unsigned __int16 **)v18 + 6), (struct tagVARIANT *)v12 + 6);
        if ( inited >= 0 )
        {
          inited = MakeVariantFromStringList(*((unsigned __int16 **)v18 + 7), (struct tagVARIANT *)v12 + 7);
          if ( inited >= 0 )
          {
            inited = MakeVariantFromStringList(*((unsigned __int16 **)v18 + 8), (struct tagVARIANT *)v12 + 8);
            if ( inited >= 0 )
            {
              inited = ADsAllocString(*((_QWORD *)v18 + 10), (char *)v12 + 224);
              if ( inited >= 0 )
              {
LABEL_27:
                inited = CCoreADsObject::InitializeCoreObject(v12, a1, a2, L"Class", v21, &CLSID_IISClass, a4);
                if ( inited >= 0 )
                {
                  inited = (**((__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v12 + 8))(
                             (__int64)v12 + 64,
                             v24,
                             a6);
                  if ( inited >= 0 )
                  {
                    (*(void (__fastcall **)(__int64))(*((_QWORD *)v12 + 8) + 16LL))((__int64)v12 + 64);
                    goto LABEL_10;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    inited = -2147024882;
  }
LABEL_6:
  if ( pv )
    CoTaskMemFree(pv);
  *a6 = 0;
  if ( v12 )
    CIISClass::`scalar deleting destructor'(v12, v11);
LABEL_10:
  FreeObjectInfo((struct _objectinfo *)v27);
  FreeADsStr(v26);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180009a44  mov     [rsp-8+arg_18], rbx
0x180009a49  push    rbp
0x180009a4a  push    rsi
0x180009a4b  push    rdi
0x180009a4c  push    r12
0x180009a4e  push    r13
0x180009a50  push    r14
0x180009a52  push    r15
0x180009a54  lea     rbp, [rsp-1C0h]
0x180009a5c  sub     rsp, 2C0h
0x180009a63  mov     rax, cs:__security_cookie
0x180009a6a  xor     rax, rsp
0x180009a6d  mov     [rbp+1F0h+var_40], rax
0x180009a74  mov     rax, [rbp+1F0h+arg_20]
0x180009a7b  mov     rbx, r8
0x180009a7e  mov     r15, [rbp+1F0h+arg_28]
0x180009a85  mov     r14, rdx
0x180009a88  mov     r12, rcx
0x180009a8b  mov     [rsp+2F0h+var_2A0], rax
0x180009a90  mov     edi, 230h
0x180009a95  mov     [rsp+2F0h+var_2A8], 0
0x180009a9e  mov     r8d, edi; Size
0x180009aa1  mov     [rsp+2F0h+pv], 0
0x180009aaa  xor     edx, edx; Val
0x180009aac  lea     rcx, [rbp+1F0h+var_270]; void *
0x180009ab0  mov     r13d, r9d
0x180009ab3  call    memset_0
0x180009ab8  mov     rdx, r12; unsigned __int16 *
0x180009abb  lea     rcx, [rsp+2F0h+var_298]; this
0x180009ac0  call    ??0CLexer@@QEAA@PEBG@Z; CLexer::CLexer(ushort const *)
0x180009ac5  mov     r8d, edi; Size
0x180009ac8  lea     rcx, [rbp+1F0h+var_270]; void *
0x180009acc  xor     edx, edx; Val
0x180009ace  call    memset_0
0x180009ad3  mov     rdx, rbx; struct CCredentials *
0x180009ad6  lea     rcx, [rsp+2F0h+var_2A8]; struct CIISClass **
0x180009adb  call    ?AllocateClassObject@CIISClass@@SAJPEAPEAV1@AEAVCCredentials@@@Z; CIISClass::AllocateClassObject(CIISClass * *,CCredentials &)
0x180009ae0  mov     rdi, [rsp+2F0h+var_2A8]
0x180009ae5  mov     ebx, eax
0x180009ae7  test    eax, eax
0x180009ae9  js      short loc_180009B41
0x180009aeb  lea     rdx, [rbp+1F0h+var_270]; struct _objectinfo *
0x180009aef  lea     rcx, [rsp+2F0h+var_298]; struct CLexer *
0x180009af4  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180009af9  mov     ebx, eax
0x180009afb  test    eax, eax
0x180009afd  js      short loc_180009B41
0x180009aff  mov     rdx, [rbp+1F0h+pStr]; unsigned __int16 *
0x180009b03  lea     rsi, [rdi+120h]
0x180009b0a  mov     r9, rsi; struct IIsSchema **
0x180009b0d  lea     r8, [rdi+128h]; struct IMSAdminBaseW **
0x180009b14  lea     rcx, [rdi+108h]; struct CCredentials *
0x180009b1b  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x180009b20  mov     ebx, eax
0x180009b22  test    eax, eax
0x180009b24  js      short loc_180009B41
0x180009b26  mov     rcx, [rbp+1F0h+pStr]; pStr
0x180009b2a  call    cs:__imp_AllocADsStr
0x180009b30  mov     [rdi+0F0h], rax
0x180009b37  test    rax, rax
0x180009b3a  jnz     short loc_180009BA5
0x180009b3c  mov     ebx, 8007000Eh
0x180009b41  mov     rcx, [rsp+2F0h+pv]; pv
0x180009b46  test    rcx, rcx
0x180009b49  jz      short loc_180009B51
0x180009b4b  call    cs:__imp_CoTaskMemFree
0x180009b51  mov     qword ptr [r15], 0
0x180009b58  test    rdi, rdi
0x180009b5b  jz      short loc_180009B65
0x180009b5d  mov     rcx, rdi; this
0x180009b60  call    ??_GCIISClass@@QEAAPEAXI@Z; CIISClass::`scalar deleting destructor'(uint)
0x180009b65  lea     rcx, [rbp+1F0h+var_270]; struct _objectinfo *
0x180009b69  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180009b6e  mov     rcx, [rsp+2F0h+var_290]; pStr
0x180009b73  call    cs:__imp_FreeADsStr
0x180009b79  mov     eax, ebx
0x180009b7b  mov     rcx, [rbp+1F0h+var_40]
0x180009b82  xor     rcx, rsp; StackCookie
0x180009b85  call    __security_check_cookie
0x180009b8a  mov     rbx, [rsp+2F0h+arg_18]
0x180009b92  add     rsp, 2C0h
0x180009b99  pop     r15
0x180009b9b  pop     r14
0x180009b9d  pop     r13
0x180009b9f  pop     r12
0x180009ba1  pop     rdi
0x180009ba2  pop     rsi
0x180009ba3  pop     rbp
0x180009ba4  retn
0x180009ba5  mov     rcx, r14; pStr
0x180009ba8  call    cs:__imp_AllocADsStr
0x180009bae  mov     [rdi+0F8h], rax
0x180009bb5  test    rax, rax
0x180009bb8  jz      short loc_180009B3C
0x180009bba  mov     rcx, [rsi]; this
0x180009bbd  mov     rdx, r14; unsigned __int16 *
0x180009bc0  call    ?GetClassInfoW@IIsSchema@@QEAAPEAU_ClassInfo@@PEBG@Z; IIsSchema::GetClassInfoW(ushort const *)
0x180009bc5  mov     rsi, rax
0x180009bc8  test    rax, rax
0x180009bcb  jz      loc_180009D21
0x180009bd1  mov     dword ptr [rdi+100h], 1
0x180009bdb  mov     ecx, [rax+58h]
0x180009bde  mov     [rdi+0E8h], ecx
0x180009be4  movzx   ecx, word ptr [rax+48h]
0x180009be8  mov     [rdi+0D8h], cx
0x180009bef  movzx   ecx, word ptr [rax+20h]
0x180009bf3  mov     [rdi+70h], cx
0x180009bf7  mov     rcx, [rax+10h]; rclsid
0x180009bfb  test    rcx, rcx
0x180009bfe  jz      short loc_180009C41
0x180009c00  lea     rdx, [rsp+2F0h+pv]; lplpsz
0x180009c05  call    cs:__imp_StringFromCLSID
0x180009c0b  mov     ebx, eax
0x180009c0d  test    eax, eax
0x180009c0f  js      loc_180009B41
0x180009c15  mov     rcx, [rsp+2F0h+pv]
0x180009c1a  lea     rdx, [rdi+68h]
0x180009c1e  call    ADsAllocString
0x180009c23  mov     ebx, eax
0x180009c25  test    eax, eax
0x180009c27  js      loc_180009B41
0x180009c2d  mov     rcx, [rsp+2F0h+pv]; pv
0x180009c32  call    cs:__imp_CoTaskMemFree
0x180009c38  mov     [rsp+2F0h+pv], 0
0x180009c41  mov     rcx, [rsi+8]; rclsid
0x180009c45  test    rcx, rcx
0x180009c48  jz      short loc_180009C8B
0x180009c4a  lea     rdx, [rsp+2F0h+pv]; lplpsz
0x180009c4f  call    cs:__imp_StringFromCLSID
0x180009c55  mov     ebx, eax
0x180009c57  test    eax, eax
0x180009c59  js      loc_180009B41
0x180009c5f  mov     rcx, [rsp+2F0h+pv]
0x180009c64  lea     rdx, [rdi+58h]
0x180009c68  call    ADsAllocString
0x180009c6d  mov     ebx, eax
0x180009c6f  test    eax, eax
0x180009c71  js      loc_180009B41
0x180009c77  mov     rcx, [rsp+2F0h+pv]; pv
0x180009c7c  call    cs:__imp_CoTaskMemFree
0x180009c82  mov     [rsp+2F0h+pv], 0
0x180009c8b  mov     rcx, [rsi+18h]
0x180009c8f  lea     rdx, [rdi+60h]
0x180009c93  call    ADsAllocString
0x180009c98  mov     ebx, eax
0x180009c9a  test    eax, eax
0x180009c9c  js      loc_180009B41
0x180009ca2  mov     rcx, [rsi+28h]; unsigned __int16 *
0x180009ca6  lea     rdx, [rdi+78h]; struct tagVARIANT *
0x180009caa  call    ?MakeVariantFromStringList@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringList(ushort *,tagVARIANT *)
0x180009caf  mov     ebx, eax
0x180009cb1  test    eax, eax
0x180009cb3  js      loc_180009B41
0x180009cb9  mov     rcx, [rsi+30h]; unsigned __int16 *
0x180009cbd  lea     rdx, [rdi+90h]; struct tagVARIANT *
0x180009cc4  call    ?MakeVariantFromStringList@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringList(ushort *,tagVARIANT *)
0x180009cc9  mov     ebx, eax
0x180009ccb  test    eax, eax
0x180009ccd  js      loc_180009B41
0x180009cd3  mov     rcx, [rsi+38h]; unsigned __int16 *
0x180009cd7  lea     rdx, [rdi+0A8h]; struct tagVARIANT *
0x180009cde  call    ?MakeVariantFromStringList@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringList(ushort *,tagVARIANT *)
0x180009ce3  mov     ebx, eax
0x180009ce5  test    eax, eax
0x180009ce7  js      loc_180009B41
0x180009ced  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180009cf1  lea     rdx, [rdi+0C0h]; struct tagVARIANT *
0x180009cf8  call    ?MakeVariantFromStringList@@YAJPEAGPEAUtagVARIANT@@@Z; MakeVariantFromStringList(ushort *,tagVARIANT *)
0x180009cfd  mov     ebx, eax
0x180009cff  test    eax, eax
0x180009d01  js      loc_180009B41
0x180009d07  mov     rcx, [rsi+50h]
0x180009d0b  lea     rdx, [rdi+0E0h]
0x180009d12  call    ADsAllocString
0x180009d17  mov     ebx, eax
0x180009d19  test    eax, eax
0x180009d1b  js      loc_180009B41
0x180009d21  lea     rax, CLSID_IISClass
0x180009d28  mov     [rsp+2F0h+var_2C0], r13d; unsigned int
0x180009d2d  lea     r9, aClass_0; "Class"
0x180009d34  mov     [rsp+2F0h+var_2C8], rax; struct _GUID *
0x180009d39  mov     r8, r14; unsigned __int16 *
0x180009d3c  mov     rdx, r12; unsigned __int16 *
0x180009d3f  mov     rcx, rdi; this
0x180009d42  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x180009d47  mov     ebx, eax
0x180009d49  test    eax, eax
0x180009d4b  js      loc_180009B41
0x180009d51  mov     rdx, [rsp+2F0h+var_2A0]
0x180009d56  lea     rsi, [rdi+40h]
0x180009d5a  mov     rax, [rsi]
0x180009d5d  mov     r8, r15
0x180009d60  mov     rcx, rsi
0x180009d63  mov     rax, [rax]
0x180009d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d6b  mov     ebx, eax
0x180009d6d  test    eax, eax
0x180009d6f  js      loc_180009B41
0x180009d75  mov     rax, [rsi]
0x180009d78  mov     rcx, rsi
0x180009d7b  mov     rax, [rax+10h]
0x180009d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d84  jmp     loc_180009B65
```
