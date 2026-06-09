# Windows::Internal::StateRepository::PackageResourceResolverServer::GetLogoLocalizedAsUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x1800091f0`
- end: `0x180009242`
- name: `?GetLogoLocalizedAsUri@PackageResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, struct Windows::Foundation::IUriRuntimeClass **, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800091f0`
- `0x180009f04`

## string_xrefs

- `0x18000920a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::GetLogoLocalizedAsUri(
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
    v4 = 84;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolver.cpp",
      (const char *)(unsigned int)MrtUri,
      v6);
    return (unsigned int)MrtUri;
  }
  *a2 = 0;
  MrtUri = StateRepository::Localization::CreateMrtUri(this[11], (const unsigned __int16 *)a2, a3);
  if ( MrtUri < 0 )
  {
    v4 = 88;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800091f0  push    rbx; int
0x1800091f2  sub     rsp, 20h
0x1800091f6  test    rdx, rdx
0x1800091f9  jnz     short loc_18000921D
0x1800091fb  mov     ebx, 80004003h
0x180009200  mov     edx, 54h ; 'T'; void *
0x180009205  mov     rcx, [rsp+28h]; this
0x18000920a  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180009211  mov     r9d, ebx; char *
0x180009214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009219  mov     eax, ebx
0x18000921b  jmp     short loc_18000923C
0x18000921d  mov     qword ptr [rdx], 0
0x180009224  mov     rcx, [rcx+58h]; this
0x180009228  call    ?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x18000922d  mov     ebx, eax
0x18000922f  test    eax, eax
0x180009231  jns     short loc_18000923A
0x180009233  mov     edx, 58h ; 'X'
0x180009238  jmp     short loc_180009205
0x18000923a  xor     eax, eax
0x18000923c  add     rsp, 20h
0x180009240  pop     rbx
0x180009241  retn
```
