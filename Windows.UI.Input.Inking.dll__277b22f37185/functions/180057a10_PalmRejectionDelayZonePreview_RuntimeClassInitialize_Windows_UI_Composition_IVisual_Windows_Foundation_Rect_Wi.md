# PalmRejectionDelayZonePreview::RuntimeClassInitialize(Windows::UI::Composition::IVisual *,Windows::Foundation::Rect,Windows::UI::Composition::IVisual *,Windows::Foundation::Rect)

- ea: `0x180057a10`
- end: `0x180057b8d`
- name: `?RuntimeClassInitialize@PalmRejectionDelayZonePreview@@UEAAJPEAUIVisual@Composition@UI@Windows@@URect@Foundation@5@01@Z`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005702c`

## callees

- `0x1800062a0`
- `0x180057a10`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057a7e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057b52`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057a7e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057b52`
- `api-ms-win-rtcore-ntuser-private-l1-1-8!__imp_CreatePalmRejectionDelayZoneWithViewportClipping` at `0x180057b42`
- `api-ms-win-rtcore-ntuser-private-l1-1-8!__imp_CreatePalmRejectionDelayZoneWithViewportClipping` at `0x180057b42`

## pseudocode

```c
__int64 __fastcall PalmRejectionDelayZonePreview::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        float *a3,
        __int64 a4,
        float *a5)
{
  float v6; // xmm6_4
  float v8; // xmm7_4
  float v11; // xmm8_4
  float v12; // xmm9_4
  float v13; // xmm1_4
  float v14; // xmm0_4
  float v15; // xmm8_4
  float v16; // xmm6_4
  float v17; // xmm7_4
  int v18; // eax
  float v19; // xmm0_4
  int v20; // eax
  float v21; // xmm0_4
  int v22; // eax
  unsigned int v23; // ebx
  _DWORD v25[4]; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v26[4]; // [rsp+40h] [rbp-88h] BYREF

  v6 = a3[2];
  v8 = a3[3];
  v11 = a5[2];
  v12 = a5[3];
  if ( !a2 || !a4 )
    RoOriginateError(2147500035LL, 0);
  v13 = a5[1];
  v14 = *a3 + 0.5;
  v15 = v11 + *a5;
  v16 = (float)(v6 + *a3) + 0.5;
  v17 = (float)(v8 + a3[1]) + 0.5;
  *(_DWORD *)(a1 + 80) = 0;
  v18 = (int)v14;
  *(_BYTE *)(a1 + 84) = 0;
  v19 = a3[1];
  v26[0] = v18;
  v20 = (int)(float)(v19 + 0.5);
  v21 = *a5;
  v26[1] = v20;
  v26[2] = (int)v16;
  v26[3] = (int)v17;
  v25[0] = (int)(float)(v21 + 0.5);
  v25[1] = (int)(float)(v13 + 0.5);
  v25[2] = (int)(float)(v15 + 0.5);
  v25[3] = (int)(float)((float)(v12 + v13) + 0.5);
  v22 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64, _DWORD *, int, __int64))CreatePalmRejectionDelayZoneWithViewportClipping)(
          a2,
          v26,
          a4,
          v25,
          1,
          a1 + 80);
  v23 = v22;
  if ( v22 < 0 )
    RoOriginateError((unsigned int)v22, 0);
  return v23;
}

