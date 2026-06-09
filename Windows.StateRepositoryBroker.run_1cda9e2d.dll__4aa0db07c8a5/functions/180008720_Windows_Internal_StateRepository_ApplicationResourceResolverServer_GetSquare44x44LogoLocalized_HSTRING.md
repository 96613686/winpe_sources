# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare44x44LogoLocalized(HSTRING__ * *)

- ea: `0x180008720`
- end: `0x180008772`
- name: `?GetSquare44x44LogoLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008720`
- `0x180009d58`

## string_xrefs

- `0x18000873a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare44x44LogoLocalized(
        StateRepository::Localization **this,
        HSTRING *a2,
        HSTRING *a3)
{
  int MrtString; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    MrtString = -2147467261;
    v4 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appli"
                    "cationresourceresolver.cpp",
      (const char *)(unsigned int)MrtString,
      v6);
    return (unsigned int)MrtString;
  }
  *a2 = 0;
  MrtString = StateRepository::Localization::CreateMrtString(this[11], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 118;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008720  push    rbx; int
0x180008722  sub     rsp, 20h
0x180008726  test    rdx, rdx
0x180008729  jnz     short loc_18000874D
0x18000872b  mov     ebx, 80004003h
0x180008730  mov     edx, 72h ; 'r'; void *
0x180008735  mov     rcx, [rsp+28h]; this
0x18000873a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008741  mov     r9d, ebx; char *
0x180008744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008749  mov     eax, ebx
0x18000874b  jmp     short loc_18000876C
0x18000874d  mov     qword ptr [rdx], 0
0x180008754  mov     rcx, [rcx+58h]; this
0x180008758  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x18000875d  mov     ebx, eax
0x18000875f  test    eax, eax
0x180008761  jns     short loc_18000876A
0x180008763  mov     edx, 76h ; 'v'
0x180008768  jmp     short loc_180008735
0x18000876a  xor     eax, eax
0x18000876c  add     rsp, 20h
0x180008770  pop     rbx
0x180008771  retn
```
