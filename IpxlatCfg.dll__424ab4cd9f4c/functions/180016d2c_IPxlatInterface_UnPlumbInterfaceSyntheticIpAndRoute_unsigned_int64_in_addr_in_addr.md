# IPxlatInterface::UnPlumbInterfaceSyntheticIpAndRoute(unsigned __int64,in_addr &,in_addr &)

- ea: `0x180016d2c`
- end: `0x180016f7e`
- name: `?UnPlumbInterfaceSyntheticIpAndRoute@IPxlatInterface@@CAX_KAEAUin_addr@@1@Z`
- size: `594`
- prototype: `void __fastcall(unsigned __int64, struct in_addr *, struct in_addr *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011134`

## callees

- `0x180001d40`
- `0x180012388`
- `0x180016a94`
- `0x180016d2c`

## import_xrefs

- `NSI!NsiSetAllParameters` at `0x180016de6`
- `NSI!NsiSetAllParameters` at `0x180016e50`
- `NSI!NsiSetAllParameters` at `0x180016ed3`
- `NSI!NsiSetAllParameters` at `0x180016f34`
- `NSI!NsiSetAllParameters` at `0x180016de6`
- `NSI!NsiSetAllParameters` at `0x180016e50`
- `NSI!NsiSetAllParameters` at `0x180016ed3`
- `NSI!NsiSetAllParameters` at `0x180016f34`

## string_xrefs

- `0x180016e01`: `Could not delete synthetic IPv6 address from the interface`
- `0x180016e6b`: `Could not delete ARP entry for default gateway`
- `0x180016eee`: `Could not delete route for synthetic IPv4 address`
- `0x180016f4f`: `Could not delete synthetic IPv4 address from the interface`

## pseudocode

```c
void __fastcall IPxlatInterface::UnPlumbInterfaceSyntheticIpAndRoute(
        unsigned __int64 a1,
        struct in_addr *a2,
        struct in_addr *a3)
{
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  int v17; // ecx
  in6_addr v18; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-49h]
  in6_addr v20; // [rsp+58h] [rbp-41h]
  unsigned __int64 v21; // [rsp+68h] [rbp-31h]
  __int64 v22; // [rsp+70h] [rbp-29h]
  __int128 v23; // [rsp+78h] [rbp-21h]
  __int64 v24; // [rsp+88h] [rbp-11h]
  unsigned __int64 v25; // [rsp+90h] [rbp-9h]
  unsigned __int64 v26; // [rsp+98h] [rbp-1h]
  __int64 v27; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v28; // [rsp+A8h] [rbp+Fh]
  unsigned __int64 v29; // [rsp+B0h] [rbp+17h]
  __int64 S_addr; // [rsp+B8h] [rbp+1Fh]

  *(_QWORD *)&v18.u.Byte[1] = 0;
  *(_DWORD *)((char *)&v18.u.Word[4] + 1) = 0;
  v19 = 0;
  v18.u.Byte[0] = 0;
  *(USHORT *)((char *)&v18.u.Word[6] + 1) = 0;
  v18.u.Byte[15] = 0;
  v20 = 0;
  if ( IPxlatInterface::TryGetInterfaceSyntheticIPv6Address(a1, a3, &v18) )
  {
    v20 = v18;
    v19 = a1;
    v6 = NsiSetAllParameters(1, 3, &NPI_MS_IPV6_MODULEID);
    if ( v6 )
    {
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        McTemplateU0sqx_EventWriteTransfer(
          v8,
          v7,
          (unsigned int)"Could not delete synthetic IPv6 address from the interface",
          v6,
          a1);
    }
  }
  S_addr = a2->S_un.S_addr;
  v28 = a1;
  v29 = a1;
  v9 = NsiSetAllParameters(1, 3, &NPI_MS_IPV4_MODULEID);
  if ( v9 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(v11, v10, (unsigned int)"Could not delete ARP entry for default gateway", v9, a1);
  v27 = a2->S_un.S_addr;
  v23 = 1u;
  v25 = a1;
  v26 = a1;
  v24 = 0;
  v12 = NsiSetAllParameters(1, 3, &NPI_MS_IPV4_MODULEID);
  if ( v12 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(
      v14,
      v13,
      (unsigned int)"Could not delete route for synthetic IPv4 address",
      v12,
      a1);
  v22 = 0;
  LODWORD(v22) = *a3;
  v21 = a1;
  v15 = NsiSetAllParameters(1, 3, &NPI_MS_IPV4_MODULEID);
  if ( v15 )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      McTemplateU0sqx_EventWriteTransfer(
        v17,
        v16,
        (unsigned int)"Could not delete synthetic IPv4 address from the interface",
        v15,
        a1);
  }
}

```

## disassembly

