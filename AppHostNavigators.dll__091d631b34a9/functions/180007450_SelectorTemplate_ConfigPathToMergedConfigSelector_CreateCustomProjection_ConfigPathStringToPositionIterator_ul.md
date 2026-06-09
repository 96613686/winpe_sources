# SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateCustomProjection<ConfigPathStringToPositionIterator>(ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x180007450`
- end: `0x1800074fc`
- name: `??$CreateCustomProjection@VConfigPathStringToPositionIterator@@@?$SelectorTemplate@VConfigPathToMergedConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x180007450`
- `0x18000764c`
- `0x180007d88`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateCustomProjection<ConfigPathStringToPositionIterator>(
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
  *(_QWORD *)v6 = &ConfigPathStringToPositionIterator::`vftable';
  *((_QWORD *)v6 + 4) = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v10 = v6;
  if ( !v6 )
    goto LABEL_8;
  Instance = ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance((__int64)v6, a3);
  if ( Instance >= 0 )
    Instance = 0;
LABEL_9:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007450  mov     [rsp+arg_0], rbx
0x180007455  mov     [rsp+arg_8], rsi
0x18000745a  push    rdi
0x18000745b  sub     rsp, 30h
0x18000745f  mov     rsi, r8
0x180007462  mov     rdi, rdx
0x180007465  mov     [rsp+38h+arg_18], 0
0x18000746e  mov     ecx, 28h ; '('; Size
0x180007473  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007478  mov     rbx, rax
0x18000747b  mov     [rsp+38h+var_18], rax
0x180007480  test    rax, rax
0x180007483  jz      short loc_1800074D2
0x180007485  mov     rdi, [rdi]
0x180007488  mov     rcx, rax; this
0x18000748b  call    ??0SingletonIteratorBase@@QEAA@XZ; SingletonIteratorBase::SingletonIteratorBase(void)
0x180007490  lea     rax, ??_7ConfigPathStringToPositionIterator@@6B@; const ConfigPathStringToPositionIterator::`vftable'
0x180007497  mov     [rbx], rax
0x18000749a  mov     [rbx+20h], rdi
0x18000749e  test    rdi, rdi
0x1800074a1  jz      short loc_1800074B3
0x1800074a3  mov     rax, [rdi]
0x1800074a6  mov     rcx, rdi
0x1800074a9  mov     rax, [rax+8]
0x1800074ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b2  nop
0x1800074b3  mov     [rsp+38h+arg_18], rbx
0x1800074b8  test    rbx, rbx
0x1800074bb  jz      short loc_1800074DB
0x1800074bd  mov     rdx, rsi
0x1800074c0  mov     rcx, rbx
0x1800074c3  call    ?CreateInstance@?$ProjectionIterator@VConfigPathToMergedConfigSelector@@@@SAJPEAUIXPathNodeIterator@@PEAPEAUIUnknown@@@Z; ProjectionIterator<ConfigPathToMergedConfigSelector>::CreateInstance(IXPathNodeIterator *,IUnknown * *)
0x1800074c8  mov     ebx, eax
0x1800074ca  test    eax, eax
0x1800074cc  js      short loc_1800074E0
0x1800074ce  xor     ebx, ebx
0x1800074d0  jmp     short loc_1800074E0
0x1800074d2  mov     [rsp+38h+arg_18], 0
0x1800074db  mov     ebx, 8007000Eh
0x1800074e0  lea     rcx, [rsp+38h+arg_18]
0x1800074e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800074ea  mov     eax, ebx
0x1800074ec  mov     rbx, [rsp+38h+arg_0]
0x1800074f1  mov     rsi, [rsp+38h+arg_8]
0x1800074f6  add     rsp, 30h
0x1800074fa  pop     rdi
0x1800074fb  retn
```
