# AipLogDesktopAppXProcessStartSuccess(ulong,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000cf00`
- end: `0x18000d0cb`
- name: `?AipLogDesktopAppXProcessStartSuccess@@YAXKPEBG000@Z`
- size: `459`
- prototype: `void(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002a1d8`

## callees

- `0x18000cf00`
- `0x1800444e0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000cf84`
- `msvcrt!wcsnlen` at `0x18000cfda`
- `msvcrt!wcsnlen` at `0x18000d02d`
- `msvcrt!wcsnlen` at `0x18000d05c`
- `msvcrt!wcsnlen` at `0x18000cf84`
- `msvcrt!wcsnlen` at `0x18000cfda`
- `msvcrt!wcsnlen` at `0x18000d02d`
- `msvcrt!wcsnlen` at `0x18000d05c`
- `ntdll!EtwEventWrite` at `0x18000d0a0`
- `ntdll!EtwEventWrite` at `0x18000d0a0`

## pseudocode

```c
void __fastcall AipLogDesktopAppXProcessStartSuccess(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        wchar_t *Source)
{
  __int64 v5; // xmm0_8
  const wchar_t *v6; // rdi
  const unsigned __int16 *v7; // r15
  int v10; // edx
  wchar_t v12; // r8
  int v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const unsigned __int16 *v17; // r15
  int v18; // eax
  const unsigned __int16 *v19; // rsi
  int v20; // eax
  __int16 v21; // [rsp+20h] [rbp-61h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-51h] BYREF
  int v23; // [rsp+48h] [rbp-39h]
  int v24; // [rsp+4Ch] [rbp-35h]
  const unsigned __int16 *v25; // [rsp+50h] [rbp-31h]
  int v26; // [rsp+58h] [rbp-29h]
  int v27; // [rsp+5Ch] [rbp-25h]
  const unsigned __int16 *v28; // [rsp+60h] [rbp-21h]
  int v29; // [rsp+68h] [rbp-19h]
  int v30; // [rsp+6Ch] [rbp-15h]
  const wchar_t *v31; // [rsp+70h] [rbp-11h]
  int v32; // [rsp+78h] [rbp-9h]
  int v33; // [rsp+7Ch] [rbp-5h]
  __int64 v34; // [rsp+80h] [rbp-1h] BYREF
  int v35; // [rsp+88h] [rbp+7h]
  wchar_t v36; // [rsp+8Ch] [rbp+Bh]
  int v37; // [rsp+E0h] [rbp+5Fh] BYREF

  v37 = a1;
  v5 = *(_QWORD *)L"<NULL>";
  v6 = Source;
  v7 = (const unsigned __int16 *)&v34;
  v22[0] = &v37;
  v22[1] = 4;
  v10 = *(_DWORD *)L"L>";
  v12 = aNull_1[6];
  v34 = *(_QWORD *)L"<NULL>";
  v13 = 7;
  v35 = *(_DWORD *)L"L>";
  v14 = 7;
  v36 = aNull_1[6];
  if ( a2 )
  {
    v7 = a2;
    v15 = wcsnlen(a2, 0x7Fu);
    v12 = aNull_1[6];
    v14 = v15 + 1;
    v10 = *(_DWORD *)L"L>";
    v5 = *(_QWORD *)L"<NULL>";
  }
  v22[2] = v7;
  v23 = 2 * v14;
  v16 = 7;
  v24 = 0;
  v17 = (const unsigned __int16 *)&v34;
  v34 = v5;
  v35 = v10;
  v36 = v12;
  if ( a3 )
  {
    v17 = a3;
    v18 = wcsnlen(a3, 0x104u);
    v12 = aNull_1[6];
    v16 = v18 + 1;
    v10 = *(_DWORD *)L"L>";
    v5 = *(_QWORD *)L"<NULL>";
  }
  v25 = v17;
  v26 = 2 * v16;
  v19 = (const unsigned __int16 *)&v34;
  v27 = 0;
  v34 = v5;
  v35 = v10;
  v36 = v12;
  if ( a4 )
  {
    v19 = a4;
    v13 = wcsnlen(a4, 0x82u) + 1;
  }
  v28 = v19;
  v29 = 2 * v13;
  v30 = 0;
  v21 = 0;
  if ( v6 )
  {
    v20 = wcsnlen(v6, 0x104u) + 1;
  }
  else
  {
    v6 = (const wchar_t *)&v21;
    v20 = 1;
  }
  v31 = v6;
  v32 = 2 * v20;
  v33 = 0;
  if ( g_EventRegHandleAppModelRuntime )
    EtwEventWrite(g_EventRegHandleAppModelRuntime, &AppModelDesktopAppXProcessStartSuccess, 5, v22);
}

```

## disassembly

