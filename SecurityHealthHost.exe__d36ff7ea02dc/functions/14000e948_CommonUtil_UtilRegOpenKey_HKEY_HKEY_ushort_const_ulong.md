# CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)

- ea: `0x14000e948`
- end: `0x14000ea5c`
- name: `?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z`
- size: `276`
- prototype: `__int64 __fastcall(CommonUtil *this, HKEY *, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000285c`

## callees

- `0x14000cfa0`
- `0x14000db28`
- `0x14000e948`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e98c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e98c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e9d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ea2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e9d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ea2c`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegOpenKey(CommonUtil *this, HKEY *a2, const WCHAR *a3, const unsigned __int16 *a4)
{
  int v6; // ebx
  int v7; // r8d
  bool v9; // sf
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a3, 0, 0x20019u, &hKey);
  if ( v6 == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_473dbbf2212f33a3d422106396b3062c_Traceguids, a3);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  else
  {
    if ( !v6 )
      goto LABEL_18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v7, (_DWORD)a3, v6);
    v9 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v9 = v6 < 0;
    }
    if ( v9 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v6;
    }
    else
    {
LABEL_18:
      if ( hKey )
      {
        *(_QWORD *)this = hKey;
        return 0;
      }
      else
      {
        return 2147549183LL;
      }
    }
  }
}

```

## disassembly

```asm
0x14000e948  mov     r11, rsp
0x14000e94b  mov     [r11+8], rbx
0x14000e94f  mov     [r11+18h], rsi
0x14000e953  mov     [r11+10h], rdx
0x14000e957  push    rdi
0x14000e958  sub     rsp, 30h
0x14000e95c  mov     rdi, r8
0x14000e95f  mov     qword ptr [rcx], 0
0x14000e966  mov     rsi, rcx
0x14000e969  mov     qword ptr [r11+10h], 0
0x14000e971  lea     rax, [r11+10h]
0x14000e975  mov     rdx, rdi; lpSubKey
0x14000e978  mov     r9d, 20019h; samDesired
0x14000e97e  mov     [r11-18h], rax
0x14000e982  xor     r8d, r8d; ulOptions
0x14000e985  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000e98c  call    cs:__imp_RegOpenKeyExW
0x14000e992  mov     ebx, eax
0x14000e994  cmp     eax, 2
0x14000e997  jnz     short loc_14000E9DF
0x14000e999  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9a0  lea     rax, WPP_GLOBAL_Control
0x14000e9a7  cmp     rcx, rax
0x14000e9aa  jz      short loc_14000E9C8
0x14000e9ac  test    byte ptr [rcx+1Ch], 10h
0x14000e9b0  jz      short loc_14000E9C8
0x14000e9b2  mov     rcx, [rcx+10h]
0x14000e9b6  lea     edx, [rbx+8]
0x14000e9b9  mov     r9, rdi
0x14000e9bc  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x14000e9c3  call    WPP_SF_S
0x14000e9c8  mov     rcx, [rsp+38h+hKey]; hKey
0x14000e9cd  test    rcx, rcx
0x14000e9d0  jz      short loc_14000E9D8
0x14000e9d2  call    cs:__imp_RegCloseKey
0x14000e9d8  mov     eax, 80070002h
0x14000e9dd  jmp     short loc_14000EA4C
0x14000e9df  test    ebx, ebx
0x14000e9e1  jz      short loc_14000EA36
0x14000e9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9ea  lea     rax, WPP_GLOBAL_Control
0x14000e9f1  cmp     rcx, rax
0x14000e9f4  jz      short loc_14000EA11
0x14000e9f6  test    byte ptr [rcx+1Ch], 1
0x14000e9fa  jz      short loc_14000EA11
0x14000e9fc  mov     rcx, [rcx+10h]
0x14000ea00  mov     edx, 0Bh
0x14000ea05  mov     r9, rdi
0x14000ea08  mov     [rsp+38h+var_18], ebx
0x14000ea0c  call    WPP_SF_SD
0x14000ea11  test    ebx, ebx
0x14000ea13  jle     short loc_14000EA20
0x14000ea15  movzx   ebx, bx
0x14000ea18  or      ebx, 80070000h
0x14000ea1e  test    ebx, ebx
0x14000ea20  jns     short loc_14000EA36
0x14000ea22  mov     rcx, [rsp+38h+hKey]; hKey
0x14000ea27  test    rcx, rcx
0x14000ea2a  jz      short loc_14000EA32
0x14000ea2c  call    cs:__imp_RegCloseKey
0x14000ea32  mov     eax, ebx
0x14000ea34  jmp     short loc_14000EA4C
0x14000ea36  mov     rax, [rsp+38h+hKey]
0x14000ea3b  test    rax, rax
0x14000ea3e  jnz     short loc_14000EA47
0x14000ea40  mov     eax, 8000FFFFh
0x14000ea45  jmp     short loc_14000EA4C
0x14000ea47  mov     [rsi], rax
0x14000ea4a  xor     eax, eax
0x14000ea4c  mov     rbx, [rsp+38h+arg_0]
0x14000ea51  mov     rsi, [rsp+38h+arg_10]
0x14000ea56  add     rsp, 30h
0x14000ea5a  pop     rdi
0x14000ea5b  retn
```
