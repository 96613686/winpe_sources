# KdcHandleNoLogonServers(void *,sockaddr *)

- ea: `0x18001ca90`
- end: `0x18001cb68`
- name: `?KdcHandleNoLogonServers@@YAJPEAXPEAUsockaddr@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(void *, struct sockaddr *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180016148`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18001ca90`

## import_xrefs

- `SAMSRV!SamIUpdateLogonStatistics` at `0x18001cb3f`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18001cb3f`

## pseudocode

```c
__int64 __fastcall KdcHandleNoLogonServers(void *a1, struct sockaddr_storage *a2)
{
  struct sockaddr v4; // xmm1
  struct sockaddr v5; // xmm0
  struct sockaddr v6; // xmm1
  struct sockaddr v7; // xmm0
  struct sockaddr v8; // xmm1
  struct sockaddr v9; // xmm0
  struct sockaddr v10; // xmm1
  int v12; // [rsp+20h] [rbp-79h] BYREF
  _BYTE v13[52]; // [rsp+24h] [rbp-75h] BYREF
  int v14; // [rsp+58h] [rbp-41h]
  __int128 v15; // [rsp+60h] [rbp-39h]
  struct sockaddr v16; // [rsp+70h] [rbp-29h]
  struct sockaddr v17; // [rsp+80h] [rbp-19h]
  struct sockaddr v18; // [rsp+90h] [rbp-9h]
  struct sockaddr v19; // [rsp+A0h] [rbp+7h]
  struct sockaddr v20; // [rsp+B0h] [rbp+17h]
  struct sockaddr v21; // [rsp+C0h] [rbp+27h]
  struct sockaddr v22; // [rsp+D0h] [rbp+37h]

  memset_0(v13, 0, 0xBCu);
  v12 = 75497472;
  if ( !a2 || a2->ss_family == 2 || a2->ss_family == 23 )
  {
    v14 = 1;
    if ( !a2 )
      a2 = &GlobalLocalhostAddress;
    v4 = *(struct sockaddr *)a2->__ss_pad2;
    v15 = *(_OWORD *)&a2->ss_family;
    v5 = *(struct sockaddr *)&a2->__ss_pad2[16];
    v16 = v4;
    v6 = *(struct sockaddr *)&a2->__ss_pad2[32];
    v17 = v5;
    v7 = *(struct sockaddr *)&a2->__ss_pad2[48];
    v18 = v6;
    v8 = *(struct sockaddr *)&a2->__ss_pad2[64];
    v19 = v7;
    v9 = *(struct sockaddr *)&a2->__ss_pad2[80];
    v20 = v8;
    v10 = *(struct sockaddr *)&a2->__ss_pad2[96];
    v21 = v9;
    v22 = v10;
  }
  SamIUpdateLogonStatistics(a1, &v12);
  return 0;
}

```

## disassembly

```asm
0x18001ca90  mov     [rsp-8+arg_10], rbx
0x18001ca95  mov     [rsp-8+arg_18], rdi
0x18001ca9a  push    rbp
0x18001ca9b  lea     rbp, [rsp-57h]
0x18001caa0  sub     rsp, 0F0h
0x18001caa7  mov     rax, cs:__security_cookie
0x18001caae  xor     rax, rsp
0x18001cab1  mov     [rbp+57h+var_10], rax
0x18001cab5  mov     rbx, rdx
0x18001cab8  mov     rdi, rcx
0x18001cabb  xor     edx, edx; Val
0x18001cabd  lea     rcx, [rbp+57h+var_CC]; void *
0x18001cac1  mov     r8d, 0BCh; Size
0x18001cac7  call    memset_0
0x18001cacc  mov     [rbp+57h+var_D0], 4800000h
0x18001cad3  test    rbx, rbx
0x18001cad6  jz      short loc_18001CAE4
0x18001cad8  cmp     word ptr [rbx], 2
0x18001cadc  jz      short loc_18001CAE4
0x18001cade  cmp     word ptr [rbx], 17h
0x18001cae2  jnz     short loc_18001CB38
0x18001cae4  test    rbx, rbx
0x18001cae7  mov     [rbp+57h+var_98], 1
0x18001caee  lea     rax, ?GlobalLocalhostAddress@@3Usockaddr_storage@@A; sockaddr_storage GlobalLocalhostAddress
0x18001caf5  cmovz   rbx, rax
0x18001caf9  movups  xmm0, xmmword ptr [rbx]
0x18001cafc  movups  xmm1, xmmword ptr [rbx+10h]
0x18001cb00  movaps  [rbp+57h+var_90], xmm0
0x18001cb04  movups  xmm0, xmmword ptr [rbx+20h]
0x18001cb08  movaps  [rbp+57h+var_80], xmm1
0x18001cb0c  movups  xmm1, xmmword ptr [rbx+30h]
0x18001cb10  movaps  [rbp+57h+var_70], xmm0
0x18001cb14  movups  xmm0, xmmword ptr [rbx+40h]
0x18001cb18  movaps  [rbp+57h+var_60], xmm1
0x18001cb1c  movups  xmm1, xmmword ptr [rbx+50h]
0x18001cb20  movaps  [rbp+57h+var_50], xmm0
0x18001cb24  movups  xmm0, xmmword ptr [rbx+60h]
0x18001cb28  movaps  [rbp+57h+var_40], xmm1
0x18001cb2c  movups  xmm1, xmmword ptr [rbx+70h]
0x18001cb30  movaps  [rbp+57h+var_30], xmm0
0x18001cb34  movaps  [rbp+57h+var_20], xmm1
0x18001cb38  lea     rdx, [rbp+57h+var_D0]
0x18001cb3c  mov     rcx, rdi
0x18001cb3f  call    cs:__imp_SamIUpdateLogonStatistics
0x18001cb45  xor     eax, eax
0x18001cb47  mov     rcx, [rbp+57h+var_10]
0x18001cb4b  xor     rcx, rsp; StackCookie
0x18001cb4e  call    __security_check_cookie
0x18001cb53  lea     r11, [rsp+0F0h+var_s0]
0x18001cb5b  mov     rbx, [r11+20h]
0x18001cb5f  mov     rdi, [r11+28h]
0x18001cb63  mov     rsp, r11
0x18001cb66  pop     rbp
0x18001cb67  retn
```
