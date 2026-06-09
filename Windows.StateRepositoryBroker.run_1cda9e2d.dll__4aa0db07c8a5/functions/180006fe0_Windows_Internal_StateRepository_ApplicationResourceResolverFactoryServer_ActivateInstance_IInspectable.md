# Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer::ActivateInstance(IInspectable * *)

- ea: `0x180006fe0`
- end: `0x18000701d`
- name: `?ActivateInstance@ApplicationResourceResolverFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180006fe0`

## string_xrefs

- `0x180006fee`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolverfactory.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer::ActivateInstance(
        Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer *this,
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolverfactory.cpp",
      (const char *)0x80004003LL,
      v3);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180006fe0  sub     rsp, 28h
0x180006fe4  test    rdx, rdx
0x180006fe7  jnz     short loc_18000700C
0x180006fe9  mov     rcx, [rsp+28h]; this
0x180006fee  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x180006ff5  mov     r9d, 80004003h; char *
0x180006ffb  mov     edx, 10h; void *
0x180007000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007005  mov     eax, 80004003h
0x18000700a  jmp     short loc_180007018
0x18000700c  mov     qword ptr [rdx], 0
0x180007013  mov     eax, 80004001h
0x180007018  add     rsp, 28h
0x18000701c  retn
```
