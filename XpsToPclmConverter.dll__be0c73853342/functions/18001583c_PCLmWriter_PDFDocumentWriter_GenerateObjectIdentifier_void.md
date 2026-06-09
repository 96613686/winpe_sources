# PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(void)

- ea: `0x18001583c`
- end: `0x1800158dd`
- name: `?GenerateObjectIdentifier@PDFDocumentWriter@PCLmWriter@@QEAA?AU?$pair@II@std@@XZ`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180014a14`
- `0x1800158e4`
- `0x180017418`

## callees

- `0x1800015f0`
- `0x180002154`
- `0x18000f3e0`
- `0x180010718`
- `0x180011600`
- `0x18001583c`

## string_xrefs

- `0x180015862`: `Maximum object count reached, new objects cannot be created`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(__int64 a1, _DWORD *a2)
{
  int v2; // eax
  _BYTE v4[32]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+40h] [rbp-58h] BYREF

  v2 = *(_DWORD *)(a1 + 72);
  if ( v2 == 0x7FFFFF )
  {
    std::string::string(v4, "Maximum object count reached, new objects cannot be created");
    PCLmWriter::Exception::Exception((std::exception *)pExceptionObject);
    std::string::_Tidy_deallocate(v4);
    pExceptionObject[0] = &PCLmWriter::ObjectIdGenerationException::`vftable';
    throw (PCLmWriter::ObjectIdGenerationException *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 72) = v2 + 1;
  *a2 = v2;
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x18001583c  sub     rsp, 98h
0x180015843  mov     rax, cs:__security_cookie
0x18001584a  xor     rax, rsp
0x18001584d  mov     [rsp+98h+var_18], rax
0x180015855  mov     r8, rcx
0x180015858  mov     eax, [rcx+48h]
0x18001585b  cmp     eax, 7FFFFFh
0x180015860  jnz     short loc_1800158B2
0x180015862  lea     rdx, aMaximumObjectC; "Maximum object count reached, new objec"...
0x180015869  lea     rcx, [rsp+98h+var_78]
0x18001586e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180015873  nop
0x180015874  mov     r8d, 80004005h
0x18001587a  lea     rdx, [rsp+98h+var_78]
0x18001587f  lea     rcx, [rsp+98h+pExceptionObject]; this
0x180015884  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x180015889  nop
0x18001588a  lea     rcx, [rsp+98h+var_78]
0x18001588f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015894  lea     rax, ??_7ObjectIdGenerationException@PCLmWriter@@6B@; const PCLmWriter::ObjectIdGenerationException::`vftable'
0x18001589b  mov     [rsp+98h+pExceptionObject], rax
0x1800158a0  lea     rdx, _TI3?AVObjectIdGenerationException@PCLmWriter@@; pThrowInfo
0x1800158a7  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800158ac  call    _CxxThrowException_0
0x1800158b2  lea     ecx, [rax+1]
0x1800158b5  mov     [r8+48h], ecx
0x1800158b9  mov     [rdx], eax
0x1800158bb  mov     dword ptr [rdx+4], 0
0x1800158c2  mov     rax, rdx
0x1800158c5  mov     rcx, [rsp+98h+var_18]
0x1800158cd  xor     rcx, rsp; StackCookie
0x1800158d0  call    __security_check_cookie
0x1800158d5  add     rsp, 98h
0x1800158dc  retn
```
