# CombinedFilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)

- ea: `0x18005e830`
- end: `0x18005eab5`
- name: `?Deserialize@CombinedFilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(struct ISyncFilterDeserializer *, struct IdParameters *, const unsigned __int8 *, unsigned int, struct ISyncFilterInfo **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b9fc`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18004b9fc`
- `0x18005e6b8`
- `0x18005e830`
- `0x180094010`

## string_xrefs

- `0x18005e873`: `CombinedFilterInfo::Deserialize`
- `0x18005ea86`: `CombinedFilterInfo::Deserialize`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::Deserialize(
        struct ISyncFilterDeserializer *a1,
        struct IdParameters *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct ISyncFilterInfo **a5)
{
  __int64 v5; // r14
  unsigned int v9; // edi
  unsigned int CombinedFilterInfo; // ebx
  __int64 v11; // rdx
  unsigned int v12; // r15d
  unsigned int v13; // edi
  struct ISyncFilterInfo *v15; // [rsp+30h] [rbp-28h] BYREF
  struct ISyncFilterInfo *v16; // [rsp+38h] [rbp-20h] BYREF
  struct ISyncFilterInfo2 *v17; // [rsp+40h] [rbp-18h] BYREF
  struct ISyncFilterInfo2 *v18; // [rsp+48h] [rbp-10h] BYREF

  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::Deserialize");
  }
  v16 = 0;
  v15 = 0;
  v18 = 0;
  v17 = 0;
  if ( a1 && (!(_DWORD)v5 || a3) )
  {
    if ( &a3[v5] < a3 || (unsigned int)v5 < 8 )
    {
      CombinedFilterInfo = -2147217396;
    }
    else
    {
      v9 = a3[3] | ((a3[2] | ((a3[1] | (*a3 << 8)) << 8)) << 8);
      if ( v9 > (int)v5 - 4 )
      {
LABEL_14:
        CombinedFilterInfo = -2147217396;
        goto LABEL_24;
      }
      CombinedFilterInfo = FilterInfo::Deserialize(a1, a2, a3 + 4, v9, &v15);
      if ( !CombinedFilterInfo )
      {
        v11 = v9 + 4;
        if ( (unsigned int)(v5 - v11) < 4 )
          goto LABEL_14;
        v12 = v9 + 8;
        v13 = a3[v11 + 3] | ((a3[v11 + 2] | (((a3[v11] << 8) | a3[v11 + 1]) << 8)) << 8);
        if ( v13 > (unsigned int)v5 - v12 )
          goto LABEL_14;
        CombinedFilterInfo = FilterInfo::Deserialize(a1, a2, &a3[v12], v13, &v16);
        if ( !CombinedFilterInfo )
        {
          if ( v12 + v13 <= (unsigned int)v5 )
          {
            CombinedFilterInfo = ((__int64 (__fastcall *)(struct ISyncFilterInfo *, GUID *, struct ISyncFilterInfo2 **))v15->lpVtbl->QueryInterface)(
                                   v15,
                                   &GUID_19b394ba_e3d0_468c_934d_321968b2ab34,
                                   &v17);
            if ( !CombinedFilterInfo )
            {
              CombinedFilterInfo = ((__int64 (__fastcall *)(struct ISyncFilterInfo *, GUID *, struct ISyncFilterInfo2 **))v16->lpVtbl->QueryInterface)(
                                     v16,
                                     &GUID_19b394ba_e3d0_468c_934d_321968b2ab34,
                                     &v18);
              if ( !CombinedFilterInfo )
                CombinedFilterInfo = CombinedFilterInfo::CreateCombinedFilterInfo(
                                       a2,
                                       v17,
                                       v18,
                                       FCT_INTERSECTION,
                                       &IID_ISyncFilterInfo,
                                       (void **)a5);
            }
          }
          else
          {
            CombinedFilterInfo = -2147217379;
          }
        }
      }
    }
  }
  else
  {
    CombinedFilterInfo = -2147467261;
  }
LABEL_24:
  if ( v15 )
    ((void (__fastcall *)(struct ISyncFilterInfo *))v15->lpVtbl->Release)(v15);
  if ( v16 )
    ((void (__fastcall *)(struct ISyncFilterInfo *))v16->lpVtbl->Release)(v16);
  if ( v17 )
    ((void (__fastcall *)(struct ISyncFilterInfo2 *))v17->lpVtbl->Release)(v17);
  if ( v18 )
    ((void (__fastcall *)(struct ISyncFilterInfo2 *))v18->lpVtbl->Release)(v18);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::Deserialize",
      CombinedFilterInfo);
  }
  return CombinedFilterInfo;
}

```

## disassembly

