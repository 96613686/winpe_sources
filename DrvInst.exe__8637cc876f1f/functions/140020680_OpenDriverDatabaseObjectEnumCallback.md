# OpenDriverDatabaseObjectEnumCallback

- ea: `0x140020680`
- end: `0x1400207c5`
- name: `OpenDriverDatabaseObjectEnumCallback`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140001b64`
- `0x140009794`
- `0x140020680`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002077f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002077f`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002075b`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002075b`

## pseudocode

```c
_BOOL8 __fastcall OpenDriverDatabaseObjectEnumCallback(__int64 a1, unsigned int a2, const wchar_t *a3, int *a4)
{
  LSTATUS v8; // eax
  _QWORD *v9; // rbx
  wchar_t pszDest[520]; // [rsp+60h] [rbp-448h] BYREF

  if ( StringCchPrintfW(
         pszDest,
         0x208u,
         L"%ws\\%ws\\%ws\\%ws",
         a3,
         L"DriverDatabase",
         qword_1400489A8[*a4],
         *((_QWORD *)a4 + 1)) >= 0 )
  {
    if ( wcsicmp_0(a3, L"SYSTEM") )
      DriverStoreGetObjectPropertyW(a1, a2, a3, DEVPKEY_DriverDatabase_Loaded);
    v9 = a4 + 4;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, (PHKEY)a4 + 2);
    if ( v8 == 2 )
    {
      *v9 = 0;
      v8 = 0;
    }
  }
  else
  {
    v8 = 13;
    v9 = a4 + 4;
  }
  a4[6] = v8;
  return !v8 && !*v9;
}

```

## disassembly

```asm
0x140020680  push    rbx
0x140020682  push    rbp
0x140020683  push    rsi
0x140020684  push    rdi
0x140020685  sub     rsp, 488h
0x14002068c  mov     rax, cs:__security_cookie
0x140020693  xor     rax, rsp
0x140020696  mov     [rsp+4A8h+var_38], rax
0x14002069e  mov     rax, [r9+8]
0x1400206a2  mov     rsi, rcx
0x1400206a5  movsxd  rcx, dword ptr [r9]
0x1400206a8  mov     ebp, edx
0x1400206aa  mov     [rsp+4A8h+var_478], rax
0x1400206af  lea     rdx, qword_1400489A8
0x1400206b6  mov     rdi, r9
0x1400206b9  mov     [rsp+4A8h+var_454], 0
0x1400206c1  mov     rbx, r8
0x1400206c4  mov     [rsp+4A8h+var_458], 0
0x1400206cc  mov     rax, [rdx+rcx*8]
0x1400206d0  mov     r9, r8
0x1400206d3  mov     [rsp+4A8h+var_480], rax
0x1400206d8  lea     r8, aWsWsWsWs; "%ws\\%ws\\%ws\\%ws"
0x1400206df  lea     rax, aDriverdatabase; "DriverDatabase"
0x1400206e6  mov     edx, 208h; cchDest
0x1400206eb  lea     rcx, [rsp+4A8h+pszDest]; pszDest
0x1400206f0  mov     [rsp+4A8h+phkResult], rax
0x1400206f5  call    StringCchPrintfW
0x1400206fa  test    eax, eax
0x1400206fc  jns     short loc_14002070C
0x1400206fe  mov     eax, 0Dh
0x140020703  lea     rbx, [rdi+10h]
0x140020707  jmp     loc_140020793
0x14002070c  lea     rdx, aSystem; "SYSTEM"
0x140020713  mov     rcx, rbx; String1
0x140020716  call    _wcsicmp_0
0x14002071b  test    eax, eax
0x14002071d  jz      short loc_140020761
0x14002071f  mov     [rsp+4A8h+var_468], 0
0x140020727  lea     rax, [rsp+4A8h+var_458]
0x14002072c  mov     [rsp+4A8h+var_470], rax
0x140020731  lea     r9, DEVPKEY_DriverDatabase_Loaded
0x140020738  mov     dword ptr [rsp+4A8h+var_478], 0
0x140020740  lea     rax, [rsp+4A8h+var_454]
0x140020745  mov     [rsp+4A8h+var_480], 0
0x14002074e  mov     r8, rbx
0x140020751  mov     edx, ebp
0x140020753  mov     [rsp+4A8h+phkResult], rax
0x140020758  mov     rcx, rsi
0x14002075b  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140020761  lea     rbx, [rdi+10h]
0x140020765  mov     r9d, 20019h; samDesired
0x14002076b  xor     r8d, r8d; ulOptions
0x14002076e  mov     [rsp+4A8h+phkResult], rbx; phkResult
0x140020773  lea     rdx, [rsp+4A8h+pszDest]; lpSubKey
0x140020778  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002077f  call    cs:__imp_RegOpenKeyExW
0x140020785  cmp     eax, 2
0x140020788  jnz     short loc_140020793
0x14002078a  mov     qword ptr [rbx], 0
0x140020791  xor     eax, eax
0x140020793  mov     [rdi+18h], eax
0x140020796  test    eax, eax
0x140020798  jnz     short loc_1400207A7
0x14002079a  cmp     qword ptr [rbx], 0
0x14002079e  jnz     short loc_1400207A7
0x1400207a0  mov     eax, 1
0x1400207a5  jmp     short loc_1400207A9
0x1400207a7  xor     eax, eax
0x1400207a9  mov     rcx, [rsp+4A8h+var_38]
0x1400207b1  xor     rcx, rsp; StackCookie
0x1400207b4  call    __security_check_cookie
0x1400207b9  add     rsp, 488h
0x1400207c0  pop     rdi
0x1400207c1  pop     rsi
0x1400207c2  pop     rbp
0x1400207c3  pop     rbx
0x1400207c4  retn
```
