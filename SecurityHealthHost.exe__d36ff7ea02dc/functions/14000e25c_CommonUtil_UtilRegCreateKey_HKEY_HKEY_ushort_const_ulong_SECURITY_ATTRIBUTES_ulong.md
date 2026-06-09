# CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x14000e25c`
- end: `0x14000e356`
- name: `?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `250`
- prototype: `__int64 __fastcall(CommonUtil *this, HKEY *, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003188`

## callees

- `0x14000db28`
- `0x14000e25c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000e2c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000e2c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e31e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e31e`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegCreateKey(
        CommonUtil *this,
        HKEY *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  int v4; // edi
  int v6; // ebx
  int v7; // r8d
  bool v8; // sf
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  DWORD v11; // [rsp+78h] [rbp+20h] BYREF

  *(_QWORD *)this = 0;
  v4 = (int)a3;
  v11 = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x20019u, 0, &hKey, &v11);
  if ( !v6 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, v4, v6);
  v8 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v8 = v6 < 0;
  }
  if ( v8 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  else
  {
LABEL_11:
    if ( hKey )
    {
      *(_QWORD *)this = hKey;
      return v11 == 2;
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
0x14000e25c  mov     r11, rsp
0x14000e25f  mov     [r11+8], rbx
0x14000e263  mov     [r11+18h], rsi
0x14000e267  mov     [r11+20h], r9d
0x14000e26b  mov     [r11+10h], rdx
0x14000e26f  push    rdi
0x14000e270  sub     rsp, 50h
0x14000e274  lea     rax, [r11+20h]
0x14000e278  mov     qword ptr [rcx], 0
0x14000e27f  mov     [r11-18h], rax
0x14000e283  mov     rdi, r8
0x14000e286  lea     rax, [r11+10h]
0x14000e28a  mov     [rsp+58h+arg_18], 0
0x14000e292  mov     [r11-20h], rax
0x14000e296  mov     rsi, rcx
0x14000e299  mov     qword ptr [r11-28h], 0
0x14000e2a1  xor     r9d, r9d; lpClass
0x14000e2a4  mov     [rsp+58h+samDesired], 20019h; samDesired
0x14000e2ac  xor     r8d, r8d; Reserved
0x14000e2af  mov     rdx, rdi; lpSubKey
0x14000e2b2  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14000e2ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e2c1  mov     qword ptr [r11+10h], 0
0x14000e2c9  call    cs:__imp_RegCreateKeyExW
0x14000e2cf  mov     ebx, eax
0x14000e2d1  test    eax, eax
0x14000e2d3  jz      short loc_14000E328
0x14000e2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e2dc  lea     rax, WPP_GLOBAL_Control
0x14000e2e3  cmp     rcx, rax
0x14000e2e6  jz      short loc_14000E303
0x14000e2e8  test    byte ptr [rcx+1Ch], 1
0x14000e2ec  jz      short loc_14000E303
0x14000e2ee  mov     rcx, [rcx+10h]
0x14000e2f2  mov     edx, 0Ch
0x14000e2f7  mov     r9, rdi
0x14000e2fa  mov     [rsp+58h+dwOptions], ebx
0x14000e2fe  call    WPP_SF_SD
0x14000e303  test    ebx, ebx
0x14000e305  jle     short loc_14000E312
0x14000e307  movzx   ebx, bx
0x14000e30a  or      ebx, 80070000h
0x14000e310  test    ebx, ebx
0x14000e312  jns     short loc_14000E328
0x14000e314  mov     rcx, [rsp+58h+hKey]; hKey
0x14000e319  test    rcx, rcx
0x14000e31c  jz      short loc_14000E324
0x14000e31e  call    cs:__imp_RegCloseKey
0x14000e324  mov     eax, ebx
0x14000e326  jmp     short loc_14000E346
0x14000e328  mov     rax, [rsp+58h+hKey]
0x14000e32d  test    rax, rax
0x14000e330  jnz     short loc_14000E339
0x14000e332  mov     eax, 8000FFFFh
0x14000e337  jmp     short loc_14000E346
0x14000e339  mov     [rsi], rax
0x14000e33c  xor     eax, eax
0x14000e33e  cmp     [rsp+58h+arg_18], 2
0x14000e343  setz    al
0x14000e346  mov     rbx, [rsp+58h+arg_0]
0x14000e34b  mov     rsi, [rsp+58h+arg_10]
0x14000e350  add     rsp, 50h
0x14000e354  pop     rdi
0x14000e355  retn
```
