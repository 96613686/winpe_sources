# _anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry

- ea: `0x140010e44`
- end: `0x140010ffa`
- name: `_anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry`
- size: `438`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000fd08`

## callees

- `0x140004890`
- `0x14000abd8`
- `0x14000c220`
- `0x14000c2bc`
- `0x140010e44`
- `0x140011100`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140010eab`
- `ADVAPI32!RegOpenKeyExW` at `0x140010eab`
- `ADVAPI32!RegCloseKey` at `0x140010fcc`
- `ADVAPI32!RegCloseKey` at `0x140010fcc`
- `KERNEL32!RegSetValueExW` at `0x140010f44`
- `KERNEL32!RegSetValueExW` at `0x140010f44`

## string_xrefs

- `0x140010e6f`: ``anonymous-namespace'::WriteAccessibilityConfigStringListToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::WriteAccessibilityConfigStringListToRegistry(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        BYTE *lpData)
{
  HKEY v8; // rsi
  int v9; // eax
  int v10; // r8d
  const wchar_t *v11; // r14
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // rax
  unsigned int v15; // ebx
  HKEY hKeya; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-30h] BYREF
  HKEY v19; // [rsp+48h] [rbp-20h]
  __int64 v20; // [rsp+50h] [rbp-18h]
  __int64 v21; // [rsp+58h] [rbp-10h]
  int v22; // [rsp+B0h] [rbp+48h] BYREF

  v22 = 0;
  _Trace::_Trace((_Trace *)v18, L"`anonymous-namespace'::WriteAccessibilityConfigStringListToRegistry", &v22);
  v8 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  hKeya = 0;
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20006u, &hKeya);
  if ( !v9 )
    v8 = hKeya;
  v19 = v8;
  v11 = L"HKLM";
  if ( hKey != HKEY_LOCAL_MACHINE )
    v11 = L"HKCU";
  if ( v9 )
  {
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v22 = v9;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v13 = 22;
LABEL_20:
      WPP_SF_SSd(v12[2], v13, v10, (_DWORD)v11, (__int64)lpSubKey, v9);
    }
  }
  else
  {
    if ( !lpData )
      ATL::AtlThrowImpl(-2147467259);
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&lpData[2 * v14] );
    v9 = RegSetValueExW(v8, lpValueName, 0, 1u, lpData, 2 * v14 + 2);
    if ( v9 )
    {
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v22 = v9;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v13 = 23;
        goto LABEL_20;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, lpData);
    }
  }
  v15 = v22;
  if ( v8 )
    RegCloseKey(v8);
  _Trace::~_Trace((_Trace *)v18);
  return v15;
}

