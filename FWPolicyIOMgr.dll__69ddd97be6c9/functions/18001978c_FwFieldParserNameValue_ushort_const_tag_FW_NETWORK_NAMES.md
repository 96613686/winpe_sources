# FwFieldParserNameValue(ushort const *,_tag_FW_NETWORK_NAMES *)

- ea: `0x18001978c`
- end: `0x180019858`
- name: `?FwFieldParserNameValue@@YAJPEBGPEAU_tag_FW_NETWORK_NAMES@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_NETWORK_NAMES *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800196c0`

## callees

- `0x1800042c4`
- `0x18001978c`
- `0x18001f650`

## import_xrefs

- `fwbase!FwFree` at `0x180019838`
- `fwbase!FwFree` at `0x180019838`
- `fwbase!FwStringCopy` at `0x1800197b6`
- `fwbase!FwStringCopy` at `0x1800197b6`
- `fwbase!FwArrayAppend` at `0x1800197f6`
- `fwbase!FwArrayAppend` at `0x1800197f6`

## pseudocode

```c
__int64 __fastcall FwFieldParserNameValue(const unsigned __int16 *a1, struct _tag_FW_NETWORK_NAMES *a2)
{
  int v3; // ebx
  LPCOLESTR v4; // rcx
  __int64 v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v3 = FwStringCopy(a1, &v7);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v5 = 16;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v3);
LABEL_10:
    FwFree(v7);
    return (unsigned int)v3;
  }
  v3 = FwArrayAppend(8, FwCopyIPv4SubNet, a2, &v7);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v5 = 17;
    goto LABEL_9;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001978c  mov     [rsp+arg_10], rbx
0x180019791  push    rdi
0x180019792  sub     rsp, 30h
0x180019796  mov     rax, cs:__security_cookie
0x18001979d  xor     rax, rsp
0x1800197a0  mov     [rsp+38h+var_10], rax
0x1800197a5  mov     rdi, rdx
0x1800197a8  mov     [rsp+38h+var_18], 0
0x1800197b1  lea     rdx, [rsp+38h+var_18]
0x1800197b6  call    cs:__imp_FwStringCopy
0x1800197bc  mov     ebx, eax
0x1800197be  test    eax, eax
0x1800197c0  jns     short loc_1800197E2
0x1800197c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197c9  lea     rax, WPP_GLOBAL_Control
0x1800197d0  cmp     rcx, rax
0x1800197d3  jz      short loc_180019833
0x1800197d5  test    byte ptr [rcx+1Ch], 1
0x1800197d9  jz      short loc_180019833
0x1800197db  mov     edx, 10h
0x1800197e0  jmp     short loc_180019820
0x1800197e2  lea     r9, [rsp+38h+var_18]
0x1800197e7  mov     r8, rdi
0x1800197ea  lea     rdx, FwCopyIPv4SubNet
0x1800197f1  mov     ecx, 8
0x1800197f6  call    cs:__imp_FwArrayAppend
0x1800197fc  mov     ebx, eax
0x1800197fe  test    eax, eax
0x180019800  jns     short loc_18001983E
0x180019802  mov     rcx, cs:WPP_GLOBAL_Control
0x180019809  lea     rax, WPP_GLOBAL_Control
0x180019810  cmp     rcx, rax
0x180019813  jz      short loc_180019833
0x180019815  test    byte ptr [rcx+1Ch], 1
0x180019819  jz      short loc_180019833
0x18001981b  mov     edx, 11h
0x180019820  mov     rcx, [rcx+10h]
0x180019824  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x18001982b  mov     r9d, ebx
0x18001982e  call    WPP_SF_d
0x180019833  mov     rcx, [rsp+38h+var_18]
0x180019838  call    cs:__imp_FwFree
0x18001983e  mov     eax, ebx
0x180019840  mov     rcx, [rsp+38h+var_10]
0x180019845  xor     rcx, rsp; StackCookie
0x180019848  call    __security_check_cookie
0x18001984d  mov     rbx, [rsp+38h+arg_10]
0x180019852  add     rsp, 30h
0x180019856  pop     rdi
0x180019857  retn
```
