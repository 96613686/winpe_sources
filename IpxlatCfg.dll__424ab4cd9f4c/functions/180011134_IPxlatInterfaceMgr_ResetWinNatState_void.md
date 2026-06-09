# IPxlatInterfaceMgr::ResetWinNatState(void)

- ea: `0x180011134`
- end: `0x1800113cd`
- name: `?ResetWinNatState@IPxlatInterfaceMgr@@AEAAXXZ`
- size: `665`
- prototype: `void __fastcall(struct in_addr *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x180011134`
- `0x180016860`
- `0x180016d2c`

## import_xrefs

- `NSI!NsiSetAllParameters` at `0x180011264`
- `NSI!NsiSetAllParameters` at `0x180011264`
- `NSI!NsiGetAllParameters` at `0x180011229`
- `NSI!NsiGetAllParameters` at `0x180011229`
- `NSI!NsiAllocateAndGetTable` at `0x1800111bc`
- `NSI!NsiAllocateAndGetTable` at `0x1800111bc`
- `NSI!NsiFreeTable` at `0x18001139a`
- `NSI!NsiFreeTable` at `0x18001139a`

## string_xrefs

- `0x18001128e`: `Service and driver out of sync. Disabled translation on this interface`
- `0x1800112e6`: `CleanupInterface is called to remove synthetic IPv4 and IPv6`

## pseudocode

