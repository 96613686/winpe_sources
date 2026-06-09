# GetOfflineDeviceUniqueIDFromTPM

- ea: `0x180040dc4`
- end: `0x180040ef5`
- name: `GetOfflineDeviceUniqueIDFromTPM`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180040efc`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x1800408c0`
- `0x180040dc4`
- `0x18004128c`
- `0x180041cd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040e56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040e56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040e45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040e45`

## pseudocode

```c
__int64 __fastcall GetOfflineDeviceUniqueIDFromTPM(__int64 a1, __int64 a2, _DWORD *a3, _OWORD *a4)
{
  LSTATUS v6; // esi
  __int64 result; // rax
  unsigned __int8 *v8; // rdx
  __int64 v9; // rcx
  __int128 v10; // xmm1
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v14[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v16[256]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(v16, 0, sizeof(v16));
  v11 = 0;
  v12 = 32;
  hKey = 0;
  *(_OWORD *)v14 = 0;
  v15 = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  if ( !v6 )
    RegCloseKey(hKey);
  if ( *a3 < 0x20u )
  {
    result = 2147942522LL;
LABEL_10:
    *a3 = 32;
    return result;
  }
  result = GetEKPubFromTPM(v16, &v11, v6 == 0);
  if ( (int)result < 0 )
    return result;
  if ( !IsValidEKPub(v16, v11) )
    return 2150105123LL;
  result = GenerateOfflineDeviceID(v9, v8, (ULONG)v8, v16, v14, &v12);
  if ( (int)result >= 0 )
  {
    v10 = v15;
    *a4 = *(_OWORD *)v14;
    a4[1] = v10;
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x180040dc4  mov     [rsp-8+arg_0], rbx
0x180040dc9  push    rbp
0x180040dca  push    rsi
0x180040dcb  push    rdi
0x180040dcc  lea     rbp, [rsp-70h]
0x180040dd1  sub     rsp, 170h
0x180040dd8  mov     rax, cs:__security_cookie
0x180040ddf  xor     rax, rsp
0x180040de2  mov     [rbp+80h+var_20], rax
0x180040de6  mov     rbx, r8
0x180040de9  lea     rcx, [rsp+180h+var_120]; void *
0x180040dee  mov     r8d, 100h; Size
0x180040df4  xor     edx, edx; Val
0x180040df6  mov     rdi, r9
0x180040df9  call    memset_0
0x180040dfe  xorps   xmm0, xmm0
0x180040e01  mov     [rsp+180h+var_150], 0
0x180040e09  lea     rax, [rsp+180h+hKey]
0x180040e0e  mov     [rsp+180h+var_14C], 20h ; ' '
0x180040e16  mov     r9d, 20019h; samDesired
0x180040e1c  mov     [rsp+180h+phkResult], rax; phkResult
0x180040e21  xor     r8d, r8d; ulOptions
0x180040e24  mov     [rsp+180h+hKey], 0
0x180040e2d  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180040e34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040e3b  movups  xmmword ptr [rsp+180h+var_140], xmm0
0x180040e40  movups  [rsp+180h+var_130], xmm0
0x180040e45  call    cs:__imp_RegOpenKeyExW
0x180040e4b  mov     esi, eax
0x180040e4d  test    eax, eax
0x180040e4f  jnz     short loc_180040E5C
0x180040e51  mov     rcx, [rsp+180h+hKey]; hKey
0x180040e56  call    cs:__imp_RegCloseKey
0x180040e5c  test    esi, esi
0x180040e5e  setz    r8b; unsigned __int8
0x180040e62  cmp     dword ptr [rbx], 20h ; ' '
0x180040e65  jnb     short loc_180040E6E
0x180040e67  mov     eax, 8007007Ah
0x180040e6c  jmp     short loc_180040ED0
0x180040e6e  lea     rdx, [rsp+180h+var_150]; unsigned int *
0x180040e73  lea     rcx, [rsp+180h+var_120]; unsigned __int8 *
0x180040e78  call    ?GetEKPubFromTPM@@YAJPEAEPEAIE@Z; GetEKPubFromTPM(uchar *,uint *,uchar)
0x180040e7d  test    eax, eax
0x180040e7f  js      short loc_180040ED6
0x180040e81  mov     edx, [rsp+180h+var_150]; unsigned int
0x180040e85  lea     rcx, [rsp+180h+var_120]; unsigned __int8 *
0x180040e8a  call    ?IsValidEKPub@@YAEPEAEI@Z; IsValidEKPub(uchar *,uint)
0x180040e8f  test    al, al
0x180040e91  jnz     short loc_180040E9A
0x180040e93  mov     eax, 80280023h
0x180040e98  jmp     short loc_180040ED6
0x180040e9a  lea     rax, [rsp+180h+var_14C]
0x180040e9f  mov     r8d, edx; unsigned int
0x180040ea2  mov     [rsp+180h+var_158], rax; unsigned int *
0x180040ea7  lea     r9, [rsp+180h+var_120]; unsigned __int8 *
0x180040eac  lea     rax, [rsp+180h+var_140]
0x180040eb1  mov     [rsp+180h+phkResult], rax; unsigned __int8 *
0x180040eb6  call    ?GenerateOfflineDeviceID@@YAJIPEAEI00PEAI@Z; GenerateOfflineDeviceID(uint,uchar *,uint,uchar *,uchar *,uint *)
0x180040ebb  test    eax, eax
0x180040ebd  js      short loc_180040ED6
0x180040ebf  movups  xmm0, xmmword ptr [rsp+180h+var_140]
0x180040ec4  movups  xmm1, [rsp+180h+var_130]
0x180040ec9  movups  xmmword ptr [rdi], xmm0
0x180040ecc  movups  xmmword ptr [rdi+10h], xmm1
0x180040ed0  mov     dword ptr [rbx], 20h ; ' '
0x180040ed6  mov     rcx, [rbp+80h+var_20]
0x180040eda  xor     rcx, rsp; StackCookie
0x180040edd  call    __security_check_cookie
0x180040ee2  mov     rbx, [rsp+180h+arg_0]
0x180040eea  add     rsp, 170h
0x180040ef1  pop     rdi
0x180040ef2  pop     rsi
0x180040ef3  pop     rbp
0x180040ef4  retn
```
