# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800030a4`
- end: `0x180003149`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003280`
- `0x180019f20`

## callees

- `0x1800030a4`
- `0x1800069fc`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800030ee`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800030ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003125`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003125`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, int a2, unsigned int a3)
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
        JUMPOUT(0x180003148LL);
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
0x1800030a4  push    rbx
0x1800030a6  push    rsi
0x1800030a7  push    rdi
0x1800030a8  push    r14
0x1800030aa  push    r15
0x1800030ac  sub     rsp, 20h
0x1800030b0  mov     rdi, rcx
0x1800030b3  lea     r14, [rcx+8]
0x1800030b7  cmp     dword ptr [r14], 0
0x1800030bb  jz      short loc_180003132
0x1800030bd  cmp     qword ptr [rcx+10h], 0
0x1800030c2  jz      short loc_18000310C
0x1800030c4  mov     rax, rcx
0x1800030c7  neg     rax
0x1800030ca  sbb     rsi, rsi
0x1800030cd  and     rsi, r14
0x1800030d0  jz      short loc_18000313E
0x1800030d2  mov     r15, [rsi+8]
0x1800030d6  test    r15, r15
0x1800030d9  jz      short loc_1800030FC
0x1800030db  mov     rcx, [r15+8]
0x1800030df  mov     rax, [r15]
0x1800030e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e7  mov     rbx, [r15+10h]
0x1800030eb  mov     rcx, r15
0x1800030ee  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800030f4  mov     r15, rbx
0x1800030f7  test    rbx, rbx
0x1800030fa  jnz     short loc_1800030DB
0x1800030fc  mov     qword ptr [rsi+8], 0
0x180003104  mov     qword ptr [rdi+10h], 0
0x18000310c  mov     rcx, [rdi+40h]
0x180003110  test    rcx, rcx
0x180003113  jz      short loc_180003121
0x180003115  mov     rax, [rcx]
0x180003118  mov     rax, [rax+10h]
0x18000311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003121  lea     rcx, [rdi+18h]; lpCriticalSection
0x180003125  call    cs:__imp_DeleteCriticalSection
0x18000312b  mov     dword ptr [r14], 0
0x180003132  add     rsp, 20h
0x180003136  pop     r15
0x180003138  pop     r14
0x18000313a  pop     rdi
0x18000313b  pop     rsi
0x18000313c  pop     rbx
0x18000313d  retn
0x18000313e  mov     ecx, 0C0000005h; this
0x180003143  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
