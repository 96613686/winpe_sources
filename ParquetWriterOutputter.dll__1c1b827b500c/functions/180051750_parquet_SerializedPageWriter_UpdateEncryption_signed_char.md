# parquet::SerializedPageWriter::UpdateEncryption(signed char)

- ea: `0x180051750`
- end: `0x180051a46`
- name: `?UpdateEncryption@SerializedPageWriter@parquet@@AEAAXC@Z`
- size: `758`
- prototype: `void __fastcall __noreturn(parquet::SerializedPageWriter *__hidden this, signed __int8)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18004e8b0`
- `0x18004ee10`
- `0x1800563e0`
- `0x180057e80`

## callees

- `0x180010860`
- `0x18001d210`
- `0x180051750`
- `0x180059220`
- `0x18030c180`
- `0x18030c3f0`
- `0x18032b080`
- `0x180334640`

## string_xrefs

- `0x180051a23`: `Unknown module type in UpdateEncryption`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall __noreturn parquet::SerializedPageWriter::UpdateEncryption(
        parquet::SerializedPageWriter *this,
        char a2)
{
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-50h] BYREF

  if ( a2 != 1 )
  {
    if ( a2 != 2 )
    {
      if ( a2 != 3 )
      {
        if ( a2 != 4 )
        {
          if ( a2 == 5 )
            parquet::encryption::AesEncryptor::WipeOut((parquet::encryption::AesEncryptor *)pExceptionObject);
          parquet::ParquetException::ParquetException(
            (parquet::ParquetException *)pExceptionObject,
            "Unknown module type in UpdateEncryption");
          throw (parquet::ParquetException *)pExceptionObject;
        }
        parquet::encryption::AesEncryptor::WipeOut((parquet::SerializedPageWriter *)((char *)this + 136));
      }
      parquet::encryption::AesEncryptor::WipeOut((parquet::encryption::AesEncryptor *)pExceptionObject);
    }
    parquet::encryption::AesEncryptor::WipeOut((parquet::SerializedPageWriter *)((char *)this + 104));
  }
  parquet::encryption::AesEncryptor::WipeOut((parquet::encryption::AesEncryptor *)pExceptionObject);
}

