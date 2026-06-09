# CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(HKEY__ *,ushort const *,int *)

- ea: `0x18000c238`
- end: `0x18000c307`
- name: `?KeyExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBGPEAH@Z`
- size: `207`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016bcc`
- `0x180016d34`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c238`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c26d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c26d`

## pseudocode

```c
__int64 __fastcall CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(__int64 a1, const WCHAR *a2, int *a3)
{
  int v4; // esi
  int v5; // eax
  HKEY v6; // rbx
  unsigned int v7; // edi
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v4 = 1;
  v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 1u, &hKey);
  if ( v5 )
  {
    v6 = 0;
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v7 = v5;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  }
  else
  {
    v6 = hKey;
    v7 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !(_WORD)v7 )
    goto LABEL_14;
  if ( (unsigned __int16)v7 == 2 )
  {
    v4 = 0;
LABEL_14:
    *a3 = v4;
    v7 = 0;
    goto LABEL_15;
  }
  if ( (v7 & 0x80000000) == 0 )
    v7 = -2147467259;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x18000c238  mov     r11, rsp
0x18000c23b  mov     [r11+8], rcx
0x18000c23f  push    rbx
0x18000c240  push    rsi
0x18000c241  push    rdi
0x18000c242  push    r14
0x18000c244  sub     rsp, 38h
0x18000c248  mov     r14, r8
0x18000c24b  mov     qword ptr [r11+8], 0
0x18000c253  lea     rax, [r11+8]
0x18000c257  mov     esi, 1
0x18000c25c  mov     r9d, esi; samDesired
0x18000c25f  mov     [r11-38h], rax
0x18000c263  xor     r8d, r8d; ulOptions
0x18000c266  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c26d  call    cs:__imp_RegOpenKeyExW
0x18000c273  test    eax, eax
0x18000c275  jz      short loc_18000C290
0x18000c277  xor     ebx, ebx
0x18000c279  test    eax, eax
0x18000c27b  jle     short loc_18000C285
0x18000c27d  movzx   eax, ax
0x18000c280  or      eax, 80070000h
0x18000c285  mov     ecx, eax
0x18000c287  mov     edi, eax
0x18000c289  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c28e  jmp     short loc_18000C2A0
0x18000c290  mov     rbx, [rsp+58h+hKey]
0x18000c295  xor     edi, edi
0x18000c297  mov     [rsp+58h+hKey], 0
0x18000c2a0  mov     ecx, edi
0x18000c2a2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c2a7  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c2ac  test    rcx, rcx
0x18000c2af  jz      short loc_18000C2C0
0x18000c2b1  call    cs:__imp_RegCloseKey
0x18000c2b7  mov     [rsp+58h+hKey], 0
0x18000c2c0  movzx   eax, di
0x18000c2c3  test    eax, eax
0x18000c2c5  jz      short loc_18000C2E1
0x18000c2c7  cmp     eax, 2
0x18000c2ca  jz      short loc_18000C2DF
0x18000c2cc  test    edi, edi
0x18000c2ce  mov     eax, 80004005h
0x18000c2d3  cmovns  edi, eax
0x18000c2d6  mov     ecx, edi
0x18000c2d8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c2dd  jmp     short loc_18000C2E6
0x18000c2df  xor     esi, esi
0x18000c2e1  mov     [r14], esi
0x18000c2e4  xor     edi, edi
0x18000c2e6  mov     ecx, edi
0x18000c2e8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c2ed  test    rbx, rbx
0x18000c2f0  jz      short loc_18000C2FB
0x18000c2f2  mov     rcx, rbx; hKey
0x18000c2f5  call    cs:__imp_RegCloseKey
0x18000c2fb  mov     eax, edi
0x18000c2fd  add     rsp, 38h
0x18000c301  pop     r14
0x18000c303  pop     rdi
0x18000c304  pop     rsi
0x18000c305  pop     rbx
0x18000c306  retn
```
