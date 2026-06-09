# AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)

- ea: `0x18000de30`
- end: `0x18000df68`
- name: `?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z`
- size: `312`
- prototype: `void(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180029110`

## callees

- `0x18000de30`
- `0x1800444e0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000de90`
- `msvcrt!wcsnlen` at `0x18000deeb`
- `msvcrt!wcsnlen` at `0x18000de90`
- `msvcrt!wcsnlen` at `0x18000deeb`
- `ntdll!EtwEventWrite` at `0x18000df3e`
- `ntdll!EtwEventWrite` at `0x18000df3e`

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
0x18000de30  mov     [rsp+arg_18], rbx
0x18000de35  mov     [rsp+arg_10], r8d
0x18000de3a  push    rbp
0x18000de3b  push    rsi
0x18000de3c  push    rdi
0x18000de3d  sub     rsp, 70h
0x18000de41  mov     rax, cs:__security_cookie
0x18000de48  xor     rax, rsp
0x18000de4b  mov     [rsp+88h+var_28], rax
0x18000de50  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000de58  mov     rdi, rdx
0x18000de5b  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000de63  mov     ebx, 7
0x18000de68  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000de6e  mov     eax, ebx
0x18000de70  movsd   [rsp+88h+var_38], xmm0
0x18000de76  lea     rsi, [rsp+88h+var_38]
0x18000de7b  mov     [rsp+88h+var_30], edx
0x18000de7f  mov     [rsp+88h+var_2C], r8w
0x18000de85  test    rcx, rcx
0x18000de88  jz      short loc_18000DEB5
0x18000de8a  lea     edx, [rbx+78h]; MaxCount
0x18000de8d  mov     rsi, rcx
0x18000de90  call    cs:__imp_wcsnlen
0x18000de97  nop     dword ptr [rax+rax+00h]
0x18000de9c  movzx   r8d, word ptr cs:aNull_1+0Ch; ""
0x18000dea4  inc     rax
0x18000dea7  mov     edx, dword ptr cs:aNull_1+8; "L>"
0x18000dead  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000deb5  add     eax, eax
0x18000deb7  mov     [rsp+88h+var_68], rsi
0x18000debc  xor     ebp, ebp
0x18000debe  mov     [rsp+88h+var_60], eax
0x18000dec2  mov     [rsp+88h+var_5C], ebp
0x18000dec6  lea     rsi, [rsp+88h+var_38]
0x18000decb  movsd   [rsp+88h+var_38], xmm0
0x18000ded1  mov     [rsp+88h+var_30], edx
0x18000ded5  mov     [rsp+88h+var_2C], r8w
0x18000dedb  test    rdi, rdi
0x18000dede  jz      short loc_18000DEFB
0x18000dee0  mov     edx, 82h; MaxCount
0x18000dee5  mov     rcx, rdi; Source
0x18000dee8  mov     rsi, rdi
0x18000deeb  call    cs:__imp_wcsnlen
0x18000def2  nop     dword ptr [rax+rax+00h]
0x18000def7  lea     rbx, [rax+1]
0x18000defb  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18000df02  lea     rax, [rsp+88h+arg_10]
0x18000df0a  add     ebx, ebx
0x18000df0c  mov     [rsp+88h+var_58], rsi
0x18000df11  mov     [rsp+88h+var_50], ebx
0x18000df15  mov     [rsp+88h+var_4C], ebp
0x18000df19  mov     [rsp+88h+var_48], rax
0x18000df1e  mov     [rsp+88h+var_40], 4
0x18000df27  test    rcx, rcx
0x18000df2a  jz      short loc_18000DF4A
0x18000df2c  lea     r9, [rsp+88h+var_68]
0x18000df31  mov     r8d, 3
0x18000df37  lea     rdx, AppModelDesktopAppXProcessLogPSMFlags
0x18000df3e  call    cs:__imp_EtwEventWrite
0x18000df45  nop     dword ptr [rax+rax+00h]
0x18000df4a  mov     rcx, [rsp+88h+var_28]
0x18000df4f  xor     rcx, rsp; StackCookie
0x18000df52  call    __security_check_cookie
0x18000df57  mov     rbx, [rsp+88h+arg_18]
0x18000df5f  add     rsp, 70h
0x18000df63  pop     rdi
0x18000df64  pop     rsi
0x18000df65  pop     rbp
0x18000df66  retn
```
