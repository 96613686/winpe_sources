# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetWide310x150LogoLocalized(HSTRING__ * *)

- ea: `0x180008a20`
- end: `0x180008a72`
- name: `?GetWide310x150LogoLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::ApplicationResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180008a20`
- `0x180009d58`

## string_xrefs

- `0x180008a3a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetWide310x150LogoLocalized(
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
    v4 = 161;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[12], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 165;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008a20  push    rbx; int
0x180008a22  sub     rsp, 20h
0x180008a26  test    rdx, rdx
0x180008a29  jnz     short loc_180008A4D
0x180008a2b  mov     ebx, 80004003h
0x180008a30  mov     edx, 0A1h; void *
0x180008a35  mov     rcx, [rsp+28h]; this
0x180008a3a  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180008a41  mov     r9d, ebx; char *
0x180008a44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a49  mov     eax, ebx
0x180008a4b  jmp     short loc_180008A6C
0x180008a4d  mov     qword ptr [rdx], 0
0x180008a54  mov     rcx, [rcx+60h]; this
0x180008a58  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x180008a5d  mov     ebx, eax
0x180008a5f  test    eax, eax
0x180008a61  jns     short loc_180008A6A
0x180008a63  mov     edx, 0A5h
0x180008a68  jmp     short loc_180008A35
0x180008a6a  xor     eax, eax
0x180008a6c  add     rsp, 20h
0x180008a70  pop     rbx
0x180008a71  retn
```
