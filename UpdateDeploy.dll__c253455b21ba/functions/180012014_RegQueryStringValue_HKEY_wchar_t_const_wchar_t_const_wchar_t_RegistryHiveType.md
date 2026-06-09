# RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)

- ea: `0x180012014`
- end: `0x180012173`
- name: `?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180046e50`
- `0x180047000`
- `0x1800530e4`

## callees

- `0x18000dc6c`
- `0x18000dce4`
- `0x180011cb8`
- `0x180012014`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012091`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012150`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800120bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001210f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800120bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001210f`

## pseudocode

```c
__int64 __fastcall RegQueryStringValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, void **a4)
{
  signed int v9; // ebx
  LSTATUS v10; // eax
  BYTE *v11; // rax
  REGSAM samDesired; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF

  samDesired = 1;
  Type = 0;
  hKey = 0;
  cbData = 0;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v9 = SetRegistryType(a1, &samDesired);
  if ( v9 < 0 )
    goto LABEL_16;
  v10 = RegOpenKeyExW(a1, a2, 0, samDesired, &hKey);
  if ( v10 )
    goto LABEL_13;
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  if ( v10 || !cbData )
    goto LABEL_13;
  if ( Type != 1 )
  {
    v9 = -2147024883;
LABEL_16:
    SusFree(*a4);
    *a4 = 0;
    goto LABEL_17;
  }
  cbData += 2;
  v11 = (BYTE *)SusAlloc(cbData);
  *a4 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    goto LABEL_16;
  }
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, v11, &cbData);
  if ( v10 )
  {
LABEL_13:
    v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v9 = v10;
    if ( v9 >= 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  *(_WORD *)((char *)*a4 + (cbData & 0xFFFFFFFE)) = 0;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012014  push    rbp
0x180012016  push    rbx
0x180012017  push    rsi
0x180012018  push    rdi
0x180012019  push    r12
0x18001201b  push    r14
0x18001201d  push    r15
0x18001201f  mov     rbp, rsp
0x180012022  sub     rsp, 50h
0x180012026  mov     rax, cs:__security_cookie
0x18001202d  xor     rax, rsp
0x180012030  mov     [rbp+var_8], rax
0x180012034  xor     r12d, r12d
0x180012037  mov     [rbp+samDesired], 1
0x18001203e  mov     [rbp+Type], r12d
0x180012042  mov     rdi, r9
0x180012045  mov     [rbp+hKey], r12
0x180012049  mov     rsi, r8
0x18001204c  mov     [rbp+cbData], r12d
0x180012050  mov     r15, rdx
0x180012053  mov     r14, rcx
0x180012056  test    r9, r9
0x180012059  jnz     short loc_180012065
0x18001205b  mov     eax, 80070057h
0x180012060  jmp     loc_180012158
0x180012065  lea     rdx, [rbp+samDesired]
0x180012069  mov     [r9], r12
0x18001206c  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180012071  mov     ebx, eax
0x180012073  test    eax, eax
0x180012075  js      loc_18001213C
0x18001207b  mov     r9d, [rbp+samDesired]; samDesired
0x18001207f  lea     rax, [rbp+hKey]
0x180012083  xor     r8d, r8d; ulOptions
0x180012086  mov     [rsp+50h+phkResult], rax; phkResult
0x18001208b  mov     rdx, r15; lpSubKey
0x18001208e  mov     rcx, r14; hKey
0x180012091  call    cs:__imp_RegOpenKeyExW
0x180012097  test    eax, eax
0x180012099  jnz     loc_18001212A
0x18001209f  mov     rcx, [rbp+hKey]; hKey
0x1800120a3  lea     rax, [rbp+cbData]
0x1800120a7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800120ac  lea     r9, [rbp+Type]; lpType
0x1800120b0  xor     r8d, r8d; lpReserved
0x1800120b3  mov     [rsp+50h+phkResult], r12; lpData
0x1800120b8  mov     rdx, rsi; lpValueName
0x1800120bb  call    cs:__imp_RegQueryValueExW
0x1800120c1  test    eax, eax
0x1800120c3  jnz     short loc_18001212A
0x1800120c5  mov     ecx, [rbp+cbData]
0x1800120c8  test    ecx, ecx
0x1800120ca  jz      short loc_18001212A
0x1800120cc  cmp     [rbp+Type], 1
0x1800120d0  jz      short loc_1800120D9
0x1800120d2  mov     ebx, 8007000Dh
0x1800120d7  jmp     short loc_18001213C
0x1800120d9  add     ecx, 2; unsigned __int64
0x1800120dc  mov     [rbp+cbData], ecx
0x1800120df  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x1800120e4  mov     [rdi], rax
0x1800120e7  test    rax, rax
0x1800120ea  jnz     short loc_1800120F3
0x1800120ec  mov     ebx, 8007000Eh
0x1800120f1  jmp     short loc_18001213C
0x1800120f3  lea     rcx, [rbp+cbData]
0x1800120f7  xor     r8d, r8d; lpReserved
0x1800120fa  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x1800120ff  lea     r9, [rbp+Type]; lpType
0x180012103  mov     rcx, [rbp+hKey]; hKey
0x180012107  mov     rdx, rsi; lpValueName
0x18001210a  mov     [rsp+50h+phkResult], rax; lpData
0x18001210f  call    cs:__imp_RegQueryValueExW
0x180012115  test    eax, eax
0x180012117  jnz     short loc_18001212A
0x180012119  mov     ecx, [rbp+cbData]
0x18001211c  mov     rax, [rdi]
0x18001211f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180012123  mov     [rcx+rax], r12w
0x180012128  jmp     short loc_180012147
0x18001212a  movzx   ebx, ax
0x18001212d  or      ebx, 80070000h
0x180012133  test    eax, eax
0x180012135  cmovle  ebx, eax
0x180012138  test    ebx, ebx
0x18001213a  jns     short loc_180012147
0x18001213c  mov     rcx, [rdi]; lpMem
0x18001213f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180012144  mov     [rdi], r12
0x180012147  mov     rcx, [rbp+hKey]; hKey
0x18001214b  test    rcx, rcx
0x18001214e  jz      short loc_180012156
0x180012150  call    cs:__imp_RegCloseKey
0x180012156  mov     eax, ebx
0x180012158  mov     rcx, [rbp+var_8]
0x18001215c  xor     rcx, rsp; StackCookie
0x18001215f  call    __security_check_cookie
0x180012164  add     rsp, 50h
0x180012168  pop     r15
0x18001216a  pop     r14
0x18001216c  pop     r12
0x18001216e  pop     rdi
0x18001216f  pop     rsi
0x180012170  pop     rbx
0x180012171  pop     rbp
0x180012172  retn
```
