# GetSecurityDescriptor

- ea: `0x40865e`
- end: `0x4086fe`
- name: `GetSecurityDescriptor`
- size: `160`
- prototype: `unsigned int __fastcall(HANDLE Handle, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x40895f`

## callees

- `0x40865e`

## import_xrefs

- `ADVAPI32!GetKernelObjectSecurity` at `0x408682`
- `ADVAPI32!GetKernelObjectSecurity` at `0x4086d7`
- `ADVAPI32!GetKernelObjectSecurity` at `0x408682`
- `ADVAPI32!GetKernelObjectSecurity` at `0x4086d7`
- `KERNEL32!LocalAlloc` at `0x4086ae`
- `KERNEL32!LocalAlloc` at `0x4086ae`
- `KERNEL32!LocalFree` at `0x4086c2`
- `KERNEL32!LocalFree` at `0x4086c2`
- `KERNEL32!GetLastError` at `0x40868e`
- `KERNEL32!GetLastError` at `0x4086e1`
- `KERNEL32!GetLastError` at `0x40868e`
- `KERNEL32!GetLastError` at `0x4086e1`

## pseudocode

```c
unsigned int __fastcall GetSecurityDescriptor(HANDLE Handle, _DWORD *a2)
{
  unsigned int v3; // esi
  signed int LastError; // eax
  HLOCAL v5; // edi
  signed int v6; // eax
  DWORD nLengthNeeded; // [esp+10h] [ebp-4h] BYREF

  nLengthNeeded = 0;
  v3 = -2147418113;
  if ( !GetKernelObjectSecurity(Handle, 7u, 0, 0, &nLengthNeeded) )
  {
    v3 = 0;
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
      goto LABEL_8;
    }
    v5 = LocalAlloc(0x40u, nLengthNeeded);
    if ( !v5 )
    {
      v3 = -2147024882;
LABEL_8:
      *a2 = 0;
      LocalFree(0);
      return v3;
    }
    if ( !GetKernelObjectSecurity(Handle, 7u, v5, nLengthNeeded, &nLengthNeeded) )
    {
      v6 = GetLastError();
      v3 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v3 = v6;
    }
    *a2 = v5;
  }
  return v3;
}

```

## disassembly

```asm
0x40865e  mov     edi, edi
0x408660  push    ebp
0x408661  mov     ebp, esp
0x408663  push    ecx
0x408664  push    ecx
0x408665  push    ebx
0x408666  push    esi
0x408667  push    edi
0x408668  mov     eax, ecx
0x40866a  xor     edi, edi
0x40866c  lea     ecx, [ebp+nLengthNeeded]
0x40866f  mov     [ebp+Handle], eax
0x408672  push    ecx; lpnLengthNeeded
0x408673  push    edi; nLength
0x408674  push    edi; pSecurityDescriptor
0x408675  push    7; RequestedInformation
0x408677  push    eax; Handle
0x408678  mov     ebx, edx
0x40867a  mov     [ebp+nLengthNeeded], edi
0x40867d  mov     esi, 8000FFFFh
0x408682  call    ds:__imp__GetKernelObjectSecurity@20; GetKernelObjectSecurity(x,x,x,x,x)
0x408688  test    eax, eax
0x40868a  jnz     short loc_4086F7
0x40868c  mov     esi, edi
0x40868e  call    ds:__imp__GetLastError@0; GetLastError()
0x408694  cmp     eax, 7Ah ; 'z'
0x408697  jz      short loc_4086A9
0x408699  movzx   esi, ax
0x40869c  or      esi, 80070000h
0x4086a2  test    eax, eax
0x4086a4  cmovle  esi, eax
0x4086a7  jmp     short loc_4086BF
0x4086a9  push    [ebp+nLengthNeeded]; uBytes
0x4086ac  push    40h ; '@'; uFlags
0x4086ae  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x4086b4  mov     edi, eax
0x4086b6  test    edi, edi
0x4086b8  jnz     short loc_4086CA
0x4086ba  mov     esi, 8007000Eh
0x4086bf  push    edi; hMem
0x4086c0  mov     [ebx], edi
0x4086c2  call    ds:__imp__LocalFree@4; LocalFree(x)
0x4086c8  jmp     short loc_4086F7
0x4086ca  lea     eax, [ebp+nLengthNeeded]
0x4086cd  push    eax; lpnLengthNeeded
0x4086ce  push    [ebp+nLengthNeeded]; nLength
0x4086d1  push    edi; pSecurityDescriptor
0x4086d2  push    7; RequestedInformation
0x4086d4  push    [ebp+Handle]; Handle
0x4086d7  call    ds:__imp__GetKernelObjectSecurity@20; GetKernelObjectSecurity(x,x,x,x,x)
0x4086dd  test    eax, eax
0x4086df  jnz     short loc_4086F5
0x4086e1  call    ds:__imp__GetLastError@0; GetLastError()
0x4086e7  movzx   esi, ax
0x4086ea  or      esi, 80070000h
0x4086f0  test    eax, eax
0x4086f2  cmovle  esi, eax
0x4086f5  mov     [ebx], edi
0x4086f7  pop     edi
0x4086f8  mov     eax, esi
0x4086fa  pop     esi
0x4086fb  pop     ebx
0x4086fc  leave
0x4086fd  retn
```
