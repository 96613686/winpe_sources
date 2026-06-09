# SuInitializeDriveTemplateList_VerifyDisks

- ea: `0x140015b5c`
- end: `0x140015bf4`
- name: `SuInitializeDriveTemplateList_VerifyDisks`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001593c`

## callees

- `0x140015b5c`
- `0x140015e10`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140015bdb`
- `KERNEL32!SetLastError` at `0x140015bdb`
- `KERNEL32!GetLastError` at `0x140015ba6`
- `KERNEL32!GetLastError` at `0x140015ba6`

## pseudocode

```c
__int64 __fastcall SuInitializeDriveTemplateList_VerifyDisks(int a1, int a2, int *a3, DWORD *a4, _DWORD *a5)
{
  int v7; // esi
  unsigned int v9; // ebx
  DWORD v10; // edi
  int i; // ebp
  int v12; // edx
  int v13; // r15d
  DWORD LastError; // eax
  BOOL v16; // [rsp+78h] [rbp+10h] BYREF

  v7 = a2;
  v9 = a2 == 0;
  v10 = 0;
  for ( i = 0; v7; --v7 )
  {
    v12 = *a3;
    v16 = 0;
    v13 = SuInitializeDriveTemplate_VerifyDisk(a1, v12, &v16);
    if ( v13 )
      LastError = 0;
    else
      LastError = GetLastError();
    v9 |= v13;
    *a4 = LastError;
    if ( v10 )
      LastError = v10;
    i |= v16;
    ++a3;
    ++a4;
    v10 = LastError;
  }
  *a5 = i;
  SetLastError(v10);
  return v9;
}

```

## disassembly

```asm
0x140015b5c  push    rbx
0x140015b5e  push    rbp
0x140015b5f  push    rsi
0x140015b60  push    rdi
0x140015b61  push    r12
0x140015b63  push    r13
0x140015b65  push    r14
0x140015b67  push    r15
0x140015b69  sub     rsp, 28h
0x140015b6d  xor     ebx, ebx
0x140015b6f  mov     r12, r9
0x140015b72  test    edx, edx
0x140015b74  mov     r14, r8
0x140015b77  mov     esi, edx
0x140015b79  mov     r13d, ecx
0x140015b7c  setz    bl
0x140015b7f  xor     edi, edi
0x140015b81  xor     ebp, ebp
0x140015b83  test    edx, edx
0x140015b85  jz      short loc_140015BCF
0x140015b87  mov     edx, [r14]
0x140015b8a  lea     r8, [rsp+68h+arg_8]
0x140015b8f  mov     ecx, r13d
0x140015b92  mov     [rsp+68h+arg_8], 0
0x140015b9a  call    SuInitializeDriveTemplate_VerifyDisk
0x140015b9f  mov     r15d, eax
0x140015ba2  test    eax, eax
0x140015ba4  jnz     short loc_140015BAE
0x140015ba6  call    cs:__imp_GetLastError
0x140015bac  jmp     short loc_140015BB0
0x140015bae  xor     eax, eax
0x140015bb0  or      ebx, r15d
0x140015bb3  mov     [r12], eax
0x140015bb7  test    edi, edi
0x140015bb9  cmovnz  eax, edi
0x140015bbc  or      ebp, [rsp+68h+arg_8]
0x140015bc0  add     r14, 4
0x140015bc4  add     r12, 4
0x140015bc8  mov     edi, eax
0x140015bca  add     esi, 0FFFFFFFFh
0x140015bcd  jnz     short loc_140015B87
0x140015bcf  mov     rdx, [rsp+68h+arg_20]
0x140015bd7  mov     ecx, edi; dwErrCode
0x140015bd9  mov     [rdx], ebp
0x140015bdb  call    cs:__imp_SetLastError
0x140015be1  mov     eax, ebx
0x140015be3  add     rsp, 28h
0x140015be7  pop     r15
0x140015be9  pop     r14
0x140015beb  pop     r13
0x140015bed  pop     r12
0x140015bef  pop     rdi
0x140015bf0  pop     rsi
0x140015bf1  pop     rbp
0x140015bf2  pop     rbx
0x140015bf3  retn
```
