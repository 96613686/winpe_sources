# IPxlatInterface::SetSyntheticIPv4MTU(void)

- ea: `0x1800163d0`
- end: `0x180016675`
- name: `?SetSyntheticIPv4MTU@IPxlatInterface@@AEAAXXZ`
- size: `677`
- prototype: `void __fastcall(IPxlatInterface *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015a1c`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x180012388`
- `0x1800145fc`
- `0x180016340`
- `0x1800163d0`

## string_xrefs

- `0x180016423`: `Failed to get IPv6 Link MTU for physical interface.`
- `0x180016464`: `Failed to get IPv4 Link MTU for physical interface.`
- `0x18001647f`: `MTU for IPv4 Link interface is:`
- `0x1800164e0`: `No MTU configured for IPv6 Link interface.`
- `0x180016535`: `MTU for IPv6 Link interface is:`
- `0x18001657e`: `IPv6 Link MTU is smaller than IPv6 header!`

## pseudocode

```c
void __fastcall IPxlatInterface::SetSyntheticIPv4MTU(IPxlatInterface *this)
{
  unsigned int InterfaceMTU; // eax
  int v3; // edx
  unsigned int v4; // eax
  int v5; // edx
  __int64 v6; // r8
  unsigned int v7; // esi
  __int64 v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v12; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-48h] BYREF
  const char *v15; // [rsp+50h] [rbp-38h]
  __int64 v16; // [rsp+58h] [rbp-30h]
  unsigned int *v17; // [rsp+60h] [rbp-28h]
  __int64 v18; // [rsp+68h] [rbp-20h]

  v12 = 0;
  v13 = 0;
  InterfaceMTU = IPxlatInterface::GetInterfaceMTU(this, 0x17u, &v12);
  if ( InterfaceMTU && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(
      *(_QWORD *)this,
      v3,
      (unsigned int)"Failed to get IPv6 Link MTU for physical interface.",
      InterfaceMTU,
      *(_QWORD *)this);
  v4 = IPxlatInterface::GetInterfaceMTU(this, 2u, &v13);
  v7 = v13;
  v8 = (unsigned int)Microsoft_Windows_IPxlatCfgEnableBits;
  if ( v4 )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) == 0 )
      goto LABEL_10;
    McTemplateU0sqx_EventWriteTransfer(
      *(_QWORD *)this,
      v5,
      (unsigned int)"Failed to get IPv4 Link MTU for physical interface.",
      v4,
      *(_QWORD *)this);
  }
  else
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) == 0 )
      goto LABEL_10;
    v15 = "MTU for IPv4 Link interface is:";
    v16 = 32;
    v17 = &v13;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(
      (unsigned int)Microsoft_Windows_IPxlatCfgEnableBits,
      IPXLATCFG_MTU_INFO_EVENT,
      v6,
      3,
      v14);
  }
  v8 = (unsigned int)Microsoft_Windows_IPxlatCfgEnableBits;
LABEL_10:
  if ( !v12 )
  {
    v9 = 1260;
    if ( (v8 & 2) == 0 )
    {
LABEL_21:
      v10 = IPxlatInterface::SetInterfaceMTU(this, v5, v9);
      if ( v10 )
      {
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
          McTemplateU0sqx_EventWriteTransfer(
            *(_QWORD *)this,
            v11,
            (unsigned int)"Failed to set MTU on IPv4 synthetic interface.",
            v10,
            *(_QWORD *)this);
      }
      else
      {
        *((_DWORD *)this + 47) = v7;
      }
      return;
    }
    v16 = 43;
    v15 = "No MTU configured for IPv6 Link interface.";
    McGenEventWrite_EventWriteTransfer(v8, IPXLATCFG_INFO_EVENT, v6, 2, v14);
    v8 = (unsigned int)Microsoft_Windows_IPxlatCfgEnableBits;
LABEL_19:
    if ( (v8 & 2) != 0 )
    {
      v12 = v9;
      v15 = "MTU for IPv4 synthetic interface is:";
      v16 = 37;
      v17 = &v12;
      v18 = 4;
      McGenEventWrite_EventWriteTransfer(v8, IPXLATCFG_MTU_INFO_EVENT, v6, 3, v14);
    }
    goto LABEL_21;
  }
  if ( v12 > 0x28 )
  {
    v9 = v12 - 20;
    goto LABEL_19;
  }
  if ( (v8 & 2) != 0 )
  {
    v16 = 32;
    v15 = "MTU for IPv6 Link interface is:";
    v18 = 4;
    v17 = &v12;
    McGenEventWrite_EventWriteTransfer(v8, IPXLATCFG_MTU_INFO_EVENT, v6, 3, v14);
    v8 = (unsigned int)Microsoft_Windows_IPxlatCfgEnableBits;
  }
  if ( (v8 & 1) != 0 )
  {
    v12 = 10;
    v15 = "IPv6 Link MTU is smaller than IPv6 header!";
    v16 = 43;
    v17 = &v12;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(v8, IPXLATCFG_ERROR_EVENT, v6, 3, v14);
  }
}

