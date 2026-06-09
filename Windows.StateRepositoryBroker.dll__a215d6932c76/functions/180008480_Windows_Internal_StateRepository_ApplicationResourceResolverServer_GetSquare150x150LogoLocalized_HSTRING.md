# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare150x150LogoLocalized(HSTRING__ * *)

- ea: `0x180008480`
- end: `0x1800084d2`
- name: `?GetSquare150x150LogoLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008480`
- `0x180009d58`

## string_xrefs

- `0x18000849a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare150x150LogoLocalized(
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
    v4 = 67;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[10], (const unsigned __int16 *)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 71;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008480  push    rbx; int
0x180008482  sub     rsp, 20h
0x180008486  test    rdx, rdx
0x180008489  jnz     short loc_1800084AD
0x18000848b  mov     ebx, 80004003h
0x180008490  mov     edx, 43h ; 'C'; void *
0x180008495  mov     rcx, [rsp+28h]; this
0x18000849a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800084a1  mov     r9d, ebx; char *
0x1800084a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084a9  mov     eax, ebx
0x1800084ab  jmp     short loc_1800084CC
0x1800084ad  mov     qword ptr [rdx], 0
0x1800084b4  mov     rcx, [rcx+50h]; this
0x1800084b8  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x1800084bd  mov     ebx, eax
0x1800084bf  test    eax, eax
0x1800084c1  jns     short loc_1800084CA
0x1800084c3  mov     edx, 47h ; 'G'
0x1800084c8  jmp     short loc_180008495
0x1800084ca  xor     eax, eax
0x1800084cc  add     rsp, 20h
0x1800084d0  pop     rbx
0x1800084d1  retn
```
