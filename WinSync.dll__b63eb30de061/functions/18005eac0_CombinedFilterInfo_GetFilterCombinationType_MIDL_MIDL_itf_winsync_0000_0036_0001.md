# CombinedFilterInfo::GetFilterCombinationType(__MIDL___MIDL_itf_winsync_0000_0036_0001 *)

- ea: `0x18005eac0`
- end: `0x18005eb6e`
- name: `?GetFilterCombinationType@CombinedFilterInfo@@UEAAJPEAW4__MIDL___MIDL_itf_winsync_0000_0036_0001@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(CombinedFilterInfo *__hidden this, enum __MIDL___MIDL_itf_winsync_0000_0036_0001 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18005eac0`

## string_xrefs

- `0x18005eaf5`: `CombinedFilterInfo::GetFilterCombinationType`
- `0x18005eb40`: `CombinedFilterInfo::GetFilterCombinationType`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::GetFilterCombinationType(
        CombinedFilterInfo *this,
        enum __MIDL___MIDL_itf_winsync_0000_0036_0001 *a2)
{
  PVOID *v3; // rcx
  unsigned int v4; // ebx

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::GetFilterCombinationType");
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v4 = 0;
    *a2 = FCT_INTERSECTION;
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v4 = -2147467261;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v3[2],
      22,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::GetFilterCombinationType",
      v4);
  return v4;
}

```

## disassembly

```asm
0x18005eac0  mov     [rsp+arg_0], rbx
0x18005eac5  mov     [rsp+arg_8], rsi
0x18005eaca  push    rdi
0x18005eacb  sub     rsp, 30h
0x18005eacf  mov     rdi, rdx
0x18005ead2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ead9  lea     rsi, WPP_GLOBAL_Control
0x18005eae0  cmp     rcx, rsi
0x18005eae3  jz      short loc_18005EB14
0x18005eae5  test    byte ptr [rcx+1Ch], 40h
0x18005eae9  jz      short loc_18005EB14
0x18005eaeb  cmp     byte ptr [rcx+19h], 5
0x18005eaef  jb      short loc_18005EB14
0x18005eaf1  mov     rcx, [rcx+10h]
0x18005eaf5  lea     r9, aCombinedfilter_6; "CombinedFilterInfo::GetFilterCombinatio"...
0x18005eafc  mov     edx, 15h
0x18005eb01  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005eb08  call    WPP_SF_s
0x18005eb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb14  test    rdi, rdi
0x18005eb17  jnz     short loc_18005EB20
0x18005eb19  mov     ebx, 80004003h
0x18005eb1e  jmp     short loc_18005EB2B
0x18005eb20  xor     ebx, ebx
0x18005eb22  mov     [rdi], ebx
0x18005eb24  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb2b  cmp     rcx, rsi
0x18005eb2e  jz      short loc_18005EB5C
0x18005eb30  test    byte ptr [rcx+1Ch], 40h
0x18005eb34  jz      short loc_18005EB5C
0x18005eb36  cmp     byte ptr [rcx+19h], 5
0x18005eb3a  jb      short loc_18005EB5C
0x18005eb3c  mov     rcx, [rcx+10h]
0x18005eb40  lea     r9, aCombinedfilter_6; "CombinedFilterInfo::GetFilterCombinatio"...
0x18005eb47  mov     edx, 16h
0x18005eb4c  mov     [rsp+38h+var_18], ebx
0x18005eb50  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005eb57  call    WPP_SF_sD
0x18005eb5c  mov     rsi, [rsp+38h+arg_8]
0x18005eb61  mov     eax, ebx
0x18005eb63  mov     rbx, [rsp+38h+arg_0]
0x18005eb68  add     rsp, 30h
0x18005eb6c  pop     rdi
0x18005eb6d  retn
```
