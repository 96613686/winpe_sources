# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSplashScreenImageLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008390`
- end: `0x180008416`
- name: `?GetSplashScreenImageLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `134`
- prototype: `int __high(struct Windows::Foundation::Size, struct Windows::Storage::Streams::IRandomAccessStreamReference **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008390`
- `0x18000a510`

## string_xrefs

- `0x1800083b1`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x1800083df`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSplashScreenImageLocalizedAsRandomAccessStreamReference(
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
    v5 = 326;
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
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 120));
  v8 = MrtRandomAccessStreamReference;
  if ( MrtRandomAccessStreamReference >= 0 )
  {
    if ( !*a3 )
    {
      v4 = -2147023728;
      v5 = 331;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
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
0x180008390  mov     [rsp+arg_0], rbx
0x180008395  push    rdi; int
0x180008396  sub     rsp, 20h
0x18000839a  mov     rbx, r8
0x18000839d  test    r8, r8
0x1800083a0  jnz     short loc_1800083C4
0x1800083a2  mov     ebx, 80004003h
0x1800083a7  mov     edx, 146h; void *
0x1800083ac  mov     rcx, [rsp+28h]; this
0x1800083b1  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800083b8  mov     r9d, ebx; char *
0x1800083bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083c0  mov     eax, ebx
0x1800083c2  jmp     short loc_18000840B
0x1800083c4  mov     qword ptr [r8], 0
0x1800083cb  mov     rcx, [rcx+78h]
0x1800083cf  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800083d4  mov     edi, eax
0x1800083d6  test    eax, eax
0x1800083d8  jns     short loc_1800083F7
0x1800083da  mov     rcx, [rsp+28h]; this
0x1800083df  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800083e6  mov     r9d, eax; char *
0x1800083e9  mov     edx, 14Ah; void *
0x1800083ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083f3  mov     eax, edi
0x1800083f5  jmp     short loc_18000840B
0x1800083f7  cmp     qword ptr [rbx], 0
0x1800083fb  jnz     short loc_180008409
0x1800083fd  mov     ebx, 80070490h
0x180008402  mov     edx, 14Bh
0x180008407  jmp     short loc_1800083AC
0x180008409  xor     eax, eax
0x18000840b  mov     rbx, [rsp+28h+arg_0]
0x180008410  add     rsp, 20h
0x180008414  pop     rdi
0x180008415  retn
```
