# Windows::UI::Input::Preview::Injection::WritePenTelemetry(Windows::UI::Input::Preview::Injection::PenTelemetry &)

- ea: `0x180010aac`
- end: `0x180010c79`
- name: `?WritePenTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUPenTelemetry@12345@@Z`
- size: `461`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *__hidden this, struct Windows::UI::Input::Preview::Injection::PenTelemetry *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e3d0`

## callees

- `0x18000125c`
- `0x180010aac`
- `0x180011460`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WritePenTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::PenTelemetry *a2)
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
  _BYTE v14[32]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+88h] [rbp-78h]
  int *v17; // [rsp+90h] [rbp-70h]
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

  if ( (unsigned int)dword_180022000 > 5
    && (qword_180022010 & 0x400000000000LL) != 0
    && (qword_180022018 & 0x400000000000LL) == qword_180022018 )
  {
    v2 = *((_DWORD *)this + 11);
    v3 = *((_DWORD *)this + 9);
    v4 = *((_DWORD *)this + 12);
    v5 = *((_DWORD *)this + 10);
    v6 = *((_DWORD *)this + 5);
    v7 = *((_DWORD *)this + 7);
    v8 = *((_DWORD *)this + 6);
    v9 = *((_DWORD *)this + 1);
    v10 = *(_DWORD *)this;
    v11 = *((_DWORD *)this + 3);
    v12 = *((_DWORD *)this + 2);
    v13 = *((_DWORD *)this + 4);
    v39 = &v2;
    v37 = &v3;
    v35 = &v4;
    v33 = &v5;
    v31 = &v6;
    v29 = &v7;
    v27 = &v8;
    v25 = &v9;
    v23 = &v10;
    v21 = &v11;
    v19 = &v12;
    v17 = &v13;
    v15 = "InjectPen";
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
    v18 = 4;
    v16 = 10;
    tlgWriteTransfer_EventWriteTransfer(&dword_180022000, byte_18001E6C1, 0, 0, 15, v14);
  }
}

```

## disassembly

```asm
0x180010aac  push    rbp
0x180010aae  lea     rbp, [rsp-60h]
0x180010ab3  sub     rsp, 160h
0x180010aba  mov     rax, cs:__security_cookie
0x180010ac1  xor     rax, rsp
0x180010ac4  mov     [rbp+60h+var_10], rax
0x180010ac8  mov     eax, cs:dword_180022000
0x180010ace  cmp     eax, 5
0x180010ad1  jbe     loc_180010C64
0x180010ad7  mov     rdx, cs:qword_180022018
0x180010ade  mov     r8, 400000000000h
0x180010ae8  mov     rax, cs:qword_180022010
0x180010aef  test    r8, rax
0x180010af2  jz      loc_180010C64
0x180010af8  mov     rax, rdx
0x180010afb  and     rax, r8
0x180010afe  cmp     rax, rdx
0x180010b01  jnz     loc_180010C64
0x180010b07  mov     eax, [rcx+2Ch]
0x180010b0a  lea     rdx, byte_18001E6C1
0x180010b11  mov     [rsp+160h+var_130], eax
0x180010b15  xor     r9d, r9d
0x180010b18  mov     eax, [rcx+24h]
0x180010b1b  xor     r8d, r8d
0x180010b1e  mov     [rsp+160h+var_12C], eax
0x180010b22  mov     eax, [rcx+30h]
0x180010b25  mov     [rsp+160h+var_128], eax
0x180010b29  mov     eax, [rcx+28h]
0x180010b2c  mov     [rsp+160h+var_124], eax
0x180010b30  mov     eax, [rcx+14h]
0x180010b33  mov     [rsp+160h+var_120], eax
0x180010b37  mov     eax, [rcx+1Ch]
0x180010b3a  mov     [rsp+160h+var_11C], eax
0x180010b3e  mov     eax, [rcx+18h]
0x180010b41  mov     [rsp+160h+var_118], eax
0x180010b45  mov     eax, [rcx+4]
0x180010b48  mov     [rsp+160h+var_114], eax
0x180010b4c  mov     eax, [rcx]
0x180010b4e  mov     [rsp+160h+var_110], eax
0x180010b52  mov     eax, [rcx+0Ch]
0x180010b55  mov     [rsp+160h+var_10C], eax
0x180010b59  mov     eax, [rcx+8]
0x180010b5c  mov     [rsp+160h+var_108], eax
0x180010b60  mov     eax, [rcx+10h]
0x180010b63  lea     rcx, dword_180022000
0x180010b6a  mov     [rsp+160h+var_104], eax
0x180010b6e  lea     rax, [rsp+160h+var_130]
0x180010b73  mov     [rbp+60h+var_20], rax
0x180010b77  lea     rax, [rsp+160h+var_12C]
0x180010b7c  mov     [rbp+60h+var_30], rax
0x180010b80  lea     rax, [rsp+160h+var_128]
0x180010b85  mov     [rbp+60h+var_40], rax
0x180010b89  lea     rax, [rsp+160h+var_124]
0x180010b8e  mov     [rbp+60h+var_50], rax
0x180010b92  lea     rax, [rsp+160h+var_120]
0x180010b97  mov     [rbp+60h+var_60], rax
0x180010b9b  lea     rax, [rsp+160h+var_11C]
0x180010ba0  mov     [rbp+60h+var_70], rax
0x180010ba4  lea     rax, [rsp+160h+var_118]
0x180010ba9  mov     [rbp+60h+var_80], rax
0x180010bad  lea     rax, [rsp+160h+var_114]
0x180010bb2  mov     [rbp+60h+var_90], rax
0x180010bb6  lea     rax, [rsp+160h+var_110]
0x180010bbb  mov     [rbp+60h+var_A0], rax
0x180010bbf  lea     rax, [rsp+160h+var_10C]
0x180010bc4  mov     [rbp+60h+var_B0], rax
0x180010bc8  lea     rax, [rsp+160h+var_108]
0x180010bcd  mov     [rbp+60h+var_C0], rax
0x180010bd1  lea     rax, [rsp+160h+var_104]
0x180010bd6  mov     [rbp+60h+var_D0], rax
0x180010bda  lea     rax, aInjectpen; "InjectPen"
0x180010be1  mov     [rbp+60h+var_E0], rax
0x180010be5  lea     rax, [rsp+160h+var_100]
0x180010bea  mov     [rsp+160h+var_138], rax
0x180010bef  mov     [rsp+160h+var_140], 0Fh
0x180010bf7  mov     [rbp+60h+var_18], 4
0x180010bff  mov     [rbp+60h+var_28], 4
0x180010c07  mov     [rbp+60h+var_38], 4
0x180010c0f  mov     [rbp+60h+var_48], 4
0x180010c17  mov     [rbp+60h+var_58], 4
0x180010c1f  mov     [rbp+60h+var_68], 4
0x180010c27  mov     [rbp+60h+var_78], 4
0x180010c2f  mov     [rbp+60h+var_88], 4
0x180010c37  mov     [rbp+60h+var_98], 4
0x180010c3f  mov     [rbp+60h+var_A8], 4
0x180010c47  mov     [rbp+60h+var_B8], 4
0x180010c4f  mov     [rbp+60h+var_C8], 4
0x180010c57  mov     [rbp+60h+var_D8], 0Ah
0x180010c5f  call    _tlgWriteTransfer_EventWriteTransfer
0x180010c64  mov     rcx, [rbp+60h+var_10]
0x180010c68  xor     rcx, rsp; StackCookie
0x180010c6b  call    __security_check_cookie
0x180010c70  add     rsp, 160h
0x180010c77  pop     rbp
0x180010c78  retn
```
