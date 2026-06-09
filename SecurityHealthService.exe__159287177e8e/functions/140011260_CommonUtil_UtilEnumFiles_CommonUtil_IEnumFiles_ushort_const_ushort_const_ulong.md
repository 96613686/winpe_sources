# CommonUtil::UtilEnumFiles(CommonUtil::IEnumFiles * *,ushort const *,ushort const *,ulong)

- ea: `0x140011260`
- end: `0x140011345`
- name: `?UtilEnumFiles@CommonUtil@@YAJPEAPEAUIEnumFiles@1@PEBG1K@Z`
- size: `229`
- prototype: `__int64 __fastcall(CommonUtil *this, struct CommonUtil::IEnumFiles **, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006714`

## callees

- `0x1400015f4`
- `0x14000202c`
- `0x1400100bc`
- `0x140011260`
- `0x140011cf0`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilEnumFiles(
        CommonUtil *this,
        struct CommonUtil::IEnumFiles **a2,
        unsigned __int16 **a3,
        const unsigned __int16 *a4)
{
  int v5; // r14d
  unsigned __int64 v8; // rdx
  int v9; // edi
  const unsigned __int16 *v10; // r8
  __int64 v11; // rax
  _QWORD *v12; // rbx
  CommonUtil *v13; // rdi
  void *v14; // rcx
  unsigned __int64 v15; // rdx
  const unsigned __int16 *v16; // r8
  void *v17; // rcx
  _QWORD *v19; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  v19 = 0;
  v5 = (int)a4;
  v9 = CommonUtil::CreateNewRefObject<CommonUtil::CFlatEnumFiles>(&v19);
  if ( v9 >= 0 )
  {
    v12 = v19;
    v13 = (CommonUtil *)(v19 + 3);
    v14 = (void *)v19[3];
    if ( v14 )
    {
      operator delete(v14, v8);
      *(_QWORD *)v13 = 0;
    }
    v9 = CommonUtil::HrDuplicateStringW(v13, (unsigned __int16 **)a2, v10);
    if ( v9 >= 0 )
    {
      v17 = (void *)v12[4];
      if ( v17 )
      {
        operator delete(v17, v15);
        v12[4] = 0;
      }
      v9 = CommonUtil::HrDuplicateStringW((CommonUtil *)(v12 + 4), a3, v16);
      if ( v9 >= 0 )
      {
        memset_0(v12 + 5, 0, 0x250u);
        *((_DWORD *)v12 + 160) = v5;
        v9 = 0;
        *(_QWORD *)this = v12;
        return (unsigned int)v9;
      }
    }
    if ( v12 )
    {
      v11 = *v12;
      goto LABEL_12;
    }
  }
  else if ( v19 )
  {
    v11 = *v19;
LABEL_12:
    (*(void (**)(void))(v11 + 8))();
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140011260  push    rbx
0x140011262  push    rbp
0x140011263  push    rsi
0x140011264  push    rdi
0x140011265  push    r14
0x140011267  push    r15
0x140011269  sub     rsp, 28h
0x14001126d  mov     rsi, rcx
0x140011270  mov     qword ptr [rcx], 0
0x140011277  lea     rcx, [rsp+58h+arg_0]
0x14001127c  mov     [rsp+58h+arg_0], 0
0x140011285  mov     r14d, r9d
0x140011288  mov     r15, r8
0x14001128b  mov     rbp, rdx
0x14001128e  call    ??$CreateNewRefObject@VCFlatEnumFiles@CommonUtil@@@CommonUtil@@YAJPEAPEAVCFlatEnumFiles@0@@Z; CommonUtil::CreateNewRefObject<CommonUtil::CFlatEnumFiles>(CommonUtil::CFlatEnumFiles * *)
0x140011293  mov     edi, eax
0x140011295  test    eax, eax
0x140011297  jns     short loc_1400112AC
0x140011299  mov     rcx, [rsp+58h+arg_0]
0x14001129e  test    rcx, rcx
0x1400112a1  jz      loc_140011336
0x1400112a7  mov     rax, [rcx]
0x1400112aa  jmp     short loc_14001130E
0x1400112ac  mov     rbx, [rsp+58h+arg_0]
0x1400112b1  lea     rdi, [rbx+18h]
0x1400112b5  mov     rcx, [rdi]; void *
0x1400112b8  test    rcx, rcx
0x1400112bb  jz      short loc_1400112C9
0x1400112bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400112c2  mov     qword ptr [rdi], 0
0x1400112c9  mov     rdx, rbp; unsigned __int16 **
0x1400112cc  mov     rcx, rdi; this
0x1400112cf  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x1400112d4  mov     edi, eax
0x1400112d6  test    eax, eax
0x1400112d8  js      short loc_140011303
0x1400112da  lea     rdi, [rbx+20h]
0x1400112de  mov     rcx, [rdi]; void *
0x1400112e1  test    rcx, rcx
0x1400112e4  jz      short loc_1400112F2
0x1400112e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400112eb  mov     qword ptr [rdi], 0
0x1400112f2  mov     rdx, r15; unsigned __int16 **
0x1400112f5  mov     rcx, rdi; this
0x1400112f8  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x1400112fd  mov     edi, eax
0x1400112ff  test    eax, eax
0x140011301  jns     short loc_140011319
0x140011303  test    rbx, rbx
0x140011306  jz      short loc_140011336
0x140011308  mov     rax, [rbx]
0x14001130b  mov     rcx, rbx
0x14001130e  mov     rax, [rax+8]
0x140011312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011317  jmp     short loc_140011336
0x140011319  lea     rcx, [rbx+28h]; void *
0x14001131d  xor     edx, edx; Val
0x14001131f  mov     r8d, 250h; Size
0x140011325  call    memset_0
0x14001132a  mov     [rbx+280h], r14d
0x140011331  xor     edi, edi
0x140011333  mov     [rsi], rbx
0x140011336  mov     eax, edi
0x140011338  add     rsp, 28h
0x14001133c  pop     r15
0x14001133e  pop     r14
0x140011340  pop     rdi
0x140011341  pop     rsi
0x140011342  pop     rbp
0x140011343  pop     rbx
0x140011344  retn
```
