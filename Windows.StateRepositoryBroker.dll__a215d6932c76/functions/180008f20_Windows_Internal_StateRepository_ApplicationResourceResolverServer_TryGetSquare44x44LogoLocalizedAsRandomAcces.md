# Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare44x44LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008f20`
- end: `0x180008f72`
- name: `?TryGetSquare44x44LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008f20`
- `0x18000a510`

## string_xrefs

- `0x180008f3a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare44x44LogoLocalizedAsRandomAccessStreamReference(
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
    v4 = 150;
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
                                     *(HSTRING *)(a1 + 88),
                                     a2,
                                     a3);
  if ( MrtRandomAccessStreamReference < 0 )
  {
    v4 = 154;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008f20  push    rbx; int
0x180008f22  sub     rsp, 20h
0x180008f26  test    r8, r8
0x180008f29  jnz     short loc_180008F4D
0x180008f2b  mov     ebx, 80004003h
0x180008f30  mov     edx, 96h; void *
0x180008f35  mov     rcx, [rsp+28h]; this
0x180008f3a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008f41  mov     r9d, ebx; char *
0x180008f44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f49  mov     eax, ebx
0x180008f4b  jmp     short loc_180008F6C
0x180008f4d  mov     qword ptr [r8], 0
0x180008f54  mov     rcx, [rcx+58h]
0x180008f58  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008f5d  mov     ebx, eax
0x180008f5f  test    eax, eax
0x180008f61  jns     short loc_180008F6A
0x180008f63  mov     edx, 9Ah
0x180008f68  jmp     short loc_180008F35
0x180008f6a  xor     eax, eax
0x180008f6c  add     rsp, 20h
0x180008f70  pop     rbx
0x180008f71  retn
```
