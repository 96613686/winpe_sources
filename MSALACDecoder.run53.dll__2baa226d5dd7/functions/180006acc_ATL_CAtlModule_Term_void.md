# ATL::CAtlModule::Term(void)

- ea: `0x180006acc`
- end: `0x180006b75`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004200`
- `0x180007420`
- `0x18000a230`

## callees

- `0x180001574`
- `0x180006acc`
- `0x18000725c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006b51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006b51`

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
        JUMPOUT(0x180006B74LL);
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
0x180006acc  push    rbx
0x180006ace  push    rsi
0x180006acf  push    rdi
0x180006ad0  push    r14
0x180006ad2  push    r15
0x180006ad4  sub     rsp, 20h
0x180006ad8  mov     rdi, rcx
0x180006adb  lea     r14, [rcx+8]
0x180006adf  cmp     dword ptr [r14], 0
0x180006ae3  jz      short loc_180006B5E
0x180006ae5  cmp     qword ptr [rcx+10h], 0
0x180006aea  jz      short loc_180006B38
0x180006aec  mov     rax, rcx
0x180006aef  neg     rax
0x180006af2  sbb     rsi, rsi
0x180006af5  and     rsi, r14
0x180006af8  jz      short loc_180006B6A
0x180006afa  mov     r15, [rsi+8]
0x180006afe  test    r15, r15
0x180006b01  jz      short loc_180006B28
0x180006b03  mov     rcx, [r15+8]
0x180006b07  mov     rax, [r15]
0x180006b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0f  mov     rbx, [r15+10h]
0x180006b13  mov     edx, 18h
0x180006b18  mov     rcx, r15; Block
0x180006b1b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006b20  mov     r15, rbx
0x180006b23  test    rbx, rbx
0x180006b26  jnz     short loc_180006B03
0x180006b28  mov     qword ptr [rsi+8], 0
0x180006b30  mov     qword ptr [rdi+10h], 0
0x180006b38  mov     rcx, [rdi+40h]
0x180006b3c  test    rcx, rcx
0x180006b3f  jz      short loc_180006B4D
0x180006b41  mov     rax, [rcx]
0x180006b44  mov     rax, [rax+10h]
0x180006b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006b51  call    cs:__imp_DeleteCriticalSection
0x180006b57  mov     dword ptr [r14], 0
0x180006b5e  add     rsp, 20h
0x180006b62  pop     r15
0x180006b64  pop     r14
0x180006b66  pop     rdi
0x180006b67  pop     rsi
0x180006b68  pop     rbx
0x180006b69  retn
0x180006b6a  mov     ecx, 0C0000005h; unsigned int
0x180006b6f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
