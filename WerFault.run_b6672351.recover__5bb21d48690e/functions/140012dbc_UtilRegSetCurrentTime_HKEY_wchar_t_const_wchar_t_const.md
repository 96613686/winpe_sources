# UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)

- ea: `0x140012dbc`
- end: `0x140012fa7`
- name: `?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z`
- size: `491`
- prototype: `__int64 __fastcall(HKEY hKey, const wchar_t *, const wchar_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002b158`
- `0x14004dba8`
- `0x140050bf4`
- `0x140055b1c`
- `0x140057568`

## callees

- `0x140012dbc`
- `0x140014ee4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012ea2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012f86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012e29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012ea2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012f86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012f32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012f32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012e7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140012e7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140012efa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140012efa`

## pseudocode

```c
__int64 __fastcall UtilRegSetCurrentTime(HKEY hKey, const wchar_t *a2, const wchar_t *a3)
{
  HKEY v5; // rcx
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  unsigned int v9; // ebx
  CUserModeHangReport *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY *p_hKeya; // [rsp+60h] [rbp-10h]
  struct _FILETIME Data; // [rsp+88h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+98h] [rbp+28h] BYREF

  v5 = 0;
  hKeya = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  if ( __PAIR128__((unsigned __int64)hKey, 0) == (unsigned __int64)a2 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
      v5 = hKeya;
    }
    if ( v5 )
      RegCloseKey(v5);
    return 2147942487LL;
  }
  if ( a2 )
  {
    p_hKeya = &hKeya;
    phkResult = 0;
    v7 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x20106u, 0, &phkResult, 0);
    if ( phkResult )
    {
      v8 = *p_hKeya;
      *p_hKeya = phkResult;
      if ( v8 )
        RegCloseKey(v8);
    }
    if ( v7 )
    {
      v9 = -2147467259;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_26;
      }
      v11 = 88;
      goto LABEL_17;
    }
    hKey = hKeya;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Data = SystemTimeAsFileTime;
  v12 = RegSetValueExW(hKey, a3, 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( !v12 )
  {
    v9 = 0;
    goto LABEL_26;
  }
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v9 = v12;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    goto LABEL_26;
  }
  v11 = 89;
LABEL_17:
  WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
LABEL_26:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x140012dbc  mov     [rsp-8+arg_0], rbx
0x140012dc1  mov     [rsp-8+arg_10], rdi
0x140012dc6  push    rbp
0x140012dc7  mov     rbp, rsp
0x140012dca  sub     rsp, 70h
0x140012dce  mov     rbx, rcx
0x140012dd1  mov     rdi, r8
0x140012dd4  xor     ecx, ecx
0x140012dd6  mov     [rbp+hKey], rcx
0x140012dda  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x140012dde  mov     [rbp+Data], rcx
0x140012de2  test    rdx, rdx
0x140012de5  jnz     short loc_140012DEC
0x140012de7  test    rbx, rbx
0x140012dea  jz      short loc_140012DF1
0x140012dec  test    rdi, rdi
0x140012def  jnz     short loc_140012E3F
0x140012df1  mov     r9, cs:WPP_GLOBAL_Control
0x140012df8  lea     rax, WPP_GLOBAL_Control
0x140012dff  cmp     r9, rax
0x140012e02  jz      short loc_140012E24
0x140012e04  test    byte ptr [r9+1Ch], 1
0x140012e09  jz      short loc_140012E24
0x140012e0b  mov     rcx, [r9+10h]
0x140012e0f  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140012e16  mov     edx, 57h ; 'W'
0x140012e1b  call    WPP_SF_
0x140012e20  mov     rcx, [rbp+hKey]; hKey
0x140012e24  test    rcx, rcx
0x140012e27  jz      short loc_140012E35
0x140012e29  call    cs:__imp_RegCloseKey
0x140012e30  nop     dword ptr [rax+rax+00h]
0x140012e35  mov     eax, 80070057h
0x140012e3a  jmp     loc_140012F94
0x140012e3f  test    rdx, rdx
0x140012e42  jz      loc_140012EF6
0x140012e48  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x140012e4d  lea     rax, [rbp+hKey]
0x140012e51  mov     [rbp+var_10], rax
0x140012e55  xor     r9d, r9d; lpClass
0x140012e58  lea     rax, [rbp+var_18]
0x140012e5c  mov     [rbp+var_18], rcx
0x140012e60  mov     [rsp+70h+phkResult], rax; phkResult
0x140012e65  xor     r8d, r8d; Reserved
0x140012e68  mov     [rsp+70h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x140012e6d  mov     [rsp+70h+samDesired], 20106h; samDesired
0x140012e75  mov     [rsp+70h+dwOptions], ecx; dwOptions
0x140012e79  mov     rcx, rbx; hKey
0x140012e7c  call    cs:__imp_RegCreateKeyExW
0x140012e83  nop     dword ptr [rax+rax+00h]
0x140012e88  mov     r8, [rbp+var_18]
0x140012e8c  mov     ebx, eax
0x140012e8e  test    r8, r8
0x140012e91  jz      short loc_140012EAE
0x140012e93  mov     rdx, [rbp+var_10]
0x140012e97  mov     rcx, [rdx]; hKey
0x140012e9a  mov     [rdx], r8
0x140012e9d  test    rcx, rcx
0x140012ea0  jz      short loc_140012EAE
0x140012ea2  call    cs:__imp_RegCloseKey
0x140012ea9  nop     dword ptr [rax+rax+00h]
0x140012eae  test    ebx, ebx
0x140012eb0  jz      short loc_140012EF2
0x140012eb2  mov     ebx, 80004005h
0x140012eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ebe  lea     rax, WPP_GLOBAL_Control
0x140012ec5  cmp     rcx, rax
0x140012ec8  jz      loc_140012F7D
0x140012ece  test    byte ptr [rcx+1Ch], 1
0x140012ed2  jz      loc_140012F7D
0x140012ed8  mov     edx, 58h ; 'X'
0x140012edd  mov     rcx, [rcx+10h]
0x140012ee1  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140012ee8  call    WPP_SF_
0x140012eed  jmp     loc_140012F7D
0x140012ef2  mov     rbx, [rbp+hKey]
0x140012ef6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140012efa  call    cs:__imp_GetSystemTimeAsFileTime
0x140012f01  nop     dword ptr [rax+rax+00h]
0x140012f06  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140012f09  mov     r9d, 0Bh; dwType
0x140012f0f  mov     dword ptr [rbp+Data+4], eax
0x140012f12  xor     r8d, r8d; Reserved
0x140012f15  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140012f18  mov     rdx, rdi; lpValueName
0x140012f1b  mov     dword ptr [rbp+Data], eax
0x140012f1e  mov     rcx, rbx; hKey
0x140012f21  lea     rax, [rbp+Data]
0x140012f25  mov     [rsp+70h+samDesired], 8; cbData
0x140012f2d  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x140012f32  call    cs:__imp_RegSetValueExW
0x140012f39  nop     dword ptr [rax+rax+00h]
0x140012f3e  test    eax, eax
0x140012f40  jz      short loc_140012F7B
0x140012f42  jle     short loc_140012F4C
0x140012f44  movzx   eax, ax
0x140012f47  or      eax, 80070000h
0x140012f4c  mov     ebx, 80004005h
0x140012f51  test    eax, eax
0x140012f53  cmovns  eax, ebx
0x140012f56  mov     ebx, eax
0x140012f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f5f  lea     rax, WPP_GLOBAL_Control
0x140012f66  cmp     rcx, rax
0x140012f69  jz      short loc_140012F7D
0x140012f6b  test    byte ptr [rcx+1Ch], 1
0x140012f6f  jz      short loc_140012F7D
0x140012f71  mov     edx, 59h ; 'Y'
0x140012f76  jmp     loc_140012EDD
0x140012f7b  xor     ebx, ebx
0x140012f7d  mov     rcx, [rbp+hKey]; hKey
0x140012f81  test    rcx, rcx
0x140012f84  jz      short loc_140012F92
0x140012f86  call    cs:__imp_RegCloseKey
0x140012f8d  nop     dword ptr [rax+rax+00h]
0x140012f92  mov     eax, ebx
0x140012f94  lea     r11, [rsp+70h+var_s0]
0x140012f99  mov     rbx, [r11+10h]
0x140012f9d  mov     rdi, [r11+20h]
0x140012fa1  mov     rsp, r11
0x140012fa4  pop     rbp
0x140012fa5  retn
```
