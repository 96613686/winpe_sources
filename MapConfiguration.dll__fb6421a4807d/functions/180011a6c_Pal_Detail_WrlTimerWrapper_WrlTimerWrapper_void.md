# Pal::Detail::WrlTimerWrapper::~WrlTimerWrapper(void)

- ea: `0x180011a6c`
- end: `0x180011ab4`
- name: `??1WrlTimerWrapper@Detail@Pal@@UEAA@XZ`
- size: `72`
- prototype: `void __fastcall(Pal::Detail::WrlTimerWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012bb0`

## callees

- `0x18000b4b8`
- `0x180011a6c`
- `0x180013de0`
- `0x180014cd8`
- `0x18001bb2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011a9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011a9a`

## pseudocode

```c
void __fastcall Pal::Detail::WrlTimerWrapper::~WrlTimerWrapper(Pal::Detail::WrlTimerWrapper *this)
{
  std::_Ref_count_base *v2; // rcx

  std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>((char *)this + 144);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 128);
  std::_Func_class<void,>::_Tidy((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
}

```

## disassembly

```asm
0x180011a6c  push    rbx
0x180011a6e  sub     rsp, 20h
0x180011a72  mov     rbx, rcx
0x180011a75  add     rcx, 90h
0x180011a7c  call    ??1?$unique_ptr@VManualResetEventImplWindows@Pal@@U?$default_delete@VManualResetEventImplWindows@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::ManualResetEventImplWindows>::~unique_ptr<Pal::ManualResetEventImplWindows>(void)
0x180011a81  lea     rcx, [rbx+80h]
0x180011a88  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011a8d  lea     rcx, [rbx+40h]
0x180011a91  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011a96  lea     rcx, [rbx+18h]; lpCriticalSection
0x180011a9a  call    cs:__imp_DeleteCriticalSection
0x180011aa0  mov     rcx, [rbx+10h]; this
0x180011aa4  test    rcx, rcx
0x180011aa7  jz      short loc_180011AAE
0x180011aa9  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011aae  add     rsp, 20h
0x180011ab2  pop     rbx
0x180011ab3  retn
```
