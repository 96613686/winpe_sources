# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare44x44LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180008780`
- end: `0x180008806`
- name: `?GetSquare44x44LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008780`
- `0x18000a510`

## string_xrefs

- `0x1800087a1`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x1800087cf`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare44x44LogoLocalizedAsRandomAccessStreamReference(
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
    v5 = 137;
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
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 88));
  v8 = MrtRandomAccessStreamReference;
  if ( MrtRandomAccessStreamReference >= 0 )
  {
    if ( !*a3 )
    {
      v4 = -2147023728;
      v5 = 142;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
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
0x180008780  mov     [rsp+arg_0], rbx
0x180008785  push    rdi; int
0x180008786  sub     rsp, 20h
0x18000878a  mov     rbx, r8
0x18000878d  test    r8, r8
0x180008790  jnz     short loc_1800087B4
0x180008792  mov     ebx, 80004003h
0x180008797  mov     edx, 89h; void *
0x18000879c  mov     rcx, [rsp+28h]; this
0x1800087a1  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800087a8  mov     r9d, ebx; char *
0x1800087ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087b0  mov     eax, ebx
0x1800087b2  jmp     short loc_1800087FB
0x1800087b4  mov     qword ptr [r8], 0
0x1800087bb  mov     rcx, [rcx+58h]
0x1800087bf  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800087c4  mov     edi, eax
0x1800087c6  test    eax, eax
0x1800087c8  jns     short loc_1800087E7
0x1800087ca  mov     rcx, [rsp+28h]; this
0x1800087cf  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800087d6  mov     r9d, eax; char *
0x1800087d9  mov     edx, 8Dh; void *
0x1800087de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087e3  mov     eax, edi
0x1800087e5  jmp     short loc_1800087FB
0x1800087e7  cmp     qword ptr [rbx], 0
0x1800087eb  jnz     short loc_1800087F9
0x1800087ed  mov     ebx, 80070490h
0x1800087f2  mov     edx, 8Eh
0x1800087f7  jmp     short loc_18000879C
0x1800087f9  xor     eax, eax
0x1800087fb  mov     rbx, [rsp+28h+arg_0]
0x180008800  add     rsp, 20h
0x180008804  pop     rdi
0x180008805  retn
```
