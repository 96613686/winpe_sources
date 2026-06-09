# ConfigPathTagNode::ConfigPathTagNode(void)

- ea: `0x180004288`
- end: `0x1800042e5`
- name: `??0ConfigPathTagNode@@IEAA@XZ`
- size: `93`
- prototype: `ConfigPathTagNode *__fastcall(ConfigPathTagNode *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180004164`
- `0x18000c9e8`

## string_xrefs

- `0x1800042c9`: `ConfigPathNodeType_Unknown`

## pseudocode

```c
ConfigPathTagNode *__fastcall ConfigPathTagNode::ConfigPathTagNode(ConfigPathTagNode *this)
{
  ConfigPathTagNode *result; // rax

  *((_DWORD *)this + 2) = -1;
  *((_DWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = (char *)this + 56;
  *((_QWORD *)this + 7) = (char *)this + 56;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 11) = 0;
  *(_QWORD *)this = &ConfigPathTagNode::`vftable';
  *((_BYTE *)this + 96) = 0;
  *((_QWORD *)this + 14) = L"ConfigPathNodeType_Unknown";
  result = this;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180004288  xor     edx, edx
0x18000428a  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x180004291  mov     [rcx+0Ch], edx
0x180004294  lea     rax, [rcx+38h]
0x180004298  mov     [rcx+10h], rdx
0x18000429c  mov     [rcx+18h], rdx
0x1800042a0  mov     [rcx+20h], rdx
0x1800042a4  mov     [rcx+28h], rdx
0x1800042a8  mov     [rcx+30h], rdx
0x1800042ac  mov     [rax+8], rax
0x1800042b0  mov     [rax], rax
0x1800042b3  lea     rax, ??_7ConfigPathTagNode@@6B@; const ConfigPathTagNode::`vftable'
0x1800042ba  mov     [rcx+50h], rdx
0x1800042be  mov     [rcx+48h], rdx
0x1800042c2  mov     [rcx+58h], rdx
0x1800042c6  mov     [rcx], rax
0x1800042c9  lea     rax, aConfigpathnode_4; "ConfigPathNodeType_Unknown"
0x1800042d0  mov     [rcx+60h], dl
0x1800042d3  mov     [rcx+70h], rax
0x1800042d7  mov     rax, rcx
0x1800042da  mov     [rcx+68h], edx
0x1800042dd  mov     [rcx+80h], rdx
0x1800042e4  retn
```
