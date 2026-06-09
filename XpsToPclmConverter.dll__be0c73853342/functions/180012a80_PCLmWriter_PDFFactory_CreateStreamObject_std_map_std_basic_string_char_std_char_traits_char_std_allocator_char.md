# PCLmWriter::PDFFactory::CreateStreamObject(std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> const &,std::shared_ptr<PCLmWriter::IByteStream> const &,bool,uint,uint)

- ea: `0x180012a80`
- end: `0x180012b97`
- name: `?CreateStreamObject@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@$$CBVIStreamObject@PCLmWriter@@@std@@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@4@AEBV?$shared_ptr@VIByteStream@PCLmWriter@@@4@_NII@Z`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001f6c`
- `0x1800101cc`
- `0x1800117bc`
- `0x180012a80`
- `0x1800135d4`
- `0x180018aa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall PCLmWriter::PDFFactory::CreateStreamObject(
        __int64 a1,
        __int64 *a2,
        int a3,
        int a4,
        char a5,
        int a6,
        int a7)
{
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rbx
  _DWORD *v14; // rax
  __int128 v16; // [rsp+50h] [rbp-28h] BYREF
  char v17[8]; // [rsp+60h] [rbp-18h] BYREF
  std::_Ref_count_base *v18; // [rsp+68h] [rbp-10h]
  __int64 *v19; // [rsp+B8h] [rbp+40h] BYREF

  v19 = a2;
  v11 = (__int64 *)operator new(0x60u);
  v19 = v11;
  v12 = std::enable_shared_from_this<PCLmWriter::PDFFactory>::shared_from_this(a1 + 8, v17);
  v16 = 0;
  v16 = *(_OWORD *)v12;
  *(_QWORD *)v12 = 0;
  *(_QWORD *)(v12 + 8) = 0;
  v13 = PCLmWriter::StreamObject::StreamObject((_DWORD)v11, a3, a4, (unsigned int)&v16, a5, a6, a7);
  *a2 = 0;
  a2[1] = 0;
  v19 = (__int64 *)v13;
  v14 = operator new(0x18u);
  *(_OWORD *)v14 = 0;
  v14[2] = 1;
  v14[3] = 1;
  *(_QWORD *)v14 = &std::_Ref_count<PCLmWriter::StreamObject>::`vftable';
  *((_QWORD *)v14 + 2) = v13;
  *a2 = v13;
  a2[1] = (__int64)v14;
  v19 = 0;
  std::_Temporary_owner<PCLmWriter::StreamObject>::~_Temporary_owner<PCLmWriter::StreamObject>(&v19);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return a2;
}

```

## disassembly

```asm
0x180012a80  mov     [rsp-30h+arg_8], rdx
0x180012a85  push    rbp
0x180012a86  push    rbx
0x180012a87  push    rsi
0x180012a88  push    rdi
0x180012a89  push    r14
0x180012a8b  push    r15
0x180012a8d  mov     rbp, rsp
0x180012a90  sub     rsp, 78h
0x180012a94  mov     rsi, r9
0x180012a97  mov     r14, r8
0x180012a9a  mov     r15, rdx
0x180012a9d  mov     rbx, rcx
0x180012aa0  mov     [rbp+var_38], 0
0x180012aa7  mov     ecx, 60h ; '`'; Size
0x180012aac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012ab1  mov     rdi, rax
0x180012ab4  mov     [rbp+arg_8], rax
0x180012ab8  lea     rcx, [rbx+8]
0x180012abc  lea     rdx, [rbp+var_18]
0x180012ac0  call    ?shared_from_this@?$enable_shared_from_this@VPDFFactory@PCLmWriter@@@std@@QEAA?AV?$shared_ptr@VPDFFactory@PCLmWriter@@@2@XZ; std::enable_shared_from_this<PCLmWriter::PDFFactory>::shared_from_this(void)
0x180012ac5  nop
0x180012ac6  mov     [rbp+var_38], 1
0x180012acd  xorps   xmm0, xmm0
0x180012ad0  movdqu  [rbp+var_28], xmm0
0x180012ad5  mov     rcx, [rax]
0x180012ad8  mov     qword ptr [rbp+var_28], rcx
0x180012adc  mov     rcx, [rax+8]
0x180012ae0  mov     qword ptr [rbp+var_28+8], rcx
0x180012ae4  mov     qword ptr [rax], 0
0x180012aeb  mov     qword ptr [rax+8], 0
0x180012af3  mov     eax, [rbp+arg_30]
0x180012af6  mov     [rsp+78h+var_48], eax
0x180012afa  mov     eax, [rbp+arg_28]
0x180012afd  mov     [rsp+78h+var_50], eax
0x180012b01  mov     al, [rbp+arg_20]
0x180012b04  mov     [rsp+78h+var_58], al
0x180012b08  lea     r9, [rbp+var_28]
0x180012b0c  mov     r8, rsi
0x180012b0f  mov     rdx, r14
0x180012b12  mov     rcx, rdi
0x180012b15  call    ??0StreamObject@PCLmWriter@@QEAA@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEBV?$shared_ptr@VIByteStream@PCLmWriter@@@3@V?$shared_ptr@VIPDFFactory@PCLmWriter@@@3@_NII@Z; PCLmWriter::StreamObject::StreamObject(std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> const &,std::shared_ptr<PCLmWriter::IByteStream> const &,std::shared_ptr<PCLmWriter::IPDFFactory>,bool,uint,uint)
0x180012b1a  mov     rbx, rax
0x180012b1d  mov     qword ptr [r15], 0
0x180012b24  mov     qword ptr [r15+8], 0
0x180012b2c  mov     [rbp+arg_8], rax
0x180012b30  mov     ecx, 18h; Size
0x180012b35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012b3a  mov     [rbp+arg_8], rax
0x180012b3e  xorps   xmm0, xmm0
0x180012b41  movups  xmmword ptr [rax], xmm0
0x180012b44  mov     dword ptr [rax+8], 1
0x180012b4b  mov     dword ptr [rax+0Ch], 1
0x180012b52  lea     rcx, ??_7?$_Ref_count@VStreamObject@PCLmWriter@@@std@@6B@; const std::_Ref_count<PCLmWriter::StreamObject>::`vftable'
0x180012b59  mov     [rax], rcx
0x180012b5c  mov     [rax+10h], rbx
0x180012b60  mov     [r15], rbx
0x180012b63  mov     [r15+8], rax
0x180012b67  mov     [rbp+arg_8], 0
0x180012b6f  lea     rcx, [rbp+arg_8]
0x180012b73  call    ??1?$_Temporary_owner@VStreamObject@PCLmWriter@@@std@@QEAA@XZ; std::_Temporary_owner<PCLmWriter::StreamObject>::~_Temporary_owner<PCLmWriter::StreamObject>(void)
0x180012b78  nop
0x180012b79  mov     rcx, [rbp+var_10]; this
0x180012b7d  test    rcx, rcx
0x180012b80  jz      short loc_180012B87
0x180012b82  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012b87  mov     rax, r15
0x180012b8a  add     rsp, 78h
0x180012b8e  pop     r15
0x180012b90  pop     r14
0x180012b92  pop     rdi
0x180012b93  pop     rsi
0x180012b94  pop     rbx
0x180012b95  pop     rbp
0x180012b96  retn
```
