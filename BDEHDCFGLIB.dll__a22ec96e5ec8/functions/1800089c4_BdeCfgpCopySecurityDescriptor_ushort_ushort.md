# BdeCfgpCopySecurityDescriptor(ushort *,ushort *)

- ea: `0x1800089c4`
- end: `0x180008aa6`
- name: `?BdeCfgpCopySecurityDescriptor@@YAJPEAG0@Z`
- size: `226`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180008968`
- `0x180009000`

## callees

- `0x1800089c4`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x180008a2f`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180008a2f`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180008a75`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180008a75`
- `KERNEL32!LocalFree` at `0x180008a81`
- `KERNEL32!LocalFree` at `0x180008a81`

## pseudocode

```c
__int64 __fastcall BdeCfgpCopySecurityDescriptor(unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int NamedSecurityInfoW; // eax
  signed int v4; // ebx
  PSID psidGroup; // [rsp+40h] [rbp-20h] BYREF
  PSID ppsidOwner; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF
  PACL pSacl; // [rsp+80h] [rbp+20h] BYREF
  PACL pDacl; // [rsp+88h] [rbp+28h] BYREF

  ppsidOwner = 0;
  psidGroup = 0;
  pDacl = 0;
  pSacl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 0xFu, &ppsidOwner, &psidGroup, &pDacl, &pSacl, &hMem);
  v4 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v4 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v4 >= 0 )
  {
    v4 = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 0xC000000F, ppsidOwner, psidGroup, pDacl, pSacl);
    LocalFree(hMem);
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800089c4  mov     r11, rsp
0x1800089c7  mov     [r11+8], rbx
0x1800089cb  mov     [r11+10h], rdi
0x1800089cf  push    rbp
0x1800089d0  mov     rbp, rsp
0x1800089d3  sub     rsp, 60h
0x1800089d7  lea     rax, [rbp+hMem]
0x1800089db  mov     [rbp+ppsidOwner], 0
0x1800089e3  mov     [r11-30h], rax
0x1800089e7  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x1800089eb  lea     rax, [rbp+arg_10]
0x1800089ef  mov     [rbp+var_20], 0
0x1800089f7  mov     [r11-38h], rax
0x1800089fb  mov     rdi, rdx
0x1800089fe  mov     edx, 1; ObjectType
0x180008a03  mov     [rbp+arg_18], 0
0x180008a0b  lea     rax, [rbp+arg_18]
0x180008a0f  mov     [rbp+arg_10], 0
0x180008a17  mov     [r11-40h], rax
0x180008a1b  lea     rax, [rbp+var_20]
0x180008a1f  mov     [r11-48h], rax
0x180008a23  lea     r8d, [rdx+0Eh]; SecurityInfo
0x180008a27  mov     [rbp+hMem], 0
0x180008a2f  call    cs:__imp_GetNamedSecurityInfoW
0x180008a35  mov     ebx, eax
0x180008a37  test    eax, eax
0x180008a39  jle     short loc_180008A44
0x180008a3b  movzx   ebx, ax
0x180008a3e  or      ebx, 80070000h
0x180008a44  test    ebx, ebx
0x180008a46  js      short loc_180008A94
0x180008a48  mov     rax, [rbp+arg_10]
0x180008a4c  mov     edx, 1; ObjectType
0x180008a51  mov     r9, [rbp+ppsidOwner]; psidOwner
0x180008a55  mov     r8d, 0C000000Fh; SecurityInfo
0x180008a5b  mov     [rsp+60h+pSacl], rax; pSacl
0x180008a60  mov     rcx, rdi; pObjectName
0x180008a63  mov     rax, [rbp+arg_18]
0x180008a67  mov     [rsp+60h+pDacl], rax; pDacl
0x180008a6c  mov     rax, [rbp+var_20]
0x180008a70  mov     [rsp+60h+psidGroup], rax; psidGroup
0x180008a75  call    cs:__imp_SetNamedSecurityInfoW
0x180008a7b  mov     rcx, [rbp+hMem]; hMem
0x180008a7f  mov     ebx, eax
0x180008a81  call    cs:__imp_LocalFree
0x180008a87  test    ebx, ebx
0x180008a89  jle     short loc_180008A94
0x180008a8b  movzx   ebx, bx
0x180008a8e  or      ebx, 80070000h
0x180008a94  mov     rdi, [rsp+60h+arg_8]
0x180008a99  mov     eax, ebx
0x180008a9b  mov     rbx, [rsp+60h+arg_0]
0x180008aa0  add     rsp, 60h
0x180008aa4  pop     rbp
0x180008aa5  retn
```
