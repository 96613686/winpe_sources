# Windows::Internal::StateRepository::PackageResourceResolverFactoryServer::ActivateInstance(IInspectable * *)

- ea: `0x180007550`
- end: `0x18000758d`
- name: `?ActivateInstance@PackageResourceResolverFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PackageResourceResolverFactoryServer *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180007550`

## string_xrefs

- `0x18000755e`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolverfactory.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverFactoryServer::ActivateInstance(
        Windows::Internal::StateRepository::PackageResourceResolverFactoryServer *this,
        struct IInspectable **a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    return 2147500033LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolverfactory.cpp",
      (const char *)0x80004003LL,
      v3);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180007550  sub     rsp, 28h
0x180007554  test    rdx, rdx
0x180007557  jnz     short loc_18000757C
0x180007559  mov     rcx, [rsp+28h]; this
0x18000755e  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180007565  mov     r9d, 80004003h; char *
0x18000756b  mov     edx, 10h; void *
0x180007570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007575  mov     eax, 80004003h
0x18000757a  jmp     short loc_180007588
0x18000757c  mov     qword ptr [rdx], 0
0x180007583  mov     eax, 80004001h
0x180007588  add     rsp, 28h
0x18000758c  retn
```
