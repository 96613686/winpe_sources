# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare44x44LogoLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180008810`
- end: `0x180008862`
- name: `?GetSquare44x44LogoLocalizedAsUri@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, struct Windows::Foundation::IUriRuntimeClass **, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008810`
- `0x180009f04`

## string_xrefs

- `0x18000882a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare44x44LogoLocalizedAsUri(
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
    v4 = 125;
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
  MrtUri = StateRepository::Localization::CreateMrtUri(this[11], (const unsigned __int16 *)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 129;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008810  push    rbx; int
0x180008812  sub     rsp, 20h
0x180008816  test    rdx, rdx
0x180008819  jnz     short loc_18000883D
0x18000881b  mov     ebx, 80004003h
0x180008820  mov     edx, 7Dh ; '}'; void *
0x180008825  mov     rcx, [rsp+28h]; this
0x18000882a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008831  mov     r9d, ebx; char *
0x180008834  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008839  mov     eax, ebx
0x18000883b  jmp     short loc_18000885C
0x18000883d  mov     qword ptr [rdx], 0
0x180008844  mov     rcx, [rcx+58h]; this
0x180008848  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x18000884d  mov     ebx, eax
0x18000884f  test    eax, eax
0x180008851  jns     short loc_18000885A
0x180008853  mov     edx, 81h
0x180008858  jmp     short loc_180008825
0x18000885a  xor     eax, eax
0x18000885c  add     rsp, 20h
0x180008860  pop     rbx
0x180008861  retn
```
