# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare310x310LogoLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x1800086c0`
- end: `0x180008712`
- name: `?GetSquare310x310LogoLocalizedAsUri@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800086c0`
- `0x180009f04`

## string_xrefs

- `0x1800086da`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare310x310LogoLocalizedAsUri(
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
    v4 = 220;
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
  MrtUri = StateRepository::Localization::CreateMrtUri(this[13], (HSTRING)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 224;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800086c0  push    rbx; int
0x1800086c2  sub     rsp, 20h
0x1800086c6  test    rdx, rdx
0x1800086c9  jnz     short loc_1800086ED
0x1800086cb  mov     ebx, 80004003h
0x1800086d0  mov     edx, 0DCh; void *
0x1800086d5  mov     rcx, [rsp+28h]; this
0x1800086da  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800086e1  mov     r9d, ebx; char *
0x1800086e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086e9  mov     eax, ebx
0x1800086eb  jmp     short loc_18000870C
0x1800086ed  mov     qword ptr [rdx], 0
0x1800086f4  mov     rcx, [rcx+68h]; this
0x1800086f8  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x1800086fd  mov     ebx, eax
0x1800086ff  test    eax, eax
0x180008701  jns     short loc_18000870A
0x180008703  mov     edx, 0E0h
0x180008708  jmp     short loc_1800086D5
0x18000870a  xor     eax, eax
0x18000870c  add     rsp, 20h
0x180008710  pop     rbx
0x180008711  retn
```
