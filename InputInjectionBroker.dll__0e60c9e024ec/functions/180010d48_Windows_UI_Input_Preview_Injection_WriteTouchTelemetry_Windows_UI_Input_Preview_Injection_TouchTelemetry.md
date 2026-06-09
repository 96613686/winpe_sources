# Windows::UI::Input::Preview::Injection::WriteTouchTelemetry(Windows::UI::Input::Preview::Injection::TouchTelemetry &)

- ea: `0x180010d48`
- end: `0x180010f4e`
- name: `?WriteTouchTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUTouchTelemetry@12345@@Z`
- size: `518`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *__hidden this, struct Windows::UI::Input::Preview::Injection::TouchTelemetry *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e460`

## callees

- `0x18000125c`
- `0x180010d48`
- `0x180011460`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WriteTouchTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::TouchTelemetry *a2)
{
  int v2; // [rsp+30h] [rbp-D0h] BYREF
  int v3; // [rsp+34h] [rbp-CCh] BYREF
  int v4; // [rsp+38h] [rbp-C8h] BYREF
  int v5; // [rsp+3Ch] [rbp-C4h] BYREF
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+44h] [rbp-BCh] BYREF
  int v8; // [rsp+48h] [rbp-B8h] BYREF
  int v9; // [rsp+4Ch] [rbp-B4h] BYREF
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+54h] [rbp-ACh] BYREF
  int v12; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+5Ch] [rbp-A4h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp-90h] BYREF
  const char *v17; // [rsp+90h] [rbp-70h]
  __int64 v18; // [rsp+98h] [rbp-68h]
  int *v19; // [rsp+A0h] [rbp-60h]
  __int64 v20; // [rsp+A8h] [rbp-58h]
  int *v21; // [rsp+B0h] [rbp-50h]
  __int64 v22; // [rsp+B8h] [rbp-48h]
  int *v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  int *v25; // [rsp+D0h] [rbp-30h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  int *v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  int *v29; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+F8h] [rbp-8h]
  int *v31; // [rsp+100h] [rbp+0h]
  __int64 v32; // [rsp+108h] [rbp+8h]
  int *v33; // [rsp+110h] [rbp+10h]
  __int64 v34; // [rsp+118h] [rbp+18h]
  int *v35; // [rsp+120h] [rbp+20h]
  __int64 v36; // [rsp+128h] [rbp+28h]
  int *v37; // [rsp+130h] [rbp+30h]
  __int64 v38; // [rsp+138h] [rbp+38h]
  int *v39; // [rsp+140h] [rbp+40h]
  __int64 v40; // [rsp+148h] [rbp+48h]
  int *v41; // [rsp+150h] [rbp+50h]
  __int64 v42; // [rsp+158h] [rbp+58h]
  int *v43; // [rsp+160h] [rbp+60h]
  __int64 v44; // [rsp+168h] [rbp+68h]
  int *v45; // [rsp+170h] [rbp+70h]
  __int64 v46; // [rsp+178h] [rbp+78h]

  if ( (unsigned int)dword_180022000 > 5
    && (qword_180022010 & 0x400000000000LL) != 0
    && (qword_180022018 & 0x400000000000LL) == qword_180022018 )
  {
    v2 = *((_DWORD *)this + 12);
    v3 = *((_DWORD *)this + 10);
    v4 = *((_DWORD *)this + 13);
    v5 = *((_DWORD *)this + 11);
    v6 = *((_DWORD *)this + 9);
    v7 = *((_DWORD *)this + 8);
    v8 = *((_DWORD *)this + 7);
    v9 = *((_DWORD *)this + 2);
    v10 = *((_DWORD *)this + 5);
    v11 = *((_DWORD *)this + 1);
    v12 = *(_DWORD *)this;
    v13 = *((_DWORD *)this + 4);
    v14 = *((_DWORD *)this + 3);
    v15 = *((_DWORD *)this + 6);
    v45 = &v2;
    v43 = &v3;
    v41 = &v4;
    v39 = &v5;
    v37 = &v6;
    v35 = &v7;
    v33 = &v8;
    v31 = &v9;
    v29 = &v10;
    v27 = &v11;
    v25 = &v12;
    v23 = &v13;
    v21 = &v14;
    v19 = &v15;
    v17 = "InjectTouch";
    v46 = 4;
    v44 = 4;
    v42 = 4;
    v40 = 4;
    v38 = 4;
    v36 = 4;
    v34 = 4;
    v32 = 4;
    v30 = 4;
    v28 = 4;
    v26 = 4;
    v24 = 4;
    v22 = 4;
    v20 = 4;
    v18 = 12;
    tlgWriteTransfer_EventWriteTransfer(&dword_180022000, &word_18001E9F6, 0, 0, 17, v16);
  }
}

```

## disassembly

