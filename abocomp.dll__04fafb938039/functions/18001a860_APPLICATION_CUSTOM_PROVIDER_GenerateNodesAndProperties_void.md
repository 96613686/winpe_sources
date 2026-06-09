# APPLICATION_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x18001a860`
- end: `0x18001aae3`
- name: `?GenerateNodesAndProperties@APPLICATION_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `643`
- prototype: `__int64 __fastcall(APPLICATION_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000473c`
- `0x1800047b0`
- `0x180006e28`
- `0x180007148`
- `0x18001a36c`
- `0x18001a5e0`
- `0x18001a690`
- `0x18001a860`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001a9aa`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001aa40`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001a9aa`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001aa40`

## string_xrefs

- `0x18001aa4d`: `Failed to generate Common App Properties for node (%s).  error = %08x\n`

## pseudocode

```c
__int64 __fastcall APPLICATION_CUSTOM_PROVIDER::GenerateNodesAndProperties(APPLICATION_CUSTOM_PROVIDER *this)
{
  __int64 *v2; // rcx
  ABO_NODE *v3; // rdi
  __int64 v4; // rax
  int LegacyIdentifiers; // ebx
  unsigned int v6; // r15d
  VDIR_CUSTOM_PROVIDER *v7; // rax
  VDIR_CUSTOM_PROVIDER *v8; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v9; // r14
  int v10; // ebx
  const unsigned __int16 *Str; // rax
  int CommonAppProperties; // ebx
  const unsigned __int16 *v13; // rax
  unsigned __int16 *v15; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+38h] BYREF
  struct INativeConfigurationElement *v17; // [rsp+88h] [rbp+40h] BYREF
  __int64 v18; // [rsp+90h] [rbp+48h] BYREF
  ABO_NODE *v19; // [rsp+98h] [rbp+50h] BYREF

  v17 = 0;
  v2 = (__int64 *)*((_QWORD *)this + 3);
  v18 = 0;
  v3 = 0;
  v16 = 0;
  v15 = 0;
  v4 = *v2;
  v19 = 0;
  LegacyIdentifiers = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 40))(v2, &v18);
  if ( LegacyIdentifiers >= 0 )
  {
    LegacyIdentifiers = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, &v16);
    if ( LegacyIdentifiers >= 0 )
    {
      v6 = 0;
      if ( v16 )
      {
        while ( 1 )
        {
          LegacyIdentifiers = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v18 + 32LL))(
                                v18,
                                v6,
                                &v17);
          if ( LegacyIdentifiers < 0 )
            break;
          LegacyIdentifiers = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                                v17,
                                L"path",
                                &v15,
                                0,
                                0);
          if ( LegacyIdentifiers < 0 )
            break;
          LegacyIdentifiers = ABO_NODE::CreateNode(*((struct ABO_TREE ***)this + 2), v15, 1, &v19, 0);
          if ( LegacyIdentifiers < 0 )
          {
            v3 = v19;
            goto LABEL_16;
          }
          v7 = (VDIR_CUSTOM_PROVIDER *)operator new(0x60u);
          v3 = v19;
          if ( !v7
            || (v8 = VDIR_CUSTOM_PROVIDER::VDIR_CUSTOM_PROVIDER(
                       v7,
                       v19,
                       v17,
                       *((struct INativeConfigurationElement **)this + 3)),
                (v9 = v8) == 0) )
          {
            LegacyIdentifiers = -2147024888;
            goto LABEL_16;
          }
          v10 = (*(__int64 (__fastcall **)(VDIR_CUSTOM_PROVIDER *))(*(_QWORD *)v8 + 32LL))(v8);
          if ( v10 < 0 )
          {
            Str = STRU::QueryStr((ABO_NODE *)((char *)v3 + 56));
            ABO_MAPPER_LOG::WriteLogEntry(
              (HANDLE *)g_pAboLog,
              L"Failed to generate Vdir Node and Properties for node (%s).  error = %08x\n",
              Str,
              (unsigned int)v10);
            *((_DWORD *)v3 + 61) = 3;
            *((_DWORD *)v3 + 62) = v10;
          }
          LegacyIdentifiers = ABO_NODE::AddProvider(v3, v9);
          if ( LegacyIdentifiers < 0 )
          {
            CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v9);
            goto LABEL_16;
          }
          CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v9);
          ABO_NODE::DereferenceAboNode(v3);
          v3 = 0;
          v19 = 0;
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
          ++v6;
          v17 = 0;
          if ( v6 >= v16 )
            goto LABEL_13;
        }
      }
      else
      {
LABEL_13:
        CommonAppProperties = APPLICATION_CUSTOM_PROVIDER::GenerateCommonAppProperties(
                                *((struct ABO_NODE **)this + 2),
                                *((struct INativeConfigurationElement **)this + 3));
        if ( CommonAppProperties < 0 )
        {
          v13 = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
          ABO_MAPPER_LOG::WriteLogEntry(
            (HANDLE *)g_pAboLog,
            L"Failed to generate Common App Properties for node (%s).  error = %08x\n",
            v13,
            (unsigned int)CommonAppProperties);
          *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 2;
          *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = CommonAppProperties;
        }
        LegacyIdentifiers = APPLICATION_CUSTOM_PROVIDER::GenerateLegacyIdentifiers(this);
LABEL_16:
        if ( v3 )
          ABO_NODE::DereferenceAboNode(v3);
      }
    }
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)LegacyIdentifiers;
}

