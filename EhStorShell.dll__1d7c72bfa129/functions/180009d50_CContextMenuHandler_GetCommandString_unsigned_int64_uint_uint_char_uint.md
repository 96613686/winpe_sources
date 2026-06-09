# CContextMenuHandler::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x180009d50`
- end: `0x180009d89`
- name: `?GetCommandString@CContextMenuHandler@@UEAAJ_KIPEAIPEADI@Z`
- size: `57`
- prototype: `__int64 __fastcall(CContextMenuHandler *this, __int64, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000684c`
- `0x180009d50`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::GetCommandString(
        CContextMenuHandler *this,
        __int64 a2,
        __int64 a3,
        unsigned int *a4)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
  return 0;
}

```

## disassembly

```asm
0x180009d50  sub     rsp, 28h
0x180009d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d5b  lea     rax, WPP_GLOBAL_Control
0x180009d62  cmp     rcx, rax
0x180009d65  jz      short loc_180009D82
0x180009d67  test    byte ptr [rcx+1Ch], 20h
0x180009d6b  jz      short loc_180009D82
0x180009d6d  mov     rcx, [rcx+10h]
0x180009d71  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009d78  mov     edx, 17h
0x180009d7d  call    WPP_SF_
0x180009d82  xor     eax, eax
0x180009d84  add     rsp, 28h
0x180009d88  retn
```
