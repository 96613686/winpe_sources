# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetDescriptionLocalized(HSTRING__ * *)

- ea: `0x180008270`
- end: `0x1800082c2`
- name: `?GetDescriptionLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008270`
- `0x180009d58`

## string_xrefs

- `0x18000828a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetDescriptionLocalized(
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
    v4 = 56;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[9], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 60;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008270  push    rbx; int
0x180008272  sub     rsp, 20h
0x180008276  test    rdx, rdx
0x180008279  jnz     short loc_18000829D
0x18000827b  mov     ebx, 80004003h
0x180008280  mov     edx, 38h ; '8'; void *
0x180008285  mov     rcx, [rsp+28h]; this
0x18000828a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008291  mov     r9d, ebx; char *
0x180008294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008299  mov     eax, ebx
0x18000829b  jmp     short loc_1800082BC
0x18000829d  mov     qword ptr [rdx], 0
0x1800082a4  mov     rcx, [rcx+48h]; this
0x1800082a8  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x1800082ad  mov     ebx, eax
0x1800082af  test    eax, eax
0x1800082b1  jns     short loc_1800082BA
0x1800082b3  mov     edx, 3Ch ; '<'
0x1800082b8  jmp     short loc_180008285
0x1800082ba  xor     eax, eax
0x1800082bc  add     rsp, 20h
0x1800082c0  pop     rbx
0x1800082c1  retn
```
