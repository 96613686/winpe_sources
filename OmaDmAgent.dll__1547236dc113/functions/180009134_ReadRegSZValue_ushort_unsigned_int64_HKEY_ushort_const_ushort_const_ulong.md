# ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180009134`
- end: `0x18000927c`
- name: `?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z`
- size: `328`
- prototype: `__int64 __usercall@<rax>(LPBYTE lpData@<rcx>, unsigned __int64@<rdx>, HKEY@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800078f4`
- `0x18000e524`
- `0x18000ea88`
- `0x18001ab3c`

## callees

- `0x180009134`
- `0x18000a3c0`
- `0x18001f3da`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000924f`
- `ADVAPI32!RegCloseKey` at `0x18000924f`
- `ADVAPI32!RegQueryValueExW` at `0x1800091ea`
- `ADVAPI32!RegQueryValueExW` at `0x1800091ea`
- `ADVAPI32!RegOpenKeyExW` at `0x18000917f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000917f`
- `KERNEL32!SetLastError` at `0x18000925d`
- `KERNEL32!SetLastError` at `0x18000925d`

## pseudocode

```c
__int64 __fastcall ReadRegSZValue(
        LPBYTE lpData,
        int a2,
        HKEY a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpValueName,
        unsigned int *hKey)
{
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  LPCWSTR v11; // rcx
  int v12; // edx
  int v13; // r9d
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  cbData = 2 * a2;
  memset_0(lpData, 0, (unsigned int)(2 * a2));
  v9 = RegOpenKeyExW(a3, a4, 0, 0x101u, (PHKEY)&hKey);
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    else
      v10 = v9;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_16;
    v12 = 22;
    v13 = (int)a4;
    goto LABEL_15;
  }
  v10 = 0;
  v9 = RegQueryValueExW((HKEY)hKey, lpValueName, 0, 0, lpData, &cbData);
  if ( !v9 )
    goto LABEL_16;
  if ( v9 > 0 )
  {
    v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 == 2 )
      goto LABEL_16;
  }
  else
  {
    v10 = v9;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v13 = (int)lpValueName;
    v12 = 23;
LABEL_15:
    WPP_SF_Sd(*((_QWORD *)v11 + 2), v12, (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, v13, v9);
  }
LABEL_16:
  if ( hKey )
    RegCloseKey((HKEY)hKey);
  SetLastError(0);
  return v10;
}

```

## disassembly

```asm
0x180009134  mov     [rsp+arg_0], rbx
0x180009139  mov     [rsp+arg_10], rsi
0x18000913e  push    rdi
0x18000913f  sub     rsp, 30h
0x180009143  lea     eax, [rdx+rdx]
0x180009146  mov     [rsp+38h+hKey], 0
0x18000914f  mov     rbx, r8
0x180009152  mov     [rsp+38h+cbData], eax
0x180009156  mov     r8d, eax; Size
0x180009159  xor     edx, edx; Val
0x18000915b  mov     rsi, r9
0x18000915e  mov     rdi, rcx
0x180009161  call    memset_0
0x180009166  lea     rax, [rsp+38h+hKey]
0x18000916b  mov     r9d, 101h; samDesired
0x180009171  xor     r8d, r8d; ulOptions
0x180009174  mov     [rsp+38h+phkResult], rax; phkResult
0x180009179  mov     rdx, rsi; lpSubKey
0x18000917c  mov     rcx, rbx; hKey
0x18000917f  call    cs:__imp_RegOpenKeyExW
0x180009186  nop     dword ptr [rax+rax+00h]
0x18000918b  test    eax, eax
0x18000918d  jz      short loc_1800091C9
0x18000918f  jg      short loc_180009195
0x180009191  mov     ebx, eax
0x180009193  jmp     short loc_18000919E
0x180009195  movzx   ebx, ax
0x180009198  or      ebx, 80070000h
0x18000919e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091a5  lea     rdx, WPP_GLOBAL_Control
0x1800091ac  cmp     rcx, rdx
0x1800091af  jz      loc_180009245
0x1800091b5  test    byte ptr [rcx+1Ch], 1
0x1800091b9  jz      loc_180009245
0x1800091bf  mov     edx, 16h
0x1800091c4  mov     r9, rsi
0x1800091c7  jmp     short loc_180009231
0x1800091c9  mov     rdx, [rsp+38h+lpValueName]; lpValueName
0x1800091ce  lea     rax, [rsp+38h+cbData]
0x1800091d3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800091d8  xor     r9d, r9d; lpType
0x1800091db  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800091e0  xor     r8d, r8d; lpReserved
0x1800091e3  mov     [rsp+38h+phkResult], rdi; lpData
0x1800091e8  xor     ebx, ebx
0x1800091ea  call    cs:__imp_RegQueryValueExW
0x1800091f1  nop     dword ptr [rax+rax+00h]
0x1800091f6  test    eax, eax
0x1800091f8  jz      short loc_180009245
0x1800091fa  jg      short loc_180009200
0x1800091fc  mov     ebx, eax
0x1800091fe  jmp     short loc_18000920E
0x180009200  movzx   ebx, ax
0x180009203  or      ebx, 80070000h
0x180009209  cmp     eax, 2
0x18000920c  jz      short loc_180009245
0x18000920e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009215  lea     rdx, WPP_GLOBAL_Control
0x18000921c  cmp     rcx, rdx
0x18000921f  jz      short loc_180009245
0x180009221  test    byte ptr [rcx+1Ch], 1
0x180009225  jz      short loc_180009245
0x180009227  mov     r9, [rsp+38h+lpValueName]
0x18000922c  mov     edx, 17h
0x180009231  mov     rcx, [rcx+10h]
0x180009235  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x18000923c  mov     dword ptr [rsp+38h+phkResult], eax
0x180009240  call    WPP_SF_Sd
0x180009245  mov     rcx, [rsp+38h+hKey]; hKey
0x18000924a  test    rcx, rcx
0x18000924d  jz      short loc_18000925B
0x18000924f  call    cs:__imp_RegCloseKey
0x180009256  nop     dword ptr [rax+rax+00h]
0x18000925b  xor     ecx, ecx; dwErrCode
0x18000925d  call    cs:__imp_SetLastError
0x180009264  nop     dword ptr [rax+rax+00h]
0x180009269  mov     rsi, [rsp+38h+arg_10]
0x18000926e  mov     eax, ebx
0x180009270  mov     rbx, [rsp+38h+arg_0]
0x180009275  add     rsp, 30h
0x180009279  pop     rdi
0x18000927a  retn
```
