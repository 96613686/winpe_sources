# ConfigLocationNonRootNode::QueryConfigLocationNodeType(void)

- ea: `0x18000a440`
- end: `0x18000a483`
- name: `?QueryConfigLocationNodeType@ConfigLocationNonRootNode@@UEAA?AV?$NamedEnum@W4ConfigLocationNodeType@@@@XZ`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000a440`
- `0x180014010`

## string_xrefs

- `0x18000a460`: `ConfigLocationNodeType_Intermediate`
- `0x18000a46f`: `ConfigLocationNodeType_Location`

## pseudocode

```c
__int64 __fastcall ConfigLocationNonRootNode::QueryConfigLocationNodeType(__int64 a1, __int64 a2)
{
  const wchar_t *v3; // rax

  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 80LL))(a1) )
  {
    *(_DWORD *)a2 = 3;
    v3 = L"ConfigLocationNodeType_Location";
  }
  else
  {
    *(_DWORD *)a2 = 2;
    v3 = L"ConfigLocationNodeType_Intermediate";
  }
  *(_QWORD *)(a2 + 8) = v3;
  return a2;
}

```

## disassembly

```asm
0x18000a440  push    rbx
0x18000a442  sub     rsp, 20h
0x18000a446  mov     rax, [rcx]
0x18000a449  mov     rbx, rdx
0x18000a44c  mov     rax, [rax+50h]
0x18000a450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a455  test    rax, rax
0x18000a458  jnz     short loc_18000A469
0x18000a45a  mov     dword ptr [rbx], 2
0x18000a460  lea     rax, aConfiglocation_1; "ConfigLocationNodeType_Intermediate"
0x18000a467  jmp     short loc_18000A476
0x18000a469  mov     dword ptr [rbx], 3
0x18000a46f  lea     rax, aConfiglocation_0; "ConfigLocationNodeType_Location"
0x18000a476  mov     [rbx+8], rax
0x18000a47a  mov     rax, rbx
0x18000a47d  add     rsp, 20h
0x18000a481  pop     rbx
0x18000a482  retn
```