```asm
0x18005e830  push    rbp
0x18005e832  push    rbx
0x18005e833  push    rsi
0x18005e834  push    rdi
0x18005e835  push    r12
0x18005e837  push    r13
0x18005e839  push    r14
0x18005e83b  push    r15
0x18005e83d  mov     rbp, rsp
0x18005e840  sub     rsp, 58h
0x18005e844  mov     r14d, r9d
0x18005e847  mov     rsi, r8
0x18005e84a  mov     r13, rdx
0x18005e84d  mov     r12, rcx
0x18005e850  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e857  lea     rdi, WPP_GLOBAL_Control
0x18005e85e  cmp     rcx, rdi
0x18005e861  jz      short loc_18005E88B
0x18005e863  test    byte ptr [rcx+1Ch], 40h
0x18005e867  jz      short loc_18005E88B
0x18005e869  cmp     byte ptr [rcx+19h], 5
0x18005e86d  jb      short loc_18005E88B
0x18005e86f  mov     rcx, [rcx+10h]
0x18005e873  lea     r9, aCombinedfilter_1; "CombinedFilterInfo::Deserialize"
0x18005e87a  mov     edx, 17h
0x18005e87f  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005e886  call    WPP_SF_s
0x18005e88b  mov     [rbp+var_20], 0
0x18005e893  mov     [rbp+var_28], 0
0x18005e89b  mov     [rbp+var_10], 0
0x18005e8a3  mov     [rbp+var_18], 0
0x18005e8ab  test    r12, r12
0x18005e8ae  jz      loc_18005EA11
0x18005e8b4  test    r14d, r14d
0x18005e8b7  jz      short loc_18005E8C2
0x18005e8b9  test    rsi, rsi
0x18005e8bc  jz      loc_18005EA11
0x18005e8c2  lea     rax, [rsi+r14]
0x18005e8c6  cmp     rax, rsi
0x18005e8c9  jb      loc_18005EA0A
0x18005e8cf  cmp     r14d, 8
0x18005e8d3  jb      loc_18005EA0A
0x18005e8d9  movzx   eax, byte ptr [rsi+1]
0x18005e8dd  movzx   edi, byte ptr [rsi]
0x18005e8e0  shl     edi, 8
0x18005e8e3  or      edi, eax
0x18005e8e5  movzx   eax, byte ptr [rsi+2]
0x18005e8e9  shl     edi, 8
0x18005e8ec  or      edi, eax
0x18005e8ee  movzx   eax, byte ptr [rsi+3]
0x18005e8f2  shl     edi, 8
0x18005e8f5  or      edi, eax
0x18005e8f7  lea     eax, [r14-4]
0x18005e8fb  cmp     edi, eax
0x18005e8fd  ja      short loc_18005E95D
0x18005e8ff  lea     rax, [rbp+var_28]
0x18005e903  mov     r9d, edi; unsigned int
0x18005e906  lea     r8, [rsi+4]; unsigned __int8 *
0x18005e90a  mov     [rsp+58h+var_38], rax; struct ISyncFilterInfo **
0x18005e90f  mov     rdx, r13; struct IdParameters *
0x18005e912  mov     rcx, r12; struct ISyncFilterDeserializer *
0x18005e915  call    ?Deserialize@FilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; FilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18005e91a  mov     ebx, eax
0x18005e91c  test    eax, eax
0x18005e91e  jnz     short loc_18005E995
0x18005e920  lea     edx, [rdi+4]
0x18005e923  mov     eax, r14d
0x18005e926  sub     eax, edx
0x18005e928  cmp     eax, 4
0x18005e92b  jb      short loc_18005E95D
0x18005e92d  movzx   eax, byte ptr [rdx+rsi]
0x18005e931  lea     r15d, [rdx+4]
0x18005e935  movzx   edi, byte ptr [rdx+rsi+1]
0x18005e93a  shl     eax, 8
0x18005e93d  or      edi, eax
0x18005e93f  movzx   eax, byte ptr [rdx+rsi+2]
0x18005e944  shl     edi, 8
0x18005e947  or      edi, eax
0x18005e949  movzx   eax, byte ptr [rdx+rsi+3]
0x18005e94e  shl     edi, 8
0x18005e951  or      edi, eax
0x18005e953  mov     eax, r14d
0x18005e956  sub     eax, r15d
0x18005e959  cmp     edi, eax
0x18005e95b  jbe     short loc_18005E964
0x18005e95d  mov     ebx, 8004100Ch
0x18005e962  jmp     short loc_18005E995
0x18005e964  lea     rax, [rbp+var_20]
0x18005e968  mov     r8d, r15d
0x18005e96b  add     r8, rsi; unsigned __int8 *
0x18005e96e  mov     [rsp+58h+var_38], rax; struct ISyncFilterInfo **
0x18005e973  mov     r9d, edi; unsigned int
0x18005e976  mov     rdx, r13; struct IdParameters *
0x18005e979  mov     rcx, r12; struct ISyncFilterDeserializer *
0x18005e97c  call    ?Deserialize@FilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; FilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18005e981  mov     ebx, eax
0x18005e983  test    eax, eax
0x18005e985  jnz     short loc_18005E995
0x18005e987  lea     eax, [r15+rdi]
0x18005e98b  cmp     eax, r14d
0x18005e98e  jbe     short loc_18005E99E
0x18005e990  mov     ebx, 8004101Dh
0x18005e995  lea     rdi, WPP_GLOBAL_Control
0x18005e99c  jmp     short loc_18005EA16
0x18005e99e  mov     rcx, [rbp+var_28]
0x18005e9a2  lea     r8, [rbp+var_18]
0x18005e9a6  lea     rdx, _GUID_19b394ba_e3d0_468c_934d_321968b2ab34
0x18005e9ad  mov     rax, [rcx]
0x18005e9b0  mov     rax, [rax]
0x18005e9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9b8  mov     ebx, eax
0x18005e9ba  test    eax, eax
0x18005e9bc  jnz     short loc_18005E995
0x18005e9be  mov     rcx, [rbp+var_20]
0x18005e9c2  lea     r8, [rbp+var_10]
0x18005e9c6  lea     rdx, _GUID_19b394ba_e3d0_468c_934d_321968b2ab34
0x18005e9cd  mov     rax, [rcx]
0x18005e9d0  mov     rax, [rax]
0x18005e9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9d8  mov     ebx, eax
0x18005e9da  test    eax, eax
0x18005e9dc  jnz     short loc_18005E995
0x18005e9de  mov     rax, [rbp+arg_20]
0x18005e9e2  xor     r9d, r9d; enum __MIDL___MIDL_itf_winsync_0000_0036_0001
0x18005e9e5  mov     r8, [rbp+var_10]; struct ISyncFilterInfo2 *
0x18005e9e9  mov     rcx, r13; struct IdParameters *
0x18005e9ec  mov     rdx, [rbp+var_18]; struct ISyncFilterInfo2 *
0x18005e9f0  mov     [rsp+58h+var_30], rax; void **
0x18005e9f5  lea     rax, IID_ISyncFilterInfo
0x18005e9fc  mov     [rsp+58h+var_38], rax; struct _GUID *
0x18005ea01  call    ?CreateCombinedFilterInfo@CombinedFilterInfo@@SAJPEAVIdParameters@@PEAUISyncFilterInfo2@@1W4__MIDL___MIDL_itf_winsync_0000_0036_0001@@AEBU_GUID@@PEAPEAX@Z; CombinedFilterInfo::CreateCombinedFilterInfo(IdParameters *,ISyncFilterInfo2 *,ISyncFilterInfo2 *,__MIDL___MIDL_itf_winsync_0000_0036_0001,_GUID const &,void * *)
0x18005ea06  mov     ebx, eax
0x18005ea08  jmp     short loc_18005E995
0x18005ea0a  mov     ebx, 8004100Ch
0x18005ea0f  jmp     short loc_18005EA16
0x18005ea11  mov     ebx, 80004003h
0x18005ea16  mov     rcx, [rbp+var_28]
0x18005ea1a  test    rcx, rcx
0x18005ea1d  jz      short loc_18005EA2B
0x18005ea1f  mov     rax, [rcx]
0x18005ea22  mov     rax, [rax+10h]
0x18005ea26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea2b  mov     rcx, [rbp+var_20]
0x18005ea2f  test    rcx, rcx
0x18005ea32  jz      short loc_18005EA40
0x18005ea34  mov     rax, [rcx]
0x18005ea37  mov     rax, [rax+10h]
0x18005ea3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea40  mov     rcx, [rbp+var_18]
0x18005ea44  test    rcx, rcx
0x18005ea47  jz      short loc_18005EA55
0x18005ea49  mov     rax, [rcx]
0x18005ea4c  mov     rax, [rax+10h]
0x18005ea50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea55  mov     rcx, [rbp+var_10]
0x18005ea59  test    rcx, rcx
0x18005ea5c  jz      short loc_18005EA6A
0x18005ea5e  mov     rax, [rcx]
0x18005ea61  mov     rax, [rax+10h]
0x18005ea65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ea71  cmp     rcx, rdi
0x18005ea74  jz      short loc_18005EAA2
0x18005ea76  test    byte ptr [rcx+1Ch], 40h
0x18005ea7a  jz      short loc_18005EAA2
0x18005ea7c  cmp     byte ptr [rcx+19h], 5
0x18005ea80  jb      short loc_18005EAA2
0x18005ea82  mov     rcx, [rcx+10h]
0x18005ea86  lea     r9, aCombinedfilter_1; "CombinedFilterInfo::Deserialize"
0x18005ea8d  mov     edx, 18h
0x18005ea92  mov     dword ptr [rsp+58h+var_38], ebx
0x18005ea96  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005ea9d  call    WPP_SF_sD
0x18005eaa2  mov     eax, ebx
0x18005eaa4  add     rsp, 58h
0x18005eaa8  pop     r15
0x18005eaaa  pop     r14
0x18005eaac  pop     r13
0x18005eaae  pop     r12
0x18005eab0  pop     rdi
0x18005eab1  pop     rsi
0x18005eab2  pop     rbx
0x18005eab3  pop     rbp
0x18005eab4  retn
```
