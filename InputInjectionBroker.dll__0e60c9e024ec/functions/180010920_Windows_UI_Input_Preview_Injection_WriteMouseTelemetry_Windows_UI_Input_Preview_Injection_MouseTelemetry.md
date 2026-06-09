# Windows::UI::Input::Preview::Injection::WriteMouseTelemetry(Windows::UI::Input::Preview::Injection::MouseTelemetry &)

- ea: `0x180010920`
- end: `0x180010aa5`
- name: `?WriteMouseTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUMouseTelemetry@12345@@Z`
- size: `389`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection *__hidden this, struct Windows::UI::Input::Preview::Injection::MouseTelemetry *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009c10`

## callees

- `0x18000125c`
- `0x180010920`
- `0x180011460`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::WriteMouseTelemetry(
        Windows::UI::Input::Preview::Injection *this,
        struct Windows::UI::Input::Preview::Injection::MouseTelemetry *a2)
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
  _BYTE v11[32]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v12; // [rsp+80h] [rbp-80h]
  __int64 v13; // [rsp+88h] [rbp-78h]
  int *v14; // [rsp+90h] [rbp-70h]
  __int64 v15; // [rsp+98h] [rbp-68h]
  int *v16; // [rsp+A0h] [rbp-60h]
  __int64 v17; // [rsp+A8h] [rbp-58h]
  int *v18; // [rsp+B0h] [rbp-50h]
  __int64 v19; // [rsp+B8h] [rbp-48h]
  int *v20; // [rsp+C0h] [rbp-40h]
  __int64 v21; // [rsp+C8h] [rbp-38h]
  int *v22; // [rsp+D0h] [rbp-30h]
  __int64 v23; // [rsp+D8h] [rbp-28h]
  int *v24; // [rsp+E0h] [rbp-20h]
  __int64 v25; // [rsp+E8h] [rbp-18h]
  int *v26; // [rsp+F0h] [rbp-10h]
  __int64 v27; // [rsp+F8h] [rbp-8h]
  int *v28; // [rsp+100h] [rbp+0h]
  __int64 v29; // [rsp+108h] [rbp+8h]
  int *v30; // [rsp+110h] [rbp+10h]
  __int64 v31; // [rsp+118h] [rbp+18h]

  if ( (unsigned int)dword_180022000 > 5
    && (qword_180022010 & 0x400000000000LL) != 0
    && (qword_180022018 & 0x400000000000LL) == qword_180022018 )
  {
    v2 = *((_DWORD *)this + 8);
    v3 = *((_DWORD *)this + 7);
    v4 = *((_DWORD *)this + 6);
    v5 = *((_DWORD *)this + 5);
    v6 = *((_DWORD *)this + 2);
    v7 = *((_DWORD *)this + 4);
    v8 = *((_DWORD *)this + 1);
    v9 = *(_DWORD *)this;
    v10 = *((_DWORD *)this + 3);
    v30 = &v2;
    v28 = &v3;
    v26 = &v4;
    v24 = &v5;
    v22 = &v6;
    v20 = &v7;
    v18 = &v8;
    v16 = &v9;
    v14 = &v10;
    v12 = "InputMouse";
    v31 = 4;
    v29 = 4;
    v27 = 4;
    v25 = 4;
    v23 = 4;
    v21 = 4;
    v19 = 4;
    v17 = 4;
    v15 = 4;
    v13 = 11;
    tlgWriteTransfer_EventWriteTransfer(&dword_180022000, byte_18001EB81, 0, 0, 12, v11);
  }
}

```

## disassembly