```

## disassembly

```asm
0x140010e44  push    rbp
0x140010e46  push    rbx
0x140010e47  push    rsi
0x140010e48  push    rdi
0x140010e49  push    r12
0x140010e4b  push    r13
0x140010e4d  push    r14
0x140010e4f  push    r15
0x140010e51  mov     rbp, rsp
0x140010e54  sub     rsp, 68h
0x140010e58  mov     rdi, r9
0x140010e5b  mov     r12, r8
0x140010e5e  mov     r15, rdx
0x140010e61  mov     rbx, rcx
0x140010e64  xor     r13d, r13d
0x140010e67  mov     [rbp+arg_0], r13d
0x140010e6b  lea     r8, [rbp+arg_0]; int *
0x140010e6f  lea     rdx, aAnonymousNames; "`anonymous-namespace'::WriteAccessibili"...
0x140010e76  lea     rcx, [rbp+var_30]; this
0x140010e7a  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x140010e7f  nop
0x140010e80  mov     esi, r13d
0x140010e83  mov     [rbp+var_20], r13
0x140010e87  mov     [rbp+var_18], r13
0x140010e8b  mov     [rbp+var_10], r13
0x140010e8f  mov     [rbp+hKey], r13
0x140010e93  lea     rax, [rbp+hKey]
0x140010e97  mov     [rsp+68h+phkResult], rax; phkResult
0x140010e9c  mov     r9d, 20006h; samDesired
0x140010ea2  xor     r8d, r8d; ulOptions
0x140010ea5  mov     rdx, r15; lpSubKey
0x140010ea8  mov     rcx, rbx; hKey
0x140010eab  call    cs:__imp_RegOpenKeyExW
0x140010eb1  test    eax, eax
0x140010eb3  cmovz   rsi, [rbp+hKey]
0x140010eb8  mov     [rbp+var_20], rsi
0x140010ebc  lea     rcx, aHkcu; "HKCU"
0x140010ec3  lea     r14, aHklm; "HKLM"
0x140010eca  cmp     rbx, 0FFFFFFFF80000002h
0x140010ed1  cmovnz  r14, rcx
0x140010ed5  test    eax, eax
0x140010ed7  jz      short loc_140010F0E
0x140010ed9  jle     short loc_140010EE3
0x140010edb  movzx   eax, ax
0x140010ede  or      eax, 80070000h
0x140010ee3  mov     [rbp+arg_0], eax
0x140010ee6  lea     rdx, WPP_GLOBAL_Control
0x140010eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ef4  cmp     rcx, rdx
0x140010ef7  jz      loc_140010FC1
0x140010efd  test    byte ptr [rcx+1Ch], 8
0x140010f01  jz      loc_140010FC1
0x140010f07  mov     edx, 16h
0x140010f0c  jmp     short loc_140010F79
0x140010f0e  test    rdi, rdi
0x140010f11  jz      loc_140010FEF
0x140010f17  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010f1b  inc     rax
0x140010f1e  cmp     [rdi+rax*2], r13w
0x140010f23  jnz     short loc_140010F1B
0x140010f25  lea     eax, ds:2[rax*2]
0x140010f2c  mov     [rsp+68h+cbData], eax; cbData
0x140010f30  mov     [rsp+68h+phkResult], rdi; lpData
0x140010f35  mov     r9d, 1; dwType
0x140010f3b  xor     r8d, r8d; Reserved
0x140010f3e  mov     rdx, r12; lpValueName
0x140010f41  mov     rcx, rsi; hKey
0x140010f44  call    cs:__imp_RegSetValueExW
0x140010f4a  test    eax, eax
0x140010f4c  jz      short loc_140010F90
0x140010f4e  jle     short loc_140010F58
0x140010f50  movzx   eax, ax
0x140010f53  or      eax, 80070000h
0x140010f58  mov     [rbp+arg_0], eax
0x140010f5b  lea     rdx, WPP_GLOBAL_Control
0x140010f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f69  cmp     rcx, rdx
0x140010f6c  jz      short loc_140010FC1
0x140010f6e  test    byte ptr [rcx+1Ch], 8
0x140010f72  jz      short loc_140010FC1
0x140010f74  mov     edx, 17h
0x140010f79  mov     [rsp+68h+cbData], eax
0x140010f7d  mov     [rsp+68h+phkResult], r15
0x140010f82  mov     r9, r14
0x140010f85  mov     rcx, [rcx+10h]
0x140010f89  call    WPP_SF_SSd
0x140010f8e  jmp     short loc_140010FC1
0x140010f90  lea     rdx, WPP_GLOBAL_Control
0x140010f97  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f9e  cmp     rcx, rdx
0x140010fa1  jz      short loc_140010FC1
0x140010fa3  test    byte ptr [rcx+1Ch], 10h
0x140010fa7  jz      short loc_140010FC1
0x140010fa9  mov     edx, 18h
0x140010fae  mov     r9, rdi
0x140010fb1  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x140010fb8  mov     rcx, [rcx+10h]
0x140010fbc  call    WPP_SF_S
0x140010fc1  mov     ebx, [rbp+arg_0]
0x140010fc4  test    rsi, rsi
0x140010fc7  jz      short loc_140010FD3
0x140010fc9  mov     rcx, rsi; hKey
0x140010fcc  call    cs:__imp_RegCloseKey
0x140010fd2  nop
0x140010fd3  lea     rcx, [rbp+var_30]; this
0x140010fd7  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x140010fdc  mov     eax, ebx
0x140010fde  add     rsp, 68h
0x140010fe2  pop     r15
0x140010fe4  pop     r14
0x140010fe6  pop     r13
0x140010fe8  pop     r12
0x140010fea  pop     rdi
0x140010feb  pop     rsi
0x140010fec  pop     rbx
0x140010fed  pop     rbp
0x140010fee  retn
0x140010fef  mov     ecx, 80004005h; int
0x140010ff4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
