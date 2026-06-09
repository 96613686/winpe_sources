# SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateCustomProjection<FileConfigPathStringToPositionIterator>(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007510`
- end: `0x1800075bc`
- name: `??$CreateCustomProjection@VFileConfigPathStringToPositionIterator@@@?$SelectorTemplate@VConfigLocationToRawConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x180007510`
- `0x18000764c`
- `0x180007c58`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateCustomProjection<FileConfigPathStringToPositionIterator>(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3)
{
  SingletonIteratorBase *v5; // rax
  SingletonIteratorBase *v6; // rbx
  __int64 v7; // rdi
  int Instance; // ebx
  SingletonIteratorBase *v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v5 = (SingletonIteratorBase *)operator new(0x28u);
  v6 = v5;
  if ( !v5 )
  {
    v10 = 0;
LABEL_8:
    Instance = -2147024882;
    goto LABEL_9;
  }
  v7 = *a2;
  SingletonIteratorBase::SingletonIteratorBase(v5);
  *(_QWORD *)v6 = &FileConfigPathStringToPositionIterator::`vftable';
  *((_QWORD *)v6 + 4) = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v10 = v6;
  if ( !v6 )
    goto LABEL_8;
  Instance = ProjectionIterator<ConfigLocationToRawConfigSelector>::CreateInstance((__int64)v6, a3);
  if ( Instance >= 0 )
    Instance = 0;
LABEL_9:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007510  mov     [rsp+arg_0], rbx
0x180007515  mov     [rsp+arg_8], rsi
0x18000751a  push    rdi
0x18000751b  sub     rsp, 30h
0x18000751f  mov     rsi, r8
0x180007522  mov     rdi, rdx
0x180007525  mov     [rsp+38h+arg_18], 0
0x18000752e  mov     ecx, 28h ; '('; Size
0x180007533  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007538  mov     rbx, rax
0x18000753b  mov     [rsp+38h+var_18], rax
0x180007540  test    rax, rax
0x180007543  jz      short loc_180007592
0x180007545  mov     rdi, [rdi]
0x180007548  mov     rcx, rax; this
0x18000754b  call    ??0SingletonIteratorBase@@QEAA@XZ; SingletonIteratorBase::SingletonIteratorBase(void)
0x180007550  lea     rax, ??_7FileConfigPathStringToPositionIterator@@6B@; const FileConfigPathStringToPositionIterator::`vftable'
0x180007557  mov     [rbx], rax
0x18000755a  mov     [rbx+20h], rdi
0x18000755e  test    rdi, rdi
0x180007561  jz      short loc_180007573
0x180007563  mov     rax, [rdi]
0x180007566  mov     rcx, rdi
0x180007569  mov     rax, [rax+8]
0x18000756d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007572  nop
0x180007573  mov     [rsp+38h+arg_18], rbx
0x180007578  test    rbx, rbx
0x18000757b  jz      short loc_18000759B
0x18000757d  mov     rdx, rsi
0x180007580  mov     rcx, rbx
0x180007583  call    ?CreateInstance@?$ProjectionIterator@VConfigLocationToRawConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigLocationToRawConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x180007588  mov     ebx, eax
0x18000758a  test    eax, eax
0x18000758c  js      short loc_1800075A0
0x18000758e  xor     ebx, ebx
0x180007590  jmp     short loc_1800075A0
0x180007592  mov     [rsp+38h+arg_18], 0
0x18000759b  mov     ebx, 8007000Eh
0x1800075a0  lea     rcx, [rsp+38h+arg_18]
0x1800075a5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800075aa  mov     eax, ebx
0x1800075ac  mov     rbx, [rsp+38h+arg_0]
0x1800075b1  mov     rsi, [rsp+38h+arg_8]
0x1800075b6  add     rsp, 30h
0x1800075ba  pop     rdi
0x1800075bb  retn
```
