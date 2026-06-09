# WriteBSTRToStreamEx(ushort *,ISequentialStream *,ulong)

- ea: `0x180002f60`
- end: `0x180003020`
- name: `?WriteBSTRToStreamEx@@YAJPEAGPEAUISequentialStream@@K@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct ISequentialStream *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f50`
- `0x180003390`

## callees

- `0x180002f60`
- `0x180004010`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180002f93`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002f93`

## pseudocode

```c
__int64 __fastcall WriteBSTRToStreamEx(unsigned __int16 *a1, struct ISequentialStream *a2, UINT a3)
{
  int v6; // ecx
  UINT v7; // eax
  UINT v9; // [rsp+48h] [rbp+10h] BYREF
  int v10; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  if ( a2 )
  {
    v7 = SysStringByteLen(a1);
    v9 = v7;
    if ( a3 < v7 || a3 - v7 < 4 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v6 = ((__int64 (__fastcall *)(struct ISequentialStream *, UINT *, __int64, int *))a2->lpVtbl->Write)(
             a2,
             &v9,
             4,
             &v10);
      if ( v6 >= 0 )
      {
        if ( v10 != 4 )
          return (unsigned int)-2147467259;
        v6 = ((__int64 (__fastcall *)(struct ISequentialStream *, unsigned __int16 *, _QWORD, int *))a2->lpVtbl->Write)(
               a2,
               a1,
               v9,
               &v10);
        if ( v6 >= 0 && v10 != v9 )
          return (unsigned int)-2147467259;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002f60  mov     rax, rsp
0x180002f63  mov     [rax+8], rbx
0x180002f67  mov     [rax+18h], rsi
0x180002f6b  push    rdi
0x180002f6c  sub     rsp, 30h
0x180002f70  mov     dword ptr [rax+10h], 0
0x180002f77  mov     ebx, r8d
0x180002f7a  mov     dword ptr [rax+20h], 0
0x180002f81  mov     rdi, rdx
0x180002f84  mov     rsi, rcx
0x180002f87  test    rdx, rdx
0x180002f8a  jnz     short loc_180002F93
0x180002f8c  mov     ecx, 80004003h; bstr
0x180002f91  jmp     short loc_18000300E
0x180002f93  call    cs:__imp_SysStringByteLen
0x180002f99  mov     [rsp+38h+arg_8], eax
0x180002f9d  cmp     ebx, eax
0x180002f9f  jb      short loc_180003009
0x180002fa1  sub     ebx, eax
0x180002fa3  cmp     ebx, 4
0x180002fa6  jb      short loc_180003009
0x180002fa8  mov     rax, [rdi]
0x180002fab  lea     r9, [rsp+38h+arg_18]
0x180002fb0  mov     r8d, 4
0x180002fb6  lea     rdx, [rsp+38h+arg_8]
0x180002fbb  mov     rcx, rdi
0x180002fbe  mov     rax, [rax+20h]
0x180002fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc7  mov     ecx, eax
0x180002fc9  test    eax, eax
0x180002fcb  js      short loc_18000300E
0x180002fcd  cmp     [rsp+38h+arg_18], 4
0x180002fd2  jz      short loc_180002FDB
0x180002fd4  mov     ecx, 80004005h
0x180002fd9  jmp     short loc_18000300E
0x180002fdb  mov     rax, [rdi]
0x180002fde  lea     r9, [rsp+38h+arg_18]
0x180002fe3  mov     r8d, [rsp+38h+arg_8]
0x180002fe8  mov     rdx, rsi
0x180002feb  mov     rcx, rdi
0x180002fee  mov     rax, [rax+20h]
0x180002ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff7  mov     ecx, eax
0x180002ff9  test    eax, eax
0x180002ffb  js      short loc_18000300E
0x180002ffd  mov     eax, [rsp+38h+arg_8]
0x180003001  cmp     [rsp+38h+arg_18], eax
0x180003005  jz      short loc_18000300E
0x180003007  jmp     short loc_180002FD4
0x180003009  mov     ecx, 80070216h
0x18000300e  mov     rbx, [rsp+38h+arg_0]
0x180003013  mov     eax, ecx
0x180003015  mov     rsi, [rsp+38h+arg_10]
0x18000301a  add     rsp, 30h
0x18000301e  pop     rdi
0x18000301f  retn
```
