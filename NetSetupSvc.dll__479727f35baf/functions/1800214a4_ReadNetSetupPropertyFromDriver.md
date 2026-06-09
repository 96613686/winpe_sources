# ReadNetSetupPropertyFromDriver

- ea: `0x1800214a4`
- end: `0x180021577`
- name: `ReadNetSetupPropertyFromDriver`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180021350`

## callees

- `0x1800027c0`
- `0x18000d974`
- `0x18001b120`
- `0x18001cee8`
- `0x18001d294`
- `0x1800214a4`
- `0x18002498c`

## pseudocode

```c
void __fastcall ReadNetSetupPropertyFromDriver(__int64 a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  int v4; // eax
  __int64 v5; // r9
  __int64 v6; // r10
  int v7; // r11d
  __int64 v8; // rax
  int v9; // eax
  __int128 v10; // [rsp+30h] [rbp-19h] BYREF
  int v11; // [rsp+40h] [rbp-9h]
  __int64 v12; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v13[24]; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v14[24]; // [rsp+78h] [rbp+2Fh] BYREF

  v3 = *(_OWORD *)(a3 + 20);
  v4 = *(unsigned __int16 *)(a3 + 18);
  v12 = a2;
  v10 = v3;
  v11 = v4;
  NetSetup2::Property::Property((NetSetup2::Property *)v13, (const struct _NETSETUPPROPKEY *)&v10);
  v8 = lambda_157e969c7af1d8bc14c924e68f78f30a_::_lambda_157e969c7af1d8bc14c924e68f78f30a_(
         (unsigned int)&v10,
         v7,
         (unsigned int)&v12,
         (unsigned int)v13,
         v6,
         v5);
  v9 = wil::ResultFromException__lambda_157e969c7af1d8bc14c924e68f78f30a___(v8);
  if ( v9 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
      v12,
      v9);
  std::vector<unsigned char>::_Tidy((__int64)v14);
}

```

## disassembly

```asm
0x1800214a4  push    rbp
0x1800214a6  lea     rbp, [rsp-57h]
0x1800214ab  sub     rsp, 0A0h
0x1800214b2  mov     rax, cs:__security_cookie
0x1800214b9  xor     rax, rsp
0x1800214bc  mov     [rbp+57h+var_10], rax
0x1800214c0  movups  xmm0, xmmword ptr [r8+14h]
0x1800214c5  movzx   eax, word ptr [r8+12h]
0x1800214ca  mov     r11, rcx
0x1800214cd  mov     [rbp+57h+var_48], rdx
0x1800214d1  lea     rcx, [rbp+57h+var_40]; this
0x1800214d5  mov     qword ptr [rbp+57h+var_70], 0
0x1800214dd  lea     rdx, [rbp+57h+var_70]; struct _NETSETUPPROPKEY *
0x1800214e1  mov     qword ptr [rbp+57h+var_70+8], 0
0x1800214e9  mov     r10, r8
0x1800214ec  movdqu  [rbp+57h+var_70], xmm0
0x1800214f1  mov     [rbp+57h+var_60], eax
0x1800214f4  call    ??0Property@NetSetup2@@QEAA@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::Property::Property(_NETSETUPPROPKEY const &)
0x1800214f9  mov     [rsp+0A0h+var_78], r9
0x1800214fe  lea     r8, [rbp+57h+var_48]
0x180021502  lea     r9, [rbp+57h+var_40]
0x180021506  mov     [rsp+0A0h+var_80], r10
0x18002150b  lea     rcx, [rbp+57h+var_70]
0x18002150f  mov     rdx, r11
0x180021512  call    _lambda_157e969c7af1d8bc14c924e68f78f30a____lambda_157e969c7af1d8bc14c924e68f78f30a_
0x180021517  mov     rcx, rax
0x18002151a  call    wil__ResultFromException__lambda_157e969c7af1d8bc14c924e68f78f30a___
0x18002151f  test    eax, eax
0x180021521  jns     short loc_180021559
0x180021523  mov     rcx, cs:WPP_GLOBAL_Control
0x18002152a  lea     rdx, WPP_GLOBAL_Control
0x180021531  cmp     rcx, rdx
0x180021534  jz      short loc_180021559
0x180021536  cmp     byte ptr [rcx+19h], 3
0x18002153a  jb      short loc_180021559
0x18002153c  mov     r9, [rbp+57h+var_48]
0x180021540  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180021547  mov     rcx, [rcx+10h]
0x18002154b  mov     edx, 2Fh ; '/'
0x180021550  mov     dword ptr [rsp+0A0h+var_80], eax
0x180021554  call    WPP_SF_Sd
0x180021559  lea     rcx, [rbp+57h+var_28]
0x18002155d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180021562  mov     rcx, [rbp+57h+var_10]
0x180021566  xor     rcx, rsp; StackCookie
0x180021569  call    __security_check_cookie
0x18002156e  add     rsp, 0A0h
0x180021575  pop     rbp
0x180021576  retn
```
