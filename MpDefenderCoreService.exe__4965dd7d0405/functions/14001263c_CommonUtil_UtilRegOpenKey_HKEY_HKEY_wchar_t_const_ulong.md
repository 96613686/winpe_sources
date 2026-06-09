# CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)

- ea: `0x14001263c`
- end: `0x1400126dd`
- name: `?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z`
- size: `161`
- prototype: `int(CommonUtil *__hidden this, HKEY *, HKEY, const wchar_t *, unsigned int)`
- caller_count: `37`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ba9c`
- `0x14000bbdc`
- `0x140081db4`
- `0x140081fc8`
- `0x1400820b4`
- `0x14008236c`
- `0x1400826cc`
- `0x1400831e0`
- `0x140083458`
- `0x14008371c`
- `0x140088000`
- `0x1400895b0`
- `0x140089890`
- `0x140089c78`
- `0x14008eeb0`
- `0x14008fa7c`
- `0x14008fb8c`
- `0x14008ffb0`
- `0x140091034`
- `0x140091ad0`
- `0x1400927d0`
- `0x140092b74`
- `0x140092cd8`
- `0x140097924`
- `0x14009e034`
- `0x14009e3c0`
- `0x14009e52c`
- `0x14009f6a8`
- `0x1400a02fc`
- `0x1400a1500`
- `0x1400b09d0`
- `0x1400b7960`
- `0x1400c205c`
- `0x1400c4760`
- `0x1400c5a4c`
- `0x1400f45d4`
- `0x1400f48a8`

## callees

- `0x14001263c`
- `0x14003a5c0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001267e`
- `ADVAPI32!RegOpenKeyExW` at `0x14001267e`
- `ADVAPI32!RegCloseKey` at `0x1400126a9`
- `ADVAPI32!RegCloseKey` at `0x1400126a9`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegOpenKey(CommonUtil *this, HKEY *a2, const WCHAR *a3, const wchar_t *a4)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)this = 0;
  hKey = 0;
  v5 = RegOpenKeyExW((HKEY)a2, a3, 0, (REGSAM)a4, &hKey);
  if ( v5 )
  {
    v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      v6 = v5;
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  else if ( hKey )
  {
    *(_QWORD *)this = hKey;
    return 0;
  }
  else
  {
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x14001263c  push    rbx
0x14001263e  push    rdi
0x14001263f  sub     rsp, 48h
0x140012643  mov     rax, cs:__security_cookie
0x14001264a  xor     rax, rsp
0x14001264d  mov     [rsp+58h+var_20], rax
0x140012652  mov     rdi, rcx
0x140012655  mov     qword ptr [rcx], 0
0x14001265c  mov     r10, r8
0x14001265f  mov     [rsp+58h+hKey], 0
0x140012668  mov     rax, rdx
0x14001266b  lea     rcx, [rsp+58h+hKey]
0x140012670  mov     [rsp+58h+phkResult], rcx; phkResult
0x140012675  xor     r8d, r8d; ulOptions
0x140012678  mov     rcx, rax; hKey
0x14001267b  mov     rdx, r10; lpSubKey
0x14001267e  call    cs:__imp_RegOpenKeyExW
0x140012684  test    eax, eax
0x140012686  jz      short loc_1400126B3
0x140012688  movzx   ebx, ax
0x14001268b  or      ebx, 80070000h
0x140012691  test    eax, eax
0x140012693  cmovle  ebx, eax
0x140012696  mov     ecx, ebx
0x140012698  shr     ecx, 1Fh
0x14001269b  test    cl, cl
0x14001269d  jz      short loc_1400126B3
0x14001269f  mov     rcx, [rsp+58h+hKey]; hKey
0x1400126a4  test    rcx, rcx
0x1400126a7  jz      short loc_1400126AF
0x1400126a9  call    cs:__imp_RegCloseKey
0x1400126af  mov     eax, ebx
0x1400126b1  jmp     short loc_1400126C9
0x1400126b3  mov     rax, [rsp+58h+hKey]
0x1400126b8  test    rax, rax
0x1400126bb  jnz     short loc_1400126C4
0x1400126bd  mov     eax, 8000FFFFh
0x1400126c2  jmp     short loc_1400126C9
0x1400126c4  mov     [rdi], rax
0x1400126c7  xor     eax, eax
0x1400126c9  mov     rcx, [rsp+58h+var_20]
0x1400126ce  xor     rcx, rsp; StackCookie
0x1400126d1  call    __security_check_cookie
0x1400126d6  add     rsp, 48h
0x1400126da  pop     rdi
0x1400126db  pop     rbx
0x1400126dc  retn
```
