# AiInitializeConfiguration

- ea: `0x1400253ac`
- end: `0x140025447`
- name: `AiInitializeConfiguration`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140038a54`

## callees

- `0x1400253ac`
- `0x1400293ac`

## string_xrefs

- `0x1400253b5`: `\Registry\Machine\System\CurrentControlSet\Control\AppID\Configuration`

## pseudocode

```c
__int64 __fastcall AiInitializeConfiguration(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rcx
  __int64 result; // rax
  _QWORD v4[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v5[2]; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v6[2]; // [rsp+40h] [rbp-10h] BYREF
  int v7; // [rsp+60h] [rbp+10h] BYREF

  v4[0] = 9306252;
  v4[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\AppID\\Configuration";
  v5[0] = 1966108;
  v5[1] = L"UsePublisherId";
  v6[0] = 2883626;
  v6[1] = L"UseSystemIdentityOnly";
  v7 = 0;
  v1 = AiRegReadDwordValue(a1, v4, v5, &v7);
  AiEnablePublisherId = 0;
  if ( v1 >= 0 )
    AiEnablePublisherId = v7 == 1;
  result = AiRegReadDwordValue(v2, v4, v6, &v7);
  if ( (int)result >= 0 && v7 == 1 )
    AiUseSystemAppIdentityOnly = 1;
  return result;
}

```

## disassembly

```asm
0x1400253ac  push    rbp
0x1400253ae  mov     rbp, rsp
0x1400253b1  sub     rsp, 50h
0x1400253b5  lea     rax, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400253bc  mov     [rbp+var_30], 8E008Ch
0x1400253c4  mov     [rbp+var_28], rax
0x1400253c8  lea     r9, [rbp+arg_0]
0x1400253cc  lea     rax, aUsepublisherid; "UsePublisherId"
0x1400253d3  mov     [rbp+var_20], 1E001Ch
0x1400253db  mov     [rbp+var_18], rax
0x1400253df  lea     r8, [rbp+var_20]
0x1400253e3  lea     rax, aUsesystemident; "UseSystemIdentityOnly"
0x1400253ea  mov     [rbp+var_10], 2C002Ah
0x1400253f2  lea     rdx, [rbp+var_30]
0x1400253f6  mov     [rbp+var_8], rax
0x1400253fa  mov     [rbp+arg_0], 0
0x140025401  call    AiRegReadDwordValue
0x140025406  mov     cs:AiEnablePublisherId, 0
0x14002540d  test    eax, eax
0x14002540f  js      short loc_14002541E
0x140025411  cmp     [rbp+arg_0], 1
0x140025415  jnz     short loc_14002541E
0x140025417  mov     cs:AiEnablePublisherId, 1
0x14002541e  lea     r9, [rbp+arg_0]
0x140025422  lea     r8, [rbp+var_10]
0x140025426  lea     rdx, [rbp+var_30]
0x14002542a  call    AiRegReadDwordValue
0x14002542f  test    eax, eax
0x140025431  js      short loc_140025440
0x140025433  cmp     [rbp+arg_0], 1
0x140025437  jnz     short loc_140025440
0x140025439  mov     cs:AiUseSystemAppIdentityOnly, 1
0x140025440  add     rsp, 50h
0x140025444  pop     rbp
0x140025445  retn
```
