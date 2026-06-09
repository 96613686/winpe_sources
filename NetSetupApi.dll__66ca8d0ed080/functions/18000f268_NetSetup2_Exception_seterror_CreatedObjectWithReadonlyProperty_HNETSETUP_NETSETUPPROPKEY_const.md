# NetSetup2::Exception::seterror_CreatedObjectWithReadonlyProperty(HNETSETUP__ *,_NETSETUPPROPKEY const &)

- ea: `0x18000f268`
- end: `0x18000f372`
- name: `?seterror_CreatedObjectWithReadonlyProperty@Exception@NetSetup2@@YAXPEAUHNETSETUP__@@AEBU_NETSETUPPROPKEY@@@Z`
- size: `266`
- prototype: `void __fastcall(NetSetup2::Exception *__hidden this, struct HNETSETUP__ *, const struct _NETSETUPPROPKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180002320`

## callees

- `0x180001600`
- `0x18000895c`
- `0x18000d710`
- `0x18000ec70`
- `0x18000f268`
- `0x1800119f0`

## pseudocode

```c
void __fastcall NetSetup2::Exception::seterror_CreatedObjectWithReadonlyProperty(
        NetSetup2::Exception *this,
        struct HNETSETUP__ *a2,
        const struct _NETSETUPPROPKEY *a3)
{
  _DWORD *v5; // rdx
  int v6; // eax
  int pExceptionObject; // [rsp+38h] [rbp-29h] BYREF
  _DWORD *v8; // [rsp+40h] [rbp-21h] BYREF
  int v9; // [rsp+48h] [rbp-19h]
  __int64 v10; // [rsp+58h] [rbp-9h]
  __int128 v11; // [rsp+68h] [rbp+7h] BYREF
  __int128 v12; // [rsp+78h] [rbp+17h] BYREF
  int v13; // [rsp+88h] [rbp+27h]
  int v14; // [rsp+8Ch] [rbp+2Bh]
  __int64 v15; // [rsp+90h] [rbp+2Fh]
  int v16; // [rsp+98h] [rbp+37h]
  int v17; // [rsp+9Ch] [rbp+3Bh]
  _DWORD *v18; // [rsp+A0h] [rbp+3Fh]

  v10 = -2;
  std::vector<unsigned char>::vector<unsigned char>(&v8);
  v5 = v8;
  *v8 = 1;
  v5[1] = 131;
  v5[2] = 20;
  v5[3] = 12;
  *((_OWORD *)v5 + 1) = *(_OWORD *)a2;
  v5[8] = *((_DWORD *)a2 + 4);
  v12 = NETSETUPERROR_Object_CreatedObjectWithReadonlyProperty;
  v13 = 1020;
  v14 = 0;
  v15 = 0;
  v16 = 130;
  v17 = v9 - (_DWORD)v5;
  v18 = v5;
  v11 = 0;
  v6 = NetSetupSetObjectProperties(this, (GUID *)9, (__int64)&v11, 1, (__int64)&v12);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  std::vector<unsigned char>::_Tidy((__int64)&v8);
}

```

## disassembly

```asm
0x18000f268  mov     rax, rsp
0x18000f26b  push    rbp
0x18000f26c  lea     rbp, [rax-5Fh]
0x18000f270  sub     rsp, 0B0h
0x18000f277  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x18000f27f  mov     [rax+10h], rbx
0x18000f283  mov     [rax+18h], rdi
0x18000f287  mov     rax, cs:__security_cookie
0x18000f28e  xor     rax, rsp
0x18000f291  mov     [rbp+57h+var_10], rax
0x18000f295  mov     rbx, rdx
0x18000f298  mov     rdi, rcx
0x18000f29b  mov     edx, 24h ; '$'
0x18000f2a0  lea     rcx, [rbp+57h+var_78]
0x18000f2a4  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z; std::vector<uchar>::vector<uchar>(unsigned __int64)
0x18000f2a9  nop
0x18000f2aa  mov     r9d, 1
0x18000f2b0  mov     rdx, [rbp+57h+var_78]
0x18000f2b4  mov     [rdx], r9d
0x18000f2b7  mov     dword ptr [rdx+4], 83h
0x18000f2be  mov     dword ptr [rdx+8], 14h
0x18000f2c5  mov     dword ptr [rdx+0Ch], 0Ch
0x18000f2cc  movups  xmm0, xmmword ptr [rbx]
0x18000f2cf  movups  xmmword ptr [rdx+10h], xmm0
0x18000f2d3  mov     eax, [rbx+10h]
0x18000f2d6  mov     [rdx+20h], eax
0x18000f2d9  movups  xmm0, cs:NETSETUPERROR_Object_CreatedObjectWithReadonlyProperty
0x18000f2e0  movups  [rbp+57h+var_40], xmm0
0x18000f2e4  mov     eax, cs:dword_18001F4A8
0x18000f2ea  mov     [rbp+57h+var_30], eax
0x18000f2ed  mov     [rbp+57h+var_2C], 0
0x18000f2f4  mov     [rbp+57h+var_28], 0
0x18000f2fc  mov     [rbp+57h+var_20], 82h
0x18000f303  mov     eax, [rbp+57h+var_70]
0x18000f306  sub     eax, edx
0x18000f308  mov     [rbp+57h+var_1C], eax
0x18000f30b  mov     [rbp+57h+var_18], rdx
0x18000f30f  xorps   xmm0, xmm0
0x18000f312  movdqa  [rbp+57h+var_50], xmm0
0x18000f317  lea     rax, [rbp+57h+var_40]
0x18000f31b  mov     [rsp+0B0h+var_90], rax
0x18000f320  lea     r8, [rbp+57h+var_50]
0x18000f324  lea     edx, [r9+8]
0x18000f328  mov     rcx, rdi
0x18000f32b  call    NetSetupSetObjectProperties
0x18000f330  test    eax, eax
0x18000f332  jns     short loc_18000F348
0x18000f334  mov     [rbp+57h+pExceptionObject], eax
0x18000f337  lea     rdx, _TI1J; pThrowInfo
0x18000f33e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f342  call    _CxxThrowException_0
0x18000f348  lea     rcx, [rbp+57h+var_78]
0x18000f34c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000f351  mov     rcx, [rbp+57h+var_10]
0x18000f355  xor     rcx, rsp; StackCookie
0x18000f358  call    __security_check_cookie
0x18000f35d  lea     r11, [rsp+0B0h+var_s0]
0x18000f365  mov     rbx, [r11+18h]
0x18000f369  mov     rdi, [r11+20h]
0x18000f36d  mov     rsp, r11
0x18000f370  pop     rbp
0x18000f371  retn
```
