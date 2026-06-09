# AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)

- ea: `0x18000d290`
- end: `0x18000d3bd`
- name: `?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z`
- size: `301`
- prototype: `void __fastcall(wchar_t *Source, wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ce70`

## callees

- `0x18000d290`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000d2f9`
- `msvcrt!wcsnlen` at `0x18000d34e`
- `msvcrt!wcsnlen` at `0x18000d2f9`
- `msvcrt!wcsnlen` at `0x18000d34e`
- `ntdll!EtwEventWrite` at `0x18000d3a2`
- `ntdll!EtwEventWrite` at `0x18000d3a2`

## pseudocode

```c
void __fastcall AipLogDesktopAppXProcessLogPSMFlags(wchar_t *Source, wchar_t *a2, int a3)
{
  __int64 v3; // xmm1_8
  int v5; // ecx
  wchar_t v7; // dx
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  __int128 v11; // [rsp+20h] [rbp-68h] BYREF
  __int128 v12; // [rsp+30h] [rbp-58h]
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-38h] BYREF
  int v15; // [rsp+58h] [rbp-30h]
  wchar_t v16; // [rsp+5Ch] [rbp-2Ch]
  int v17; // [rsp+A0h] [rbp+18h] BYREF

  v17 = a3;
  v3 = *(_QWORD *)L"<NULL>";
  v14 = *(_QWORD *)L"<NULL>";
  v5 = *(_DWORD *)L"L>";
  v7 = aNull_1[6];
  v8 = 7;
  v16 = aNull_1[6];
  v15 = *(_DWORD *)L"L>";
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( Source )
  {
    v9 = wcsnlen(Source, 0x7Fu);
    v7 = aNull_1[6];
    v10 = v9 + 1;
    v5 = *(_DWORD *)L"L>";
    v3 = *(_QWORD *)L"<NULL>";
  }
  else
  {
    Source = (wchar_t *)&v14;
    v10 = 7;
  }
  *(_QWORD *)&v11 = Source;
  *((_QWORD *)&v11 + 1) = (unsigned int)(2 * v10);
  v14 = v3;
  v15 = v5;
  v16 = v7;
  if ( a2 )
    v8 = wcsnlen(a2, 0x82u) + 1;
  else
    a2 = (wchar_t *)&v14;
  *(_QWORD *)&v12 = a2;
  *((_QWORD *)&v12 + 1) = (unsigned int)(2 * v8);
  *(_QWORD *)&v13 = &v17;
  *((_QWORD *)&v13 + 1) = 4;
  if ( g_EventRegHandleAppModelRuntime )
    EtwEventWrite(g_EventRegHandleAppModelRuntime, AppModelDesktopAppXProcessLogPSMFlags, 3, &v11);
}

```

## disassembly

```asm
0x18000d290  mov     [rsp+arg_10], r8d
0x18000d295  push    rbx
0x18000d296  push    rsi
0x18000d297  push    rdi
0x18000d298  sub     rsp, 70h
0x18000d29c  mov     rax, cs:__security_cookie
0x18000d2a3  xor     rax, rsp
0x18000d2a6  mov     [rsp+88h+var_28], rax
0x18000d2ab  movsd   xmm1, qword ptr cs:aNull_1; "<NULL>"
0x18000d2b3  xorps   xmm0, xmm0
0x18000d2b6  mov     rsi, rcx
0x18000d2b9  movsd   [rsp+88h+var_38], xmm1
0x18000d2bf  mov     ecx, dword ptr cs:aNull_1+8; "L>"
0x18000d2c5  mov     rdi, rdx
0x18000d2c8  movzx   edx, word ptr cs:aNull_1+0Ch; ""
0x18000d2cf  mov     ebx, 7
0x18000d2d4  mov     [rsp+88h+var_2C], dx
0x18000d2d9  mov     [rsp+88h+var_30], ecx
0x18000d2dd  movups  [rsp+88h+var_68], xmm0
0x18000d2e2  movups  [rsp+88h+var_58], xmm0
0x18000d2e7  movups  [rsp+88h+var_48], xmm0
0x18000d2ec  test    rsi, rsi
0x18000d2ef  jz      short loc_18000D319
0x18000d2f1  mov     edx, 7Fh; MaxCount
0x18000d2f6  mov     rcx, rsi; Source
0x18000d2f9  call    cs:__imp_wcsnlen
0x18000d2ff  movzx   edx, word ptr cs:aNull_1+0Ch; ""
0x18000d306  inc     rax
0x18000d309  mov     ecx, dword ptr cs:aNull_1+8; "L>"
0x18000d30f  movsd   xmm1, qword ptr cs:aNull_1; "<NULL>"
0x18000d317  jmp     short loc_18000D321
0x18000d319  lea     rsi, [rsp+88h+var_38]
0x18000d31e  mov     rax, rbx
0x18000d321  add     eax, eax
0x18000d323  mov     qword ptr [rsp+88h+var_68], rsi
0x18000d328  xor     esi, esi
0x18000d32a  mov     dword ptr [rsp+88h+var_68+8], eax
0x18000d32e  mov     dword ptr [rsp+88h+var_68+0Ch], esi
0x18000d332  movsd   [rsp+88h+var_38], xmm1
0x18000d338  mov     [rsp+88h+var_30], ecx
0x18000d33c  mov     [rsp+88h+var_2C], dx
0x18000d341  test    rdi, rdi
0x18000d344  jz      short loc_18000D35A
0x18000d346  mov     edx, 82h; MaxCount
0x18000d34b  mov     rcx, rdi; Source
0x18000d34e  call    cs:__imp_wcsnlen
0x18000d354  lea     rbx, [rax+1]
0x18000d358  jmp     short loc_18000D35F
0x18000d35a  lea     rdi, [rsp+88h+var_38]
0x18000d35f  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18000d366  lea     rax, [rsp+88h+arg_10]
0x18000d36e  add     ebx, ebx
0x18000d370  mov     qword ptr [rsp+88h+var_58], rdi
0x18000d375  mov     dword ptr [rsp+88h+var_58+8], ebx
0x18000d379  mov     dword ptr [rsp+88h+var_58+0Ch], esi
0x18000d37d  mov     qword ptr [rsp+88h+var_48], rax
0x18000d382  mov     qword ptr [rsp+88h+var_48+8], 4
0x18000d38b  test    rcx, rcx
0x18000d38e  jz      short loc_18000D3A8
0x18000d390  lea     r9, [rsp+88h+var_68]
0x18000d395  mov     r8d, 3
0x18000d39b  lea     rdx, AppModelDesktopAppXProcessLogPSMFlags
0x18000d3a2  call    cs:__imp_EtwEventWrite
0x18000d3a8  mov     rcx, [rsp+88h+var_28]
0x18000d3ad  xor     rcx, rsp; StackCookie
0x18000d3b0  call    __security_check_cookie
0x18000d3b5  add     rsp, 70h
0x18000d3b9  pop     rdi
0x18000d3ba  pop     rsi
0x18000d3bb  pop     rbx
0x18000d3bc  retn
```
