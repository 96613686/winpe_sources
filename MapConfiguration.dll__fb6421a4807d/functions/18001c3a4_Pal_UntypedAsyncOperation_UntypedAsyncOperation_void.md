# Pal::UntypedAsyncOperation::~UntypedAsyncOperation(void)

- ea: `0x18001c3a4`
- end: `0x18001c3f1`
- name: `??1UntypedAsyncOperation@Pal@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(Pal::UntypedAsyncOperation *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180010cc0`
- `0x180010cf8`
- `0x180010d44`
- `0x18001c450`
- `0x18002a444`

## callees

- `0x180013de0`
- `0x180014cd8`
- `0x18001bb2c`
- `0x18001c3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c3cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c3cd`

## pseudocode

```c
void __fastcall Pal::UntypedAsyncOperation::~UntypedAsyncOperation(Pal::UntypedAsyncOperation *this)
{
  std::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &Pal::UntypedAsyncOperation::`vftable';
  std::_Func_class<void,>::_Tidy((char *)this + 80);
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
0x18001c3a4  push    rbx
0x18001c3a6  sub     rsp, 20h
0x18001c3aa  lea     rax, ??_7UntypedAsyncOperation@Pal@@6B@; const Pal::UntypedAsyncOperation::`vftable'
0x18001c3b1  mov     rbx, rcx
0x18001c3b4  mov     [rcx], rax
0x18001c3b7  add     rcx, 50h ; 'P'
0x18001c3bb  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001c3c0  lea     rcx, [rbx+48h]
0x18001c3c4  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x18001c3c9  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001c3cd  call    cs:__imp_DeleteCriticalSection
0x18001c3d3  lea     rax, ??_7AsyncInfo@Pal@@6B@; const Pal::AsyncInfo::`vftable'
0x18001c3da  mov     [rbx], rax
0x18001c3dd  mov     rcx, [rbx+10h]; this
0x18001c3e1  test    rcx, rcx
0x18001c3e4  jz      short loc_18001C3EB
0x18001c3e6  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001c3eb  add     rsp, 20h
0x18001c3ef  pop     rbx
0x18001c3f0  retn
```
