# PalmRejectionDelayZonePreview::RuntimeClassInitialize(Windows::UI::Composition::IVisual *,Windows::Foundation::Rect,bool)

- ea: `0x180057ba0`
- end: `0x180057c87`
- name: `?RuntimeClassInitialize@PalmRejectionDelayZonePreview@@UEAAJPEAUIVisual@Composition@UI@Windows@@URect@Foundation@5@_N@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057144`

## callees

- `0x1800062a0`
- `0x180057ba0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057be5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057c5f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057be5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180057c5f`
- `api-ms-win-rtcore-ntuser-private-l1-1-6!__imp_CreatePalmRejectionDelayZone` at `0x180057c4f`
- `api-ms-win-rtcore-ntuser-private-l1-1-6!__imp_CreatePalmRejectionDelayZone` at `0x180057c4f`

## pseudocode

```c
__int64 __fastcall PalmRejectionDelayZonePreview::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        float *a3,
        unsigned __int8 a4)
{
  float v4; // xmm6_4
  float v6; // xmm7_4
  unsigned int v8; // ebp
  float v10; // xmm6_4
  float v11; // xmm7_4
  float v12; // xmm0_4
  int v13; // eax
  float v14; // xmm0_4
  int PalmRejectionDelayZone; // eax
  unsigned int v16; // ebx
  _DWORD v18[4]; // [rsp+20h] [rbp-68h] BYREF

  v4 = a3[2];
  v6 = a3[3];
  v8 = a4;
  if ( !a2 )
    RoOriginateError(2147500035LL, 0);
  v10 = v4 + *a3;
  v11 = v6 + a3[1];
  v12 = *a3 + 0.5;
  *(_DWORD *)(a1 + 80) = 0;
  *(_BYTE *)(a1 + 84) = 0;
  v13 = (int)v12;
  v14 = a3[1];
  v18[0] = v13;
  v18[1] = (int)(float)(v14 + 0.5);
  v18[2] = (int)(float)(v10 + 0.5);
  v18[3] = (int)(float)(v11 + 0.5);
  PalmRejectionDelayZone = CreatePalmRejectionDelayZone(a2, v18, v8);
  v16 = PalmRejectionDelayZone;
  if ( PalmRejectionDelayZone < 0 )
    RoOriginateError((unsigned int)PalmRejectionDelayZone, 0);
  return v16;
}

```

## disassembly

```asm
0x180057ba0  push    rbx
0x180057ba2  push    rbp
0x180057ba3  push    rsi
0x180057ba4  push    rdi
0x180057ba5  sub     rsp, 68h
0x180057ba9  movaps  [rsp+88h+var_38], xmm6
0x180057bae  movaps  [rsp+88h+var_48], xmm7
0x180057bb3  mov     rax, cs:__security_cookie
0x180057bba  xor     rax, rsp
0x180057bbd  mov     [rsp+88h+var_58], rax
0x180057bc2  movss   xmm6, dword ptr [r8+8]
0x180057bc8  mov     rbx, r8
0x180057bcb  movss   xmm7, dword ptr [r8+0Ch]
0x180057bd1  mov     rdi, rdx
0x180057bd4  movzx   ebp, r9b
0x180057bd8  mov     rsi, rcx
0x180057bdb  test    rdx, rdx
0x180057bde  jnz     short loc_180057BEB
0x180057be0  mov     ecx, 80004003h
0x180057be5  call    cs:__imp_RoOriginateError
0x180057beb  movss   xmm1, cs:__real@3f000000
0x180057bf3  lea     r9, [rsi+50h]
0x180057bf7  movss   xmm0, dword ptr [rbx]
0x180057bfb  lea     rdx, [rsp+88h+var_68]
0x180057c00  addss   xmm6, dword ptr [rbx]
0x180057c04  addss   xmm7, dword ptr [rbx+4]
0x180057c09  addss   xmm0, xmm1
0x180057c0d  mov     dword ptr [r9], 0
0x180057c14  mov     r8d, ebp
0x180057c17  mov     byte ptr [rsi+54h], 0
0x180057c1b  mov     rcx, rdi
0x180057c1e  addss   xmm6, xmm1
0x180057c22  addss   xmm7, xmm1
0x180057c26  cvttss2si eax, xmm0
0x180057c2a  movss   xmm0, dword ptr [rbx+4]
0x180057c2f  mov     [rsp+88h+var_68], eax
0x180057c33  addss   xmm0, xmm1
0x180057c37  cvttss2si eax, xmm0
0x180057c3b  mov     [rsp+88h+var_64], eax
0x180057c3f  cvttss2si eax, xmm6
0x180057c43  mov     [rsp+88h+var_60], eax
0x180057c47  cvttss2si eax, xmm7
0x180057c4b  mov     [rsp+88h+var_5C], eax
0x180057c4f  call    cs:__imp_CreatePalmRejectionDelayZone
0x180057c55  mov     ebx, eax
0x180057c57  test    eax, eax
0x180057c59  jns     short loc_180057C65
0x180057c5b  xor     edx, edx
0x180057c5d  mov     ecx, eax
0x180057c5f  call    cs:__imp_RoOriginateError
0x180057c65  mov     eax, ebx
0x180057c67  mov     rcx, [rsp+88h+var_58]
0x180057c6c  xor     rcx, rsp; StackCookie
0x180057c6f  call    __security_check_cookie
0x180057c74  movaps  xmm6, [rsp+88h+var_38]
0x180057c79  movaps  xmm7, [rsp+88h+var_48]
0x180057c7e  add     rsp, 68h
0x180057c82  pop     rdi
0x180057c83  pop     rsi
0x180057c84  pop     rbp
0x180057c85  pop     rbx
0x180057c86  retn
```
