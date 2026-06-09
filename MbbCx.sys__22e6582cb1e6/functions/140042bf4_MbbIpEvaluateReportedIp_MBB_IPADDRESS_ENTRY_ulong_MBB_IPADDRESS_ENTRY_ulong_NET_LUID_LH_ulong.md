# MbbIpEvaluateReportedIp(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong)

- ea: `0x140042bf4`
- end: `0x140042e27`
- name: `?MbbIpEvaluateReportedIp@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0KPEAT_NET_LUID_LH@@K@Z`
- size: `563`
- prototype: `char __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int, union _NET_LUID_LH *Source1, NET_IFINDEX)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140046d80`

## callees

- `0x140042bf4`
- `0x14004316c`
- `0x1400445e8`
- `0x1400450ac`
- `0x140046378`
- `0x1400466a4`
- `0x1400469e8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140042cad`
- `ntoskrnl!RtlCompareMemory` at `0x140042cad`
- `NETIO!FreeMibTable` at `0x140042e06`
- `NETIO!FreeMibTable` at `0x140042e06`
- `NETIO!GetUnicastIpAddressTable` at `0x140042c21`
- `NETIO!GetUnicastIpAddressTable` at `0x140042c21`
- `NETIO!DeleteUnicastIpAddressEntry` at `0x140042dcb`
- `NETIO!DeleteUnicastIpAddressEntry` at `0x140042dcb`

## pseudocode

```c
char __fastcall MbbIpEvaluateReportedIp(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MBB_IPADDRESS_ENTRY *a3,
        unsigned int a4,
        union _NET_LUID_LH *Source1,
        NET_IFINDEX a6)
{
  NTSTATUS UnicastIpAddressTable; // eax
  int v11; // edx
  int v12; // r8d
  PMIB_UNICASTIPADDRESS_TABLE v14; // rsi
  char v15; // r14
  __int64 v16; // rdi
  PMIB_UNICASTIPADDRESS_TABLE v17; // rbx
  __int64 v18; // rbp
  char *v19; // rsi
  int v20; // edx
  int v21; // r8d
  ADDRESS_FAMILY sin_family; // ax
  unsigned int v23; // [rsp+40h] [rbp-58h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+48h] [rbp-50h] BYREF

  Table = 0;
  UnicastIpAddressTable = GetUnicastIpAddressTable(0, &Table);
  if ( !UnicastIpAddressTable )
  {
    v14 = Table;
    v15 = 0;
    v16 = 0;
    if ( !Table->NumEntries )
      goto LABEL_22;
    do
    {
      if ( RtlCompareMemory(Source1, &v14->Table[v16].InterfaceLuid, 8u) == 8
        && MbbIpProcessIpEntry(a1, a2, a3, a4, &v14->Table[v16]) == 1 )
      {
        v15 = 1;
      }
      v17 = Table;
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < Table->NumEntries );
    if ( v15 )
    {
      v18 = 0;
      v23 = 0;
      if ( !Table->NumEntries )
      {
LABEL_24:
        FreeMibTable(v17);
        return v15;
      }
      do
      {
        v19 = (char *)v17 + 80 * v18;
        if ( !(unsigned int)MbbIpFindIpInTable(a1, a2, (struct _MIB_UNICASTIPADDRESS_ROW *)(v19 + 8), &v23) )
        {
          sin_family = v17->Table[v18].Address.Ipv4.sin_family;
          if ( sin_family == 2 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v20, v21, 76);
          }
          else if ( sin_family == 23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v20, v21, 77);
          }
          DeleteUnicastIpAddressEntry((const MIB_UNICASTIPADDRESS_ROW *)(v19 + 8));
        }
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < v17->NumEntries );
    }
    else
    {
LABEL_22:
      MbbIpReportIps(a1, a2, Source1, a6);
    }
    v17 = Table;
    goto LABEL_24;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_id(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      v12,
      40,
      (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids,
      Source1->Value,
      UnicastIpAddressTable);
  return 0;
}

```

