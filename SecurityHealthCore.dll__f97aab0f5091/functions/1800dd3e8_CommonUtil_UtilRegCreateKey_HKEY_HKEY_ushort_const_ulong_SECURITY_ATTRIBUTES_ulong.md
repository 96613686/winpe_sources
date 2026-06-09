# CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x1800dd3e8`
- end: `0x1800dd4e3`
- name: `?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `251`
- prototype: `int(CommonUtil *__hidden this, HKEY *, HKEY, const unsigned __int16 *, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b800`
- `0x180052f0c`
- `0x180064e28`
- `0x180073390`
- `0x180074f40`
- `0x180076ea0`
- `0x180097560`
- `0x1800b5100`
- `0x1800c9f14`
- `0x1800cee78`
- `0x1800cf6f8`
- `0x1800cfdb8`
- `0x1800d0c14`

## callees

- `0x1800159a0`
- `0x1800dd3e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dd4a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dd4a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800dd44c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800dd44c`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegCreateKey(
        CommonUtil *this,
        HKEY *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4,
        struct _SECURITY_ATTRIBUTES *a5,
        struct _SECURITY_ATTRIBUTES *a6)
{
  int v6; // esi
  int v8; // ebx
  bool v9; // sf
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  v6 = (int)a3;
  LODWORD(a6) = 0;
  hKey = 0;
  v8 = RegCreateKeyExW((HKEY)a2, a3, 0, 0, 0, (REGSAM)a4, a5, &hKey, (LPDWORD)&a6);
  if ( !v8 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_473dbbf2212f33a3d422106396b3062c_Traceguids,
      v6,
      v8);
  v9 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = v8 < 0;
  }
  if ( v9 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v8;
  }
  else
  {
LABEL_11:
    if ( hKey )
    {
      *(_QWORD *)this = hKey;
      return (_DWORD)a6 == 2;
    }
    else
    {
      return 2147549183LL;
    }
  }
}

```

## disassembly

```asm
0x1800dd3e8  mov     r11, rsp
0x1800dd3eb  mov     [r11+10h], rbx
0x1800dd3ef  mov     [r11+18h], rsi
0x1800dd3f3  push    rdi
0x1800dd3f4  sub     rsp, 50h
0x1800dd3f8  lea     rax, [r11+30h]
0x1800dd3fc  mov     qword ptr [rcx], 0
0x1800dd403  mov     [r11-18h], rax
0x1800dd407  mov     rsi, r8
0x1800dd40a  lea     rax, [r11+8]
0x1800dd40e  mov     dword ptr [r11+30h], 0
0x1800dd416  mov     [r11-20h], rax
0x1800dd41a  mov     r10, rdx
0x1800dd41d  mov     rax, [rsp+58h+arg_20]
0x1800dd425  mov     rdi, rcx
0x1800dd428  mov     [r11-28h], rax
0x1800dd42c  xor     r8d, r8d; Reserved
0x1800dd42f  mov     [r11-30h], r9d
0x1800dd433  mov     rdx, rsi; lpSubKey
0x1800dd436  xor     r9d, r9d; lpClass
0x1800dd439  mov     qword ptr [r11+8], 0
0x1800dd441  mov     rcx, r10; hKey
0x1800dd444  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800dd44c  call    cs:__imp_RegCreateKeyExW
0x1800dd452  mov     ebx, eax
0x1800dd454  test    eax, eax
0x1800dd456  jz      short loc_1800DD4B2
0x1800dd458  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dd45f  lea     rax, WPP_GLOBAL_Control
0x1800dd466  cmp     rcx, rax
0x1800dd469  jz      short loc_1800DD48D
0x1800dd46b  test    byte ptr [rcx+1Ch], 1
0x1800dd46f  jz      short loc_1800DD48D
0x1800dd471  mov     rcx, [rcx+10h]
0x1800dd475  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x1800dd47c  mov     edx, 0Ch
0x1800dd481  mov     [rsp+58h+dwOptions], ebx
0x1800dd485  mov     r9, rsi
0x1800dd488  call    WPP_SF_Sd
0x1800dd48d  test    ebx, ebx
0x1800dd48f  jle     short loc_1800DD49C
0x1800dd491  movzx   ebx, bx
0x1800dd494  or      ebx, 80070000h
0x1800dd49a  test    ebx, ebx
0x1800dd49c  jns     short loc_1800DD4B2
0x1800dd49e  mov     rcx, [rsp+58h+hKey]; hKey
0x1800dd4a3  test    rcx, rcx
0x1800dd4a6  jz      short loc_1800DD4AE
0x1800dd4a8  call    cs:__imp_RegCloseKey
0x1800dd4ae  mov     eax, ebx
0x1800dd4b0  jmp     short loc_1800DD4D3
0x1800dd4b2  mov     rax, [rsp+58h+hKey]
0x1800dd4b7  test    rax, rax
0x1800dd4ba  jnz     short loc_1800DD4C3
0x1800dd4bc  mov     eax, 8000FFFFh
0x1800dd4c1  jmp     short loc_1800DD4D3
0x1800dd4c3  mov     [rdi], rax
0x1800dd4c6  xor     eax, eax
0x1800dd4c8  cmp     dword ptr [rsp+58h+arg_28], 2
0x1800dd4d0  setz    al
0x1800dd4d3  mov     rbx, [rsp+58h+arg_8]
0x1800dd4d8  mov     rsi, [rsp+58h+arg_10]
0x1800dd4dd  add     rsp, 50h
0x1800dd4e1  pop     rdi
0x1800dd4e2  retn
```
