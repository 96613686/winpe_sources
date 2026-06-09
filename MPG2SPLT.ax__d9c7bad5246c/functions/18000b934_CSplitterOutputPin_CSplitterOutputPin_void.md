# CSplitterOutputPin::~CSplitterOutputPin(void)

- ea: `0x18000b934`
- end: `0x18000b9e3`
- name: `??1CSplitterOutputPin@@UEAA@XZ`
- size: `175`
- prototype: `void __fastcall(CSplitterOutputPin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000bb00`

## callees

- `0x180001048`
- `0x1800030c8`
- `0x18000676c`
- `0x180006860`
- `0x180006b18`
- `0x18000b934`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b9c6`
- `KERNEL32!DeleteCriticalSection` at `0x18000b9c6`

## pseudocode

```c
void __fastcall CSplitterOutputPin::~CSplitterOutputPin(CSplitterOutputPin *this)
{
  bool v1; // zf
  CBaseList *v3; // rdi
  struct _AMMediaType *v4; // rax
  struct _AMMediaType *v5; // rsi

  v1 = *((_DWORD *)this + 80) == 0;
  *(_QWORD *)this = &CSplitterOutputPin::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CSplitterOutputPin::`vftable'{for `IPin'};
  *((_QWORD *)this + 4) = &CSplitterOutputPin::`vftable'{for `IQualityControl'};
  if ( v1 )
  {
    v3 = (CSplitterOutputPin *)((char *)this + 304);
  }
  else
  {
    do
    {
      v3 = (CSplitterOutputPin *)((char *)this + 304);
      v4 = (struct _AMMediaType *)CBaseList::RemoveI(
                                    (CSplitterOutputPin *)((char *)this + 304),
                                    *((struct __POSITION **)this + 38));
      v5 = v4;
      if ( v4 )
      {
        FreeMediaType(v4);
        operator delete(v5, 0x58u);
      }
    }
    while ( *((_DWORD *)this + 80) );
  }
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  CBaseList::~CBaseList(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  CBasePin::~CBasePin(this);
}

```

## disassembly

```asm
0x18000b934  mov     [rsp+arg_0], rbx
0x18000b939  mov     [rsp+arg_8], rsi
0x18000b93e  push    rdi
0x18000b93f  sub     rsp, 20h
0x18000b943  cmp     dword ptr [rcx+140h], 0
0x18000b94a  lea     rax, ??_7CSplitterOutputPin@@6BCUnknown@@@; const CSplitterOutputPin::`vftable'{for `CUnknown'}
0x18000b951  mov     [rcx], rax
0x18000b954  mov     rbx, rcx
0x18000b957  lea     rax, ??_7CSplitterOutputPin@@6BIPin@@@; const CSplitterOutputPin::`vftable'{for `IPin'}
0x18000b95e  mov     [rcx+18h], rax
0x18000b962  lea     rax, ??_7CSplitterOutputPin@@6BIQualityControl@@@; const CSplitterOutputPin::`vftable'{for `IQualityControl'}
0x18000b969  mov     [rcx+20h], rax
0x18000b96d  jz      short loc_18000B9A9
0x18000b96f  lea     rdi, [rbx+130h]
0x18000b976  mov     rdx, [rdi]; struct __POSITION *
0x18000b979  mov     rcx, rdi; this
0x18000b97c  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000b981  mov     rsi, rax
0x18000b984  test    rax, rax
0x18000b987  jz      short loc_18000B99E
0x18000b989  mov     rcx, rax; struct _AMMediaType *
0x18000b98c  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000b991  mov     edx, 58h ; 'X'; unsigned __int64
0x18000b996  mov     rcx, rsi; void *
0x18000b999  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b99e  cmp     dword ptr [rbx+140h], 0
0x18000b9a5  jnz     short loc_18000B96F
0x18000b9a7  jmp     short loc_18000B9B0
0x18000b9a9  lea     rdi, [rcx+130h]
0x18000b9b0  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000b9b7  mov     rcx, rdi; this
0x18000b9ba  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000b9bf  lea     rcx, [rbx+100h]; lpCriticalSection
0x18000b9c6  call    cs:__imp_DeleteCriticalSection
0x18000b9cc  mov     rcx, rbx; this
0x18000b9cf  mov     rbx, [rsp+28h+arg_0]
0x18000b9d4  mov     rsi, [rsp+28h+arg_8]
0x18000b9d9  add     rsp, 20h
0x18000b9dd  pop     rdi
0x18000b9de  jmp     ??1CBasePin@@UEAA@XZ; CBasePin::~CBasePin(void)
```