## disassembly

```asm
0x140042bf4  push    rbx
0x140042bf6  push    rbp
0x140042bf7  push    rsi
0x140042bf8  push    rdi
0x140042bf9  push    r12
0x140042bfb  push    r13
0x140042bfd  push    r14
0x140042bff  push    r15
0x140042c01  sub     rsp, 58h
0x140042c05  mov     r12d, edx
0x140042c08  mov     [rsp+98h+Table], 0
0x140042c11  mov     r13, rcx
0x140042c14  lea     rdx, [rsp+98h+Table]; Table
0x140042c19  xor     ecx, ecx; Family
0x140042c1b  mov     ebp, r9d
0x140042c1e  mov     r15, r8
0x140042c21  call    cs:__imp_GetUnicastIpAddressTable
0x140042c28  nop     dword ptr [rax+rax+00h]
0x140042c2d  test    eax, eax
0x140042c2f  jz      short loc_140042C7E
0x140042c31  lea     rdi, WPP_RECORDER_INITIALIZED
0x140042c38  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140042c3f  jz      short loc_140042C77
0x140042c41  mov     dword ptr [rsp+98h+var_68], eax
0x140042c45  mov     r9d, 28h ; '('
0x140042c4b  mov     rax, [rsp+98h+Source1]
0x140042c53  mov     rcx, [rax]
0x140042c56  lea     rax, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x140042c5d  mov     [rsp+98h+var_70], rcx
0x140042c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140042c69  mov     [rsp+98h+Row], rax
0x140042c6e  mov     rcx, [rcx+40h]
0x140042c72  call    WPP_RECORDER_SF_id
0x140042c77  xor     al, al
0x140042c79  jmp     loc_140042E15
0x140042c7e  mov     rsi, [rsp+98h+Table]
0x140042c83  xor     r14b, r14b
0x140042c86  xor     edi, edi
0x140042c88  cmp     [rsi], edi
0x140042c8a  jbe     loc_140042DE3
0x140042c90  mov     rcx, [rsp+98h+Source1]; Source1
0x140042c98  lea     rbx, [rdi+rdi*4]
0x140042c9c  shl     rbx, 4
0x140042ca0  lea     rdx, [rsi+28h]
0x140042ca4  add     rdx, rbx; Source2
0x140042ca7  mov     r8d, 8; Length
0x140042cad  call    cs:__imp_RtlCompareMemory
0x140042cb4  nop     dword ptr [rax+rax+00h]
0x140042cb9  cmp     rax, 8
0x140042cbd  jnz     short loc_140042CED
0x140042cbf  lea     rax, [rsi+8]
0x140042cc3  mov     r9d, ebp; unsigned int
0x140042cc6  add     rax, rbx
0x140042cc9  mov     r8, r15; struct _MBB_IPADDRESS_ENTRY *
0x140042ccc  mov     edx, r12d; unsigned int
0x140042ccf  mov     [rsp+98h+Row], rax; Row
0x140042cd4  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140042cd7  call    ?MbbIpProcessIpEntry@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0KPEAU_MIB_UNICASTIPADDRESS_ROW@@@Z; MbbIpProcessIpEntry(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MIB_UNICASTIPADDRESS_ROW *)
0x140042cdc  mov     ecx, 1
0x140042ce1  movzx   r14d, r14b
0x140042ce5  cmp     al, cl
0x140042ce7  cmovz   r14d, ecx
0x140042ceb  jmp     short loc_140042CF2
0x140042ced  mov     ecx, 1
0x140042cf2  mov     rbx, [rsp+98h+Table]
0x140042cf7  add     edi, ecx
0x140042cf9  cmp     edi, [rbx]
0x140042cfb  jb      short loc_140042C90
0x140042cfd  test    r14b, r14b
0x140042d00  jz      loc_140042DE3
0x140042d06  xor     ebp, ebp
0x140042d08  mov     [rsp+98h+var_58], 0
0x140042d10  cmp     [rbx], ebp
0x140042d12  jbe     loc_140042E03
0x140042d18  lea     rdi, WPP_RECORDER_INITIALIZED
0x140042d1f  lea     r15, ds:0[rbp*4]
0x140042d27  mov     edx, r12d; unsigned int
0x140042d2a  add     r15, rbp
0x140042d2d  lea     r9, [rsp+98h+var_58]; unsigned int *
0x140042d32  add     r15, r15
0x140042d35  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140042d38  lea     rsi, [rbx+r15*8]
0x140042d3c  lea     r8, [rsi+8]; struct _MIB_UNICASTIPADDRESS_ROW *
0x140042d40  call    ?MbbIpFindIpInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_UNICASTIPADDRESS_ROW@@PEAK@Z; MbbIpFindIpInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_UNICASTIPADDRESS_ROW *,ulong *)
0x140042d45  test    eax, eax
0x140042d47  jnz     loc_140042DD7
0x140042d4d  movzx   eax, word ptr [rbx+r15*8+8]
0x140042d53  mov     ecx, 2
0x140042d58  cmp     cx, ax
0x140042d5b  jnz     short loc_140042D8E
0x140042d5d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140042d64  jz      short loc_140042DC7
0x140042d66  lea     r9d, [rcx+4Ah]
0x140042d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140042d71  lea     rax, [rsi+0Ch]
0x140042d75  mov     [rsp+98h+var_68], rax
0x140042d7a  mov     rax, [rsi+28h]
0x140042d7e  mov     rcx, [rcx+40h]
0x140042d82  mov     [rsp+98h+var_70], rax
0x140042d87  call    WPP_RECORDER_SF_i_IPV4_
0x140042d8c  jmp     short loc_140042DC7
0x140042d8e  mov     ecx, 17h
0x140042d93  cmp     cx, ax
0x140042d96  jnz     short loc_140042DC7
0x140042d98  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140042d9f  jz      short loc_140042DC7
0x140042da1  lea     r9d, [rcx+36h]
0x140042da5  mov     rcx, cs:WPP_GLOBAL_Control
0x140042dac  lea     rax, [rsi+10h]
0x140042db0  mov     [rsp+98h+var_68], rax
0x140042db5  mov     rax, [rsi+28h]
0x140042db9  mov     rcx, [rcx+40h]
0x140042dbd  mov     [rsp+98h+var_70], rax
0x140042dc2  call    WPP_RECORDER_SF_i_IPV6_
0x140042dc7  lea     rcx, [rsi+8]; Row
0x140042dcb  call    cs:__imp_DeleteUnicastIpAddressEntry
0x140042dd2  nop     dword ptr [rax+rax+00h]
0x140042dd7  inc     ebp
0x140042dd9  cmp     ebp, [rbx]
0x140042ddb  jb      loc_140042D1F
0x140042de1  jmp     short loc_140042DFE
0x140042de3  mov     r9d, [rsp+98h+arg_28]; unsigned int
0x140042deb  mov     edx, r12d; unsigned int
0x140042dee  mov     r8, [rsp+98h+Source1]; union _NET_LUID_LH *
0x140042df6  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x140042df9  call    ?MbbIpReportIps@@YAXPEAU_MBB_IPADDRESS_ENTRY@@KPEAT_NET_LUID_LH@@K@Z; MbbIpReportIps(_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong)
0x140042dfe  mov     rbx, [rsp+98h+Table]
0x140042e03  mov     rcx, rbx; Memory
0x140042e06  call    cs:__imp_FreeMibTable
0x140042e0d  nop     dword ptr [rax+rax+00h]
0x140042e12  mov     al, r14b
0x140042e15  add     rsp, 58h
0x140042e19  pop     r15
0x140042e1b  pop     r14
0x140042e1d  pop     r13
0x140042e1f  pop     r12
0x140042e21  pop     rdi
0x140042e22  pop     rsi
0x140042e23  pop     rbp
0x140042e24  pop     rbx
0x140042e25  retn
```
