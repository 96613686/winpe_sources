# NetSetup2::Exception::seterror_ModifiedReadonlyProperty(HNETSETUP__ *,_NETSETUP_OBJECT_ID const &,_NETSETUPPROPKEY const &)

- ea: `0x18000f378`
- end: `0x18000f498`
- name: `?seterror_ModifiedReadonlyProperty@Exception@NetSetup2@@YAXPEAUHNETSETUP__@@AEBU_NETSETUP_OBJECT_ID@@AEBU_NETSETUPPROPKEY@@@Z`
- size: `288`
- prototype: `void __fastcall(NetSetup2::Exception *__hidden this, struct HNETSETUP__ *, const struct _NETSETUP_OBJECT_ID *, const struct _NETSETUPPROPKEY *)`
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
- `0x18000f378`
- `0x1800119f0`

## pseudocode

```c
void __fastcall NetSetup2::Exception::seterror_ModifiedReadonlyProperty(
        NetSetup2::Exception *this,
        struct HNETSETUP__ *a2,
        const struct _NETSETUP_OBJECT_ID *a3,
        const struct _NETSETUPPROPKEY *a4)
{
  _DWORD *v7; // rdx
  int v8; // eax
  int pExceptionObject; // [rsp+30h] [rbp-49h] BYREF
  _DWORD *v10; // [rsp+38h] [rbp-41h] BYREF
  int v11; // [rsp+40h] [rbp-39h]
  __int64 v12; // [rsp+50h] [rbp-29h]
  __int128 v13; // [rsp+60h] [rbp-19h] BYREF
  __int128 v14; // [rsp+70h] [rbp-9h] BYREF
  int v15; // [rsp+80h] [rbp+7h]
  int v16; // [rsp+84h] [rbp+Bh]
  __int64 v17; // [rsp+88h] [rbp+Fh]
  int v18; // [rsp+90h] [rbp+17h]
  int v19; // [rsp+94h] [rbp+1Bh]
  _DWORD *v20; // [rsp+98h] [rbp+1Fh]

  v12 = -2;
  std::vector<unsigned char>::vector<unsigned char>(&v10);
  v7 = v10;
  *v10 = 2;
  v7[1] = 129;
  v7[2] = 20;
  v7[3] = 24;
  v7[4] = 131;
  v7[5] = 20;
  v7[6] = 32;
  *(_OWORD *)(v7 + 7) = *(_OWORD *)a2;
  v7[11] = *((_DWORD *)a2 + 4);
  *((_OWORD *)v7 + 3) = *(_OWORD *)a3;
  v7[16] = *((_DWORD *)a3 + 4);
  v14 = NETSETUPERROR_Object_ModifiedReadonlyProperty;
  v15 = 1022;
  v16 = 0;
  v17 = 0;
  v18 = 130;
  v19 = v11 - (_DWORD)v7;
  v20 = v7;
  v13 = 0;
  v8 = NetSetupSetObjectProperties(this, (GUID *)9, (__int64)&v13, 1, (__int64)&v14);
  if ( v8 < 0 )
  {
    pExceptionObject = v8;
    throw (long *)&pExceptionObject;
  }
  std::vector<unsigned char>::_Tidy((__int64)&v10);
}

```

## disassembly

```asm
0x18000f378  push    rbp
0x18000f37a  push    rbx
0x18000f37b  push    rsi
0x18000f37c  push    rdi
0x18000f37d  lea     rbp, [rsp-3Fh]
0x18000f382  sub     rsp, 0B8h
0x18000f389  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x18000f391  mov     rax, cs:__security_cookie
0x18000f398  xor     rax, rsp
0x18000f39b  mov     [rbp+57h+var_30], rax
0x18000f39f  mov     rdi, r8
0x18000f3a2  mov     rbx, rdx
0x18000f3a5  mov     rsi, rcx
0x18000f3a8  mov     edx, 44h ; 'D'
0x18000f3ad  lea     rcx, [rbp+57h+var_98]
0x18000f3b1  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z; std::vector<uchar>::vector<uchar>(unsigned __int64)
0x18000f3b6  nop
0x18000f3b7  mov     rdx, [rbp+57h+var_98]
0x18000f3bb  mov     dword ptr [rdx], 2
0x18000f3c1  mov     dword ptr [rdx+4], 81h
0x18000f3c8  mov     eax, 14h
0x18000f3cd  mov     [rdx+8], eax
0x18000f3d0  mov     dword ptr [rdx+0Ch], 18h
0x18000f3d7  mov     dword ptr [rdx+10h], 83h
0x18000f3de  mov     [rdx+14h], eax
0x18000f3e1  mov     dword ptr [rdx+18h], 20h ; ' '
0x18000f3e8  movups  xmm0, xmmword ptr [rbx]
0x18000f3eb  movups  xmmword ptr [rdx+1Ch], xmm0
0x18000f3ef  mov     eax, [rbx+10h]
0x18000f3f2  mov     [rdx+2Ch], eax
0x18000f3f5  movups  xmm0, xmmword ptr [rdi]
0x18000f3f8  movups  xmmword ptr [rdx+30h], xmm0
0x18000f3fc  mov     eax, [rdi+10h]
0x18000f3ff  mov     [rdx+40h], eax
0x18000f402  movups  xmm0, cs:NETSETUPERROR_Object_ModifiedReadonlyProperty
0x18000f409  movups  [rbp+57h+var_60], xmm0
0x18000f40d  mov     eax, cs:dword_18001F490
0x18000f413  mov     [rbp+57h+var_50], eax
0x18000f416  mov     [rbp+57h+var_4C], 0
0x18000f41d  mov     [rbp+57h+var_48], 0
0x18000f425  mov     [rbp+57h+var_40], 82h
0x18000f42c  mov     eax, [rbp+57h+var_90]
0x18000f42f  sub     eax, edx
0x18000f431  mov     [rbp+57h+var_3C], eax
0x18000f434  mov     [rbp+57h+var_38], rdx
0x18000f438  xorps   xmm0, xmm0
0x18000f43b  movdqa  [rbp+57h+var_70], xmm0
0x18000f440  lea     rax, [rbp+57h+var_60]
0x18000f444  mov     [rsp+0D0h+var_B0], rax
0x18000f449  mov     r9d, 1
0x18000f44f  lea     r8, [rbp+57h+var_70]
0x18000f453  lea     edx, [r9+8]
0x18000f457  mov     rcx, rsi
0x18000f45a  call    NetSetupSetObjectProperties
0x18000f45f  test    eax, eax
0x18000f461  jns     short loc_18000F477
0x18000f463  mov     [rbp+57h+pExceptionObject], eax
0x18000f466  lea     rdx, _TI1J; pThrowInfo
0x18000f46d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f471  call    _CxxThrowException_0
0x18000f477  lea     rcx, [rbp+57h+var_98]
0x18000f47b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000f480  mov     rcx, [rbp+57h+var_30]
0x18000f484  xor     rcx, rsp; StackCookie
0x18000f487  call    __security_check_cookie
0x18000f48c  add     rsp, 0B8h
0x18000f493  pop     rdi
0x18000f494  pop     rsi
0x18000f495  pop     rbx
0x18000f496  pop     rbp
0x18000f497  retn
```
