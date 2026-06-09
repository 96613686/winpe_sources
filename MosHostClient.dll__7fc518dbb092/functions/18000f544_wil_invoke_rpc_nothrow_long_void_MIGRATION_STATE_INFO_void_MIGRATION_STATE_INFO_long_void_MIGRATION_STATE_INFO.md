# wil::invoke_rpc_nothrow<long (&)(void *,_MIGRATION_STATE_INFO *),void * &,_MIGRATION_STATE_INFO * &>(long (&)(void *,_MIGRATION_STATE_INFO *),void * &,_MIGRATION_STATE_INFO * &)

- ea: `0x18000f544`
- end: `0x18000f5b3`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAU_MIGRATION_STATE_INFO@@@ZAEAPEAXAEAPEAU1@@wil@@YAJA6AJPEAXPEAU_MIGRATION_STATE_INFO@@@ZAEAPEAXAEAPEAU1@@Z`
- size: `111`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd50`

## callees

- `0x180006214`
- `0x180008504`
- `0x18000f544`

## string_xrefs

- `0x18000f564`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000f59a`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,_MIGRATION_STATE_INFO *),void * &,_MIGRATION_STATE_INFO * &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,unsigned long *),void * &,unsigned long * &>(MapsStorageSvcGetMigrationState);
  v1 = v0;
  if ( v0 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v0,
    v3);
  return v1;
}

```

## disassembly

```asm
0x18000f544  push    rbx; int
0x18000f546  sub     rsp, 20h
0x18000f54a  lea     rcx, MapsStorageSvcGetMigrationState
0x18000f551  call    ??$__invoke@A6AJPEAXPEAK@ZAEAPEAXAEAPEAK@wistd@@YAJA6AJPEAXPEAK@ZAEAPEAXAEAPEAK@Z; wistd::__invoke<long (&)(void *,ulong *),void * &,ulong * &>(long (&)(void *,ulong *),void * &,ulong * &)
0x18000f556  mov     ebx, eax
0x18000f558  test    eax, eax
0x18000f55a  jns     short loc_18000F579
0x18000f55c  mov     rcx, [rsp+28h]; this
0x18000f561  mov     r9d, eax; char *
0x18000f564  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f56b  mov     edx, 5Eh ; '^'; void *
0x18000f570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f575  mov     eax, ebx
0x18000f577  jmp     short loc_18000F5AD
0x18000f579  xor     eax, eax
0x18000f57b  jmp     short loc_18000F5AD
0x18000f57d  mov     ebx, eax
0x18000f57f  test    eax, eax
0x18000f581  js      short loc_18000F58E
0x18000f583  jle     short loc_18000F58E
0x18000f585  movzx   ebx, ax
0x18000f588  or      ebx, 80070000h
0x18000f58e  test    ebx, ebx
0x18000f590  jns     short loc_18000F5AB
0x18000f592  mov     rcx, [rsp+28h]; this
0x18000f597  mov     r9d, ebx; char *
0x18000f59a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f5a1  mov     edx, 63h ; 'c'; void *
0x18000f5a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5ab  mov     eax, ebx
0x18000f5ad  add     rsp, 20h
0x18000f5b1  pop     rbx
0x18000f5b2  retn
```
