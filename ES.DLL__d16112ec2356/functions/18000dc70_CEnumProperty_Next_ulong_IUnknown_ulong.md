# CEnumProperty::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18000dc70`
- end: `0x18000deeb`
- name: `?Next@CEnumProperty@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `635`
- prototype: `int(CEnumProperty *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d66c`
- `0x18000dc70`
- `0x18000def4`
- `0x18000e050`
- `0x18000e1f0`
- `0x180026634`
- `0x1800434c6`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ddeb`

## pseudocode

```c
__int64 __fastcall CEnumProperty::Next(CEnumProperty *this, unsigned int a2, struct IUnknown **a3, unsigned int *a4)
{
  int v8; // r14d
  __int64 i; // rbx
  unsigned int v10; // edx
  CEventProperty *v11; // rax
  unsigned int v12; // edx
  volatile signed __int32 *v13; // r8
  struct IUnknown *v14; // rcx
  void *v15; // rcx
  RefCountedVariant *v16; // rcx
  void *v17; // rcx
  __int64 j; // rbx
  struct IUnknown *v19; // rcx
  RefCountedVariant *v21; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v22[8]; // [rsp+38h] [rbp-40h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  if ( !a2 )
    return 1;
  v8 = 0;
  memset_0(a3, 0, 8LL * a2);
  UTSemReadWriteES::LockRead((UTSemReadWriteES *)(*((_QWORD *)this + 2) + 48LL));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a2 )
      goto LABEL_22;
    v22[0] = &dword_180053104;
    v21 = 0;
    if ( !(unsigned __int8)CEnumProperty::AdvanceCursor(this, v22, &v21) )
    {
      v8 = 1;
      v16 = v21;
      if ( v21 && !_InterlockedDecrement((volatile signed __int32 *)v21 + 6) && v16 )
        RefCountedVariant::`scalar deleting destructor'(v16, v10);
      v21 = 0;
      v17 = (void *)(v22[0] - 12LL);
      if ( (__int64 *)(v22[0] - 12LL) != &qword_1800530F8 )
        goto LABEL_20;
      goto LABEL_22;
    }
    v11 = (CEventProperty *)CoTaskMemAlloc(0x28u);
    v13 = (volatile signed __int32 *)v21;
    v14 = v11 ? (struct IUnknown *)CEventProperty::CEventProperty(v11, (struct CString *)v22, v21) : 0LL;
    a3[i] = v14;
    if ( !v14 )
      break;
    if ( v13 && !_InterlockedDecrement(v13 + 6) )
      RefCountedVariant::`scalar deleting destructor'((RefCountedVariant *)v13, v12);
    v21 = 0;
    v15 = (void *)(v22[0] - 12LL);
    if ( (__int64 *)(v22[0] - 12LL) != &qword_1800530F8 && !_InterlockedDecrement((volatile signed __int32 *)v15) )
      CoTaskMemFree(v15);
  }
  v8 = -2147024882;
  if ( v13 && !_InterlockedDecrement(v13 + 6) )
    RefCountedVariant::`scalar deleting destructor'((RefCountedVariant *)v13, v12);
  v21 = 0;
  v17 = (void *)(v22[0] - 12LL);
  if ( (__int64 *)(v22[0] - 12LL) != &qword_1800530F8 )
  {
LABEL_20:
    if ( !_InterlockedDecrement((volatile signed __int32 *)v17) )
      CoTaskMemFree(v17);
  }
