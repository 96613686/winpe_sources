# LocationCallerInfoHelper::PackageFullNameToCSid(ushort const *,ATL::CSid &)

- ea: `0x180119ff0`
- end: `0x18011a0fc`
- name: `?PackageFullNameToCSid@LocationCallerInfoHelper@@SAJPEBGAEAVCSid@ATL@@@Z`
- size: `268`
- prototype: `static int(const unsigned __int16 *, struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180119d40`

## callees

- `0x18001e858`
- `0x18001eb88`
- `0x18009c310`
- `0x1800a98c0`
- `0x180119ff0`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18011a051`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18011a051`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18011a02d`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18011a02d`

## string_xrefs

- `0x18011a07c`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\locationCallerInfoHelper.h`
- `0x18011a05d`: `AppContainerDeriveSidFromMoniker(familyName, &packageSid)`
- `0x18011a0ac`: `!(wil::verify_bool(SidAppContainer.LoadAccount(static_cast<const SID*>(packageSid))))`
- `0x18011a071`: `LocationCallerInfoHelper::PackageFullNameToCSid`
- `0x18011a0cb`: `!(wil::verify_bool(SidAppContainer.IsValid()))`

## pseudocode

```c
__int64 __fastcall LocationCallerInfoHelper::PackageFullNameToCSid(const unsigned __int16 *a1, struct ATL::CSid *a2)
{
  LONG v3; // eax
  bool v4; // sf
  int v5; // ebx
  const unsigned __int16 *v6; // r8
  const char *v7; // rax
  __int64 v8; // rdx
  wil::details *v10; // [rsp+28h] [rbp-C0h]
  struct _SID *v11; // [rsp+30h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+38h] [rbp-B0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-A8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+0h]

  packageFamilyNameLength = 65;
  v11 = 0;
  v3 = PackageFamilyNameFromFullName(a1, &packageFamilyNameLength, packageFamilyName);
  v4 = v3 < 0;
  if ( v3 > 0 )
    v4 = 1;
  if ( !v4 )
  {
    v5 = AppContainerDeriveSidFromMoniker(packageFamilyName, &v11);
    if ( v5 < 0 )
    {
      v7 = "AppContainerDeriveSidFromMoniker(familyName, &packageSid)";
      v8 = 797;
LABEL_6:
      LODWORD(v10) = v5;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\locationCallerInfoHelper.h",
        "LocationCallerInfoHelper::PackageFullNameToCSid",
        v7,
        v10,
        (int)v11);
      return (unsigned int)v5;
    }
    if ( v11 )
    {
      if ( !ATL::CSid::LoadAccount(a2, v11, v6) )
      {
        v5 = -2147023559;
        v7 = "!(wil::verify_bool(SidAppContainer.LoadAccount(static_cast<const SID*>(packageSid))))";
        v8 = 802;
        goto LABEL_6;
      }
      if ( !ATL::CSid::IsValid(a2) )
      {
        v5 = -2147023559;
        v7 = "!(wil::verify_bool(SidAppContainer.IsValid()))";
        v8 = 803;
        goto LABEL_6;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180119ff0  mov     [rsp+arg_10], rbx
0x180119ff5  push    rdi
0x180119ff6  sub     rsp, 0E0h
0x180119ffd  mov     rax, cs:__security_cookie
0x18011a004  xor     rax, rsp
0x18011a007  mov     [rsp+0E8h+var_18], rax
0x18011a00f  mov     rdi, rdx
0x18011a012  mov     [rsp+0E8h+packageFamilyNameLength], 41h ; 'A'
0x18011a01a  lea     rdx, [rsp+0E8h+packageFamilyNameLength]; packageFamilyNameLength
0x18011a01f  mov     [rsp+0E8h+var_B8], 0; int
0x18011a028  lea     r8, [rsp+0E8h+packageFamilyName]; packageFamilyName
0x18011a02d  call    cs:__imp_PackageFamilyNameFromFullName
0x18011a033  test    eax, eax
0x18011a035  jle     short loc_18011A041
0x18011a037  movzx   eax, ax
0x18011a03a  or      eax, 80070000h
0x18011a03f  test    eax, eax
0x18011a041  js      loc_18011A0D9
0x18011a047  lea     rdx, [rsp+0E8h+var_B8]
0x18011a04c  lea     rcx, [rsp+0E8h+packageFamilyName]
0x18011a051  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18011a057  mov     ebx, eax
0x18011a059  test    eax, eax
0x18011a05b  jns     short loc_18011A091
0x18011a05d  lea     rax, aAppcontainerde_0; "AppContainerDeriveSidFromMoniker(family"...
0x18011a064  mov     edx, 31Dh; void *
0x18011a069  mov     rcx, [rsp+0E8h]; this
0x18011a071  lea     r9, aLocationcaller_5; "LocationCallerInfoHelper::PackageFullNa"...
0x18011a078  mov     dword ptr [rsp+0E8h+var_C0], ebx; wil::details *
0x18011a07c  lea     r8, aOnecoreuapDriv_91; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18011a083  mov     [rsp+0E8h+var_C8], rax; char *
0x18011a088  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18011a08d  mov     eax, ebx
0x18011a08f  jmp     short loc_18011A0DB
0x18011a091  mov     rdx, [rsp+0E8h+var_B8]; struct _SID *
0x18011a096  test    rdx, rdx
0x18011a099  jz      short loc_18011A0D9
0x18011a09b  mov     rcx, rdi; this
0x18011a09e  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x18011a0a3  test    al, al
0x18011a0a5  jnz     short loc_18011A0BA
0x18011a0a7  mov     ebx, 80070539h
0x18011a0ac  lea     rax, aWilVerifyBoolS_3; "!(wil::verify_bool(SidAppContainer.Load"...
0x18011a0b3  mov     edx, 322h
0x18011a0b8  jmp     short loc_18011A069
0x18011a0ba  mov     rcx, rdi; this
0x18011a0bd  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18011a0c2  test    al, al
0x18011a0c4  jnz     short loc_18011A0D9
0x18011a0c6  mov     ebx, 80070539h
0x18011a0cb  lea     rax, aWilVerifyBoolS_4; "!(wil::verify_bool(SidAppContainer.IsVa"...
0x18011a0d2  mov     edx, 323h
0x18011a0d7  jmp     short loc_18011A069
0x18011a0d9  xor     eax, eax
0x18011a0db  mov     rcx, [rsp+0E8h+var_18]
0x18011a0e3  xor     rcx, rsp; StackCookie
0x18011a0e6  call    __security_check_cookie
0x18011a0eb  mov     rbx, [rsp+0E8h+arg_10]
0x18011a0f3  add     rsp, 0E0h
0x18011a0fa  pop     rdi
0x18011a0fb  retn
```
