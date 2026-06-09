# MbbIpProcessIpEntry(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong,_MIB_UNICASTIPADDRESS_ROW *)

- ea: `0x1400445e8`
- end: `0x1400448bf`
- name: `?MbbIpProcessIpEntry@@YAEPEAU_MBB_IPADDRESS_ENTRY@@K0KPEAU_MIB_UNICASTIPADDRESS_ROW@@@Z`
- size: `727`
- prototype: `unsigned __int8 __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int, MIB_UNICASTIPADDRESS_ROW *Row)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140042bf4`

## callees

- `0x14004316c`
- `0x1400445e8`
- `0x140046378`
- `0x14004654c`
- `0x1400466a4`
- `0x140046888`

## import_xrefs

- `NETIO!DeleteUnicastIpAddressEntry` at `0x14004489e`
- `NETIO!DeleteUnicastIpAddressEntry` at `0x14004489e`

## pseudocode

```c
unsigned __int8 __fastcall MbbIpProcessIpEntry(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MBB_IPADDRESS_ENTRY *a3,
        unsigned int a4,
        MIB_UNICASTIPADDRESS_ROW *Row)
{
  char v5; // r14
  bool v10; // bp
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  unsigned int v16[22]; // [rsp+60h] [rbp-58h] BYREF

  v5 = 0;
  v16[0] = 0;
  v10 = Row->PrefixOrigin == IpPrefixOriginDhcp || Row->SuffixOrigin == NlsoDhcp;
  if ( Row->Address.Ipv4.sin_family == 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_i_IPV4_dddd(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)Row + 4, (_DWORD)a3, a4);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_i_IPV6_dddd(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)Row + 8, (_DWORD)a3, a4);
  }
  if ( (unsigned int)MbbIpFindIpInTable(a1, a2, Row, v16) )
  {
    if ( !(unsigned int)MbbIpFindIpInTable(a3, a4, Row, v16) || v10 )
    {
      if ( Row->Address.Ipv4.sin_family == 2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v13, v14, 67);
      }
      else if ( Row->Address.Ipv4.sin_family == 23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, Row->InterfaceLuid.Value, v14, 68);
      }
      DeleteUnicastIpAddressEntry(Row);
    }
    else if ( Row->PrefixOrigin == IpPrefixOriginManual || Row->SuffixOrigin == NlsoManual )
    {
      if ( Row->Address.Ipv4.sin_family == 2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v13, v14, 69);
      }
      else if ( Row->Address.Ipv4.sin_family == 23 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v13, v14, 70);
      }
      return 1;
    }
  }
  else
  {
    if ( Row->Address.Ipv4.sin_family == 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 65);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 66);
    }
    *((_DWORD *)a1 + 6 * v16[0]) |= 2u;
  }
  return v5;
}

```

## disassembly

