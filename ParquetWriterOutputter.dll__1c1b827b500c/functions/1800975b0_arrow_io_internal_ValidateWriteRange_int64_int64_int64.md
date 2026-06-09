# arrow::io::internal::ValidateWriteRange(__int64,__int64,__int64)

- ea: `0x1800975b0`
- end: `0x18009773f`
- name: `?ValidateWriteRange@internal@io@arrow@@YA?AVStatus@3@_J00@Z`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800a0d40`
- `0x1800a0e50`

## callees

- `0x180086fc0`
- `0x180095970`
- `0x1800975b0`
- `0x18009a010`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800976be`: `Invalid write (offset = `
- `0x18009762e`: `Write out of bounds (offset = `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::io::internal::ValidateWriteRange(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v12; // [rsp+40h] [rbp-58h] BYREF
  __int64 v13; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v15[3]; // [rsp+60h] [rbp-38h] BYREF
  unsigned __int64 v16; // [rsp+78h] [rbp-20h]

  v14[1] = -2;
  v13 = a2;
  v12 = a3;
  v14[0] = a4;
  if ( a2 < 0 || a3 < 0 )
  {
    v9 = arrow::util::StringBuilder<char const (&)[27],__int64 &,char const (&)[20],__int64,char const (&)[6]>(
           (unsigned int)v15,
           (unsigned int)"Invalid write (offset = ",
           (unsigned int)&v13,
           (unsigned int)", size = ",
           (__int64)&v12,
           (__int64)")");
    LOBYTE(v10) = 4;
    arrow::Status::Status(a1, v10, v9);
    if ( v16 >= 0x10 )
    {
      v7 = v16 + 1;
      v8 = (void *)v15[0];
      if ( v16 + 1 >= 0x1000 )
      {
        v7 = v16 + 40;
        v8 = *(void **)(v15[0] - 8LL);
        if ( (unsigned __int64)(v15[0] - (_QWORD)v8 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      goto LABEL_12;
    }
  }
  else if ( a2 + a3 <= a4 )
  {
    *(_QWORD *)(a1 + 8) = 0;
  }
  else
  {
    v5 = arrow::util::StringBuilder<char const (&)[30],__int64 &,char const (&)[10],__int64 &,char const (&)[19],__int64 &>(
           (unsigned int)v15,
           (unsigned int)"Write out of bounds (offset = ",
           (unsigned int)&v13,
           (unsigned int)", size = ",
           (__int64)&v12,
           (__int64)") in file of size ",
           (__int64)v14);
    LOBYTE(v6) = 5;
    arrow::Status::Status(a1, v6, v5);
    if ( v16 >= 0x10 )
    {
      v7 = v16 + 1;
      v8 = (void *)v15[0];
      if ( v16 + 1 >= 0x1000 )
      {
        v7 = v16 + 40;
        v8 = *(void **)(v15[0] - 8LL);
        if ( (unsigned __int64)(v15[0] - (_QWORD)v8 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
LABEL_12:
      operator delete(v8, v7);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800975b0  mov     r11, rsp
0x1800975b3  push    rbx
0x1800975b4  sub     rsp, 90h
0x1800975bb  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1800975c3  mov     rax, cs:__security_cookie
0x1800975ca  xor     rax, rsp
0x1800975cd  mov     [rsp+98h+var_18], rax
0x1800975d5  mov     rbx, rcx
0x1800975d8  mov     [rsp+98h+var_48], rcx
0x1800975dd  mov     [r11-50h], rdx
0x1800975e1  mov     [r11-58h], r8
0x1800975e5  mov     [r11-48h], r9
0x1800975e9  test    rdx, rdx
0x1800975ec  js      loc_18009769C
0x1800975f2  test    r8, r8
0x1800975f5  js      loc_18009769C
0x1800975fb  lea     rax, [rdx+r8]
0x1800975ff  cmp     rax, r9
0x180097602  jle     loc_180097692
0x180097608  lea     rax, [r11-48h]
0x18009760c  mov     [r11-68h], rax
0x180097610  lea     rax, aInFileOfSize; ") in file of size "
0x180097617  mov     [r11-70h], rax
0x18009761b  lea     rax, [r11-58h]
0x18009761f  mov     [r11-78h], rax
0x180097623  lea     r9, aSize; ", size = "
0x18009762a  lea     r8, [r11-50h]
0x18009762e  lea     rdx, aWriteOutOfBoun; "Write out of bounds (offset = "
0x180097635  lea     rcx, [r11-38h]
0x180097639  call    ??$StringBuilder@AEAY0BO@$$CBDAEA_JAEAY09$$CBDAEA_JAEAY0BD@$$CBDAEA_J@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0BO@$$CBDAEA_JAEAY09$$CBD1AEAY0BD@$$CBD1@Z; arrow::util::StringBuilder<char const (&)[30],__int64 &,char const (&)[10],__int64 &,char const (&)[19],__int64 &>(char const (&)[30],__int64 &,char const (&)[10],__int64 &,char const (&)[19],__int64 &)
0x18009763e  nop
0x18009763f  mov     r8, rax
0x180097642  mov     dl, 5
0x180097644  mov     rcx, rbx
0x180097647  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009764c  nop
0x18009764d  mov     rdx, [rsp+98h+var_20]
0x180097652  cmp     rdx, 10h
0x180097656  jb      loc_180097717
0x18009765c  inc     rdx
0x18009765f  mov     rcx, [rsp+98h+var_38]
0x180097664  mov     rax, rcx
0x180097667  cmp     rdx, 1000h
0x18009766e  jb      loc_180097712
0x180097674  add     rdx, 27h ; '''
0x180097678  mov     rcx, [rcx-8]
0x18009767c  sub     rax, rcx
0x18009767f  add     rax, 0FFFFFFFFFFFFFFF8h
0x180097683  cmp     rax, 1Fh
0x180097687  ja      loc_180097739
0x18009768d  jmp     loc_180097712
0x180097692  mov     qword ptr [rcx+8], 0
0x18009769a  jmp     short loc_180097717
0x18009769c  lea     rax, asc_180375DE0; ")"
0x1800976a3  mov     [rsp+98h+var_70], rax
0x1800976a8  lea     rax, [rsp+98h+var_58]
0x1800976ad  mov     [rsp+98h+var_78], rax
0x1800976b2  lea     r9, aSize; ", size = "
0x1800976b9  lea     r8, [rsp+98h+var_50]
0x1800976be  lea     rdx, aInvalidWriteOf; "Invalid write (offset = "
0x1800976c5  lea     rcx, [rsp+98h+var_38]
0x1800976ca  call    ??$StringBuilder@AEAY0BL@$$CBDAEA_JAEAY0BE@$$CBD_JAEAY05$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0BL@$$CBDAEA_JAEAY0BE@$$CBD$$QEA_JAEAY05$$CBD@Z; arrow::util::StringBuilder<char const (&)[27],__int64 &,char const (&)[20],__int64,char const (&)[6]>(char const (&)[27],__int64 &,char const (&)[20],__int64 &&,char const (&)[6])
0x1800976cf  nop
0x1800976d0  mov     r8, rax
0x1800976d3  mov     dl, 4
0x1800976d5  mov     rcx, rbx
0x1800976d8  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800976dd  nop
0x1800976de  mov     rdx, [rsp+98h+var_20]
0x1800976e3  cmp     rdx, 10h
0x1800976e7  jb      short loc_180097717
0x1800976e9  inc     rdx
0x1800976ec  mov     rcx, [rsp+98h+var_38]
0x1800976f1  mov     rax, rcx
0x1800976f4  cmp     rdx, 1000h
0x1800976fb  jb      short loc_180097712
0x1800976fd  add     rdx, 27h ; '''; unsigned __int64
0x180097701  mov     rcx, [rcx-8]; void *
0x180097705  sub     rax, rcx
0x180097708  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009770c  cmp     rax, 1Fh
0x180097710  ja      short loc_180097733
0x180097712  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180097717  mov     rax, rbx
0x18009771a  mov     rcx, [rsp+98h+var_18]
0x180097722  xor     rcx, rsp; StackCookie
0x180097725  call    __security_check_cookie
0x18009772a  add     rsp, 90h
0x180097731  pop     rbx
0x180097732  retn
0x180097733  call    _invalid_parameter_noinfo_noreturn
0x180097739  call    _invalid_parameter_noinfo_noreturn
```
