# LanguageManager::_EnsureTrustedCaller(void)

- ea: `0x180031a2c`
- end: `0x180031aee`
- name: `?_EnsureTrustedCaller@LanguageManager@@CAXXZ`
- size: `194`
- prototype: `void __fastcall(CallerIdentity *, __int64, bool *)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002ee00`
- `0x18002f100`
- `0x18002f410`
- `0x1800306c0`
- `0x1800308a0`
- `0x180033418`

## callees

- `0x180012a98`
- `0x180031a2c`
- `0x1800362a0`
- `0x180036fd4`
- `0x180062fa8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a85`
- `Windows.Storage!__imp_SHTestTokenMembership` at `0x180031a70`
- `Windows.Storage!__imp_SHTestTokenMembership` at `0x180031a70`

## string_xrefs

- `0x180031a9f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x180031abc`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x180031ad6`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanguageManager::_EnsureTrustedCaller(CallerIdentity *a1, __int64 a2, bool *a3)
{
  int v3; // eax
  char *v4; // rbx
  BOOL v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE hToken; // [rsp+30h] [rbp+8h] BYREF

  LOBYTE(hToken) = 0;
  v3 = CallerIdentity::CheckCallerCapability(a1, (const unsigned __int16 *)&hToken, a3);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
      (const char *)(unsigned int)v3,
      v6);
  if ( !(_BYTE)hToken && !IsCallerLocalSystem() )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
      (const char *)0x80070005LL,
      v6);
  GetCallerTokenHandleForIdentification((__int64)&hToken);
  v4 = (char *)hToken;
  v5 = SHTestTokenMembership(hToken, 0x222u);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
      (const char *)0x80070005LL,
      v6);
}

```

## disassembly

```asm
0x180031a2c  mov     [rsp+arg_8], rbx
0x180031a31  push    rdi; int
0x180031a32  sub     rsp, 20h
0x180031a36  lea     rdx, [rsp+28h+hToken]; unsigned __int16 *
0x180031a3b  mov     byte ptr [rsp+28h+hToken], 0
0x180031a40  call    ?CheckCallerCapability@CallerIdentity@@YAJPEBGPEA_N@Z; CallerIdentity::CheckCallerCapability(ushort const *,bool *)
0x180031a45  test    eax, eax
0x180031a47  js      short loc_180031AB7
0x180031a49  cmp     byte ptr [rsp+28h+hToken], 0
0x180031a4e  jnz     short loc_180031A59
0x180031a50  call    ?IsCallerLocalSystem@@YA_NXZ; IsCallerLocalSystem(void)
0x180031a55  test    al, al
0x180031a57  jz      short loc_180031AD1
0x180031a59  lea     rcx, [rsp+28h+hToken]
0x180031a5e  call    ?GetCallerTokenHandleForIdentification@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; GetCallerTokenHandleForIdentification(void)
0x180031a63  mov     rbx, [rsp+28h+hToken]
0x180031a68  mov     edx, 222h; ulRID
0x180031a6d  mov     rcx, rbx; hToken
0x180031a70  call    cs:__imp_SHTestTokenMembership
0x180031a76  lea     rdx, [rbx-1]
0x180031a7a  mov     edi, eax
0x180031a7c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180031a80  ja      short loc_180031A8B
0x180031a82  mov     rcx, rbx; hObject
0x180031a85  call    cs:__imp_CloseHandle
0x180031a8b  test    edi, edi
0x180031a8d  jnz     short loc_180031A9A
0x180031a8f  mov     rbx, [rsp+28h+arg_8]
0x180031a94  add     rsp, 20h
0x180031a98  pop     rdi
0x180031a99  retn
0x180031a9a  mov     rcx, [rsp+28h]; this
0x180031a9f  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180031aa6  mov     r9d, 80070005h; char *
0x180031aac  mov     edx, 1BFh; void *
0x180031ab1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031ab7  mov     rcx, [rsp+28h]; this
0x180031abc  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180031ac3  mov     r9d, eax; char *
0x180031ac6  mov     edx, 1BDh; void *
0x180031acb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031ad1  mov     rcx, [rsp+28h]; this
0x180031ad6  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180031add  mov     r9d, 80070005h; char *
0x180031ae3  mov     edx, 1BEh; void *
0x180031ae8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
