# McTemplateU0zz_EtwEventWriteTransfer

- ea: `0x180004f94`
- end: `0x180005023`
- name: `McTemplateU0zz_EtwEventWriteTransfer`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012c4`
- `0x1800023a8`
- `0x180003a1c`
- `0x180006c40`

## callees

- `0x180004f94`
- `0x18000502c`
- `0x18000a980`

## pseudocode

```c
__int64 __fastcall McTemplateU0zz_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v9 = 74;
  v8 = L"bc90d167-9470-4139-a9ba-be0bbbf5b74d";
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, (__int64)L"NULL", 3, (__int64)v7);
}

```

## disassembly

```asm
0x180004f94  sub     rsp, 78h
0x180004f98  mov     rax, cs:__security_cookie
0x180004f9f  xor     rax, rsp
0x180004fa2  mov     [rsp+78h+var_18], rax
0x180004fa7  xor     r10d, r10d
0x180004faa  mov     [rsp+78h+var_30], 4Ah ; 'J'
0x180004fb3  lea     rax, aBc90d167947041; "bc90d167-9470-4139-a9ba-be0bbbf5b74d"
0x180004fba  mov     [rsp+78h+var_38], rax
0x180004fbf  test    r9, r9
0x180004fc2  jz      short loc_18000501C
0x180004fc4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004fc8  inc     rax
0x180004fcb  cmp     [r9+rax*2], r10w
0x180004fd0  jnz     short loc_180004FC8
0x180004fd2  lea     eax, ds:2[rax*2]
0x180004fd9  test    r9, r9
0x180004fdc  mov     [rsp+78h+var_20], eax
0x180004fe0  lea     r8, aNull; "NULL"
0x180004fe7  mov     [rsp+78h+var_1C], r10d
0x180004fec  cmovz   r9, r8
0x180004ff0  lea     rax, [rsp+78h+var_48]
0x180004ff5  mov     [rsp+78h+var_28], r9
0x180004ffa  mov     r9d, 3
0x180005000  mov     [rsp+78h+var_58], rax
0x180005005  call    McGenEventWrite_EtwEventWriteTransfer
0x18000500a  mov     rcx, [rsp+78h+var_18]
0x18000500f  xor     rcx, rsp; StackCookie
0x180005012  call    __security_check_cookie
0x180005017  add     rsp, 78h
0x18000501b  retn
0x18000501c  mov     eax, 0Ah
0x180005021  jmp     short loc_180004FD9
```
