# FwppXmlFileWriterCreate

- ea: `0x180080834`
- end: `0x1800809a6`
- name: `FwppXmlFileWriterCreate`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180076284`

## callees

- `0x1800197d0`
- `0x18003cc48`
- `0x18003cfac`
- `0x180048c60`
- `0x18004c54c`
- `0x18005aa60`
- `0x180080834`
- `0x1800809ac`
- `0x18008a63c`
- `0x18008a754`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800808ee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800808ee`

## string_xrefs

- `0x180080855`: `<?xml version="1.0" encoding="UTF-8" standalone="yes"?>`
- `0x1800808ff`: `FwppXmlFileWriterCreate`

## pseudocode

```c
__int64 __fastcall FwppXmlFileWriterCreate(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v3; // r14d
  const WCHAR *v6; // rcx
  __int64 v7; // rbx
  const WCHAR *v8; // rcx
  __int64 v10; // rsi
  __int64 v11; // [rsp+20h] [rbp-50h] BYREF
  __int64 v12; // [rsp+28h] [rbp-48h] BYREF
  char v13[56]; // [rsp+30h] [rbp-40h] BYREF

  v3 = 0;
  v12 = 0;
  strcpy(v13, "<?xml version=\"1.0\" encoding=\"UTF-8\" standalone=\"yes\"?>");
  v11 = 0;
  if ( (unsigned int)((__int64 (*)(void))FwppIsStdIoPseudoFileName)() )
  {
    v7 = FwppXmlWriterCreate(&FwppWriteUtf8ToStdOut, 0, 0, &v11);
    if ( v7 )
      goto LABEL_3;
  }
  else
  {
    v7 = FwppFileWriterCreate(v6, &v12);
    if ( v7 )
      goto LABEL_3;
    v3 = 1;
    v7 = FwppXmlWriterCreate(FwppFileWriterWrite, v12, 1, &v11);
    if ( v7 )
      goto LABEL_3;
    v12 = 0;
  }
  v10 = v11;
  v7 = FwppXmlPutS(v11, v13);
  if ( !v7 )
  {
    v7 = FwppXmlWriteNewLine(v10);
    if ( !v7 )
    {
      *a3 = v10;
      return v7;
    }
  }
LABEL_3:
  FwppXmlFileWriterDestroy(&v11);
  FwppFileWriterDestroy(&v12);
  if ( v3 && a1 && !(unsigned int)FwppIsStdIoPseudoFileName(a1) )
    DeleteFileW(v8);
  WfpReportError(v7, "FwppXmlFileWriterCreate");
  return v7;
}

```

## disassembly

```asm
0x180080834  mov     [rsp-28h+arg_8], rbx
0x180080839  push    rbp
0x18008083a  push    rsi
0x18008083b  push    rdi
0x18008083c  push    r14
0x18008083e  push    r15
0x180080840  mov     rbp, rsp
0x180080843  sub     rsp, 70h
0x180080847  mov     rax, cs:__security_cookie
0x18008084e  xor     rax, rsp
0x180080851  mov     [rbp+var_8], rax
0x180080855  movups  xmm0, xmmword ptr cs:aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x18008085c  xor     r14d, r14d
0x18008085f  mov     r15, r8
0x180080862  movups  xmm1, xmmword ptr cs:aXmlVersion10En+10h; ".0\" encoding=\"UTF-8\" standalone=\"ye"...
0x180080869  mov     rdi, rcx
0x18008086c  mov     [rbp+var_48], 0
0x180080874  movups  xmmword ptr [rbp+var_40], xmm0
0x180080878  mov     [rbp+var_50], r14
0x18008087c  movups  xmm0, xmmword ptr cs:aXmlVersion10En+20h; "F-8\" standalone=\"yes\"?>"
0x180080883  movups  xmmword ptr [rbp+var_40+10h], xmm1
0x180080887  movsd   xmm1, qword ptr cs:aXmlVersion10En+30h; "\"yes\"?>"
0x18008088f  movups  xmmword ptr [rbp+var_40+20h], xmm0
0x180080893  movsd   qword ptr [rbp+var_40+30h], xmm1
0x180080898  call    FwppIsStdIoPseudoFileName
0x18008089d  test    eax, eax
0x18008089f  jz      loc_180080932
0x1800808a5  lea     r9, [rbp+var_50]
0x1800808a9  xor     r8d, r8d
0x1800808ac  xor     edx, edx
0x1800808ae  lea     rcx, FwppWriteUtf8ToStdOut
0x1800808b5  call    FwppXmlWriterCreate
0x1800808ba  mov     rbx, rax
0x1800808bd  test    rax, rax
0x1800808c0  jz      loc_18008096E
0x1800808c6  lea     rcx, [rbp+var_50]
0x1800808ca  call    FwppXmlFileWriterDestroy
0x1800808cf  lea     rcx, [rbp+var_48]
0x1800808d3  call    FwppFileWriterDestroy
0x1800808d8  test    r14d, r14d
0x1800808db  jz      short loc_1800808FA
0x1800808dd  test    rdi, rdi
0x1800808e0  jz      short loc_1800808FA
0x1800808e2  mov     rcx, rdi
0x1800808e5  call    FwppIsStdIoPseudoFileName
0x1800808ea  test    eax, eax
0x1800808ec  jnz     short loc_1800808FA
0x1800808ee  call    cs:__imp_DeleteFileW
0x1800808f5  nop     dword ptr [rax+rax+00h]
0x1800808fa  test    rbx, rbx
0x1800808fd  jz      short loc_18008090E
0x1800808ff  lea     rdx, aFwppxmlfilewri; "FwppXmlFileWriterCreate"
0x180080906  mov     rcx, rbx
0x180080909  call    WfpReportError
0x18008090e  mov     rax, rbx
0x180080911  mov     rcx, [rbp+var_8]
0x180080915  xor     rcx, rsp; StackCookie
0x180080918  call    __security_check_cookie
0x18008091d  mov     rbx, [rsp+70h+arg_8]
0x180080925  add     rsp, 70h
0x180080929  pop     r15
0x18008092b  pop     r14
0x18008092d  pop     rdi
0x18008092e  pop     rsi
0x18008092f  pop     rbp
0x180080930  retn
0x180080932  lea     rdx, [rbp+var_48]
0x180080936  call    FwppFileWriterCreate
0x18008093b  mov     rbx, rax
0x18008093e  test    rax, rax
0x180080941  jnz     short loc_1800808C6
0x180080943  mov     rdx, [rbp+var_48]
0x180080947  lea     r14d, [rax+1]
0x18008094b  mov     r8d, r14d
0x18008094e  lea     r9, [rbp+var_50]
0x180080952  lea     rcx, FwppFileWriterWrite
0x180080959  call    FwppXmlWriterCreate
0x18008095e  mov     rbx, rax
0x180080961  test    rax, rax
0x180080964  jnz     loc_1800808C6
0x18008096a  mov     [rbp+var_48], rax
0x18008096e  mov     rsi, [rbp+var_50]
0x180080972  lea     rdx, [rbp+var_40]
0x180080976  mov     rcx, rsi
0x180080979  call    FwppXmlPutS
0x18008097e  mov     rbx, rax
0x180080981  test    rax, rax
0x180080984  jnz     loc_1800808C6
0x18008098a  mov     rcx, rsi
0x18008098d  call    FwppXmlWriteNewLine
0x180080992  mov     rbx, rax
0x180080995  test    rax, rax
0x180080998  jnz     loc_1800808C6
0x18008099e  mov     [r15], rsi
0x1800809a1  jmp     loc_18008090E
```
