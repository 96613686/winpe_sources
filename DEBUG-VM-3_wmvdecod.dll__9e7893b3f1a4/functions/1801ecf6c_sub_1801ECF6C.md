# sub_1801ECF6C

- ea: `0x1801ecf6c`
- end: `0x1801ed04c`
- name: `sub_1801ECF6C`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c5b28`
- `0x1800c5ff8`

## callees

- `0x1800ad3e0`
- `0x1801ecf6c`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1801ed000`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1801ed000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ed010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ed010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ecf8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ecf8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ed02e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ed02e`

## pseudocode

```c
__int64 __fastcall sub_1801ECF6C(HCRYPTPROV *a1, const void *a2, unsigned int a3, int a4, HCRYPTKEY *phKey)
{
  size_t v5; // rsi
  DWORD v9; // ebp
  BYTE *v10; // rax
  BYTE *v11; // rdi
  unsigned int v12; // ebx
  signed int LastError; // eax

  v5 = a3;
  v9 = a3 + 20;
  v10 = (BYTE *)CoTaskMemAlloc(a3 + 20);
  v11 = v10;
  if ( v10 )
  {
    *(_WORD *)v10 = 518;
    *((_DWORD *)v10 + 1) = 41984;
    *((_WORD *)v10 + 1) = 0;
    *((_DWORD *)v10 + 2) = 826364754;
    *((_DWORD *)v10 + 3) = 8 * v5;
    v12 = 0;
    *((_DWORD *)v10 + 4) = a4;
    memcpy(v10 + 20, a2, v5);
    if ( !CryptImportKey(*a1, v11, v9, 0, 0, phKey) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    CoTaskMemFree(v11);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v12;
}

```

## disassembly

```asm
0x1801ecf6c  push    rbx
0x1801ecf6e  push    rbp
0x1801ecf6f  push    rsi
0x1801ecf70  push    rdi
0x1801ecf71  push    r12
0x1801ecf73  push    r14
0x1801ecf75  push    r15
0x1801ecf77  sub     rsp, 30h
0x1801ecf7b  mov     esi, r8d
0x1801ecf7e  mov     r12, rcx
0x1801ecf81  mov     r14d, r9d
0x1801ecf84  mov     r15, rdx
0x1801ecf87  lea     ebp, [rsi+14h]
0x1801ecf8a  mov     ecx, ebp; cb
0x1801ecf8c  call    cs:CoTaskMemAlloc
0x1801ecf93  nop     dword ptr [rax+rax+00h]
0x1801ecf98  mov     rdi, rax
0x1801ecf9b  test    rax, rax
0x1801ecf9e  jnz     short loc_1801ECFAA
0x1801ecfa0  mov     ebx, 8007000Eh
0x1801ecfa5  jmp     loc_1801ED03A
0x1801ecfaa  mov     word ptr [rax], 206h
0x1801ecfaf  lea     rcx, [rdi+14h]; void *
0x1801ecfb3  xor     eax, eax
0x1801ecfb5  mov     dword ptr [rdi+4], 0A400h
0x1801ecfbc  mov     [rdi+2], ax
0x1801ecfc0  mov     r8, rsi; Size
0x1801ecfc3  lea     eax, ds:0[rsi*8]
0x1801ecfca  mov     dword ptr [rdi+8], 31415352h
0x1801ecfd1  mov     rdx, r15; Src
0x1801ecfd4  mov     [rdi+0Ch], eax
0x1801ecfd7  xor     ebx, ebx
0x1801ecfd9  mov     [rdi+10h], r14d
0x1801ecfdd  call    memcpy
0x1801ecfe2  mov     rax, [rsp+68h+arg_20]
0x1801ecfea  xor     r9d, r9d; hPubKey
0x1801ecfed  mov     rcx, [r12]; hProv
0x1801ecff1  mov     r8d, ebp; dwDataLen
0x1801ecff4  mov     [rsp+68h+phKey], rax; phKey
0x1801ecff9  mov     rdx, rdi; pbData
0x1801ecffc  mov     [rsp+68h+dwFlags], ebx; dwFlags
0x1801ed000  call    cs:CryptImportKey
0x1801ed007  nop     dword ptr [rax+rax+00h]
0x1801ed00c  test    eax, eax
0x1801ed00e  jnz     short loc_1801ED02B
0x1801ed010  call    cs:GetLastError
0x1801ed017  nop     dword ptr [rax+rax+00h]
0x1801ed01c  mov     ebx, eax
0x1801ed01e  test    eax, eax
0x1801ed020  jle     short loc_1801ED02B
0x1801ed022  movzx   ebx, ax
0x1801ed025  or      ebx, 80070000h
0x1801ed02b  mov     rcx, rdi; pv
0x1801ed02e  call    cs:CoTaskMemFree
0x1801ed035  nop     dword ptr [rax+rax+00h]
0x1801ed03a  mov     eax, ebx
0x1801ed03c  add     rsp, 30h
0x1801ed040  pop     r15
0x1801ed042  pop     r14
0x1801ed044  pop     r12
0x1801ed046  pop     rdi
0x1801ed047  pop     rsi
0x1801ed048  pop     rbp
0x1801ed049  pop     rbx
0x1801ed04a  retn
```
