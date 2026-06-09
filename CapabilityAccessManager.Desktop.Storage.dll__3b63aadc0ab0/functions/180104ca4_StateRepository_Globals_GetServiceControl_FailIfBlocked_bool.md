# StateRepository::Globals::GetServiceControl_FailIfBlocked(bool)

- ea: `0x180104ca4`
- end: `0x180104cfb`
- name: `?GetServiceControl_FailIfBlocked@Globals@StateRepository@@YAJ_N@Z`
- size: `87`
- prototype: `__int64 __fastcall(StateRepository::Globals *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180101504`
- `0x1801019b8`

## callees

- `0x180104ca4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180104cb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180104cb0`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::GetServiceControl_FailIfBlocked(StateRepository::Globals *this)
{
  int v1; // ebx

  v1 = dword_180140478;
  if ( v1 == GetCurrentThreadId() )
    return 0;
  if ( (qword_180140470 & 0x200000000LL) != 0 )
    return 2147943515LL;
  if ( (qword_180140470 & 0x100000000LL) != 0 )
    return 2154233872LL;
  return (_DWORD)qword_180140470 != 0 ? 0x80670006 : 0;
}

```

## disassembly

```asm
0x180104ca4  push    rbx
0x180104ca6  sub     rsp, 20h
0x180104caa  mov     ebx, cs:dword_180140478
0x180104cb0  call    cs:__imp_GetCurrentThreadId
0x180104cb6  cmp     ebx, eax
0x180104cb8  jnz     short loc_180104CBE
0x180104cba  xor     eax, eax
0x180104cbc  jmp     short loc_180104CF5
0x180104cbe  mov     rax, cs:qword_180140470
0x180104cc5  mov     [rsp+28h+arg_8], rax
0x180104cca  mov     eax, dword ptr [rsp+28h+arg_8+4]
0x180104cce  test    al, 2
0x180104cd0  jz      short loc_180104CD9
0x180104cd2  mov     eax, 8007045Bh
0x180104cd7  jmp     short loc_180104CF5
0x180104cd9  mov     eax, dword ptr [rsp+28h+arg_8+4]
0x180104cdd  test    al, 1
0x180104cdf  jz      short loc_180104CE8
0x180104ce1  mov     eax, 80670010h
0x180104ce6  jmp     short loc_180104CF5
0x180104ce8  mov     eax, dword ptr [rsp+28h+arg_8]
0x180104cec  neg     eax
0x180104cee  sbb     eax, eax
0x180104cf0  and     eax, 80670006h
0x180104cf5  add     rsp, 20h
0x180104cf9  pop     rbx
0x180104cfa  retn
```
