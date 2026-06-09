# FwSetDynamicKeywordAddressInRegistry

- ea: `0x180030070`
- end: `0x180030150`
- name: `FwSetDynamicKeywordAddressInRegistry`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e740`
- `0x180030bf0`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x180030070`
- `0x180031500`

## import_xrefs

- `fwbase!FwFree` at `0x18003013e`
- `fwbase!FwFree` at `0x18003013e`
- `fwbase!FwRegSetString` at `0x180030103`
- `fwbase!FwRegSetString` at `0x180030103`

## pseudocode

```c
__int64 __fastcall FwSetDynamicKeywordAddressInRegistry(
        __int64 a1,
        struct _tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *a2,
        __int64 a3)
{
  int v5; // eax
  unsigned int v6; // edi
  LPCOLESTR v7; // rcx
  __int64 v8; // rdx

  v5 = FwEncodeDynamicKeywordAddress(a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 389, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, 0);
    v5 = FwRegSetString(a3, 0, a1, 0);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v8 = 390;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 388;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v5);
    }
  }
  FwFree(0);
  return v6;
}

```

## disassembly

```asm
0x180030070  push    rbx
0x180030072  push    rbp
0x180030073  push    rdi
0x180030074  push    r14
0x180030076  sub     rsp, 28h
0x18003007a  mov     rax, rdx
0x18003007d  mov     [rsp+48h+arg_18], 0
0x180030086  mov     r14, rcx
0x180030089  lea     rdx, [rsp+48h+arg_18]
0x18003008e  mov     rcx, rax; struct _tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *
0x180030091  mov     rbp, r8
0x180030094  call    FwEncodeDynamicKeywordAddress
0x180030099  mov     edi, eax
0x18003009b  test    eax, eax
0x18003009d  jns     short loc_1800300C3
0x18003009f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300a6  lea     rbx, WPP_GLOBAL_Control
0x1800300ad  cmp     rcx, rbx
0x1800300b0  jz      loc_180030139
0x1800300b6  test    byte ptr [rcx+1Ch], 1
0x1800300ba  jz      short loc_180030139
0x1800300bc  mov     edx, 184h
0x1800300c1  jmp     short loc_180030126
0x1800300c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300ca  lea     rbx, WPP_GLOBAL_Control
0x1800300d1  cmp     rcx, rbx
0x1800300d4  jz      short loc_1800300F6
0x1800300d6  test    byte ptr [rcx+1Ch], 4
0x1800300da  jz      short loc_1800300F6
0x1800300dc  mov     r9, [rsp+48h+arg_18]
0x1800300e1  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800300e8  mov     rcx, [rcx+10h]
0x1800300ec  mov     edx, 185h
0x1800300f1  call    WPP_SF_S
0x1800300f6  mov     r9, [rsp+48h+arg_18]
0x1800300fb  mov     r8, r14
0x1800300fe  xor     edx, edx
0x180030100  mov     rcx, rbp
0x180030103  call    cs:__imp_FwRegSetString
0x180030109  mov     edi, eax
0x18003010b  test    eax, eax
0x18003010d  jns     short loc_180030139
0x18003010f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030116  cmp     rcx, rbx
0x180030119  jz      short loc_180030139
0x18003011b  test    byte ptr [rcx+1Ch], 1
0x18003011f  jz      short loc_180030139
0x180030121  mov     edx, 186h
0x180030126  mov     rcx, [rcx+10h]
0x18003012a  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180030131  mov     r9d, eax
0x180030134  call    WPP_SF_d
0x180030139  mov     rcx, [rsp+48h+arg_18]
0x18003013e  call    cs:__imp_FwFree
0x180030144  mov     eax, edi
0x180030146  add     rsp, 28h
0x18003014a  pop     r14
0x18003014c  pop     rdi
0x18003014d  pop     rbp
0x18003014e  pop     rbx
0x18003014f  retn
```