```asm
0x180010d48  push    rbp
0x180010d4a  lea     rbp, [rsp-90h]
0x180010d52  sub     rsp, 190h
0x180010d59  mov     rax, cs:__security_cookie
0x180010d60  xor     rax, rsp
0x180010d63  mov     [rbp+90h+var_10], rax
0x180010d6a  mov     eax, cs:dword_180022000
0x180010d70  cmp     eax, 5
0x180010d73  jbe     loc_180010F36
0x180010d79  mov     rdx, cs:qword_180022018
0x180010d80  mov     r8, 400000000000h
0x180010d8a  mov     rax, cs:qword_180022010
0x180010d91  test    r8, rax
0x180010d94  jz      loc_180010F36
0x180010d9a  mov     rax, rdx
0x180010d9d  and     rax, r8
0x180010da0  cmp     rax, rdx
0x180010da3  jnz     loc_180010F36
0x180010da9  mov     eax, [rcx+30h]
0x180010dac  lea     rdx, word_18001E9F6
0x180010db3  mov     [rsp+190h+var_160], eax
0x180010db7  xor     r9d, r9d
0x180010dba  mov     eax, [rcx+28h]
0x180010dbd  xor     r8d, r8d
0x180010dc0  mov     [rsp+190h+var_15C], eax
0x180010dc4  mov     eax, [rcx+34h]
0x180010dc7  mov     [rsp+190h+var_158], eax
0x180010dcb  mov     eax, [rcx+2Ch]
0x180010dce  mov     [rsp+190h+var_154], eax
0x180010dd2  mov     eax, [rcx+24h]
0x180010dd5  mov     [rsp+190h+var_150], eax
0x180010dd9  mov     eax, [rcx+20h]
0x180010ddc  mov     [rsp+190h+var_14C], eax
0x180010de0  mov     eax, [rcx+1Ch]
0x180010de3  mov     [rsp+190h+var_148], eax
0x180010de7  mov     eax, [rcx+8]
0x180010dea  mov     [rsp+190h+var_144], eax
0x180010dee  mov     eax, [rcx+14h]
0x180010df1  mov     [rsp+190h+var_140], eax
0x180010df5  mov     eax, [rcx+4]
0x180010df8  mov     [rsp+190h+var_13C], eax
0x180010dfc  mov     eax, [rcx]
0x180010dfe  mov     [rsp+190h+var_138], eax
0x180010e02  mov     eax, [rcx+10h]
0x180010e05  mov     [rsp+190h+var_134], eax
0x180010e09  mov     eax, [rcx+0Ch]
0x180010e0c  mov     [rsp+190h+var_130], eax
0x180010e10  mov     eax, [rcx+18h]
0x180010e13  lea     rcx, dword_180022000
0x180010e1a  mov     [rsp+190h+var_12C], eax
0x180010e1e  lea     rax, [rsp+190h+var_160]
0x180010e23  mov     [rbp+90h+var_20], rax
0x180010e27  lea     rax, [rsp+190h+var_15C]
0x180010e2c  mov     [rbp+90h+var_30], rax
0x180010e30  lea     rax, [rsp+190h+var_158]
0x180010e35  mov     [rbp+90h+var_40], rax
0x180010e39  lea     rax, [rsp+190h+var_154]
0x180010e3e  mov     [rbp+90h+var_50], rax
0x180010e42  lea     rax, [rsp+190h+var_150]
0x180010e47  mov     [rbp+90h+var_60], rax
0x180010e4b  lea     rax, [rsp+190h+var_14C]
0x180010e50  mov     [rbp+90h+var_70], rax
0x180010e54  lea     rax, [rsp+190h+var_148]
0x180010e59  mov     [rbp+90h+var_80], rax
0x180010e5d  lea     rax, [rsp+190h+var_144]
0x180010e62  mov     [rbp+90h+var_90], rax
0x180010e66  lea     rax, [rsp+190h+var_140]
0x180010e6b  mov     [rbp+90h+var_A0], rax
0x180010e6f  lea     rax, [rsp+190h+var_13C]
0x180010e74  mov     [rbp+90h+var_B0], rax
0x180010e78  lea     rax, [rsp+190h+var_138]
0x180010e7d  mov     [rbp+90h+var_C0], rax
0x180010e81  lea     rax, [rsp+190h+var_134]
0x180010e86  mov     [rbp+90h+var_D0], rax
0x180010e8a  lea     rax, [rsp+190h+var_130]
0x180010e8f  mov     [rbp+90h+var_E0], rax
0x180010e93  lea     rax, [rsp+190h+var_12C]
0x180010e98  mov     [rbp+90h+var_F0], rax
0x180010e9c  lea     rax, aInjecttouch; "InjectTouch"
0x180010ea3  mov     [rbp+90h+var_100], rax
0x180010ea7  lea     rax, [rsp+190h+var_120]
0x180010eac  mov     [rsp+190h+var_168], rax
0x180010eb1  mov     [rsp+190h+var_170], 11h
0x180010eb9  mov     [rbp+90h+var_18], 4
0x180010ec1  mov     [rbp+90h+var_28], 4
0x180010ec9  mov     [rbp+90h+var_38], 4
0x180010ed1  mov     [rbp+90h+var_48], 4
0x180010ed9  mov     [rbp+90h+var_58], 4
0x180010ee1  mov     [rbp+90h+var_68], 4
0x180010ee9  mov     [rbp+90h+var_78], 4
0x180010ef1  mov     [rbp+90h+var_88], 4
0x180010ef9  mov     [rbp+90h+var_98], 4
0x180010f01  mov     [rbp+90h+var_A8], 4
0x180010f09  mov     [rbp+90h+var_B8], 4
0x180010f11  mov     [rbp+90h+var_C8], 4
0x180010f19  mov     [rbp+90h+var_D8], 4
0x180010f21  mov     [rbp+90h+var_E8], 4
0x180010f29  mov     [rbp+90h+var_F8], 0Ch
0x180010f31  call    _tlgWriteTransfer_EventWriteTransfer
0x180010f36  mov     rcx, [rbp+90h+var_10]
0x180010f3d  xor     rcx, rsp; StackCookie
0x180010f40  call    __security_check_cookie
0x180010f45  add     rsp, 190h
0x180010f4c  pop     rbp
0x180010f4d  retn
```
