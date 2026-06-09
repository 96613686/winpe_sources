# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180012a64`
- end: `0x180012b08`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012b10`
- `0x180013ae0`

## callees

- `0x180001520`
- `0x18000bcbc`
- `0x180012a64`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012ae4`
- `KERNEL32!DeleteCriticalSection` at `0x180012ae4`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180012B07LL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180012a64  push    rbx
0x180012a66  push    rsi
0x180012a67  push    rdi
0x180012a68  push    r14
0x180012a6a  push    r15
0x180012a6c  sub     rsp, 20h
0x180012a70  lea     r14, [rcx+8]
0x180012a74  mov     rdi, rcx
0x180012a77  cmp     dword ptr [r14], 0
0x180012a7b  jz      short loc_180012AF1
0x180012a7d  cmp     qword ptr [rcx+10h], 0
0x180012a82  jz      short loc_180012ACB
0x180012a84  mov     rax, rcx
0x180012a87  neg     rax
0x180012a8a  sbb     rsi, rsi
0x180012a8d  and     rsi, r14
0x180012a90  jz      short loc_180012AFD
0x180012a92  mov     r15, [rsi+8]
0x180012a96  test    r15, r15
0x180012a99  jz      short loc_180012ABB
0x180012a9b  mov     rcx, [r15+8]
0x180012a9f  mov     rax, [r15]
0x180012aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aa7  mov     rbx, [r15+10h]
0x180012aab  mov     rcx, r15; Block
0x180012aae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012ab3  mov     r15, rbx
0x180012ab6  test    rbx, rbx
0x180012ab9  jnz     short loc_180012A9B
0x180012abb  mov     qword ptr [rsi+8], 0
0x180012ac3  mov     qword ptr [rdi+10h], 0
0x180012acb  mov     rcx, [rdi+40h]
0x180012acf  test    rcx, rcx
0x180012ad2  jz      short loc_180012AE0
0x180012ad4  mov     rax, [rcx]
0x180012ad7  mov     rax, [rax+10h]
0x180012adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ae0  lea     rcx, [rdi+18h]; lpCriticalSection
0x180012ae4  call    cs:__imp_DeleteCriticalSection
0x180012aea  mov     dword ptr [r14], 0
0x180012af1  add     rsp, 20h
0x180012af5  pop     r15
0x180012af7  pop     r14
0x180012af9  pop     rdi
0x180012afa  pop     rsi
0x180012afb  pop     rbx
0x180012afc  retn
0x180012afd  mov     ecx, 0C0000005h; unsigned int
0x180012b02  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
