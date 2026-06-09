# KdcVerifyClientCertDnsName(_CERT_CONTEXT const *,_KDC_TICKET_INFO *)

- ea: `0x180054e6c`
- end: `0x180055084`
- name: `?KdcVerifyClientCertDnsName@@YAJPEBU_CERT_CONTEXT@@PEAU_KDC_TICKET_INFO@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, struct _KDC_TICKET_INFO *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fdb0`
- `0x180050e78`

## callees

- `0x18000a82c`
- `0x18000a860`
- `0x1800101ec`
- `0x18001ff94`
- `0x18004d8bc`
- `0x180054e6c`
- `0x180075f84`
- `0x180076eac`
- `0x18007dc20`

## import_xrefs

- `ntdll!RtlEqualDomainName` at `0x180054fb4`
- `ntdll!RtlEqualDomainName` at `0x180054fb4`
- `ntdll!RtlEqualComputerName` at `0x180054fc6`
- `ntdll!RtlEqualComputerName` at `0x180054fc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcVerifyClientCertDnsName(const struct _CERT_CONTEXT *a1, struct _KDC_TICKET_INFO *a2)
{
  __int64 v3; // rax
  const struct _CERT_CONTEXT *v4; // r10
  unsigned int DnsNameArrayFromCertificate; // eax
  CSecurityData *v6; // rcx
  __int64 v7; // rdx
  unsigned __int16 v8; // ax
  USHORT v9; // cx
  bool v10; // zf
  unsigned int i; // edi
  __int64 v12; // r14
  unsigned int v13; // ebx
  struct _UNICODE_STRING ComputerName2; // [rsp+20h] [rbp-29h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING ComputerName1; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v18[24]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v19[40]; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned int v20; // [rsp+B8h] [rbp+6Fh] BYREF
  struct _UNICODE_STRING *v21; // [rsp+C0h] [rbp+77h] BYREF

  ComputerName1 = 0;
  DomainName1 = 0;
  v21 = 0;
  v20 = 0;
  v3 = ((__int64 (__fastcall *)(_BYTE *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING **, _QWORD, _QWORD))lambda_21c4ea7e66c71d2f543b9ee2e639597c_::_lambda_21c4ea7e66c71d2f543b9ee2e639597c_)(
         v18,
         &DomainName1,
         &ComputerName1,
         &v21,
         0,
         0);
  wil::scope_exit__lambda_21c4ea7e66c71d2f543b9ee2e639597c___(v19, v3);
  if ( (*((_BYTE *)a2 + 112) & 0x20) != 0
    || (*((_DWORD *)a2 + 11) & 0x180) == 0
    || (DnsNameArrayFromCertificate = KerbGetDnsNameArrayFromCertificate(v4, &v21, &v20),
        DnsNameArrayFromCertificate == -1073741275) )
  {
LABEL_23:
    v13 = 0;
    goto LABEL_24;
  }
  if ( !DnsNameArrayFromCertificate )
  {
    v8 = *(_WORD *)a2 >> 1;
    if ( v8 )
    {
      v9 = 2 * v8;
      v10 = *(_WORD *)(*((_QWORD *)a2 + 1) + 2LL * v8 - 2) == 36;
      ComputerName2.Buffer = (PWSTR)*((_QWORD *)a2 + 1);
      if ( v10 )
        v9 -= 2;
      ComputerName2.MaximumLength = v9;
      ComputerName2.Length = v9;
      for ( i = 0; i < v20; ++i )
      {
        KerbFreeString(&ComputerName1);
        KerbFreeString(&DomainName1);
        v12 = i;
        DnsNameArrayFromCertificate = KerbParseMachineDnsName(&v21[v12], &ComputerName1, &DomainName1);
        if ( DnsNameArrayFromCertificate == -1073741811 )
          goto LABEL_23;
        if ( DnsNameArrayFromCertificate )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 32;
            goto LABEL_28;
          }
          goto LABEL_29;
        }
        if ( RtlEqualDomainName(&DomainName1, &DomainName2) && RtlEqualComputerName(&ComputerName1, &ComputerName2) )
        {
          *((_DWORD *)a2 + 28) |= 0x1008u;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
              &v21[v12]);
          }
          break;
        }
      }
      if ( v20 )
      {
        v10 = (*((_BYTE *)a2 + 112) & 8) == 0;
        v13 = 75;
        if ( v10 )
          goto LABEL_24;
      }
    }
    goto LABEL_23;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 31;
LABEL_28:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, DnsNameArrayFromCertificate);
  }
LABEL_29:
  v13 = 60;
LABEL_24:
  wil::details::lambda_call__lambda_192914a142c1025aaa7682176721bbce___::_lambda_call__lambda_192914a142c1025aaa7682176721bbce___(v19);
  return v13;
}

```

