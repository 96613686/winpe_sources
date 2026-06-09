# _parseProviderNode

- ea: `0x18000bf80`
- end: `0x18000c047`
- name: `_parseProviderNode`
- size: `199`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b880`

## callees

- `0x18000bf80`
- `0x180012bc8`

## pseudocode

```c
__int64 __fastcall parseProviderNode(struct IXMLDOMNode *a1, unsigned __int16 *a2, unsigned int a3)
{
  const unsigned __int16 *v6; // rdx
  __int64 result; // rax
  const unsigned __int16 *v8; // rdx

  if ( a3 < 3 )
  {
    v6 = L"MBNProfileV4:ProviderID";
    if ( a3 != 2 )
      v6 = L"MBNProfile:ProviderID";
  }
  else
  {
    v6 = L"MBNProfileV9:ProviderID";
  }
  result = XcGetNodeStringValue(a1, v6, a2, 7u, 0, 0, 0);
  if ( !(_DWORD)result )
  {
    if ( a3 < 3 )
    {
      v8 = L"MBNProfileV4:ProviderName";
      if ( a3 != 2 )
        v8 = L"MBNProfile:ProviderName";
    }
    else
    {
      v8 = L"MBNProfileV9:ProviderName";
    }
    return XcGetNodeStringValue(a1, v8, a2 + 7, 0x15u, 0, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000bf80  mov     [rsp+arg_0], rbx
0x18000bf85  mov     [rsp+arg_8], rsi
0x18000bf8a  push    rdi
0x18000bf8b  sub     rsp, 40h
0x18000bf8f  mov     ebx, r8d
0x18000bf92  mov     rdi, rdx
0x18000bf95  mov     rsi, rcx
0x18000bf98  cmp     r8d, 3
0x18000bf9c  jb      short loc_18000BFA7
0x18000bf9e  lea     rdx, aMbnprofilev9Pr_2; "MBNProfileV9:ProviderID"
0x18000bfa5  jmp     short loc_18000BFBC
0x18000bfa7  cmp     ebx, 2
0x18000bfaa  lea     rdx, aMbnprofilev4Pr_1; "MBNProfileV4:ProviderID"
0x18000bfb1  lea     rax, aMbnprofileProv_1; "MBNProfile:ProviderID"
0x18000bfb8  cmovnz  rdx, rax; unsigned __int16 *
0x18000bfbc  mov     [rsp+48h+var_18], 0; int *
0x18000bfc5  mov     r9d, 7; unsigned __int64
0x18000bfcb  mov     [rsp+48h+var_20], 0; unsigned __int16 *
0x18000bfd4  mov     r8, rdi; unsigned __int16 *
0x18000bfd7  mov     [rsp+48h+var_28], 0; int
0x18000bfdf  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000bfe4  test    eax, eax
0x18000bfe6  jnz     short loc_18000C037
0x18000bfe8  cmp     ebx, 3
0x18000bfeb  jb      short loc_18000BFF6
0x18000bfed  lea     rdx, aMbnprofilev9Pr_4; "MBNProfileV9:ProviderName"
0x18000bff4  jmp     short loc_18000C00B
0x18000bff6  cmp     ebx, 2
0x18000bff9  lea     rdx, aMbnprofilev4Pr_4; "MBNProfileV4:ProviderName"
0x18000c000  lea     rax, aMbnprofileProv; "MBNProfile:ProviderName"
0x18000c007  cmovnz  rdx, rax; unsigned __int16 *
0x18000c00b  mov     [rsp+48h+var_18], 0; int *
0x18000c014  lea     r8, [rdi+0Eh]; unsigned __int16 *
0x18000c018  mov     [rsp+48h+var_20], 0; unsigned __int16 *
0x18000c021  mov     r9d, 15h; unsigned __int64
0x18000c027  mov     rcx, rsi; struct IXMLDOMNode *
0x18000c02a  mov     [rsp+48h+var_28], 0; int
0x18000c032  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c037  mov     rbx, [rsp+48h+arg_0]
0x18000c03c  mov     rsi, [rsp+48h+arg_8]
0x18000c041  add     rsp, 40h
0x18000c045  pop     rdi
0x18000c046  retn
```
