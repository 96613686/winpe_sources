# Windows::Internal::StateRepository::PackageResourceResolverServer::GetDescriptionLocalized(HSTRING__ * *)

- ea: `0x180009040`
- end: `0x180009092`
- name: `?GetDescriptionLocalized@PackageResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180009040`
- `0x180009d58`

## string_xrefs

- `0x18000905a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.packageresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::GetDescriptionLocalized(
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
    v4 = 62;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[10], (const unsigned __int16 *)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 66;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009040  push    rbx; int
0x180009042  sub     rsp, 20h
0x180009046  test    rdx, rdx
0x180009049  jnz     short loc_18000906D
0x18000904b  mov     ebx, 80004003h
0x180009050  mov     edx, 3Eh ; '>'; void *
0x180009055  mov     rcx, [rsp+28h]; this
0x18000905a  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180009061  mov     r9d, ebx; char *
0x180009064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009069  mov     eax, ebx
0x18000906b  jmp     short loc_18000908C
0x18000906d  mov     qword ptr [rdx], 0
0x180009074  mov     rcx, [rcx+50h]; this
0x180009078  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x18000907d  mov     ebx, eax
0x18000907f  test    eax, eax
0x180009081  jns     short loc_18000908A
0x180009083  mov     edx, 42h ; 'B'
0x180009088  jmp     short loc_180009055
0x18000908a  xor     eax, eax
0x18000908c  add     rsp, 20h
0x180009090  pop     rbx
0x180009091  retn
```
