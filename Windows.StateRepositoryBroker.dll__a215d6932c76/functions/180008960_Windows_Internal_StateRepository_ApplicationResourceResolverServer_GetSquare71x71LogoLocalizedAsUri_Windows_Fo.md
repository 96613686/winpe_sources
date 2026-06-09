# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare71x71LogoLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180008960`
- end: `0x1800089b2`
- name: `?GetSquare71x71LogoLocalizedAsUri@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, struct Windows::Foundation::IUriRuntimeClass **, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008960`
- `0x180009f04`

## string_xrefs

- `0x18000897a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare71x71LogoLocalizedAsUri(
        StateRepository::Localization **this,
        struct Windows::Foundation::IUriRuntimeClass **a2,
        struct Windows::Foundation::IUriRuntimeClass **a3)
{
  int MrtUri; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    MrtUri = -2147467261;
    v4 = 267;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)(unsigned int)MrtUri,
      v6);
    return (unsigned int)MrtUri;
  }
  *a2 = 0;
  MrtUri = StateRepository::Localization::CreateMrtUri(this[14], (const unsigned __int16 *)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 271;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008960  push    rbx; int
0x180008962  sub     rsp, 20h
0x180008966  test    rdx, rdx
0x180008969  jnz     short loc_18000898D
0x18000896b  mov     ebx, 80004003h
0x180008970  mov     edx, 10Bh; void *
0x180008975  mov     rcx, [rsp+28h]; this
0x18000897a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008981  mov     r9d, ebx; char *
0x180008984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008989  mov     eax, ebx
0x18000898b  jmp     short loc_1800089AC
0x18000898d  mov     qword ptr [rdx], 0
0x180008994  mov     rcx, [rcx+70h]; this
0x180008998  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x18000899d  mov     ebx, eax
0x18000899f  test    eax, eax
0x1800089a1  jns     short loc_1800089AA
0x1800089a3  mov     edx, 10Fh
0x1800089a8  jmp     short loc_180008975
0x1800089aa  xor     eax, eax
0x1800089ac  add     rsp, 20h
0x1800089b0  pop     rbx
0x1800089b1  retn
```
