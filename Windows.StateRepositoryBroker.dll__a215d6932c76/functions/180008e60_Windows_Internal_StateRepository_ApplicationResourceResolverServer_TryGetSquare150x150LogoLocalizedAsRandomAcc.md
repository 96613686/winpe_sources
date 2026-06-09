# Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare150x150LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008e60`
- end: `0x180008eb1`
- name: `?TryGetSquare150x150LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008e60`
- `0x18000a510`

## string_xrefs

- `0x180008e79`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare150x150LogoLocalizedAsRandomAccessStreamReference(
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
    v4 = 103;
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
                                     *(HSTRING *)(a1 + 80),
                                     a2,
                                     a3);
  if ( MrtRandomAccessStreamReference < 0 )
  {
    v4 = 107;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008e60  push    rbx; int
0x180008e62  sub     rsp, 20h
0x180008e66  test    r8, r8
0x180008e69  jnz     short loc_180008E8C
0x180008e6b  mov     ebx, 80004003h
0x180008e70  lea     edx, [r8+67h]; void *
0x180008e74  mov     rcx, [rsp+28h]; this
0x180008e79  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008e80  mov     r9d, ebx; char *
0x180008e83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e88  mov     eax, ebx
0x180008e8a  jmp     short loc_180008EAB
0x180008e8c  mov     qword ptr [r8], 0
0x180008e93  mov     rcx, [rcx+50h]
0x180008e97  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008e9c  mov     ebx, eax
0x180008e9e  test    eax, eax
0x180008ea0  jns     short loc_180008EA9
0x180008ea2  mov     edx, 6Bh ; 'k'
0x180008ea7  jmp     short loc_180008E74
0x180008ea9  xor     eax, eax
0x180008eab  add     rsp, 20h
0x180008eaf  pop     rbx
0x180008eb0  retn
```
