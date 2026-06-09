# Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetWide310x150LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008fe0`
- end: `0x180009032`
- name: `?TryGetWide310x150LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008fe0`
- `0x18000a510`

## string_xrefs

- `0x180008ffa`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetWide310x150LogoLocalizedAsRandomAccessStreamReference(
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
    v4 = 197;
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
                                     *(HSTRING *)(a1 + 96),
                                     a2,
                                     a3);
  if ( MrtRandomAccessStreamReference < 0 )
  {
    v4 = 201;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008fe0  push    rbx; int
0x180008fe2  sub     rsp, 20h
0x180008fe6  test    r8, r8
0x180008fe9  jnz     short loc_18000900D
0x180008feb  mov     ebx, 80004003h
0x180008ff0  mov     edx, 0C5h; void *
0x180008ff5  mov     rcx, [rsp+28h]; this
0x180008ffa  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180009001  mov     r9d, ebx; char *
0x180009004  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009009  mov     eax, ebx
0x18000900b  jmp     short loc_18000902C
0x18000900d  mov     qword ptr [r8], 0
0x180009014  mov     rcx, [rcx+60h]
0x180009018  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x18000901d  mov     ebx, eax
0x18000901f  test    eax, eax
0x180009021  jns     short loc_18000902A
0x180009023  mov     edx, 0C9h
0x180009028  jmp     short loc_180008FF5
0x18000902a  xor     eax, eax
0x18000902c  add     rsp, 20h
0x180009030  pop     rbx
0x180009031  retn
```
