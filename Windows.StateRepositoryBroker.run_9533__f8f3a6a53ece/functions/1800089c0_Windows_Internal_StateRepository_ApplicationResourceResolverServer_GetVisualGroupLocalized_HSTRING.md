# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetVisualGroupLocalized(HSTRING__ * *)

- ea: `0x1800089c0`
- end: `0x180008a15`
- name: `?GetVisualGroupLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `85`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800089c0`
- `0x180009d58`

## string_xrefs

- `0x1800089da`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetVisualGroupLocalized(
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
    v4 = 350;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[16], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 354;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800089c0  push    rbx; int
0x1800089c2  sub     rsp, 20h
0x1800089c6  test    rdx, rdx
0x1800089c9  jnz     short loc_1800089ED
0x1800089cb  mov     ebx, 80004003h
0x1800089d0  mov     edx, 15Eh; void *
0x1800089d5  mov     rcx, [rsp+28h]; this
0x1800089da  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800089e1  mov     r9d, ebx; char *
0x1800089e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089e9  mov     eax, ebx
0x1800089eb  jmp     short loc_180008A0F
0x1800089ed  mov     qword ptr [rdx], 0
0x1800089f4  mov     rcx, [rcx+80h]; this
0x1800089fb  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x180008a00  mov     ebx, eax
0x180008a02  test    eax, eax
0x180008a04  jns     short loc_180008A0D
0x180008a06  mov     edx, 162h
0x180008a0b  jmp     short loc_1800089D5
0x180008a0d  xor     eax, eax
0x180008a0f  add     rsp, 20h
0x180008a13  pop     rbx
0x180008a14  retn
```
