# Mso::Logging::StructuredTraceHolder::IsValid(void)

- ea: `0x180019830`
- end: `0x18001989f`
- name: `?IsValid@StructuredTraceHolder@Logging@Mso@@UEAA_NXZ`
- size: `111`
- prototype: `bool __fastcall(Mso::Logging::StructuredTraceHolder *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800198c0`

## callees

- `0x180019830`
- `0x180019fcc`
- `0x1800261b0`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180019857`
- `KERNEL32!InitOnceBeginInitialize` at `0x180019857`
- `KERNEL32!InitOnceComplete` at `0x180019882`
- `KERNEL32!InitOnceComplete` at `0x180019882`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180019861`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180019861`

## pseudocode

```c
bool __fastcall Mso::Logging::StructuredTraceHolder::IsValid(union _RTL_RUN_ONCE *this)
{
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  union _RTL_RUN_ONCE *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = this;
  v3 = 0;
  if ( !__std_init_once_begin_initialize(this + 4, 0, &v3, 0) )
    abort();
  if ( v3 )
  {
    sub_180019FCC(&v4);
    if ( !InitOnceComplete(this + 4, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  return (bool)this[5].Ptr;
}

```

## disassembly

```asm
0x180019830  mov     rax, rsp
0x180019833  mov     [rax+18h], rbx
0x180019837  push    rdi
0x180019838  sub     rsp, 30h
0x18001983c  mov     rbx, rcx
0x18001983f  mov     [rax+10h], rcx
0x180019843  add     rcx, 20h ; ' '; lpInitOnce
0x180019847  mov     dword ptr [rax+8], 0
0x18001984e  xor     r9d, r9d; lpContext
0x180019851  lea     r8, [rax+8]; fPending
0x180019855  xor     edx, edx; dwFlags
0x180019857  call    cs:__imp___std_init_once_begin_initialize
0x18001985d  test    eax, eax
0x18001985f  jnz     short loc_180019868
0x180019861  call    cs:__imp_abort
0x180019868  cmp     [rsp+38h+arg_0], 0
0x18001986d  jz      short loc_18001988C
0x18001986f  lea     rcx, [rsp+38h+arg_8]
0x180019874  call    sub_180019FCC
0x180019879  xor     r8d, r8d; lpContext
0x18001987c  lea     rcx, [rbx+20h]; lpInitOnce
0x180019880  xor     edx, edx; dwFlags
0x180019882  call    cs:__imp_InitOnceComplete
0x180019888  test    eax, eax
0x18001988a  jz      short loc_18001989A
0x18001988c  mov     al, [rbx+28h]
0x18001988f  mov     rbx, [rsp+38h+arg_10]
0x180019894  add     rsp, 30h
0x180019898  pop     rdi
0x180019899  retn
0x18001989a  call    __std_init_once_link_alternate_names_and_abort
```
