# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSplashScreenImageLocalized(HSTRING__ * *)

- ea: `0x180008330`
- end: `0x180008382`
- name: `?GetSplashScreenImageLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008330`
- `0x180009d58`

## string_xrefs

- `0x18000834a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSplashScreenImageLocalized(
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
    v4 = 303;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[15], (const unsigned __int16 *)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 307;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008330  push    rbx; int
0x180008332  sub     rsp, 20h
0x180008336  test    rdx, rdx
0x180008339  jnz     short loc_18000835D
0x18000833b  mov     ebx, 80004003h
0x180008340  mov     edx, 12Fh; void *
0x180008345  mov     rcx, [rsp+28h]; this
0x18000834a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008351  mov     r9d, ebx; char *
0x180008354  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008359  mov     eax, ebx
0x18000835b  jmp     short loc_18000837C
0x18000835d  mov     qword ptr [rdx], 0
0x180008364  mov     rcx, [rcx+78h]; this
0x180008368  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x18000836d  mov     ebx, eax
0x18000836f  test    eax, eax
0x180008371  jns     short loc_18000837A
0x180008373  mov     edx, 133h
0x180008378  jmp     short loc_180008345
0x18000837a  xor     eax, eax
0x18000837c  add     rsp, 20h
0x180008380  pop     rbx
0x180008381  retn
```
