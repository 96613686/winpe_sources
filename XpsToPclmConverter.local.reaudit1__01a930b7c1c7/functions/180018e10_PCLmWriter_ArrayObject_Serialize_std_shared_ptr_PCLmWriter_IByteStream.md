# PCLmWriter::ArrayObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x180018e10`
- end: `0x180018fa3`
- name: `?Serialize@ArrayObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800015f0`
- `0x180002154`
- `0x18000e7c8`
- `0x18000f3e0`
- `0x1800101cc`
- `0x180011600`
- `0x180018e10`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PCLmWriter::ArrayObject::Serialize(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 i; // rbx
  __int64 v5; // rsi
  _QWORD *v6; // rax
  void (__fastcall *v7)(__int64, _QWORD *); // r8
  std::_Ref_count_base *v8; // rcx
  _WORD v9[4]; // [rsp+20h] [rbp-59h] BYREF
  __int64 v10; // [rsp+28h] [rbp-51h] BYREF
  std::_Ref_count_base *v11; // [rsp+30h] [rbp-49h]
  _QWORD *v12; // [rsp+38h] [rbp-41h]
  _QWORD v13[5]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+70h] [rbp-9h] BYREF

  v12 = a2;
  qmemcpy(v9, "[] ", 3);
  (*(void (__fastcall **)(_QWORD, _WORD *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, v9, 1);
  (*(void (__fastcall **)(_QWORD, _WORD *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, &v9[1], 1);
  for ( i = 0; i < (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 48LL))(a1); ++i )
  {
    std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v10, (_QWORD *)(a1[3] + 16 * i));
    v5 = v10;
    if ( !v10 )
    {
      std::string::string(v13, "nullptr found in array object");
      PCLmWriter::Exception::Exception((std::exception *)pExceptionObject, (__int64)v13, 0);
      throw (PCLmWriter::Exception *)pExceptionObject;
    }
    if ( i )
      (*(void (__fastcall **)(_QWORD, _WORD *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, &v9[1], 1);
    v6 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v13, a2);
    v7(v5, v6);
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
  }
  (*(void (__fastcall **)(_QWORD, _WORD *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, &v9[1], 1);
  (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, (char *)v9 + 1, 1);
  v8 = (std::_Ref_count_base *)a2[1];
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
}

```

## disassembly

```asm
0x180018e10  mov     [rsp-8+arg_10], rbx
0x180018e15  mov     [rsp-8+arg_18], rsi
0x180018e1a  push    rbp
0x180018e1b  push    rdi
0x180018e1c  push    r14
0x180018e1e  lea     rbp, [rsp-47h]
0x180018e23  sub     rsp, 0C0h
0x180018e2a  mov     rax, cs:__security_cookie
0x180018e31  xor     rax, rsp
0x180018e34  mov     [rbp+57h+var_20], rax
0x180018e38  mov     rdi, rdx
0x180018e3b  mov     r14, rcx
0x180018e3e  mov     [rbp+57h+var_98], rdx
0x180018e42  mov     [rbp+57h+var_B0], 5D5Bh
0x180018e48  mov     [rbp+57h+var_AE], 20h ; ' '
0x180018e4c  mov     rcx, [rdx]
0x180018e4f  mov     rax, [rcx]
0x180018e52  mov     r8d, 1
0x180018e58  lea     rdx, [rbp+57h+var_B0]
0x180018e5c  mov     rax, [rax+18h]
0x180018e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e65  mov     rcx, [rdi]
0x180018e68  mov     rax, [rcx]
0x180018e6b  mov     r8d, 1
0x180018e71  lea     rdx, [rbp+57h+var_AE]
0x180018e75  mov     rax, [rax+18h]
0x180018e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e7e  xor     ebx, ebx
0x180018e80  mov     rax, [r14]
0x180018e83  mov     rcx, r14
0x180018e86  mov     rax, [rax+30h]
0x180018e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e8f  cmp     rbx, rax
0x180018e92  jnb     loc_180018F3E
0x180018e98  mov     rdx, rbx
0x180018e9b  shl     rdx, 4
0x180018e9f  add     rdx, [r14+18h]
0x180018ea3  lea     rcx, [rbp+57h+var_A8]
0x180018ea7  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180018eac  nop
0x180018ead  mov     rsi, [rbp+57h+var_A8]
0x180018eb1  test    rsi, rsi
0x180018eb4  jz      short loc_180018F0C
0x180018eb6  test    rbx, rbx
0x180018eb9  jz      short loc_180018ED4
0x180018ebb  mov     rcx, [rdi]
0x180018ebe  mov     rax, [rcx]
0x180018ec1  mov     r8d, 1
0x180018ec7  lea     rdx, [rbp+57h+var_AE]
0x180018ecb  mov     rax, [rax+18h]
0x180018ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed4  mov     rax, [rsi]
0x180018ed7  mov     r8, [rax+20h]
0x180018edb  mov     rdx, rdi
0x180018ede  lea     rcx, [rbp+57h+var_88]
0x180018ee2  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180018ee7  mov     rdx, rax
0x180018eea  mov     rcx, rsi
0x180018eed  mov     rax, r8
0x180018ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ef5  nop
0x180018ef6  mov     rcx, [rbp+57h+var_A0]; this
0x180018efa  test    rcx, rcx
0x180018efd  jz      short loc_180018F04
0x180018eff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018f04  inc     rbx
0x180018f07  jmp     loc_180018E80
0x180018f0c  lea     rdx, aNullptrFoundIn_0; "nullptr found in array object"
0x180018f13  lea     rcx, [rbp+57h+var_88]
0x180018f17  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180018f1c  nop
0x180018f1d  xor     r8d, r8d
0x180018f20  lea     rdx, [rbp+57h+var_88]
0x180018f24  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180018f28  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x180018f2d  lea     rdx, _TI2?AVException@PCLmWriter@@; pThrowInfo
0x180018f34  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018f38  call    _CxxThrowException_0
0x180018f3e  mov     rcx, [rdi]
0x180018f41  mov     rax, [rcx]
0x180018f44  mov     r8d, 1
0x180018f4a  lea     rdx, [rbp+57h+var_AE]
0x180018f4e  mov     rax, [rax+18h]
0x180018f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f57  mov     rcx, [rdi]
0x180018f5a  mov     rax, [rcx]
0x180018f5d  mov     r8d, 1
0x180018f63  lea     rdx, [rbp+57h+var_B0+1]
0x180018f67  mov     rax, [rax+18h]
0x180018f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f70  nop
0x180018f71  mov     rcx, [rdi+8]; this
0x180018f75  test    rcx, rcx
0x180018f78  jz      short loc_180018F7F
0x180018f7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018f7f  mov     rcx, [rbp+57h+var_20]
0x180018f83  xor     rcx, rsp; StackCookie
0x180018f86  call    __security_check_cookie
0x180018f8b  lea     r11, [rsp+0D0h+var_10]
0x180018f93  mov     rbx, [r11+30h]
0x180018f97  mov     rsi, [r11+38h]
0x180018f9b  mov     rsp, r11
0x180018f9e  pop     r14
0x180018fa0  pop     rdi
0x180018fa1  pop     rbp
0x180018fa2  retn
```
