# AhcpCacheEntryFilter

- ea: `0x1400440d8`
- end: `0x14004429e`
- name: `AhcpCacheEntryFilter`
- size: `454`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140027bc8`
- `0x1400436c0`
- `0x140043bb0`
- `0x14004c3a0`

## callees

- `0x140001b78`
- `0x140007b40`
- `0x14003e364`
- `0x1400440d8`
- `0x1400442a4`
- `0x140045c38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400441bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441bd`

## string_xrefs

- `0x14004419e`: `AhcpCacheEntryFilter`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntryFilter(__int64 a1, int a2)
{
  void *v2; // rdx
  int v4; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rcx
  char *v10; // r12
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rax
  const char *v13; // r9
  __int64 v14; // r8
  int v16; // eax
  size_t v17; // rsi
  __int64 v18; // [rsp+20h] [rbp-40h]
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  __int128 v20; // [rsp+38h] [rbp-28h]
  __int64 v21; // [rsp+48h] [rbp-18h]
  PVOID P[2]; // [rsp+50h] [rbp-10h]
  bool v23; // [rsp+90h] [rbp+30h] BYREF
  int v24; // [rsp+98h] [rbp+38h] BYREF

  v24 = a2;
  v2 = *(void **)(a1 + 24);
  v19 = 0;
  v21 = 4096;
  v20 = 0;
  *(_OWORD *)P = 0;
  if ( !v2 )
  {
LABEL_23:
    v5 = 0;
    goto LABEL_11;
  }
  v4 = RtlMemoryStream::InitializeFromBuffer((RtlMemoryStream *)&v19, v2, *(unsigned int *)(a1 + 16));
  v5 = v4;
  if ( v4 < 0 )
  {
    v13 = "InitializeFromBuffer failed [%x]";
    v14 = 658;
  }
  else
  {
    v6 = v20;
    v7 = 0;
    v23 = 0;
    while ( 1 )
    {
      P[0] = (PVOID)v7;
      v8 = v7;
      if ( v7 >= v6 )
        goto LABEL_22;
      v9 = v7 + 8;
      if ( v7 + 8 < v7 || v9 > v6 )
      {
        v5 = -1073741275;
        goto LABEL_9;
      }
      v10 = (char *)P[1];
      P[0] = (PVOID)(v7 + 8);
      v11 = *(_QWORD *)((char *)P[1] + v7);
      v12 = HIDWORD(v11) + v9;
      if ( v12 < v9 || v12 + 3 < v12 || (v7 = (v12 + 3) & 0xFFFFFFFFFFFFFFFCuLL, v7 > v6) )
      {
        v5 = -1073741675;
LABEL_9:
        LODWORD(v18) = v5;
        v13 = "Failed to filter stream [%x]";
        v14 = 664;
        goto LABEL_10;
      }
      v23 = 0;
      v16 = AhcpCacheEntryFilterParamIfSubset(&v23, (__int64)P[1] + v9, HIDWORD(v11), v11, &v24);
      v5 = v16;
      if ( v16 )
        break;
      if ( v23 )
      {
        v17 = v6 - v7;
        memmove(&v10[v8], &v10[v7], v17);
        v6 = v8 + v17;
        v7 = v8;
        *(_QWORD *)&v20 = v6;
        if ( v8 > v6 )
        {
          v5 = -1073741811;
          goto LABEL_9;
        }
      }
    }
    if ( v16 < 0 )
      goto LABEL_9;
LABEL_22:
    v4 = AhcpCacheEntrySetDataFromStream(a1, (__int64)&v19);
    v5 = v4;
    if ( v4 >= 0 )
      goto LABEL_23;
    v13 = "Failed to set data in entry [%x]";
    v14 = 674;
  }
  LODWORD(v18) = v4;
LABEL_10:
  AslLogCallPrintf(1, "AhcpCacheEntryFilter", v14, v13, v18);
LABEL_11:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x7274534Du);
  return v5;
}

```

## disassembly

