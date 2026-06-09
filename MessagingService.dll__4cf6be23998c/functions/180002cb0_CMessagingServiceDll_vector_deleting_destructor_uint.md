# CMessagingServiceDll::`vector deleting destructor'(uint)

- ea: `0x180002cb0`
- end: `0x180002d22`
- name: `??_ECMessagingServiceDll@@UEAAPEAXI@Z`
- size: `114`
- prototype: `CMessagingServiceDll *__fastcall(CMessagingServiceDll *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002c08`
- `0x180002cb0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d09`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d09`

## pseudocode

```c
CMessagingServiceDll *__fastcall CMessagingServiceDll::`vector deleting destructor'(
        CMessagingServiceDll *this,
        char a2)
{
  __int64 *v4; // rbx
  __int64 *v5; // rax

  v4 = off_180013180[0];
  v5 = off_180013188;
  while ( v4 < v5 )
  {
    if ( *v4 )
    {
      (*(void (__fastcall **)(_QWORD))(*v4 + 64))(0);
      v5 = off_180013188;
    }
    ++v4;
  }
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp+arg_0], rbx
0x180002cb5  mov     [rsp+arg_8], rsi
0x180002cba  push    rdi
0x180002cbb  sub     rsp, 20h
0x180002cbf  mov     esi, edx
0x180002cc1  mov     rdi, rcx
0x180002cc4  mov     rbx, cs:off_180013180
0x180002ccb  mov     rax, cs:off_180013188
0x180002cd2  jmp     short loc_180002CF2
0x180002cd4  mov     r8, [rbx]
0x180002cd7  test    r8, r8
0x180002cda  jz      short loc_180002CEE
0x180002cdc  xor     ecx, ecx
0x180002cde  mov     rax, [r8+40h]
0x180002ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce7  mov     rax, cs:off_180013188
0x180002cee  add     rbx, 8
0x180002cf2  cmp     rbx, rax
0x180002cf5  jb      short loc_180002CD4
0x180002cf7  mov     rcx, rdi; this
0x180002cfa  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x180002cff  nop
0x180002d00  test    sil, 1
0x180002d04  jz      short loc_180002D0F
0x180002d06  mov     rcx, rdi
0x180002d09  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d0f  mov     rax, rdi
0x180002d12  mov     rbx, [rsp+28h+arg_0]
0x180002d17  mov     rsi, [rsp+28h+arg_8]
0x180002d1c  add     rsp, 20h
0x180002d20  pop     rdi
0x180002d21  retn
```
