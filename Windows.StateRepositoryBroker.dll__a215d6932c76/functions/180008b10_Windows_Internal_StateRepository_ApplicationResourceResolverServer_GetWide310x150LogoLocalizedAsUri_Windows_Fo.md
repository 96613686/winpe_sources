# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetWide310x150LogoLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180008b10`
- end: `0x180008b62`
- name: `?GetWide310x150LogoLocalizedAsUri@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, struct Windows::Foundation::IUriRuntimeClass **, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008b10`
- `0x180009f04`

## string_xrefs

- `0x180008b2a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetWide310x150LogoLocalizedAsUri(
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
    v4 = 172;
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
  MrtUri = StateRepository::Localization::CreateMrtUri(this[12], (const unsigned __int16 *)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 176;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008b10  push    rbx; int
0x180008b12  sub     rsp, 20h
0x180008b16  test    rdx, rdx
0x180008b19  jnz     short loc_180008B3D
0x180008b1b  mov     ebx, 80004003h
0x180008b20  mov     edx, 0ACh; void *
0x180008b25  mov     rcx, [rsp+28h]; this
0x180008b2a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008b31  mov     r9d, ebx; char *
0x180008b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b39  mov     eax, ebx
0x180008b3b  jmp     short loc_180008B5C
0x180008b3d  mov     qword ptr [rdx], 0
0x180008b44  mov     rcx, [rcx+60h]; this
0x180008b48  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x180008b4d  mov     ebx, eax
0x180008b4f  test    eax, eax
0x180008b51  jns     short loc_180008B5A
0x180008b53  mov     edx, 0B0h
0x180008b58  jmp     short loc_180008B25
0x180008b5a  xor     eax, eax
0x180008b5c  add     rsp, 20h
0x180008b60  pop     rbx
0x180008b61  retn
```
