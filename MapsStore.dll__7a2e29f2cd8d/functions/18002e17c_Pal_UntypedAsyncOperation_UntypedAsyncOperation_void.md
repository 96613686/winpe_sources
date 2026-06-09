# Pal::UntypedAsyncOperation::~UntypedAsyncOperation(void)

- ea: `0x18002e17c`
- end: `0x18002e1c9`
- name: `??1UntypedAsyncOperation@Pal@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(Pal::UntypedAsyncOperation *__hidden this)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x1800254e8`
- `0x180025520`
- `0x18002556c`
- `0x18002e220`
- `0x180031b54`
- `0x180043f94`
- `0x180049828`
- `0x180049e74`
- `0x180050b18`
- `0x1800581a4`
- `0x18005c130`
- `0x180068a4c`
- `0x18006c048`
- `0x180074e40`
- `0x180093e86`

## callees

- `0x180016cbc`
- `0x18001ba18`
- `0x18002e17c`
- `0x18002f774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e1a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e1a5`

## pseudocode

```c
void __fastcall Pal::UntypedAsyncOperation::~UntypedAsyncOperation(Pal::UntypedAsyncOperation *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &Pal::UntypedAsyncOperation::`vftable';
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy((char *)this + 80);
  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>((char *)this + 72);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *(_QWORD *)this = &Pal::AsyncInfo::`vftable';
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
}

```

## disassembly

```asm
0x18002e17c  push    rbx
0x18002e17e  sub     rsp, 20h
0x18002e182  lea     rax, ??_7UntypedAsyncOperation@Pal@@6B@; const Pal::UntypedAsyncOperation::`vftable'
0x18002e189  mov     rbx, rcx
0x18002e18c  mov     [rcx], rax
0x18002e18f  add     rcx, 50h ; 'P'
0x18002e193  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x18002e198  lea     rcx, [rbx+48h]
0x18002e19c  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x18002e1a1  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002e1a5  call    cs:__imp_DeleteCriticalSection
0x18002e1ab  lea     rax, ??_7AsyncInfo@Pal@@6B@; const Pal::AsyncInfo::`vftable'
0x18002e1b2  mov     [rbx], rax
0x18002e1b5  mov     rcx, [rbx+10h]; this
0x18002e1b9  test    rcx, rcx
0x18002e1bc  jz      short loc_18002E1C3
0x18002e1be  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002e1c3  add     rsp, 20h
0x18002e1c7  pop     rbx
0x18002e1c8  retn
```
