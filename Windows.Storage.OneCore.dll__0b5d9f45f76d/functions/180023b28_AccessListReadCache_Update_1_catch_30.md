# _AccessListReadCache::Update_::_1_::catch$30

- ea: `0x180023b28`
- end: `0x180023b91`
- name: `_AccessListReadCache::Update_::_1_::catch$30`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000dd28`
- `0x18000e4d4`
- `0x18001050c`
- `0x180023b28`

## string_xrefs

- `0x180023b43`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x180023b6e`: `onecore\base\windows.storage\src\accesslistreadcache.cpp`
- `0x180023b3c`: `AccessListReadCache::Update`

## pseudocode

```c
__int64 __fastcall AccessListReadCache::Update_::_1_::catch_30(__int64 a1, __int64 a2)
{
  int v3; // eax
  const char *v5; // [rsp+20h] [rbp-18h]
  int v6; // [rsp+20h] [rbp-18h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 616),
    (void *)0xA3,
    (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
    "AccessListReadCache::Update",
    v5);
  v3 = AccessListReadCache::Clear(*(AccessListReadCache **)(a2 + 624));
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      *(wil::details::in1diag3 **)(a2 + 616),
      (void *)0xA4,
      (unsigned int)"onecore\\base\\windows.storage\\src\\accesslistreadcache.cpp",
      (const char *)(unsigned int)v3,
      v6);
  return 0;
}

```

## disassembly

```asm
0x180023b28  mov     [rsp+arg_8], rdx
0x180023b2d  push    rbp
0x180023b2e  sub     rsp, 30h
0x180023b32  mov     rbp, rdx
0x180023b35  mov     rcx, [rbp+268h]; this
0x180023b3c  lea     r9, aAccesslistread; "AccessListReadCache::Update"
0x180023b43  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x180023b4a  mov     edx, 0A3h; void *
0x180023b4f  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x180023b54  mov     rcx, [rbp+270h]; this
0x180023b5b  call    ?Clear@AccessListReadCache@@QEAAJXZ; AccessListReadCache::Clear(void)
0x180023b60  mov     rcx, [rbp+268h]; this
0x180023b67  test    eax, eax
0x180023b69  jns     short loc_180023B80
0x180023b6b  mov     r9d, eax; char *
0x180023b6e  lea     r8, aOnecoreBaseWin_6; "onecore\\base\\windows.storage\\src\\ac"...
0x180023b75  mov     edx, 0A4h; void *
0x180023b7a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023b7f  nop
0x180023b80  mov     rax, 0
0x180023b8a  add     rsp, 30h
0x180023b8e  pop     rbp
0x180023b8f  retn
```
