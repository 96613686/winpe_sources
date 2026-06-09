# StateRepository::Localization::CreateMrtUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180009f2c`
- end: `0x180009fb8`
- name: `?CreateMrtUri@Localization@StateRepository@@YAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(StateRepository::Localization *this, unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009f04`

## callees

- `0x180006224`
- `0x180006f34`
- `0x180009d80`
- `0x180009f2c`
- `0x180009fc0`

## string_xrefs

- `0x180009f43`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009f7c`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::CreateMrtUri(
        StateRepository::Localization *this,
        unsigned __int16 *a2,
        HSTRING *a3)
{
  unsigned int Uri; // ebx
  int MrtString; // eax
  struct Windows::Foundation::IUriRuntimeClass **v6; // r8
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  StateRepository::Localization *v10; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v10 = 0;
    MrtString = StateRepository::Localization::CreateMrtString(this, (unsigned __int16 *)&v10, a3);
    Uri = MrtString;
    if ( MrtString >= 0 )
      Uri = StateRepository::Localization::CreateUri(v10, (HSTRING)a2, v6);
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
        (const char *)(unsigned int)MrtString,
        v8);
    Windows::Internal::String::~String((HSTRING *)&v10);
  }
  else
  {
    Uri = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
      (const char *)0x80004003LL,
      v8);
  }
  return Uri;
}

```

## disassembly

```asm
0x180009f2c  mov     [rsp+arg_0], rbx
0x180009f31  push    rdi; int
0x180009f32  sub     rsp, 20h
0x180009f36  mov     rdi, rdx
0x180009f39  test    rdx, rdx
0x180009f3c  jnz     short loc_180009F5E
0x180009f3e  mov     rcx, [rsp+28h]; this
0x180009f43  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009f4a  mov     ebx, 80004003h
0x180009f4f  mov     edx, 8Bh; void *
0x180009f54  mov     r9d, ebx; char *
0x180009f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f5c  jmp     short loc_180009FAB
0x180009f5e  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 *
0x180009f63  mov     [rsp+28h+arg_8], 0
0x180009f6c  call    ?CreateMrtString@Localization@StateRepository@@YAJPEBGPEAPEAUHSTRING__@@@Z; StateRepository::Localization::CreateMrtString(ushort const *,HSTRING__ * *)
0x180009f71  mov     ebx, eax
0x180009f73  test    eax, eax
0x180009f75  jns     short loc_180009F92
0x180009f77  mov     rcx, [rsp+28h]; this
0x180009f7c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009f83  mov     r9d, eax; char *
0x180009f86  mov     edx, 8Eh; void *
0x180009f8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f90  jmp     short loc_180009FA1
0x180009f92  mov     rcx, [rsp+28h+arg_8]; this
0x180009f97  mov     rdx, rdi; HSTRING
0x180009f9a  call    ?CreateUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x180009f9f  mov     ebx, eax
0x180009fa1  lea     rcx, [rsp+28h+arg_8]; this
0x180009fa6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180009fab  mov     eax, ebx
0x180009fad  mov     rbx, [rsp+28h+arg_0]
0x180009fb2  add     rsp, 20h
0x180009fb6  pop     rdi
0x180009fb7  retn
```
