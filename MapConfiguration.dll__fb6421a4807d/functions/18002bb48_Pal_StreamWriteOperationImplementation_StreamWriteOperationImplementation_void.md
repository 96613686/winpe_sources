# Pal::StreamWriteOperationImplementation::~StreamWriteOperationImplementation(void)

- ea: `0x18002bb48`
- end: `0x18002bbcf`
- name: `??1StreamWriteOperationImplementation@Pal@@UEAA@XZ`
- size: `135`
- prototype: `void __fastcall(Pal::StreamWriteOperationImplementation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002adc0`

## callees

- `0x180010d44`
- `0x180013da8`
- `0x18001c490`
- `0x18002bb48`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bb8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002bb8d`

## pseudocode

```c
void __fastcall Pal::StreamWriteOperationImplementation::~StreamWriteOperationImplementation(
        Pal::StreamWriteOperationImplementation *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx

  *(_QWORD *)this = &Pal::StreamWriteOperationImplementation::`vftable';
  Pal::UntypedAsyncOperation::cancel(this);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 46);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 44);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  v5 = *((_QWORD *)this + 37);
  if ( v5 )
  {
    LOBYTE(v4) = v5 != (_QWORD)this + 240;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, v4);
    *((_QWORD *)this + 37) = 0;
  }
  Pal::AsyncOperation<unsigned __int64>::~AsyncOperation<unsigned __int64>(this);
}

```

## disassembly

```asm
0x18002bb48  mov     [rsp+arg_0], rbx
0x18002bb4d  push    rdi
0x18002bb4e  sub     rsp, 20h
0x18002bb52  mov     rbx, rcx
0x18002bb55  lea     rax, ??_7StreamWriteOperationImplementation@Pal@@6B@; const Pal::StreamWriteOperationImplementation::`vftable'
0x18002bb5c  mov     [rcx], rax
0x18002bb5f  call    ?cancel@UntypedAsyncOperation@Pal@@UEAA_NXZ; Pal::UntypedAsyncOperation::cancel(void)
0x18002bb64  mov     rcx, [rbx+170h]; this
0x18002bb6b  test    rcx, rcx
0x18002bb6e  jz      short loc_18002BB75
0x18002bb70  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bb75  mov     rcx, [rbx+160h]; this
0x18002bb7c  test    rcx, rcx
0x18002bb7f  jz      short loc_18002BB86
0x18002bb81  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002bb86  lea     rcx, [rbx+130h]; lpCriticalSection
0x18002bb8d  call    cs:__imp_DeleteCriticalSection
0x18002bb93  lea     rdi, [rbx+0F0h]
0x18002bb9a  mov     rcx, [rdi+38h]
0x18002bb9e  test    rcx, rcx
0x18002bba1  jz      short loc_18002BBBD
0x18002bba3  mov     rax, [rcx]
0x18002bba6  cmp     rcx, rdi
0x18002bba9  setnz   dl
0x18002bbac  mov     rax, [rax+20h]
0x18002bbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbb5  mov     qword ptr [rdi+38h], 0
0x18002bbbd  mov     rcx, rbx; this
0x18002bbc0  mov     rbx, [rsp+28h+arg_0]
0x18002bbc5  add     rsp, 20h
0x18002bbc9  pop     rdi
0x18002bbca  jmp     ??1?$AsyncOperation@_K@Pal@@UEAA@XZ; Pal::AsyncOperation<unsigned __int64>::~AsyncOperation<unsigned __int64>(void)
```
