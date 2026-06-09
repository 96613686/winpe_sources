# McTemplateU0z_EtwEventWriteTransfer

- ea: `0x180007c90`
- end: `0x180007d11`
- name: `McTemplateU0z_EtwEventWriteTransfer`
- size: `129`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c20`
- `0x1800066f0`
- `0x180013404`
- `0x1800157d4`
- `0x18001640c`
- `0x1800167c8`
- `0x180016b9c`

## callees

- `0x180007c90`
- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0z_EtwEventWriteTransfer(__int64 a1, int a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    while ( a3[++v3] != 0 )
      ;
    v5 = 2 * v3 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EtwEventWriteTransfer((unsigned int)L"NULL", a2, (_DWORD)a3, 2, (__int64)v7);
}

```

## disassembly

```asm
0x180007c90  sub     rsp, 68h
0x180007c94  mov     rax, cs:__security_cookie
0x180007c9b  xor     rax, rsp
0x180007c9e  mov     [rsp+68h+var_18], rax
0x180007ca3  test    r8, r8
0x180007ca6  jz      short loc_180007CC6
0x180007ca8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007caf  nop
0x180007cb0  cmp     word ptr [r8+rax*2+2], 0
0x180007cb7  lea     rax, [rax+1]
0x180007cbb  jnz     short loc_180007CB0
0x180007cbd  lea     eax, ds:2[rax*2]
0x180007cc4  jmp     short loc_180007CCB
0x180007cc6  mov     eax, 0Ah
0x180007ccb  test    r8, r8
0x180007cce  mov     [rsp+68h+var_20], eax
0x180007cd2  lea     rcx, aNull_1; "NULL"
0x180007cd9  mov     [rsp+68h+var_1C], 0
0x180007ce1  cmovz   r8, rcx
0x180007ce5  lea     rax, [rsp+68h+var_38]
0x180007cea  mov     r9d, 2
0x180007cf0  mov     [rsp+68h+var_28], r8
0x180007cf5  mov     [rsp+68h+var_48], rax
0x180007cfa  call    McGenEventWrite_EtwEventWriteTransfer
0x180007cff  mov     rcx, [rsp+68h+var_18]
0x180007d04  xor     rcx, rsp; StackCookie
0x180007d07  call    __security_check_cookie
0x180007d0c  add     rsp, 68h
0x180007d10  retn
```
