# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare71x71LogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x1800088d0`
- end: `0x180008956`
- name: `?GetSquare71x71LogoLocalizedAsRandomAccessStreamReference@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800088d0`
- `0x18000a510`

## string_xrefs

- `0x1800088f1`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`
- `0x18000891f`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare71x71LogoLocalizedAsRandomAccessStreamReference(
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
    v5 = 279;
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
  MrtRandomAccessStreamReference = StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(*(_QWORD *)(a1 + 112));
  v8 = MrtRandomAccessStreamReference;
  if ( MrtRandomAccessStreamReference >= 0 )
  {
    if ( !*a3 )
    {
      v4 = -2147023728;
      v5 = 284;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B,
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
0x1800088d0  mov     [rsp+arg_0], rbx
0x1800088d5  push    rdi; int
0x1800088d6  sub     rsp, 20h
0x1800088da  mov     rbx, r8
0x1800088dd  test    r8, r8
0x1800088e0  jnz     short loc_180008904
0x1800088e2  mov     ebx, 80004003h
0x1800088e7  mov     edx, 117h; void *
0x1800088ec  mov     rcx, [rsp+28h]; this
0x1800088f1  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800088f8  mov     r9d, ebx; char *
0x1800088fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008900  mov     eax, ebx
0x180008902  jmp     short loc_18000894B
0x180008904  mov     qword ptr [r8], 0
0x18000890b  mov     rcx, [rcx+70h]
0x18000890f  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x180008914  mov     edi, eax
0x180008916  test    eax, eax
0x180008918  jns     short loc_180008937
0x18000891a  mov     rcx, [rsp+28h]; this
0x18000891f  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008926  mov     r9d, eax; char *
0x180008929  mov     edx, 11Bh; void *
0x18000892e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008933  mov     eax, edi
0x180008935  jmp     short loc_18000894B
0x180008937  cmp     qword ptr [rbx], 0
0x18000893b  jnz     short loc_180008949
0x18000893d  mov     ebx, 80070490h
0x180008942  mov     edx, 11Ch
0x180008947  jmp     short loc_1800088EC
0x180008949  xor     eax, eax
0x18000894b  mov     rbx, [rsp+28h+arg_0]
0x180008950  add     rsp, 20h
0x180008954  pop     rdi
0x180008955  retn
```
