# FveBcdUtil::GetCurrentOsGuid(void *,_GUID *)

- ea: `0x18006b260`
- end: `0x18006b2e1`
- name: `?GetCurrentOsGuid@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006ad70`

## callees

- `0x18001b890`
- `0x18006b260`

## import_xrefs

- `bcd!BcdOpenObject` at `0x18006b282`
- `bcd!BcdOpenObject` at `0x18006b282`
- `bcd!BcdQueryObject` at `0x18006b2a8`
- `bcd!BcdQueryObject` at `0x18006b2a8`
- `bcd!BcdCloseObject` at `0x18006b2c7`
- `bcd!BcdCloseObject` at `0x18007d2d1`
- `bcd!BcdCloseObject` at `0x18006b2c7`
- `bcd!BcdCloseObject` at `0x18007d2d1`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetCurrentOsGuid(void *a1, struct _GUID *a2)
{
  int v3; // eax
  int v4; // ebx
  int Object; // eax
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v3 = BcdOpenObject(a1, &GUID_CURRENT_BOOT_ENTRY, &v7);
  v4 = FromNtStatus(v3);
  if ( v4 >= 0 )
  {
    Object = BcdQueryObject(v7, 0, 0, a2);
    v4 = FromNtStatus(Object);
  }
  if ( v7 )
    BcdCloseObject(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006b260  mov     [rsp+arg_0], rbx
0x18006b265  push    rdi
0x18006b266  sub     rsp, 20h
0x18006b26a  mov     rdi, rdx
0x18006b26d  mov     [rsp+28h+arg_10], 0
0x18006b276  lea     r8, [rsp+28h+arg_10]
0x18006b27b  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18006b282  call    cs:__imp_BcdOpenObject
0x18006b289  nop     dword ptr [rax+rax+00h]
0x18006b28e  mov     ecx, eax; int
0x18006b290  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006b295  mov     ebx, eax
0x18006b297  test    eax, eax
0x18006b299  js      short loc_18006B2BD
0x18006b29b  mov     r9, rdi
0x18006b29e  xor     r8d, r8d
0x18006b2a1  xor     edx, edx
0x18006b2a3  mov     rcx, [rsp+28h+arg_10]
0x18006b2a8  call    cs:__imp_BcdQueryObject
0x18006b2af  nop     dword ptr [rax+rax+00h]
0x18006b2b4  mov     ecx, eax; int
0x18006b2b6  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006b2bb  mov     ebx, eax
0x18006b2bd  mov     rcx, [rsp+28h+arg_10]
0x18006b2c2  test    rcx, rcx
0x18006b2c5  jz      short loc_18006B2D3
0x18006b2c7  call    cs:__imp_BcdCloseObject
0x18006b2ce  nop     dword ptr [rax+rax+00h]
0x18006b2d3  mov     eax, ebx
0x18006b2d5  mov     rbx, [rsp+28h+arg_0]
0x18006b2da  add     rsp, 20h
0x18006b2de  pop     rdi
0x18006b2df  retn
0x18007d2bf  push    rbp
0x18007d2c1  sub     rsp, 20h
0x18007d2c5  mov     rbp, rdx
0x18007d2c8  mov     rcx, [rbp+40h]
0x18007d2cc  test    rcx, rcx
0x18007d2cf  jz      short loc_18007D2DE
0x18007d2d1  call    cs:__imp_BcdCloseObject
0x18007d2d8  nop     dword ptr [rax+rax+00h]
0x18007d2dd  nop
0x18007d2de  add     rsp, 20h
0x18007d2e2  pop     rbp
0x18007d2e3  retn
```
