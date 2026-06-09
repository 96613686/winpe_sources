# CPersistStreamInit::~CPersistStreamInit(void)

- ea: `0x18001a9f4`
- end: `0x18001aa8e`
- name: `??1CPersistStreamInit@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(CPersistStreamInit *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013948`

## callees

- `0x18000266c`
- `0x18001a9f4`
- `0x180020880`
- `0x180030010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18001aa87`

## pseudocode

```c
void __fastcall CPersistStreamInit::~CPersistStreamInit(CPersistStreamInit *this)
{
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CPersistStreamInit::`vftable';
  v2 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
  if ( v2 )
  {
    if ( *((_QWORD *)this + 7) )
    {
      v3 = 0;
      if ( (**v2)(v2, &IID_IChapteredRowset, &v3) >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, *((_QWORD *)this + 7), 0);
      *((_QWORD *)this + 7) = 0;
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v3);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
  }
  ReleaseDataConvert(*((struct IDataConvert **)this + 5));
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x18001a9f4  push    rbx
0x18001a9f6  sub     rsp, 20h
0x18001a9fa  mov     rbx, rcx
0x18001a9fd  lea     rax, ??_7CPersistStreamInit@@6B@; const CPersistStreamInit::`vftable'
0x18001aa04  mov     [rcx], rax
0x18001aa07  mov     rcx, [rcx+20h]
0x18001aa0b  test    rcx, rcx
0x18001aa0e  jz      short loc_18001AA75
0x18001aa10  cmp     qword ptr [rbx+38h], 0
0x18001aa15  jz      short loc_18001AA65
0x18001aa17  mov     [rsp+28h+arg_0], 0
0x18001aa20  mov     rax, [rcx]
0x18001aa23  lea     r8, [rsp+28h+arg_0]
0x18001aa28  lea     rdx, IID_IChapteredRowset
0x18001aa2f  mov     rax, [rax]
0x18001aa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa37  test    eax, eax
0x18001aa39  js      short loc_18001AA53
0x18001aa3b  mov     rcx, [rsp+28h+arg_0]
0x18001aa40  mov     rax, [rcx]
0x18001aa43  xor     r8d, r8d
0x18001aa46  mov     rdx, [rbx+38h]
0x18001aa4a  mov     rax, [rax+20h]
0x18001aa4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa53  mov     qword ptr [rbx+38h], 0
0x18001aa5b  lea     rcx, [rsp+28h+arg_0]
0x18001aa60  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001aa65  mov     rcx, [rbx+20h]
0x18001aa69  mov     rax, [rcx]
0x18001aa6c  mov     rax, [rax+10h]
0x18001aa70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa75  mov     rcx, [rbx+28h]; struct IDataConvert *
0x18001aa79  call    ?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z; ReleaseDataConvert(IDataConvert *)
0x18001aa7e  lea     rcx, [rbx+10h]
0x18001aa82  add     rsp, 20h
0x18001aa86  pop     rbx
0x18001aa87  jmp     cs:__imp_MPDeleteCriticalSection
```
