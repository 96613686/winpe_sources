# CDriveConfiguration::QueryStepPercentComplete(ulong *)

- ea: `0x1800100b0`
- end: `0x180010113`
- name: `?QueryStepPercentComplete@CDriveConfiguration@@QEAAJPEAK@Z`
- size: `99`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800100b0`
- `0x180015010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800100cf`
- `KERNEL32!EnterCriticalSection` at `0x1800100cf`
- `KERNEL32!LeaveCriticalSection` at `0x180010101`
- `KERNEL32!LeaveCriticalSection` at `0x180010101`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::QueryStepPercentComplete(CDriveConfiguration *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx

  *a2 = 0;
  v4 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_DWORD *)this + 4) == 1 )
  {
    v5 = *((_QWORD *)this + 160);
    if ( v5 )
      v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 16LL))(v5, a2);
    else
      v4 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v4;
}

```

## disassembly

```asm
0x1800100b0  push    rbx
0x1800100b2  push    rsi
0x1800100b3  push    rdi
0x1800100b4  push    r14
0x1800100b6  sub     rsp, 28h
0x1800100ba  mov     rdi, rcx
0x1800100bd  mov     dword ptr [rdx], 0
0x1800100c3  add     rcx, 18h; lpCriticalSection
0x1800100c7  mov     r14, rdx
0x1800100ca  mov     ebx, 1
0x1800100cf  call    cs:__imp_EnterCriticalSection
0x1800100d5  mov     eax, [rdi+10h]
0x1800100d8  cmp     eax, ebx
0x1800100da  jnz     short loc_1800100FD
0x1800100dc  mov     rcx, [rdi+500h]
0x1800100e3  test    rcx, rcx
0x1800100e6  jz      short loc_1800100FB
0x1800100e8  mov     rax, [rcx]
0x1800100eb  mov     rdx, r14
0x1800100ee  mov     rax, [rax+10h]
0x1800100f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100f7  mov     ebx, eax
0x1800100f9  jmp     short loc_1800100FD
0x1800100fb  xor     ebx, ebx
0x1800100fd  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010101  call    cs:__imp_LeaveCriticalSection
0x180010107  mov     eax, ebx
0x180010109  add     rsp, 28h
0x18001010d  pop     r14
0x18001010f  pop     rdi
0x180010110  pop     rsi
0x180010111  pop     rbx
0x180010112  retn
```
