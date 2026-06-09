# ATL::CAtlModule::Term(void)

- ea: `0x140004614`
- end: `0x1400046b8`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400027d0`

## callees

- `0x140001a00`
- `0x140004614`
- `0x1400047bc`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004694`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004694`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x1400046B7LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x140004614  push    rbx
0x140004616  push    rsi
0x140004617  push    rdi
0x140004618  push    r14
0x14000461a  push    r15
0x14000461c  sub     rsp, 20h
0x140004620  mov     rdi, rcx
0x140004623  lea     r14, [rcx+8]
0x140004627  cmp     dword ptr [r14], 0
0x14000462b  jz      short loc_1400046A1
0x14000462d  cmp     qword ptr [rcx+10h], 0
0x140004632  jz      short loc_14000467B
0x140004634  mov     rax, rcx
0x140004637  neg     rax
0x14000463a  sbb     rsi, rsi
0x14000463d  and     rsi, r14
0x140004640  jz      short loc_1400046AD
0x140004642  mov     r15, [rsi+8]
0x140004646  test    r15, r15
0x140004649  jz      short loc_14000466B
0x14000464b  mov     rcx, [r15+8]
0x14000464f  mov     rax, [r15]
0x140004652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004657  mov     rbx, [r15+10h]
0x14000465b  mov     rcx, r15; Block
0x14000465e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004663  mov     r15, rbx
0x140004666  test    rbx, rbx
0x140004669  jnz     short loc_14000464B
0x14000466b  mov     qword ptr [rsi+8], 0
0x140004673  mov     qword ptr [rdi+10h], 0
0x14000467b  mov     rcx, [rdi+40h]
0x14000467f  test    rcx, rcx
0x140004682  jz      short loc_140004690
0x140004684  mov     rax, [rcx]
0x140004687  mov     rax, [rax+10h]
0x14000468b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004690  lea     rcx, [rdi+18h]; lpCriticalSection
0x140004694  call    cs:__imp_DeleteCriticalSection
0x14000469a  mov     dword ptr [r14], 0
0x1400046a1  add     rsp, 20h
0x1400046a5  pop     r15
0x1400046a7  pop     r14
0x1400046a9  pop     rdi
0x1400046aa  pop     rsi
0x1400046ab  pop     rbx
0x1400046ac  retn
0x1400046ad  mov     ecx, 0C0000005h; unsigned int
0x1400046b2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
