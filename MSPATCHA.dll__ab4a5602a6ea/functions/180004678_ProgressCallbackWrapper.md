# ProgressCallbackWrapper

- ea: `0x180004678`
- end: `0x1800046d9`
- name: `ProgressCallbackWrapper`
- size: `97`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(__int64, _QWORD, _QWORD), __int64, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d10`
- `0x180002720`
- `0x180003580`
- `0x180004a9c`

## callees

- `0x180004678`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046c5`

## pseudocode

```c
__int64 __fastcall ProgressCallbackWrapper(
        __int64 (__fastcall *a1)(__int64, _QWORD, _QWORD),
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // ebx

  v4 = 1;
  if ( a1 )
  {
    v4 = a1(a2, a3, a4);
    if ( !v4 && !GetLastError() )
      SetLastError(0x4C7u);
  }
  return v4;
}

```

## disassembly

```asm
0x180004678  push    rbx
0x18000467a  sub     rsp, 30h
0x18000467e  mov     r10d, r8d
0x180004681  mov     r11, rdx
0x180004684  mov     rax, rcx
0x180004687  mov     ebx, 1
0x18000468c  test    rcx, rcx
0x18000468f  jz      short loc_1800046D1
0x180004691  mov     r8d, r9d
0x180004694  mov     edx, r10d
0x180004697  mov     rcx, r11
0x18000469a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469f  mov     ebx, eax
0x1800046a1  mov     [rsp+38h+var_18], eax
0x1800046a5  test    eax, eax
0x1800046a7  jnz     short loc_1800046BE
0x1800046a9  call    cs:__imp_GetLastError
0x1800046af  test    eax, eax
0x1800046b1  jnz     short loc_1800046BE
0x1800046b3  mov     ecx, 4C7h; dwErrCode
0x1800046b8  call    cs:__imp_SetLastError
0x1800046be  jmp     short loc_1800046D1
0x1800046c0  mov     ecx, 4C7h; dwErrCode
0x1800046c5  call    cs:__imp_SetLastError
0x1800046cb  xor     ebx, ebx
0x1800046cd  mov     [rsp+38h+var_18], ebx
0x1800046d1  mov     eax, ebx
0x1800046d3  add     rsp, 30h
0x1800046d7  pop     rbx
0x1800046d8  retn
```
