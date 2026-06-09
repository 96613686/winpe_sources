# privateRegReadStringValueW

- ea: `0x18000f9c8`
- end: `0x18000fb37`
- name: `privateRegReadStringValueW`
- size: `367`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, __int64, BYTE **, DWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007988`
- `0x180007f4c`
- `0x180009808`

## callees

- `0x1800014b0`
- `0x18000f9c8`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fa51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fab5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fa51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fab5`

## pseudocode

```c
__int64 __fastcall privateRegReadStringValueW(HKEY hKey, LPCWSTR lpValueName, __int64 a3, BYTE **a4, DWORD *a5)
{
  unsigned int v8; // ebx
  DWORD v9; // eax
  BYTE *lpData; // rax
  BYTE *v11; // rdi
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+34h] [rbp-Ch] BYREF

  Type = 0;
  cbData = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !hKey || !lpValueName || !a4 || !a5 )
  {
    v8 = 87;
    goto LABEL_25;
  }
  v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( !v8 )
  {
    if ( Type != 1 )
    {
      v8 = 1010;
      goto LABEL_25;
    }
    v9 = cbData;
    if ( cbData <= 2 )
    {
      v9 = 2;
      cbData = 2;
    }
    lpData = (BYTE *)Dns_Allocate(v9);
    v11 = lpData;
    if ( !lpData )
    {
      v8 = 14;
      goto LABEL_25;
    }
    *(_WORD *)lpData = 0;
    v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    if ( !v8 )
    {
      v12 = cbData;
      if ( cbData )
      {
        v13 = cbData >> 1;
        if ( !(_DWORD)v13 )
        {
LABEL_23:
          *a4 = v11;
          *a5 = v12 >> 1;
          cbData = 0;
          goto LABEL_25;
        }
        *(_WORD *)&v11[2 * v13 - 2] = 0;
      }
      else
      {
        *(_WORD *)v11 = 0;
      }
      v12 = cbData;
      goto LABEL_23;
    }
    Dns_Free(v11);
  }
LABEL_25:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 14, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000f9c8  push    rbp
0x18000f9ca  push    rbx
0x18000f9cb  push    rsi
0x18000f9cc  push    rdi
0x18000f9cd  push    r12
0x18000f9cf  push    r14
0x18000f9d1  push    r15
0x18000f9d3  mov     rbp, rsp
0x18000f9d6  sub     rsp, 40h
0x18000f9da  mov     rax, cs:__security_cookie
0x18000f9e1  xor     rax, rsp
0x18000f9e4  mov     [rbp+var_8], rax
0x18000f9e8  mov     rsi, [rbp+arg_20]
0x18000f9ec  mov     r14, r9
0x18000f9ef  mov     [rbp+Type], 0
0x18000f9f6  mov     r12, rdx
0x18000f9f9  mov     [rbp+cbData], 0
0x18000fa00  mov     r15, rcx
0x18000fa03  test    r9, r9
0x18000fa06  jz      short loc_18000FA0F
0x18000fa08  mov     qword ptr [r9], 0
0x18000fa0f  test    rsi, rsi
0x18000fa12  jz      short loc_18000FA1A
0x18000fa14  mov     dword ptr [rsi], 0
0x18000fa1a  test    r15, r15
0x18000fa1d  jnz     short loc_18000FA29
0x18000fa1f  mov     ebx, 57h ; 'W'
0x18000fa24  jmp     loc_18000FAF8
0x18000fa29  test    r12, r12
0x18000fa2c  jz      short loc_18000FA1F
0x18000fa2e  test    r14, r14
0x18000fa31  jz      short loc_18000FA1F
0x18000fa33  test    rsi, rsi
0x18000fa36  jz      short loc_18000FA1F
0x18000fa38  lea     rax, [rbp+cbData]
0x18000fa3c  xor     r8d, r8d; lpReserved
0x18000fa3f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000fa44  lea     r9, [rbp+Type]; lpType
0x18000fa48  mov     [rsp+40h+lpData], 0; lpData
0x18000fa51  call    cs:__imp_RegQueryValueExW
0x18000fa57  mov     ebx, eax
0x18000fa59  test    eax, eax
0x18000fa5b  jnz     loc_18000FAF8
0x18000fa61  cmp     [rbp+Type], 1
0x18000fa65  jz      short loc_18000FA71
0x18000fa67  mov     ebx, 3F2h
0x18000fa6c  jmp     loc_18000FAF8
0x18000fa71  mov     eax, [rbp+cbData]
0x18000fa74  cmp     eax, 2
0x18000fa77  ja      short loc_18000FA81
0x18000fa79  mov     eax, 2
0x18000fa7e  mov     [rbp+cbData], eax
0x18000fa81  mov     ecx, eax
0x18000fa83  call    Dns_Allocate
0x18000fa88  mov     rdi, rax
0x18000fa8b  test    rax, rax
0x18000fa8e  jnz     short loc_18000FA95
0x18000fa90  lea     ebx, [rax+0Eh]
0x18000fa93  jmp     short loc_18000FAF8
0x18000fa95  xor     eax, eax
0x18000fa97  lea     r9, [rbp+Type]; lpType
0x18000fa9b  mov     [rdi], ax
0x18000fa9e  xor     r8d, r8d; lpReserved
0x18000faa1  lea     rax, [rbp+cbData]
0x18000faa5  mov     rdx, r12; lpValueName
0x18000faa8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000faad  mov     rcx, r15; hKey
0x18000fab0  mov     [rsp+40h+lpData], rdi; lpData
0x18000fab5  call    cs:__imp_RegQueryValueExW
0x18000fabb  mov     ebx, eax
0x18000fabd  test    eax, eax
0x18000fabf  jnz     short loc_18000FAF0
0x18000fac1  mov     eax, [rbp+cbData]
0x18000fac4  test    eax, eax
0x18000fac6  jnz     short loc_18000FACD
0x18000fac8  mov     [rdi], ax
0x18000facb  jmp     short loc_18000FADD
0x18000facd  mov     ecx, eax
0x18000facf  shr     ecx, 1
0x18000fad1  cmp     ecx, 1
0x18000fad4  jb      short loc_18000FAE0
0x18000fad6  xor     eax, eax
0x18000fad8  mov     [rdi+rcx*2-2], ax
0x18000fadd  mov     eax, [rbp+cbData]
0x18000fae0  shr     eax, 1
0x18000fae2  mov     [r14], rdi
0x18000fae5  mov     [rsi], eax
0x18000fae7  mov     [rbp+cbData], 0
0x18000faee  jmp     short loc_18000FAF8
0x18000faf0  mov     rcx, rdi; lpMem
0x18000faf3  call    Dns_Free
0x18000faf8  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000faff  jz      short loc_18000FB1A
0x18000fb01  mov     edx, 0Eh
0x18000fb06  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18000fb0d  mov     ecx, 40Bh
0x18000fb12  mov     r9d, ebx
0x18000fb15  call    WPP_SF_d
0x18000fb1a  mov     eax, ebx
0x18000fb1c  mov     rcx, [rbp+var_8]
0x18000fb20  xor     rcx, rsp; StackCookie
0x18000fb23  call    __security_check_cookie
0x18000fb28  add     rsp, 40h
0x18000fb2c  pop     r15
0x18000fb2e  pop     r14
0x18000fb30  pop     r12
0x18000fb32  pop     rdi
0x18000fb33  pop     rsi
0x18000fb34  pop     rbx
0x18000fb35  pop     rbp
0x18000fb36  retn
```
