# ATL::CAtlModule::Term(void)

- ea: `0x1800172f8`
- end: `0x1800173a1`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800126a0`
- `0x1800126f0`
- `0x18001718c`
- `0x180034290`

## callees

- `0x180001900`
- `0x180006e00`
- `0x1800172f8`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001737d`
- `KERNEL32!DeleteCriticalSection` at `0x18001737d`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, int a2, unsigned int a3)
{
  unsigned __int64 v4; // r14
  __int64 v5; // rsi
  _QWORD *v6; // r15
  _QWORD *v7; // rbx
  __int64 v8; // rcx

  v4 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v5 = v4 & -(__int64)(this != 0);
      if ( !v5 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC0000005LL, a2, a3);
        JUMPOUT(0x1800173A0LL);
      }
      v6 = *(_QWORD **)((v4 & -(__int64)(this != 0)) + 8);
      if ( v6 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v6)(v6[1]);
          v7 = (_QWORD *)v6[2];
          operator delete(v6);
          v6 = v7;
        }
        while ( v7 );
      }
      *(_QWORD *)(v5 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v8 = *((_QWORD *)this + 8);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v4 = 0;
  }
}

```

## disassembly

```asm
0x1800172f8  push    rbx
0x1800172fa  push    rsi
0x1800172fb  push    rdi
0x1800172fc  push    r14
0x1800172fe  push    r15
0x180017300  sub     rsp, 20h
0x180017304  mov     rdi, rcx
0x180017307  lea     r14, [rcx+8]
0x18001730b  cmp     dword ptr [r14], 0
0x18001730f  jz      short loc_18001738A
0x180017311  cmp     qword ptr [rcx+10h], 0
0x180017316  jz      short loc_180017364
0x180017318  mov     rax, rcx
0x18001731b  neg     rax
0x18001731e  sbb     rsi, rsi
0x180017321  and     rsi, r14
0x180017324  jz      short loc_180017396
0x180017326  mov     r15, [rsi+8]
0x18001732a  test    r15, r15
0x18001732d  jz      short loc_180017354
0x18001732f  mov     rcx, [r15+8]
0x180017333  mov     rax, [r15]
0x180017336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001733b  mov     rbx, [r15+10h]
0x18001733f  mov     edx, 18h
0x180017344  mov     rcx, r15; Block
0x180017347  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001734c  mov     r15, rbx
0x18001734f  test    rbx, rbx
0x180017352  jnz     short loc_18001732F
0x180017354  mov     qword ptr [rsi+8], 0
0x18001735c  mov     qword ptr [rdi+10h], 0
0x180017364  mov     rcx, [rdi+40h]
0x180017368  test    rcx, rcx
0x18001736b  jz      short loc_180017379
0x18001736d  mov     rax, [rcx]
0x180017370  mov     rax, [rax+10h]
0x180017374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017379  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001737d  call    cs:__imp_DeleteCriticalSection
0x180017383  mov     dword ptr [r14], 0
0x18001738a  add     rsp, 20h
0x18001738e  pop     r15
0x180017390  pop     r14
0x180017392  pop     rdi
0x180017393  pop     rsi
0x180017394  pop     rbx
0x180017395  retn
0x180017396  mov     ecx, 0C0000005h; this
0x18001739b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
