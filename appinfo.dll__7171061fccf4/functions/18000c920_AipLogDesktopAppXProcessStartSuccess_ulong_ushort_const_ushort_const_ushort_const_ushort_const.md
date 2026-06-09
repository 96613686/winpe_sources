# AipLogDesktopAppXProcessStartSuccess(ulong,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000c920`
- end: `0x18000cae1`
- name: `?AipLogDesktopAppXProcessStartSuccess@@YAXKPEBG000@Z`
- size: `449`
- prototype: `void __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ed98`

## callees

- `0x18000c920`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000c9b5`
- `msvcrt!wcsnlen` at `0x18000ca02`
- `msvcrt!wcsnlen` at `0x18000ca4f`
- `msvcrt!wcsnlen` at `0x18000ca7f`
- `msvcrt!wcsnlen` at `0x18000c9b5`
- `msvcrt!wcsnlen` at `0x18000ca02`
- `msvcrt!wcsnlen` at `0x18000ca4f`
- `msvcrt!wcsnlen` at `0x18000ca7f`
- `ntdll!EtwEventWrite` at `0x18000cabd`
- `ntdll!EtwEventWrite` at `0x18000cabd`

## pseudocode

```c
void __fastcall AipLogDesktopAppXProcessStartSuccess(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        wchar_t *Source)
{
  int v5; // ecx
  const wchar_t *v6; // rdi
  wchar_t v8; // dx
  __int64 v9; // xmm0_8
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int16 v18; // [rsp+20h] [rbp-61h] BYREF
  _QWORD v19[2]; // [rsp+30h] [rbp-51h] BYREF
  __int128 v20; // [rsp+40h] [rbp-41h]
  __int128 v21; // [rsp+50h] [rbp-31h]
  __int128 v22; // [rsp+60h] [rbp-21h]
  __int128 v23; // [rsp+70h] [rbp-11h]
  __int64 v24; // [rsp+80h] [rbp-1h] BYREF
  int v25; // [rsp+88h] [rbp+7h]
  wchar_t v26; // [rsp+8Ch] [rbp+Bh]
  int v27; // [rsp+E0h] [rbp+5Fh] BYREF

  v27 = a1;
  v5 = *(_DWORD *)L"L>";
  v6 = Source;
  v20 = 0;
  v8 = aNull_1[6];
  v22 = 0;
  v9 = *(_QWORD *)L"<NULL>";
  v24 = *(_QWORD *)L"<NULL>";
  v21 = 0;
  v12 = 7;
  v23 = 0;
  v19[0] = &v27;
  v19[1] = 4;
  v25 = *(_DWORD *)L"L>";
  v26 = aNull_1[6];
  if ( a2 )
  {
    v13 = wcsnlen(a2, 0x7Fu);
    v8 = aNull_1[6];
    v14 = v13 + 1;
    v5 = *(_DWORD *)L"L>";
    v9 = *(_QWORD *)L"<NULL>";
  }
  else
  {
    a2 = (const unsigned __int16 *)&v24;
    v14 = 7;
  }
  *(_QWORD *)&v20 = a2;
  *((_QWORD *)&v20 + 1) = (unsigned int)(2 * v14);
  v24 = v9;
  v25 = v5;
  v26 = v8;
  if ( a3 )
  {
    v15 = wcsnlen(a3, 0x104u);
    v8 = aNull_1[6];
    v16 = v15 + 1;
    v5 = *(_DWORD *)L"L>";
    v9 = *(_QWORD *)L"<NULL>";
  }
  else
  {
    a3 = (const unsigned __int16 *)&v24;
    v16 = 7;
  }
  *(_QWORD *)&v21 = a3;
  *((_QWORD *)&v21 + 1) = (unsigned int)(2 * v16);
  v24 = v9;
  v25 = v5;
  v26 = v8;
  if ( a4 )
    v12 = wcsnlen(a4, 0x82u) + 1;
  else
    a4 = (const unsigned __int16 *)&v24;
  *(_QWORD *)&v22 = a4;
  *((_QWORD *)&v22 + 1) = (unsigned int)(2 * v12);
  v18 = 0;
  if ( v6 )
  {
    v17 = wcsnlen(v6, 0x104u) + 1;
  }
  else
  {
    v6 = (const wchar_t *)&v18;
    v17 = 1;
  }
  *(_QWORD *)&v23 = v6;
  *((_QWORD *)&v23 + 1) = (unsigned int)(2 * v17);
  if ( g_EventRegHandleAppModelRuntime )
    EtwEventWrite(g_EventRegHandleAppModelRuntime, AppModelDesktopAppXProcessStartSuccess, 5, v19);
}