```asm
0x1400445e8  push    rbx
0x1400445ea  push    rbp
0x1400445eb  push    rsi
0x1400445ec  push    rdi
0x1400445ed  push    r12
0x1400445ef  push    r13
0x1400445f1  push    r14
0x1400445f3  push    r15
0x1400445f5  sub     rsp, 78h
0x1400445f9  mov     rbx, [rsp+0B8h+Row]
0x140044601  xor     r14b, r14b
0x140044604  mov     r12d, r9d
0x140044607  mov     [rsp+0B8h+var_58], 0
0x14004460f  mov     r13, r8
0x140044612  mov     r15d, edx
0x140044615  mov     rsi, rcx
0x140044618  mov     r11d, [rbx+2Ch]
0x14004461c  lea     r10, [rbx+30h]
0x140044620  cmp     r11d, 3
0x140044624  jz      short loc_140044631
0x140044626  cmp     dword ptr [r10], 3
0x14004462a  jz      short loc_140044631
0x14004462c  xor     bpl, bpl
0x14004462f  jmp     short loc_140044634
0x140044631  mov     bpl, 1
0x140044634  mov     eax, 2
0x140044639  cmp     ax, [rbx]
0x14004463c  jnz     short loc_140044691
0x14004463e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140044645  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14004464c  jz      loc_1400446DE
0x140044652  mov     eax, [rbx+40h]
0x140044655  lea     rdx, [rbx+4]
0x140044659  movzx   ecx, byte ptr [rbx+3Ch]
0x14004465d  mov     [rsp+0B8h+var_68], eax
0x140044661  mov     eax, [r10]
0x140044664  mov     [rsp+0B8h+var_70], ecx
0x140044668  mov     rcx, cs:WPP_GLOBAL_Control
0x14004466f  mov     [rsp+0B8h+var_78], eax
0x140044673  mov     rax, [rbx+20h]
0x140044677  mov     [rsp+0B8h+var_80], r11d
0x14004467c  mov     rcx, [rcx+40h]
0x140044680  mov     [rsp+0B8h+var_88], rdx
0x140044685  mov     [rsp+0B8h+var_90], rax
0x14004468a  call    WPP_RECORDER_SF_i_IPV4_dddd
0x14004468f  jmp     short loc_1400446DE
0x140044691  lea     rdi, WPP_RECORDER_INITIALIZED
0x140044698  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14004469f  jz      short loc_1400446DE
0x1400446a1  mov     eax, [rbx+40h]
0x1400446a4  lea     rdx, [rbx+8]
0x1400446a8  movzx   ecx, byte ptr [rbx+3Ch]
0x1400446ac  mov     [rsp+0B8h+var_68], eax
0x1400446b0  mov     eax, [r10]
0x1400446b3  mov     [rsp+0B8h+var_70], ecx
0x1400446b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400446be  mov     [rsp+0B8h+var_78], eax
0x1400446c2  mov     rax, [rbx+20h]
0x1400446c6  mov     [rsp+0B8h+var_80], r11d
0x1400446cb  mov     rcx, [rcx+40h]
0x1400446cf  mov     [rsp+0B8h+var_88], rdx
0x1400446d4  mov     [rsp+0B8h+var_90], rax
0x1400446d9  call    WPP_RECORDER_SF_i_IPV6_dddd
0x1400446de  lea     r9, [rsp+0B8h+var_58]; unsigned int *
0x1400446e3  mov     r8, rbx; struct _MIB_UNICASTIPADDRESS_ROW *
0x1400446e6  mov     edx, r15d; unsigned int
0x1400446e9  mov     rcx, rsi; struct _MBB_IPADDRESS_ENTRY *
0x1400446ec  call    ?MbbIpFindIpInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_UNICASTIPADDRESS_ROW@@PEAK@Z; MbbIpFindIpInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_UNICASTIPADDRESS_ROW *,ulong *)
0x1400446f1  test    eax, eax
0x1400446f3  jnz     short loc_14004476F
0x1400446f5  lea     ebp, [rax+2]
0x1400446f8  cmp     bp, [rbx]
0x1400446fb  jnz     short loc_14004472E
0x1400446fd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044704  jz      short loc_14004475F
0x140044706  mov     rcx, cs:WPP_GLOBAL_Control
0x14004470d  lea     rax, [rbx+4]
0x140044711  mov     [rsp+0B8h+var_88], rax
0x140044716  lea     r9d, [rbp+3Fh]
0x14004471a  mov     rax, [rbx+20h]
0x14004471e  mov     [rsp+0B8h+var_90], rax
0x140044723  mov     rcx, [rcx+40h]
0x140044727  call    WPP_RECORDER_SF_i_IPV4_
0x14004472c  jmp     short loc_14004475F
0x14004472e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044735  jz      short loc_14004475F
0x140044737  mov     rcx, cs:WPP_GLOBAL_Control
0x14004473e  lea     rax, [rbx+8]
0x140044742  mov     [rsp+0B8h+var_88], rax
0x140044747  mov     r9d, 42h ; 'B'
0x14004474d  mov     rax, [rbx+20h]
0x140044751  mov     [rsp+0B8h+var_90], rax
0x140044756  mov     rcx, [rcx+40h]
0x14004475a  call    WPP_RECORDER_SF_i_IPV6_
0x14004475f  mov     eax, [rsp+0B8h+var_58]
0x140044763  lea     rcx, [rax+rax*2]
0x140044767  or      [rsi+rcx*8], ebp
0x14004476a  jmp     loc_1400448AA
0x14004476f  lea     r9, [rsp+0B8h+var_58]; unsigned int *
0x140044774  mov     r8, rbx; struct _MIB_UNICASTIPADDRESS_ROW *
0x140044777  mov     edx, r12d; unsigned int
0x14004477a  mov     rcx, r13; struct _MBB_IPADDRESS_ENTRY *
0x14004477d  call    ?MbbIpFindIpInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_UNICASTIPADDRESS_ROW@@PEAK@Z; MbbIpFindIpInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_UNICASTIPADDRESS_ROW *,ulong *)
0x140044782  test    eax, eax
0x140044784  jz      loc_140044824
0x14004478a  test    bpl, bpl
0x14004478d  jnz     loc_140044824
0x140044793  cmp     dword ptr [rbx+2Ch], 1
0x140044797  jz      short loc_1400447A3
0x140044799  cmp     dword ptr [rbx+30h], 1
0x14004479d  jnz     loc_1400448AA
0x1400447a3  movzx   ecx, word ptr [rbx]
0x1400447a6  mov     ebp, 2
0x1400447ab  cmp     bp, cx
0x1400447ae  jnz     short loc_1400447E1
0x1400447b0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400447b7  jz      short loc_14004481C
0x1400447b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400447c0  lea     rax, [rbx+4]
0x1400447c4  mov     [rsp+0B8h+var_88], rax
0x1400447c9  lea     r9d, [rbp+43h]
0x1400447cd  mov     rax, [rbx+20h]
0x1400447d1  mov     [rsp+0B8h+var_90], rax
0x1400447d6  mov     rcx, [rcx+40h]
0x1400447da  call    WPP_RECORDER_SF_i_IPV4_
0x1400447df  jmp     short loc_14004481C
0x1400447e1  mov     eax, 17h
0x1400447e6  cmp     ax, cx
0x1400447e9  jnz     short loc_14004481C
0x1400447eb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400447f2  jz      short loc_14004481C
0x1400447f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400447fb  lea     rax, [rbx+8]
0x1400447ff  mov     [rsp+0B8h+var_88], rax
0x140044804  mov     r9d, 46h ; 'F'
0x14004480a  mov     rax, [rbx+20h]
0x14004480e  mov     [rsp+0B8h+var_90], rax
0x140044813  mov     rcx, [rcx+40h]
0x140044817  call    WPP_RECORDER_SF_i_IPV6_
0x14004481c  mov     r14b, 1
0x14004481f  jmp     loc_1400448AA
0x140044824  movzx   ecx, word ptr [rbx]
0x140044827  mov     ebp, 2
0x14004482c  cmp     bp, cx
0x14004482f  jnz     short loc_140044862
0x140044831  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044838  jz      short loc_14004489B
0x14004483a  mov     rcx, cs:WPP_GLOBAL_Control
0x140044841  lea     rax, [rbx+4]
0x140044845  mov     [rsp+0B8h+var_88], rax
0x14004484a  lea     r9d, [rbp+41h]
0x14004484e  mov     rax, [rbx+20h]
0x140044852  mov     [rsp+0B8h+var_90], rax
0x140044857  mov     rcx, [rcx+40h]
0x14004485b  call    WPP_RECORDER_SF_i_IPV4_
0x140044860  jmp     short loc_14004489B
0x140044862  mov     eax, 17h
0x140044867  cmp     ax, cx
0x14004486a  jnz     short loc_14004489B
0x14004486c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140044873  jz      short loc_14004489B
0x140044875  mov     rcx, cs:WPP_GLOBAL_Control
0x14004487c  lea     rdx, [rbx+8]
0x140044880  mov     [rsp+0B8h+var_88], rdx
0x140044885  lea     r9d, [rax+2Dh]
0x140044889  mov     rdx, [rbx+20h]
0x14004488d  mov     [rsp+0B8h+var_90], rdx
0x140044892  mov     rcx, [rcx+40h]
0x140044896  call    WPP_RECORDER_SF_i_IPV6_
0x14004489b  mov     rcx, rbx; Row
0x14004489e  call    cs:__imp_DeleteUnicastIpAddressEntry
0x1400448a5  nop     dword ptr [rax+rax+00h]
0x1400448aa  mov     al, r14b
0x1400448ad  add     rsp, 78h
0x1400448b1  pop     r15
0x1400448b3  pop     r14
0x1400448b5  pop     r13
0x1400448b7  pop     r12
0x1400448b9  pop     rdi
0x1400448ba  pop     rsi
0x1400448bb  pop     rbp
0x1400448bc  pop     rbx
0x1400448bd  retn
```
