# DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x14004904c`
- end: `0x140049166`
- name: `?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `282`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14004a9a4`
- `0x14004f798`

## callees

- `0x1400095b4`
- `0x14004904c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400490d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400490d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004914b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004914b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049110`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049110`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_GetRegistryDWORD(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  BYTE Data[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF

  *(_DWORD *)Data = 0;
  Type = 4;
  hKey = 0;
  cbData = 4;
  if ( !a1 )
  {
    v7 = 173;
LABEL_3:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return v8;
  }
  if ( !a4 )
  {
    v7 = 174;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v9 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
LABEL_19:
      if ( hKey )
        RegCloseKey(hKey);
      return v8;
    }
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v10 = RegQueryValueExW(a1, a3, 0, &Type, Data, &cbData);
  v8 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
  }
  else if ( Type == 4 )
  {
    v8 = 0;
    *a4 = *(_DWORD *)Data;
  }
  else
  {
    v8 = -2147418113;
  }
  if ( a2 )
    goto LABEL_19;
  return v8;
}

```

## disassembly

```asm
0x14004904c  mov     [rsp-18h+arg_8], rbx
0x140049051  mov     [rsp-18h+arg_10], rsi
0x140049056  push    rbp
0x140049057  push    rdi
0x140049058  push    r14
0x14004905a  mov     rbp, rsp
0x14004905d  sub     rsp, 40h
0x140049061  mov     dword ptr [rbp+Data], 0
0x140049068  mov     rsi, r9
0x14004906b  mov     [rbp+Type], 4
0x140049072  mov     r14, r8
0x140049075  mov     [rbp+hKey], 0
0x14004907d  mov     rdi, rdx
0x140049080  mov     [rbp+cbData], 4
0x140049087  test    rcx, rcx
0x14004908a  jnz     short loc_1400490AE
0x14004908c  mov     edx, 0ADh; void *
0x140049091  mov     rcx, [rbp+18h]; this
0x140049095  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004909c  mov     ebx, 80070057h
0x1400490a1  mov     r9d, ebx; char *
0x1400490a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400490a9  jmp     loc_140049151
0x1400490ae  test    rsi, rsi
0x1400490b1  jnz     short loc_1400490BA
0x1400490b3  mov     edx, 0AEh; lpSubKey
0x1400490b8  jmp     short loc_140049091
0x1400490ba  test    rdi, rdi
0x1400490bd  jz      short loc_1400490F0
0x1400490bf  lea     rax, [rbp+hKey]
0x1400490c3  mov     r9d, 20119h; samDesired
0x1400490c9  xor     r8d, r8d; ulOptions
0x1400490cc  mov     [rsp+40h+phkResult], rax; phkResult
0x1400490d1  call    cs:__imp_RegOpenKeyExW
0x1400490d7  mov     ebx, eax
0x1400490d9  test    eax, eax
0x1400490db  jz      short loc_1400490EA
0x1400490dd  jle     short loc_140049142
0x1400490df  movzx   ebx, ax
0x1400490e2  or      ebx, 80070000h
0x1400490e8  jmp     short loc_140049142
0x1400490ea  mov     rcx, [rbp+hKey]; hKey
0x1400490ee  jmp     short loc_1400490F4
0x1400490f0  mov     [rbp+hKey], rcx
0x1400490f4  lea     rax, [rbp+cbData]
0x1400490f8  xor     r8d, r8d; lpReserved
0x1400490fb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140049100  lea     r9, [rbp+Type]; lpType
0x140049104  lea     rax, [rbp+Data]
0x140049108  mov     rdx, r14; lpValueName
0x14004910b  mov     [rsp+40h+phkResult], rax; lpData
0x140049110  call    cs:__imp_RegQueryValueExW
0x140049116  mov     ebx, eax
0x140049118  test    eax, eax
0x14004911a  jz      short loc_140049129
0x14004911c  jle     short loc_14004913D
0x14004911e  movzx   ebx, ax
0x140049121  or      ebx, 80070000h
0x140049127  jmp     short loc_14004913D
0x140049129  cmp     [rbp+Type], 4
0x14004912d  jz      short loc_140049136
0x14004912f  mov     ebx, 8000FFFFh
0x140049134  jmp     short loc_14004913D
0x140049136  mov     eax, dword ptr [rbp+Data]
0x140049139  xor     ebx, ebx
0x14004913b  mov     [rsi], eax
0x14004913d  test    rdi, rdi
0x140049140  jz      short loc_140049151
0x140049142  mov     rcx, [rbp+hKey]; hKey
0x140049146  test    rcx, rcx
0x140049149  jz      short loc_140049151
0x14004914b  call    cs:__imp_RegCloseKey
0x140049151  mov     rsi, [rsp+40h+arg_10]
0x140049156  mov     eax, ebx
0x140049158  mov     rbx, [rsp+40h+arg_8]
0x14004915d  add     rsp, 40h
0x140049161  pop     r14
0x140049163  pop     rdi
0x140049164  pop     rbp
0x140049165  retn
```
