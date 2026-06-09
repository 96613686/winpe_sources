# CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ClassFactoryRecord,std::allocator<ClassFactoryRecord>>,ClassFactoryRecord>(CommonUtil::CStdVector<ClassFactoryRecord,std::allocator<ClassFactoryRecord>> &,ClassFactoryRecord const &)

- ea: `0x140003ed8`
- end: `0x140003f0f`
- name: `??$HrStdPushBack@V?$CStdVector@UClassFactoryRecord@@V?$allocator@UClassFactoryRecord@@@std@@@CommonUtil@@UClassFactoryRecord@@@CommonUtil@@YAJAEAV?$CStdVector@UClassFactoryRecord@@V?$allocator@UClassFactoryRecord@@@std@@@0@AEBUClassFactoryRecord@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400043d0`

## callees

- `0x140003ed8`
- `0x140003f18`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ClassFactoryRecord,std::allocator<ClassFactoryRecord>>,ClassFactoryRecord>(
        __int64 a1,
        _OWORD *a2)
{
  _OWORD *v3; // rdx
  CommonUtil *v4; // rcx
  __int64 v6; // [rsp+0h] [rbp-38h] BYREF
  const std::exception *v7; // [rsp+20h] [rbp-18h] BYREF

  v3 = *(_OWORD **)(a1 + 8);
  if ( v3 == *(_OWORD **)(a1 + 16) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      std::vector<ClassFactoryRecord>::_Emplace_reallocate<ClassFactoryRecord const &>();
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v7) )
        CommonUtil::HrFromStdException(v4, (const struct std::exception *)&v6);
    }
  }
  else
  {
    *v3 = *a2;
    *(_QWORD *)(a1 + 8) += 16LL;
  }
  return 0;
}

```

## disassembly

```asm
0x140003ed8  sub     rsp, 38h
0x140003edc  mov     r8, rdx
0x140003edf  mov     rdx, [rcx+8]
0x140003ee3  cmp     rdx, [rcx+10h]
0x140003ee7  jz      short loc_140003EF8
0x140003ee9  movups  xmm0, xmmword ptr [r8]
0x140003eed  movdqu  xmmword ptr [rdx], xmm0
0x140003ef1  add     qword ptr [rcx+8], 10h
0x140003ef6  jmp     short loc_140003EFE
0x140003ef8  call    ??$_Emplace_reallocate@AEBUClassFactoryRecord@@@?$vector@UClassFactoryRecord@@V?$allocator@UClassFactoryRecord@@@std@@@std@@AEAAPEAUClassFactoryRecord@@QEAU2@AEBU2@@Z; std::vector<ClassFactoryRecord>::_Emplace_reallocate<ClassFactoryRecord const &>(ClassFactoryRecord * const,ClassFactoryRecord const &)
0x140003efd  nop
0x140003efe  jmp     short loc_140003F08
0x140003f00  mov     eax, [rsp+38h+arg_0]
0x140003f04  test    eax, eax
0x140003f06  js      short loc_140003F0A
0x140003f08  xor     eax, eax
0x140003f0a  add     rsp, 38h
0x140003f0e  retn
```
