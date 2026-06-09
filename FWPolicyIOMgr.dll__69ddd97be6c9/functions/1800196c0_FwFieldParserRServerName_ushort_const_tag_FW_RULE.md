# FwFieldParserRServerName(ushort const *,_tag_FW_RULE *)

- ea: `0x1800196c0`
- end: `0x180019783`
- name: `?FwFieldParserRServerName@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800042c4`
- `0x1800196c0`
- `0x18001978c`
- `0x18001f650`

## import_xrefs

- `fwbase!FwFree` at `0x180019763`
- `fwbase!FwFree` at `0x180019763`
- `fwbase!FwStringCanonicalizeCopy` at `0x1800196ea`
- `fwbase!FwStringCanonicalizeCopy` at `0x1800196ea`

## pseudocode

```c
__int64 __fastcall FwFieldParserRServerName(const unsigned __int16 *a1, struct _tag_FW_RULE *a2)
{
  int v3; // ebx
  LPCOLESTR v4; // rcx
  __int64 v5; // rdx
  unsigned __int16 *v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v3 = FwStringCanonicalizeCopy(a1, &v7);
  if ( v3 >= 0 )
  {
    v3 = FwFieldParserNameValue(v7, (struct _tag_FW_RULE *)((char *)a2 + 432));
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v5 = 21;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v5 = 20;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v3);
    }
  }
  FwFree(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800196c0  mov     [rsp+arg_10], rbx
0x1800196c5  push    rdi
0x1800196c6  sub     rsp, 30h
0x1800196ca  mov     rax, cs:__security_cookie
0x1800196d1  xor     rax, rsp
0x1800196d4  mov     [rsp+38h+var_10], rax
0x1800196d9  mov     rdi, rdx
0x1800196dc  mov     [rsp+38h+var_18], 0
0x1800196e5  lea     rdx, [rsp+38h+var_18]
0x1800196ea  call    cs:__imp_FwStringCanonicalizeCopy
0x1800196f0  mov     ebx, eax
0x1800196f2  test    eax, eax
0x1800196f4  jns     short loc_180019716
0x1800196f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196fd  lea     rax, WPP_GLOBAL_Control
0x180019704  cmp     rcx, rax
0x180019707  jz      short loc_18001975E
0x180019709  test    byte ptr [rcx+1Ch], 1
0x18001970d  jz      short loc_18001975E
0x18001970f  mov     edx, 14h
0x180019714  jmp     short loc_18001974B
0x180019716  mov     rcx, [rsp+38h+var_18]; unsigned __int16 *
0x18001971b  lea     rdx, [rdi+1B0h]; struct _tag_FW_NETWORK_NAMES *
0x180019722  call    ?FwFieldParserNameValue@@YAJPEBGPEAU_tag_FW_NETWORK_NAMES@@@Z; FwFieldParserNameValue(ushort const *,_tag_FW_NETWORK_NAMES *)
0x180019727  mov     ebx, eax
0x180019729  test    eax, eax
0x18001972b  jns     short loc_18001975E
0x18001972d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019734  lea     rax, WPP_GLOBAL_Control
0x18001973b  cmp     rcx, rax
0x18001973e  jz      short loc_18001975E
0x180019740  test    byte ptr [rcx+1Ch], 1
0x180019744  jz      short loc_18001975E
0x180019746  mov     edx, 15h
0x18001974b  mov     rcx, [rcx+10h]
0x18001974f  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180019756  mov     r9d, ebx
0x180019759  call    WPP_SF_d
0x18001975e  mov     rcx, [rsp+38h+var_18]
0x180019763  call    cs:__imp_FwFree
0x180019769  mov     eax, ebx
0x18001976b  mov     rcx, [rsp+38h+var_10]
0x180019770  xor     rcx, rsp; StackCookie
0x180019773  call    __security_check_cookie
0x180019778  mov     rbx, [rsp+38h+arg_10]
0x18001977d  add     rsp, 30h
0x180019781  pop     rdi
0x180019782  retn
```
