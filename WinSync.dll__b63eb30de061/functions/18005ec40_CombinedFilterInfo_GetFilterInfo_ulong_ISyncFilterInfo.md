# CombinedFilterInfo::GetFilterInfo(ulong,ISyncFilterInfo * *)

- ea: `0x18005ec40`
- end: `0x18005ed08`
- name: `?GetFilterInfo@CombinedFilterInfo@@UEAAJKPEAPEAUISyncFilterInfo@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CombinedFilterInfo *__hidden this, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18005ec40`
- `0x180094010`

## string_xrefs

- `0x18005ec76`: `CombinedFilterInfo::GetFilterInfo`
- `0x18005ecdf`: `CombinedFilterInfo::GetFilterInfo`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::GetFilterInfo(
        CombinedFilterInfo *this,
        unsigned int a2,
        struct ISyncFilterInfo **a3)
{
  __int64 v4; // rsi
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  struct ISyncFilterInfo *v8; // rcx

  v4 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::GetFilterInfo");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( (unsigned int)v4 < 2 )
    {
      v8 = (struct ISyncFilterInfo *)*((_QWORD *)this + v4 + 1);
      v7 = 0;
      *a3 = v8;
      ((void (__fastcall *)(struct ISyncFilterInfo *))v8->lpVtbl->AddRef)(v8);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v7 = -2147024809;
    }
  }
  else
  {
    v7 = -2147467261;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      20,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::GetFilterInfo",
      v7);
  return v7;
}

```

## disassembly

```asm
0x18005ec40  push    rbx
0x18005ec42  push    rbp
0x18005ec43  push    rsi
0x18005ec44  push    rdi
0x18005ec45  push    r14
0x18005ec47  sub     rsp, 30h
0x18005ec4b  mov     rdi, r8
0x18005ec4e  mov     esi, edx
0x18005ec50  mov     rbp, rcx
0x18005ec53  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec5a  lea     r14, WPP_GLOBAL_Control
0x18005ec61  cmp     rcx, r14
0x18005ec64  jz      short loc_18005EC95
0x18005ec66  test    byte ptr [rcx+1Ch], 40h
0x18005ec6a  jz      short loc_18005EC95
0x18005ec6c  cmp     byte ptr [rcx+19h], 5
0x18005ec70  jb      short loc_18005EC95
0x18005ec72  mov     rcx, [rcx+10h]
0x18005ec76  lea     r9, aCombinedfilter_4; "CombinedFilterInfo::GetFilterInfo"
0x18005ec7d  mov     edx, 13h
0x18005ec82  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005ec89  call    WPP_SF_s
0x18005ec8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec95  test    rdi, rdi
0x18005ec98  jnz     short loc_18005ECA1
0x18005ec9a  mov     ebx, 80004003h
0x18005ec9f  jmp     short loc_18005ECCA
0x18005eca1  cmp     esi, 2
0x18005eca4  jb      short loc_18005ECAD
0x18005eca6  mov     ebx, 80070057h
0x18005ecab  jmp     short loc_18005ECCA
0x18005ecad  mov     rcx, [rbp+rsi*8+8]
0x18005ecb2  xor     ebx, ebx
0x18005ecb4  mov     [rdi], rcx
0x18005ecb7  mov     rax, [rcx]
0x18005ecba  mov     rax, [rax+8]
0x18005ecbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ecca  cmp     rcx, r14
0x18005eccd  jz      short loc_18005ECFB
0x18005eccf  test    byte ptr [rcx+1Ch], 40h
0x18005ecd3  jz      short loc_18005ECFB
0x18005ecd5  cmp     byte ptr [rcx+19h], 5
0x18005ecd9  jb      short loc_18005ECFB
0x18005ecdb  mov     rcx, [rcx+10h]
0x18005ecdf  lea     r9, aCombinedfilter_4; "CombinedFilterInfo::GetFilterInfo"
0x18005ece6  mov     edx, 14h
0x18005eceb  mov     [rsp+58h+var_38], ebx
0x18005ecef  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005ecf6  call    WPP_SF_sD
0x18005ecfb  mov     eax, ebx
0x18005ecfd  add     rsp, 30h
0x18005ed01  pop     r14
0x18005ed03  pop     rdi
0x18005ed04  pop     rsi
0x18005ed05  pop     rbp
0x18005ed06  pop     rbx
0x18005ed07  retn
```
