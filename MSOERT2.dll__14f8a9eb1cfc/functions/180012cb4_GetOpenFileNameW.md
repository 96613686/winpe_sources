# GetOpenFileNameW

- ea: `0x180012cb4`
- end: `0x180012d0c`
- name: `GetOpenFileNameW`
- size: `88`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001cb0`

## callees

- `0x1800129d8`
- `0x180012a40`
- `0x180012cb4`
- `0x180012e24`
- `0x180014010`

## pseudocode

```c
BOOL __stdcall GetOpenFileNameW(LPOPENFILENAMEW a1)
{
  int v2; // ebx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  GetProcFromComDlg();
  if ( qword_180020A10 )
  {
    SHActivateContext(&ulCookie);
    v2 = ((__int64 (__fastcall *)(LPOPENFILENAMEW))qword_180020A10)(a1);
    SHDeactivateContext(ulCookie);
  }
  return v2;
}

```

## disassembly

```asm
0x180012cb4  mov     [rsp+arg_0], rbx
0x180012cb9  push    rdi
0x180012cba  sub     rsp, 20h
0x180012cbe  mov     rdi, rcx
0x180012cc1  mov     [rsp+28h+ulCookie], 0
0x180012cca  xor     ebx, ebx
0x180012ccc  call    _GetProcFromComDlg
0x180012cd1  cmp     cs:qword_180020A10, rbx
0x180012cd8  jz      short loc_180012CFF
0x180012cda  lea     rcx, [rsp+28h+ulCookie]
0x180012cdf  call    SHActivateContext
0x180012ce4  mov     rax, cs:qword_180020A10
0x180012ceb  mov     rcx, rdi
0x180012cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf3  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180012cf8  mov     ebx, eax
0x180012cfa  call    SHDeactivateContext
0x180012cff  mov     eax, ebx
0x180012d01  mov     rbx, [rsp+28h+arg_0]
0x180012d06  add     rsp, 20h
0x180012d0a  pop     rdi
0x180012d0b  retn
```