## disassembly

```asm
0x180054e6c  mov     [rsp-8+arg_0], rbx
0x180054e71  mov     [rsp-8+arg_18], rdi
0x180054e76  push    rbp
0x180054e77  push    r14
0x180054e79  push    r15
0x180054e7b  lea     rbp, [rsp-47h]
0x180054e80  sub     rsp, 90h
0x180054e87  mov     rbx, rdx
0x180054e8a  mov     r10, rcx
0x180054e8d  xorps   xmm0, xmm0
0x180054e90  movups  xmmword ptr [rbp+57h+ComputerName1.Length], xmm0
0x180054e94  xorps   xmm1, xmm1
0x180054e97  movups  xmmword ptr [rbp+57h+DomainName1.Length], xmm1
0x180054e9b  movups  xmmword ptr [rbp+57h+ComputerName2.Length], xmm0
0x180054e9f  xor     r15d, r15d
0x180054ea2  mov     [rbp+57h+arg_10], r15
0x180054ea6  mov     [rbp+57h+arg_8], r15d
0x180054eaa  lea     r9, [rbp+57h+arg_10]
0x180054eae  lea     r8, [rbp+57h+ComputerName1]
0x180054eb2  lea     rdx, [rbp+57h+DomainName1]
0x180054eb6  lea     rcx, [rbp+57h+var_50]
0x180054eba  call    _lambda_21c4ea7e66c71d2f543b9ee2e639597c____lambda_21c4ea7e66c71d2f543b9ee2e639597c_
0x180054ebf  mov     rdx, rax
0x180054ec2  lea     rcx, [rbp+57h+var_38]
0x180054ec6  call    wil__scope_exit__lambda_21c4ea7e66c71d2f543b9ee2e639597c___
0x180054ecb  nop
0x180054ecc  test    byte ptr [rbx+70h], 20h
0x180054ed0  jnz     loc_180055024
0x180054ed6  test    dword ptr [rbx+2Ch], 180h
0x180054edd  jz      loc_180055024
0x180054ee3  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x180054ee7  lea     rdx, [rbp+57h+arg_10]; struct _UNICODE_STRING **
0x180054eeb  mov     rcx, r10; struct _CERT_CONTEXT *
0x180054eee  call    ?KerbGetDnsNameArrayFromCertificate@@YAJPEBU_CERT_CONTEXT@@PEAPEAU_UNICODE_STRING@@PEAK@Z; KerbGetDnsNameArrayFromCertificate(_CERT_CONTEXT const *,_UNICODE_STRING * *,ulong *)
0x180054ef3  cmp     eax, 0C0000225h
0x180054ef8  jz      loc_180055024
0x180054efe  test    eax, eax
0x180054f00  jz      short loc_180054F2C
0x180054f02  lea     rdx, WPP_GLOBAL_Control
0x180054f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f10  cmp     rcx, rdx
0x180054f13  jz      loc_18005507C
0x180054f19  test    byte ptr [rcx+1Ch], 1
0x180054f1d  jz      loc_18005507C
0x180054f23  lea     edx, [r15+1Fh]
0x180054f27  jmp     loc_180055069
0x180054f2c  movzx   eax, word ptr [rbx]
0x180054f2f  shr     ax, 1
0x180054f32  jz      loc_180055024
0x180054f38  mov     rdx, [rbx+8]
0x180054f3c  movzx   ecx, ax
0x180054f3f  add     cx, cx
0x180054f42  movzx   eax, ax
0x180054f45  cmp     word ptr [rdx+rax*2-2], 24h ; '$'
0x180054f4b  mov     [rbp+57h+ComputerName2.Buffer], rdx
0x180054f4f  jnz     short loc_180054F55
0x180054f51  sub     cx, 2
0x180054f55  mov     [rbp+57h+ComputerName2.MaximumLength], cx
0x180054f59  mov     [rbp+57h+ComputerName2.Length], cx
0x180054f5d  mov     edi, r15d
0x180054f60  cmp     edi, [rbp+57h+arg_8]
0x180054f63  jnb     loc_180055013
0x180054f69  lea     rcx, [rbp+57h+ComputerName1]
0x180054f6d  call    KerbFreeString
0x180054f72  lea     rcx, [rbp+57h+DomainName1]
0x180054f76  call    KerbFreeString
0x180054f7b  mov     r14d, edi
0x180054f7e  shl     r14, 4
0x180054f82  mov     rcx, [rbp+57h+arg_10]
0x180054f86  add     rcx, r14; struct _UNICODE_STRING *
0x180054f89  lea     r8, [rbp+57h+DomainName1]; struct _UNICODE_STRING *
0x180054f8d  lea     rdx, [rbp+57h+ComputerName1]; struct _UNICODE_STRING *
0x180054f91  call    ?KerbParseMachineDnsName@@YAJPEAU_UNICODE_STRING@@00@Z; KerbParseMachineDnsName(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180054f96  cmp     eax, 0C000000Dh
0x180054f9b  jz      loc_180055024
0x180054fa1  test    eax, eax
0x180054fa3  jnz     loc_18005504B
0x180054fa9  lea     rdx, DomainName2; DomainName2
0x180054fb0  lea     rcx, [rbp+57h+DomainName1]; DomainName1
0x180054fb4  call    cs:__imp_RtlEqualDomainName
0x180054fba  test    al, al
0x180054fbc  jz      short loc_180054FD0
0x180054fbe  lea     rdx, [rbp+57h+ComputerName2]; ComputerName2
0x180054fc2  lea     rcx, [rbp+57h+ComputerName1]; ComputerName1
0x180054fc6  call    cs:__imp_RtlEqualComputerName
0x180054fcc  test    al, al
0x180054fce  jnz     short loc_180054FD4
0x180054fd0  inc     edi
0x180054fd2  jmp     short loc_180054F60
0x180054fd4  or      dword ptr [rbx+70h], 1008h
0x180054fdb  lea     rdx, WPP_GLOBAL_Control
0x180054fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fe9  cmp     rcx, rdx
0x180054fec  jz      short loc_180055013
0x180054fee  test    dword ptr [rcx+1Ch], 1000h
0x180054ff5  jz      short loc_180055013
0x180054ff7  mov     r9, [rbp+57h+arg_10]
0x180054ffb  add     r9, r14
0x180054ffe  mov     edx, 21h ; '!'
0x180055003  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18005500a  mov     rcx, [rcx+10h]
0x18005500e  call    WPP_SF_Z
0x180055013  cmp     [rbp+57h+arg_8], r15d
0x180055017  jz      short loc_180055024
0x180055019  test    byte ptr [rbx+70h], 8
0x18005501d  mov     ebx, 4Bh ; 'K'
0x180055022  jz      short loc_180055027
0x180055024  mov     ebx, r15d
0x180055027  lea     rcx, [rbp+57h+var_38]
0x18005502b  call    wil__details__lambda_call__lambda_192914a142c1025aaa7682176721bbce______lambda_call__lambda_192914a142c1025aaa7682176721bbce___
0x180055030  mov     eax, ebx
0x180055032  lea     r11, [rsp+0A0h+var_10]
0x18005503a  mov     rbx, [r11+20h]
0x18005503e  mov     rdi, [r11+38h]
0x180055042  mov     rsp, r11
0x180055045  pop     r15
0x180055047  pop     r14
0x180055049  pop     rbp
0x18005504a  retn
0x18005504b  lea     rdx, WPP_GLOBAL_Control
0x180055052  mov     rcx, cs:WPP_GLOBAL_Control
0x180055059  cmp     rcx, rdx
0x18005505c  jz      short loc_18005507C
0x18005505e  test    byte ptr [rcx+1Ch], 1
0x180055062  jz      short loc_18005507C
0x180055064  mov     edx, 20h ; ' '
0x180055069  mov     r9d, eax
0x18005506c  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055073  mov     rcx, [rcx+10h]
0x180055077  call    WPP_SF_d
0x18005507c  mov     ebx, 3Ch ; '<'
0x180055081  jmp     short loc_180055027
```