```

## disassembly

```asm
0x18000c920  mov     [rsp-8+arg_0], ecx
0x18000c924  push    rbp
0x18000c925  push    rbx
0x18000c926  push    rsi
0x18000c927  push    rdi
0x18000c928  push    r12
0x18000c92a  push    r14
0x18000c92c  push    r15
0x18000c92e  lea     rbp, [rsp-1Fh]
0x18000c933  sub     rsp, 0A0h
0x18000c93a  mov     rax, cs:__security_cookie
0x18000c941  xor     rax, rsp
0x18000c944  mov     [rbp+4Fh+var_40], rax
0x18000c948  mov     ecx, dword ptr cs:aNull_1+8; "L>"
0x18000c94e  lea     rax, [rbp+4Fh+arg_0]
0x18000c952  mov     rdi, [rbp+4Fh+Source]
0x18000c956  xorps   xmm0, xmm0
0x18000c959  mov     r15, rdx
0x18000c95c  movdqa  [rbp+4Fh+var_90], xmm0
0x18000c961  movzx   edx, word ptr cs:aNull_1+0Ch; ""
0x18000c968  xorps   xmm1, xmm1
0x18000c96b  movdqa  [rbp+4Fh+var_70], xmm0
0x18000c970  xor     r12d, r12d
0x18000c973  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000c97b  mov     rsi, r9
0x18000c97e  movsd   [rbp+4Fh+var_50], xmm0
0x18000c983  mov     r14, r8
0x18000c986  movdqa  [rbp+4Fh+var_80], xmm1
0x18000c98b  mov     ebx, 7
0x18000c990  movdqa  [rbp+4Fh+var_60], xmm1
0x18000c995  mov     [rbp+4Fh+var_A0], rax
0x18000c999  mov     [rbp+4Fh+var_98], 4
0x18000c9a1  mov     [rbp+4Fh+var_48], ecx
0x18000c9a4  mov     [rbp+4Fh+var_44], dx
0x18000c9a8  test    r15, r15
0x18000c9ab  jz      short loc_18000C9D5
0x18000c9ad  mov     edx, 7Fh; MaxCount
0x18000c9b2  mov     rcx, r15; Source
0x18000c9b5  call    cs:__imp_wcsnlen
0x18000c9bb  movzx   edx, word ptr cs:aNull_1+0Ch; ""
0x18000c9c2  inc     rax
0x18000c9c5  mov     ecx, dword ptr cs:aNull_1+8; "L>"
0x18000c9cb  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000c9d3  jmp     short loc_18000C9DC
0x18000c9d5  lea     r15, [rbp+4Fh+var_50]
0x18000c9d9  mov     rax, rbx
0x18000c9dc  add     eax, eax
0x18000c9de  mov     qword ptr [rbp+4Fh+var_90], r15
0x18000c9e2  mov     dword ptr [rbp+4Fh+var_90+8], eax
0x18000c9e5  mov     dword ptr [rbp+4Fh+var_90+0Ch], r12d
0x18000c9e9  movsd   [rbp+4Fh+var_50], xmm0
0x18000c9ee  mov     [rbp+4Fh+var_48], ecx
0x18000c9f1  mov     [rbp+4Fh+var_44], dx
0x18000c9f5  test    r14, r14
0x18000c9f8  jz      short loc_18000CA22
0x18000c9fa  mov     edx, 104h; MaxCount
0x18000c9ff  mov     rcx, r14; Source
0x18000ca02  call    cs:__imp_wcsnlen
0x18000ca08  movzx   edx, word ptr cs:aNull_1+0Ch; ""
0x18000ca0f  inc     rax
0x18000ca12  mov     ecx, dword ptr cs:aNull_1+8; "L>"
0x18000ca18  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000ca20  jmp     short loc_18000CA29
0x18000ca22  lea     r14, [rbp+4Fh+var_50]
0x18000ca26  mov     rax, rbx
0x18000ca29  add     eax, eax
0x18000ca2b  mov     qword ptr [rbp+4Fh+var_80], r14
0x18000ca2f  mov     dword ptr [rbp+4Fh+var_80+8], eax
0x18000ca32  mov     dword ptr [rbp+4Fh+var_80+0Ch], r12d
0x18000ca36  movsd   [rbp+4Fh+var_50], xmm0
0x18000ca3b  mov     [rbp+4Fh+var_48], ecx
0x18000ca3e  mov     [rbp+4Fh+var_44], dx
0x18000ca42  test    rsi, rsi
0x18000ca45  jz      short loc_18000CA5B
0x18000ca47  mov     edx, 82h; MaxCount
0x18000ca4c  mov     rcx, rsi; Source
0x18000ca4f  call    cs:__imp_wcsnlen
0x18000ca55  lea     rbx, [rax+1]
0x18000ca59  jmp     short loc_18000CA5F
0x18000ca5b  lea     rsi, [rbp+4Fh+var_50]
0x18000ca5f  mov     qword ptr [rbp+4Fh+var_70], rsi
0x18000ca63  lea     eax, [rbx+rbx]
0x18000ca66  mov     dword ptr [rbp+4Fh+var_70+8], eax
0x18000ca69  mov     dword ptr [rbp+4Fh+var_70+0Ch], r12d
0x18000ca6d  mov     [rbp+4Fh+var_B0], r12w
0x18000ca72  test    rdi, rdi
0x18000ca75  jz      short loc_18000CA8A
0x18000ca77  mov     edx, 104h; MaxCount
0x18000ca7c  mov     rcx, rdi; Source
0x18000ca7f  call    cs:__imp_wcsnlen
0x18000ca85  inc     rax
0x18000ca88  jmp     short loc_18000CA93
0x18000ca8a  lea     rdi, [rbp+4Fh+var_B0]
0x18000ca8e  mov     eax, 1
0x18000ca93  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18000ca9a  add     eax, eax
0x18000ca9c  mov     qword ptr [rbp+4Fh+var_60], rdi
0x18000caa0  mov     dword ptr [rbp+4Fh+var_60+8], eax
0x18000caa3  mov     dword ptr [rbp+4Fh+var_60+0Ch], r12d
0x18000caa7  test    rcx, rcx
0x18000caaa  jz      short loc_18000CAC3
0x18000caac  lea     r9, [rbp+4Fh+var_A0]
0x18000cab0  mov     r8d, 5
0x18000cab6  lea     rdx, AppModelDesktopAppXProcessStartSuccess
0x18000cabd  call    cs:__imp_EtwEventWrite
0x18000cac3  mov     rcx, [rbp+4Fh+var_40]
0x18000cac7  xor     rcx, rsp; StackCookie
0x18000caca  call    __security_check_cookie
0x18000cacf  add     rsp, 0A0h
0x18000cad6  pop     r15
0x18000cad8  pop     r14
0x18000cada  pop     r12
0x18000cadc  pop     rdi
0x18000cadd  pop     rsi
0x18000cade  pop     rbx
0x18000cadf  pop     rbp
0x18000cae0  retn
```