```

## disassembly

```asm
0x1800163d0  mov     [rsp+arg_8], rbx
0x1800163d5  mov     [rsp+arg_10], rsi
0x1800163da  push    rdi
0x1800163db  sub     rsp, 80h
0x1800163e2  mov     rax, cs:__security_cookie
0x1800163e9  xor     rax, rsp
0x1800163ec  mov     [rsp+88h+var_18], rax
0x1800163f1  mov     edx, 17h; unsigned __int16
0x1800163f6  mov     [rsp+88h+var_58], 0
0x1800163fe  lea     r8, [rsp+88h+var_58]; unsigned int *
0x180016403  mov     [rsp+88h+var_50], 0
0x18001640b  mov     rbx, rcx
0x18001640e  call    ?GetInterfaceMTU@IPxlatInterface@@AEBAKGPEAK@Z; IPxlatInterface::GetInterfaceMTU(ushort,ulong *)
0x180016413  test    eax, eax
0x180016415  jz      short loc_180016437
0x180016417  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18001641e  jz      short loc_180016437
0x180016420  mov     rcx, [rbx]
0x180016423  lea     r8, aFailedToGetIpv; "Failed to get IPv6 Link MTU for physica"...
0x18001642a  mov     r9d, eax
0x18001642d  mov     [rsp+88h+var_68], rcx
0x180016432  call    McTemplateU0sqx_EventWriteTransfer
0x180016437  mov     edx, 2; unsigned __int16
0x18001643c  lea     r8, [rsp+88h+var_50]; unsigned int *
0x180016441  mov     rcx, rbx; this
0x180016444  call    ?GetInterfaceMTU@IPxlatInterface@@AEBAKGPEAK@Z; IPxlatInterface::GetInterfaceMTU(ushort,ulong *)
0x180016449  mov     esi, [rsp+88h+var_50]
0x18001644d  mov     edi, 3
0x180016452  mov     ecx, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x180016458  test    eax, eax
0x18001645a  jz      short loc_18001647A
0x18001645c  test    cl, 1
0x18001645f  jz      short loc_1800164CA
0x180016461  mov     rcx, [rbx]
0x180016464  lea     r8, aFailedToGetIpv_0; "Failed to get IPv4 Link MTU for physica"...
0x18001646b  mov     r9d, eax
0x18001646e  mov     [rsp+88h+var_68], rcx
0x180016473  call    McTemplateU0sqx_EventWriteTransfer
0x180016478  jmp     short loc_1800164C4
0x18001647a  test    cl, 2
0x18001647d  jz      short loc_1800164CA
0x18001647f  lea     rax, aMtuForIpv4Link; "MTU for IPv4 Link interface is:"
0x180016486  mov     [rsp+88h+var_50], esi
0x18001648a  mov     [rsp+88h+var_38], rax
0x18001648f  lea     rdx, IPXLATCFG_MTU_INFO_EVENT
0x180016496  lea     rax, [rsp+88h+var_50]
0x18001649b  mov     [rsp+88h+var_30], 20h ; ' '
0x1800164a4  mov     [rsp+88h+var_28], rax
0x1800164a9  mov     r9d, edi
0x1800164ac  lea     rax, [rsp+88h+var_48]
0x1800164b1  mov     [rsp+88h+var_20], 4
0x1800164ba  mov     [rsp+88h+var_68], rax
0x1800164bf  call    McGenEventWrite_EventWriteTransfer
0x1800164c4  mov     ecx, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x1800164ca  mov     eax, [rsp+88h+var_58]
0x1800164ce  test    eax, eax
0x1800164d0  jnz     short loc_18001651C
0x1800164d2  mov     edi, 4ECh
0x1800164d7  test    cl, 2
0x1800164da  jz      loc_18001661C
0x1800164e0  lea     rax, aNoMtuConfigure; "No MTU configured for IPv6 Link interfa"...
0x1800164e7  mov     [rsp+88h+var_30], 2Bh ; '+'
0x1800164f0  mov     [rsp+88h+var_38], rax
0x1800164f5  lea     rdx, IPXLATCFG_INFO_EVENT
0x1800164fc  lea     rax, [rsp+88h+var_48]
0x180016501  mov     r9d, 2
0x180016507  mov     [rsp+88h+var_68], rax
0x18001650c  call    McGenEventWrite_EventWriteTransfer
0x180016511  mov     ecx, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x180016517  jmp     loc_1800165CF
0x18001651c  cmp     eax, 28h ; '('
0x18001651f  ja      loc_1800165CC
0x180016525  test    cl, 2
0x180016528  jz      short loc_180016575
0x18001652a  mov     [rsp+88h+var_58], eax
0x18001652e  lea     rdx, IPXLATCFG_MTU_INFO_EVENT
0x180016535  lea     rax, aMtuForIpv6Link; "MTU for IPv6 Link interface is:"
0x18001653c  mov     [rsp+88h+var_30], 20h ; ' '
0x180016545  mov     [rsp+88h+var_38], rax
0x18001654a  mov     r9d, edi
0x18001654d  lea     rax, [rsp+88h+var_58]
0x180016552  mov     [rsp+88h+var_20], 4
0x18001655b  mov     [rsp+88h+var_28], rax
0x180016560  lea     rax, [rsp+88h+var_48]
0x180016565  mov     [rsp+88h+var_68], rax
0x18001656a  call    McGenEventWrite_EventWriteTransfer
0x18001656f  mov     ecx, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x180016575  test    cl, 1
0x180016578  jz      loc_180016653
0x18001657e  lea     rax, aIpv6LinkMtuIsS; "IPv6 Link MTU is smaller than IPv6 head"...
0x180016585  mov     [rsp+88h+var_58], 0Ah
0x18001658d  mov     [rsp+88h+var_38], rax
0x180016592  lea     rdx, IPXLATCFG_ERROR_EVENT
0x180016599  lea     rax, [rsp+88h+var_58]
0x18001659e  mov     [rsp+88h+var_30], 2Bh ; '+'
0x1800165a7  mov     [rsp+88h+var_28], rax
0x1800165ac  mov     r9d, edi
0x1800165af  lea     rax, [rsp+88h+var_48]
0x1800165b4  mov     [rsp+88h+var_20], 4
0x1800165bd  mov     [rsp+88h+var_68], rax
0x1800165c2  call    McGenEventWrite_EventWriteTransfer
0x1800165c7  jmp     loc_180016653
0x1800165cc  lea     edi, [rax-14h]
0x1800165cf  test    cl, 2
0x1800165d2  jz      short loc_18001661C
0x1800165d4  lea     rax, aMtuForIpv4Synt; "MTU for IPv4 synthetic interface is:"
0x1800165db  mov     [rsp+88h+var_58], edi
0x1800165df  mov     [rsp+88h+var_38], rax
0x1800165e4  lea     rdx, IPXLATCFG_MTU_INFO_EVENT
0x1800165eb  lea     rax, [rsp+88h+var_58]
0x1800165f0  mov     [rsp+88h+var_30], 25h ; '%'
0x1800165f9  mov     [rsp+88h+var_28], rax
0x1800165fe  mov     r9d, 3
0x180016604  lea     rax, [rsp+88h+var_48]
0x180016609  mov     [rsp+88h+var_20], 4
0x180016612  mov     [rsp+88h+var_68], rax
0x180016617  call    McGenEventWrite_EventWriteTransfer
0x18001661c  mov     r8d, edi; unsigned int
0x18001661f  mov     rcx, rbx; this
0x180016622  call    ?SetInterfaceMTU@IPxlatInterface@@AEAAKGK@Z; IPxlatInterface::SetInterfaceMTU(ushort,ulong)
0x180016627  test    eax, eax
0x180016629  jz      short loc_18001664D
0x18001662b  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180016632  jz      short loc_180016653
0x180016634  mov     rcx, [rbx]
0x180016637  lea     r8, aFailedToSetMtu; "Failed to set MTU on IPv4 synthetic int"...
0x18001663e  mov     r9d, eax
0x180016641  mov     [rsp+88h+var_68], rcx
0x180016646  call    McTemplateU0sqx_EventWriteTransfer
0x18001664b  jmp     short loc_180016653
0x18001664d  mov     [rbx+0BCh], esi
0x180016653  mov     rcx, [rsp+88h+var_18]
0x180016658  xor     rcx, rsp; StackCookie
0x18001665b  call    __security_check_cookie
0x180016660  lea     r11, [rsp+88h+var_8]
0x180016668  mov     rbx, [r11+18h]
0x18001666c  mov     rsi, [r11+20h]
0x180016670  mov     rsp, r11
0x180016673  pop     rdi
0x180016674  retn
```
