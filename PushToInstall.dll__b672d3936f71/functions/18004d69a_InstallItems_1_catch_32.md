# _InstallItems_::_1_::catch$32

- ea: `0x18004d69a`
- end: `0x18004d716`
- name: `_InstallItems_::_1_::catch$32`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18002c4b8`
- `0x18004d69a`

## string_xrefs

- `0x18004d6f4`: `onecoreuap\enduser\winstore\pushtoinstall\lib\pushtoinstall.cpp`
- `0x18004d6e7`: `InstallItems`
- `0x18004d6cd`: `Installation failed for item with storeId %s, isInteractive = %u`

## pseudocode

```c
__int64 __fastcall InstallItems_::_1_::catch_32(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  BOOL v3; // ecx
  _QWORD *v4; // rax
  BOOL v6; // [rsp+38h] [rbp-40h]

  v2 = *(_QWORD *)(a2 + 192);
  v3 = *(_BYTE *)(v2 + 64) != 0;
  v4 = (_QWORD *)(v2 + 32);
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  v6 = v3;
  LogMessage(
    1u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\pushtoinstall.cpp",
    0x4Au,
    "InstallItems",
    *(_DWORD *)(*(_QWORD *)(a2 + 256) + 32LL),
    L"Installation failed for item with storeId %s, isInteractive = %u",
    v4,
    v6);
  return 0;
}

```

## disassembly

```asm
0x18004d69a  mov     [rsp+arg_8], rdx
0x18004d69f  push    rbp
0x18004d6a0  sub     rsp, 70h
0x18004d6a4  mov     rbp, rdx
0x18004d6a7  xor     ecx, ecx
0x18004d6a9  mov     rax, [rbp+0C0h]
0x18004d6b0  cmp     [rax+40h], cl
0x18004d6b3  setnz   cl
0x18004d6b6  add     rax, 20h ; ' '
0x18004d6ba  cmp     qword ptr [rax+18h], 7
0x18004d6bf  jbe     short loc_18004D6C4
0x18004d6c1  mov     rax, [rax]
0x18004d6c4  mov     dword ptr [rsp+78h+var_40], ecx
0x18004d6c8  mov     [rsp+78h+var_48], rax
0x18004d6cd  lea     rax, aInstallationFa; "Installation failed for item with store"...
0x18004d6d4  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x18004d6d9  mov     rax, [rbp+100h]
0x18004d6e0  mov     ecx, [rax+20h]
0x18004d6e3  mov     [rsp+78h+var_58], ecx; int
0x18004d6e7  lea     r9, aInstallitems; "InstallItems"
0x18004d6ee  mov     r8d, 4Ah ; 'J'; unsigned int
0x18004d6f4  lea     rdx, aOnecoreuapEndu_9; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18004d6fb  lea     ecx, [r8-49h]; unsigned int
0x18004d6ff  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x18004d704  nop
0x18004d705  mov     rax, 0
0x18004d70f  add     rsp, 70h
0x18004d713  pop     rbp
0x18004d714  retn
```
