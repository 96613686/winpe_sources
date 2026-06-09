# CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)

- ea: `0x140004fac`
- end: `0x14000504d`
- name: `?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z`
- size: `161`
- prototype: `int(CommonUtil *__hidden this, HKEY *, HKEY, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400029b0`
- `0x140002af0`

## callees

- `0x140004fac`
- `0x140005c20`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140004fee`
- `ADVAPI32!RegOpenKeyExW` at `0x140004fee`
- `ADVAPI32!RegCloseKey` at `0x140005019`
- `ADVAPI32!RegCloseKey` at `0x140005019`

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
0x140004fac  push    rbx
0x140004fae  push    rdi
0x140004faf  sub     rsp, 48h
0x140004fb3  mov     rax, cs:__security_cookie
0x140004fba  xor     rax, rsp
0x140004fbd  mov     [rsp+58h+var_20], rax
0x140004fc2  mov     rdi, rcx
0x140004fc5  mov     qword ptr [rcx], 0
0x140004fcc  mov     r10, r8
0x140004fcf  mov     [rsp+58h+hKey], 0
0x140004fd8  mov     rax, rdx
0x140004fdb  lea     rcx, [rsp+58h+hKey]
0x140004fe0  mov     [rsp+58h+phkResult], rcx; phkResult
0x140004fe5  xor     r8d, r8d; ulOptions
0x140004fe8  mov     rcx, rax; hKey
0x140004feb  mov     rdx, r10; lpSubKey
0x140004fee  call    cs:__imp_RegOpenKeyExW
0x140004ff4  test    eax, eax
0x140004ff6  jz      short loc_140005023
0x140004ff8  movzx   ebx, ax
0x140004ffb  or      ebx, 80070000h
0x140005001  test    eax, eax
0x140005003  cmovle  ebx, eax
0x140005006  mov     ecx, ebx
0x140005008  shr     ecx, 1Fh
0x14000500b  test    cl, cl
0x14000500d  jz      short loc_140005023
0x14000500f  mov     rcx, [rsp+58h+hKey]; hKey
0x140005014  test    rcx, rcx
0x140005017  jz      short loc_14000501F
0x140005019  call    cs:__imp_RegCloseKey
0x14000501f  mov     eax, ebx
0x140005021  jmp     short loc_140005039
0x140005023  mov     rax, [rsp+58h+hKey]
0x140005028  test    rax, rax
0x14000502b  jnz     short loc_140005034
0x14000502d  mov     eax, 8000FFFFh
0x140005032  jmp     short loc_140005039
0x140005034  mov     [rdi], rax
0x140005037  xor     eax, eax
0x140005039  mov     rcx, [rsp+58h+var_20]
0x14000503e  xor     rcx, rsp; StackCookie
0x140005041  call    __security_check_cookie
0x140005046  add     rsp, 48h
0x14000504a  pop     rdi
0x14000504b  pop     rbx
0x14000504c  retn
```
