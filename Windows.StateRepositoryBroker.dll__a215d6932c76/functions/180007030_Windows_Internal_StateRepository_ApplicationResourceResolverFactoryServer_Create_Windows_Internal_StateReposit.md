# Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer::Create(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolver * *)

- ea: `0x180007030`
- end: `0x1800070e5`
- name: `?Create@ApplicationResourceResolverFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUIApplication@234@PEAPEAUIApplicationResourceResolver@234@@Z`
- size: `181`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer *this, struct Windows::Internal::StateRepository::IApplication *, struct Windows::Internal::StateRepository::IApplicationResourceResolver **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180006d10`
- `0x180007030`
- `0x1800071a4`

## string_xrefs

- `0x180007051`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolverfactory.cpp`
- `0x1800070a5`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolverfactory.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer::Create(
        Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer *this,
        struct Windows::Internal::StateRepository::IApplication *a2,
        struct Windows::Internal::StateRepository::IApplicationResourceResolver **a3)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct Windows::Internal::StateRepository::IApplication *v10; // [rsp+38h] [rbp+10h] BYREF
  struct Windows::Internal::StateRepository::IApplicationResourceResolver *v11; // [rsp+48h] [rbp+20h] BYREF

  v10 = a2;
  if ( !a2 )
  {
    v4 = 28;
LABEL_3:
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolverfactory.cpp",
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
  v6 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::ApplicationResourceResolverServer,Windows::Internal::StateRepository::IApplicationResourceResolver,Windows::Internal::StateRepository::IApplication * &>(
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolverfactory.cpp",
      (const char *)(unsigned int)v6,
      v8);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v11);
  return v5;
}

```

## disassembly

```asm
0x180007030  mov     [rsp+arg_0], rbx
0x180007035  mov     [rsp+arg_8], rdx
0x18000703a  push    rdi; int
0x18000703b  sub     rsp, 20h
0x18000703f  mov     rdi, r8
0x180007042  test    rdx, rdx
0x180007045  jnz     short loc_180007067
0x180007047  mov     edx, 1Ch; void *
0x18000704c  mov     rcx, [rsp+28h]; this
0x180007051  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x180007058  mov     ebx, 80004003h
0x18000705d  mov     r9d, ebx; char *
0x180007060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007065  jmp     short loc_1800070D8
0x180007067  test    rdi, rdi
0x18000706a  jnz     short loc_180007071
0x18000706c  lea     edx, [rdi+1Dh]
0x18000706f  jmp     short loc_18000704C
0x180007071  lea     rcx, [rsp+28h+arg_18]
0x180007076  mov     qword ptr [r8], 0
0x18000707d  mov     [rsp+28h+arg_18], 0
0x180007086  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000708b  lea     rdx, [rsp+28h+arg_8]
0x180007090  lea     rcx, [rsp+28h+arg_18]
0x180007095  call    ??$MakeAndInitialize@VApplicationResourceResolverServer@StateRepository@Internal@Windows@@UIApplicationResourceResolver@234@AEAPEAUIApplication@234@@Details@WRL@Microsoft@@YAJPEAPEAUIApplicationResourceResolver@StateRepository@Internal@Windows@@AEAPEAUIApplication@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::ApplicationResourceResolverServer,Windows::Internal::StateRepository::IApplicationResourceResolver,Windows::Internal::StateRepository::IApplication * &>(Windows::Internal::StateRepository::IApplicationResourceResolver * *,Windows::Internal::StateRepository::IApplication * &)
0x18000709a  mov     ebx, eax
0x18000709c  test    eax, eax
0x18000709e  jns     short loc_1800070BB
0x1800070a0  mov     rcx, [rsp+28h]; this
0x1800070a5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x1800070ac  mov     r9d, eax; char *
0x1800070af  mov     edx, 22h ; '"'; void *
0x1800070b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070b9  jmp     short loc_1800070CE
0x1800070bb  mov     rax, [rsp+28h+arg_18]
0x1800070c0  xor     ebx, ebx
0x1800070c2  mov     [rdi], rax
0x1800070c5  mov     [rsp+28h+arg_18], 0
0x1800070ce  lea     rcx, [rsp+28h+arg_18]
0x1800070d3  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x1800070d8  mov     eax, ebx
0x1800070da  mov     rbx, [rsp+28h+arg_0]
0x1800070df  add     rsp, 20h
0x1800070e3  pop     rdi
0x1800070e4  retn
```
