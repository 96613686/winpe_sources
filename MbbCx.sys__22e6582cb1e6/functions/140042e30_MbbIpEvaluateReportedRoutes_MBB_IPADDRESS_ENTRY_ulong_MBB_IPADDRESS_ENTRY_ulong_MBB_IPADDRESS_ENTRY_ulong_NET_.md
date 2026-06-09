# MbbIpEvaluateReportedRoutes(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong,uchar)

- ea: `0x140042e30`
- end: `0x1400430c7`
- name: `?MbbIpEvaluateReportedRoutes@@YAXPEAU_MBB_IPADDRESS_ENTRY@@K0K0KPEAT_NET_LUID_LH@@KE@Z`
- size: `663`
- prototype: `void __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int, union _NET_LUID_LH *Source1, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140046d80`

## callees

- `0x140042e30`
- `0x14004323c`
- `0x1400448c8`
- `0x140045448`
- `0x140046378`
- `0x1400466a4`
- `0x1400469e8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140042f02`
- `ntoskrnl!RtlCompareMemory` at `0x140042f02`
- `NETIO!FreeMibTable` at `0x1400430a2`
- `NETIO!FreeMibTable` at `0x1400430a2`
- `NETIO!DeleteIpForwardEntry2` at `0x140043032`
- `NETIO!DeleteIpForwardEntry2` at `0x140043032`
- `NETIO!GetIpForwardTable2` at `0x140042e62`
- `NETIO!GetIpForwardTable2` at `0x140042e62`

## pseudocode

```c
void __fastcall MbbIpEvaluateReportedRoutes(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MBB_IPADDRESS_ENTRY *a3,
        unsigned int a4,
        struct _MBB_IPADDRESS_ENTRY *a5,
        unsigned int a6,
        union _NET_LUID_LH *Source1,
        NET_IFINDEX a8,
        unsigned int a9)
{
  NTSTATUS IpForwardTable2; // eax
  int v12; // edx
  int v13; // r8d
  char *v14; // rbp
  char v15; // si
  unsigned int v16; // edi
  unsigned int *v17; // rbx
  unsigned int v18; // esi
  __int64 v19; // rbp
  unsigned int *v20; // r15
  int v21; // edx
  int v22; // r8d
  unsigned int *v23; // rbp
  __int16 v24; // ax
  NTSTATUS v25; // eax
  int v26; // edx
  int v27; // r8d
  PVOID Memory; // [rsp+40h] [rbp-48h] BYREF

  Memory = 0;
  IpForwardTable2 = GetIpForwardTable2(0, (PMIB_IPFORWARD_TABLE2 *)&Memory);
  if ( !IpForwardTable2 )
  {
    v14 = (char *)Memory;
    v15 = 0;
    v16 = 0;
    if ( !*(_DWORD *)Memory )
      goto LABEL_23;
    do
    {
      if ( RtlCompareMemory(Source1, &v14[104 * v16 + 8], 8u) == 8
        && MbbIpProcessRouteEntry(a1, a2, a3, a4, a5, a6, (MIB_IPFORWARD_ROW2 *)&v14[104 * v16 + 8]) == 1 )
      {
        v15 = 1;
      }
      v17 = (unsigned int *)Memory;
      ++v16;
    }
    while ( v16 < *(_DWORD *)Memory );
    if ( v15 )
    {
      v18 = 0;
      a9 = 0;
      if ( !*(_DWORD *)Memory )
      {
LABEL_25:
        FreeMibTable(v17);
        return;
      }
      do
      {
        v19 = 26LL * v18;
        v20 = &v17[v19];
        if ( !(unsigned int)MbbIpFindRouteInTable(a1, a2, (struct _MIB_IPFORWARD_ROW2 *)&v17[v19 + 2], &a9) )
        {
          v23 = &v17[v19];
          v24 = *((_WORD *)v23 + 26);
          if ( v24 == 2 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v21, v22, 89);
          }
          else if ( v24 == 23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v21, v22, 90);
          }
          v25 = DeleteIpForwardEntry2((const MIB_IPFORWARD_ROW2 *)(v23 + 2));
          if ( v25 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_id(
              WPP_GLOBAL_Control->DeviceExtension,
              v26,
              v27,
              91,
              (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
              *((_QWORD *)v20 + 1),
              v25);
        }
        ++v18;
      }
      while ( v18 < *v17 );
    }
    else
    {
LABEL_23:
      MbbIpReportRoutes(a1, a2, Source1, a8);
    }
    v17 = (unsigned int *)Memory;
    goto LABEL_25;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_id(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      41,
      (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
      Source1->Value,
      IpForwardTable2);
}

```

