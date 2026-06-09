# arrow::ExtensionArray::ExtensionArray(std::shared_ptr<arrow::DataType> const &,std::shared_ptr<arrow::Array> const &)

- ea: `0x18025e2c0`
- end: `0x18025e624`
- name: `??0ExtensionArray@arrow@@QEAA@AEBV?$shared_ptr@VDataType@arrow@@@std@@AEBV?$shared_ptr@VArray@arrow@@@3@@Z`
- size: `868`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18020f1b0`
- `0x18020f5e0`

## callees

- `0x18001b360`
- `0x1800a60d0`
- `0x1800c6140`
- `0x1800dc8f0`
- `0x1800dca00`
- `0x18025e2c0`
- `0x18025e700`
- `0x180358070`

## string_xrefs

- `0x18025e324`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\extension_type.cc`
- `0x18025e3fe`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\extension_type.cc`
- `0x18025e36b`: ` Check failed: (type->id()) == (Type::EXTENSION) `
- `0x18025e447`: ` Check failed: storage->type()->Equals(*checked_cast<const ExtensionType&>(*type).storage_type()) `

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall arrow::ExtensionArray::ExtensionArray(_QWORD *a1, _QWORD *a2, __int64 *a3)
{
  char v6; // di
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  const struct arrow::DataType *v11; // rdx
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rsi
  __int64 v14; // rbp
  __int64 v15; // rax
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  _QWORD *v23; // [rsp+20h] [rbp-A8h] BYREF
  volatile signed __int32 *v24; // [rsp+28h] [rbp-A0h]
  __int64 v25; // [rsp+30h] [rbp-98h]
  const struct arrow::DataType *v26; // [rsp+38h] [rbp-90h]
  volatile signed __int32 *v27; // [rsp+40h] [rbp-88h]
  arrow::DataType *v28; // [rsp+48h] [rbp-80h]
  volatile signed __int32 *v29; // [rsp+50h] [rbp-78h]
  __int64 v30; // [rsp+58h] [rbp-70h]
  volatile signed __int32 *v31; // [rsp+60h] [rbp-68h]
  _BYTE v32[24]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v33[32]; // [rsp+80h] [rbp-48h] BYREF
  char v34; // [rsp+D8h] [rbp+10h]

  v25 = -2;
  v6 = 0;
  v34 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  *a1 = &arrow::ExtensionArray::`vftable';
  a1[4] = 0;
  a1[5] = 0;
  if ( *(_DWORD *)(*a2 + 24LL) != 30 )
  {
    v7 = arrow::util::ArrowLog::ArrowLog(
           v32,
           "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\extension_type.cc",
           49,
           3);
    v6 = 1;
    v34 = 1;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      std::operator<<<std::char_traits<char>>(v8, " Check failed: (type->id()) == (Type::EXTENSION) ");
    }
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    v34 = v6;
    arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v32);
  }
  v9 = *a2;
  v10 = *(volatile signed __int32 **)(*a2 + 64LL);
  if ( v10 )
  {
    _InterlockedIncrement(v10 + 2);
    v10 = *(volatile signed __int32 **)(v9 + 64);
    v6 = v34;
  }
  v11 = *(const struct arrow::DataType **)(v9 + 56);
  v26 = v11;
  v27 = v10;
  v12 = *(_QWORD *)(*a3 + 8);
  v13 = *(volatile signed __int32 **)(v12 + 8);
  if ( v13 )
  {
    _InterlockedIncrement(v13 + 2);
    v13 = *(volatile signed __int32 **)(v12 + 8);
    v6 = v34;
  }
  v28 = *(arrow::DataType **)v12;
  v29 = v13;
  if ( !arrow::DataType::Equals(v28, v11, 0) )
  {
    v14 = arrow::util::ArrowLog::ArrowLog(
            v33,
            "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\extension_type.cc",
            51,
            3);
    v6 |= 2u;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) )
    {
      v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      std::operator<<<std::char_traits<char>>(
        v15,
        " Check failed: storage->type()->Equals(*checked_cast<const ExtensionType&>(*type).storage_type()) ");
    }
  }
  if ( (v6 & 2) != 0 )
    arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v33);
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v16 = *a3;
  v17 = *(volatile signed __int32 **)(*a3 + 16);
  if ( v17 )
  {
    _InterlockedIncrement(v17 + 2);
    v17 = *(volatile signed __int32 **)(v16 + 16);
  }
  v30 = *(_QWORD *)(v16 + 8);
  v31 = v17;
  arrow::ArrayData::Copy(v30, &v23);
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = a2[1];
  if ( v18 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
    v18 = a2[1];
  }
  v19 = v23;
  *v23 = *a2;
  v20 = (volatile signed __int32 *)v19[1];
  v19[1] = v18;
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  arrow::ExtensionArray::SetData(a1, &v23);
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      v21 = v24;
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18025e2c0  mov     rax, rsp
0x18025e2c3  mov     [rax+8], rcx
0x18025e2c7  push    rsi
0x18025e2c8  push    rdi
0x18025e2c9  push    r12
0x18025e2cb  push    r14
0x18025e2cd  push    r15
0x18025e2cf  sub     rsp, 0A0h
0x18025e2d6  mov     [rsp+0C8h+var_98], 0FFFFFFFFFFFFFFFEh
0x18025e2df  mov     [rax+18h], rbx
0x18025e2e3  mov     [rax+20h], rbp
0x18025e2e7  mov     r12, r8
0x18025e2ea  mov     r15, rdx
0x18025e2ed  mov     r14, rcx
0x18025e2f0  xor     edi, edi
0x18025e2f2  mov     [rax+10h], edi
0x18025e2f5  mov     [rcx+8], rdi
0x18025e2f9  mov     [rcx+10h], rdi
0x18025e2fd  mov     [rcx+18h], rdi
0x18025e301  lea     rax, ??_7ExtensionArray@arrow@@6B@; const arrow::ExtensionArray::`vftable'
0x18025e308  mov     [rcx], rax
0x18025e30b  mov     [rcx+20h], rdi
0x18025e30f  mov     [rcx+28h], rdi
0x18025e313  mov     rax, [rdx]
0x18025e316  cmp     dword ptr [rax+18h], 1Eh
0x18025e31a  jz      short loc_18025E378
0x18025e31c  lea     r9d, [rdi+3]
0x18025e320  lea     r8d, [rdi+31h]
0x18025e324  lea     rdx, aCSourceSrcSubm_0; "c:\\source\\src\\submodules\\apache\\ar"...
0x18025e32b  lea     rcx, [rsp+0C8h+var_60]
0x18025e330  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x18025e335  mov     rbx, rax
0x18025e338  mov     edi, 1
0x18025e33d  mov     [rsp+0C8h+arg_8], edi
0x18025e344  mov     rcx, [rax]
0x18025e347  mov     rax, [rcx+8]
0x18025e34b  mov     rcx, rbx
0x18025e34e  call    cs:__guard_dispatch_icall_fptr
0x18025e354  test    al, al
0x18025e356  jz      short loc_18025E378
0x18025e358  mov     rax, [rbx]
0x18025e35b  mov     rcx, rbx
0x18025e35e  mov     rax, [rax+10h]
0x18025e362  call    cs:__guard_dispatch_icall_fptr
0x18025e368  mov     rcx, rax
0x18025e36b  lea     rdx, aCheckFailedTyp_2; " Check failed: (type->id()) == (Type::E"...
0x18025e372  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18025e377  nop
0x18025e378  test    dil, 1
0x18025e37c  jz      short loc_18025E392
0x18025e37e  and     edi, 0FFFFFFFEh
0x18025e381  mov     [rsp+0C8h+arg_8], edi
0x18025e388  lea     rcx, [rsp+0C8h+var_60]; this
0x18025e38d  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x18025e392  mov     rax, [r15]
0x18025e395  mov     rbx, [rax+40h]
0x18025e399  test    rbx, rbx
0x18025e39c  jz      short loc_18025E3AD
0x18025e39e  lock inc dword ptr [rbx+8]
0x18025e3a2  mov     rbx, [rax+40h]
0x18025e3a6  mov     edi, [rsp+0C8h+arg_8]
0x18025e3ad  mov     rdx, [rax+38h]; struct arrow::DataType *
0x18025e3b1  mov     [rsp+0C8h+var_90], rdx
0x18025e3b6  mov     [rsp+0C8h+var_88], rbx
0x18025e3bb  mov     rax, [r12]
0x18025e3bf  mov     rcx, [rax+8]
0x18025e3c3  mov     rsi, [rcx+8]
0x18025e3c7  test    rsi, rsi
0x18025e3ca  jz      short loc_18025E3DB
0x18025e3cc  lock inc dword ptr [rsi+8]
0x18025e3d0  mov     rsi, [rcx+8]
0x18025e3d4  mov     edi, [rsp+0C8h+arg_8]
0x18025e3db  mov     rcx, [rcx]; this
0x18025e3de  mov     [rsp+0C8h+var_80], rcx
0x18025e3e3  mov     [rsp+0C8h+var_78], rsi
0x18025e3e8  xor     r8d, r8d; bool
0x18025e3eb  call    ?Equals@DataType@arrow@@QEBA_NAEBV12@_N@Z; arrow::DataType::Equals(arrow::DataType const &,bool)
0x18025e3f0  test    al, al
0x18025e3f2  jnz     short loc_18025E454
0x18025e3f4  mov     r9d, 3
0x18025e3fa  lea     r8d, [r9+30h]
0x18025e3fe  lea     rdx, aCSourceSrcSubm_0; "c:\\source\\src\\submodules\\apache\\ar"...
0x18025e405  lea     rcx, [rsp+0C8h+var_48]
0x18025e40d  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x18025e412  mov     rbp, rax
0x18025e415  or      edi, 2
0x18025e418  mov     [rsp+0C8h+arg_8], edi
0x18025e41f  mov     rcx, [rax]
0x18025e422  mov     rax, [rcx+8]
0x18025e426  mov     rcx, rbp
0x18025e429  call    cs:__guard_dispatch_icall_fptr
0x18025e42f  test    al, al
0x18025e431  jz      short loc_18025E454
0x18025e433  mov     rax, [rbp+0]
0x18025e437  mov     rcx, rbp
0x18025e43a  mov     rax, [rax+10h]
0x18025e43e  call    cs:__guard_dispatch_icall_fptr
0x18025e444  mov     rcx, rax
0x18025e447  lea     rdx, aCheckFailedSto; " Check failed: storage->type()->Equals("...
0x18025e44e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18025e453  nop
0x18025e454  test    dil, 2
0x18025e458  jz      short loc_18025E468
0x18025e45a  lea     rcx, [rsp+0C8h+var_48]; this
0x18025e462  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x18025e467  nop
0x18025e468  mov     edi, 0FFFFFFFFh
0x18025e46d  test    rsi, rsi
0x18025e470  jz      short loc_18025E4AA
0x18025e472  mov     eax, edi
0x18025e474  lock xadd [rsi+8], eax
0x18025e479  cmp     eax, 1
0x18025e47c  jnz     short loc_18025E4AA
0x18025e47e  mov     rax, [rsi]
0x18025e481  mov     rcx, rsi
0x18025e484  mov     rax, [rax]
0x18025e487  call    cs:__guard_dispatch_icall_fptr
0x18025e48d  mov     eax, edi
0x18025e48f  lock xadd [rsi+0Ch], eax
0x18025e494  cmp     eax, 1
0x18025e497  jnz     short loc_18025E4AA
0x18025e499  mov     rax, [rsi]
0x18025e49c  mov     rcx, rsi
0x18025e49f  mov     rax, [rax+8]
0x18025e4a3  call    cs:__guard_dispatch_icall_fptr
0x18025e4a9  nop
0x18025e4aa  test    rbx, rbx
0x18025e4ad  jz      short loc_18025E4E6
0x18025e4af  mov     eax, edi
0x18025e4b1  lock xadd [rbx+8], eax
0x18025e4b6  cmp     eax, 1
0x18025e4b9  jnz     short loc_18025E4E6
0x18025e4bb  mov     rax, [rbx]
0x18025e4be  mov     rcx, rbx
0x18025e4c1  mov     rax, [rax]
0x18025e4c4  call    cs:__guard_dispatch_icall_fptr
0x18025e4ca  mov     eax, edi
0x18025e4cc  lock xadd [rbx+0Ch], eax
0x18025e4d1  cmp     eax, 1
0x18025e4d4  jnz     short loc_18025E4E6
0x18025e4d6  mov     rax, [rbx]
0x18025e4d9  mov     rcx, rbx
0x18025e4dc  mov     rax, [rax+8]
0x18025e4e0  call    cs:__guard_dispatch_icall_fptr
0x18025e4e6  mov     rcx, [r12]
0x18025e4ea  mov     rbx, [rcx+10h]
0x18025e4ee  test    rbx, rbx
0x18025e4f1  jz      short loc_18025E4FB
0x18025e4f3  lock inc dword ptr [rbx+8]
0x18025e4f7  mov     rbx, [rcx+10h]
0x18025e4fb  mov     rcx, [rcx+8]
0x18025e4ff  mov     [rsp+0C8h+var_70], rcx
0x18025e504  mov     [rsp+0C8h+var_68], rbx
0x18025e509  lea     rdx, [rsp+0C8h+var_A8]
0x18025e50e  call    ?Copy@ArrayData@arrow@@QEBA?AV?$shared_ptr@UArrayData@arrow@@@std@@XZ; arrow::ArrayData::Copy(void)
0x18025e513  nop
0x18025e514  test    rbx, rbx
0x18025e517  jz      short loc_18025E550
0x18025e519  mov     eax, edi
0x18025e51b  lock xadd [rbx+8], eax
0x18025e520  cmp     eax, 1
0x18025e523  jnz     short loc_18025E550
0x18025e525  mov     rax, [rbx]
0x18025e528  mov     rcx, rbx
0x18025e52b  mov     rax, [rax]
0x18025e52e  call    cs:__guard_dispatch_icall_fptr
0x18025e534  mov     eax, edi
0x18025e536  lock xadd [rbx+0Ch], eax
0x18025e53b  cmp     eax, 1
0x18025e53e  jnz     short loc_18025E550
0x18025e540  mov     rax, [rbx]
0x18025e543  mov     rcx, rbx
0x18025e546  mov     rax, [rax+8]
0x18025e54a  call    cs:__guard_dispatch_icall_fptr
0x18025e550  mov     rdx, [r15+8]
0x18025e554  test    rdx, rdx
0x18025e557  jz      short loc_18025E561
0x18025e559  lock inc dword ptr [rdx+8]
0x18025e55d  mov     rdx, [r15+8]
0x18025e561  mov     rax, [r15]
0x18025e564  mov     rcx, [rsp+0C8h+var_A8]
0x18025e569  mov     [rcx], rax
0x18025e56c  mov     rbx, [rcx+8]
0x18025e570  mov     [rcx+8], rdx
0x18025e574  test    rbx, rbx
0x18025e577  jz      short loc_18025E5B0
0x18025e579  mov     eax, edi
0x18025e57b  lock xadd [rbx+8], eax
0x18025e580  cmp     eax, 1
0x18025e583  jnz     short loc_18025E5B0
0x18025e585  mov     rax, [rbx]
0x18025e588  mov     rcx, rbx
0x18025e58b  mov     rax, [rax]
0x18025e58e  call    cs:__guard_dispatch_icall_fptr
0x18025e594  mov     eax, edi
0x18025e596  lock xadd [rbx+0Ch], eax
0x18025e59b  cmp     eax, 1
0x18025e59e  jnz     short loc_18025E5B0
0x18025e5a0  mov     rax, [rbx]
0x18025e5a3  mov     rcx, rbx
0x18025e5a6  mov     rax, [rax+8]
0x18025e5aa  call    cs:__guard_dispatch_icall_fptr
0x18025e5b0  lea     rdx, [rsp+0C8h+var_A8]
0x18025e5b5  mov     rcx, r14
0x18025e5b8  call    ?SetData@ExtensionArray@arrow@@IEAAXAEBV?$shared_ptr@UArrayData@arrow@@@std@@@Z; arrow::ExtensionArray::SetData(std::shared_ptr<arrow::ArrayData> const &)
0x18025e5bd  nop
0x18025e5be  mov     rcx, [rsp+0C8h+var_A0]
0x18025e5c3  test    rcx, rcx
0x18025e5c6  jz      short loc_18025E605
0x18025e5c8  mov     eax, edi
0x18025e5ca  lock xadd [rcx+8], eax
0x18025e5cf  cmp     eax, 1
0x18025e5d2  jnz     short loc_18025E605
0x18025e5d4  mov     rbx, [rsp+0C8h+var_A0]
0x18025e5d9  mov     rax, [rbx]
0x18025e5dc  mov     rcx, rbx
0x18025e5df  mov     rax, [rax]
0x18025e5e2  call    cs:__guard_dispatch_icall_fptr
0x18025e5e8  lock xadd [rbx+0Ch], edi
0x18025e5ed  cmp     edi, 1
0x18025e5f0  jnz     short loc_18025E605
0x18025e5f2  mov     rcx, [rsp+0C8h+var_A0]
0x18025e5f7  mov     rax, [rcx]
0x18025e5fa  mov     rax, [rax+8]
0x18025e5fe  call    cs:__guard_dispatch_icall_fptr
0x18025e604  nop
0x18025e605  mov     rax, r14
0x18025e608  lea     r11, [rsp+0C8h+var_28]
0x18025e610  mov     rbx, [r11+40h]
0x18025e614  mov     rbp, [r11+48h]
0x18025e618  mov     rsp, r11
0x18025e61b  pop     r15
0x18025e61d  pop     r14
0x18025e61f  pop     r12
0x18025e621  pop     rdi
0x18025e622  pop     rsi
0x18025e623  retn
```
