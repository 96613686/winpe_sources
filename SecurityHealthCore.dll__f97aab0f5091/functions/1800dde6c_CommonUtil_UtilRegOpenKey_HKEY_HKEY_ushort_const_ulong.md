# CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)

- ea: `0x1800dde6c`
- end: `0x1800ddf7c`
- name: `?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z`
- size: `272`
- prototype: `int(CommonUtil *__hidden this, HKEY *, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `29`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002600c`
- `0x180064c20`
- `0x180065ec0`
- `0x1800700b0`
- `0x180070270`
- `0x1800716fc`
- `0x180074710`
- `0x180084c74`
- `0x180084d7c`
- `0x180086a98`
- `0x1800870d0`
- `0x1800876a8`
- `0x18008792c`
- `0x1800973e0`
- `0x180097560`
- `0x1800b1558`
- `0x1800b2cf0`
- `0x1800b2d8c`
- `0x1800b5100`
- `0x1800b5c30`
- `0x1800bd3d4`
- `0x1800c9c0c`
- `0x1800c9d64`
- `0x1800ce5a0`
- `0x1800ce830`
- `0x1800cee78`
- `0x1800cf7bc`
- `0x1800dafb0`
- `0x1800dd1ac`

## callees

- `0x180015894`
- `0x1800159a0`
- `0x1800dde6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ddeeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ddf4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ddeeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ddf4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ddea5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ddea5`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegOpenKey(CommonUtil *this, HKEY *a2, const WCHAR *a3, const unsigned __int16 *a4)
{
  int v6; // ebx
  bool v8; // sf
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  hKey = 0;
  v6 = RegOpenKeyExW((HKEY)a2, a3, 0, (REGSAM)a4, &hKey);
  if ( v6 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_473dbbf2212f33a3d422106396b3062c_Traceguids, a3);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  else
  {
    if ( !v6 )
      goto LABEL_18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_473dbbf2212f33a3d422106396b3062c_Traceguids,
        (_DWORD)a3,
        v6);
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
0x1800dde6c  mov     r11, rsp
0x1800dde6f  mov     [r11+10h], rbx
0x1800dde73  mov     [r11+18h], rsi
0x1800dde77  push    rdi
0x1800dde78  sub     rsp, 30h
0x1800dde7c  mov     rsi, rcx
0x1800dde7f  mov     qword ptr [rcx], 0
0x1800dde86  lea     rcx, [r11+8]
0x1800dde8a  mov     qword ptr [r11+8], 0
0x1800dde92  mov     rdi, r8
0x1800dde95  mov     [r11-18h], rcx
0x1800dde99  mov     rax, rdx
0x1800dde9c  xor     r8d, r8d; ulOptions
0x1800dde9f  mov     rcx, rax; hKey
0x1800ddea2  mov     rdx, rdi; lpSubKey
0x1800ddea5  call    cs:__imp_RegOpenKeyExW
0x1800ddeab  mov     ebx, eax
0x1800ddead  cmp     eax, 2
0x1800ddeb0  jnz     short loc_1800DDEF8
0x1800ddeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddeb9  lea     rax, WPP_GLOBAL_Control
0x1800ddec0  cmp     rcx, rax
0x1800ddec3  jz      short loc_1800DDEE1
0x1800ddec5  test    byte ptr [rcx+1Ch], 10h
0x1800ddec9  jz      short loc_1800DDEE1
0x1800ddecb  mov     rcx, [rcx+10h]
0x1800ddecf  lea     edx, [rbx+8]
0x1800dded2  mov     r9, rdi
0x1800dded5  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x1800ddedc  call    WPP_SF_S
0x1800ddee1  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ddee6  test    rcx, rcx
0x1800ddee9  jz      short loc_1800DDEF1
0x1800ddeeb  call    cs:__imp_RegCloseKey
0x1800ddef1  mov     eax, 80070002h
0x1800ddef6  jmp     short loc_1800DDF6C
0x1800ddef8  test    ebx, ebx
0x1800ddefa  jz      short loc_1800DDF56
0x1800ddefc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ddf03  lea     rax, WPP_GLOBAL_Control
0x1800ddf0a  cmp     rcx, rax
0x1800ddf0d  jz      short loc_1800DDF31
0x1800ddf0f  test    byte ptr [rcx+1Ch], 1
0x1800ddf13  jz      short loc_1800DDF31
0x1800ddf15  mov     rcx, [rcx+10h]
0x1800ddf19  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x1800ddf20  mov     edx, 0Bh
0x1800ddf25  mov     [rsp+38h+var_18], ebx
0x1800ddf29  mov     r9, rdi
0x1800ddf2c  call    WPP_SF_Sd
0x1800ddf31  test    ebx, ebx
0x1800ddf33  jle     short loc_1800DDF40
0x1800ddf35  movzx   ebx, bx
0x1800ddf38  or      ebx, 80070000h
0x1800ddf3e  test    ebx, ebx
0x1800ddf40  jns     short loc_1800DDF56
0x1800ddf42  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ddf47  test    rcx, rcx
0x1800ddf4a  jz      short loc_1800DDF52
0x1800ddf4c  call    cs:__imp_RegCloseKey
0x1800ddf52  mov     eax, ebx
0x1800ddf54  jmp     short loc_1800DDF6C
0x1800ddf56  mov     rax, [rsp+38h+hKey]
0x1800ddf5b  test    rax, rax
0x1800ddf5e  jnz     short loc_1800DDF67
0x1800ddf60  mov     eax, 8000FFFFh
0x1800ddf65  jmp     short loc_1800DDF6C
0x1800ddf67  mov     [rsi], rax
0x1800ddf6a  xor     eax, eax
0x1800ddf6c  mov     rbx, [rsp+38h+arg_8]
0x1800ddf71  mov     rsi, [rsp+38h+arg_10]
0x1800ddf76  add     rsp, 30h
0x1800ddf7a  pop     rdi
0x1800ddf7b  retn
```
