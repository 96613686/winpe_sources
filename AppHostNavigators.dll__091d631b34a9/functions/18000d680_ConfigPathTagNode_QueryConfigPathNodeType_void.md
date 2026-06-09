# ConfigPathTagNode::QueryConfigPathNodeType(void)

- ea: `0x18000d680`
- end: `0x18000d6a5`
- name: `?QueryConfigPathNodeType@ConfigPathTagNode@@UEAA?AV?$NamedEnum@W4ConfigPathNodeType@@@@XZ`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d680`

## string_xrefs

- `0x18000d686`: `ConfigPathNodeType_Location`

## pseudocode

```c
__int64 __fastcall ConfigPathTagNode::QueryConfigPathNodeType(__int64 a1, __int64 a2)
{
  if ( *(_DWORD *)(a1 + 104) )
  {
    *(_OWORD *)a2 = *(_OWORD *)(a1 + 104);
  }
  else
  {
    *(_DWORD *)a2 = 10;
    *(_QWORD *)(a2 + 8) = L"ConfigPathNodeType_Location";
  }
  return a2;
}

```

## disassembly

```asm
0x18000d680  cmp     dword ptr [rcx+68h], 0
0x18000d684  jnz     short loc_18000D699
0x18000d686  lea     rax, aConfigpathnode_6; "ConfigPathNodeType_Location"
0x18000d68d  mov     dword ptr [rdx], 0Ah
0x18000d693  mov     [rdx+8], rax
0x18000d697  jmp     short loc_18000D6A1
0x18000d699  movups  xmm0, xmmword ptr [rcx+68h]
0x18000d69d  movdqu  xmmword ptr [rdx], xmm0
0x18000d6a1  mov     rax, rdx
0x18000d6a4  retn
```
