# CommsPlatformHelperUtilModule::`vector deleting destructor'(uint)

- ea: `0x180003d70`
- end: `0x180003de0`
- name: `??_ECommsPlatformHelperUtilModule@@UEAAPEAXI@Z`
- size: `112`
- prototype: `CommsPlatformHelperUtilModule *__fastcall(CommsPlatformHelperUtilModule *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180003bfc`
- `0x180003d70`
- `0x18000b010`

## pseudocode

```c
CommsPlatformHelperUtilModule *__fastcall CommsPlatformHelperUtilModule::`vector deleting destructor'(
        CommsPlatformHelperUtilModule *this,
        char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_1800110B0;
  v4 = off_1800110B8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v4 = off_1800110B8;
    }
    ++v2;
  }
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003d70  mov     [rsp+arg_0], rbx
0x180003d75  mov     [rsp+arg_8], rsi
0x180003d7a  push    rdi
0x180003d7b  sub     rsp, 20h
0x180003d7f  mov     rbx, cs:off_1800110B0
0x180003d86  mov     esi, edx
0x180003d88  mov     rax, cs:off_1800110B8
0x180003d8f  mov     rdi, rcx
0x180003d92  jmp     short loc_180003DB2
0x180003d94  mov     r8, [rbx]
0x180003d97  test    r8, r8
0x180003d9a  jz      short loc_180003DAE
0x180003d9c  mov     rax, [r8+40h]
0x180003da0  xor     ecx, ecx
0x180003da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da7  mov     rax, cs:off_1800110B8
0x180003dae  add     rbx, 8
0x180003db2  cmp     rbx, rax
0x180003db5  jb      short loc_180003D94
0x180003db7  mov     rcx, rdi; this
0x180003dba  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x180003dbf  test    sil, 1
0x180003dc3  jz      short loc_180003DCD
0x180003dc5  mov     rcx, rdi; Block
0x180003dc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003dcd  mov     rbx, [rsp+28h+arg_0]
0x180003dd2  mov     rax, rdi
0x180003dd5  mov     rsi, [rsp+28h+arg_8]
0x180003dda  add     rsp, 20h
0x180003dde  pop     rdi
0x180003ddf  retn
```
