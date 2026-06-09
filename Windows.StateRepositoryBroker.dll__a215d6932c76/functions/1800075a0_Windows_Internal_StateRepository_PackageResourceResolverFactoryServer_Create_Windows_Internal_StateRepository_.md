# Windows::Internal::StateRepository::PackageResourceResolverFactoryServer::Create(Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IPackageResourceResolver * *)

- ea: `0x1800075a0`
- end: `0x180007655`
- name: `?Create@PackageResourceResolverFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUIPackage@234@PEAPEAUIPackageResourceResolver@234@@Z`
- size: `181`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PackageResourceResolverFactoryServer *this, struct Windows::Internal::StateRepository::IPackage *, struct Windows::Internal::StateRepository::IPackageResourceResolver **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800071a4`
- `0x180007370`
- `0x1800075a0`

## string_xrefs

- `0x1800075c1`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolverfactory.cpp`
- `0x180007615`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolverfactory.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverFactoryServer::Create(
        Windows::Internal::StateRepository::PackageResourceResolverFactoryServer *this,
        struct Windows::Internal::StateRepository::IPackage *a2,
        struct Windows::Internal::StateRepository::IPackageResourceResolver **a3)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct Windows::Internal::StateRepository::IPackage *v10; // [rsp+38h] [rbp+10h] BYREF
  struct Windows::Internal::StateRepository::IPackageResourceResolver *v11; // [rsp+48h] [rbp+20h] BYREF

  v10 = a2;
  if ( !a2 )
  {
    v4 = 28;
LABEL_3:
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolverfactory.cpp",
      (const char *)0x80004003LL,
      v8);
    return v5;
  }
  if ( !a3 )
  {
    v4 = 29;
    goto LABEL_3;
  }
  *a3 = 0;
  v11 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v11);
  v6 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::PackageResourceResolverServer,Windows::Internal::StateRepository::IPackageResourceResolver,Windows::Internal::StateRepository::IPackage * &>(
         &v11,
         &v10);
  v5 = v6;
  if ( v6 >= 0 )
  {
    v5 = 0;
    *a3 = v11;
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolverfactory.cpp",
      (const char *)(unsigned int)v6,
      v8);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v11);
  return v5;
}

```

## disassembly

```asm
0x1800075a0  mov     [rsp+arg_0], rbx
0x1800075a5  mov     [rsp+arg_8], rdx
0x1800075aa  push    rdi; int
0x1800075ab  sub     rsp, 20h
0x1800075af  mov     rdi, r8
0x1800075b2  test    rdx, rdx
0x1800075b5  jnz     short loc_1800075D7
0x1800075b7  mov     edx, 1Ch; void *
0x1800075bc  mov     rcx, [rsp+28h]; this
0x1800075c1  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x1800075c8  mov     ebx, 80004003h
0x1800075cd  mov     r9d, ebx; char *
0x1800075d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075d5  jmp     short loc_180007648
0x1800075d7  test    rdi, rdi
0x1800075da  jnz     short loc_1800075E1
0x1800075dc  lea     edx, [rdi+1Dh]
0x1800075df  jmp     short loc_1800075BC
0x1800075e1  lea     rcx, [rsp+28h+arg_18]
0x1800075e6  mov     qword ptr [r8], 0
0x1800075ed  mov     [rsp+28h+arg_18], 0
0x1800075f6  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x1800075fb  lea     rdx, [rsp+28h+arg_8]
0x180007600  lea     rcx, [rsp+28h+arg_18]
0x180007605  call    ??$MakeAndInitialize@VPackageResourceResolverServer@StateRepository@Internal@Windows@@UIPackageResourceResolver@234@AEAPEAUIPackage@234@@Details@WRL@Microsoft@@YAJPEAPEAUIPackageResourceResolver@StateRepository@Internal@Windows@@AEAPEAUIPackage@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::PackageResourceResolverServer,Windows::Internal::StateRepository::IPackageResourceResolver,Windows::Internal::StateRepository::IPackage * &>(Windows::Internal::StateRepository::IPackageResourceResolver * *,Windows::Internal::StateRepository::IPackage * &)
0x18000760a  mov     ebx, eax
0x18000760c  test    eax, eax
0x18000760e  jns     short loc_18000762B
0x180007610  mov     rcx, [rsp+28h]; this
0x180007615  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18000761c  mov     r9d, eax; char *
0x18000761f  mov     edx, 22h ; '"'; void *
0x180007624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007629  jmp     short loc_18000763E
0x18000762b  mov     rax, [rsp+28h+arg_18]
0x180007630  xor     ebx, ebx
0x180007632  mov     [rdi], rax
0x180007635  mov     [rsp+28h+arg_18], 0
0x18000763e  lea     rcx, [rsp+28h+arg_18]
0x180007643  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007648  mov     eax, ebx
0x18000764a  mov     rbx, [rsp+28h+arg_0]
0x18000764f  add     rsp, 20h
0x180007653  pop     rdi
0x180007654  retn
```
