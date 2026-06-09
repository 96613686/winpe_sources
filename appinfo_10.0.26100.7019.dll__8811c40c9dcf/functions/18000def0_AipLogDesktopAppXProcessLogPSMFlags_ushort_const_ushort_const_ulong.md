# AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)

- ea: `0x18000def0`
- end: `0x18000e028`
- name: `?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z`
- size: `312`
- prototype: `void(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002a750`

## callees

- `0x18000def0`
- `0x180042950`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000df50`
- `msvcrt!wcsnlen` at `0x18000dfab`
- `msvcrt!wcsnlen` at `0x18000df50`
- `msvcrt!wcsnlen` at `0x18000dfab`
- `ntdll!EtwEventWrite` at `0x18000dffe`
- `ntdll!EtwEventWrite` at `0x18000dffe`

## pseudocode

```c
void __fastcall AipLogDesktopAppXProcessLogPSMFlags(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // xmm0_8
  wchar_t v5; // r8
  int v6; // ebx
  int v7; // edx
  int v8; // eax
  const unsigned __int16 *v9; // rsi
  int v10; // eax
  const unsigned __int16 *v11; // rsi
  const unsigned __int16 *v12; // [rsp+20h] [rbp-68h] BYREF
  int v13; // [rsp+28h] [rbp-60h]
  int v14; // [rsp+2Ch] [rbp-5Ch]
  const unsigned __int16 *v15; // [rsp+30h] [rbp-58h]
  int v16; // [rsp+38h] [rbp-50h]
  int v17; // [rsp+3Ch] [rbp-4Ch]
  int *v18; // [rsp+40h] [rbp-48h]
  __int64 v19; // [rsp+48h] [rbp-40h]
  __int64 v20; // [rsp+50h] [rbp-38h] BYREF
  int v21; // [rsp+58h] [rbp-30h]
  wchar_t v22; // [rsp+5Ch] [rbp-2Ch]
  int v23; // [rsp+A0h] [rbp+18h] BYREF

  v23 = a3;
  v3 = *(_QWORD *)L"<NULL>";
  v5 = aNull_1[6];
  v6 = 7;
  v7 = *(_DWORD *)L"L>";
  v8 = 7;
  v20 = *(_QWORD *)L"<NULL>";
  v9 = (const unsigned __int16 *)&v20;
  v21 = *(_DWORD *)L"L>";
  v22 = aNull_1[6];
  if ( a1 )
  {
    v9 = a1;
    v10 = wcsnlen(a1, 0x7Fu);
    v5 = aNull_1[6];
    v8 = v10 + 1;
    v7 = *(_DWORD *)L"L>";
    v3 = *(_QWORD *)L"<NULL>";
  }
  v12 = v9;
  v13 = 2 * v8;
  v14 = 0;
  v11 = (const unsigned __int16 *)&v20;
  v20 = v3;
  v21 = v7;
  v22 = v5;
  if ( a2 )
  {
    v11 = a2;
    v6 = wcsnlen(a2, 0x82u) + 1;
  }
  v15 = v11;
  v16 = 2 * v6;
  v17 = 0;
  v18 = &v23;
  v19 = 4;
  if ( g_EventRegHandleAppModelRuntime )
    EtwEventWrite(g_EventRegHandleAppModelRuntime, &AppModelDesktopAppXProcessLogPSMFlags, 3, &v12);
}

```

## disassembly

```asm
0x18000def0  mov     [rsp+arg_18], rbx
0x18000def5  mov     [rsp+arg_10], r8d
0x18000defa  push    rbp
0x18000defb  push    rsi
0x18000defc  push    rdi
0x18000defd  sub     rsp, 70h
0x18000df01  mov     rax, cs:__security_cookie
0x18000df08  xor     rax, rsp
0x18000df0b  mov     [rsp+88h+var_28], rax
0x18000df10  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000df18  mov     rdi, rdx
0x18000df1b  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000df23  mov     ebx, 7
0x18000df28  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000df2e  mov     eax, ebx
0x18000df30  movsd   [rsp+88h+var_38], xmm0
0x18000df36  lea     rsi, [rsp+88h+var_38]
0x18000df3b  mov     [rsp+88h+var_30], edx
0x18000df3f  mov     [rsp+88h+var_2C], r8w
0x18000df45  test    rcx, rcx
0x18000df48  jz      short loc_18000DF75
0x18000df4a  lea     edx, [rbx+78h]; MaxCount
0x18000df4d  mov     rsi, rcx
0x18000df50  call    cs:__imp_wcsnlen
0x18000df57  nop     dword ptr [rax+rax+00h]
0x18000df5c  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000df64  inc     rax
0x18000df67  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000df6d  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000df75  add     eax, eax
0x18000df77  mov     [rsp+88h+var_68], rsi
0x18000df7c  xor     ebp, ebp
0x18000df7e  mov     [rsp+88h+var_60], eax
0x18000df82  mov     [rsp+88h+var_5C], ebp
0x18000df86  lea     rsi, [rsp+88h+var_38]
0x18000df8b  movsd   [rsp+88h+var_38], xmm0
0x18000df91  mov     [rsp+88h+var_30], edx
0x18000df95  mov     [rsp+88h+var_2C], r8w
0x18000df9b  test    rdi, rdi
0x18000df9e  jz      short loc_18000DFBB
0x18000dfa0  mov     edx, 82h; MaxCount
0x18000dfa5  mov     rcx, rdi; Source
0x18000dfa8  mov     rsi, rdi
0x18000dfab  call    cs:__imp_wcsnlen
0x18000dfb2  nop     dword ptr [rax+rax+00h]
0x18000dfb7  lea     rbx, [rax+1]
0x18000dfbb  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18000dfc2  lea     rax, [rsp+88h+arg_10]
0x18000dfca  add     ebx, ebx
0x18000dfcc  mov     [rsp+88h+var_58], rsi
0x18000dfd1  mov     [rsp+88h+var_50], ebx
0x18000dfd5  mov     [rsp+88h+var_4C], ebp
0x18000dfd9  mov     [rsp+88h+var_48], rax
0x18000dfde  mov     [rsp+88h+var_40], 4
0x18000dfe7  test    rcx, rcx
0x18000dfea  jz      short loc_18000E00A
0x18000dfec  lea     r9, [rsp+88h+var_68]
0x18000dff1  mov     r8d, 3
0x18000dff7  lea     rdx, AppModelDesktopAppXProcessLogPSMFlags
0x18000dffe  call    cs:__imp_EtwEventWrite
0x18000e005  nop     dword ptr [rax+rax+00h]
0x18000e00a  mov     rcx, [rsp+88h+var_28]
0x18000e00f  xor     rcx, rsp; StackCookie
0x18000e012  call    __security_check_cookie
0x18000e017  mov     rbx, [rsp+88h+arg_18]
0x18000e01f  add     rsp, 70h
0x18000e023  pop     rdi
0x18000e024  pop     rsi
0x18000e025  pop     rbp
0x18000e026  retn
```