```

## disassembly

```asm
0x180051750  push    rdi
0x180051752  sub     rsp, 80h
0x180051759  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x180051762  mov     [rsp+88h+arg_10], rbx
0x18005176a  mov     rax, cs:__security_cookie
0x180051771  xor     rax, rsp
0x180051774  mov     [rsp+88h+var_18], rax
0x180051779  movsx   r8d, dl
0x18005177d  mov     rbx, rcx
0x180051780  mov     ecx, r8d
0x180051783  sub     ecx, 1
0x180051786  jz      loc_180051965
0x18005178c  sub     ecx, 1
0x18005178f  jz      loc_180051926
0x180051795  sub     ecx, 1
0x180051798  jz      loc_18005188C
0x18005179e  sub     ecx, 1
0x1800517a1  jz      loc_18005184A
0x1800517a7  cmp     ecx, 1
0x1800517aa  jnz     loc_180051A23
0x1800517b0  mov     rdx, [rbx+0A8h]
0x1800517b7  mov     eax, 0FFFFFFFFh
0x1800517bc  add     rdx, 28h ; '('
0x1800517c0  mov     [rsp+88h+var_60], ax
0x1800517c5  movzx   eax, word ptr [rbx+54h]
0x1800517c9  mov     [rsp+88h+var_68], ax
0x1800517ce  movzx   r9d, word ptr [rbx+52h]
0x1800517d3  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800517d8  call    ?WipeOut@AesEncryptor@encryption@parquet@@QEAAXXZ
0x1800517de  mov     rcx, [rbx+0A8h]
0x1800517e5  add     rcx, 48h ; 'H'; void *
0x1800517e9  cmp     rcx, rax
0x1800517ec  jz      short loc_180051805
0x1800517ee  mov     rdx, rax
0x1800517f1  cmp     qword ptr [rax+18h], 10h
0x1800517f6  jb      short loc_1800517FB
0x1800517f8  mov     rdx, [rax]; Src
0x1800517fb  mov     r8, [rax+10h]; Size
0x1800517ff  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z
0x180051804  nop
0x180051805  mov     rdx, [rsp+88h+var_38]
0x18005180a  cmp     rdx, 10h
0x18005180e  jb      loc_1800519F3
0x180051814  inc     rdx
0x180051817  mov     rcx, [rsp+88h+pExceptionObject]
0x18005181c  mov     rax, rcx
0x18005181f  cmp     rdx, 1000h
0x180051826  jb      loc_1800519EE
0x18005182c  add     rdx, 27h ; '''
0x180051830  mov     rcx, [rcx-8]
0x180051834  sub     rax, rcx
0x180051837  add     rax, 0FFFFFFFFFFFFFFF8h
0x18005183b  cmp     rax, 1Fh
0x18005183f  ja      loc_180051A17
0x180051845  jmp     loc_1800519EE
0x18005184a  lea     rdi, [rbx+88h]
0x180051851  movzx   edx, word ptr [rbx+50h]
0x180051855  mov     rcx, rdi; this
0x180051858  call    ?WipeOut@AesEncryptor@encryption@parquet@@QEAAXXZ
0x18005185d  mov     rcx, [rbx+0A8h]
0x180051864  add     rcx, 48h ; 'H'; void *
0x180051868  cmp     rcx, rdi
0x18005186b  jz      loc_1800519F3
0x180051871  mov     rdx, rdi
0x180051874  cmp     qword ptr [rdi+18h], 10h
0x180051879  jb      short loc_18005187E
0x18005187b  mov     rdx, [rdi]; Src
0x18005187e  mov     r8, [rdi+10h]; Size
0x180051882  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z
0x180051887  jmp     loc_1800519F3
0x18005188c  mov     rdx, [rbx+0B8h]
0x180051893  mov     eax, 0FFFFFFFFh
0x180051898  add     rdx, 28h ; '('
0x18005189c  mov     [rsp+88h+var_60], ax
0x1800518a1  movzx   eax, word ptr [rbx+54h]
0x1800518a5  mov     [rsp+88h+var_68], ax
0x1800518aa  movzx   r9d, word ptr [rbx+52h]
0x1800518af  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800518b4  call    ?WipeOut@AesEncryptor@encryption@parquet@@QEAAXXZ
0x1800518ba  mov     rcx, [rbx+0B8h]
0x1800518c1  add     rcx, 48h ; 'H'; void *
0x1800518c5  cmp     rcx, rax
0x1800518c8  jz      short loc_1800518E1
0x1800518ca  mov     rdx, rax
0x1800518cd  cmp     qword ptr [rax+18h], 10h
0x1800518d2  jb      short loc_1800518D7
0x1800518d4  mov     rdx, [rax]; Src
0x1800518d7  mov     r8, [rax+10h]; Size
0x1800518db  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z
0x1800518e0  nop
0x1800518e1  mov     rdx, [rsp+88h+var_38]
0x1800518e6  cmp     rdx, 10h
0x1800518ea  jb      loc_1800519F3
0x1800518f0  inc     rdx
0x1800518f3  mov     rcx, [rsp+88h+pExceptionObject]
0x1800518f8  mov     rax, rcx
0x1800518fb  cmp     rdx, 1000h
0x180051902  jb      loc_1800519EE
0x180051908  add     rdx, 27h ; '''
0x18005190c  mov     rcx, [rcx-8]
0x180051910  sub     rax, rcx
0x180051913  add     rax, 0FFFFFFFFFFFFFFF8h
0x180051917  cmp     rax, 1Fh
0x18005191b  ja      loc_180051A1D
0x180051921  jmp     loc_1800519EE
0x180051926  lea     rdi, [rbx+68h]
0x18005192a  movzx   edx, word ptr [rbx+50h]
0x18005192e  mov     rcx, rdi; this
0x180051931  call    ?WipeOut@AesEncryptor@encryption@parquet@@QEAAXXZ
0x180051936  mov     rcx, [rbx+0B8h]
0x18005193d  add     rcx, 48h ; 'H'; void *
0x180051941  cmp     rcx, rdi
0x180051944  jz      loc_1800519F3
0x18005194a  mov     rdx, rdi
0x18005194d  cmp     qword ptr [rdi+18h], 10h
0x180051952  jb      short loc_180051957
0x180051954  mov     rdx, [rdi]; Src
0x180051957  mov     r8, [rdi+10h]; Size
0x18005195b  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z
0x180051960  jmp     loc_1800519F3
0x180051965  mov     rdx, [rbx+0A8h]
0x18005196c  mov     eax, 0FFFFFFFFh
0x180051971  add     rdx, 28h ; '('
0x180051975  mov     [rsp+88h+var_60], ax
0x18005197a  movzx   eax, word ptr [rbx+54h]
0x18005197e  mov     [rsp+88h+var_68], ax
0x180051983  movzx   r9d, word ptr [rbx+52h]
0x180051988  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18005198d  call    ?WipeOut@AesEncryptor@encryption@parquet@@QEAAXXZ
0x180051993  mov     rcx, [rbx+0A8h]
0x18005199a  add     rcx, 48h ; 'H'; void *
0x18005199e  cmp     rcx, rax
0x1800519a1  jz      short loc_1800519BA
0x1800519a3  mov     rdx, rax
0x1800519a6  cmp     qword ptr [rax+18h], 10h
0x1800519ab  jb      short loc_1800519B0
0x1800519ad  mov     rdx, [rax]; Src
0x1800519b0  mov     r8, [rax+10h]; Size
0x1800519b4  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z
0x1800519b9  nop
0x1800519ba  mov     rdx, [rsp+88h+var_38]
0x1800519bf  cmp     rdx, 10h
0x1800519c3  jb      short loc_1800519F3
0x1800519c5  inc     rdx
0x1800519c8  mov     rcx, [rsp+88h+pExceptionObject]
0x1800519cd  mov     rax, rcx
0x1800519d0  cmp     rdx, 1000h
0x1800519d7  jb      short loc_1800519EE
0x1800519d9  add     rdx, 27h ; '''; unsigned __int64
0x1800519dd  mov     rcx, [rcx-8]; void *
0x1800519e1  sub     rax, rcx
0x1800519e4  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800519e8  cmp     rax, 1Fh
0x1800519ec  ja      short loc_180051A11
0x1800519ee  call    ??3@YAXPEAX_K@Z
0x1800519f3  mov     rcx, [rsp+88h+var_18]
0x1800519f8  xor     rcx, rsp; StackCookie
0x1800519fb  call    __security_check_cookie
0x180051a00  mov     rbx, [rsp+88h+arg_10]
0x180051a08  add     rsp, 80h
0x180051a0f  pop     rdi
0x180051a10  retn
0x180051a11  call    _invalid_parameter_noinfo_noreturn
0x180051a17  call    _invalid_parameter_noinfo_noreturn
0x180051a1d  call    _invalid_parameter_noinfo_noreturn
0x180051a23  lea     rdx, aUnknownModuleT
0x180051a2a  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180051a2f  call    ??0ParquetException@parquet@@QEAA@PEBD@Z
0x180051a34  lea     rdx, _TI2?AVParquetException@parquet@@; pThrowInfo
0x180051a3b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180051a40  call    _CxxThrowException
```
