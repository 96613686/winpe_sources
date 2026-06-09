# IIS_CRYPTO_BASE::SafeImportSessionKeyBlob(unsigned __int64 *,_IIS_CRYPTO_BLOB *,unsigned __int64,unsigned __int64)

- ea: `0x180005528`
- end: `0x1800055c8`
- name: `?SafeImportSessionKeyBlob@IIS_CRYPTO_BASE@@KAJPEA_KPEFAU_IIS_CRYPTO_BLOB@@_K2@Z`
- size: `160`
- prototype: `__int64 __fastcall(unsigned __int64 *, struct _IIS_CRYPTO_BLOB *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004f68`
- `0x180005aac`

## callees

- `0x18000534c`
- `0x180005528`
- `0x1800055d0`
- `0x180006508`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800055a9`
- `KERNEL32!CloseHandle` at `0x1800055a9`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::SafeImportSessionKeyBlob(unsigned __int64 *a1, struct _IIS_CRYPTO_BLOB *a2)
{
  int v3; // ebx
  int v4; // eax
  HANDLE hObject; // [rsp+20h] [rbp-38h] BYREF
  HCRYPTKEY phKey[6]; // [rsp+28h] [rbp-30h] BYREF

  phKey[0] = 0;
  hObject = 0;
  v3 = IISCryptoImportSessionKeyBlob(phKey);
  if ( v3 >= 0 )
    goto LABEL_9;
  if ( (int)IIS_CRYPTO_BASE::GetThreadImpersonationToken(&hObject) >= 0 && hObject )
  {
    if ( (int)IIS_CRYPTO_BASE::SetThreadImpersonationToken(0) >= 0 )
    {
      v4 = IISCryptoImportSessionKeyBlob(phKey);
      if ( v4 >= 0 )
        v3 = v4;
      IIS_CRYPTO_BASE::SetThreadImpersonationToken(hObject);
    }
    CloseHandle(hObject);
    if ( v3 >= 0 )
LABEL_9:
      *a1 = phKey[0];
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180005528  push    rbx
0x18000552a  push    rbp
0x18000552b  push    rsi
0x18000552c  push    rdi
0x18000552d  push    r14
0x18000552f  sub     rsp, 30h
0x180005533  mov     rdi, rcx
0x180005536  mov     [rsp+58h+phKey], 0
0x18000553f  lea     rcx, [rsp+58h+phKey]; phKey
0x180005544  mov     [rsp+58h+hObject], 0
0x18000554d  mov     rsi, r9
0x180005550  mov     rbp, r8
0x180005553  mov     r14, rdx
0x180005556  call    IISCryptoImportSessionKeyBlob
0x18000555b  mov     ebx, eax
0x18000555d  test    eax, eax
0x18000555f  jns     short loc_1800055B3
0x180005561  lea     rcx, [rsp+58h+hObject]; TokenHandle
0x180005566  call    ?GetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAPEAX@Z; IIS_CRYPTO_BASE::GetThreadImpersonationToken(void * *)
0x18000556b  test    eax, eax
0x18000556d  js      short loc_1800055BB
0x18000556f  cmp     [rsp+58h+hObject], 0
0x180005575  jz      short loc_1800055BB
0x180005577  xor     ecx, ecx; Token
0x180005579  call    ?SetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAX@Z; IIS_CRYPTO_BASE::SetThreadImpersonationToken(void *)
0x18000557e  test    eax, eax
0x180005580  js      short loc_1800055A4
0x180005582  mov     r9, rsi
0x180005585  lea     rcx, [rsp+58h+phKey]; phKey
0x18000558a  mov     r8, rbp
0x18000558d  mov     rdx, r14
0x180005590  call    IISCryptoImportSessionKeyBlob
0x180005595  mov     rcx, [rsp+58h+hObject]; Token
0x18000559a  test    eax, eax
0x18000559c  cmovns  ebx, eax
0x18000559f  call    ?SetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAX@Z; IIS_CRYPTO_BASE::SetThreadImpersonationToken(void *)
0x1800055a4  mov     rcx, [rsp+58h+hObject]; hObject
0x1800055a9  call    cs:__imp_CloseHandle
0x1800055af  test    ebx, ebx
0x1800055b1  js      short loc_1800055BB
0x1800055b3  mov     rax, [rsp+58h+phKey]
0x1800055b8  mov     [rdi], rax
0x1800055bb  mov     eax, ebx
0x1800055bd  add     rsp, 30h
0x1800055c1  pop     r14
0x1800055c3  pop     rdi
0x1800055c4  pop     rsi
0x1800055c5  pop     rbp
0x1800055c6  pop     rbx
0x1800055c7  retn
```
