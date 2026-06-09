# CspRemoveCachedPin

- ea: `0x18001e86c`
- end: `0x18001e9af`
- name: `CspRemoveCachedPin`
- size: `323`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c6ac`
- `0x1800102a8`
- `0x180013420`
- `0x180022c80`
- `0x180026fdc`

## callees

- `0x18000a772`
- `0x180017bac`
- `0x180019650`
- `0x18001c71c`
- `0x18001e86c`
- `0x1800226f8`
- `0x18002a798`
- `0x18002cfa0`

## string_xrefs

- `0x18001e8fc`: `Cached_Pin`

## pseudocode

```c
char *__fastcall CspRemoveCachedPin(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  char *result; // rax
  int v9; // [rsp+20h] [rbp-278h]
  __int64 v10; // [rsp+30h] [rbp-268h] BYREF
  int v11; // [rsp+38h] [rbp-260h]
  int v12; // [rsp+3Ch] [rbp-25Ch]
  wchar_t pszDest[278]; // [rsp+44h] [rbp-254h] BYREF

  memset_0(&v10, 0, 0x238u);
  WppTraceIndent(v6, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  memset_0(&v10, 0, 0x238u);
  v9 = a2;
  StringCbPrintfW(pszDest, 0x104u, L"%s\\%d", L"Cached_Pin", v9);
  v11 = 1;
  v12 = 1;
  v10 = a1;
  MyCacheDeleteItem(&v10);
  PinCacheFlush(a1 + 584, a2, a3);
  result = WppTraceIndent(v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    return (char *)WPP_SF_s(
                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                     19,
                     WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
                     WPP_pszIndent);
  }
  return result;
}

```

## disassembly

```asm
0x18001e86c  mov     [rsp+arg_10], rbx
0x18001e871  push    rsi
0x18001e872  push    rdi
0x18001e873  push    r14
0x18001e875  sub     rsp, 280h
0x18001e87c  mov     rax, cs:__security_cookie
0x18001e883  xor     rax, rsp
0x18001e886  mov     [rsp+298h+var_28], rax
0x18001e88e  mov     esi, r8d
0x18001e891  mov     edi, edx
0x18001e893  mov     rbx, rcx
0x18001e896  xor     edx, edx; Val
0x18001e898  mov     r8d, 238h; Size
0x18001e89e  lea     rcx, [rsp+298h+var_268]; void *
0x18001e8a3  call    memset_0
0x18001e8a8  xor     edx, edx
0x18001e8aa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e8af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8b6  lea     r14, WPP_GLOBAL_Control
0x18001e8bd  cmp     rcx, r14
0x18001e8c0  jz      short loc_18001E8EA
0x18001e8c2  test    byte ptr [rcx+1Ch], 2
0x18001e8c6  jz      short loc_18001E8EA
0x18001e8c8  cmp     byte ptr [rcx+19h], 5
0x18001e8cc  jb      short loc_18001E8EA
0x18001e8ce  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001e8d5  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001e8dc  mov     rcx, [rcx+10h]
0x18001e8e0  mov     edx, 12h
0x18001e8e5  call    WPP_SF_s
0x18001e8ea  xor     edx, edx; Val
0x18001e8ec  lea     rcx, [rsp+298h+var_268]; void *
0x18001e8f1  mov     r8d, 238h; Size
0x18001e8f7  call    memset_0
0x18001e8fc  lea     r9, aCachedPin; "Cached_Pin"
0x18001e903  mov     [rsp+298h+var_278], edi
0x18001e907  lea     r8, aSD; "%s\\%d"
0x18001e90e  mov     edx, 104h; cbDest
0x18001e913  lea     rcx, [rsp+298h+pszDest]; pszDest
0x18001e918  call    StringCbPrintfW
0x18001e91d  lea     rcx, [rsp+298h+var_268]
0x18001e922  mov     [rsp+298h+var_260], 1
0x18001e92a  mov     [rsp+298h+var_25C], 1
0x18001e932  mov     [rsp+298h+var_268], rbx
0x18001e937  call    MyCacheDeleteItem
0x18001e93c  lea     rcx, [rbx+248h]
0x18001e943  mov     r8d, esi
0x18001e946  mov     edx, edi
0x18001e948  call    PinCacheFlush
0x18001e94d  mov     edx, 1
0x18001e952  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001e957  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e95e  cmp     rcx, r14
0x18001e961  jz      short loc_18001E98B
0x18001e963  test    byte ptr [rcx+1Ch], 2
0x18001e967  jz      short loc_18001E98B
0x18001e969  cmp     byte ptr [rcx+19h], 5
0x18001e96d  jb      short loc_18001E98B
0x18001e96f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001e976  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001e97d  mov     rcx, [rcx+10h]
0x18001e981  mov     edx, 13h
0x18001e986  call    WPP_SF_s
0x18001e98b  mov     rcx, [rsp+298h+var_28]
0x18001e993  xor     rcx, rsp; StackCookie
0x18001e996  call    __security_check_cookie
0x18001e99b  mov     rbx, [rsp+298h+arg_10]
0x18001e9a3  add     rsp, 280h
0x18001e9aa  pop     r14
0x18001e9ac  pop     rdi
0x18001e9ad  pop     rsi
0x18001e9ae  retn
```
