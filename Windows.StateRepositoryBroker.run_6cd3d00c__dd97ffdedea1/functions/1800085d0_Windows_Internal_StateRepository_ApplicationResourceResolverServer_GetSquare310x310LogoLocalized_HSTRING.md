# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare310x310LogoLocalized(HSTRING__ * *)

- ea: `0x1800085d0`
- end: `0x180008622`
- name: `?GetSquare310x310LogoLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800085d0`
- `0x180009d58`

## string_xrefs

- `0x1800085ea`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetSquare310x310LogoLocalized(
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
    v4 = 209;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[13], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 213;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800085d0  push    rbx; int
0x1800085d2  sub     rsp, 20h
0x1800085d6  test    rdx, rdx
0x1800085d9  jnz     short loc_1800085FD
0x1800085db  mov     ebx, 80004003h
0x1800085e0  mov     edx, 0D1h; void *
0x1800085e5  mov     rcx, [rsp+28h]; this
0x1800085ea  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800085f1  mov     r9d, ebx; char *
0x1800085f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085f9  mov     eax, ebx
0x1800085fb  jmp     short loc_18000861C
0x1800085fd  mov     qword ptr [rdx], 0
0x180008604  mov     rcx, [rcx+68h]; this
0x180008608  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x18000860d  mov     ebx, eax
0x18000860f  test    eax, eax
0x180008611  jns     short loc_18000861A
0x180008613  mov     edx, 0D5h
0x180008618  jmp     short loc_1800085E5
0x18000861a  xor     eax, eax
0x18000861c  add     rsp, 20h
0x180008620  pop     rbx
0x180008621  retn
```
