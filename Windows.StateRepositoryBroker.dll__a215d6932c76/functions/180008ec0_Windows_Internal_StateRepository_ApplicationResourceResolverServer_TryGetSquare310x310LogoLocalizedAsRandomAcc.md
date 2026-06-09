# Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare310x310LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008ec0`
- end: `0x180008f12`
- name: `?TryGetSquare310x310LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008ec0`
- `0x18000a510`

## string_xrefs

- `0x180008eda`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare310x310LogoLocalizedAsRandomAccessStreamReference(
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
    v4 = 245;
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
                                     *(HSTRING *)(a1 + 104),
                                     a2,
                                     a3);
  if ( MrtRandomAccessStreamReference < 0 )
  {
    v4 = 249;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008ec0  push    rbx; int
0x180008ec2  sub     rsp, 20h
0x180008ec6  test    r8, r8
0x180008ec9  jnz     short loc_180008EED
0x180008ecb  mov     ebx, 80004003h
0x180008ed0  mov     edx, 0F5h; void *
0x180008ed5  mov     rcx, [rsp+28h]; this
0x180008eda  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008ee1  mov     r9d, ebx; char *
0x180008ee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ee9  mov     eax, ebx
0x180008eeb  jmp     short loc_180008F0C
0x180008eed  mov     qword ptr [r8], 0
0x180008ef4  mov     rcx, [rcx+68h]
0x180008ef8  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008efd  mov     ebx, eax
0x180008eff  test    eax, eax
0x180008f01  jns     short loc_180008F0A
0x180008f03  mov     edx, 0F9h
0x180008f08  jmp     short loc_180008ED5
0x180008f0a  xor     eax, eax
0x180008f0c  add     rsp, 20h
0x180008f10  pop     rbx
0x180008f11  retn
```
