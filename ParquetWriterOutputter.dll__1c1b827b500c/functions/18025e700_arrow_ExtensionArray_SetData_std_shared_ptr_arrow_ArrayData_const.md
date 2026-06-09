# arrow::ExtensionArray::SetData(std::shared_ptr<arrow::ArrayData> const &)

- ea: `0x18025e700`
- end: `0x18025e967`
- name: `?SetData@ExtensionArray@arrow@@IEAAXAEBV?$shared_ptr@UArrayData@arrow@@@std@@@Z`
- size: `615`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18025e270`
- `0x18025e2c0`

## callees

- `0x18001b360`
- `0x180049a90`
- `0x1800c6140`
- `0x1800dc8f0`
- `0x1800dca00`
- `0x1800f2950`
- `0x18025e700`
- `0x180358070`

## string_xrefs

- `0x18025e737`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\extension_type.cc`
- `0x18025e77e`: ` Check failed: (data->type->id()) == (Type::EXTENSION) `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::ExtensionArray::SetData(_QWORD *a1, __int64 **a2)
{
  char v4; // di
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  volatile signed __int32 *v12; // rdi
  __int64 result; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rdi
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  _QWORD *v19; // [rsp+28h] [rbp-50h] BYREF
  volatile signed __int32 *v20; // [rsp+30h] [rbp-48h]
  _BYTE v21[8]; // [rsp+38h] [rbp-40h] BYREF
  volatile signed __int32 *v22; // [rsp+40h] [rbp-38h]
  _BYTE v23[48]; // [rsp+48h] [rbp-30h] BYREF

  v4 = 0;
  if ( *(_DWORD *)(**a2 + 24) != 30 )
  {
    v5 = arrow::util::ArrowLog::ArrowLog(
           v23,
           "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\extension_type.cc",
           59,
           3);
    v4 = 1;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) )
    {
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      std::operator<<<std::char_traits<char>>(v6, " Check failed: (data->type->id()) == (Type::EXTENSION) ");
    }
  }
  if ( (v4 & 1) != 0 )
    arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v23);
  v7 = (__int64 *)(*a2)[5];
  if ( ((*a2)[6] - (__int64)v7) >> 4 && (v8 = *v7) != 0 )
  {
    if ( *(_BYTE *)(v8 + 9) )
      a1[3] = *(_QWORD *)(v8 + 16);
    else
      a1[3] = 0;
  }
  else
  {
    a1[3] = 0;
  }
  std::shared_ptr<arrow::ArrayData>::operator=(a1 + 1, a2);
  arrow::ArrayData::Copy(*a2, &v19);
  v9 = **a2;
  v10 = *(_QWORD *)(v9 + 64);
  if ( v10 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v10 = *(_QWORD *)(v9 + 64);
  }
  v11 = v19;
  *v19 = *(_QWORD *)(v9 + 56);
  v12 = (volatile signed __int32 *)v11[1];
  v11[1] = v10;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  result = arrow::MakeArray(v21, &v19);
  v14 = *(_QWORD *)result;
  v15 = *(_QWORD *)(result + 8);
  *(_QWORD *)result = 0;
  *(_QWORD *)(result + 8) = 0;
  a1[4] = v14;
  v16 = (volatile signed __int32 *)a1[5];
  a1[5] = v15;
  if ( v16 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      result = (unsigned int)_InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v17 = v22;
  if ( v22 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      result = (unsigned int)_InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = v20;
  if ( v20 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      result = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18025e700  mov     rax, rsp
0x18025e703  push    rsi
0x18025e704  push    rdi
0x18025e705  push    r14
0x18025e707  sub     rsp, 60h
0x18025e70b  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18025e713  mov     [rax+18h], rbx
0x18025e717  mov     rbx, rdx
0x18025e71a  mov     rsi, rcx
0x18025e71d  xor     edi, edi
0x18025e71f  mov     [rax+8], edi
0x18025e722  mov     rax, [rdx]
0x18025e725  mov     r8, [rax]
0x18025e728  cmp     dword ptr [r8+18h], 1Eh
0x18025e72d  jz      short loc_18025E78B
0x18025e72f  lea     r9d, [rdi+3]
0x18025e733  lea     r8d, [rdi+3Bh]
0x18025e737  lea     rdx, aCSourceSrcSubm_0; "c:\\source\\src\\submodules\\apache\\ar"...
0x18025e73e  lea     rcx, [rsp+78h+var_30]
0x18025e743  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x18025e748  mov     r14, rax
0x18025e74b  mov     edi, 1
0x18025e750  mov     [rsp+78h+arg_0], edi
0x18025e757  mov     rcx, [rax]
0x18025e75a  mov     rax, [rcx+8]
0x18025e75e  mov     rcx, r14
0x18025e761  call    cs:__guard_dispatch_icall_fptr
0x18025e767  test    al, al
0x18025e769  jz      short loc_18025E78B
0x18025e76b  mov     rax, [r14]
0x18025e76e  mov     rcx, r14
0x18025e771  mov     rax, [rax+10h]
0x18025e775  call    cs:__guard_dispatch_icall_fptr
0x18025e77b  mov     rcx, rax
0x18025e77e  lea     rdx, aCheckFailedDat_8; " Check failed: (data->type->id()) == (T"...
0x18025e785  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18025e78a  nop
0x18025e78b  test    dil, 1
0x18025e78f  jz      short loc_18025E79B
0x18025e791  lea     rcx, [rsp+78h+var_30]; this
0x18025e796  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x18025e79b  mov     rax, [rbx]
0x18025e79e  mov     rdx, [rax+28h]
0x18025e7a2  mov     rcx, [rax+30h]
0x18025e7a6  sub     rcx, rdx
0x18025e7a9  sar     rcx, 4
0x18025e7ad  test    rcx, rcx
0x18025e7b0  jz      short loc_18025E7D2
0x18025e7b2  mov     rax, [rdx]
0x18025e7b5  test    rax, rax
0x18025e7b8  jz      short loc_18025E7D2
0x18025e7ba  cmp     byte ptr [rax+9], 0
0x18025e7be  jz      short loc_18025E7CA
0x18025e7c0  mov     rcx, [rax+10h]
0x18025e7c4  mov     [rsi+18h], rcx
0x18025e7c8  jmp     short loc_18025E7DA
0x18025e7ca  xor     ecx, ecx
0x18025e7cc  mov     [rsi+18h], rcx
0x18025e7d0  jmp     short loc_18025E7DA
0x18025e7d2  mov     qword ptr [rsi+18h], 0
0x18025e7da  lea     rcx, [rsi+8]
0x18025e7de  mov     rdx, rbx
0x18025e7e1  call    ??4?$shared_ptr@UArrayData@arrow@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<arrow::ArrayData>::operator=(std::shared_ptr<arrow::ArrayData> const &)
0x18025e7e6  lea     rdx, [rsp+78h+var_50]
0x18025e7eb  mov     rcx, [rbx]
0x18025e7ee  call    ?Copy@ArrayData@arrow@@QEBA?AV?$shared_ptr@UArrayData@arrow@@@std@@XZ; arrow::ArrayData::Copy(void)
0x18025e7f3  nop
0x18025e7f4  mov     rax, [rbx]
0x18025e7f7  mov     rax, [rax]
0x18025e7fa  mov     rdx, [rax+40h]
0x18025e7fe  test    rdx, rdx
0x18025e801  jz      short loc_18025E80B
0x18025e803  lock inc dword ptr [rdx+8]
0x18025e807  mov     rdx, [rax+40h]
0x18025e80b  mov     rcx, [rsp+78h+var_50]
0x18025e810  mov     rax, [rax+38h]
0x18025e814  mov     [rcx], rax
0x18025e817  mov     rdi, [rcx+8]
0x18025e81b  mov     [rcx+8], rdx
0x18025e81f  mov     ebx, 0FFFFFFFFh
0x18025e824  test    rdi, rdi
0x18025e827  jz      short loc_18025E860
0x18025e829  mov     eax, ebx
0x18025e82b  lock xadd [rdi+8], eax
0x18025e830  cmp     eax, 1
0x18025e833  jnz     short loc_18025E860
0x18025e835  mov     rax, [rdi]
0x18025e838  mov     rcx, rdi
0x18025e83b  mov     rax, [rax]
0x18025e83e  call    cs:__guard_dispatch_icall_fptr
0x18025e844  mov     eax, ebx
0x18025e846  lock xadd [rdi+0Ch], eax
0x18025e84b  cmp     eax, 1
0x18025e84e  jnz     short loc_18025E860
0x18025e850  mov     rax, [rdi]
0x18025e853  mov     rcx, rdi
0x18025e856  mov     rax, [rax+8]
0x18025e85a  call    cs:__guard_dispatch_icall_fptr
0x18025e860  lea     rdx, [rsp+78h+var_50]
0x18025e865  lea     rcx, [rsp+78h+var_40]
0x18025e86a  call    ?MakeArray@arrow@@YA?AV?$shared_ptr@VArray@arrow@@@std@@AEBV?$shared_ptr@UArrayData@arrow@@@3@@Z; arrow::MakeArray(std::shared_ptr<arrow::ArrayData> const &)
0x18025e86f  mov     rcx, [rax]
0x18025e872  mov     rdx, [rax+8]
0x18025e876  mov     qword ptr [rax], 0
0x18025e87d  mov     qword ptr [rax+8], 0
0x18025e885  mov     [rsi+20h], rcx
0x18025e889  mov     [rsp+78h+arg_8], rdx
0x18025e891  mov     rdi, [rsi+28h]
0x18025e895  mov     [rsi+28h], rdx
0x18025e899  test    rdi, rdi
0x18025e89c  jz      short loc_18025E8D5
0x18025e89e  mov     eax, ebx
0x18025e8a0  lock xadd [rdi+8], eax
0x18025e8a5  cmp     eax, 1
0x18025e8a8  jnz     short loc_18025E8D5
0x18025e8aa  mov     rax, [rdi]
0x18025e8ad  mov     rcx, rdi
0x18025e8b0  mov     rax, [rax]
0x18025e8b3  call    cs:__guard_dispatch_icall_fptr
0x18025e8b9  mov     eax, ebx
0x18025e8bb  lock xadd [rdi+0Ch], eax
0x18025e8c0  cmp     eax, 1
0x18025e8c3  jnz     short loc_18025E8D5
0x18025e8c5  mov     rax, [rdi]
0x18025e8c8  mov     rcx, rdi
0x18025e8cb  mov     rax, [rax+8]
0x18025e8cf  call    cs:__guard_dispatch_icall_fptr
0x18025e8d5  mov     rdi, [rsp+78h+var_38]
0x18025e8da  test    rdi, rdi
0x18025e8dd  jz      short loc_18025E917
0x18025e8df  mov     eax, ebx
0x18025e8e1  lock xadd [rdi+8], eax
0x18025e8e6  cmp     eax, 1
0x18025e8e9  jnz     short loc_18025E917
0x18025e8eb  mov     rax, [rdi]
0x18025e8ee  mov     rcx, rdi
0x18025e8f1  mov     rax, [rax]
0x18025e8f4  call    cs:__guard_dispatch_icall_fptr
0x18025e8fa  mov     eax, ebx
0x18025e8fc  lock xadd [rdi+0Ch], eax
0x18025e901  cmp     eax, 1
0x18025e904  jnz     short loc_18025E917
0x18025e906  mov     rax, [rdi]
0x18025e909  mov     rcx, rdi
0x18025e90c  mov     rax, [rax+8]
0x18025e910  call    cs:__guard_dispatch_icall_fptr
0x18025e916  nop
0x18025e917  mov     rdi, [rsp+78h+var_48]
0x18025e91c  test    rdi, rdi
0x18025e91f  jz      short loc_18025E956
0x18025e921  mov     eax, ebx
0x18025e923  lock xadd [rdi+8], eax
0x18025e928  cmp     eax, 1
0x18025e92b  jnz     short loc_18025E956
0x18025e92d  mov     rax, [rdi]
0x18025e930  mov     rcx, rdi
0x18025e933  mov     rax, [rax]
0x18025e936  call    cs:__guard_dispatch_icall_fptr
0x18025e93c  lock xadd [rdi+0Ch], ebx
0x18025e941  cmp     ebx, 1
0x18025e944  jnz     short loc_18025E956
0x18025e946  mov     rax, [rdi]
0x18025e949  mov     rcx, rdi
0x18025e94c  mov     rax, [rax+8]
0x18025e950  call    cs:__guard_dispatch_icall_fptr
0x18025e956  mov     rbx, [rsp+78h+arg_10]
0x18025e95e  add     rsp, 60h
0x18025e962  pop     r14
0x18025e964  pop     rdi
0x18025e965  pop     rsi
0x18025e966  retn
```
