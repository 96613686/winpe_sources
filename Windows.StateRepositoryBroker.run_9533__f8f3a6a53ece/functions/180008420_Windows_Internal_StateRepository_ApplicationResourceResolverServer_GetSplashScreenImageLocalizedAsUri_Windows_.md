# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSplashScreenImageLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180008420`
- end: `0x180008472`
- name: `?GetSplashScreenImageLocalizedAsUri@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008420`
- `0x180009f04`

## string_xrefs

- `0x18000843a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSplashScreenImageLocalizedAsUri(
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
    v4 = 314;
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
  MrtUri = StateRepository::Localization::CreateMrtUri(this[15], (HSTRING)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 318;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008420  push    rbx; int
0x180008422  sub     rsp, 20h
0x180008426  test    rdx, rdx
0x180008429  jnz     short loc_18000844D
0x18000842b  mov     ebx, 80004003h
0x180008430  mov     edx, 13Ah; void *
0x180008435  mov     rcx, [rsp+28h]; this
0x18000843a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008441  mov     r9d, ebx; char *
0x180008444  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008449  mov     eax, ebx
0x18000844b  jmp     short loc_18000846C
0x18000844d  mov     qword ptr [rdx], 0
0x180008454  mov     rcx, [rcx+78h]; this
0x180008458  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x18000845d  mov     ebx, eax
0x18000845f  test    eax, eax
0x180008461  jns     short loc_18000846A
0x180008463  mov     edx, 13Eh
0x180008468  jmp     short loc_180008435
0x18000846a  xor     eax, eax
0x18000846c  add     rsp, 20h
0x180008470  pop     rbx
0x180008471  retn
```
