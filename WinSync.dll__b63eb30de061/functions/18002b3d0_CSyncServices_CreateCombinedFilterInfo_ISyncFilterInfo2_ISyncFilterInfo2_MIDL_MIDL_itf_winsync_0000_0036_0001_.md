# CSyncServices::CreateCombinedFilterInfo(ISyncFilterInfo2 *,ISyncFilterInfo2 *,__MIDL___MIDL_itf_winsync_0000_0036_0001,ICombinedFilterInfo * *)

- ea: `0x18002b3d0`
- end: `0x18002b4a9`
- name: `?CreateCombinedFilterInfo@CSyncServices@@UEAAJPEAUISyncFilterInfo2@@0W4__MIDL___MIDL_itf_winsync_0000_0036_0001@@PEAPEAUICombinedFilterInfo@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(struct IdParameters **this, struct ISyncFilterInfo2 *, struct ISyncFilterInfo2 *, enum __MIDL___MIDL_itf_winsync_0000_0036_0001, struct ICombinedFilterInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002b3d0`
- `0x18005e6b8`

## string_xrefs

- `0x18002b40a`: `CSyncServices::CreateCombinedFilterInfo`
- `0x18002b480`: `CSyncServices::CreateCombinedFilterInfo`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateCombinedFilterInfo(
        struct IdParameters **this,
        struct ISyncFilterInfo2 *a2,
        struct ISyncFilterInfo2 *a3,
        enum __MIDL___MIDL_itf_winsync_0000_0036_0001 a4,
        struct ICombinedFilterInfo **a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  unsigned int CombinedFilterInfo; // eax

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateCombinedFilterInfo");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[4] )
  {
    CombinedFilterInfo = CombinedFilterInfo::CreateCombinedFilterInfo(
                           this[4],
                           a2,
                           a3,
                           a4,
                           &GUID_11f9de71_2818_4779_b2ac_42d450565f45,
                           (void **)a5);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = CombinedFilterInfo;
  }
  else
  {
    v10 = -2147217407;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      67,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateCombinedFilterInfo",
      v10);
  return v10;
}

```

## disassembly

```asm
0x18002b3d0  push    rbx
0x18002b3d2  push    rbp
0x18002b3d3  push    rsi
0x18002b3d4  push    rdi
0x18002b3d5  push    r14
0x18002b3d7  sub     rsp, 30h
0x18002b3db  mov     edi, r9d
0x18002b3de  mov     rsi, r8
0x18002b3e1  mov     rbp, rdx
0x18002b3e4  mov     rbx, rcx
0x18002b3e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3ee  lea     r14, WPP_GLOBAL_Control
0x18002b3f5  cmp     rcx, r14
0x18002b3f8  jz      short loc_18002B429
0x18002b3fa  test    byte ptr [rcx+1Ch], 2
0x18002b3fe  jz      short loc_18002B429
0x18002b400  cmp     byte ptr [rcx+19h], 5
0x18002b404  jb      short loc_18002B429
0x18002b406  mov     rcx, [rcx+10h]
0x18002b40a  lea     r9, aCsyncservicesC_11; "CSyncServices::CreateCombinedFilterInfo"
0x18002b411  mov     edx, 42h ; 'B'
0x18002b416  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b41d  call    WPP_SF_s
0x18002b422  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b429  cmp     qword ptr [rbx+20h], 0
0x18002b42e  jnz     short loc_18002B437
0x18002b430  mov     ebx, 80041001h
0x18002b435  jmp     short loc_18002B46B
0x18002b437  mov     rax, [rsp+58h+arg_20]
0x18002b43f  mov     r9d, edi; enum __MIDL___MIDL_itf_winsync_0000_0036_0001
0x18002b442  mov     rcx, [rbx+20h]; struct IdParameters *
0x18002b446  mov     r8, rsi; struct ISyncFilterInfo2 *
0x18002b449  mov     [rsp+58h+var_30], rax; void **
0x18002b44e  mov     rdx, rbp; struct ISyncFilterInfo2 *
0x18002b451  lea     rax, _GUID_11f9de71_2818_4779_b2ac_42d450565f45
0x18002b458  mov     [rsp+58h+var_38], rax; struct _GUID *
0x18002b45d  call    ?CreateCombinedFilterInfo@CombinedFilterInfo@@SAJPEAVIdParameters@@PEAUISyncFilterInfo2@@1W4__MIDL___MIDL_itf_winsync_0000_0036_0001@@AEBU_GUID@@PEAPEAX@Z; CombinedFilterInfo::CreateCombinedFilterInfo(IdParameters *,ISyncFilterInfo2 *,ISyncFilterInfo2 *,__MIDL___MIDL_itf_winsync_0000_0036_0001,_GUID const &,void * *)
0x18002b462  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b469  mov     ebx, eax
0x18002b46b  cmp     rcx, r14
0x18002b46e  jz      short loc_18002B49C
0x18002b470  test    byte ptr [rcx+1Ch], 2
0x18002b474  jz      short loc_18002B49C
0x18002b476  cmp     byte ptr [rcx+19h], 5
0x18002b47a  jb      short loc_18002B49C
0x18002b47c  mov     rcx, [rcx+10h]
0x18002b480  lea     r9, aCsyncservicesC_11; "CSyncServices::CreateCombinedFilterInfo"
0x18002b487  mov     edx, 43h ; 'C'
0x18002b48c  mov     dword ptr [rsp+58h+var_38], ebx
0x18002b490  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b497  call    WPP_SF_sD
0x18002b49c  mov     eax, ebx
0x18002b49e  add     rsp, 30h
0x18002b4a2  pop     r14
0x18002b4a4  pop     rdi
0x18002b4a5  pop     rsi
0x18002b4a6  pop     rbp
0x18002b4a7  pop     rbx
0x18002b4a8  retn
```
