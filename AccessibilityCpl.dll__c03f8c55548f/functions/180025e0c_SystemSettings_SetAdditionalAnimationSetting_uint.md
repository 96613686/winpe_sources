# SystemSettings::SetAdditionalAnimationSetting(uint)

- ea: `0x180025e0c`
- end: `0x180025eae`
- name: `?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z`
- size: `162`
- prototype: `__int64 __fastcall(PVOID pvParam)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025fdc`

## callees

- `0x180025e0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e68`
- `USER32!SystemParametersInfoW` at `0x180025e5a`
- `USER32!SystemParametersInfoW` at `0x180025e92`
- `USER32!SystemParametersInfoW` at `0x180025e5a`
- `USER32!SystemParametersInfoW` at `0x180025e92`

## pseudocode

```c
signed int __fastcall SystemSettings::SetAdditionalAnimationSetting(PVOID pvParam)
{
  unsigned __int64 v1; // rdi
  unsigned int v2; // ebx
  signed int result; // eax
  UINT uiAction[10]; // [rsp+20h] [rbp-28h]
  int pvParama; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v1 = (unsigned int)pvParam;
  v2 = 0;
  uiAction[0] = 4099;
  uiAction[1] = 4101;
  uiAction[2] = 4103;
  uiAction[3] = 4117;
  uiAction[4] = 4119;
  while ( v2 < 5 )
  {
    if ( !SystemParametersInfoW(uiAction[v2], 0, (PVOID)v1, 3u) )
      goto LABEL_5;
    ++v2;
  }
  pvParama = 8;
  v6 = v1;
  if ( SystemParametersInfoW(0x49u, 0, &pvParama, 3u) )
    return 0;
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025e0c  mov     rax, rsp
0x180025e0f  mov     [rax+8], rbx
0x180025e13  mov     [rax+18h], rsi
0x180025e17  push    rdi
0x180025e18  sub     rsp, 40h
0x180025e1c  mov     edi, ecx
0x180025e1e  xor     ebx, ebx
0x180025e20  mov     dword ptr [rax-28h], 1003h
0x180025e27  mov     dword ptr [rax-24h], 1005h
0x180025e2e  mov     dword ptr [rax-20h], 1007h
0x180025e35  mov     dword ptr [rax-1Ch], 1015h
0x180025e3c  mov     dword ptr [rax-18h], 1017h
0x180025e43  xor     edx, edx; uiParam
0x180025e45  mov     r9d, 3; fWinIni
0x180025e4b  cmp     ebx, 5
0x180025e4e  jnb     short loc_180025E7C
0x180025e50  movsxd  rcx, ebx
0x180025e53  mov     r8, rdi; pvParam
0x180025e56  mov     ecx, [rsp+rcx*4+48h+uiAction]; uiAction
0x180025e5a  call    cs:__imp_SystemParametersInfoW
0x180025e60  test    eax, eax
0x180025e62  jz      short loc_180025E68
0x180025e64  inc     ebx
0x180025e66  jmp     short loc_180025E43
0x180025e68  call    cs:__imp_GetLastError
0x180025e6e  test    eax, eax
0x180025e70  jle     short loc_180025E9E
0x180025e72  movzx   eax, ax
0x180025e75  or      eax, 80070000h
0x180025e7a  jmp     short loc_180025E9E
0x180025e7c  lea     r8, [rsp+48h+pvParam]; pvParam
0x180025e81  mov     [rsp+48h+pvParam], 8
0x180025e89  mov     ecx, 49h ; 'I'; uiAction
0x180025e8e  mov     [rsp+48h+arg_C], edi
0x180025e92  call    cs:__imp_SystemParametersInfoW
0x180025e98  test    eax, eax
0x180025e9a  jz      short loc_180025E68
0x180025e9c  xor     eax, eax
0x180025e9e  mov     rbx, [rsp+48h+arg_0]
0x180025ea3  mov     rsi, [rsp+48h+arg_10]
0x180025ea8  add     rsp, 40h
0x180025eac  pop     rdi
0x180025ead  retn
```
