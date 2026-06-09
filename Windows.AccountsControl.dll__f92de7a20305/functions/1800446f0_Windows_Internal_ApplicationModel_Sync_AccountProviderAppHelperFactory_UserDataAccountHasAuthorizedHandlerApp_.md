# Windows::Internal::ApplicationModel::Sync::AccountProviderAppHelperFactory::UserDataAccountHasAuthorizedHandlerApp(HSTRING__ *,uchar *)

- ea: `0x1800446f0`
- end: `0x180044773`
- name: `?UserDataAccountHasAuthorizedHandlerApp@AccountProviderAppHelperFactory@Sync@ApplicationModel@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `131`
- prototype: `int(Windows::Internal::ApplicationModel::Sync::AccountProviderAppHelperFactory *__hidden this, HSTRING, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006eac`
- `0x1800446f0`
- `0x18004f028`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004470f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004470f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044760`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AccountProviderAppHelperFactory::UserDataAccountHasAuthorizedHandlerApp(
        Windows::Internal::ApplicationModel::Sync::AccountProviderAppHelperFactory *this,
        HSTRING a2,
        bool *a3)
{
  int UserDataAccountsProvider; // eax
  unsigned int v6; // ebx
  HSTRING v7; // rcx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  UserDataAccountsProvider = GetUserDataAccountsProvider(a2, &string);
  v6 = UserDataAccountsProvider;
  if ( UserDataAccountsProvider >= 0 )
  {
    v7 = string;
    *a3 = string != 0;
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\accountproviderapphelperfactory.cpp",
      (const char *)(unsigned int)UserDataAccountsProvider,
      v9);
    v7 = string;
  }
  WindowsDeleteString(v7);
  return v6;
}

```

## disassembly

```asm
0x1800446f0  mov     [rsp+arg_0], rbx
0x1800446f5  push    rdi; int
0x1800446f6  sub     rsp, 20h
0x1800446fa  mov     rdi, r8
0x1800446fd  mov     rbx, rdx
0x180044700  mov     byte ptr [r8], 0
0x180044704  mov     [rsp+28h+string], 0
0x18004470d  xor     ecx, ecx; string
0x18004470f  call    cs:__imp_WindowsDeleteString
0x180044715  mov     [rsp+28h+string], 0
0x18004471e  lea     rdx, [rsp+28h+string]; HSTRING *
0x180044723  mov     rcx, rbx; HSTRING
0x180044726  call    ?GetUserDataAccountsProvider@@YAJPEAUHSTRING__@@PEAPEAU1@@Z; GetUserDataAccountsProvider(HSTRING__ *,HSTRING__ * *)
0x18004472b  mov     ebx, eax
0x18004472d  test    eax, eax
0x18004472f  jns     short loc_180044751
0x180044731  mov     rcx, [rsp+28h]; this
0x180044736  mov     r9d, eax; char *
0x180044739  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\accountscontrol\\api"...
0x180044740  mov     edx, 20h ; ' '; void *
0x180044745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004474a  mov     rcx, [rsp+28h+string]
0x18004474f  jmp     short loc_180044760
0x180044751  mov     rcx, [rsp+28h+string]; string
0x180044756  test    rcx, rcx
0x180044759  setnz   al
0x18004475c  mov     [rdi], al
0x18004475e  xor     ebx, ebx
0x180044760  call    cs:__imp_WindowsDeleteString
0x180044766  mov     eax, ebx
0x180044768  mov     rbx, [rsp+28h+arg_0]
0x18004476d  add     rsp, 20h
0x180044771  pop     rdi
0x180044772  retn
```
