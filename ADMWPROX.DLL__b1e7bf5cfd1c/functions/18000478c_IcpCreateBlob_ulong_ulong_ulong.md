# IcpCreateBlob(ulong,ulong,ulong)

- ea: `0x18000478c`
- end: `0x180004802`
- name: `?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z`
- size: `118`
- prototype: `struct _IC_BLOB *__fastcall(int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005f7c`
- `0x180006104`
- `0x180006704`
- `0x180006ad8`

## callees

- `0x18000478c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800047bc`
- `KERNEL32!SetLastError` at `0x1800047bc`
- `ole32!CoTaskMemAlloc` at `0x1800047e6`
- `ole32!CoTaskMemAlloc` at `0x1800047e6`

## pseudocode

```c
struct _IC_BLOB *__fastcall IcpCreateBlob(int a1, unsigned int a2, unsigned int a3)
{
  unsigned int v5; // edx
  unsigned int v7; // eax
  _DWORD *v8; // rbx
  unsigned int v10; // edi
  _DWORD *v11; // rax

  v5 = a3 + 8;
  if ( a3 + 8 < a3 )
    goto LABEL_4;
  if ( a3 )
  {
    v7 = (a2 + 7) & 0xFFFFFFF8;
    if ( v7 < a2 )
    {
LABEL_4:
      v8 = 0;
      SetLastError(8u);
      return (struct _IC_BLOB *)v8;
    }
  }
  else
  {
    v7 = a2;
  }
  v10 = v5 + v7;
  if ( v5 + v7 < v7 || !v10 || v10 + 8 < v10 )
    goto LABEL_4;
  v11 = CoTaskMemAlloc(v10 + 8);
  v8 = v11;
  if ( v11 )
  {
    *v11 = a1;
    v11[1] = v10;
    v11[2] = a2;
    v11[3] = a3;
  }
  return (struct _IC_BLOB *)v8;
}

```

## disassembly

```asm
0x18000478c  push    rbx
0x18000478e  push    rbp
0x18000478f  push    rsi
0x180004790  push    rdi
0x180004791  push    r14
0x180004793  sub     rsp, 20h
0x180004797  mov     esi, edx
0x180004799  mov     ebp, r8d
0x18000479c  lea     edx, [r8+8]
0x1800047a0  mov     r14d, ecx
0x1800047a3  cmp     edx, r8d
0x1800047a6  jb      short loc_1800047B7
0x1800047a8  test    r8d, r8d
0x1800047ab  jz      short loc_1800047D0
0x1800047ad  lea     eax, [rsi+7]
0x1800047b0  and     eax, 0FFFFFFF8h
0x1800047b3  cmp     eax, esi
0x1800047b5  jnb     short loc_1800047D2
0x1800047b7  xor     ebx, ebx
0x1800047b9  lea     ecx, [rbx+8]; dwErrCode
0x1800047bc  call    cs:__imp_SetLastError
0x1800047c2  mov     rax, rbx
0x1800047c5  add     rsp, 20h
0x1800047c9  pop     r14
0x1800047cb  pop     rdi
0x1800047cc  pop     rsi
0x1800047cd  pop     rbp
0x1800047ce  pop     rbx
0x1800047cf  retn
0x1800047d0  mov     eax, esi
0x1800047d2  lea     edi, [rdx+rax]
0x1800047d5  cmp     edi, eax
0x1800047d7  jb      short loc_1800047B7
0x1800047d9  test    edi, edi
0x1800047db  jz      short loc_1800047B7
0x1800047dd  lea     eax, [rdi+8]
0x1800047e0  cmp     eax, edi
0x1800047e2  jb      short loc_1800047B7
0x1800047e4  mov     ecx, eax; cb
0x1800047e6  call    cs:__imp_CoTaskMemAlloc
0x1800047ec  mov     rbx, rax
0x1800047ef  test    rax, rax
0x1800047f2  jz      short loc_1800047C2
0x1800047f4  mov     [rax], r14d
0x1800047f7  mov     [rax+4], edi
0x1800047fa  mov     [rax+8], esi
0x1800047fd  mov     [rax+0Ch], ebp
0x180004800  jmp     short loc_1800047C2
```
