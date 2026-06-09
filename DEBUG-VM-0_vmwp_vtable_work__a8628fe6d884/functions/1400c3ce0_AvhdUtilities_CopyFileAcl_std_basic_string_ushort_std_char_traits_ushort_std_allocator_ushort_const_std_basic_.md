# AvhdUtilities::CopyFileAcl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400c3ce0`
- end: `0x1400c3e24`
- name: `?CopyFileAcl@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `324`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140083da0`

## callees

- `0x1400c3ce0`
- `0x1400c3e2c`
- `0x140132940`
- `0x1401bbeec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3df5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400c3df5`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1400c3d5b`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1400c3d5b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1400c3dd0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1400c3dd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AvhdUtilities::CopyFileAcl(LPWSTR *pObjectName, const WCHAR *a2)
{
  const WCHAR *v2; // rax
  LPWSTR *v3; // r14
  LPWSTR v4; // rsi
  signed int NamedSecurityInfoW; // eax
  signed int v6; // ebx
  const char *v7; // r9
  struct _ACL *Dacl; // rax
  signed int v9; // eax
  int v11; // [rsp+40h] [rbp-38h]
  PSECURITY_DESCRIPTOR hMem[2]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = a2;
  v3 = pObjectName;
  v4 = (LPWSTR)pObjectName;
  *(_OWORD *)hMem = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const WCHAR **)a2;
  NamedSecurityInfoW = GetNamedSecurityInfoW(v2, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, hMem);
  v6 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v6 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v6 >= 0 )
  {
    try
    {
      Vml::VmSecurityDescriptor::MakeSelfRelative((Vml::VmSecurityDescriptor *)hMem);
    }
    catch ( ... )
    {
      v11 = wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x21F,
              (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
              v7);
      v6 = v11;
      if ( v11 < 0 )
        goto LABEL_13;
      v4 = (LPWSTR)pObjectName;
      v3 = pObjectName;
    }
    Dacl = (struct _ACL *)Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)hMem);
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *v3;
    v9 = SetNamedSecurityInfoW(v4, SE_FILE_OBJECT, 4u, 0, 0, Dacl, 0);
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
  }
LABEL_13:
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400c3ce0  mov     [rsp+arg_10], rbx
0x1400c3ce5  mov     [rsp+arg_18], rsi
0x1400c3cea  push    r14
0x1400c3cec  sub     rsp, 70h
0x1400c3cf0  mov     rax, cs:__security_cookie
0x1400c3cf7  xor     rax, rsp
0x1400c3cfa  mov     [rsp+78h+var_10], rax
0x1400c3cff  mov     rax, rdx
0x1400c3d02  mov     r14, rcx
0x1400c3d05  mov     rsi, rcx
0x1400c3d08  mov     [rsp+78h+var_30], rcx
0x1400c3d0d  xorps   xmm0, xmm0
0x1400c3d10  movups  xmmword ptr [rsp+78h+hMem], xmm0
0x1400c3d15  mov     [rsp+78h+hMem], 0
0x1400c3d1e  cmp     qword ptr [rdx+18h], 7
0x1400c3d23  jbe     short loc_1400C3D28
0x1400c3d25  mov     rax, [rdx]
0x1400c3d28  lea     rcx, [rsp+78h+hMem]
0x1400c3d2d  mov     [rsp+78h+ppSecurityDescriptor], rcx; ppSecurityDescriptor
0x1400c3d32  mov     [rsp+78h+ppSacl], 0; ppSacl
0x1400c3d3b  mov     [rsp+78h+ppDacl], 0; ppDacl
0x1400c3d44  mov     [rsp+78h+ppsidGroup], 0; ppsidGroup
0x1400c3d4d  xor     r9d, r9d; ppsidOwner
0x1400c3d50  lea     edx, [r9+1]; ObjectType
0x1400c3d54  lea     r8d, [r9+4]; SecurityInfo
0x1400c3d58  mov     rcx, rax; pObjectName
0x1400c3d5b  call    cs:__imp_GetNamedSecurityInfoW
0x1400c3d62  nop     dword ptr [rax+rax+00h]
0x1400c3d67  mov     ebx, eax
0x1400c3d69  test    eax, eax
0x1400c3d6b  jle     short loc_1400C3D76
0x1400c3d6d  movzx   ebx, ax
0x1400c3d70  or      ebx, 80070000h
0x1400c3d76  test    ebx, ebx
0x1400c3d78  js      short loc_1400C3DEB
0x1400c3d7a  lea     rcx, [rsp+78h+hMem]; this
0x1400c3d7f  call    ?MakeSelfRelative@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeSelfRelative(void)
0x1400c3d84  nop
0x1400c3d85  jmp     short loc_1400C3D97
0x1400c3d87  mov     ebx, [rsp+78h+var_38]
0x1400c3d8b  test    ebx, ebx
0x1400c3d8d  js      short loc_1400C3DEB
0x1400c3d8f  mov     rsi, [rsp+78h+var_30]
0x1400c3d94  mov     r14, rsi
0x1400c3d97  lea     rcx, [rsp+78h+hMem]; this
0x1400c3d9c  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400c3da1  cmp     qword ptr [rsi+18h], 7
0x1400c3da6  jbe     short loc_1400C3DAB
0x1400c3da8  mov     rsi, [r14]
0x1400c3dab  mov     [rsp+78h+ppSacl], 0; pSacl
0x1400c3db4  mov     [rsp+78h+ppDacl], rax; pDacl
0x1400c3db9  mov     [rsp+78h+ppsidGroup], 0; psidGroup
0x1400c3dc2  xor     r9d, r9d; psidOwner
0x1400c3dc5  lea     edx, [r9+1]; ObjectType
0x1400c3dc9  lea     r8d, [r9+4]; SecurityInfo
0x1400c3dcd  mov     rcx, rsi; pObjectName
0x1400c3dd0  call    cs:__imp_SetNamedSecurityInfoW
0x1400c3dd7  nop     dword ptr [rax+rax+00h]
0x1400c3ddc  mov     ebx, eax
0x1400c3dde  test    eax, eax
0x1400c3de0  jle     short loc_1400C3DEB
0x1400c3de2  movzx   ebx, ax
0x1400c3de5  or      ebx, 80070000h
0x1400c3deb  mov     rcx, [rsp+78h+hMem]; hMem
0x1400c3df0  test    rcx, rcx
0x1400c3df3  jz      short loc_1400C3E01
0x1400c3df5  call    cs:__imp_LocalFree
0x1400c3dfc  nop     dword ptr [rax+rax+00h]
0x1400c3e01  mov     eax, ebx
0x1400c3e03  mov     rcx, [rsp+78h+var_10]
0x1400c3e08  xor     rcx, rsp; StackCookie
0x1400c3e0b  call    __security_check_cookie
0x1400c3e10  lea     r11, [rsp+78h+var_8]
0x1400c3e15  mov     rbx, [r11+20h]
0x1400c3e19  mov     rsi, [r11+28h]
0x1400c3e1d  mov     rsp, r11
0x1400c3e20  pop     r14
0x1400c3e22  retn
```