```

## disassembly

```asm
0x18001a860  push    rbp
0x18001a862  push    rbx
0x18001a863  push    rsi
0x18001a864  push    rdi
0x18001a865  push    r14
0x18001a867  push    r15
0x18001a869  mov     rbp, rsp
0x18001a86c  sub     rsp, 48h
0x18001a870  mov     rsi, rcx
0x18001a873  mov     [rbp+arg_8], 0
0x18001a87b  mov     rcx, [rcx+18h]
0x18001a87f  lea     rdx, [rbp+arg_10]
0x18001a883  mov     [rbp+arg_10], 0
0x18001a88b  xor     edi, edi
0x18001a88d  mov     [rbp+arg_0], 0
0x18001a894  mov     [rbp+var_18], 0
0x18001a89c  mov     rax, [rcx]
0x18001a89f  mov     [rbp+arg_18], rdi
0x18001a8a3  mov     rax, [rax+28h]
0x18001a8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8ac  mov     ebx, eax
0x18001a8ae  test    eax, eax
0x18001a8b0  js      loc_18001AA8E
0x18001a8b6  mov     rcx, [rbp+arg_10]
0x18001a8ba  lea     rdx, [rbp+arg_0]
0x18001a8be  mov     rax, [rcx]
0x18001a8c1  mov     rax, [rax+18h]
0x18001a8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8ca  mov     ebx, eax
0x18001a8cc  test    eax, eax
0x18001a8ce  js      loc_18001AA8E
0x18001a8d4  xor     r15d, r15d
0x18001a8d7  cmp     [rbp+arg_0], edi
0x18001a8da  jbe     loc_18001AA25
0x18001a8e0  mov     rcx, [rbp+arg_10]
0x18001a8e4  lea     r8, [rbp+arg_8]
0x18001a8e8  mov     edx, r15d
0x18001a8eb  mov     rax, [rcx]
0x18001a8ee  mov     rax, [rax+20h]
0x18001a8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8f7  mov     ebx, eax
0x18001a8f9  test    eax, eax
0x18001a8fb  js      loc_18001AA8E
0x18001a901  mov     rcx, [rbp+arg_8]
0x18001a905  lea     r8, [rbp+var_18]
0x18001a909  xor     r9d, r9d
0x18001a90c  mov     qword ptr [rsp+48h+var_28], 0
0x18001a915  lea     rdx, aPath; "path"
0x18001a91c  mov     rax, [rcx]
0x18001a91f  mov     rax, [rax+40h]
0x18001a923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a928  mov     ebx, eax
0x18001a92a  test    eax, eax
0x18001a92c  js      loc_18001AA8E
0x18001a932  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18001a936  lea     r9, [rbp+arg_18]; struct ABO_NODE **
0x18001a93a  mov     rcx, [rsi+10h]; this
0x18001a93e  mov     r8d, 1; int
0x18001a944  mov     [rsp+48h+var_28], 0; int
0x18001a94c  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x18001a951  mov     ebx, eax
0x18001a953  test    eax, eax
0x18001a955  js      loc_18001AADD
0x18001a95b  mov     ecx, 60h ; '`'; Size
0x18001a960  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a965  mov     rdi, [rbp+arg_18]
0x18001a969  test    rax, rax
0x18001a96c  jz      loc_18001AAD6
0x18001a972  mov     r9, [rsi+18h]; struct INativeConfigurationElement *
0x18001a976  mov     rdx, rdi; struct ABO_NODE *
0x18001a979  mov     r8, [rbp+arg_8]; struct INativeConfigurationElement *
0x18001a97d  mov     rcx, rax; this
0x18001a980  call    ??0VDIR_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; VDIR_CUSTOM_PROVIDER::VDIR_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x18001a985  mov     r14, rax
0x18001a988  test    rax, rax
0x18001a98b  jz      loc_18001AAD6
0x18001a991  mov     rcx, [rax]
0x18001a994  mov     rax, [rcx+20h]
0x18001a998  mov     rcx, r14
0x18001a99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a0  mov     ebx, eax
0x18001a9a2  test    eax, eax
0x18001a9a4  jns     short loc_18001A9D9
0x18001a9a6  lea     rcx, [rdi+38h]
0x18001a9aa  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001a9b0  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18001a9b7  lea     rdx, aFailedToGenera_23; "Failed to generate Vdir Node and Proper"...
0x18001a9be  mov     r8, rax
0x18001a9c1  mov     r9d, ebx
0x18001a9c4  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18001a9c9  mov     dword ptr [rdi+0F4h], 3
0x18001a9d3  mov     [rdi+0F8h], ebx
0x18001a9d9  mov     rdx, r14; struct CUSTOM_PROPERTY_PROVIDER *
0x18001a9dc  mov     rcx, rdi; this
0x18001a9df  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x18001a9e4  mov     ebx, eax
0x18001a9e6  mov     rcx, r14; this
0x18001a9e9  test    eax, eax
0x18001a9eb  js      loc_18001AACF
0x18001a9f1  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18001a9f6  mov     rcx, rdi; this
0x18001a9f9  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18001a9fe  mov     rcx, [rbp+arg_8]
0x18001aa02  xor     edi, edi
0x18001aa04  mov     [rbp+arg_18], rdi
0x18001aa08  mov     rax, [rcx]
0x18001aa0b  mov     rax, [rax+10h]
0x18001aa0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa14  inc     r15d
0x18001aa17  mov     [rbp+arg_8], rdi
0x18001aa1b  cmp     r15d, [rbp+arg_0]
0x18001aa1f  jb      loc_18001A8E0
0x18001aa25  mov     rdx, [rsi+18h]; struct INativeConfigurationElement *
0x18001aa29  mov     rcx, [rsi+10h]; struct ABO_NODE *
0x18001aa2d  call    ?GenerateCommonAppProperties@APPLICATION_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; APPLICATION_CUSTOM_PROVIDER::GenerateCommonAppProperties(ABO_NODE *,INativeConfigurationElement *)
0x18001aa32  mov     ebx, eax
0x18001aa34  test    eax, eax
0x18001aa36  jns     short loc_18001AA77
0x18001aa38  mov     rcx, [rsi+10h]
0x18001aa3c  add     rcx, 38h ; '8'
0x18001aa40  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001aa46  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18001aa4d  lea     rdx, aFailedToGenera_27; "Failed to generate Common App Propertie"...
0x18001aa54  mov     r8, rax
0x18001aa57  mov     r9d, ebx
0x18001aa5a  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18001aa5f  mov     rcx, [rsi+10h]
0x18001aa63  mov     dword ptr [rcx+0F4h], 2
0x18001aa6d  mov     rax, [rsi+10h]
0x18001aa71  mov     [rax+0F8h], ebx
0x18001aa77  mov     rcx, rsi; this
0x18001aa7a  call    ?GenerateLegacyIdentifiers@APPLICATION_CUSTOM_PROVIDER@@QEAAJXZ; APPLICATION_CUSTOM_PROVIDER::GenerateLegacyIdentifiers(void)
0x18001aa7f  mov     ebx, eax
0x18001aa81  test    rdi, rdi
0x18001aa84  jz      short loc_18001AA8E
0x18001aa86  mov     rcx, rdi; this
0x18001aa89  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18001aa8e  mov     rcx, [rbp+arg_10]
0x18001aa92  test    rcx, rcx
0x18001aa95  jz      short loc_18001AAAB
0x18001aa97  mov     rax, [rcx]
0x18001aa9a  mov     rax, [rax+10h]
0x18001aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa3  mov     [rbp+arg_10], 0
0x18001aaab  mov     rcx, [rbp+arg_8]
0x18001aaaf  test    rcx, rcx
0x18001aab2  jz      short loc_18001AAC0
0x18001aab4  mov     rax, [rcx]
0x18001aab7  mov     rax, [rax+10h]
0x18001aabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aac0  mov     eax, ebx
0x18001aac2  add     rsp, 48h
0x18001aac6  pop     r15
0x18001aac8  pop     r14
0x18001aaca  pop     rdi
0x18001aacb  pop     rsi
0x18001aacc  pop     rbx
0x18001aacd  pop     rbp
0x18001aace  retn
0x18001aacf  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18001aad4  jmp     short loc_18001AA81
0x18001aad6  mov     ebx, 80070008h
0x18001aadb  jmp     short loc_18001AA81
0x18001aadd  mov     rdi, [rbp+arg_18]
0x18001aae1  jmp     short loc_18001AA81
```