```c
void __fastcall IPxlatInterfaceMgr::ResetWinNatState(struct in_addr *this)
{
  unsigned int i; // ebx
  __int64 v3; // rcx
  __int64 v4; // r8
  char v5; // al
  unsigned __int8 s_b1; // r15
  unsigned __int64 v7; // rdi
  char v8; // [rsp+60h] [rbp-98h]
  in_addr v9; // [rsp+70h] [rbp-88h] BYREF
  unsigned int v10; // [rsp+74h] [rbp-84h] BYREF
  unsigned __int64 v11; // [rsp+78h] [rbp-80h] BYREF
  __int64 v12; // [rsp+80h] [rbp-78h] BYREF
  unsigned __int64 v13; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v14[16]; // [rsp+90h] [rbp-68h] BYREF
  const char *v15; // [rsp+A0h] [rbp-58h]
  __int64 v16; // [rsp+A8h] [rbp-50h]
  unsigned __int64 *v17; // [rsp+B0h] [rbp-48h]
  __int64 v18; // [rsp+B8h] [rbp-40h]

  v8 = 0;
  v12 = 0;
  v10 = 0;
  if ( !(unsigned int)NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v12, 8, 0, 0, 0, 0, 0, 0, &v10, v8) )
  {
    for ( i = 0; i < v10; ++i )
    {
      v11 = 0;
      v11 = *(_QWORD *)(v12 + 8LL * i);
      if ( !(unsigned int)NsiGetAllParameters(1, NPI_MS_WINNAT_MODULEID, 11, &v11, 8, 0, 0, 0, 0, 0, 0) )
      {
        NsiSetAllParameters(1, 3, NPI_MS_WINNAT_MODULEID);
        v5 = Microsoft_Windows_IPxlatCfgEnableBits;
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
        {
          v13 = v11;
          v16 = 71;
          v15 = "Service and driver out of sync. Disabled translation on this interface";
          v17 = &v13;
          v18 = 8;
          McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v14);
          v5 = Microsoft_Windows_IPxlatCfgEnableBits;
        }
        s_b1 = this[25].S_un.S_un_b.s_b1;
        v7 = v11;
        if ( (v5 & 2) != 0 )
        {
          v13 = v11;
          v15 = "CleanupInterface is called to remove synthetic IPv4 and IPv6";
          v16 = 61;
          v17 = &v13;
          v18 = 8;
          McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_INTERFACE_INFO_EVENT, v4, 3, v14);
        }
        v9.S_un.S_un_b.s_b1 = 0;
        *(_WORD *)&v9.S_un.S_un_b.s_b2 = 0;
        v9.S_un.S_un_b.s_b4 = 0;
        if ( IPxlatInterface::TryGetInterfaceSyntheticIPv4Address(v7, this + 24, s_b1, &v9) )
          IPxlatInterface::UnPlumbInterfaceSyntheticIpAndRoute(v7, this + 24, &v9);
      }
    }
    if ( v12 )
      NsiFreeTable(v12, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x180011134  mov     r11, rsp
0x180011137  mov     [r11+10h], rbx
0x18001113b  mov     [r11+18h], rsi
0x18001113f  push    rdi
0x180011140  push    r12
0x180011142  push    r13
0x180011144  push    r14
0x180011146  push    r15
0x180011148  sub     rsp, 0D0h
0x18001114f  mov     rax, cs:__security_cookie
0x180011156  xor     rax, rsp
0x180011159  mov     [rsp+0F8h+var_38], rax
0x180011161  xor     r12d, r12d
0x180011164  lea     rax, [rsp+0F8h+var_84]
0x180011169  mov     [rsp+0F8h+var_98], r12b
0x18001116e  lea     r9, [r11-78h]
0x180011172  mov     [rsp+0F8h+var_A0], rax
0x180011177  lea     rdx, NPI_MS_IPV6_MODULEID
0x18001117e  mov     [rsp+0F8h+var_A8], r12d
0x180011183  mov     r14, rcx
0x180011186  mov     [rsp+0F8h+var_B0], r12
0x18001118b  lea     r13d, [r12+8]
0x180011190  mov     [rsp+0F8h+var_B8], r12d
0x180011195  lea     r8d, [r12+7]
0x18001119a  mov     [rsp+0F8h+var_C0], r12
0x18001119f  lea     ecx, [r12+1]
0x1800111a4  mov     dword ptr [rsp+0F8h+var_C8], r12d
0x1800111a9  mov     [rsp+0F8h+var_D0], r12
0x1800111ae  mov     dword ptr [rsp+0F8h+var_D8], r13d
0x1800111b3  mov     [r11-78h], r12
0x1800111b7  mov     [rsp+0F8h+var_84], r12d
0x1800111bc  call    cs:__imp_NsiAllocateAndGetTable
0x1800111c2  test    eax, eax
0x1800111c4  jnz     loc_1800113A0
0x1800111ca  mov     ebx, r12d
0x1800111cd  cmp     [rsp+0F8h+var_84], r12d
0x1800111d2  jbe     loc_180011385
0x1800111d8  mov     rax, [rsp+0F8h+var_78]
0x1800111e0  lea     r9, [rsp+0F8h+var_80]
0x1800111e5  mov     [rsp+0F8h+var_A8], r12d
0x1800111ea  lea     rdx, NPI_MS_WINNAT_MODULEID
0x1800111f1  mov     [rsp+0F8h+var_B0], r12
0x1800111f6  mov     r8d, 0Bh
0x1800111fc  mov     [rsp+0F8h+var_B8], r12d
0x180011201  mov     [rsp+0F8h+var_80], r12
0x180011206  mov     [rsp+0F8h+var_C0], r12
0x18001120b  mov     dword ptr [rsp+0F8h+var_C8], r12d
0x180011210  mov     ecx, ebx
0x180011212  mov     [rsp+0F8h+var_D0], r12
0x180011217  mov     dword ptr [rsp+0F8h+var_D8], r13d
0x18001121c  mov     rcx, [rax+rcx*8]
0x180011220  mov     [rsp+0F8h+var_80], rcx
0x180011225  lea     ecx, [r8-0Ah]
0x180011229  call    cs:__imp_NsiGetAllParameters
0x18001122f  test    eax, eax
0x180011231  jnz     loc_180011379
0x180011237  mov     dword ptr [rsp+0F8h+var_C0], r12d
0x18001123c  lea     rax, [rsp+0F8h+var_80]
0x180011241  mov     r9d, 0Bh
0x180011247  mov     [rsp+0F8h+var_C8], r12
0x18001124c  mov     dword ptr [rsp+0F8h+var_D0], r13d
0x180011251  lea     r8, NPI_MS_WINNAT_MODULEID
0x180011258  mov     [rsp+0F8h+var_D8], rax
0x18001125d  lea     edx, [r9-8]
0x180011261  lea     ecx, [rdx-2]
0x180011264  call    cs:__imp_NsiSetAllParameters
0x18001126a  mov     eax, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x180011270  test    al, 2
0x180011272  jz      short loc_1800112D9
0x180011274  mov     rax, [rsp+0F8h+var_80]
0x180011279  lea     rdx, IPXLATCFG_INTERFACE_INFO_EVENT
0x180011280  mov     [rsp+0F8h+var_70], rax
0x180011288  mov     r9d, 3
0x18001128e  lea     rax, aServiceAndDriv; "Service and driver out of sync. Disable"...
0x180011295  mov     [rsp+0F8h+var_50], 47h ; 'G'
0x1800112a1  mov     [rsp+0F8h+var_58], rax
0x1800112a9  lea     rax, [rsp+0F8h+var_70]
0x1800112b1  mov     [rsp+0F8h+var_48], rax
0x1800112b9  lea     rax, [rsp+0F8h+var_68]
0x1800112c1  mov     [rsp+0F8h+var_D8], rax
0x1800112c6  mov     [rsp+0F8h+var_40], r13
0x1800112ce  call    McGenEventWrite_EventWriteTransfer
0x1800112d3  mov     eax, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x1800112d9  mov     r15b, [r14+64h]
0x1800112dd  mov     rdi, [rsp+0F8h+var_80]
0x1800112e2  test    al, 2
0x1800112e4  jz      short loc_180011340
0x1800112e6  lea     rax, aCleanupinterfa; "CleanupInterface is called to remove sy"...
0x1800112ed  mov     [rsp+0F8h+var_70], rdi
0x1800112f5  mov     [rsp+0F8h+var_58], rax
0x1800112fd  lea     rdx, IPXLATCFG_INTERFACE_INFO_EVENT
0x180011304  lea     rax, [rsp+0F8h+var_70]
0x18001130c  mov     [rsp+0F8h+var_50], 3Dh ; '='
0x180011318  mov     [rsp+0F8h+var_48], rax
0x180011320  mov     r9d, 3
0x180011326  lea     rax, [rsp+0F8h+var_68]
0x18001132e  mov     [rsp+0F8h+var_40], r13
0x180011336  mov     [rsp+0F8h+var_D8], rax
0x18001133b  call    McGenEventWrite_EventWriteTransfer
0x180011340  xor     eax, eax
0x180011342  mov     byte ptr [rsp+0F8h+var_88.S_un], r12b
0x180011347  lea     r9, [rsp+0F8h+var_88]; struct in_addr *
0x18001134c  mov     word ptr [rsp+0F8h+var_88.S_un+1], ax
0x180011351  mov     r8b, r15b; unsigned __int8
0x180011354  mov     byte ptr [rsp+0F8h+var_88.S_un+3], al
0x180011358  lea     rdx, [r14+60h]; struct in_addr *
0x18001135c  mov     rcx, rdi; unsigned __int64
0x18001135f  call    ?TryGetInterfaceSyntheticIPv4Address@IPxlatInterface@@CA_N_KAEAUin_addr@@EPEAU2@@Z; IPxlatInterface::TryGetInterfaceSyntheticIPv4Address(unsigned __int64,in_addr &,uchar,in_addr *)
0x180011364  test    al, al
0x180011366  jz      short loc_180011379
0x180011368  lea     r8, [rsp+0F8h+var_88]; struct in_addr *
0x18001136d  mov     rcx, rdi; unsigned __int64
0x180011370  lea     rdx, [r14+60h]; struct in_addr *
0x180011374  call    ?UnPlumbInterfaceSyntheticIpAndRoute@IPxlatInterface@@CAX_KAEAUin_addr@@1@Z; IPxlatInterface::UnPlumbInterfaceSyntheticIpAndRoute(unsigned __int64,in_addr &,in_addr &)
0x180011379  inc     ebx
0x18001137b  cmp     ebx, [rsp+0F8h+var_84]
0x18001137f  jb      loc_1800111D8
0x180011385  mov     rcx, [rsp+0F8h+var_78]
0x18001138d  test    rcx, rcx
0x180011390  jz      short loc_1800113A0
0x180011392  xor     r9d, r9d
0x180011395  xor     r8d, r8d
0x180011398  xor     edx, edx
0x18001139a  call    cs:__imp_NsiFreeTable
0x1800113a0  mov     rcx, [rsp+0F8h+var_38]
0x1800113a8  xor     rcx, rsp; StackCookie
0x1800113ab  call    __security_check_cookie
0x1800113b0  lea     r11, [rsp+0F8h+var_28]
0x1800113b8  mov     rbx, [r11+38h]
0x1800113bc  mov     rsi, [r11+40h]
0x1800113c0  mov     rsp, r11
0x1800113c3  pop     r15
0x1800113c5  pop     r14
0x1800113c7  pop     r13
0x1800113c9  pop     r12
0x1800113cb  pop     rdi
0x1800113cc  retn
```
