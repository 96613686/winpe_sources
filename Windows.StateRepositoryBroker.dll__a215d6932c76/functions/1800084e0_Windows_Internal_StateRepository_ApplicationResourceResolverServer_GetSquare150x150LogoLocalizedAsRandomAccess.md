# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare150x150LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x1800084e0`
- end: `0x180008565`
- name: `?GetSquare150x150LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800084e0`
- `0x18000a510`

## string_xrefs

- `0x180008500`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x18000852e`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare150x150LogoLocalizedAsRandomAccessStreamReference(
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
    v5 = 90;
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
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 80));
  v8 = MrtRandomAccessStreamReference;
  if ( MrtRandomAccessStreamReference >= 0 )
  {
    if ( !*a3 )
    {
      v4 = -2147023728;
      v5 = 95;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
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
0x1800084e0  mov     [rsp+arg_0], rbx
0x1800084e5  push    rdi; int
0x1800084e6  sub     rsp, 20h
0x1800084ea  mov     rbx, r8
0x1800084ed  test    r8, r8
0x1800084f0  jnz     short loc_180008513
0x1800084f2  mov     ebx, 80004003h
0x1800084f7  lea     edx, [r8+5Ah]; void *
0x1800084fb  mov     rcx, [rsp+28h]; this
0x180008500  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008507  mov     r9d, ebx; char *
0x18000850a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000850f  mov     eax, ebx
0x180008511  jmp     short loc_18000855A
0x180008513  mov     qword ptr [r8], 0
0x18000851a  mov     rcx, [rcx+50h]
0x18000851e  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008523  mov     edi, eax
0x180008525  test    eax, eax
0x180008527  jns     short loc_180008546
0x180008529  mov     rcx, [rsp+28h]; this
0x18000852e  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008535  mov     r9d, eax; char *
0x180008538  mov     edx, 5Eh ; '^'; void *
0x18000853d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008542  mov     eax, edi
0x180008544  jmp     short loc_18000855A
0x180008546  cmp     qword ptr [rbx], 0
0x18000854a  jnz     short loc_180008558
0x18000854c  mov     ebx, 80070490h
0x180008551  mov     edx, 5Fh ; '_'
0x180008556  jmp     short loc_1800084FB
0x180008558  xor     eax, eax
0x18000855a  mov     rbx, [rsp+28h+arg_0]
0x18000855f  add     rsp, 20h
0x180008563  pop     rdi
0x180008564  retn
```
