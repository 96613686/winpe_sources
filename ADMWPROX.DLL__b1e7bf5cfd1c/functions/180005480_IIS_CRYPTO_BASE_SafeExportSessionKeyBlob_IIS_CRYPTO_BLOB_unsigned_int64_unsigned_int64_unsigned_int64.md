# IIS_CRYPTO_BASE::SafeExportSessionKeyBlob(_IIS_CRYPTO_BLOB * *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180005480`
- end: `0x180005520`
- name: `?SafeExportSessionKeyBlob@IIS_CRYPTO_BASE@@KAJPEAPEFAU_IIS_CRYPTO_BLOB@@_K11@Z`
- size: `160`
- prototype: `__int64 __fastcall(struct _IIS_CRYPTO_BLOB **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004f68`
- `0x180005988`

## callees

- `0x18000534c`
- `0x180005480`
- `0x1800055d0`
- `0x180006104`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005501`
- `KERNEL32!CloseHandle` at `0x180005501`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::SafeExportSessionKeyBlob(struct _IIS_CRYPTO_BLOB **a1)
{
  int v2; // ebx
  int v3; // eax
  HANDLE hObject; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v6[6]; // [rsp+28h] [rbp-30h] BYREF

  v6[0] = 0;
  hObject = 0;
  v2 = IISCryptoExportSessionKeyBlob(v6);
  if ( v2 >= 0 )
    goto LABEL_9;
  if ( (int)IIS_CRYPTO_BASE::GetThreadImpersonationToken(&hObject) >= 0 && hObject )
  {
    if ( (int)IIS_CRYPTO_BASE::SetThreadImpersonationToken(0) >= 0 )
    {
      v3 = IISCryptoExportSessionKeyBlob(v6);
      if ( v3 >= 0 )
        v2 = v3;
      IIS_CRYPTO_BASE::SetThreadImpersonationToken(hObject);
    }
    CloseHandle(hObject);
    if ( v2 >= 0 )
LABEL_9:
      *a1 = (struct _IIS_CRYPTO_BLOB *)v6[0];
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180005480  push    rbx
0x180005482  push    rbp
0x180005483  push    rsi
0x180005484  push    rdi
0x180005485  push    r14
0x180005487  sub     rsp, 30h
0x18000548b  mov     rdi, rcx
0x18000548e  mov     [rsp+58h+var_30], 0
0x180005497  lea     rcx, [rsp+58h+var_30]
0x18000549c  mov     [rsp+58h+hObject], 0
0x1800054a5  mov     rsi, r9
0x1800054a8  mov     rbp, r8
0x1800054ab  mov     r14, rdx
0x1800054ae  call    IISCryptoExportSessionKeyBlob
0x1800054b3  mov     ebx, eax
0x1800054b5  test    eax, eax
0x1800054b7  jns     short loc_18000550B
0x1800054b9  lea     rcx, [rsp+58h+hObject]; TokenHandle
0x1800054be  call    ?GetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAPEAX@Z; IIS_CRYPTO_BASE::GetThreadImpersonationToken(void * *)
0x1800054c3  test    eax, eax
0x1800054c5  js      short loc_180005513
0x1800054c7  cmp     [rsp+58h+hObject], 0
0x1800054cd  jz      short loc_180005513
0x1800054cf  xor     ecx, ecx; Token
0x1800054d1  call    ?SetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAX@Z; IIS_CRYPTO_BASE::SetThreadImpersonationToken(void *)
0x1800054d6  test    eax, eax
0x1800054d8  js      short loc_1800054FC
0x1800054da  mov     r9, rsi
0x1800054dd  lea     rcx, [rsp+58h+var_30]
0x1800054e2  mov     r8, rbp
0x1800054e5  mov     rdx, r14
0x1800054e8  call    IISCryptoExportSessionKeyBlob
0x1800054ed  mov     rcx, [rsp+58h+hObject]; Token
0x1800054f2  test    eax, eax
0x1800054f4  cmovns  ebx, eax
0x1800054f7  call    ?SetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAX@Z; IIS_CRYPTO_BASE::SetThreadImpersonationToken(void *)
0x1800054fc  mov     rcx, [rsp+58h+hObject]; hObject
0x180005501  call    cs:__imp_CloseHandle
0x180005507  test    ebx, ebx
0x180005509  js      short loc_180005513
0x18000550b  mov     rax, [rsp+58h+var_30]
0x180005510  mov     [rdi], rax
0x180005513  mov     eax, ebx
0x180005515  add     rsp, 30h
0x180005519  pop     r14
0x18000551b  pop     rdi
0x18000551c  pop     rsi
0x18000551d  pop     rbp
0x18000551e  pop     rbx
0x18000551f  retn
```
