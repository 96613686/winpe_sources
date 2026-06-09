# WmiSecurity::DestructAbsoluteSD(void *)

- ea: `0x140006b2c`
- end: `0x140006bae`
- name: `?DestructAbsoluteSD@WmiSecurity@@AEAAXPEAX@Z`
- size: `130`
- prototype: `void __fastcall(WmiSecurity *__hidden this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000653c`
- `0x140006894`

## callees

- `0x140006b2c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b3e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b55`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b83`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b9a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b3e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b55`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b83`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006b9a`

## pseudocode

```c
void __fastcall WmiSecurity::DestructAbsoluteSD(WmiSecurity *this, void *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CWin32DefaultArena::WbemMemFree(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    CWin32DefaultArena::WbemMemFree(v4);
    *((_QWORD *)this + 3) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    CWin32DefaultArena::WbemMemFree(v5);
    *((_QWORD *)this + 4) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    CWin32DefaultArena::WbemMemFree(v6);
    *((_QWORD *)this + 5) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    CWin32DefaultArena::WbemMemFree(v7);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x140006b2c  push    rbx
0x140006b2e  sub     rsp, 20h
0x140006b32  mov     rbx, rcx
0x140006b35  mov     rcx, [rcx+10h]
0x140006b39  test    rcx, rcx
0x140006b3c  jz      short loc_140006B4C
0x140006b3e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006b44  mov     qword ptr [rbx+10h], 0
0x140006b4c  mov     rcx, [rbx+18h]
0x140006b50  test    rcx, rcx
0x140006b53  jz      short loc_140006B63
0x140006b55  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006b5b  mov     qword ptr [rbx+18h], 0
0x140006b63  mov     rcx, [rbx+20h]
0x140006b67  test    rcx, rcx
0x140006b6a  jz      short loc_140006B7A
0x140006b6c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006b72  mov     qword ptr [rbx+20h], 0
0x140006b7a  mov     rcx, [rbx+28h]
0x140006b7e  test    rcx, rcx
0x140006b81  jz      short loc_140006B91
0x140006b83  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006b89  mov     qword ptr [rbx+28h], 0
0x140006b91  mov     rcx, [rbx+8]
0x140006b95  test    rcx, rcx
0x140006b98  jz      short loc_140006BA8
0x140006b9a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006ba0  mov     qword ptr [rbx+8], 0
0x140006ba8  add     rsp, 20h
0x140006bac  pop     rbx
0x140006bad  retn
```
