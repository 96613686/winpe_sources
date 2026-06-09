# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetDisplayNameLocalized(HSTRING__ * *)

- ea: `0x1800082d0`
- end: `0x180008322`
- name: `?GetDisplayNameLocalized@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(StateRepository::Localization **this, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x1800082d0`
- `0x180009d58`

## string_xrefs

- `0x1800082ea`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.applicationresourceresolver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetDisplayNameLocalized(
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
    v4 = 45;
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
  MrtString = StateRepository::Localization::CreateMrtString(this[8], (const unsigned __int16 *)a2, a3);
  if ( MrtString < 0 )
  {
    v4 = 49;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800082d0  push    rbx; int
0x1800082d2  sub     rsp, 20h
0x1800082d6  test    rdx, rdx
0x1800082d9  jnz     short loc_1800082FD
0x1800082db  mov     ebx, 80004003h
0x1800082e0  mov     edx, 2Dh ; '-'; void *
0x1800082e5  mov     rcx, [rsp+28h]; this
0x1800082ea  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x1800082f1  mov     r9d, ebx; char *
0x1800082f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082f9  mov     eax, ebx
0x1800082fb  jmp     short loc_18000831C
0x1800082fd  mov     qword ptr [rdx], 0
0x180008304  mov     rcx, [rcx+40h]; this
0x180008308  call    ?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)
0x18000830d  mov     ebx, eax
0x18000830f  test    eax, eax
0x180008311  jns     short loc_18000831A
0x180008313  mov     edx, 31h ; '1'
0x180008318  jmp     short loc_1800082E5
0x18000831a  xor     eax, eax
0x18000831c  add     rsp, 20h
0x180008320  pop     rbx
0x180008321  retn
```
