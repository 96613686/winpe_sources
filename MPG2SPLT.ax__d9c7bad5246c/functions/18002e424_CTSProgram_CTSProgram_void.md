# CTSProgram::~CTSProgram(void)

- ea: `0x18002e424`
- end: `0x18002e50f`
- name: `??1CTSProgram@@QEAA@XZ`
- size: `235`
- prototype: `void __fastcall(CTSProgram *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002ecc0`
- `0x18002f394`
- `0x18002fea4`
- `0x1800306f8`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18002e424`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e499`
- `KERNEL32!DeleteCriticalSection` at `0x18002e4d3`
- `KERNEL32!DeleteCriticalSection` at `0x18002e499`
- `KERNEL32!DeleteCriticalSection` at `0x18002e4d3`

## pseudocode

```c
void __fastcall CTSProgram::~CTSProgram(CTSProgram *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  volatile signed __int32 *v3; // rdi
  __int64 **v4; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rax
  __int64 **v8; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rdx
  __int64 *v11; // rax

  *(_QWORD *)this = &CTSProgram::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( _InterlockedExchangeAdd(v3 + 10, 0xFFFFFFFF) == 1 && v3 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v3);
    operator delete((void *)v3, 0x2530u);
  }
  *((_QWORD *)this + 66) = &TGenericMap<unsigned __int64,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 912));
  v4 = (__int64 **)((char *)this + 536);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == (__int64 *)v4 )
      break;
    v6 = *v5;
    v7 = (__int64 *)v5[1];
    *v7 = *v5;
    *(_QWORD *)(v6 + 8) = v7;
    operator delete(v5, 0x1A8u);
  }
  *((_QWORD *)this + 13) = &TGenericMap<unsigned __int64,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v8 = (__int64 **)((char *)this + 112);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == (__int64 *)v8 )
      break;
    v10 = *v9;
    v11 = (__int64 *)v9[1];
    *v11 = *v9;
    *(_QWORD *)(v10 + 8) = v11;
    operator delete(v9, 0x1A8u);
  }
}

```

## disassembly

```asm
0x18002e424  mov     [rsp+arg_8], rbx
0x18002e429  mov     [rsp+arg_10], rsi
0x18002e42e  push    rdi
0x18002e42f  sub     rsp, 20h
0x18002e433  lea     rax, ??_7CTSProgram@@6B@; const CTSProgram::`vftable'
0x18002e43a  mov     rbx, rcx
0x18002e43d  mov     [rcx], rax
0x18002e440  mov     rcx, [rcx+10h]
0x18002e444  test    rcx, rcx
0x18002e447  jz      short loc_18002E459
0x18002e449  mov     rax, [rcx]
0x18002e44c  mov     edx, 1
0x18002e451  mov     rax, [rax]
0x18002e454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e459  mov     rdi, [rbx+8]
0x18002e45d  or      eax, 0FFFFFFFFh
0x18002e460  lock xadd [rdi+28h], eax
0x18002e465  cmp     eax, 1
0x18002e468  jnz     short loc_18002E484
0x18002e46a  test    rdi, rdi
0x18002e46d  jz      short loc_18002E484
0x18002e46f  mov     rcx, rdi; this
0x18002e472  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002e477  mov     edx, 2530h; unsigned __int64
0x18002e47c  mov     rcx, rdi; void *
0x18002e47f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e484  lea     rsi, ??_7?$TGenericMap@_KK$0A@$04$0BD@@@6B@; const TGenericMap<unsigned __int64,ulong,0,5,19>::`vftable'
0x18002e48b  lea     rcx, [rbx+390h]; lpCriticalSection
0x18002e492  mov     [rbx+210h], rsi
0x18002e499  call    cs:__imp_DeleteCriticalSection
0x18002e49f  lea     rdi, [rbx+218h]
0x18002e4a6  mov     rcx, [rdi]; void *
0x18002e4a9  cmp     rcx, rdi
0x18002e4ac  jz      short loc_18002E4C8
0x18002e4ae  mov     rdx, [rcx]
0x18002e4b1  mov     rax, [rcx+8]
0x18002e4b5  mov     [rax], rdx
0x18002e4b8  mov     [rdx+8], rax
0x18002e4bc  mov     edx, 1A8h; unsigned __int64
0x18002e4c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e4c6  jmp     short loc_18002E4A6
0x18002e4c8  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x18002e4cf  mov     [rbx+68h], rsi
0x18002e4d3  call    cs:__imp_DeleteCriticalSection
0x18002e4d9  add     rbx, 70h ; 'p'
0x18002e4dd  mov     rcx, [rbx]; void *
0x18002e4e0  cmp     rcx, rbx
0x18002e4e3  jz      short loc_18002E4FF
0x18002e4e5  mov     rdx, [rcx]
0x18002e4e8  mov     rax, [rcx+8]
0x18002e4ec  mov     [rax], rdx
0x18002e4ef  mov     [rdx+8], rax
0x18002e4f3  mov     edx, 1A8h; unsigned __int64
0x18002e4f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e4fd  jmp     short loc_18002E4DD
0x18002e4ff  mov     rbx, [rsp+28h+arg_8]
0x18002e504  mov     rsi, [rsp+28h+arg_10]
0x18002e509  add     rsp, 20h
0x18002e50d  pop     rdi
0x18002e50e  retn
```
