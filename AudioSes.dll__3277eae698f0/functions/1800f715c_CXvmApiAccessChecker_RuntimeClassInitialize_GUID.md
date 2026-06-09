# CXvmApiAccessChecker::RuntimeClassInitialize(_GUID)

- ea: `0x1800f715c`
- end: `0x1800f74bb`
- name: `?RuntimeClassInitialize@CXvmApiAccessChecker@@QEAAJU_GUID@@@Z`
- size: `863`
- prototype: `int(CXvmApiAccessChecker *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f6b34`

## callees

- `0x180007f00`
- `0x18000cb1c`
- `0x180010a90`
- `0x180020764`
- `0x180087e80`
- `0x180088ce8`
- `0x180088d48`
- `0x18008ac8d`
- `0x1800f715c`
- `0x180123010`

## import_xrefs

- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1800f727e`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1800f727e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f7206`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f7206`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800f7389`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800f7455`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800f747a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800f7389`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800f7455`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800f747a`

## string_xrefs

- `0x1800f7252`: `avcore\audiocore\lib\crossvmapiaccesschecker\crossvmapiaccesschecker.cpp`
- `0x1800f7294`: `avcore\audiocore\lib\crossvmapiaccesschecker\crossvmapiaccesschecker.cpp`
- `0x1800f72e4`: `avcore\audiocore\lib\crossvmapiaccesschecker\crossvmapiaccesschecker.cpp`
- `0x1800f743c`: `avcore\audiocore\lib\crossvmapiaccesschecker\crossvmapiaccesschecker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CXvmApiAccessChecker::RuntimeClassInitialize(CXvmApiAccessChecker *this, struct _GUID *a2)
{
  const IID *v2; // rbx
  char *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  PROPVARIANT *v13; // rcx
  _BYTE *v14; // rdx
  unsigned int v15; // eax
  unsigned int i; // ecx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  _BYTE *v20; // rdx
  unsigned int v21; // eax
  unsigned int j; // ecx
  int v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v28; // [rsp+50h] [rbp-B0h]
  PROPVARIANT v29[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v30; // [rsp+68h] [rbp-98h]
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v2 = a2;
  v4 = (char *)this + 16;
  if ( v4 < v4 + 26 )
  {
    LOBYTE(a2) = 1;
    memset_0(v4, (int)a2, v4 + 26 >= v4 ? 0x1A : 0);
  }
  if ( (char *)this + 42 <= (char *)this + 45 )
  {
    LOBYTE(a2) = 1;
    memset_0((char *)this + 42, (int)a2, (char *)this + 45 >= (char *)this + 42 ? 3 : 0);
  }
  if ( memcmp_0(v2, &GUID_NULL, 0x10u) )
  {
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v5 = StringFromCLSID(v2, &lpsz);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = (unsigned int)v5;
      v8 = 53;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"avcore\\audiocore\\lib\\crossvmapiaccesschecker\\crossvmapiaccesschecker.cpp",
        (const char *)v7,
        v24);
LABEL_46:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpsz);
      return v6;
    }
    v24 = (int)lpsz;
    if ( swprintf_s(Buffer, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio\\Containers\\") == -1 )
    {
      v6 = -2147024774;
      v7 = 2147942522LL;
      v8 = 56;
      goto LABEL_10;
    }
    v25 = 0;
    v9 = MMDeviceCreateRegistryPropertyStore(Buffer, 257, &v25);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"avcore\\audiocore\\lib\\crossvmapiaccesschecker\\crossvmapiaccesschecker.cpp",
        (const char *)(unsigned int)v9,
        v24);
LABEL_45:
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
      goto LABEL_46;
    }
    *(_OWORD *)pvar = 0;
    v28 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
            v25,
            PKEY_BlockedProxyAudioObjects,
            pvar);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      v12 = 63;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"avcore\\audiocore\\lib\\crossvmapiaccesschecker\\crossvmapiaccesschecker.cpp",
        (const char *)v11,
        v24);
      v13 = pvar;
LABEL_44:
      PropVariantClear(v13);
      goto LABEL_45;
    }
    if ( LOWORD(pvar[0]) == 65 )
    {
      v14 = v28;
      v15 = (unsigned int)pvar[1];
      if ( LODWORD(pvar[1]) > 1 && *v28 != 1 )
      {
        v6 = -2147024809;
        v11 = 2147942487LL;
        v12 = 71;
        goto LABEL_15;
      }
      for ( i = 1; i < v15; ++i )
      {
        if ( v14[i] >= 0x1Au )
        {
          v6 = -2147024809;
          v11 = 2147942487LL;
          v12 = 77;
          goto LABEL_15;
        }
        *((_BYTE *)this + (unsigned __int8)v14[i] + 16) = 0;
        v14 = v28;
        v15 = (unsigned int)pvar[1];
      }
    }
    else if ( LOWORD(pvar[0]) )
    {
      v6 = -2147024809;
      v11 = 2147942487LL;
      v12 = 64;
      goto LABEL_15;
    }
    PropVariantClear(pvar);
    *(_OWORD *)v29 = 0;
    v30 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
            v25,
            PKEY_BlockedXvmAudioApis,
            v29);
    v6 = v17;
    if ( v17 < 0 )
    {
      v18 = (unsigned int)v17;
      v19 = 85;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"avcore\\audiocore\\lib\\crossvmapiaccesschecker\\crossvmapiaccesschecker.cpp",
        (const char *)v18,
        v24);
      v13 = v29;
      goto LABEL_44;
    }
    if ( LOWORD(v29[0]) == 65 )
    {
      v20 = v30;
      v21 = (unsigned int)v29[1];
      if ( LODWORD(v29[1]) > 1 && *v30 != 1 )
      {
        v19 = 93;
        goto LABEL_42;
      }
      for ( j = 1; j < v21; ++j )
      {
        if ( v20[j] >= 3u )
        {
          v19 = 99;
          goto LABEL_42;
        }
        *((_BYTE *)this + (unsigned __int8)v20[j] + 42) = 0;
        v20 = v30;
        v21 = (unsigned int)v29[1];
      }
    }
    else if ( LOWORD(v29[0]) )
    {
      v19 = 86;
LABEL_42:
      v6 = -2147024809;
      v18 = 2147942487LL;
      goto LABEL_43;
    }
    PropVariantClear(v29);
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpsz);
  }
  return 0;
}

```

