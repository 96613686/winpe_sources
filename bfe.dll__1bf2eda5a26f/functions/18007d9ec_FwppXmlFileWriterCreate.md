# FwppXmlFileWriterCreate

- ea: `0x18007d9ec`
- end: `0x18007db57`
- name: `FwppXmlFileWriterCreate`
- size: `363`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800738a0`

## callees

- `0x180018b74`
- `0x18003250c`
- `0x18003286c`
- `0x1800474a4`
- `0x18004a6bc`
- `0x180058b30`
- `0x18007d9ec`
- `0x18007db60`
- `0x180087718`
- `0x18008781c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007daa6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007daa6`

## string_xrefs

- `0x18007da0d`: `<?xml version="1.0" encoding="UTF-8" standalone="yes"?>`
- `0x18007dab1`: `FwppXmlFileWriterCreate`

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
0x18007d9ec  mov     [rsp-28h+arg_8], rbx
0x18007d9f1  push    rbp
0x18007d9f2  push    rsi
0x18007d9f3  push    rdi
0x18007d9f4  push    r14
0x18007d9f6  push    r15
0x18007d9f8  mov     rbp, rsp
0x18007d9fb  sub     rsp, 70h
0x18007d9ff  mov     rax, cs:__security_cookie
0x18007da06  xor     rax, rsp
0x18007da09  mov     [rbp+var_8], rax
0x18007da0d  movups  xmm0, xmmword ptr cs:aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x18007da14  xor     r14d, r14d
0x18007da17  mov     r15, r8
0x18007da1a  movups  xmm1, xmmword ptr cs:aXmlVersion10En+10h; ".0\" encoding=\"UTF-8\" standalone=\"ye"...
0x18007da21  mov     rdi, rcx
0x18007da24  mov     [rbp+var_48], 0
0x18007da2c  movups  xmmword ptr [rbp+var_40], xmm0
0x18007da30  mov     [rbp+var_50], r14
0x18007da34  movups  xmm0, xmmword ptr cs:aXmlVersion10En+20h; "F-8\" standalone=\"yes\"?>"
0x18007da3b  movups  xmmword ptr [rbp+var_40+10h], xmm1
0x18007da3f  movsd   xmm1, qword ptr cs:aXmlVersion10En+30h; "\"yes\"?>"
0x18007da47  movups  xmmword ptr [rbp+var_40+20h], xmm0
0x18007da4b  movsd   qword ptr [rbp+var_40+30h], xmm1
0x18007da50  call    FwppIsStdIoPseudoFileName
0x18007da55  test    eax, eax
0x18007da57  jz      loc_18007DAE3
0x18007da5d  lea     r9, [rbp+var_50]
0x18007da61  xor     r8d, r8d
0x18007da64  xor     edx, edx
0x18007da66  lea     rcx, FwppWriteUtf8ToStdOut
0x18007da6d  call    FwppXmlWriterCreate
0x18007da72  mov     rbx, rax
0x18007da75  test    rax, rax
0x18007da78  jz      loc_18007DB1F
0x18007da7e  lea     rcx, [rbp+var_50]
0x18007da82  call    FwppXmlFileWriterDestroy
0x18007da87  lea     rcx, [rbp+var_48]
0x18007da8b  call    FwppFileWriterDestroy
0x18007da90  test    r14d, r14d
0x18007da93  jz      short loc_18007DAAC
0x18007da95  test    rdi, rdi
0x18007da98  jz      short loc_18007DAAC
0x18007da9a  mov     rcx, rdi
0x18007da9d  call    FwppIsStdIoPseudoFileName
0x18007daa2  test    eax, eax
0x18007daa4  jnz     short loc_18007DAAC
0x18007daa6  call    cs:__imp_DeleteFileW
0x18007daac  test    rbx, rbx
0x18007daaf  jz      short loc_18007DAC0
0x18007dab1  lea     rdx, aFwppxmlfilewri; "FwppXmlFileWriterCreate"
0x18007dab8  mov     rcx, rbx
0x18007dabb  call    WfpReportError
0x18007dac0  mov     rax, rbx
0x18007dac3  mov     rcx, [rbp+var_8]
0x18007dac7  xor     rcx, rsp; StackCookie
0x18007daca  call    __security_check_cookie
0x18007dacf  mov     rbx, [rsp+70h+arg_8]
0x18007dad7  add     rsp, 70h
0x18007dadb  pop     r15
0x18007dadd  pop     r14
0x18007dadf  pop     rdi
0x18007dae0  pop     rsi
0x18007dae1  pop     rbp
0x18007dae2  retn
0x18007dae3  lea     rdx, [rbp+var_48]
0x18007dae7  call    FwppFileWriterCreate
0x18007daec  mov     rbx, rax
0x18007daef  test    rax, rax
0x18007daf2  jnz     short loc_18007DA7E
0x18007daf4  mov     rdx, [rbp+var_48]
0x18007daf8  lea     r14d, [rax+1]
0x18007dafc  mov     r8d, r14d
0x18007daff  lea     r9, [rbp+var_50]
0x18007db03  lea     rcx, FwppFileWriterWrite
0x18007db0a  call    FwppXmlWriterCreate
0x18007db0f  mov     rbx, rax
0x18007db12  test    rax, rax
0x18007db15  jnz     loc_18007DA7E
0x18007db1b  mov     [rbp+var_48], rax
0x18007db1f  mov     rsi, [rbp+var_50]
0x18007db23  lea     rdx, [rbp+var_40]
0x18007db27  mov     rcx, rsi
0x18007db2a  call    FwppXmlPutS
0x18007db2f  mov     rbx, rax
0x18007db32  test    rax, rax
0x18007db35  jnz     loc_18007DA7E
0x18007db3b  mov     rcx, rsi
0x18007db3e  call    FwppXmlWriteNewLine
0x18007db43  mov     rbx, rax
0x18007db46  test    rax, rax
0x18007db49  jnz     loc_18007DA7E
0x18007db4f  mov     [r15], rsi
0x18007db52  jmp     loc_18007DAC0
```
