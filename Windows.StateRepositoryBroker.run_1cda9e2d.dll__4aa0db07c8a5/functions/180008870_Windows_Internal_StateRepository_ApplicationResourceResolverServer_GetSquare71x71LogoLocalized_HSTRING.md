# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare71x71LogoLocalized(HSTRING__ * *)

- ea: `0x180008870`
- end: `0x1800088c2`
- name: `?GetSquare71x71LogoLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008870`
- `0x180009d58`

## string_xrefs

- `0x18000888a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare71x71LogoLocalized(
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
    v4 = 256;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[14], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 260;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008870  push    rbx; int
0x180008872  sub     rsp, 20h
0x180008876  test    rdx, rdx
0x180008879  jnz     short loc_18000889D
0x18000887b  mov     ebx, 80004003h
0x180008880  mov     edx, 100h; void *
0x180008885  mov     rcx, [rsp+28h]; this
0x18000888a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008891  mov     r9d, ebx; char *
0x180008894  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008899  mov     eax, ebx
0x18000889b  jmp     short loc_1800088BC
0x18000889d  mov     qword ptr [rdx], 0
0x1800088a4  mov     rcx, [rcx+70h]; this
0x1800088a8  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x1800088ad  mov     ebx, eax
0x1800088af  test    eax, eax
0x1800088b1  jns     short loc_1800088BA
0x1800088b3  mov     edx, 104h
0x1800088b8  jmp     short loc_180008885
0x1800088ba  xor     eax, eax
0x1800088bc  add     rsp, 20h
0x1800088c0  pop     rbx
0x1800088c1  retn
```
