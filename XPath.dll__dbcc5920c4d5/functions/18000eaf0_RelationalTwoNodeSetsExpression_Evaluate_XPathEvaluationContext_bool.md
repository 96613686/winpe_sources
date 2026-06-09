# RelationalTwoNodeSetsExpression::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x18000eaf0`
- end: `0x18000eda0`
- name: `?Evaluate@RelationalTwoNodeSetsExpression@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `688`
- prototype: `__int64 __fastcall(RelationalTwoNodeSetsExpression *__hidden this, struct XPathEvaluationContext *, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800068d8`
- `0x18000e594`
- `0x18000eaf0`
- `0x180010ee0`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall RelationalTwoNodeSetsExpression::Evaluate(
        RelationalTwoNodeSetsExpression *this,
        struct XPathEvaluationContext *a2,
        bool *a3)
{
  __int64 *v4; // rcx
  __int64 v5; // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  int v10; // esi
  char v11; // r12
  __int64 (*i)(void); // rax
  int v13; // eax
  int v14; // r15d
  __int64 v15; // rcx
  XPathNavigatorInternal *v16; // rax
  int Value; // eax
  unsigned __int8 (__fastcall *v18)(__int64 *, __int64 *); // rax
  __int64 v19; // rcx
  XPathNavigatorInternal *v20; // rax
  unsigned __int8 (__fastcall *v21)(__int64 *, __int64 *); // r8
  unsigned __int8 (__fastcall *v22)(__int64 *, __int64 *); // rax
  __int64 v24; // [rsp+20h] [rbp-30h] BYREF
  __int64 v25; // [rsp+28h] [rbp-28h] BYREF
  __int64 v26; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+38h] [rbp-18h] BYREF
  __int64 v28; // [rsp+40h] [rbp-10h] BYREF
  __int64 v29; // [rsp+48h] [rbp-8h] BYREF
  __int64 v30; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int16 *v31; // [rsp+A8h] [rbp+58h] BYREF

  v4 = (__int64 *)*((_QWORD *)this + 3);
  v5 = 0;
  v31 = 0;
  v30 = 0;
  v8 = 0;
  v25 = 0;
  v9 = *v4;
  v24 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *))(v9 + 96))(v4);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *))(**((_QWORD **)this + 4) + 96LL))(
            *((_QWORD *)this + 4),
            a2);
    if ( v10 >= 0 )
    {
      *a3 = 0;
      v11 = 1;
      v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
      for ( i = *(__int64 (**)(void))(**((_QWORD **)this + 4) + 48LL);
            ;
            i = *(__int64 (**)(void))(**((_QWORD **)this + 4) + 48LL) )
      {
        v13 = i();
        v14 = v13;
        if ( v10 == 1 && v13 == 1 )
          goto LABEL_39;
        if ( v10 < 0 )
          goto LABEL_41;
        if ( v13 < 0 )
          break;
        if ( v11 && (v10 == 1 || v13 == 1) )
          goto LABEL_39;
        if ( v10 != 1 )
        {
          v15 = *((_QWORD *)this + 3);
          v31 = 0;
          v16 = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 72LL))(v15);
          Value = XPathNavigatorInternal::GetValue(v16, (const unsigned __int16 **)&v31);
          if ( Value < 0 || (Value = String::Initialize((String *)&v30, v31), Value < 0) )
          {
LABEL_37:
            v10 = Value;
            goto LABEL_41;
          }
          if ( v11 )
            goto LABEL_20;
          v18 = (unsigned __int8 (__fastcall *)(__int64 *, __int64 *))*((_QWORD *)this + 2);
          v26 = v8;
          if ( v8 )
            _InterlockedIncrement((volatile signed __int32 *)(v8 - 8));
          v27 = v30;
          if ( v30 )
            _InterlockedIncrement((volatile signed __int32 *)(v30 - 8));
          if ( v18(&v27, &v26) )
          {
LABEL_20:
            String::operator=(&v25, &v30);
            v8 = v25;
          }
        }
        if ( v14 != 1 )
        {
          v19 = *((_QWORD *)this + 4);
          v31 = 0;
          v20 = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
          Value = XPathNavigatorInternal::GetValue(v20, (const unsigned __int16 **)&v31);
          if ( Value < 0 )
            goto LABEL_37;
          Value = String::Initialize((String *)&v30, v31);
          if ( Value < 0 )
            goto LABEL_37;
          if ( v11 )
            goto LABEL_30;
          v21 = (unsigned __int8 (__fastcall *)(__int64 *, __int64 *))*((_QWORD *)this + 2);
          v26 = v30;
          if ( v30 )
            _InterlockedIncrement((volatile signed __int32 *)(v30 - 8));
          v28 = v5;
          if ( v5 )
            _InterlockedIncrement((volatile signed __int32 *)(v5 - 8));
          if ( v21(&v28, &v26) )
          {
LABEL_30:
            String::operator=(&v24, &v30);
            v5 = v24;
          }
        }
        v22 = (unsigned __int8 (__fastcall *)(__int64 *, __int64 *))*((_QWORD *)this + 2);
        v26 = v5;
        if ( v5 )
          _InterlockedIncrement((volatile signed __int32 *)(v5 - 8));
        v29 = v8;
        if ( v8 )
          _InterlockedIncrement((volatile signed __int32 *)(v8 - 8));
        if ( v22(&v29, &v26) )
        {
          *a3 = 1;
LABEL_39:
          String::Reset((String *)&v24);
          String::Reset((String *)&v25);
          String::Reset((String *)&v30);
          return 0;
        }
        v11 = 0;
        v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
      }
      v10 = v13;
    }
  }
LABEL_41:
  String::Reset((String *)&v24);
  String::Reset((String *)&v25);
  String::Reset((String *)&v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000eaf0  mov     [rsp-38h+arg_8], rbx
0x18000eaf5  push    rbp
0x18000eaf6  push    rsi
0x18000eaf7  push    rdi
0x18000eaf8  push    r12
0x18000eafa  push    r13
0x18000eafc  push    r14
0x18000eafe  push    r15
0x18000eb00  mov     rbp, rsp
0x18000eb03  sub     rsp, 50h
0x18000eb07  xor     r12d, r12d
0x18000eb0a  mov     r14, rcx
0x18000eb0d  mov     rcx, [rcx+18h]
0x18000eb11  mov     ebx, r12d
0x18000eb14  mov     [rbp+arg_18], r12
0x18000eb18  mov     r13, r8
0x18000eb1b  mov     r15, rdx
0x18000eb1e  mov     [rbp+arg_0], r12
0x18000eb22  mov     edi, r12d
0x18000eb25  mov     [rbp+var_28], r12
0x18000eb29  mov     rax, [rcx]
0x18000eb2c  mov     [rbp+var_30], rbx
0x18000eb30  mov     rax, [rax+60h]
0x18000eb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb39  mov     esi, eax
0x18000eb3b  test    eax, eax
0x18000eb3d  js      loc_18000ED6B
0x18000eb43  mov     rcx, [r14+20h]
0x18000eb47  mov     rdx, r15
0x18000eb4a  mov     rax, [rcx]
0x18000eb4d  mov     rax, [rax+60h]
0x18000eb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb56  mov     esi, eax
0x18000eb58  test    eax, eax
0x18000eb5a  js      loc_18000ED6B
0x18000eb60  mov     [r13+0], r12b
0x18000eb64  mov     r12b, 1
0x18000eb67  mov     rcx, [r14+18h]
0x18000eb6b  mov     rax, [rcx]
0x18000eb6e  mov     rax, [rax+30h]
0x18000eb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb77  mov     rcx, [r14+20h]
0x18000eb7b  mov     esi, eax
0x18000eb7d  mov     rdx, [rcx]
0x18000eb80  mov     rax, [rdx+30h]
0x18000eb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb89  mov     r15d, eax
0x18000eb8c  cmp     esi, 1
0x18000eb8f  jnz     short loc_18000EB99
0x18000eb91  cmp     eax, esi
0x18000eb93  jz      loc_18000ED49
0x18000eb99  test    esi, esi
0x18000eb9b  js      loc_18000ED6B
0x18000eba1  test    r15d, r15d
0x18000eba4  js      loc_18000ED68
0x18000ebaa  test    r12b, r12b
0x18000ebad  jz      short loc_18000EBC2
0x18000ebaf  cmp     esi, 1
0x18000ebb2  jz      loc_18000ED49
0x18000ebb8  cmp     r15d, 1
0x18000ebbc  jz      loc_18000ED49
0x18000ebc2  cmp     esi, 1
0x18000ebc5  jz      loc_18000EC55
0x18000ebcb  mov     rcx, [r14+18h]
0x18000ebcf  mov     [rbp+arg_18], 0
0x18000ebd7  mov     rax, [rcx]
0x18000ebda  mov     rax, [rax+48h]
0x18000ebde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebe3  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18000ebe7  mov     rcx, rax; this
0x18000ebea  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000ebef  test    eax, eax
0x18000ebf1  js      loc_18000ED40
0x18000ebf7  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000ebfb  lea     rcx, [rbp+arg_0]; this
0x18000ebff  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000ec04  test    eax, eax
0x18000ec06  js      loc_18000ED40
0x18000ec0c  test    r12b, r12b
0x18000ec0f  jnz     short loc_18000EC44
0x18000ec11  mov     rax, [r14+10h]
0x18000ec15  mov     [rbp+var_20], rdi
0x18000ec19  test    rdi, rdi
0x18000ec1c  jz      short loc_18000EC22
0x18000ec1e  lock inc dword ptr [rdi-8]
0x18000ec22  mov     rcx, [rbp+arg_0]
0x18000ec26  mov     [rbp+var_18], rcx
0x18000ec2a  test    rcx, rcx
0x18000ec2d  jz      short loc_18000EC33
0x18000ec2f  lock inc dword ptr [rcx-8]
0x18000ec33  lea     rdx, [rbp+var_20]
0x18000ec37  lea     rcx, [rbp+var_18]
0x18000ec3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec40  test    al, al
0x18000ec42  jz      short loc_18000EC55
0x18000ec44  lea     rdx, [rbp+arg_0]
0x18000ec48  lea     rcx, [rbp+var_28]
0x18000ec4c  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x18000ec51  mov     rdi, [rbp+var_28]
0x18000ec55  cmp     r15d, 1
0x18000ec59  jz      loc_18000ECEC
0x18000ec5f  mov     rcx, [r14+20h]
0x18000ec63  mov     [rbp+arg_18], 0
0x18000ec6b  mov     rax, [rcx]
0x18000ec6e  mov     rax, [rax+48h]
0x18000ec72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec77  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18000ec7b  mov     rcx, rax; this
0x18000ec7e  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000ec83  test    eax, eax
0x18000ec85  js      loc_18000ED40
0x18000ec8b  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000ec8f  lea     rcx, [rbp+arg_0]; this
0x18000ec93  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000ec98  test    eax, eax
0x18000ec9a  js      loc_18000ED40
0x18000eca0  test    r12b, r12b
0x18000eca3  jnz     short loc_18000ECDB
0x18000eca5  mov     rax, [rbp+arg_0]
0x18000eca9  mov     r8, [r14+10h]
0x18000ecad  mov     [rbp+var_20], rax
0x18000ecb1  test    rax, rax
0x18000ecb4  jz      short loc_18000ECBA
0x18000ecb6  lock inc dword ptr [rax-8]
0x18000ecba  mov     [rbp+var_10], rbx
0x18000ecbe  test    rbx, rbx
0x18000ecc1  jz      short loc_18000ECC7
0x18000ecc3  lock inc dword ptr [rbx-8]
0x18000ecc7  lea     rdx, [rbp+var_20]
0x18000eccb  mov     rax, r8
0x18000ecce  lea     rcx, [rbp+var_10]
0x18000ecd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd7  test    al, al
0x18000ecd9  jz      short loc_18000ECEC
0x18000ecdb  lea     rdx, [rbp+arg_0]
0x18000ecdf  lea     rcx, [rbp+var_30]
0x18000ece3  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x18000ece8  mov     rbx, [rbp+var_30]
0x18000ecec  mov     rax, [r14+10h]
0x18000ecf0  mov     [rbp+var_20], rbx
0x18000ecf4  test    rbx, rbx
0x18000ecf7  jz      short loc_18000ECFD
0x18000ecf9  lock inc dword ptr [rbx-8]
0x18000ecfd  mov     [rbp+var_8], rdi
0x18000ed01  test    rdi, rdi
0x18000ed04  jz      short loc_18000ED0A
0x18000ed06  lock inc dword ptr [rdi-8]
0x18000ed0a  lea     rdx, [rbp+var_20]
0x18000ed0e  lea     rcx, [rbp+var_8]
0x18000ed12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed17  test    al, al
0x18000ed19  jnz     short loc_18000ED44
0x18000ed1b  mov     rcx, [r14+18h]
0x18000ed1f  xor     r12b, r12b
0x18000ed22  mov     rax, [rcx]
0x18000ed25  mov     rax, [rax+30h]
0x18000ed29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed2e  mov     rcx, [r14+20h]
0x18000ed32  mov     esi, eax
0x18000ed34  mov     rax, [rcx]
0x18000ed37  mov     rax, [rax+30h]
0x18000ed3b  jmp     loc_18000EB84
0x18000ed40  mov     esi, eax
0x18000ed42  jmp     short loc_18000ED6B
0x18000ed44  mov     byte ptr [r13+0], 1
0x18000ed49  lea     rcx, [rbp+var_30]; this
0x18000ed4d  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ed52  lea     rcx, [rbp+var_28]; this
0x18000ed56  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ed5b  lea     rcx, [rbp+arg_0]; this
0x18000ed5f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ed64  xor     eax, eax
0x18000ed66  jmp     short loc_18000ED88
0x18000ed68  mov     esi, r15d
0x18000ed6b  lea     rcx, [rbp+var_30]; this
0x18000ed6f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ed74  lea     rcx, [rbp+var_28]; this
0x18000ed78  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ed7d  lea     rcx, [rbp+arg_0]; this
0x18000ed81  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000ed86  mov     eax, esi
0x18000ed88  mov     rbx, [rsp+50h+arg_8]
0x18000ed90  add     rsp, 50h
0x18000ed94  pop     r15
0x18000ed96  pop     r14
0x18000ed98  pop     r13
0x18000ed9a  pop     r12
0x18000ed9c  pop     rdi
0x18000ed9d  pop     rsi
0x18000ed9e  pop     rbp
0x18000ed9f  retn
```