```asm
0x180010920  push    rbp
0x180010922  lea     rbp, [rsp-30h]
0x180010927  sub     rsp, 130h
0x18001092e  mov     rax, cs:__security_cookie
0x180010935  xor     rax, rsp
0x180010938  mov     [rbp+30h+var_10], rax
0x18001093c  mov     eax, cs:dword_180022000
0x180010942  cmp     eax, 5
0x180010945  jbe     loc_180010A90
0x18001094b  mov     rdx, cs:qword_180022018
0x180010952  mov     r8, 400000000000h
0x18001095c  mov     rax, cs:qword_180022010
0x180010963  test    r8, rax
0x180010966  jz      loc_180010A90
0x18001096c  mov     rax, rdx
0x18001096f  and     rax, r8
0x180010972  cmp     rax, rdx
0x180010975  jnz     loc_180010A90
0x18001097b  mov     eax, [rcx+20h]
0x18001097e  lea     rdx, byte_18001EB81
0x180010985  mov     [rsp+130h+var_100], eax
0x180010989  xor     r9d, r9d
0x18001098c  mov     eax, [rcx+1Ch]
0x18001098f  xor     r8d, r8d
0x180010992  mov     [rsp+130h+var_FC], eax
0x180010996  mov     eax, [rcx+18h]
0x180010999  mov     [rsp+130h+var_F8], eax
0x18001099d  mov     eax, [rcx+14h]
0x1800109a0  mov     [rsp+130h+var_F4], eax
0x1800109a4  mov     eax, [rcx+8]
0x1800109a7  mov     [rsp+130h+var_F0], eax
0x1800109ab  mov     eax, [rcx+10h]
0x1800109ae  mov     [rsp+130h+var_EC], eax
0x1800109b2  mov     eax, [rcx+4]
0x1800109b5  mov     [rsp+130h+var_E8], eax
0x1800109b9  mov     eax, [rcx]
0x1800109bb  mov     [rsp+130h+var_E4], eax
0x1800109bf  mov     eax, [rcx+0Ch]
0x1800109c2  lea     rcx, dword_180022000
0x1800109c9  mov     [rsp+130h+var_E0], eax
0x1800109cd  lea     rax, [rsp+130h+var_100]
0x1800109d2  mov     [rbp+30h+var_20], rax
0x1800109d6  lea     rax, [rsp+130h+var_FC]
0x1800109db  mov     [rbp+30h+var_30], rax
0x1800109df  lea     rax, [rsp+130h+var_F8]
0x1800109e4  mov     [rbp+30h+var_40], rax
0x1800109e8  lea     rax, [rsp+130h+var_F4]
0x1800109ed  mov     [rbp+30h+var_50], rax
0x1800109f1  lea     rax, [rsp+130h+var_F0]
0x1800109f6  mov     [rbp+30h+var_60], rax
0x1800109fa  lea     rax, [rsp+130h+var_EC]
0x1800109ff  mov     [rbp+30h+var_70], rax
0x180010a03  lea     rax, [rsp+130h+var_E8]
0x180010a08  mov     [rbp+30h+var_80], rax
0x180010a0c  lea     rax, [rsp+130h+var_E4]
0x180010a11  mov     [rbp+30h+var_90], rax
0x180010a15  lea     rax, [rsp+130h+var_E0]
0x180010a1a  mov     [rbp+30h+var_A0], rax
0x180010a1e  lea     rax, aInputmouse; "InputMouse"
0x180010a25  mov     [rbp+30h+var_B0], rax
0x180010a29  lea     rax, [rsp+130h+var_D0]
0x180010a2e  mov     [rsp+130h+var_108], rax
0x180010a33  mov     [rsp+130h+var_110], 0Ch
0x180010a3b  mov     [rbp+30h+var_18], 4
0x180010a43  mov     [rbp+30h+var_28], 4
0x180010a4b  mov     [rbp+30h+var_38], 4
0x180010a53  mov     [rbp+30h+var_48], 4
0x180010a5b  mov     [rbp+30h+var_58], 4
0x180010a63  mov     [rbp+30h+var_68], 4
0x180010a6b  mov     [rbp+30h+var_78], 4
0x180010a73  mov     [rbp+30h+var_88], 4
0x180010a7b  mov     [rbp+30h+var_98], 4
0x180010a83  mov     [rbp+30h+var_A8], 0Bh
0x180010a8b  call    _tlgWriteTransfer_EventWriteTransfer
0x180010a90  mov     rcx, [rbp+30h+var_10]
0x180010a94  xor     rcx, rsp; StackCookie
0x180010a97  call    __security_check_cookie
0x180010a9c  add     rsp, 130h
0x180010aa3  pop     rbp
0x180010aa4  retn
```