```asm
0x18000cf00  mov     [rsp-8+arg_0], ecx
0x18000cf04  push    rbp
0x18000cf05  push    rbx
0x18000cf06  push    rsi
0x18000cf07  push    rdi
0x18000cf08  push    r12
0x18000cf0a  push    r14
0x18000cf0c  push    r15
0x18000cf0e  lea     rbp, [rsp-1Fh]
0x18000cf13  sub     rsp, 0A0h
0x18000cf1a  mov     rax, cs:__security_cookie
0x18000cf21  xor     rax, rsp
0x18000cf24  mov     [rbp+4Fh+var_40], rax
0x18000cf28  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000cf30  lea     rax, [rbp+4Fh+arg_0]
0x18000cf34  mov     rdi, [rbp+4Fh+Source]
0x18000cf38  lea     r15, [rbp+4Fh+var_50]
0x18000cf3c  mov     r14, r9
0x18000cf3f  mov     [rbp+4Fh+var_A0], rax
0x18000cf43  mov     r9, rdx
0x18000cf46  mov     [rbp+4Fh+var_98], 4
0x18000cf4e  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000cf54  mov     rsi, r8
0x18000cf57  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000cf5f  xor     r12d, r12d
0x18000cf62  movsd   [rbp+4Fh+var_50], xmm0
0x18000cf67  mov     ebx, 7
0x18000cf6c  mov     [rbp+4Fh+var_48], edx
0x18000cf6f  mov     eax, ebx
0x18000cf71  mov     [rbp+4Fh+var_44], r8w
0x18000cf76  test    r9, r9
0x18000cf79  jz      short loc_18000CFA9
0x18000cf7b  lea     edx, [rbx+78h]; MaxCount
0x18000cf7e  mov     rcx, r9; Source
0x18000cf81  mov     r15, r9
0x18000cf84  call    cs:__imp_wcsnlen
0x18000cf8b  nop     dword ptr [rax+rax+00h]
0x18000cf90  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000cf98  inc     rax
0x18000cf9b  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000cfa1  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000cfa9  add     eax, eax
0x18000cfab  mov     [rbp+4Fh+var_90], r15
0x18000cfaf  mov     [rbp+4Fh+var_88], eax
0x18000cfb2  mov     rax, rbx
0x18000cfb5  mov     [rbp+4Fh+var_84], r12d
0x18000cfb9  lea     r15, [rbp+4Fh+var_50]
0x18000cfbd  movsd   [rbp+4Fh+var_50], xmm0
0x18000cfc2  mov     [rbp+4Fh+var_48], edx
0x18000cfc5  mov     [rbp+4Fh+var_44], r8w
0x18000cfca  test    rsi, rsi
0x18000cfcd  jz      short loc_18000CFFF
0x18000cfcf  mov     edx, 104h; MaxCount
0x18000cfd4  mov     rcx, rsi; Source
0x18000cfd7  mov     r15, rsi
0x18000cfda  call    cs:__imp_wcsnlen
0x18000cfe1  nop     dword ptr [rax+rax+00h]
0x18000cfe6  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000cfee  inc     rax
0x18000cff1  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000cff7  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000cfff  add     eax, eax
0x18000d001  mov     [rbp+4Fh+var_80], r15
0x18000d005  mov     [rbp+4Fh+var_78], eax
0x18000d008  lea     rsi, [rbp+4Fh+var_50]
0x18000d00c  mov     [rbp+4Fh+var_74], r12d
0x18000d010  movsd   [rbp+4Fh+var_50], xmm0
0x18000d015  mov     [rbp+4Fh+var_48], edx
0x18000d018  mov     [rbp+4Fh+var_44], r8w
0x18000d01d  test    r14, r14
0x18000d020  jz      short loc_18000D03D
0x18000d022  mov     edx, 82h; MaxCount
0x18000d027  mov     rcx, r14; Source
0x18000d02a  mov     rsi, r14
0x18000d02d  call    cs:__imp_wcsnlen
0x18000d034  nop     dword ptr [rax+rax+00h]
0x18000d039  lea     rbx, [rax+1]
0x18000d03d  add     ebx, ebx
0x18000d03f  mov     [rbp+4Fh+var_70], rsi
0x18000d043  mov     [rbp+4Fh+var_68], ebx
0x18000d046  mov     [rbp+4Fh+var_64], r12d
0x18000d04a  mov     [rbp+4Fh+var_B0], r12w
0x18000d04f  test    rdi, rdi
0x18000d052  jz      short loc_18000D06D
0x18000d054  mov     edx, 104h; MaxCount
0x18000d059  mov     rcx, rdi; Source
0x18000d05c  call    cs:__imp_wcsnlen
0x18000d063  nop     dword ptr [rax+rax+00h]
0x18000d068  inc     rax
0x18000d06b  jmp     short loc_18000D076
0x18000d06d  lea     rdi, [rbp+4Fh+var_B0]
0x18000d071  mov     eax, 1
0x18000d076  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18000d07d  add     eax, eax
0x18000d07f  mov     [rbp+4Fh+var_60], rdi
0x18000d083  mov     [rbp+4Fh+var_58], eax
0x18000d086  mov     [rbp+4Fh+var_54], r12d
0x18000d08a  test    rcx, rcx
0x18000d08d  jz      short loc_18000D0AC
0x18000d08f  lea     r9, [rbp+4Fh+var_A0]
0x18000d093  mov     r8d, 5
0x18000d099  lea     rdx, AppModelDesktopAppXProcessStartSuccess
0x18000d0a0  call    cs:__imp_EtwEventWrite
0x18000d0a7  nop     dword ptr [rax+rax+00h]
0x18000d0ac  mov     rcx, [rbp+4Fh+var_40]
0x18000d0b0  xor     rcx, rsp; StackCookie
0x18000d0b3  call    __security_check_cookie
0x18000d0b8  add     rsp, 0A0h
0x18000d0bf  pop     r15
0x18000d0c1  pop     r14
0x18000d0c3  pop     r12
0x18000d0c5  pop     rdi
0x18000d0c6  pop     rsi
0x18000d0c7  pop     rbx
0x18000d0c8  pop     rbp
0x18000d0c9  retn
```
