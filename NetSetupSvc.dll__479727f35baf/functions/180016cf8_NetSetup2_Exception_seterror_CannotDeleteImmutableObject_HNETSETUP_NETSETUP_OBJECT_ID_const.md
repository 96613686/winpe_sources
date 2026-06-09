# NetSetup2::Exception::seterror_CannotDeleteImmutableObject(HNETSETUP__ *,_NETSETUP_OBJECT_ID const &)

- ea: `0x180016cf8`
- end: `0x180016dff`
- name: `?seterror_CannotDeleteImmutableObject@Exception@NetSetup2@@YAXPEAUHNETSETUP__@@AEBU_NETSETUP_OBJECT_ID@@@Z`
- size: `263`
- prototype: `void __fastcall(NetSetup2::Exception *__hidden this, struct HNETSETUP__ *, const struct _NETSETUP_OBJECT_ID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180012cc8`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x18000d974`
- `0x18000ec8c`
- `0x180016cf8`

## import_xrefs

- `NetSetupApi!NetSetupSetObjectProperties` at `0x180016db7`
- `NetSetupApi!NetSetupSetObjectProperties` at `0x180016db7`

## pseudocode

```c
void __fastcall NetSetup2::Exception::seterror_CannotDeleteImmutableObject(
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
  v9 = NETSETUPERROR_Driver_CannotDeleteImmutableObject;
  v10 = 1004;
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
0x180016cf8  mov     [rsp-8+arg_8], rbx
0x180016cfd  mov     [rsp-8+arg_10], rdi
0x180016d02  push    rbp
0x180016d03  lea     rbp, [rsp-57h]
0x180016d08  sub     rsp, 0A0h
0x180016d0f  mov     rax, cs:__security_cookie
0x180016d16  xor     rax, rsp
0x180016d19  mov     [rbp+57h+var_8], rax
0x180016d1d  mov     rbx, rdx
0x180016d20  mov     rdi, rcx
0x180016d23  mov     edx, 24h ; '$'
0x180016d28  lea     rcx, [rbp+57h+var_20]
0x180016d2c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180016d31  nop
0x180016d32  mov     rcx, [rbp+57h+var_20]
0x180016d36  mov     r9d, 1
0x180016d3c  mov     [rcx], r9d
0x180016d3f  mov     dword ptr [rcx+4], 81h
0x180016d46  mov     dword ptr [rcx+8], 14h
0x180016d4d  mov     dword ptr [rcx+0Ch], 0Ch
0x180016d54  movups  xmm0, xmmword ptr [rbx]
0x180016d57  movups  xmmword ptr [rcx+10h], xmm0
0x180016d5b  mov     eax, [rbx+10h]
0x180016d5e  mov     [rcx+20h], eax
0x180016d61  movups  xmm0, cs:NETSETUPERROR_Driver_CannotDeleteImmutableObject
0x180016d68  movups  [rbp+57h+var_50], xmm0
0x180016d6c  mov     eax, cs:dword_180037980
0x180016d72  mov     [rbp+57h+var_40], eax
0x180016d75  mov     [rbp+57h+var_3C], 0
0x180016d7c  mov     [rbp+57h+var_38], 0
0x180016d84  mov     [rbp+57h+var_30], 82h
0x180016d8b  mov     eax, [rbp+57h+var_18]
0x180016d8e  mov     rdx, [rbp+57h+var_20]
0x180016d92  sub     eax, edx
0x180016d94  mov     [rbp+57h+var_2C], eax
0x180016d97  mov     [rbp+57h+var_28], rdx
0x180016d9b  xorps   xmm0, xmm0
0x180016d9e  movdqa  [rbp+57h+var_60], xmm0
0x180016da3  lea     rax, [rbp+57h+var_50]
0x180016da7  mov     [rsp+0A0h+var_80], rax
0x180016dac  lea     r8, [rbp+57h+var_60]
0x180016db0  lea     edx, [r9+8]
0x180016db4  mov     rcx, rdi
0x180016db7  call    cs:__imp_NetSetupSetObjectProperties
0x180016dbd  test    eax, eax
0x180016dbf  jns     short loc_180016DD5
0x180016dc1  mov     [rbp+57h+pExceptionObject], eax
0x180016dc4  lea     rdx, _TI1J; pThrowInfo
0x180016dcb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180016dcf  call    _CxxThrowException_0
0x180016dd5  lea     rcx, [rbp+57h+var_20]
0x180016dd9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180016dde  mov     rcx, [rbp+57h+var_8]
0x180016de2  xor     rcx, rsp; StackCookie
0x180016de5  call    __security_check_cookie
0x180016dea  lea     r11, [rsp+0A0h+var_s0]
0x180016df2  mov     rbx, [r11+18h]
0x180016df6  mov     rdi, [r11+20h]
0x180016dfa  mov     rsp, r11
0x180016dfd  pop     rbp
0x180016dfe  retn
```
