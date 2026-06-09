# unknown_libname_14

- ea: `0x140005a90`
- end: `0x140005af7`
- name: `unknown_libname_14`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005b00`
- `0x1400063f0`
- `0x14000a15c`
- `0x14000c784`

## callees

- `0x140005a20`
- `0x140005a90`
- `0x1400060d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005aa4`
- `KERNEL32!GetLastError` at `0x140005aa4`
- `KERNEL32!SetLastError` at `0x140005ad8`
- `KERNEL32!SetLastError` at `0x140005ad8`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_14(__int64 a1)
{
  DWORD LastError; // eax
  bool v3; // zf
  __int64 v4; // rdx
  __int64 v5; // rax
  DWORD v6; // ecx
  __int64 v7; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)a1 )
  {
    LastError = GetLastError();
    v3 = *(_BYTE *)(a1 + 16) == 0;
    dwErrCode = LastError;
    if ( v3 )
    {
      v4 = 0;
      *(_BYTE *)(a1 + 16) = 1;
      *(_QWORD *)(a1 + 8) = 0;
    }
    else
    {
      v4 = *(_QWORD *)(a1 + 8);
    }
    v5 = sub_1400060D8(&dwErrCode, v4);
    v6 = dwErrCode;
    v7 = v5;
    *(_QWORD *)a1 = v5;
    SetLastError(v6);
    if ( !v7 )
      abort();
  }
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x140005a90  push    rdi
0x140005a92  sub     rsp, 20h
0x140005a96  cmp     qword ptr [rcx], 0
0x140005a9a  mov     rdi, rcx
0x140005a9d  jnz     short loc_140005AE8
0x140005a9f  mov     [rsp+28h+arg_8], rbx
0x140005aa4  call    cs:GetLastError
0x140005aaa  cmp     byte ptr [rdi+10h], 0
0x140005aae  mov     [rsp+28h+dwErrCode], eax
0x140005ab2  jnz     short loc_140005AC0
0x140005ab4  xor     edx, edx
0x140005ab6  mov     byte ptr [rdi+10h], 1
0x140005aba  mov     [rdi+8], rdx
0x140005abe  jmp     short loc_140005AC4
0x140005ac0  mov     rdx, [rdi+8]
0x140005ac4  lea     rcx, [rsp+28h+dwErrCode]
0x140005ac9  call    sub_1400060D8
0x140005ace  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x140005ad2  mov     rbx, rax
0x140005ad5  mov     [rdi], rax
0x140005ad8  call    cs:SetLastError
0x140005ade  test    rbx, rbx
0x140005ae1  mov     rbx, [rsp+28h+arg_8]
0x140005ae6  jz      short loc_140005AF1
0x140005ae8  mov     rax, [rdi]
0x140005aeb  add     rsp, 20h
0x140005aef  pop     rdi
0x140005af0  retn
0x140005af1  call    abort
```
