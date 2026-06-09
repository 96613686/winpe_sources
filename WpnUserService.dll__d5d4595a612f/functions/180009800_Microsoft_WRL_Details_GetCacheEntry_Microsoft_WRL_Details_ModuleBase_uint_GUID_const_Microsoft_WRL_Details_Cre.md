# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009800`
- end: `0x180009986`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d260`

## callees

- `0x180009800`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009937`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009937`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800098ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800098ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009850`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009850`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009891`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800098a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009891`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800098a6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009862`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009917`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009862`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009917`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009908`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009908`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v9; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rbx

  v9 = Ptr;
  *Ptr = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v9);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      return v12;
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, _QWORD **))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v14);
    v15 = **(void ***)a4[1].Data4;
    if ( v15 )
    {
      v16 = DecodePointer(v15);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
    }
    else
    {
      v16 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    if ( !v16 )
    {
LABEL_17:
      v16 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    *v9 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009800  mov     rax, rsp
0x180009803  push    rbx
0x180009804  push    rbp
0x180009805  push    rsi
0x180009806  push    rdi
0x180009807  push    r14
0x180009809  push    r15
0x18000980b  sub     rsp, 38h
0x18000980f  mov     rdi, r9
0x180009812  mov     r15, r8
0x180009815  mov     rbp, rdx
0x180009818  mov     rsi, rcx
0x18000981b  mov     r14, [rsp+68h+Ptr]
0x180009823  mov     qword ptr [r14], 0
0x18000982a  mov     qword ptr [rax+28h], 0
0x180009832  mov     rax, [r9+18h]
0x180009836  mov     r10, [rax]
0x180009839  test    r10, r10
0x18000983c  jz      short loc_1800098AC
0x18000983e  mov     rax, [rcx]
0x180009841  mov     rax, [rax+38h]
0x180009845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984a  mov     rbx, rax
0x18000984d  mov     rcx, rax; SRWLock
0x180009850  call    cs:__imp_AcquireSRWLockShared
0x180009856  mov     rcx, [rdi+18h]
0x18000985a  mov     rcx, [rcx]; Ptr
0x18000985d  test    rcx, rcx
0x180009860  jz      short loc_18000989E
0x180009862  call    cs:__imp_DecodePointer
0x180009868  mov     r9, rax
0x18000986b  mov     [rsp+68h+Ptr], rax
0x180009873  mov     rcx, [rax]
0x180009876  mov     rax, [rcx]
0x180009879  mov     r8, r14
0x18000987c  mov     rdx, r15
0x18000987f  mov     rcx, r9
0x180009882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009887  mov     edi, eax
0x180009889  test    rbx, rbx
0x18000988c  jz      short loc_180009897
0x18000988e  mov     rcx, rbx; SRWLock
0x180009891  call    cs:__imp_ReleaseSRWLockShared
0x180009897  mov     eax, edi
0x180009899  jmp     loc_180009979
0x18000989e  test    rbx, rbx
0x1800098a1  jz      short loc_1800098AC
0x1800098a3  mov     rcx, rbx; SRWLock
0x1800098a6  call    cs:__imp_ReleaseSRWLockShared
0x1800098ac  lea     r9, [rsp+68h+Ptr]
0x1800098b4  mov     r8, r15
0x1800098b7  mov     rdx, rdi
0x1800098ba  mov     rcx, rbp
0x1800098bd  mov     rax, [rdi]
0x1800098c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c5  test    eax, eax
0x1800098c7  js      loc_180009979
0x1800098cd  test    byte ptr [rbp+0], 4
0x1800098d1  jnz     loc_18000996C
0x1800098d7  mov     rax, [rsi]
0x1800098da  mov     rcx, rsi
0x1800098dd  mov     rax, [rax+38h]
0x1800098e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e6  mov     rsi, rax
0x1800098e9  mov     rcx, rax; SRWLock
0x1800098ec  call    cs:__imp_AcquireSRWLockExclusive
0x1800098f2  mov     rcx, [rdi+18h]
0x1800098f6  mov     rcx, [rcx]; Ptr
0x1800098f9  test    rcx, rcx
0x1800098fc  jnz     short loc_180009917
0x1800098fe  xor     ebx, ebx
0x180009900  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180009908  call    cs:__imp_EncodePointer
0x18000990e  mov     rcx, [rdi+18h]
0x180009912  mov     [rcx], rax
0x180009915  jmp     short loc_18000992F
0x180009917  call    cs:__imp_DecodePointer
0x18000991d  mov     rbx, rax
0x180009920  mov     rcx, [rax]
0x180009923  mov     rax, [rcx+8]
0x180009927  mov     rcx, rbx
0x18000992a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000992f  test    rsi, rsi
0x180009932  jz      short loc_18000993D
0x180009934  mov     rcx, rsi; SRWLock
0x180009937  call    cs:__imp_ReleaseSRWLockExclusive
0x18000993d  test    rbx, rbx
0x180009940  jz      short loc_18000996C
0x180009942  mov     rcx, [rsp+68h+Ptr]
0x18000994a  mov     rax, [rcx]
0x18000994d  mov     rax, [rax+10h]
0x180009951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009956  mov     rcx, [rsp+68h+Ptr]
0x18000995e  mov     rax, [rcx]
0x180009961  mov     rax, [rax+10h]
0x180009965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996a  jmp     short loc_180009974
0x18000996c  mov     rbx, [rsp+68h+Ptr]
0x180009974  mov     [r14], rbx
0x180009977  xor     eax, eax
0x180009979  add     rsp, 38h
0x18000997d  pop     r15
0x18000997f  pop     r14
0x180009981  pop     rdi
0x180009982  pop     rsi
0x180009983  pop     rbp
0x180009984  pop     rbx
0x180009985  retn
```
