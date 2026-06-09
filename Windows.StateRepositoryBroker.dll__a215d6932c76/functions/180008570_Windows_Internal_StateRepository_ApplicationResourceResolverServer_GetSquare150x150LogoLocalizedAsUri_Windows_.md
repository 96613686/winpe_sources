# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare150x150LogoLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180008570`
- end: `0x1800085c2`
- name: `?GetSquare150x150LogoLocalizedAsUri@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, struct Windows::Foundation::IUriRuntimeClass **, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008570`
- `0x180009f04`

## string_xrefs

- `0x18000858a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare150x150LogoLocalizedAsUri(
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
    v4 = 78;
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
  MrtUri = StateRepository::Localization::CreateMrtUri(this[10], (const unsigned __int16 *)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 82;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008570  push    rbx; int
0x180008572  sub     rsp, 20h
0x180008576  test    rdx, rdx
0x180008579  jnz     short loc_18000859D
0x18000857b  mov     ebx, 80004003h
0x180008580  mov     edx, 4Eh ; 'N'; void *
0x180008585  mov     rcx, [rsp+28h]; this
0x18000858a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008591  mov     r9d, ebx; char *
0x180008594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008599  mov     eax, ebx
0x18000859b  jmp     short loc_1800085BC
0x18000859d  mov     qword ptr [rdx], 0
0x1800085a4  mov     rcx, [rcx+50h]; this
0x1800085a8  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x1800085ad  mov     ebx, eax
0x1800085af  test    eax, eax
0x1800085b1  jns     short loc_1800085BA
0x1800085b3  mov     edx, 52h ; 'R'
0x1800085b8  jmp     short loc_180008585
0x1800085ba  xor     eax, eax
0x1800085bc  add     rsp, 20h
0x1800085c0  pop     rbx
0x1800085c1  retn
```