```asm
0x1400440d8  mov     [rsp-28h+arg_10], rbx
0x1400440dd  mov     [rsp-28h+arg_18], rsi
0x1400440e2  mov     [rsp-28h+arg_8], edx
0x1400440e6  push    rbp
0x1400440e7  push    rdi
0x1400440e8  push    r12
0x1400440ea  push    r14
0x1400440ec  push    r15
0x1400440ee  mov     rbp, rsp
0x1400440f1  sub     rsp, 60h
0x1400440f5  mov     rdx, [rcx+18h]; void *
0x1400440f9  xorps   xmm0, xmm0
0x1400440fc  mov     [rbp+var_30], 0
0x140044104  xorps   xmm1, xmm1
0x140044107  mov     [rbp+var_18], 1000h
0x14004410f  mov     r15, rcx
0x140044112  movdqu  [rbp+var_28], xmm0
0x140044117  movdqu  xmmword ptr [rbp+P], xmm1
0x14004411c  test    rdx, rdx
0x14004411f  jz      loc_140044272
0x140044125  mov     r8d, [rcx+10h]; unsigned __int64
0x140044129  lea     rcx, [rbp+var_30]; this
0x14004412d  call    ?InitializeFromBuffer@RtlMemoryStream@@QEAAJQEAX_K@Z; RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)
0x140044132  mov     ebx, eax
0x140044134  test    eax, eax
0x140044136  js      loc_140044279
0x14004413c  mov     rsi, qword ptr [rbp+var_28]
0x140044140  xor     edi, edi
0x140044142  mov     [rbp+arg_0], 0
0x140044146  mov     [rbp+P], rdi
0x14004414a  mov     r14, rdi
0x14004414d  cmp     rdi, rsi
0x140044150  jnb     loc_140044260
0x140044156  lea     rcx, [rdi+8]
0x14004415a  cmp     rcx, rdi
0x14004415d  jb      loc_140044250
0x140044163  cmp     rcx, rsi
0x140044166  ja      loc_140044250
0x14004416c  mov     r12, [rbp+P+8]
0x140044170  mov     [rbp+P], rcx
0x140044174  mov     r9, [rdi+r12]
0x140044178  mov     r8, r9
0x14004417b  shr     r8, 20h
0x14004417f  lea     rax, [r8+rcx]
0x140044183  cmp     rax, rcx
0x140044186  jnb     short loc_1400441E5
0x140044188  mov     ebx, 0C0000095h
0x14004418d  mov     dword ptr [rsp+60h+var_40], ebx
0x140044191  lea     r9, aFailedToFilter; "Failed to filter stream [%x]"
0x140044198  mov     r8d, 298h
0x14004419e  lea     rdx, aAhcpcacheentry; "AhcpCacheEntryFilter"
0x1400441a5  mov     ecx, 1
0x1400441aa  call    AslLogCallPrintf
0x1400441af  mov     rcx, [rbp+P+8]; P
0x1400441b3  test    rcx, rcx
0x1400441b6  jz      short loc_1400441C9
0x1400441b8  mov     edx, 7274534Dh; Tag
0x1400441bd  call    cs:__imp_ExFreePoolWithTag
0x1400441c4  nop     dword ptr [rax+rax+00h]
0x1400441c9  lea     r11, [rsp+60h+var_s0]
0x1400441ce  mov     eax, ebx
0x1400441d0  mov     rbx, [r11+40h]
0x1400441d4  mov     rsi, [r11+48h]
0x1400441d8  mov     rsp, r11
0x1400441db  pop     r15
0x1400441dd  pop     r14
0x1400441df  pop     r12
0x1400441e1  pop     rdi
0x1400441e2  pop     rbp
0x1400441e3  retn
0x1400441e5  lea     rdi, [rax+3]
0x1400441e9  cmp     rdi, rax
0x1400441ec  jb      short loc_140044188
0x1400441ee  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400441f2  cmp     rdi, rsi
0x1400441f5  ja      short loc_140044188
0x1400441f7  lea     rdx, [rcx+r12]
0x1400441fb  mov     [rbp+arg_0], 0
0x1400441ff  lea     rax, [rbp+arg_8]
0x140044203  lea     rcx, [rbp+arg_0]
0x140044207  mov     [rsp+60h+var_40], rax
0x14004420c  call    AhcpCacheEntryFilterParamIfSubset
0x140044211  mov     ebx, eax
0x140044213  test    eax, eax
0x140044215  jnz     short loc_14004425A
0x140044217  cmp     [rbp+arg_0], al
0x14004421a  jz      loc_140044146
0x140044220  sub     rsi, rdi
0x140044223  lea     rdx, [rdi+r12]; Src
0x140044227  mov     r8, rsi; Size
0x14004422a  lea     rcx, [r12+r14]; void *
0x14004422e  call    memmove
0x140044233  add     rsi, r14
0x140044236  mov     rdi, r14
0x140044239  mov     qword ptr [rbp+var_28], rsi
0x14004423d  cmp     r14, rsi
0x140044240  jbe     loc_140044146
0x140044246  mov     ebx, 0C000000Dh
0x14004424b  jmp     loc_14004418D
0x140044250  mov     ebx, 0C0000225h
0x140044255  jmp     loc_14004418D
0x14004425a  js      loc_14004418D
0x140044260  lea     rdx, [rbp+var_30]
0x140044264  mov     rcx, r15
0x140044267  call    AhcpCacheEntrySetDataFromStream
0x14004426c  mov     ebx, eax
0x14004426e  test    eax, eax
0x140044270  js      short loc_140044288
0x140044272  xor     ebx, ebx
0x140044274  jmp     loc_1400441AF
0x140044279  lea     r9, aInitializefrom; "InitializeFromBuffer failed [%x]"
0x140044280  mov     r8d, 292h
0x140044286  jmp     short loc_140044295
0x140044288  lea     r9, aFailedToSetDat; "Failed to set data in entry [%x]"
0x14004428f  mov     r8d, 2A2h
0x140044295  mov     dword ptr [rsp+60h+var_40], eax
0x140044299  jmp     loc_14004419E
```
