# IPxlatInterface::UnPlumbSyntheticIpAndRoute(void)

- ea: `0x180016f84`
- end: `0x1800171ca`
- name: `?UnPlumbSyntheticIpAndRoute@IPxlatInterface@@AEAAXXZ`
- size: `582`
- prototype: `void __fastcall(IPxlatInterface *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800172a4`

## callees

- `0x180001d40`
- `0x180012388`
- `0x180016340`
- `0x180016f84`

## import_xrefs

- `NSI!NsiSetAllParameters` at `0x180016fe8`
- `NSI!NsiSetAllParameters` at `0x18001705a`
- `NSI!NsiSetAllParameters` at `0x1800170e3`
- `NSI!NsiSetAllParameters` at `0x180017150`
- `NSI!NsiSetAllParameters` at `0x180016fe8`
- `NSI!NsiSetAllParameters` at `0x18001705a`
- `NSI!NsiSetAllParameters` at `0x1800170e3`
- `NSI!NsiSetAllParameters` at `0x180017150`

## string_xrefs

- `0x18001719e`: `Failed to reset MTU on IPv4 Link interface.`
- `0x180016ffe`: `Could not delete synthetic IPv6 address from the interface`
- `0x180017070`: `Could not delete ARP entry for default gateway`
- `0x1800170f9`: `Could not delete route for synthetic IPv4 address`
- `0x180017166`: `Could not delete synthetic IPv4 address from the interface`

## pseudocode

```c
void __fastcall IPxlatInterface::UnPlumbSyntheticIpAndRoute(IPxlatInterface *this)
{
  int v2; // eax
  int v3; // edx
  int v4; // eax
  int v5; // edx
  int v6; // eax
  int v7; // edx
  int v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  unsigned int v11; // eax
  int v12; // edx

  v2 = NsiSetAllParameters(1, 3, &NPI_MS_IPV6_MODULEID);
  if ( v2 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(
      *(_QWORD *)this,
      v3,
      (unsigned int)"Could not delete synthetic IPv6 address from the interface",
      v2,
      *(_QWORD *)this);
  v4 = NsiSetAllParameters(1, 3, &NPI_MS_IPV4_MODULEID);
  if ( v4 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(
      *(_QWORD *)this,
      v5,
      (unsigned int)"Could not delete ARP entry for default gateway",
      v4,
      *(_QWORD *)this);
  v6 = NsiSetAllParameters(1, 3, &NPI_MS_IPV4_MODULEID);
  if ( v6 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(
      *(_QWORD *)this,
      v7,
      (unsigned int)"Could not delete route for synthetic IPv4 address",
      v6,
      *(_QWORD *)this);
  v8 = NsiSetAllParameters(1, 3, &NPI_MS_IPV4_MODULEID);
  if ( v8 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    McTemplateU0sqx_EventWriteTransfer(
      *(_QWORD *)this,
      v9,
      (unsigned int)"Could not delete synthetic IPv4 address from the interface",
      v8,
      *(_QWORD *)this);
  v10 = *((_DWORD *)this + 47);
  if ( v10 )
  {
    v11 = IPxlatInterface::SetInterfaceMTU(this, v9, v10);
    if ( v11 )
    {
      if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        McTemplateU0sqx_EventWriteTransfer(
          *(_QWORD *)this,
          v12,
          (unsigned int)"Failed to reset MTU on IPv4 Link interface.",
          v11,
          *(_QWORD *)this);
    }
  }
}

```

## disassembly

