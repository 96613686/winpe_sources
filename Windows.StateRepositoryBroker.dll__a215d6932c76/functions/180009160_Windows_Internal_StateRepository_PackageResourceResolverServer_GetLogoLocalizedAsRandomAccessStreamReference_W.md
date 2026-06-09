# Windows::Internal::StateRepository::PackageResourceResolverServer::GetLogoLocalizedAsRandomAccessStreamReference(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x180009160`
- end: `0x1800091e5`
- name: `?GetLogoLocalizedAsRandomAccessStreamReference@PackageResourceResolverServer@StateRepository@Internal@Windows@@UEAAJUSize@Foundation@4@PEAPEAUIRandomAccessStreamReference@Streams@Storage@4@@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180009160`
- `0x18000a510`

## string_xrefs

- `0x180009180`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`
- `0x1800091ae`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::GetLogoLocalizedAsRandomAccessStreamReference(
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
    v5 = 96;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolver.cpp",
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
      v5 = 101;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolver.cpp",
      (const char *)(unsigned int)MrtRandomAccessStreamReference,
      v9);
    return v8;
  }
}

```

## disassembly

```asm
0x180009160  mov     [rsp+arg_0], rbx
0x180009165  push    rdi; int
0x180009166  sub     rsp, 20h
0x18000916a  mov     rbx, r8
0x18000916d  test    r8, r8
0x180009170  jnz     short loc_180009193
0x180009172  mov     ebx, 80004003h
0x180009177  lea     edx, [r8+60h]; void *
0x18000917b  mov     rcx, [rsp+28h]; this
0x180009180  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180009187  mov     r9d, ebx; char *
0x18000918a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000918f  mov     eax, ebx
0x180009191  jmp     short loc_1800091DA
0x180009193  mov     qword ptr [r8], 0
0x18000919a  mov     rcx, [rcx+58h]
0x18000919e  call    ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800091a3  mov     edi, eax
0x1800091a5  test    eax, eax
0x1800091a7  jns     short loc_1800091C6
0x1800091a9  mov     rcx, [rsp+28h]; this
0x1800091ae  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x1800091b5  mov     r9d, eax; char *
0x1800091b8  mov     edx, 64h ; 'd'; void *
0x1800091bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091c2  mov     eax, edi
0x1800091c4  jmp     short loc_1800091DA
0x1800091c6  cmp     qword ptr [rbx], 0
0x1800091ca  jnz     short loc_1800091D8
0x1800091cc  mov     ebx, 80070490h
0x1800091d1  mov     edx, 65h ; 'e'
0x1800091d6  jmp     short loc_18000917B
0x1800091d8  xor     eax, eax
0x1800091da  mov     rbx, [rsp+28h+arg_0]
0x1800091df  add     rsp, 20h
0x1800091e3  pop     rdi
0x1800091e4  retn
```
