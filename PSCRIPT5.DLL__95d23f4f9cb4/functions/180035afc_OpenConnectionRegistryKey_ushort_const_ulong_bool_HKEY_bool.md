# OpenConnectionRegistryKey(ushort const *,ulong,bool,HKEY__ * *,bool *)

- ea: `0x180035afc`
- end: `0x180035c2d`
- name: `?OpenConnectionRegistryKey@@YAJPEBGK_NPEAPEAUHKEY__@@PEA_N@Z`
- size: `305`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, unsigned int, bool, HKEY *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800343d0`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180005568`
- `0x18001fe90`
- `0x180035afc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180035beb`
- `ADVAPI32!RegOpenKeyExW` at `0x180035beb`

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
0x180035afc  mov     [rsp+arg_8], rbx
0x180035b01  push    rbp
0x180035b02  push    rsi
0x180035b03  push    rdi
0x180035b04  push    r14
0x180035b06  push    r15
0x180035b08  sub     rsp, 250h
0x180035b0f  mov     rax, cs:__security_cookie
0x180035b16  xor     rax, rsp
0x180035b19  mov     [rsp+278h+var_38], rax
0x180035b21  mov     rsi, rcx
0x180035b24  xor     edx, edx; Val
0x180035b26  lea     rcx, [rsp+278h+pszDest]; void *
0x180035b2b  mov     r8d, 208h; Size
0x180035b31  mov     rbp, r9
0x180035b34  call    memset_0
0x180035b39  mov     r15d, 104h
0x180035b3f  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180035b46  mov     edx, r15d; cchDest
0x180035b49  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180035b4e  call    StringCchCopyW
0x180035b53  xor     r14d, r14d
0x180035b56  mov     ebx, eax
0x180035b58  test    eax, eax
0x180035b5a  js      short loc_180035BCD
0x180035b5c  lea     r8, SubBlock; "\\"
0x180035b63  mov     edx, r15d; cchDest
0x180035b66  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180035b6b  call    StringCchCatW
0x180035b70  mov     ebx, eax
0x180035b72  test    eax, eax
0x180035b74  js      short loc_180035BCD
0x180035b76  lea     rax, [rsp+278h+pszDest]
0x180035b7b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180035b7f  inc     rdi
0x180035b82  cmp     [rax+rdi*2], r14w
0x180035b87  jnz     short loc_180035B7F
0x180035b89  mov     r8, rsi; pszSrc
0x180035b8c  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180035b91  mov     rdx, r15; cchDest
0x180035b94  call    StringCchCatW
0x180035b99  mov     ebx, eax
0x180035b9b  test    eax, eax
0x180035b9d  js      short loc_180035BCD
0x180035b9f  lea     rax, [rsp+278h+pszDest]
0x180035ba4  lea     rax, [rax+rdi*2]
0x180035ba8  movzx   ecx, word ptr [rax]
0x180035bab  test    cx, cx
0x180035bae  jz      short loc_180035BCD
0x180035bb0  mov     edx, 5Ch ; '\'
0x180035bb5  cmp     dx, cx
0x180035bb8  jnz     short loc_180035BBF
0x180035bba  mov     word ptr [rax], 2Ch ; ','
0x180035bbf  add     rax, 2
0x180035bc3  movzx   ecx, word ptr [rax]
0x180035bc6  test    cx, cx
0x180035bc9  jnz     short loc_180035BB0
0x180035bcb  jmp     short loc_180035BD1
0x180035bcd  test    ebx, ebx
0x180035bcf  js      short loc_180035C04
0x180035bd1  mov     r9d, 20019h; samDesired
0x180035bd7  mov     [rsp+278h+phkResult], rbp; phkResult
0x180035bdc  xor     r8d, r8d; ulOptions
0x180035bdf  lea     rdx, [rsp+278h+pszDest]; lpSubKey
0x180035be4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035beb  call    cs:__imp_RegOpenKeyExW
0x180035bf1  test    eax, eax
0x180035bf3  jz      short loc_180035C04
0x180035bf5  jg      short loc_180035BFB
0x180035bf7  mov     ebx, eax
0x180035bf9  jmp     short loc_180035C04
0x180035bfb  movzx   ebx, ax
0x180035bfe  or      ebx, 80070000h
0x180035c04  mov     eax, ebx
0x180035c06  mov     rcx, [rsp+278h+var_38]
0x180035c0e  xor     rcx, rsp; StackCookie
0x180035c11  call    __security_check_cookie
0x180035c16  mov     rbx, [rsp+278h+arg_8]
0x180035c1e  add     rsp, 250h
0x180035c25  pop     r15
0x180035c27  pop     r14
0x180035c29  pop     rdi
0x180035c2a  pop     rsi
0x180035c2b  pop     rbp
0x180035c2c  retn
```