LABEL_22:
  UTSemReadWriteES::UnlockRead((UTSemReadWriteES *)(*((_QWORD *)this + 2) + 48LL));
  if ( v8 < 0 )
  {
    for ( j = 0; (unsigned int)j < a2; j = (unsigned int)(j + 1) )
    {
      v19 = a3[j];
      if ( !v19 )
        break;
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
      a3[j] = 0;
    }
    *a4 = 0;
  }
  else
  {
    *a4 = i;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000dc70  push    rbx
0x18000dc72  push    rsi
0x18000dc73  push    rdi
0x18000dc74  push    r12
0x18000dc76  push    r14
0x18000dc78  push    r15
0x18000dc7a  sub     rsp, 48h
0x18000dc7e  mov     r12, r9
0x18000dc81  mov     r15, r8
0x18000dc84  mov     esi, edx
0x18000dc86  mov     rdi, rcx
0x18000dc89  test    r8, r8
0x18000dc8c  jz      loc_18000DEDD
0x18000dc92  test    r9, r9
0x18000dc95  jz      loc_18000DEDD
0x18000dc9b  test    edx, edx
0x18000dc9d  jz      loc_18000DEE4
0x18000dca3  xor     r14d, r14d
0x18000dca6  test    edx, edx
0x18000dca8  jz      short loc_18000DCBC
0x18000dcaa  mov     r8d, esi
0x18000dcad  shl     r8, 3; Size
0x18000dcb1  xor     edx, edx; Val
0x18000dcb3  mov     rcx, r15; void *
0x18000dcb6  call    memset_0
0x18000dcbb  nop
0x18000dcbc  mov     rcx, [rdi+10h]
0x18000dcc0  add     rcx, 30h ; '0'; this
0x18000dcc4  call    ?LockRead@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::LockRead(void)
0x18000dcc9  mov     [rsp+78h+var_54], 0
0x18000dcd1  xor     ebx, ebx
0x18000dcd3  mov     [rsp+78h+var_54], ebx
0x18000dcd7  cmp     ebx, esi
0x18000dcd9  jnb     loc_18000DDF1
0x18000dcdf  lea     rax, dword_180053104
0x18000dce6  mov     [rsp+78h+var_40], rax
0x18000dceb  mov     [rsp+78h+var_48], 0
0x18000dcf4  lea     r8, [rsp+78h+var_48]
0x18000dcf9  lea     rdx, [rsp+78h+var_40]
0x18000dcfe  mov     rcx, rdi
0x18000dd01  call    ?AdvanceCursor@CEnumProperty@@AEAA_NPEAVCString@@PEAV?$RefCountedPointer@URefCountedVariant@@@@@Z; CEnumProperty::AdvanceCursor(CString *,RefCountedPointer<RefCountedVariant> *)
0x18000dd06  test    al, al
0x18000dd08  jz      loc_18000DD99
0x18000dd0e  mov     ecx, 28h ; '('; cb
0x18000dd13  call    cs:__imp_CoTaskMemAlloc
0x18000dd19  mov     r8, [rsp+78h+var_48]; struct RefCountedVariant *
0x18000dd1e  test    rax, rax
0x18000dd21  jz      loc_18000DE5A
0x18000dd27  lea     rdx, [rsp+78h+var_40]; struct CString *
0x18000dd2c  mov     rcx, rax; this
0x18000dd2f  call    ??0CEventProperty@@QEAA@AEAVCString@@PEAURefCountedVariant@@@Z; CEventProperty::CEventProperty(CString &,RefCountedVariant *)
0x18000dd34  mov     rcx, rax
0x18000dd37  mov     [r15+rbx*8], rcx
0x18000dd3b  test    rcx, rcx
0x18000dd3e  jz      loc_18000DE10
0x18000dd44  test    r8, r8
0x18000dd47  jz      short loc_18000DD62
0x18000dd49  or      eax, 0FFFFFFFFh
0x18000dd4c  lock xadd [r8+18h], eax
0x18000dd52  sub     eax, 1
0x18000dd55  mov     [rsp+78h+arg_10], eax
0x18000dd5c  jz      loc_18000DE74
0x18000dd62  mov     [rsp+78h+var_48], 0
0x18000dd6b  mov     rcx, [rsp+78h+var_40]
0x18000dd70  add     rcx, 0FFFFFFFFFFFFFFF4h; pv
0x18000dd74  lea     rax, qword_1800530F8
0x18000dd7b  cmp     rcx, rax
0x18000dd7e  jz      short loc_18000DD92
0x18000dd80  or      eax, 0FFFFFFFFh
0x18000dd83  lock xadd [rcx], eax
0x18000dd87  sub     eax, 1
0x18000dd8a  jnz     short loc_18000DD92
0x18000dd8c  call    cs:__imp_CoTaskMemFree
0x18000dd92  inc     ebx
0x18000dd94  jmp     loc_18000DCD3
0x18000dd99  mov     r14d, 1
0x18000dd9f  mov     rcx, [rsp+78h+var_48]; this
0x18000dda4  test    rcx, rcx
0x18000dda7  jz      short loc_18000DDC1
0x18000dda9  or      eax, 0FFFFFFFFh
0x18000ddac  lock xadd [rcx+18h], eax
0x18000ddb1  sub     eax, r14d
0x18000ddb4  mov     [rsp+78h+arg_10], eax
0x18000ddbb  jz      loc_18000DE61
0x18000ddc1  mov     [rsp+78h+var_48], 0
0x18000ddca  mov     rcx, [rsp+78h+var_40]
0x18000ddcf  add     rcx, 0FFFFFFFFFFFFFFF4h; pv
0x18000ddd3  lea     rax, qword_1800530F8
0x18000ddda  cmp     rcx, rax
0x18000dddd  jz      short loc_18000DDF1
0x18000dddf  or      eax, 0FFFFFFFFh
0x18000dde2  lock xadd [rcx], eax
0x18000dde6  sub     eax, r14d
0x18000dde9  jnz     short loc_18000DDF1
0x18000ddeb  call    cs:__imp_CoTaskMemFree
0x18000ddf1  mov     rcx, [rdi+10h]
0x18000ddf5  add     rcx, 30h ; '0'; this
0x18000ddf9  call    ?UnlockRead@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockRead(void)
0x18000ddfe  test    r14d, r14d
0x18000de01  js      loc_18000DE99
0x18000de07  mov     [r12], ebx
0x18000de0b  jmp     loc_18000DECC
0x18000de10  mov     r14d, 8007000Eh
0x18000de16  test    r8, r8
0x18000de19  jz      short loc_18000DE30
0x18000de1b  or      eax, 0FFFFFFFFh
0x18000de1e  lock xadd [r8+18h], eax
0x18000de24  sub     eax, 1
0x18000de27  mov     [rsp+78h+arg_10], eax
0x18000de2e  jz      short loc_18000DE8A
0x18000de30  mov     [rsp+78h+var_48], 0
0x18000de39  mov     rcx, [rsp+78h+var_40]
0x18000de3e  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18000de42  lea     rax, qword_1800530F8
0x18000de49  cmp     rcx, rax
0x18000de4c  jz      short loc_18000DDF1
0x18000de4e  or      eax, 0FFFFFFFFh
0x18000de51  lock xadd [rcx], eax
0x18000de55  sub     eax, 1
0x18000de58  jmp     short loc_18000DDE9
0x18000de5a  xor     ecx, ecx
0x18000de5c  jmp     loc_18000DD37
0x18000de61  test    rcx, rcx
0x18000de64  jz      loc_18000DDC1
0x18000de6a  call    ??_GRefCountedVariant@@AEAAPEAXI@Z; RefCountedVariant::`scalar deleting destructor'(uint)
0x18000de6f  jmp     loc_18000DDC1
0x18000de74  test    r8, r8
0x18000de77  jz      loc_18000DD62
0x18000de7d  mov     rcx, r8; this
0x18000de80  call    ??_GRefCountedVariant@@AEAAPEAXI@Z; RefCountedVariant::`scalar deleting destructor'(uint)
0x18000de85  jmp     loc_18000DD62
0x18000de8a  test    r8, r8
0x18000de8d  jz      short loc_18000DE30
0x18000de8f  mov     rcx, r8; this
0x18000de92  call    ??_GRefCountedVariant@@AEAAPEAXI@Z; RefCountedVariant::`scalar deleting destructor'(uint)
0x18000de97  jmp     short loc_18000DE30
0x18000de99  xor     ebx, ebx
0x18000de9b  mov     [rsp+78h+var_50], ebx
0x18000de9f  cmp     ebx, esi
0x18000dea1  jnb     short loc_18000DEC4
0x18000dea3  mov     rcx, [r15+rbx*8]
0x18000dea7  test    rcx, rcx
0x18000deaa  jz      short loc_18000DEC4
0x18000deac  mov     rax, [rcx]
0x18000deaf  mov     rax, [rax+10h]
0x18000deb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deb8  mov     qword ptr [r15+rbx*8], 0
0x18000dec0  inc     ebx
0x18000dec2  jmp     short loc_18000DE9B
0x18000dec4  mov     dword ptr [r12], 0
0x18000decc  mov     eax, r14d
0x18000decf  add     rsp, 48h
0x18000ded3  pop     r15
0x18000ded5  pop     r14
0x18000ded7  pop     r12
0x18000ded9  pop     rdi
0x18000deda  pop     rsi
0x18000dedb  pop     rbx
0x18000dedc  retn
0x18000dedd  mov     eax, 80004003h
0x18000dee2  jmp     short loc_18000DECF
0x18000dee4  mov     eax, 1
0x18000dee9  jmp     short loc_18000DECF
0x180043aba  push    rbp
0x180043abc  sub     rsp, 20h
0x180043ac0  mov     rbp, rdx
0x180043ac3  add     rsp, 20h
0x180043ac7  pop     rbp
0x180043ac8  retn
```