```asm
0x180016f84  push    rbp
0x180016f86  push    rbx
0x180016f87  push    rsi
0x180016f88  push    rdi
0x180016f89  lea     rbp, [rsp-3Fh]
0x180016f8e  sub     rsp, 0C8h
0x180016f95  mov     rax, cs:__security_cookie
0x180016f9c  xor     rax, rsp
0x180016f9f  mov     [rbp+57h+var_30], rax
0x180016fa3  mov     rax, [rcx]
0x180016fa6  lea     r8, NPI_MS_IPV6_MODULEID
0x180016fad  movups  xmm0, xmmword ptr [rcx+88h]
0x180016fb4  xor     esi, esi
0x180016fb6  mov     [rbp+57h+var_48], rax
0x180016fba  mov     [rsp+0E0h+var_A8], esi
0x180016fbe  lea     rax, [rbp+57h+var_48]
0x180016fc2  mov     rbx, rcx
0x180016fc5  mov     [rsp+0E0h+var_B0], rsi
0x180016fca  mov     [rsp+0E0h+var_B8], 18h
0x180016fd2  lea     edi, [rsi+1]
0x180016fd5  mov     [rsp+0E0h+var_C0], rax
0x180016fda  mov     ecx, edi
0x180016fdc  lea     r9d, [rsi+0Ah]
0x180016fe0  lea     edx, [rsi+3]
0x180016fe3  movdqu  [rbp+57h+var_40], xmm0
0x180016fe8  call    cs:__imp_NsiSetAllParameters
0x180016fee  test    eax, eax
0x180016ff0  jz      short loc_180017012
0x180016ff2  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x180016ff9  jz      short loc_180017012
0x180016ffb  mov     rcx, [rbx]
0x180016ffe  lea     r8, aCouldNotDelete_2; "Could not delete synthetic IPv6 address"...
0x180017005  mov     r9d, eax
0x180017008  mov     [rsp+0E0h+var_C0], rcx
0x18001700d  call    McTemplateU0sqx_EventWriteTransfer
0x180017012  mov     eax, [rbx+80h]
0x180017018  lea     r8, NPI_MS_IPV4_MODULEID
0x18001701f  mov     [rsp+0E0h+var_A8], esi
0x180017023  xorps   xmm0, xmm0
0x180017026  movups  [rbp+57h+var_58], xmm0
0x18001702a  mov     dword ptr [rbp+57h+var_58+8], eax
0x18001702d  mov     r9d, 0Bh
0x180017033  mov     rax, [rbx]
0x180017036  mov     ecx, edi
0x180017038  mov     [rbp+57h+var_60], rax
0x18001703c  mov     qword ptr [rbp+57h+var_58], rax
0x180017040  lea     rax, [rbp+57h+var_60]
0x180017044  mov     [rsp+0E0h+var_B0], rsi
0x180017049  lea     edx, [r9-8]
0x18001704d  mov     [rsp+0E0h+var_B8], 18h
0x180017055  mov     [rsp+0E0h+var_C0], rax
0x18001705a  call    cs:__imp_NsiSetAllParameters
0x180017060  test    eax, eax
0x180017062  jz      short loc_180017084
0x180017064  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x18001706b  jz      short loc_180017084
0x18001706d  mov     rcx, [rbx]
0x180017070  lea     r8, aCouldNotDelete_1; "Could not delete ARP entry for default "...
0x180017077  mov     r9d, eax
0x18001707a  mov     [rsp+0E0h+var_C0], rcx
0x18001707f  call    McTemplateU0sqx_EventWriteTransfer
0x180017084  mov     rax, [rbx]
0x180017087  lea     r8, NPI_MS_IPV4_MODULEID
0x18001708e  xorps   xmm0, xmm0
0x180017091  mov     [rsp+0E0h+var_A8], esi
0x180017095  movups  [rbp+57h+var_90], xmm0
0x180017099  mov     r9d, 10h
0x18001709f  mov     [rsp+0E0h+var_B0], rsi
0x1800170a4  movups  [rbp+57h+var_80], xmm0
0x1800170a8  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800170ac  mov     ecx, edi
0x1800170ae  movups  [rbp+57h+var_70], xmm0
0x1800170b2  mov     qword ptr [rbp+57h+var_70], rax
0x1800170b6  lea     edx, [r9-0Dh]
0x1800170ba  mov     eax, [rbx+80h]
0x1800170c0  mov     dword ptr [rbp+57h+var_70+8], eax
0x1800170c3  lea     rax, [rbp+57h+var_90]
0x1800170c7  mov     [rsp+0E0h+var_B8], 30h ; '0'
0x1800170cf  mov     [rsp+0E0h+var_C0], rax
0x1800170d4  mov     qword ptr [rbp+57h+var_90], rdi
0x1800170d8  mov     dword ptr [rbp+57h+var_90+0Ch], esi
0x1800170db  mov     byte ptr [rbp+57h+var_80], sil
0x1800170df  mov     byte ptr [rbp+57h+var_90+8], sil
0x1800170e3  call    cs:__imp_NsiSetAllParameters
0x1800170e9  test    eax, eax
0x1800170eb  jz      short loc_18001710D
0x1800170ed  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x1800170f4  jz      short loc_18001710D
0x1800170f6  mov     rcx, [rbx]
0x1800170f9  lea     r8, aCouldNotDelete; "Could not delete route for synthetic IP"...
0x180017100  mov     r9d, eax
0x180017103  mov     [rsp+0E0h+var_C0], rcx
0x180017108  call    McTemplateU0sqx_EventWriteTransfer
0x18001710d  xor     eax, eax
0x18001710f  mov     [rsp+0E0h+var_A8], esi
0x180017113  mov     [rbp+57h+var_98], rax
0x180017117  lea     r8, NPI_MS_IPV4_MODULEID
0x18001711e  mov     rax, [rbx]
0x180017121  mov     r9d, 0Ah
0x180017127  mov     [rbp+57h+var_A0], rax
0x18001712b  mov     ecx, edi
0x18001712d  mov     eax, [rbx+84h]
0x180017133  mov     dword ptr [rbp+57h+var_98], eax
0x180017136  lea     rax, [rbp+57h+var_A0]
0x18001713a  mov     [rsp+0E0h+var_B0], rsi
0x18001713f  lea     edx, [r9-7]
0x180017143  mov     [rsp+0E0h+var_B8], 10h
0x18001714b  mov     [rsp+0E0h+var_C0], rax
0x180017150  call    cs:__imp_NsiSetAllParameters
0x180017156  test    eax, eax
0x180017158  jz      short loc_18001717A
0x18001715a  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x180017161  jz      short loc_18001717A
0x180017163  mov     rcx, [rbx]
0x180017166  lea     r8, aCouldNotDelete_0; "Could not delete synthetic IPv4 address"...
0x18001716d  mov     r9d, eax
0x180017170  mov     [rsp+0E0h+var_C0], rcx
0x180017175  call    McTemplateU0sqx_EventWriteTransfer
0x18001717a  mov     r8d, [rbx+0BCh]; unsigned int
0x180017181  test    r8d, r8d
0x180017184  jz      short loc_1800171B2
0x180017186  mov     rcx, rbx; this
0x180017189  call    ?SetInterfaceMTU@IPxlatInterface@@AEAAKGK@Z; IPxlatInterface::SetInterfaceMTU(ushort,ulong)
0x18001718e  test    eax, eax
0x180017190  jz      short loc_1800171B2
0x180017192  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, dil
0x180017199  jz      short loc_1800171B2
0x18001719b  mov     rcx, [rbx]
0x18001719e  lea     r8, aFailedToResetM; "Failed to reset MTU on IPv4 Link interf"...
0x1800171a5  mov     r9d, eax
0x1800171a8  mov     [rsp+0E0h+var_C0], rcx
0x1800171ad  call    McTemplateU0sqx_EventWriteTransfer
0x1800171b2  mov     rcx, [rbp+57h+var_30]
0x1800171b6  xor     rcx, rsp; StackCookie
0x1800171b9  call    __security_check_cookie
0x1800171be  add     rsp, 0C8h
0x1800171c5  pop     rdi
0x1800171c6  pop     rsi
0x1800171c7  pop     rbx
0x1800171c8  pop     rbp
0x1800171c9  retn
```
