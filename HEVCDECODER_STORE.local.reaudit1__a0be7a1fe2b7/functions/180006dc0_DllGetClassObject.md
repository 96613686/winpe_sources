# DllGetClassObject

- ea: `0x180006dc0`
- end: `0x180006ead`
- name: `DllGetClassObject`
- size: `237`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002c40`
- `0x180006dc0`
- `0x180172640`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006df1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006df1`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v4; // ebp
  __int64 *v6; // rbx
  unsigned __int64 v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // rax
  int v11; // [rsp+50h] [rbp+18h] BYREF

  v4 = (int)riid;
  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_1801AB9C8 = 1;
  *ppv = 0;
  v6 = (__int64 *)((*(__int64 (__fastcall **)(int *))(*(_QWORD *)&qword_1801AB9C0 + 32LL))(&qword_1801AB9C0) + 8);
  v7 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)&qword_1801AB9C0 + 40LL))(&qword_1801AB9C0);
  if ( (unsigned __int64)v6 >= v7 )
    return -2147221231;
  while ( 1 )
  {
    v8 = *v6;
    if ( *v6 )
    {
      v9 = *(_QWORD **)(v8 + 8);
      if ( *v9 == *(_QWORD *)&rclsid->Data1 && v9[1] == *(_QWORD *)rclsid->Data4 )
        break;
    }
    if ( (unsigned __int64)++v6 >= v7 )
      return -2147221231;
  }
  v11 = 1;
  return sub_180002C40((int)&qword_1801AB9C0, (int)&v11, v4, v8, ppv);
}

```

## disassembly

```asm
0x180006dc0  mov     [rsp+arg_0], rbx
0x180006dc5  mov     [rsp+arg_8], rbp
0x180006dca  mov     [rsp+arg_18], rsi
0x180006dcf  push    rdi
0x180006dd0  sub     rsp, 30h
0x180006dd4  mov     rsi, r8
0x180006dd7  mov     rbp, rdx
0x180006dda  mov     rdi, rcx
0x180006ddd  xor     r9d, r9d; Context
0x180006de0  xor     r8d, r8d; Parameter
0x180006de3  lea     rdx, InitFn; InitFn
0x180006dea  lea     rcx, InitOnce; InitOnce
0x180006df1  call    cs:InitOnceExecuteOnce
0x180006df8  nop     dword ptr [rax+rax+00h]
0x180006dfd  mov     cs:byte_1801AB9C8, 1
0x180006e04  mov     qword ptr [rsi], 0
0x180006e0b  mov     rax, cs:qword_1801AB9C0
0x180006e12  lea     rcx, qword_1801AB9C0
0x180006e19  mov     rax, [rax+20h]
0x180006e1d  call    cs:__guard_dispatch_icall_fptr
0x180006e23  lea     rbx, [rax+8]
0x180006e27  mov     rax, cs:qword_1801AB9C0
0x180006e2e  lea     rcx, qword_1801AB9C0
0x180006e35  mov     rax, [rax+28h]
0x180006e39  call    cs:__guard_dispatch_icall_fptr
0x180006e3f  mov     rdx, rax
0x180006e42  cmp     rbx, rax
0x180006e45  jnb     short loc_180006E6E
0x180006e47  mov     r9, [rbx]; int
0x180006e4a  test    r9, r9
0x180006e4d  jz      short loc_180006E65
0x180006e4f  mov     rax, [r9+8]
0x180006e53  mov     rcx, [rax]
0x180006e56  cmp     rcx, [rdi]
0x180006e59  jnz     short loc_180006E65
0x180006e5b  mov     rax, [rax+8]
0x180006e5f  cmp     rax, [rdi+8]
0x180006e63  jz      short loc_180006E89
0x180006e65  add     rbx, 8
0x180006e69  cmp     rbx, rdx
0x180006e6c  jb      short loc_180006E47
0x180006e6e  mov     eax, 80040111h
0x180006e73  mov     rbx, [rsp+38h+arg_0]
0x180006e78  mov     rbp, [rsp+38h+arg_8]
0x180006e7d  mov     rsi, [rsp+38h+arg_18]
0x180006e82  add     rsp, 30h
0x180006e86  pop     rdi
0x180006e87  retn
0x180006e89  mov     [rsp+38h+arg_10], 1
0x180006e91  mov     [rsp+38h+Ptr], rsi; Ptr
0x180006e96  mov     r8, rbp; int
0x180006e99  lea     rdx, [rsp+38h+arg_10]; int
0x180006e9e  lea     rcx, qword_1801AB9C0; int
0x180006ea5  call    sub_180002C40
0x180006eaa  nop
0x180006eab  jmp     short loc_180006E73
```