```asm
0x180016d2c  mov     [rsp-8+arg_18], rbx
0x180016d31  push    rbp
0x180016d32  push    rsi
0x180016d33  push    rdi
0x180016d34  push    r14
0x180016d36  push    r15
0x180016d38  lea     rbp, [rsp-37h]
0x180016d3d  sub     rsp, 0D0h
0x180016d44  mov     rax, cs:__security_cookie
0x180016d4b  xor     rax, rsp
0x180016d4e  mov     [rbp+57h+var_30], rax
0x180016d52  xor     eax, eax
0x180016d54  mov     rsi, r8
0x180016d57  mov     rdi, rdx
0x180016d5a  mov     qword ptr [rbp+57h+var_B0.u+1], rax
0x180016d5e  xor     r14d, r14d
0x180016d61  mov     dword ptr [rbp+57h+var_B0.u+9], eax
0x180016d64  xorps   xmm0, xmm0
0x180016d67  mov     [rbp+57h+var_A0], r14
0x180016d6b  mov     rdx, rsi; struct in_addr *
0x180016d6e  mov     byte ptr [rbp+57h+var_B0.u], r14b
0x180016d72  lea     r8, [rbp+57h+var_B0]; struct in6_addr *
0x180016d76  mov     word ptr [rbp+57h+var_B0.u+0Dh], ax
0x180016d7a  mov     rbx, rcx
0x180016d7d  mov     byte ptr [rbp+57h+var_B0.u+0Fh], al
0x180016d80  movups  [rbp+57h+var_98], xmm0
0x180016d84  call    ?TryGetInterfaceSyntheticIPv6Address@IPxlatInterface@@CA_N_KAEAUin_addr@@PEAUin6_addr@@@Z; IPxlatInterface::TryGetInterfaceSyntheticIPv6Address(unsigned __int64,in_addr &,in6_addr *)
0x180016d89  lea     r15d, [r14+1]
0x180016d8d  test    al, al
0x180016d8f  jz      short loc_180016E0D
0x180016d91  mov     al, byte ptr [rbp+57h+var_B0.u]
0x180016d94  lea     r9d, [r14+0Ah]
0x180016d98  movsd   xmm0, qword ptr [rbp+57h+var_B0.u+1]
0x180016d9d  lea     r8, NPI_MS_IPV6_MODULEID
0x180016da4  mov     byte ptr [rbp+57h+var_98], al
0x180016da7  lea     edx, [r14+3]
0x180016dab  mov     eax, dword ptr [rbp+57h+var_B0.u+9]
0x180016dae  mov     ecx, r15d
0x180016db1  mov     dword ptr [rbp+57h+var_98+9], eax
0x180016db4  movzx   eax, word ptr [rbp+57h+var_B0.u+0Dh]
0x180016db8  mov     word ptr [rbp+57h+var_98+0Dh], ax
0x180016dbc  mov     al, byte ptr [rbp+57h+var_B0.u+0Fh]
0x180016dbf  mov     [rsp+0F0h+var_B8], r14d
0x180016dc4  mov     byte ptr [rbp+57h+var_98+0Fh], al
0x180016dc7  lea     rax, [rbp+57h+var_A0]
0x180016dcb  mov     [rsp+0F0h+var_C0], r14
0x180016dd0  mov     [rsp+0F0h+var_C8], 18h
0x180016dd8  mov     [rsp+0F0h+var_D0], rax
0x180016ddd  mov     [rbp+57h+var_A0], rbx
0x180016de1  movsd   qword ptr [rbp+57h+var_98+1], xmm0
0x180016de6  call    cs:__imp_NsiSetAllParameters
0x180016dec  test    eax, eax
0x180016dee  jz      short loc_180016E0D
0x180016df0  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r15b
0x180016df7  jz      short loc_180016E0D
0x180016df9  mov     r9d, eax
0x180016dfc  mov     [rsp+0F0h+var_D0], rbx
0x180016e01  lea     r8, aCouldNotDelete_2; "Could not delete synthetic IPv6 address"...
0x180016e08  call    McTemplateU0sqx_EventWriteTransfer
0x180016e0d  mov     eax, [rdi]
0x180016e0f  lea     r8, NPI_MS_IPV4_MODULEID
0x180016e16  mov     [rsp+0F0h+var_B8], r14d
0x180016e1b  xorps   xmm0, xmm0
0x180016e1e  movups  [rbp+57h+var_40], xmm0
0x180016e22  mov     r9d, 0Bh
0x180016e28  mov     dword ptr [rbp+57h+var_40+8], eax
0x180016e2b  lea     rax, [rbp+57h+var_48]
0x180016e2f  mov     [rsp+0F0h+var_C0], r14
0x180016e34  mov     [rsp+0F0h+var_C8], 18h
0x180016e3c  mov     ecx, r15d
0x180016e3f  mov     [rsp+0F0h+var_D0], rax
0x180016e44  lea     edx, [r9-8]
0x180016e48  mov     [rbp+57h+var_48], rbx
0x180016e4c  mov     qword ptr [rbp+57h+var_40], rbx
0x180016e50  call    cs:__imp_NsiSetAllParameters
0x180016e56  test    eax, eax
0x180016e58  jz      short loc_180016E77
0x180016e5a  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r15b
0x180016e61  jz      short loc_180016E77
0x180016e63  mov     r9d, eax
0x180016e66  mov     [rsp+0F0h+var_D0], rbx
0x180016e6b  lea     r8, aCouldNotDelete_1; "Could not delete ARP entry for default "...
0x180016e72  call    McTemplateU0sqx_EventWriteTransfer
0x180016e77  mov     eax, [rdi]
0x180016e79  lea     r8, NPI_MS_IPV4_MODULEID
0x180016e80  xorps   xmm0, xmm0
0x180016e83  mov     [rsp+0F0h+var_B8], r14d
0x180016e88  movups  [rbp+57h+var_78], xmm0
0x180016e8c  mov     edi, 10h
0x180016e91  mov     [rsp+0F0h+var_C0], r14
0x180016e96  movups  [rbp+57h+var_58], xmm0
0x180016e9a  mov     dword ptr [rbp+57h+var_58+8], eax
0x180016e9d  lea     rax, [rbp+57h+var_78]
0x180016ea1  movups  [rbp+57h+var_68], xmm0
0x180016ea5  lea     edx, [rdi-0Dh]
0x180016ea8  mov     [rsp+0F0h+var_C8], 30h ; '0'
0x180016eb0  mov     r9d, edi
0x180016eb3  mov     qword ptr [rbp+57h+var_78], r15
0x180016eb7  mov     ecx, r15d
0x180016eba  mov     qword ptr [rbp+57h+var_68+8], rbx
0x180016ebe  mov     qword ptr [rbp+57h+var_58], rbx
0x180016ec2  mov     dword ptr [rbp+57h+var_78+0Ch], r14d
0x180016ec6  mov     byte ptr [rbp+57h+var_68], r14b
0x180016eca  mov     byte ptr [rbp+57h+var_78+8], r14b
0x180016ece  mov     [rsp+0F0h+var_D0], rax
0x180016ed3  call    cs:__imp_NsiSetAllParameters
0x180016ed9  test    eax, eax
0x180016edb  jz      short loc_180016EFA
0x180016edd  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r15b
0x180016ee4  jz      short loc_180016EFA
0x180016ee6  mov     r9d, eax
0x180016ee9  mov     [rsp+0F0h+var_D0], rbx
0x180016eee  lea     r8, aCouldNotDelete; "Could not delete route for synthetic IP"...
0x180016ef5  call    McTemplateU0sqx_EventWriteTransfer
0x180016efa  xor     eax, eax
0x180016efc  mov     [rsp+0F0h+var_B8], r14d
0x180016f01  mov     [rbp+57h+var_80], rax
0x180016f05  lea     r8, NPI_MS_IPV4_MODULEID
0x180016f0c  mov     eax, [rsi]
0x180016f0e  mov     r9d, 0Ah
0x180016f14  mov     dword ptr [rbp+57h+var_80], eax
0x180016f17  mov     ecx, r15d
0x180016f1a  lea     rax, [rbp+57h+var_88]
0x180016f1e  mov     [rsp+0F0h+var_C0], r14
0x180016f23  mov     [rsp+0F0h+var_C8], edi
0x180016f27  lea     edx, [r9-7]
0x180016f2b  mov     [rsp+0F0h+var_D0], rax
0x180016f30  mov     [rbp+57h+var_88], rbx
0x180016f34  call    cs:__imp_NsiSetAllParameters
0x180016f3a  test    eax, eax
0x180016f3c  jz      short loc_180016F5B
0x180016f3e  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r15b
0x180016f45  jz      short loc_180016F5B
0x180016f47  mov     r9d, eax
0x180016f4a  mov     [rsp+0F0h+var_D0], rbx
0x180016f4f  lea     r8, aCouldNotDelete_0; "Could not delete synthetic IPv4 address"...
0x180016f56  call    McTemplateU0sqx_EventWriteTransfer
0x180016f5b  mov     rcx, [rbp+57h+var_30]
0x180016f5f  xor     rcx, rsp; StackCookie
0x180016f62  call    __security_check_cookie
0x180016f67  mov     rbx, [rsp+0F0h+arg_18]
0x180016f6f  add     rsp, 0D0h
0x180016f76  pop     r15
0x180016f78  pop     r14
0x180016f7a  pop     rdi
0x180016f7b  pop     rsi
0x180016f7c  pop     rbp
0x180016f7d  retn
```