```

## disassembly

```asm
0x180057a10  mov     rax, rsp
0x180057a13  push    rbx
0x180057a14  push    rbp
0x180057a15  push    rsi
0x180057a16  push    rdi
0x180057a17  push    r14
0x180057a19  sub     rsp, 0A0h
0x180057a20  movaps  xmmword ptr [rax-38h], xmm6
0x180057a24  movaps  xmmword ptr [rax-48h], xmm7
0x180057a28  movaps  xmmword ptr [rax-58h], xmm8
0x180057a2d  movaps  xmmword ptr [rax-68h], xmm9
0x180057a32  mov     rax, cs:__security_cookie
0x180057a39  xor     rax, rsp
0x180057a3c  mov     [rsp+0C8h+var_78], rax
0x180057a41  mov     rbx, [rsp+0C8h+arg_20]
0x180057a49  mov     rsi, r9
0x180057a4c  movss   xmm6, dword ptr [r8+8]
0x180057a52  mov     rdi, r8
0x180057a55  movss   xmm7, dword ptr [r8+0Ch]
0x180057a5b  mov     rbp, rdx
0x180057a5e  mov     r14, rcx
0x180057a61  movss   xmm8, dword ptr [rbx+8]
0x180057a67  movss   xmm9, dword ptr [rbx+0Ch]
0x180057a6d  test    rdx, rdx
0x180057a70  jz      short loc_180057A77
0x180057a72  test    r9, r9
0x180057a75  jnz     short loc_180057A84
0x180057a77  xor     edx, edx
0x180057a79  mov     ecx, 80004003h
0x180057a7e  call    cs:__imp_RoOriginateError
0x180057a84  movss   xmm2, cs:__real@3f000000
0x180057a8c  lea     rdx, [r14+50h]
0x180057a90  movss   xmm0, dword ptr [rdi]
0x180057a94  lea     r9, [rsp+0C8h+var_98]
0x180057a99  addss   xmm6, dword ptr [rdi]
0x180057a9d  addss   xmm7, dword ptr [rdi+4]
0x180057aa2  movss   xmm1, dword ptr [rbx+4]
0x180057aa7  addss   xmm0, xmm2
0x180057aab  addss   xmm8, dword ptr [rbx]
0x180057ab0  addss   xmm9, dword ptr [rbx+4]
0x180057ab6  addss   xmm6, xmm2
0x180057aba  mov     [rsp+0C8h+var_A0], rdx
0x180057abf  addss   xmm7, xmm2
0x180057ac3  mov     dword ptr [rdx], 0
0x180057ac9  cvttss2si eax, xmm0
0x180057acd  mov     r8, rsi
0x180057ad0  lea     rdx, [rsp+0C8h+var_88]
0x180057ad5  mov     rcx, rbp
0x180057ad8  mov     byte ptr [r14+54h], 0
0x180057add  mov     [rsp+0C8h+var_A8], 1
0x180057ae5  movss   xmm0, dword ptr [rdi+4]
0x180057aea  addss   xmm1, xmm2
0x180057aee  mov     [rsp+0C8h+var_88], eax
0x180057af2  addss   xmm0, xmm2
0x180057af6  addss   xmm8, xmm2
0x180057afb  addss   xmm9, xmm2
0x180057b00  cvttss2si eax, xmm0
0x180057b04  movss   xmm0, dword ptr [rbx]
0x180057b08  mov     [rsp+0C8h+var_84], eax
0x180057b0c  addss   xmm0, xmm2
0x180057b10  cvttss2si eax, xmm6
0x180057b14  mov     [rsp+0C8h+var_80], eax
0x180057b18  cvttss2si eax, xmm7
0x180057b1c  mov     [rsp+0C8h+var_7C], eax
0x180057b20  cvttss2si eax, xmm0
0x180057b24  mov     [rsp+0C8h+var_98], eax
0x180057b28  cvttss2si eax, xmm1
0x180057b2c  mov     [rsp+0C8h+var_94], eax
0x180057b30  cvttss2si eax, xmm8
0x180057b35  mov     [rsp+0C8h+var_90], eax
0x180057b39  cvttss2si eax, xmm9
0x180057b3e  mov     [rsp+0C8h+var_8C], eax
0x180057b42  call    cs:__imp_CreatePalmRejectionDelayZoneWithViewportClipping
0x180057b48  mov     ebx, eax
0x180057b4a  test    eax, eax
0x180057b4c  jns     short loc_180057B58
0x180057b4e  xor     edx, edx
0x180057b50  mov     ecx, eax
0x180057b52  call    cs:__imp_RoOriginateError
0x180057b58  mov     eax, ebx
0x180057b5a  mov     rcx, [rsp+0C8h+var_78]
0x180057b5f  xor     rcx, rsp; StackCookie
0x180057b62  call    __security_check_cookie
0x180057b67  lea     r11, [rsp+0C8h+var_28]
0x180057b6f  movaps  xmm6, xmmword ptr [r11-10h]
0x180057b74  movaps  xmm7, xmmword ptr [r11-20h]
0x180057b79  movaps  xmm8, xmmword ptr [r11-30h]
0x180057b7e  movaps  xmm9, xmmword ptr [r11-40h]
0x180057b83  mov     rsp, r11
0x180057b86  pop     r14
0x180057b88  pop     rdi
0x180057b89  pop     rsi
0x180057b8a  pop     rbp
0x180057b8b  pop     rbx
0x180057b8c  retn
```
