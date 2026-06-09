# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare310x310LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008630`
- end: `0x1800086b6`
- name: `?GetSquare310x310LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `134`
- prototype: `int __high(struct Windows::Foundation::Size, struct Windows::Storage::Streams::IRandomAccessStreamReference **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008630`
- `0x18000a510`

## string_xrefs

- `0x180008651`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x18000867f`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare310x310LogoLocalizedAsRandomAccessStreamReference(
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
    v5 = 232;
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
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 104));
  v8 = MrtRandomAccessStreamReference;
  if ( MrtRandomAccessStreamReference >= 0 )
  {
    if ( !*a3 )
    {
      v4 = -2147023728;
      v5 = 237;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
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
0x180008630  mov     [rsp+arg_0], rbx
0x180008635  push    rdi; int
0x180008636  sub     rsp, 20h
0x18000863a  mov     rbx, r8
0x18000863d  test    r8, r8
0x180008640  jnz     short loc_180008664
0x180008642  mov     ebx, 80004003h
0x180008647  mov     edx, 0E8h; void *
0x18000864c  mov     rcx, [rsp+28h]; this
0x180008651  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008658  mov     r9d, ebx; char *
0x18000865b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008660  mov     eax, ebx
0x180008662  jmp     short loc_1800086AB
0x180008664  mov     qword ptr [r8], 0
0x18000866b  mov     rcx, [rcx+68h]
0x18000866f  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008674  mov     edi, eax
0x180008676  test    eax, eax
0x180008678  jns     short loc_180008697
0x18000867a  mov     rcx, [rsp+28h]; this
0x18000867f  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008686  mov     r9d, eax; char *
0x180008689  mov     edx, 0ECh; void *
0x18000868e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008693  mov     eax, edi
0x180008695  jmp     short loc_1800086AB
0x180008697  cmp     qword ptr [rbx], 0
0x18000869b  jnz     short loc_1800086A9
0x18000869d  mov     ebx, 80070490h
0x1800086a2  mov     edx, 0EDh
0x1800086a7  jmp     short loc_18000864C
0x1800086a9  xor     eax, eax
0x1800086ab  mov     rbx, [rsp+28h+arg_0]
0x1800086b0  add     rsp, 20h
0x1800086b4  pop     rdi
0x1800086b5  retn
```