## disassembly

```asm
0x1800f715c  mov     [rsp-8+arg_10], rbx
0x1800f7161  push    rbp
0x1800f7162  push    rdi
0x1800f7163  push    r14
0x1800f7165  lea     rbp, [rsp-190h]
0x1800f716d  sub     rsp, 290h
0x1800f7174  mov     rax, cs:__security_cookie
0x1800f717b  xor     rax, rsp
0x1800f717e  mov     [rbp+1A0h+var_20], rax
0x1800f7185  mov     rbx, rdx
0x1800f7188  mov     rdi, rcx
0x1800f718b  add     rcx, 10h; void *
0x1800f718f  lea     rax, [rcx+1Ah]
0x1800f7193  cmp     rax, rcx
0x1800f7196  sbb     r8, r8
0x1800f7199  not     r8
0x1800f719c  and     r8d, 1Ah; Size
0x1800f71a0  cmp     rcx, rax
0x1800f71a3  ja      short loc_1800F71AC
0x1800f71a5  mov     dl, 1; Val
0x1800f71a7  call    memset_0
0x1800f71ac  lea     rcx, [rdi+2Ah]; void *
0x1800f71b0  lea     rax, [rcx+3]
0x1800f71b4  cmp     rax, rcx
0x1800f71b7  sbb     r8, r8
0x1800f71ba  not     r8
0x1800f71bd  and     r8d, 3; Size
0x1800f71c1  cmp     rcx, rax
0x1800f71c4  ja      short loc_1800F71CD
0x1800f71c6  mov     dl, 1; Val
0x1800f71c8  call    memset_0
0x1800f71cd  mov     r8d, 10h; Size
0x1800f71d3  lea     rdx, GUID_NULL; Buf2
0x1800f71da  mov     rcx, rbx; Buf1
0x1800f71dd  call    memcmp_0
0x1800f71e2  xor     r14d, r14d
0x1800f71e5  test    eax, eax
0x1800f71e7  jz      loc_1800F7496
0x1800f71ed  mov     [rsp+2A0h+lpsz], r14
0x1800f71f2  xor     edx, edx
0x1800f71f4  lea     rcx, [rsp+2A0h+lpsz]
0x1800f71f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f71fe  lea     rdx, [rsp+2A0h+lpsz]; lplpsz
0x1800f7203  mov     rcx, rbx; rclsid
0x1800f7206  call    cs:__imp_StringFromCLSID
0x1800f720c  mov     ebx, eax
0x1800f720e  test    eax, eax
0x1800f7210  jns     short loc_1800F721B
0x1800f7212  mov     r9d, eax
0x1800f7215  lea     edx, [r14+35h]
0x1800f7219  jmp     short loc_1800F7252
0x1800f721b  mov     rax, [rsp+2A0h+lpsz]
0x1800f7220  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800f7225  lea     r9, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800f722c  lea     r8, aSS; "%s\\%s"
0x1800f7233  mov     edx, 104h; BufferCount
0x1800f7238  lea     rcx, [rsp+2A0h+Buffer]; Buffer
0x1800f723d  call    swprintf_s
0x1800f7242  cmp     eax, 0FFFFFFFFh
0x1800f7245  jnz     short loc_1800F726A
0x1800f7247  mov     ebx, 8007007Ah
0x1800f724c  mov     r9d, ebx; char *
0x1800f724f  lea     edx, [rax+39h]; void *
0x1800f7252  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\lib\\crossvmapiacces"...
0x1800f7259  mov     rcx, [rbp+1A8h]; this
0x1800f7260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7265  jmp     loc_1800F7467
0x1800f726a  mov     [rsp+2A0h+var_270], r14
0x1800f726f  lea     r8, [rsp+2A0h+var_270]
0x1800f7274  mov     edx, 101h
0x1800f7279  lea     rcx, [rsp+2A0h+Buffer]
0x1800f727e  call    cs:__imp_MMDeviceCreateRegistryPropertyStore
0x1800f7284  mov     ebx, eax
0x1800f7286  test    eax, eax
0x1800f7288  jns     short loc_1800F72AA
0x1800f728a  mov     rcx, [rbp+1A8h]; this
0x1800f7291  mov     r9d, eax; char *
0x1800f7294  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\lib\\crossvmapiacces"...
0x1800f729b  mov     edx, 3Bh ; ';'; void *
0x1800f72a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f72a5  jmp     loc_1800F745C
0x1800f72aa  xorps   xmm0, xmm0
0x1800f72ad  xor     eax, eax
0x1800f72af  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x1800f72b4  mov     [rsp+2A0h+var_250], rax
0x1800f72b9  mov     rcx, [rsp+2A0h+var_270]
0x1800f72be  mov     rax, [rcx]
0x1800f72c1  lea     r8, [rsp+2A0h+pvar]
0x1800f72c6  lea     rdx, PKEY_BlockedProxyAudioObjects
0x1800f72cd  mov     rax, [rax+28h]
0x1800f72d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f72d6  mov     ebx, eax
0x1800f72d8  test    eax, eax
0x1800f72da  jns     short loc_1800F7302
0x1800f72dc  mov     r9d, eax; char *
0x1800f72df  mov     edx, 3Fh ; '?'; void *
0x1800f72e4  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\lib\\crossvmapiacces"...
0x1800f72eb  mov     rcx, [rbp+1A8h]; this
0x1800f72f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f72f7  nop
0x1800f72f8  lea     rcx, [rsp+2A0h+pvar]
0x1800f72fd  jmp     loc_1800F7455
0x1800f7302  movzx   eax, word ptr [rsp+2A0h+pvar]
0x1800f7307  cmp     ax, 41h ; 'A'
0x1800f730b  jz      short loc_1800F7327
0x1800f730d  test    ax, ax
0x1800f7310  jz      short loc_1800F7321
0x1800f7312  mov     ebx, 80070057h
0x1800f7317  mov     r9d, ebx
0x1800f731a  mov     edx, 40h ; '@'
0x1800f731f  jmp     short loc_1800F72E4
0x1800f7321  cmp     ax, 41h ; 'A'
0x1800f7325  jnz     short loc_1800F7384
0x1800f7327  mov     rdx, [rsp+2A0h+var_250]
0x1800f732c  mov     rax, [rsp+2A0h+pvar+8]
0x1800f7331  cmp     eax, 1
0x1800f7334  jbe     short loc_1800F734A
0x1800f7336  cmp     byte ptr [rdx], 1
0x1800f7339  jz      short loc_1800F734A
0x1800f733b  mov     ebx, 80070057h
0x1800f7340  mov     r9d, ebx
0x1800f7343  mov     edx, 47h ; 'G'
0x1800f7348  jmp     short loc_1800F72E4
0x1800f734a  mov     ecx, 1
0x1800f734f  cmp     ecx, eax
0x1800f7351  jnb     short loc_1800F7384
0x1800f7353  mov     eax, ecx
0x1800f7355  cmp     byte ptr [rax+rdx], 1Ah
0x1800f7359  jnb     short loc_1800F7372
0x1800f735b  movzx   eax, byte ptr [rax+rdx]
0x1800f735f  mov     [rax+rdi+10h], r14b
0x1800f7364  inc     ecx
0x1800f7366  mov     rdx, [rsp+2A0h+var_250]
0x1800f736b  mov     rax, [rsp+2A0h+pvar+8]
0x1800f7370  jmp     short loc_1800F734F
0x1800f7372  mov     ebx, 80070057h
0x1800f7377  mov     r9d, ebx
0x1800f737a  mov     edx, 4Dh ; 'M'
0x1800f737f  jmp     loc_1800F72E4
0x1800f7384  lea     rcx, [rsp+2A0h+pvar]; pvar
0x1800f7389  call    cs:__imp_PropVariantClear
0x1800f738f  xorps   xmm0, xmm0
0x1800f7392  xor     eax, eax
0x1800f7394  movups  xmmword ptr [rsp+2A0h+var_248], xmm0
0x1800f7399  mov     [rsp+2A0h+var_238], rax
0x1800f739e  mov     rcx, [rsp+2A0h+var_270]
0x1800f73a3  mov     rax, [rcx]
0x1800f73a6  lea     r8, [rsp+2A0h+var_248]
0x1800f73ab  lea     rdx, PKEY_BlockedXvmAudioApis
0x1800f73b2  mov     rax, [rax+28h]
0x1800f73b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f73bb  mov     ebx, eax
0x1800f73bd  test    eax, eax
0x1800f73bf  jns     short loc_1800F73CB
0x1800f73c1  mov     r9d, eax
0x1800f73c4  mov     edx, 55h ; 'U'
0x1800f73c9  jmp     short loc_1800F743C
0x1800f73cb  movzx   eax, word ptr [rsp+2A0h+var_248]
0x1800f73d0  cmp     ax, 41h ; 'A'
0x1800f73d4  jz      short loc_1800F73EC
0x1800f73d6  test    ax, ax
0x1800f73d9  jz      short loc_1800F73E2
0x1800f73db  mov     edx, 56h ; 'V'
0x1800f73e0  jmp     short loc_1800F7434
0x1800f73e2  cmp     ax, 41h ; 'A'
0x1800f73e6  jnz     loc_1800F7475
0x1800f73ec  mov     rdx, [rsp+2A0h+var_238]
0x1800f73f1  mov     rax, [rsp+2A0h+var_248+8]
0x1800f73f6  cmp     eax, 1
0x1800f73f9  jbe     short loc_1800F7407
0x1800f73fb  cmp     byte ptr [rdx], 1
0x1800f73fe  jz      short loc_1800F7407
0x1800f7400  mov     edx, 5Dh ; ']'
0x1800f7405  jmp     short loc_1800F7434
0x1800f7407  mov     ecx, 1
0x1800f740c  cmp     ecx, eax
0x1800f740e  jnb     short loc_1800F7475
0x1800f7410  mov     eax, ecx
0x1800f7412  cmp     byte ptr [rax+rdx], 3
0x1800f7416  jnb     short loc_1800F742F
0x1800f7418  movzx   eax, byte ptr [rax+rdx]
0x1800f741c  mov     [rax+rdi+2Ah], r14b
0x1800f7421  inc     ecx
0x1800f7423  mov     rdx, [rsp+2A0h+var_238]
0x1800f7428  mov     rax, [rsp+2A0h+var_248+8]
0x1800f742d  jmp     short loc_1800F740C
0x1800f742f  mov     edx, 63h ; 'c'; void *
0x1800f7434  mov     ebx, 80070057h
0x1800f7439  mov     r9d, ebx; char *
0x1800f743c  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\lib\\crossvmapiacces"...
0x1800f7443  mov     rcx, [rbp+1A8h]; this
0x1800f744a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f744f  nop
0x1800f7450  lea     rcx, [rsp+2A0h+var_248]; pvar
0x1800f7455  call    cs:__imp_PropVariantClear
0x1800f745b  nop
0x1800f745c  lea     rcx, [rsp+2A0h+var_270]; void *
0x1800f7461  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800f7466  nop
0x1800f7467  lea     rcx, [rsp+2A0h+lpsz]
0x1800f746c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800f7471  mov     eax, ebx
0x1800f7473  jmp     short loc_1800F7498
0x1800f7475  lea     rcx, [rsp+2A0h+var_248]; pvar
0x1800f747a  call    cs:__imp_PropVariantClear
0x1800f7480  nop
0x1800f7481  lea     rcx, [rsp+2A0h+var_270]; void *
0x1800f7486  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800f748b  nop
0x1800f748c  lea     rcx, [rsp+2A0h+lpsz]
0x1800f7491  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800f7496  xor     eax, eax
0x1800f7498  mov     rcx, [rbp+1A0h+var_20]
0x1800f749f  xor     rcx, rsp; StackCookie
0x1800f74a2  call    __security_check_cookie
0x1800f74a7  mov     rbx, [rsp+2A0h+arg_10]
0x1800f74af  add     rsp, 290h
0x1800f74b6  pop     r14
0x1800f74b8  pop     rdi
0x1800f74b9  pop     rbp
0x1800f74ba  retn
```
