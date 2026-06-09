# ApplicationElementCollectionProcessor::GetContextNode(ConfigPathNavigationTree *)

- ea: `0x18000c8cc`
- end: `0x18000c960`
- name: `?GetContextNode@ApplicationElementCollectionProcessor@@QEAAPEAVConfigPathTagNode@@PEAVConfigPathNavigationTree@@@Z`
- size: `148`
- prototype: `struct ConfigPathTagNode *__fastcall(ApplicationElementCollectionProcessor *__hidden this, struct ConfigPathNavigationTree *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d430`

## callees

- `0x18000c8cc`
- `0x18000c9bc`

## string_xrefs

- `0x18000c8fc`: `ConfigPathNodeType_Site`
- `0x18000c928`: `ConfigPathNodeType_Application`

## pseudocode

```c
struct ConfigPathTagNode *__fastcall ApplicationElementCollectionProcessor::GetContextNode(
        ApplicationElementCollectionProcessor *this,
        struct ConfigPathNavigationTree *a2)
{
  struct ConfigPathTagNode *result; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r8
  int v10; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v11; // [rsp+28h] [rbp-10h]

  result = (struct ConfigPathTagNode *)*((_QWORD *)this + 3);
  if ( !result )
  {
    v5 = (_QWORD *)*((_QWORD *)this + 1);
    v6 = v5[3];
    if ( !v6 )
    {
      v7 = v5[1];
      v8 = v5[2];
      v10 = 5;
      v11 = L"ConfigPathNodeType_Site";
      v6 = ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(*(_QWORD *)(v7 + 8), a2, v8, &v10);
      v5[3] = v6;
    }
    v9 = *((_QWORD *)this + 2);
    v11 = L"ConfigPathNodeType_Application";
    v10 = 6;
    result = (struct ConfigPathTagNode *)ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(v6, a2, v9, &v10);
    *((_QWORD *)this + 3) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000c8cc  mov     r11, rsp
0x18000c8cf  mov     [r11+8], rbx
0x18000c8d3  mov     [r11+10h], rsi
0x18000c8d7  push    rdi
0x18000c8d8  sub     rsp, 30h
0x18000c8dc  mov     rax, [rcx+18h]
0x18000c8e0  mov     rsi, rdx
0x18000c8e3  mov     rbx, rcx
0x18000c8e6  test    rax, rax
0x18000c8e9  jnz     short loc_18000C950
0x18000c8eb  mov     rdi, [rcx+8]
0x18000c8ef  mov     rax, [rdi+18h]
0x18000c8f3  test    rax, rax
0x18000c8f6  jnz     short loc_18000C924
0x18000c8f8  mov     rcx, [rdi+8]
0x18000c8fc  lea     rax, aConfigpathnode_1; "ConfigPathNodeType_Site"
0x18000c903  mov     r8, [rdi+10h]
0x18000c907  lea     r9, [r11-18h]
0x18000c90b  mov     [rsp+38h+var_18], 5
0x18000c913  mov     [r11-10h], rax
0x18000c917  mov     rcx, [rcx+8]
0x18000c91b  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000c920  mov     [rdi+18h], rax
0x18000c924  mov     r8, [rbx+10h]
0x18000c928  lea     rcx, aConfigpathnode_9; "ConfigPathNodeType_Application"
0x18000c92f  mov     [rsp+38h+var_10], rcx
0x18000c934  lea     r9, [rsp+38h+var_18]
0x18000c939  mov     rcx, rax
0x18000c93c  mov     [rsp+38h+var_18], 6
0x18000c944  mov     rdx, rsi
0x18000c947  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000c94c  mov     [rbx+18h], rax
0x18000c950  mov     rbx, [rsp+38h+arg_0]
0x18000c955  mov     rsi, [rsp+38h+arg_8]
0x18000c95a  add     rsp, 30h
0x18000c95e  pop     rdi
0x18000c95f  retn
```