## disassembly

```asm
0x140042e30  mov     rax, rsp
0x140042e33  mov     [rax+8], rbx
0x140042e37  mov     [rax+20h], r9d
0x140042e3b  mov     [rax+18h], r8
0x140042e3f  push    rbp
0x140042e40  push    rsi
0x140042e41  push    rdi
0x140042e42  push    r12
0x140042e44  push    r13
0x140042e46  push    r14
0x140042e48  push    r15
0x140042e4a  sub     rsp, 50h
0x140042e4e  mov     r12d, edx
0x140042e51  mov     qword ptr [rax-48h], 0
0x140042e59  mov     r13, rcx
0x140042e5c  lea     rdx, [rax-48h]; Table
0x140042e60  xor     ecx, ecx; Family
0x140042e62  call    cs:__imp_GetIpForwardTable2
0x140042e69  nop     dword ptr [rax+rax+00h]
0x140042e6e  test    eax, eax
0x140042e70  jz      short loc_140042EC1
0x140042e72  lea     rdi, WPP_RECORDER_INITIALIZED
0x140042e79  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140042e80  jz      loc_1400430AE
0x140042e86  mov     dword ptr [rsp+88h+Row], eax
0x140042e8a  lea     r14, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140042e91  mov     rax, [rsp+88h+Source1]
0x140042e99  mov     r9d, 29h ; ')'
0x140042e9f  mov     rcx, [rax]
0x140042ea2  mov     qword ptr [rsp+88h+var_60], rcx
0x140042ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x140042eae  mov     [rsp+88h+var_68], r14
0x140042eb3  mov     rcx, [rcx+40h]
0x140042eb7  call    WPP_RECORDER_SF_id
0x140042ebc  jmp     loc_1400430AE
0x140042ec1  mov     rbp, [rsp+88h+Memory]
0x140042ec6  xor     sil, sil
0x140042ec9  xor     edi, edi
0x140042ecb  cmp     [rbp+0], edi
0x140042ece  jbe     loc_14004307F
0x140042ed4  mov     r14d, [rsp+88h+arg_28]
0x140042edc  mov     r15, [rsp+88h+arg_20]
0x140042ee4  mov     rcx, [rsp+88h+Source1]; Source1
0x140042eec  mov     r8d, 8; Length
0x140042ef2  mov     eax, edi
0x140042ef4  imul    rbx, rax, 68h ; 'h'
0x140042ef8  add     rbx, 8
0x140042efc  add     rbx, rbp
0x140042eff  mov     rdx, rbx; Source2
0x140042f02  call    cs:__imp_RtlCompareMemory
0x140042f09  nop     dword ptr [rax+rax+00h]
0x140042f0e  cmp     rax, 8
0x140042f12  jnz     short loc_140042F4E
0x140042f14  mov     r9d, [rsp+88h+arg_18]; unsigned int
0x140042f1c  mov     edx, r12d; unsigned int
0x140042f1f  mov     r8, [rsp+88h+arg_10]; struct _MBB_IPADDRESS_ENTRY *
0x140042f27  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140042f2a  mov     [rsp+88h+Row], rbx; Row
0x140042f2f  mov     [rsp+88h+var_60], r14d; unsigned int
0x140042f34  mov     [rsp+88h+var_68], r15; struct _MBB_IPADDRESS_ENTRY *
0x140042f39  call    ?MbbIpProcessRouteEntry@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0K0KPEAU_MIB_IPFORWARD_ROW2@@@Z; MbbIpProcessRouteEntry(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *)
0x140042f3e  mov     ecx, 1
0x140042f43  movzx   esi, sil
0x140042f47  cmp     al, cl
0x140042f49  cmovz   esi, ecx
0x140042f4c  jmp     short loc_140042F53
0x140042f4e  mov     ecx, 1
0x140042f53  mov     rbx, [rsp+88h+Memory]
0x140042f58  add     edi, ecx
0x140042f5a  cmp     edi, [rbx]
0x140042f5c  jb      short loc_140042EE4
0x140042f5e  test    sil, sil
0x140042f61  jz      loc_14004307F
0x140042f67  xor     esi, esi
0x140042f69  mov     [rsp+88h+arg_40], 0
0x140042f74  cmp     [rbx], esi
0x140042f76  jbe     loc_14004309F
0x140042f7c  lea     rdi, WPP_RECORDER_INITIALIZED
0x140042f83  lea     r14, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140042f8a  mov     eax, esi
0x140042f8c  lea     r9, [rsp+88h+arg_40]; unsigned int *
0x140042f94  imul    rbp, rax, 68h ; 'h'
0x140042f98  mov     edx, r12d; unsigned int
0x140042f9b  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140042f9e  lea     r15, [rbx+rbp]
0x140042fa2  lea     r8, [r15+8]; struct _MIB_IPFORWARD_ROW2 *
0x140042fa6  call    ?MbbIpFindRouteInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_IPFORWARD_ROW2@@PEAK@Z; MbbIpFindRouteInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *,ulong *)
0x140042fab  test    eax, eax
0x140042fad  jnz     loc_140043073
0x140042fb3  add     rbp, rbx
0x140042fb6  mov     ecx, 2
0x140042fbb  movzx   eax, word ptr [rbp+34h]
0x140042fbf  cmp     cx, ax
0x140042fc2  jnz     short loc_140042FF5
0x140042fc4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140042fcb  jz      short loc_14004302E
0x140042fcd  lea     r9d, [rcx+57h]
0x140042fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140042fd8  lea     rax, [rbp+38h]
0x140042fdc  mov     [rsp+88h+Row], rax
0x140042fe1  mov     rax, [r15+8]
0x140042fe5  mov     rcx, [rcx+40h]
0x140042fe9  mov     qword ptr [rsp+88h+var_60], rax
0x140042fee  call    WPP_RECORDER_SF_i_IPV4_
0x140042ff3  jmp     short loc_14004302E
0x140042ff5  mov     ecx, 17h
0x140042ffa  cmp     cx, ax
0x140042ffd  jnz     short loc_14004302E
0x140042fff  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140043006  jz      short loc_14004302E
0x140043008  lea     r9d, [rcx+43h]
0x14004300c  mov     rcx, cs:WPP_GLOBAL_Control
0x140043013  lea     rax, [rbp+3Ch]
0x140043017  mov     [rsp+88h+Row], rax
0x14004301c  mov     rax, [r15+8]
0x140043020  mov     rcx, [rcx+40h]
0x140043024  mov     qword ptr [rsp+88h+var_60], rax
0x140043029  call    WPP_RECORDER_SF_i_IPV6_
0x14004302e  lea     rcx, [rbp+8]; Row
0x140043032  call    cs:__imp_DeleteIpForwardEntry2
0x140043039  nop     dword ptr [rax+rax+00h]
0x14004303e  test    eax, eax
0x140043040  jz      short loc_140043073
0x140043042  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140043049  jz      short loc_140043073
0x14004304b  mov     rcx, cs:WPP_GLOBAL_Control
0x140043052  mov     r9d, 5Bh ; '['
0x140043058  mov     dword ptr [rsp+88h+Row], eax
0x14004305c  mov     rax, [r15+8]
0x140043060  mov     qword ptr [rsp+88h+var_60], rax
0x140043065  mov     rcx, [rcx+40h]
0x140043069  mov     [rsp+88h+var_68], r14
0x14004306e  call    WPP_RECORDER_SF_id
0x140043073  inc     esi
0x140043075  cmp     esi, [rbx]
0x140043077  jb      loc_140042F8A
0x14004307d  jmp     short loc_14004309A
0x14004307f  mov     r9d, [rsp+88h+arg_38]; unsigned int
0x140043087  mov     edx, r12d; unsigned int
0x14004308a  mov     r8, [rsp+88h+Source1]; union _NET_LUID_LH *
0x140043092  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140043095  call    ?MbbIpReportRoutes@@YAXPEAU_MBB_IPADDRESS_ENTRY@@KPEAT_NET_LUID_LH@@K@Z; MbbIpReportRoutes(_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong)
0x14004309a  mov     rbx, [rsp+88h+Memory]
0x14004309f  mov     rcx, rbx; Memory
0x1400430a2  call    cs:__imp_FreeMibTable
0x1400430a9  nop     dword ptr [rax+rax+00h]
0x1400430ae  mov     rbx, [rsp+88h+arg_0]
0x1400430b6  add     rsp, 50h
0x1400430ba  pop     r15
0x1400430bc  pop     r14
0x1400430be  pop     r13
0x1400430c0  pop     r12
0x1400430c2  pop     rdi
0x1400430c3  pop     rsi
0x1400430c4  pop     rbp
0x1400430c5  retn
```
