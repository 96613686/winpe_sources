# Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare71x71LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008f80`
- end: `0x180008fd2`
- name: `?TryGetSquare71x71LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `82`
- prototype: `int __high(struct Windows::Foundation::Size, struct Windows::Storage::Streams::IRandomAccessStreamReference **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008f80`
- `0x18000a510`

## string_xrefs

- `0x180008f9a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::TryGetSquare71x71LogoLocalizedAsRandomAccessStreamReference(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int MrtRandomAccessStreamReference; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 )
  {
    MrtRandomAccessStreamReference = -2147467261;
    v4 = 292;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)(unsigned int)MrtRandomAccessStreamReference,
      v6);
    return (unsigned int)MrtRandomAccessStreamReference;
  }
  *a3 = 0;
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 112));
  if ( MrtRandomAccessStreamReference < 0 )
  {
    v4 = 296;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008f80  push    rbx; int
0x180008f82  sub     rsp, 20h
0x180008f86  test    r8, r8
0x180008f89  jnz     short loc_180008FAD
0x180008f8b  mov     ebx, 80004003h
0x180008f90  mov     edx, 124h; void *
0x180008f95  mov     rcx, [rsp+28h]; this
0x180008f9a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008fa1  mov     r9d, ebx; char *
0x180008fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fa9  mov     eax, ebx
0x180008fab  jmp     short loc_180008FCC
0x180008fad  mov     qword ptr [r8], 0
0x180008fb4  mov     rcx, [rcx+70h]
0x180008fb8  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008fbd  mov     ebx, eax
0x180008fbf  test    eax, eax
0x180008fc1  jns     short loc_180008FCA
0x180008fc3  mov     edx, 128h
0x180008fc8  jmp     short loc_180008F95
0x180008fca  xor     eax, eax
0x180008fcc  add     rsp, 20h
0x180008fd0  pop     rbx
0x180008fd1  retn
```
