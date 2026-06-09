# Windows::Internal::StateRepository::PackageResourceResolverServer::GetLogoLocalized(HSTRING__ * *)

- ea: `0x180009100`
- end: `0x180009152`
- name: `?GetLogoLocalized@PackageResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::PackageResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180009100`
- `0x180009d58`

## string_xrefs

- `0x18000911a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::GetLogoLocalized(
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
    v4 = 73;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.packa"
                    "geresourceresolver.cpp",
      (const char *)(unsigned int)MrtString,
      v6);
    return (unsigned int)MrtString;
  }
  *a2 = 0;
  MrtString = StateRepository::Localization::CreateMrtString(this[11], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 77;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009100  push    rbx; int
0x180009102  sub     rsp, 20h
0x180009106  test    rdx, rdx
0x180009109  jnz     short loc_18000912D
0x18000910b  mov     ebx, 80004003h
0x180009110  mov     edx, 49h ; 'I'; void *
0x180009115  mov     rcx, [rsp+28h]; this
0x18000911a  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180009121  mov     r9d, ebx; char *
0x180009124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009129  mov     eax, ebx
0x18000912b  jmp     short loc_18000914C
0x18000912d  mov     qword ptr [rdx], 0
0x180009134  mov     rcx, [rcx+58h]; this
0x180009138  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x18000913d  mov     ebx, eax
0x18000913f  test    eax, eax
0x180009141  jns     short loc_18000914A
0x180009143  mov     edx, 4Dh ; 'M'
0x180009148  jmp     short loc_180009115
0x18000914a  xor     eax, eax
0x18000914c  add     rsp, 20h
0x180009150  pop     rbx
0x180009151  retn
```
