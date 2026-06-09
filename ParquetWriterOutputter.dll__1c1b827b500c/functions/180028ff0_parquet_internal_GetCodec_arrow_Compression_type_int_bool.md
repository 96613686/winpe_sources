# parquet::internal::GetCodec(arrow::Compression::type,int,bool)

- ea: `0x180028ff0`
- end: `0x18002927a`
- name: `?GetCodec@internal@parquet@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@W4type@Compression@arrow@@H_N@Z`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180029350`

## callees

- `0x18000ff30`
- `0x18001b340`
- `0x18001b360`
- `0x18001c580`
- `0x18001ccf0`
- `0x18001d1d0`
- `0x18001d210`
- `0x18001d320`
- `0x18001d590`
- `0x18001d5b0`
- `0x18001f8c0`
- `0x1800262d0`
- `0x180028ff0`
- `0x180029390`
- `0x180099980`
- `0x180099e80`
- `0x18009a530`
- `0x18009a8e0`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## string_xrefs

- `0x1800291d0`: `Per ARROW-9424, writing files with LZ4 compression has been disabled until implementation issues have been resolved. It is recommended to read any existing files and rewrite them using a different compression.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char *__fastcall parquet::internal::GetCodec(char *a1, unsigned int a2, unsigned int a3, char a4)
{
  void (__fastcall ***v7)(_QWORD, __int64); // rbx
  const struct arrow::Status *v8; // rax
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  arrow::Status::State *v10; // rcx
  const struct arrow::Status *v11; // rdx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // r8
  void (__fastcall **v14)(_QWORD, __int64); // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 CodecAsString; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  _BYTE v22[16]; // [rsp+40h] [rbp-C0h] BYREF
  char v23[240]; // [rsp+50h] [rbp-B0h] BYREF
  char v24[8]; // [rsp+140h] [rbp+40h] BYREF
  arrow::Status::State *v25; // [rsp+148h] [rbp+48h]
  void (__fastcall ***v26)(_QWORD, __int64); // [rsp+150h] [rbp+50h]
  char v27[8]; // [rsp+158h] [rbp+58h] BYREF
  arrow::Status::State *v28; // [rsp+160h] [rbp+60h]
  void (__fastcall ***v29)(_QWORD, __int64); // [rsp+168h] [rbp+68h]
  char v30[8]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v31; // [rsp+178h] [rbp+78h]
  _BYTE pExceptionObject[80]; // [rsp+1B0h] [rbp+B0h] BYREF

  v7 = 0;
  *(_QWORD *)a1 = 0;
  if ( a4 && a2 - 5 <= 1 )
  {
    parquet::ParquetException::ParquetException(
      (parquet::ParquetException *)v30,
      "Per ARROW-9424, writing files with LZ4 compression has been disabled until implementation issues have been resolve"
      "d. It is recommended to read any existing files and rewrite them using a different compression.");
    throw (parquet::ParquetException *)v30;
  }
  if ( !(unsigned __int8)parquet::IsCodecSupported(a2) )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
      v22,
      3,
      1);
    CodecAsString = arrow::util::Codec::GetCodecAsString(v30);
    v19 = std::operator<<<std::char_traits<char>>(v23, "Codec type ");
    v20 = arrow::util::StringBuilderRecursive<std::string>(v19, CodecAsString);
    std::operator<<<std::char_traits<char>>(v20, " not supported in Parquet format");
    std::string::~string(v30);
    v21 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v22, v30);
    parquet::ParquetException::ParquetException(pExceptionObject, v21);
    throw (parquet::ParquetException *)pExceptionObject;
  }
  v8 = (const struct arrow::Status *)arrow::util::Codec::Create((__int64)v27, a2, a3);
  v25 = 0;
  if ( *((_QWORD *)v8 + 1) )
  {
    arrow::Status::CopyFrom((arrow::Status *)v24, v8);
  }
  else
  {
    v25 = 0;
    *((_QWORD *)v8 + 1) = 0;
    v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v8 + 2);
    *((_QWORD *)v8 + 2) = 0;
    v26 = v9;
  }
  v10 = v28;
  if ( v28 || v29 && ((**v29)(v29, 1), (v10 = v28) != 0) )
  {
    arrow::Status::State::`scalar deleting destructor'(v10, 1u);
    v28 = 0;
  }
  arrow::Status::Status((arrow::Status *)v30, (const struct arrow::Status *)v24);
  if ( v31 )
  {
    v16 = std::_Vector_alloc<std::_Vec_base_types<std::shared_ptr<arrow::Buffer>>>::_Getal(v30);
    v17 = arrow::Status::Status(v27, v16);
    parquet::ParquetStatusException::ParquetStatusException(pExceptionObject, v17);
    throw (parquet::ParquetStatusException *)pExceptionObject;
  }
  if ( v25 )
    arrow::internal::InvalidValueOrDie((arrow::internal *)v24, v11);
  v12 = v26;
  v26 = 0;
  if ( a1 == v27 )
  {
    if ( v12 )
    {
      v14 = *v12;
      goto LABEL_19;
    }
  }
  else
  {
    v13 = *(void (__fastcall ****)(_QWORD, __int64))a1;
    *(_QWORD *)a1 = v12;
    if ( v13 )
    {
      v14 = *v13;
      v12 = v13;
LABEL_19:
      (*v14)(v12, 1);
      v7 = v26;
    }
  }
  if ( v25 || v7 && ((**v7)(v7, 1), v25) )
    arrow::Status::State::`scalar deleting destructor'(v25, 1u);
  return a1;
}

