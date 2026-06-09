# Windows::Internal::StateRepository::PackageResourceResolverServer::GetDisplayNameLocalized(HSTRING__ * *)

- ea: `0x1800090a0`
- end: `0x1800090f2`
- name: `?GetDisplayNameLocalized@PackageResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `int(Windows::Internal::StateRepository::PackageResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800090a0`
- `0x180009d58`

## string_xrefs

- `0x1800090ba`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::GetDisplayNameLocalized(
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
    v4 = 40;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[8], (HSTRING)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 44;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800090a0  push    rbx; int
0x1800090a2  sub     rsp, 20h
0x1800090a6  test    rdx, rdx
0x1800090a9  jnz     short loc_1800090CD
0x1800090ab  mov     ebx, 80004003h
0x1800090b0  mov     edx, 28h ; '('; void *
0x1800090b5  mov     rcx, [rsp+28h]; this
0x1800090ba  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x1800090c1  mov     r9d, ebx; char *
0x1800090c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090c9  mov     eax, ebx
0x1800090cb  jmp     short loc_1800090EC
0x1800090cd  mov     qword ptr [rdx], 0
0x1800090d4  mov     rcx, [rcx+40h]; this
0x1800090d8  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x1800090dd  mov     ebx, eax
0x1800090df  test    eax, eax
0x1800090e1  jns     short loc_1800090EA
0x1800090e3  mov     edx, 2Ch ; ','
0x1800090e8  jmp     short loc_1800090B5
0x1800090ea  xor     eax, eax
0x1800090ec  add     rsp, 20h
0x1800090f0  pop     rbx
0x1800090f1  retn
```
