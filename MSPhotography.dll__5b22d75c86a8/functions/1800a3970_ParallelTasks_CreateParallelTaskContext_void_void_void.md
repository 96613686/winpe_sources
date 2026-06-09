# ParallelTasks::CreateParallelTaskContext(void (*)(void *),void *)

- ea: `0x1800a3970`
- end: `0x1800a3a8d`
- name: `?CreateParallelTaskContext@ParallelTasks@@AEAA?AV?$shared_ptr@VParallelTaskContext@@@std@@P6AXPEAX@Z0@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800a3c58`

## callees

- `0x18000290c`
- `0x180002da0`
- `0x180003094`
- `0x1800a3818`
- `0x1800a3970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800a39c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800a39c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall ParallelTasks::CreateParallelTaskContext(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  HANDLE Event; // rax
  _DWORD *v10; // rax
  _QWORD *pExceptionObject; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v13; // [rsp+58h] [rbp+10h]

  v13 = a2;
  pExceptionObject = a1;
  v7 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    *v7 = a3;
    v7[1] = a4;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v8[2] = Event;
    if ( !Event )
    {
      LODWORD(pExceptionObject) = 4;
      throw (ErrorCode *)&pExceptionObject;
    }
    *((_DWORD *)v8 + 6) = 0;
  }
  else
  {
    v8 = 0;
  }
  *a2 = 0;
  a2[1] = 0;
  pExceptionObject = v8;
  v10 = operator new(0x18u);
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count<ParallelTaskContext>::`vftable';
  *((_QWORD *)v10 + 2) = v8;
  *a2 = v8;
  a2[1] = v10;
  pExceptionObject = 0;
  std::_Temporary_owner<ParallelTaskContext>::~_Temporary_owner<ParallelTaskContext>(&pExceptionObject);
  if ( !*a2 )
  {
    LODWORD(pExceptionObject) = 2;
    throw (ErrorCode *)&pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x1800a3970  mov     rax, rsp
0x1800a3973  mov     [rax+18h], rbx
0x1800a3977  mov     [rax+10h], rdx
0x1800a397b  mov     [rax+8], rcx
0x1800a397f  push    rbp
0x1800a3980  push    rsi
0x1800a3981  push    rdi
0x1800a3982  sub     rsp, 30h
0x1800a3986  mov     rsi, r9
0x1800a3989  mov     rbp, r8
0x1800a398c  mov     rdi, rdx
0x1800a398f  mov     dword ptr [rax-28h], 0
0x1800a3996  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a399d  mov     ecx, 20h ; ' '; unsigned __int64
0x1800a39a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a39a7  mov     rbx, rax
0x1800a39aa  mov     [rsp+48h+var_20], rax
0x1800a39af  test    rax, rax
0x1800a39b2  jz      short loc_1800A39FA
0x1800a39b4  mov     [rax], rbp
0x1800a39b7  mov     [rax+8], rsi
0x1800a39bb  mov     r9d, 1F0003h; dwDesiredAccess
0x1800a39c1  xor     r8d, r8d; dwFlags
0x1800a39c4  xor     edx, edx; lpName
0x1800a39c6  xor     ecx, ecx; lpEventAttributes
0x1800a39c8  call    cs:__imp_CreateEventExW
0x1800a39ce  mov     [rbx+10h], rax
0x1800a39d2  test    rax, rax
0x1800a39d5  jnz     short loc_1800A39F1
0x1800a39d7  mov     dword ptr [rsp+48h+pExceptionObject], 4
0x1800a39df  lea     rdx, _TI1?AW4ErrorCode@@; pThrowInfo
0x1800a39e6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800a39eb  call    _CxxThrowException_0
0x1800a39f1  mov     dword ptr [rbx+18h], 0
0x1800a39f8  jmp     short loc_1800A39FC
0x1800a39fa  xor     ebx, ebx
0x1800a39fc  mov     qword ptr [rdi], 0
0x1800a3a03  mov     qword ptr [rdi+8], 0
0x1800a3a0b  mov     [rsp+48h+pExceptionObject], rbx
0x1800a3a10  mov     ecx, 18h; Size
0x1800a3a15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a3a1a  mov     [rsp+48h+pExceptionObject], rax
0x1800a3a1f  xorps   xmm0, xmm0
0x1800a3a22  movups  xmmword ptr [rax], xmm0
0x1800a3a25  mov     esi, 1
0x1800a3a2a  mov     [rax+8], esi
0x1800a3a2d  mov     [rax+0Ch], esi
0x1800a3a30  lea     rcx, ??_7?$_Ref_count@VParallelTaskContext@@@std@@6B@; const std::_Ref_count<ParallelTaskContext>::`vftable'
0x1800a3a37  mov     [rax], rcx
0x1800a3a3a  mov     [rax+10h], rbx
0x1800a3a3e  mov     [rdi], rbx
0x1800a3a41  mov     [rdi+8], rax
0x1800a3a45  mov     [rsp+48h+pExceptionObject], 0
0x1800a3a4e  lea     rcx, [rsp+48h+pExceptionObject]
0x1800a3a53  call    ??1?$_Temporary_owner@VParallelTaskContext@@@std@@QEAA@XZ; std::_Temporary_owner<ParallelTaskContext>::~_Temporary_owner<ParallelTaskContext>(void)
0x1800a3a58  mov     [rsp+48h+var_28], esi
0x1800a3a5c  cmp     qword ptr [rdi], 0
0x1800a3a60  jnz     short loc_1800A3A7C
0x1800a3a62  mov     dword ptr [rsp+48h+pExceptionObject], 2
0x1800a3a6a  lea     rdx, _TI1?AW4ErrorCode@@; pThrowInfo
0x1800a3a71  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800a3a76  call    _CxxThrowException_0
0x1800a3a7c  mov     rax, rdi
0x1800a3a7f  mov     rbx, [rsp+48h+arg_10]
0x1800a3a84  add     rsp, 30h
0x1800a3a88  pop     rdi
0x1800a3a89  pop     rsi
0x1800a3a8a  pop     rbp
0x1800a3a8b  retn
```
