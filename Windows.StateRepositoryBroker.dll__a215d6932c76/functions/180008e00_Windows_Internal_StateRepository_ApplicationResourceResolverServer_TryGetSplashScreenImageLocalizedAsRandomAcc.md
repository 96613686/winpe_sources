# Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSplashScreenImageLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008e00`
- end: `0x180008e52`
- name: `?TryGetSplashScreenImageLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008e00`
- `0x18000a510`

## string_xrefs

- `0x180008e1a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSplashScreenImageLocalizedAsRandomAccessStreamReference(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int MrtRandomAccessStreamReference; // ebx
  __int64 v4; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 )
  {
    MrtRandomAccessStreamReference = -2147467261;
    v4 = 339;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.applicationres"
           "ourceresolver.cpp",
      (const char *)(unsigned int)MrtRandomAccessStreamReference);
    return (unsigned int)MrtRandomAccessStreamReference;
  }
  *a3 = 0;
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(
                                     *(HSTRING *)(a1 + 120),
                                     a2,
                                     a3);
  if ( MrtRandomAccessStreamReference < 0 )
  {
    v4 = 343;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008e00  push    rbx; int
0x180008e02  sub     rsp, 20h
0x180008e06  test    r8, r8
0x180008e09  jnz     short loc_180008E2D
0x180008e0b  mov     ebx, 80004003h
0x180008e10  mov     edx, 153h; void *
0x180008e15  mov     rcx, [rsp+28h]; this
0x180008e1a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008e21  mov     r9d, ebx; char *
0x180008e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e29  mov     eax, ebx
0x180008e2b  jmp     short loc_180008E4C
0x180008e2d  mov     qword ptr [r8], 0
0x180008e34  mov     rcx, [rcx+78h]
0x180008e38  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008e3d  mov     ebx, eax
0x180008e3f  test    eax, eax
0x180008e41  jns     short loc_180008E4A
0x180008e43  mov     edx, 157h
0x180008e48  jmp     short loc_180008E15
0x180008e4a  xor     eax, eax
0x180008e4c  add     rsp, 20h
0x180008e50  pop     rbx
0x180008e51  retn
```
