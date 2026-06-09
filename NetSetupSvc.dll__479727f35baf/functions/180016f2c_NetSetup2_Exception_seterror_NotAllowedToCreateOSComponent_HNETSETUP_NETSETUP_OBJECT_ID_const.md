# NetSetup2::Exception::seterror_NotAllowedToCreateOSComponent(HNETSETUP__ *,_NETSETUP_OBJECT_ID const &)

- ea: `0x180016f2c`
- end: `0x180017033`
- name: `?seterror_NotAllowedToCreateOSComponent@Exception@NetSetup2@@YAXPEAUHNETSETUP__@@AEBU_NETSETUP_OBJECT_ID@@@Z`
- size: `263`
- prototype: `void __fastcall(NetSetup2::Exception *__hidden this, struct HNETSETUP__ *, const struct _NETSETUP_OBJECT_ID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001703c`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x18000d974`
- `0x18000ec8c`
- `0x180016f2c`

## import_xrefs

- `NetSetupApi!NetSetupSetObjectProperties` at `0x180016feb`
- `NetSetupApi!NetSetupSetObjectProperties` at `0x180016feb`

## pseudocode

```c
void __fastcall NetSetup2::Exception::seterror_NotAllowedToCreateOSComponent(
        NetSetup2::Exception *this,
        struct HNETSETUP__ *a2,
        const struct _NETSETUP_OBJECT_ID *a3)
{
  _DWORD *v5; // rcx
  int v6; // eax
  int pExceptionObject; // [rsp+30h] [rbp-19h] BYREF
  __int128 v8; // [rsp+40h] [rbp-9h] BYREF
  __int128 v9; // [rsp+50h] [rbp+7h] BYREF
  int v10; // [rsp+60h] [rbp+17h]
  int v11; // [rsp+64h] [rbp+1Bh]
  __int64 v12; // [rsp+68h] [rbp+1Fh]
  int v13; // [rsp+70h] [rbp+27h]
  int v14; // [rsp+74h] [rbp+2Bh]
  _DWORD *v15; // [rsp+78h] [rbp+2Fh]
  _DWORD *v16; // [rsp+80h] [rbp+37h] BYREF
  int v17; // [rsp+88h] [rbp+3Fh]

  std::vector<unsigned char>::vector<unsigned char>(&v16, 36);
  v5 = v16;
  *v16 = 1;
  v5[1] = 129;
  v5[2] = 20;
  v5[3] = 12;
  *((_OWORD *)v5 + 1) = *(_OWORD *)a2;
  v5[8] = *((_DWORD *)a2 + 4);
  v9 = NETSETUPERROR_Driver_NotAllowedToCreateOSComponent;
  v10 = 1006;
  v11 = 0;
  v12 = 0;
  v13 = 130;
  v14 = v17 - (_DWORD)v16;
  v15 = v16;
  v8 = 0;
  v6 = NetSetupSetObjectProperties(this, 9, &v8, 1, &v9);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  std::vector<unsigned char>::_Tidy((__int64)&v16);
}

```

## disassembly

```asm
0x180016f2c  mov     [rsp-8+arg_8], rbx
0x180016f31  mov     [rsp-8+arg_10], rdi
0x180016f36  push    rbp
0x180016f37  lea     rbp, [rsp-57h]
0x180016f3c  sub     rsp, 0A0h
0x180016f43  mov     rax, cs:__security_cookie
0x180016f4a  xor     rax, rsp
0x180016f4d  mov     [rbp+57h+var_8], rax
0x180016f51  mov     rbx, rdx
0x180016f54  mov     rdi, rcx
0x180016f57  mov     edx, 24h ; '$'
0x180016f5c  lea     rcx, [rbp+57h+var_20]
0x180016f60  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180016f65  nop
0x180016f66  mov     rcx, [rbp+57h+var_20]
0x180016f6a  mov     r9d, 1
0x180016f70  mov     [rcx], r9d
0x180016f73  mov     dword ptr [rcx+4], 81h
0x180016f7a  mov     dword ptr [rcx+8], 14h
0x180016f81  mov     dword ptr [rcx+0Ch], 0Ch
0x180016f88  movups  xmm0, xmmword ptr [rbx]
0x180016f8b  movups  xmmword ptr [rcx+10h], xmm0
0x180016f8f  mov     eax, [rbx+10h]
0x180016f92  mov     [rcx+20h], eax
0x180016f95  movups  xmm0, cs:NETSETUPERROR_Driver_NotAllowedToCreateOSComponent
0x180016f9c  movups  [rbp+57h+var_50], xmm0
0x180016fa0  mov     eax, cs:dword_180037968
0x180016fa6  mov     [rbp+57h+var_40], eax
0x180016fa9  mov     [rbp+57h+var_3C], 0
0x180016fb0  mov     [rbp+57h+var_38], 0
0x180016fb8  mov     [rbp+57h+var_30], 82h
0x180016fbf  mov     eax, [rbp+57h+var_18]
0x180016fc2  mov     rdx, [rbp+57h+var_20]
0x180016fc6  sub     eax, edx
0x180016fc8  mov     [rbp+57h+var_2C], eax
0x180016fcb  mov     [rbp+57h+var_28], rdx
0x180016fcf  xorps   xmm0, xmm0
0x180016fd2  movdqa  [rbp+57h+var_60], xmm0
0x180016fd7  lea     rax, [rbp+57h+var_50]
0x180016fdb  mov     [rsp+0A0h+var_80], rax
0x180016fe0  lea     r8, [rbp+57h+var_60]
0x180016fe4  lea     edx, [r9+8]
0x180016fe8  mov     rcx, rdi
0x180016feb  call    cs:__imp_NetSetupSetObjectProperties
0x180016ff1  test    eax, eax
0x180016ff3  jns     short loc_180017009
0x180016ff5  mov     [rbp+57h+pExceptionObject], eax
0x180016ff8  lea     rdx, _TI1J; pThrowInfo
0x180016fff  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180017003  call    _CxxThrowException_0
0x180017009  lea     rcx, [rbp+57h+var_20]
0x18001700d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180017012  mov     rcx, [rbp+57h+var_8]
0x180017016  xor     rcx, rsp; StackCookie
0x180017019  call    __security_check_cookie
0x18001701e  lea     r11, [rsp+0A0h+var_s0]
0x180017026  mov     rbx, [r11+18h]
0x18001702a  mov     rdi, [r11+20h]
0x18001702e  mov     rsp, r11
0x180017031  pop     rbp
0x180017032  retn
```
