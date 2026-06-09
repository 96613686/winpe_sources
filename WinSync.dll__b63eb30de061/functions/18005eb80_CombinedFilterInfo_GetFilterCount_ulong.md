# CombinedFilterInfo::GetFilterCount(ulong *)

- ea: `0x18005eb80`
- end: `0x18005ec32`
- name: `?GetFilterCount@CombinedFilterInfo@@UEAAJPEAK@Z`
- size: `178`
- prototype: `__int64 __fastcall(CombinedFilterInfo *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18005eb80`

## string_xrefs

- `0x18005ebb5`: `CombinedFilterInfo::GetFilterCount`
- `0x18005ec04`: `CombinedFilterInfo::GetFilterCount`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::GetFilterCount(CombinedFilterInfo *this, unsigned int *a2)
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
      17,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::GetFilterCount");
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 2;
    v4 = 0;
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v4 = -2147467261;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v3[2],
      18,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::GetFilterCount",
      v4);
  return v4;
}

```

## disassembly

```asm
0x18005eb80  mov     [rsp+arg_0], rbx
0x18005eb85  mov     [rsp+arg_8], rsi
0x18005eb8a  push    rdi
0x18005eb8b  sub     rsp, 30h
0x18005eb8f  mov     rdi, rdx
0x18005eb92  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb99  lea     rsi, WPP_GLOBAL_Control
0x18005eba0  cmp     rcx, rsi
0x18005eba3  jz      short loc_18005EBD4
0x18005eba5  test    byte ptr [rcx+1Ch], 40h
0x18005eba9  jz      short loc_18005EBD4
0x18005ebab  cmp     byte ptr [rcx+19h], 5
0x18005ebaf  jb      short loc_18005EBD4
0x18005ebb1  mov     rcx, [rcx+10h]
0x18005ebb5  lea     r9, aCombinedfilter_2; "CombinedFilterInfo::GetFilterCount"
0x18005ebbc  mov     edx, 11h
0x18005ebc1  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005ebc8  call    WPP_SF_s
0x18005ebcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebd4  test    rdi, rdi
0x18005ebd7  jnz     short loc_18005EBE0
0x18005ebd9  mov     ebx, 80004003h
0x18005ebde  jmp     short loc_18005EBEF
0x18005ebe0  mov     dword ptr [rdi], 2
0x18005ebe6  xor     ebx, ebx
0x18005ebe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebef  cmp     rcx, rsi
0x18005ebf2  jz      short loc_18005EC20
0x18005ebf4  test    byte ptr [rcx+1Ch], 40h
0x18005ebf8  jz      short loc_18005EC20
0x18005ebfa  cmp     byte ptr [rcx+19h], 5
0x18005ebfe  jb      short loc_18005EC20
0x18005ec00  mov     rcx, [rcx+10h]
0x18005ec04  lea     r9, aCombinedfilter_2; "CombinedFilterInfo::GetFilterCount"
0x18005ec0b  mov     edx, 12h
0x18005ec10  mov     [rsp+38h+var_18], ebx
0x18005ec14  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005ec1b  call    WPP_SF_sD
0x18005ec20  mov     rsi, [rsp+38h+arg_8]
0x18005ec25  mov     eax, ebx
0x18005ec27  mov     rbx, [rsp+38h+arg_0]
0x18005ec2c  add     rsp, 30h
0x18005ec30  pop     rdi
0x18005ec31  retn
```
