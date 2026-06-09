# StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)

- ea: `0x180007b30`
- end: `0x180007bce`
- name: `?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180012cdc`
- `0x180029d24`
- `0x1800323d8`
- `0x1800337f8`
- `0x180039120`

## callees

- `0x180007b30`
- `0x180007c78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180007b8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180007b8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180007b63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180007b63`

## string_xrefs

- `0x180007ba2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Manager_NoThrow::Open(__int64 *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v6; // [rsp+28h] [rbp-20h] BYREF
  char v7; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( *a1 )
    return 0;
  v6 = 0;
  v7 = 1;
  v1 = SRCacheManager_Open(0, &v6);
  if ( v7 )
  {
    v2 = v6;
    v3 = *a1;
    *a1 = v6;
    if ( v3 )
      SRCacheManager_Close(v3, v2, a1);
  }
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
    (const char *)(unsigned int)v1,
    (int)a1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180007b30  sub     rsp, 48h
0x180007b34  cmp     qword ptr [rcx], 0
0x180007b38  jz      loc_180007BC7
0x180007b3e  mov     al, 1
0x180007b40  mov     [rsp+48h+var_8], rbx
0x180007b45  test    al, al
0x180007b47  jnz     short loc_180007BC3
0x180007b49  mov     qword ptr [rsp+48h+var_28], rcx; int
0x180007b4e  lea     rdx, [rsp+48h+var_20]
0x180007b53  xor     ecx, ecx
0x180007b55  mov     [rsp+48h+var_20], 0
0x180007b5e  mov     [rsp+48h+var_18], 1
0x180007b63  call    cs:__imp_SRCacheManager_Open
0x180007b6a  nop     dword ptr [rax+rax+00h]
0x180007b6f  cmp     [rsp+48h+var_18], 0
0x180007b74  mov     ebx, eax
0x180007b76  jz      short loc_180007B99
0x180007b78  mov     r8, qword ptr [rsp+48h+var_28]
0x180007b7d  mov     rdx, [rsp+48h+var_20]
0x180007b82  mov     rcx, [r8]
0x180007b85  mov     [r8], rdx
0x180007b88  test    rcx, rcx
0x180007b8b  jz      short loc_180007B99
0x180007b8d  call    cs:__imp_SRCacheManager_Close
0x180007b94  nop     dword ptr [rax+rax+00h]
0x180007b99  test    ebx, ebx
0x180007b9b  jns     short loc_180007BC3
0x180007b9d  mov     rcx, [rsp+48h]; this
0x180007ba2  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007ba9  mov     r9d, ebx; char *
0x180007bac  mov     edx, 0A5h; void *
0x180007bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bb6  mov     eax, ebx
0x180007bb8  mov     rbx, [rsp+48h+var_8]
0x180007bbd  add     rsp, 48h
0x180007bc1  retn
0x180007bc3  xor     eax, eax
0x180007bc5  jmp     short loc_180007BB8
0x180007bc7  xor     al, al
0x180007bc9  jmp     loc_180007B40
```
