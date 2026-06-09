# OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)

- ea: `0x1800372bc`
- end: `0x1800373f4`
- name: `?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z`
- size: `312`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, __int64, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035ae0`

## callees

- `0x180001f20`
- `0x180002938`
- `0x1800055fc`
- `0x180020acc`
- `0x1800372bc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800373ab`
- `ADVAPI32!RegOpenKeyExW` at `0x1800373ab`

## pseudocode

```c
__int64 __fastcall OpenConnectionRegistryKey(STRSAFE_LPCWSTR pszSrc, __int64 a2, __int64 a3, HKEY *a4)
{
  HRESULT v6; // ebx
  __int64 v7; // rdi
  wchar_t *v8; // rax
  wchar_t v9; // cx
  LSTATUS v10; // eax
  wchar_t pszDest[264]; // [rsp+30h] [rbp-248h] BYREF

  memset_0(pszDest, 0, 0x208u);
  v6 = StringCchCopyW(pszDest, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\V4 Connections");
  if ( v6 < 0 )
    goto LABEL_11;
  v6 = StringCchCatW(pszDest, 0x104u, L"\\");
  if ( v6 < 0 )
    goto LABEL_11;
  v7 = -1;
  do
    ++v7;
  while ( pszDest[v7] );
  v6 = StringCchCatW(pszDest, 0x104u, pszSrc);
  if ( v6 >= 0 && (v8 = &pszDest[v7], (v9 = *v8) != 0) )
  {
    do
    {
      if ( v9 == 92 )
        *v8 = 44;
      v9 = *++v8;
    }
    while ( *v8 );
  }
  else
  {
LABEL_11:
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, a4);
  if ( v10 )
  {
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
    else
      return (unsigned int)v10;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800372bc  mov     [rsp+arg_8], rbx
0x1800372c1  push    rbp
0x1800372c2  push    rsi
0x1800372c3  push    rdi
0x1800372c4  push    r14
0x1800372c6  push    r15
0x1800372c8  sub     rsp, 250h
0x1800372cf  mov     rax, cs:__security_cookie
0x1800372d6  xor     rax, rsp
0x1800372d9  mov     [rsp+278h+var_38], rax
0x1800372e1  mov     rsi, rcx
0x1800372e4  xor     edx, edx; Val
0x1800372e6  lea     rcx, [rsp+278h+pszDest]; void *
0x1800372eb  mov     r8d, 208h; Size
0x1800372f1  mov     rbp, r9
0x1800372f4  call    memset_0
0x1800372f9  mov     r15d, 104h
0x1800372ff  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180037306  mov     edx, r15d; cchDest
0x180037309  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18003730e  call    StringCchCopyW
0x180037313  xor     r14d, r14d
0x180037316  mov     ebx, eax
0x180037318  test    eax, eax
0x18003731a  js      short loc_18003738D
0x18003731c  lea     r8, SubBlock; "\\"
0x180037323  mov     edx, r15d; cchDest
0x180037326  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18003732b  call    StringCchCatW
0x180037330  mov     ebx, eax
0x180037332  test    eax, eax
0x180037334  js      short loc_18003738D
0x180037336  lea     rax, [rsp+278h+pszDest]
0x18003733b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003733f  inc     rdi
0x180037342  cmp     [rax+rdi*2], r14w
0x180037347  jnz     short loc_18003733F
0x180037349  mov     r8, rsi; pszSrc
0x18003734c  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180037351  mov     rdx, r15; cchDest
0x180037354  call    StringCchCatW
0x180037359  mov     ebx, eax
0x18003735b  test    eax, eax
0x18003735d  js      short loc_18003738D
0x18003735f  lea     rax, [rsp+278h+pszDest]
0x180037364  lea     rax, [rax+rdi*2]
0x180037368  movzx   ecx, word ptr [rax]
0x18003736b  test    cx, cx
0x18003736e  jz      short loc_18003738D
0x180037370  mov     edx, 5Ch ; '\'
0x180037375  cmp     dx, cx
0x180037378  jnz     short loc_18003737F
0x18003737a  mov     word ptr [rax], 2Ch ; ','
0x18003737f  add     rax, 2
0x180037383  movzx   ecx, word ptr [rax]
0x180037386  test    cx, cx
0x180037389  jnz     short loc_180037370
0x18003738b  jmp     short loc_180037391
0x18003738d  test    ebx, ebx
0x18003738f  js      short loc_1800373CA
0x180037391  mov     r9d, 20019h; samDesired
0x180037397  mov     [rsp+278h+phkResult], rbp; phkResult
0x18003739c  xor     r8d, r8d; ulOptions
0x18003739f  lea     rdx, [rsp+278h+pszDest]; lpSubKey
0x1800373a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800373ab  call    cs:__imp_RegOpenKeyExW
0x1800373b2  nop     dword ptr [rax+rax+00h]
0x1800373b7  test    eax, eax
0x1800373b9  jz      short loc_1800373CA
0x1800373bb  jg      short loc_1800373C1
0x1800373bd  mov     ebx, eax
0x1800373bf  jmp     short loc_1800373CA
0x1800373c1  movzx   ebx, ax
0x1800373c4  or      ebx, 80070000h
0x1800373ca  mov     eax, ebx
0x1800373cc  mov     rcx, [rsp+278h+var_38]
0x1800373d4  xor     rcx, rsp; StackCookie
0x1800373d7  call    __security_check_cookie
0x1800373dc  mov     rbx, [rsp+278h+arg_8]
0x1800373e4  add     rsp, 250h
0x1800373eb  pop     r15
0x1800373ed  pop     r14
0x1800373ef  pop     rdi
0x1800373f0  pop     rsi
0x1800373f1  pop     rbp
0x1800373f2  retn
```
