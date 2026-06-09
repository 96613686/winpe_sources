# ReportDataSourceIdDeletion(_LARGE_INTEGER)

- ea: `0x18000466c`
- end: `0x180004781`
- name: `?ReportDataSourceIdDeletion@@YAJT_LARGE_INTEGER@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800031bc`
- `0x1800040a8`

## callees

- `0x18000466c`
- `0x1800051c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800046ea`
- `msvcrt!swprintf_s` at `0x1800046ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800046b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800046b5`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180004718`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180004718`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800046fe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800046fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000475c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000475c`

## string_xrefs

- `0x1800046ae`: `SYSTEM\CurrentControlSet\Services\WOF\Providers\WIM\IntegrityFiles`

## pseudocode

```c
__int64 __fastcall ReportDataSourceIdDeletion(union _LARGE_INTEGER a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // edi
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  wchar_t Buffer[8]; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\WOF\\Providers\\WIM\\IntegrityFiles",
         0,
         2u,
         &hKey);
  v3 = v2;
  if ( v2 == 2 )
  {
    v3 = 0;
LABEL_18:
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 )
    goto LABEL_18;
  if ( swprintf_s(Buffer, 8u, L"%I64u", a1.QuadPart) < 0 )
  {
    v3 = -2147467259;
    goto LABEL_18;
  }
  v4 = RegDeleteValueW(hKey, Buffer);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 )
    goto LABEL_18;
  v5 = RegFlushKey(hKey);
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 )
    goto LABEL_18;
  v6 = RegCloseKey(hKey);
  v3 = v6;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( v3 )
    goto LABEL_18;
  return v3;
}

```

## disassembly

```asm
0x18000466c  mov     r11, rsp
0x18000466f  mov     [r11+10h], rbx
0x180004673  mov     [r11+18h], rsi
0x180004677  push    rdi
0x180004678  sub     rsp, 50h
0x18000467c  mov     rax, cs:__security_cookie
0x180004683  xor     rax, rsp
0x180004686  mov     [rsp+58h+var_10], rax
0x18000468b  mov     rbx, rcx
0x18000468e  mov     qword ptr [r11-28h], 0
0x180004696  lea     rax, [r11-28h]
0x18000469a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800046a1  mov     r9d, 2; samDesired
0x1800046a7  mov     [r11-38h], rax
0x1800046ab  xor     r8d, r8d; ulOptions
0x1800046ae  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\WO"...
0x1800046b5  call    cs:__imp_RegOpenKeyExW
0x1800046bb  mov     edi, eax
0x1800046bd  cmp     eax, 2
0x1800046c0  jz      loc_180004750
0x1800046c6  mov     esi, 80070000h
0x1800046cb  test    eax, eax
0x1800046cd  jle     short loc_1800046D4
0x1800046cf  movzx   edi, ax
0x1800046d2  or      edi, esi
0x1800046d4  test    edi, edi
0x1800046d6  jnz     short loc_180004752
0x1800046d8  mov     r9, rbx
0x1800046db  lea     r8, aI64u; "%I64u"
0x1800046e2  lea     edx, [rdi+8]; BufferCount
0x1800046e5  lea     rcx, [rsp+58h+Buffer]; Buffer
0x1800046ea  call    cs:__imp_swprintf_s
0x1800046f0  test    eax, eax
0x1800046f2  js      short loc_180004749
0x1800046f4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800046f9  lea     rdx, [rsp+58h+Buffer]; lpValueName
0x1800046fe  call    cs:__imp_RegDeleteValueW
0x180004704  mov     edi, eax
0x180004706  test    eax, eax
0x180004708  jle     short loc_18000470F
0x18000470a  movzx   edi, ax
0x18000470d  or      edi, esi
0x18000470f  test    edi, edi
0x180004711  jnz     short loc_180004752
0x180004713  mov     rcx, [rsp+58h+hKey]; hKey
0x180004718  call    cs:__imp_RegFlushKey
0x18000471e  mov     edi, eax
0x180004720  test    eax, eax
0x180004722  jle     short loc_180004729
0x180004724  movzx   edi, ax
0x180004727  or      edi, esi
0x180004729  test    edi, edi
0x18000472b  jnz     short loc_180004752
0x18000472d  mov     rcx, [rsp+58h+hKey]; hKey
0x180004732  call    cs:__imp_RegCloseKey
0x180004738  mov     edi, eax
0x18000473a  test    eax, eax
0x18000473c  jle     short loc_180004743
0x18000473e  movzx   edi, ax
0x180004741  or      edi, esi
0x180004743  test    edi, edi
0x180004745  jnz     short loc_180004752
0x180004747  jmp     short loc_180004762
0x180004749  mov     edi, 80004005h
0x18000474e  jmp     short loc_180004752
0x180004750  xor     edi, edi
0x180004752  mov     rcx, [rsp+58h+hKey]; hKey
0x180004757  test    rcx, rcx
0x18000475a  jz      short loc_180004762
0x18000475c  call    cs:__imp_RegCloseKey
0x180004762  mov     eax, edi
0x180004764  mov     rcx, [rsp+58h+var_10]
0x180004769  xor     rcx, rsp; StackCookie
0x18000476c  call    __security_check_cookie
0x180004771  mov     rbx, [rsp+58h+arg_8]
0x180004776  mov     rsi, [rsp+58h+arg_10]
0x18000477b  add     rsp, 50h
0x18000477f  pop     rdi
0x180004780  retn
```
