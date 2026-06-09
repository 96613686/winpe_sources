# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetWide310x150LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008a80`
- end: `0x180008b06`
- name: `?GetWide310x150LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008a80`
- `0x18000a510`

## string_xrefs

- `0x180008aa1`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x180008acf`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetWide310x150LogoLocalizedAsRandomAccessStreamReference(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int MrtRandomAccessStreamReference; // eax
  unsigned int v8; // edi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 )
  {
    v4 = -2147467261;
    v5 = 184;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)v4,
      v9);
    return v4;
  }
  *a3 = 0;
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 96));
  v8 = MrtRandomAccessStreamReference;
  if ( MrtRandomAccessStreamReference >= 0 )
  {
    if ( !*a3 )
    {
      v4 = -2147023728;
      v5 = 189;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)(unsigned int)MrtRandomAccessStreamReference,
      v9);
    return v8;
  }
}

```

## disassembly

```asm
0x180008a80  mov     [rsp+arg_0], rbx
0x180008a85  push    rdi; int
0x180008a86  sub     rsp, 20h
0x180008a8a  mov     rbx, r8
0x180008a8d  test    r8, r8
0x180008a90  jnz     short loc_180008AB4
0x180008a92  mov     ebx, 80004003h
0x180008a97  mov     edx, 0B8h; void *
0x180008a9c  mov     rcx, [rsp+28h]; this
0x180008aa1  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008aa8  mov     r9d, ebx; char *
0x180008aab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ab0  mov     eax, ebx
0x180008ab2  jmp     short loc_180008AFB
0x180008ab4  mov     qword ptr [r8], 0
0x180008abb  mov     rcx, [rcx+60h]
0x180008abf  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008ac4  mov     edi, eax
0x180008ac6  test    eax, eax
0x180008ac8  jns     short loc_180008AE7
0x180008aca  mov     rcx, [rsp+28h]; this
0x180008acf  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008ad6  mov     r9d, eax; char *
0x180008ad9  mov     edx, 0BCh; void *
0x180008ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ae3  mov     eax, edi
0x180008ae5  jmp     short loc_180008AFB
0x180008ae7  cmp     qword ptr [rbx], 0
0x180008aeb  jnz     short loc_180008AF9
0x180008aed  mov     ebx, 80070490h
0x180008af2  mov     edx, 0BDh
0x180008af7  jmp     short loc_180008A9C
0x180008af9  xor     eax, eax
0x180008afb  mov     rbx, [rsp+28h+arg_0]
0x180008b00  add     rsp, 20h
0x180008b04  pop     rdi
0x180008b05  retn
```