```

## disassembly

```asm
0x180028ff0  push    rbp
0x180028ff2  push    rbx
0x180028ff3  push    rsi
0x180028ff4  push    rdi
0x180028ff5  push    r14
0x180028ff7  lea     rbp, [rsp-110h]
0x180028fff  sub     rsp, 210h
0x180029006  mov     [rsp+230h+var_208], 0FFFFFFFFFFFFFFFEh
0x18002900f  mov     rax, cs:__security_cookie
0x180029016  xor     rax, rsp
0x180029019  mov     [rbp+130h+var_30], rax
0x180029020  mov     r14d, r8d
0x180029023  mov     esi, edx
0x180029025  mov     rdi, rcx
0x180029028  mov     [rsp+230h+var_200], rcx
0x18002902d  xor     ebx, ebx
0x18002902f  mov     [rsp+230h+var_210], ebx
0x180029033  mov     [rcx], rbx
0x180029036  mov     [rsp+230h+var_210], 1
0x18002903e  test    r9b, r9b
0x180029041  jz      short loc_18002904F
0x180029043  lea     eax, [rdx-5]
0x180029046  cmp     eax, 1
0x180029049  jbe     loc_1800291D0
0x18002904f  mov     ecx, esi
0x180029051  call    ?IsCodecSupported@parquet@@YA_NW4type@Compression@arrow@@@Z; parquet::IsCodecSupported(arrow::Compression::type)
0x180029056  test    al, al
0x180029058  jz      loc_1800291F1
0x18002905e  mov     r8d, r14d
0x180029061  mov     edx, esi
0x180029063  lea     rcx, [rbp+130h+var_D8]
0x180029067  call    ?Create@Codec@util@arrow@@SA?AV?$Result@V?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@@3@W4type@Compression@3@H@Z; arrow::util::Codec::Create(arrow::Compression::type,int)
0x18002906c  nop
0x18002906d  mov     [rbp+130h+var_E8], rbx
0x180029071  cmp     qword ptr [rax+8], 0
0x180029076  jnz     short loc_18002908E
0x180029078  mov     [rbp+130h+var_E8], rbx
0x18002907c  mov     [rax+8], rbx
0x180029080  mov     rcx, [rax+10h]
0x180029084  mov     [rax+10h], rbx
0x180029088  mov     [rbp+130h+var_E0], rcx
0x18002908c  jmp     short loc_18002909B
0x18002908e  mov     rdx, rax; struct arrow::Status *
0x180029091  lea     rcx, [rbp+130h+var_F0]; this
0x180029095  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x18002909a  nop
0x18002909b  mov     rcx, [rbp+130h+var_D0]
0x18002909f  test    rcx, rcx
0x1800290a2  jnz     short loc_1800290C7
0x1800290a4  mov     rcx, [rbp+130h+var_C8]
0x1800290a8  test    rcx, rcx
0x1800290ab  jz      short loc_1800290D5
0x1800290ad  mov     rax, [rcx]
0x1800290b0  mov     edx, 1
0x1800290b5  mov     rax, [rax]
0x1800290b8  call    cs:__guard_dispatch_icall_fptr
0x1800290be  mov     rcx, [rbp+130h+var_D0]; this
0x1800290c2  test    rcx, rcx
0x1800290c5  jz      short loc_1800290D5
0x1800290c7  mov     edx, 1; unsigned int
0x1800290cc  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800290d1  mov     [rbp+130h+var_D0], rbx
0x1800290d5  lea     rdx, [rbp+130h+var_F0]; struct arrow::Status *
0x1800290d9  lea     rcx, [rbp+130h+var_C0]; this
0x1800290dd  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800290e2  mov     [rsp+230h+var_210], 3
0x1800290ea  cmp     [rbp+130h+var_B8], 0
0x1800290ef  jnz     loc_180029198
0x1800290f5  cmp     [rbp+130h+var_E8], 0
0x1800290fa  jz      short loc_180029105
0x1800290fc  lea     rcx, [rbp+130h+var_F0]; this
0x180029100  call    ?InvalidValueOrDie@internal@arrow@@YAXAEBVStatus@2@@Z; arrow::internal::InvalidValueOrDie(arrow::Status const &)
0x180029105  mov     rcx, [rbp+130h+var_E0]
0x180029109  mov     [rbp+130h+var_E0], rbx
0x18002910d  lea     rax, [rbp+130h+var_D8]
0x180029111  cmp     rdi, rax
0x180029114  jz      short loc_180029129
0x180029116  mov     r8, [rdi]
0x180029119  mov     [rdi], rcx
0x18002911c  test    r8, r8
0x18002911f  jz      short loc_180029143
0x180029121  mov     rax, [r8]
0x180029124  mov     rcx, r8
0x180029127  jmp     short loc_180029131
0x180029129  test    rcx, rcx
0x18002912c  jz      short loc_180029143
0x18002912e  mov     rax, [rcx]
0x180029131  mov     edx, 1
0x180029136  mov     rax, [rax]
0x180029139  call    cs:__guard_dispatch_icall_fptr
0x18002913f  mov     rbx, [rbp+130h+var_E0]
0x180029143  cmp     [rbp+130h+var_E8], 0
0x180029148  jnz     short loc_18002916A
0x18002914a  test    rbx, rbx
0x18002914d  jz      short loc_180029178
0x18002914f  mov     rax, [rbx]
0x180029152  mov     edx, 1
0x180029157  mov     rcx, rbx
0x18002915a  mov     rax, [rax]
0x18002915d  call    cs:__guard_dispatch_icall_fptr
0x180029163  cmp     [rbp+130h+var_E8], 0
0x180029168  jz      short loc_180029178
0x18002916a  mov     edx, 1; unsigned int
0x18002916f  mov     rcx, [rbp+130h+var_E8]; this
0x180029173  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180029178  mov     rax, rdi
0x18002917b  mov     rcx, [rbp+130h+var_30]
0x180029182  xor     rcx, rsp; StackCookie
0x180029185  call    __security_check_cookie
0x18002918a  add     rsp, 210h
0x180029191  pop     r14
0x180029193  pop     rdi
0x180029194  pop     rsi
0x180029195  pop     rbx
0x180029196  pop     rbp
0x180029197  retn
0x180029198  lea     rcx, [rbp+130h+var_C0]
0x18002919c  call    ?_Getal@?$_Vector_alloc@U?$_Vec_base_types@V?$shared_ptr@VBuffer@arrow@@@std@@V?$allocator@V?$shared_ptr@VBuffer@arrow@@@std@@@2@@std@@@std@@QEAAAEAV?$allocator@V?$shared_ptr@VBuffer@arrow@@@std@@@2@XZ; std::_Vector_alloc<std::_Vec_base_types<std::shared_ptr<arrow::Buffer>>>::_Getal(void)
0x1800291a1  mov     rdx, rax
0x1800291a4  lea     rcx, [rbp+130h+var_D8]
0x1800291a8  call    ??0Status@arrow@@QEAA@$$QEAV01@@Z; arrow::Status::Status(arrow::Status &&)
0x1800291ad  mov     rdx, rax
0x1800291b0  lea     rcx, [rbp+130h+pExceptionObject]
0x1800291b7  call    ??0ParquetStatusException@parquet@@QEAA@VStatus@arrow@@@Z; parquet::ParquetStatusException::ParquetStatusException(arrow::Status)
0x1800291bc  lea     rdx, _TI3?AVParquetStatusException@parquet@@; pThrowInfo
0x1800291c3  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x1800291ca  call    _CxxThrowException
0x1800291d0  lea     rdx, aPerArrow9424Wr; "Per ARROW-9424, writing files with LZ4 "...
0x1800291d7  lea     rcx, [rbp+130h+var_C0]; this
0x1800291db  call    ??0ParquetException@parquet@@QEAA@PEBD@Z; parquet::ParquetException::ParquetException(char const *)
0x1800291e0  lea     rdx, _TI2?AVParquetException@parquet@@; pThrowInfo
0x1800291e7  lea     rcx, [rbp+130h+var_C0]; pExceptionObject
0x1800291eb  call    _CxxThrowException
0x1800291f1  mov     edx, 3
0x1800291f6  lea     r8d, [rdx-2]
0x1800291fa  lea     rcx, [rsp+230h+var_1F0]
0x1800291ff  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@H@Z; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(int)
0x180029204  nop
0x180029205  mov     edx, esi
0x180029207  lea     rcx, [rbp+130h+var_C0]; void *
0x18002920b  call    ?GetCodecAsString@Codec@util@arrow@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4type@Compression@3@@Z; arrow::util::Codec::GetCodecAsString(arrow::Compression::type)
0x180029210  mov     rbx, rax
0x180029213  lea     rdx, aCodecType; "Codec type "
0x18002921a  lea     rcx, [rsp+230h+var_1E0]
0x18002921f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180029224  mov     rcx, rax
0x180029227  mov     rdx, rbx
0x18002922a  call    ??$StringBuilderRecursive@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@util@arrow@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; arrow::util::StringBuilderRecursive<std::string>(std::ostream &,std::string &&)
0x18002922f  mov     rcx, rax
0x180029232  lea     rdx, aNotSupportedIn; " not supported in Parquet format"
0x180029239  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002923e  nop
0x18002923f  lea     rcx, [rbp+130h+var_C0]
0x180029243  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180029248  lea     rdx, [rbp+130h+var_C0]
0x18002924c  lea     rcx, [rsp+230h+var_1F0]
0x180029251  call    ?str@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x180029256  nop
0x180029257  mov     rdx, rax
0x18002925a  lea     rcx, [rbp+130h+pExceptionObject]
0x180029261  call    ??0ParquetException@parquet@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; parquet::ParquetException::ParquetException(std::string const &)
0x180029266  lea     rdx, _TI2?AVParquetException@parquet@@; pThrowInfo
0x18002926d  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x180029274  call    _CxxThrowException
```
