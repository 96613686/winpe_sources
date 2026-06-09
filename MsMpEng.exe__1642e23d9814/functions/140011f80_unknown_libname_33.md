# unknown_libname_33

- ea: `0x140011f80`
- end: `0x140011fe7`
- name: `unknown_libname_33`
- size: `103`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140014130`
- `0x1400142f4`
- `0x1400144b8`
- `0x14001470c`
- `0x140015c64`
- `0x140015f48`
- `0x140016828`
- `0x14001ab10`
- `0x14001bc50`
- `0x14001c1c8`
- `0x140021700`
- `0x140023a2c`
- `0x1400245bc`

## callees

- `0x140011f80`
- `0x140019148`
- `0x140019748`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140011fc8`
- `KERNEL32!SetLastError` at `0x140011fc8`
- `KERNEL32!GetLastError` at `0x140011f94`
- `KERNEL32!GetLastError` at `0x140011f94`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_33(__int64 a1)
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
    v5 = sub_140019748(&dwErrCode, v4);
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
0x140011f80  push    rdi
0x140011f82  sub     rsp, 20h
0x140011f86  cmp     qword ptr [rcx], 0
0x140011f8a  mov     rdi, rcx
0x140011f8d  jnz     short loc_140011FD8
0x140011f8f  mov     [rsp+28h+arg_8], rbx
0x140011f94  call    cs:GetLastError
0x140011f9a  cmp     byte ptr [rdi+10h], 0
0x140011f9e  mov     [rsp+28h+dwErrCode], eax
0x140011fa2  jnz     short loc_140011FB0
0x140011fa4  xor     edx, edx
0x140011fa6  mov     byte ptr [rdi+10h], 1
0x140011faa  mov     [rdi+8], rdx
0x140011fae  jmp     short loc_140011FB4
0x140011fb0  mov     rdx, [rdi+8]
0x140011fb4  lea     rcx, [rsp+28h+dwErrCode]
0x140011fb9  call    sub_140019748
0x140011fbe  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x140011fc2  mov     rbx, rax
0x140011fc5  mov     [rdi], rax
0x140011fc8  call    cs:SetLastError
0x140011fce  test    rbx, rbx
0x140011fd1  mov     rbx, [rsp+28h+arg_8]
0x140011fd6  jz      short loc_140011FE1
0x140011fd8  mov     rax, [rdi]
0x140011fdb  add     rsp, 20h
0x140011fdf  pop     rdi
0x140011fe0  retn
0x140011fe1  call    abort
```
