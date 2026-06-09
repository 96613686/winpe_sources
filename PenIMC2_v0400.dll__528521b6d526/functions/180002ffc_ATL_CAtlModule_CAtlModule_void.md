# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180002ffc`
- end: `0x180003088`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `140`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001390`
- `0x1800018f8`
- `0x180001a94`
- `0x18000e4de`
- `0x18000e502`
- `0x18000f2b0`

## callees

- `0x180002ffc`
- `0x18000ce0c`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000306e`
- `KERNEL32!DeleteCriticalSection` at `0x18000306e`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rbx
  __int64 v4; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v2 = (_QWORD *)*((_QWORD *)this + 2);
      if ( v2 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v2)(v2[1]);
          v3 = (_QWORD *)v2[2];
          operator delete(v2);
          v2 = v3;
        }
        while ( v3 );
      }
      *((_QWORD *)this + 2) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v4 = *((_QWORD *)this + 8);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180002ffc  mov     [rsp+arg_0], rbx
0x180003001  mov     [rsp+arg_8], rsi
0x180003006  push    rdi
0x180003007  sub     rsp, 20h
0x18000300b  cmp     dword ptr [rcx+8], 0
0x18000300f  mov     rdi, rcx
0x180003012  jz      short loc_180003078
0x180003014  cmp     qword ptr [rcx+10h], 0
0x180003019  jz      short loc_180003054
0x18000301b  mov     rsi, [rcx+10h]
0x18000301f  test    rsi, rsi
0x180003022  jz      short loc_18000304A
0x180003024  mov     rcx, [rsi+8]
0x180003028  mov     rax, [rsi]
0x18000302b  call    cs:__guard_dispatch_icall_fptr
0x180003031  mov     rbx, [rsi+10h]
0x180003035  mov     edx, 18h
0x18000303a  mov     rcx, rsi; Block
0x18000303d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003042  mov     rsi, rbx
0x180003045  test    rbx, rbx
0x180003048  jnz     short loc_180003024
0x18000304a  and     qword ptr [rdi+10h], 0
0x18000304f  and     qword ptr [rdi+10h], 0
0x180003054  mov     rcx, [rdi+40h]
0x180003058  test    rcx, rcx
0x18000305b  jz      short loc_18000306A
0x18000305d  mov     rax, [rcx]
0x180003060  mov     rax, [rax+10h]
0x180003064  call    cs:__guard_dispatch_icall_fptr
0x18000306a  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000306e  call    cs:__imp_DeleteCriticalSection
0x180003074  and     dword ptr [rdi+8], 0
0x180003078  mov     rbx, [rsp+28h+arg_0]
0x18000307d  mov     rsi, [rsp+28h+arg_8]
0x180003082  add     rsp, 20h
0x180003086  pop     rdi
0x180003087  retn
```
