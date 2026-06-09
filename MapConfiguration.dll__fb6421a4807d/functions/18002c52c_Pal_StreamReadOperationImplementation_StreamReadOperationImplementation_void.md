# Pal::StreamReadOperationImplementation::~StreamReadOperationImplementation(void)

- ea: `0x18002c52c`
- end: `0x18002c5c4`
- name: `??1StreamReadOperationImplementation@Pal@@UEAA@XZ`
- size: `152`
- prototype: `void __fastcall(Pal::StreamReadOperationImplementation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002ad80`

## callees

- `0x180010cf8`
- `0x180013da8`
- `0x18001c490`
- `0x18002c52c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c582`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c582`

## pseudocode

```c
void __fastcall Pal::StreamReadOperationImplementation::~StreamReadOperationImplementation(
        Pal::StreamReadOperationImplementation *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx

  *(_QWORD *)this = &Pal::StreamReadOperationImplementation::`vftable';
  Pal::UntypedAsyncOperation::cancel(this);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 49);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 47);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 45);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v6 = *((_QWORD *)this + 38);
  if ( v6 )
  {
    LOBYTE(v5) = v6 != (_QWORD)this + 248;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v5);
    *((_QWORD *)this + 38) = 0;
  }
  Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::~AsyncOperation<std::shared_ptr<Pal::Stream>>(this);
}

```

## disassembly

```asm
0x18002c52c  mov     [rsp+arg_0], rbx
0x18002c531  push    rdi
0x18002c532  sub     rsp, 20h
0x18002c536  mov     rbx, rcx
0x18002c539  lea     rax, ??_7StreamReadOperationImplementation@Pal@@6B@; const Pal::StreamReadOperationImplementation::`vftable'
0x18002c540  mov     [rcx], rax
0x18002c543  call    ?cancel@UntypedAsyncOperation@Pal@@UEAA_NXZ; Pal::UntypedAsyncOperation::cancel(void)
0x18002c548  mov     rcx, [rbx+188h]; this
0x18002c54f  test    rcx, rcx
0x18002c552  jz      short loc_18002C559
0x18002c554  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c559  mov     rcx, [rbx+178h]; this
0x18002c560  test    rcx, rcx
0x18002c563  jz      short loc_18002C56A
0x18002c565  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c56a  mov     rcx, [rbx+168h]; this
0x18002c571  test    rcx, rcx
0x18002c574  jz      short loc_18002C57B
0x18002c576  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c57b  lea     rcx, [rbx+138h]; lpCriticalSection
0x18002c582  call    cs:__imp_DeleteCriticalSection
0x18002c588  lea     rdi, [rbx+0F8h]
0x18002c58f  mov     rcx, [rdi+38h]
0x18002c593  test    rcx, rcx
0x18002c596  jz      short loc_18002C5B2
0x18002c598  mov     rax, [rcx]
0x18002c59b  cmp     rcx, rdi
0x18002c59e  setnz   dl
0x18002c5a1  mov     rax, [rax+20h]
0x18002c5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5aa  mov     qword ptr [rdi+38h], 0
0x18002c5b2  mov     rcx, rbx; this
0x18002c5b5  mov     rbx, [rsp+28h+arg_0]
0x18002c5ba  add     rsp, 20h
0x18002c5be  pop     rdi
0x18002c5bf  jmp     ??1?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@UEAA@XZ; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::~AsyncOperation<std::shared_ptr<Pal::Stream>>(void)
```
