# DllGetClassObject

- ea: `0x1800c6db0`
- end: `0x1800c6ea4`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180096dec`
- `0x18009904c`
- `0x1800c6db0`
- `0x18020cab0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v6; // rax
  __int64 v7; // rax
  int i; // ecx
  char *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  void *v12; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = *(_QWORD *)&riid->Data1;
  if ( !*(_QWORD *)&riid->Data1 )
    v6 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( !v6 )
    goto LABEL_10;
  v7 = *(_QWORD *)&riid->Data1 - 1LL;
  if ( *(_QWORD *)&riid->Data1 == 1 )
    v7 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( v7 )
    return -2147467262;
LABEL_10:
  for ( i = 0; ; ++i )
  {
    if ( i >= 1 )
      return -2147221231;
    v9 = (char *)&off_180281000 + 16 * i;
    v10 = **(_QWORD **)v9 - *(_QWORD *)&rclsid->Data1;
    if ( !v10 )
      v10 = *(_QWORD *)(*(_QWORD *)v9 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v10 )
      break;
  }
  v11 = sub_18009904C(24);
  if ( v11 )
  {
    v12 = (void *)sub_180096DEC(v11, v9);
    *ppv = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 8LL))(v12);
      return 0;
    }
  }
  else
  {
    *ppv = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x1800c6db0  mov     [rsp+arg_0], rbx
0x1800c6db5  push    rdi
0x1800c6db6  sub     rsp, 20h
0x1800c6dba  mov     rbx, r8
0x1800c6dbd  mov     r8, rcx
0x1800c6dc0  test    rbx, rbx
0x1800c6dc3  jnz     short loc_1800C6DCF
0x1800c6dc5  mov     eax, 80004003h
0x1800c6dca  jmp     loc_1800C6E98
0x1800c6dcf  mov     qword ptr [rbx], 0
0x1800c6dd6  mov     rax, [rdx]
0x1800c6dd9  sub     rax, cs:qword_180219FD0
0x1800c6de0  jnz     short loc_1800C6DED
0x1800c6de2  mov     rax, [rdx+8]
0x1800c6de6  sub     rax, cs:qword_180219FD8
0x1800c6ded  test    rax, rax
0x1800c6df0  jz      short loc_1800C6E18
0x1800c6df2  mov     rax, [rdx]
0x1800c6df5  sub     rax, cs:qword_180219FE0
0x1800c6dfc  jnz     short loc_1800C6E09
0x1800c6dfe  mov     rax, [rdx+8]
0x1800c6e02  sub     rax, cs:qword_180219FE8
0x1800c6e09  test    rax, rax
0x1800c6e0c  jz      short loc_1800C6E18
0x1800c6e0e  mov     eax, 80004002h
0x1800c6e13  jmp     loc_1800C6E98
0x1800c6e18  xor     ecx, ecx
0x1800c6e1a  cmp     ecx, 1
0x1800c6e1d  jge     short loc_1800C6E93
0x1800c6e1f  lea     rdx, off_180281000
0x1800c6e26  movsxd  rdi, ecx
0x1800c6e29  shl     rdi, 4
0x1800c6e2d  add     rdi, rdx
0x1800c6e30  mov     rdx, [rdi]
0x1800c6e33  mov     rax, [rdx]
0x1800c6e36  sub     rax, [r8]
0x1800c6e39  jnz     short loc_1800C6E43
0x1800c6e3b  mov     rax, [rdx+8]
0x1800c6e3f  sub     rax, [r8+8]
0x1800c6e43  test    rax, rax
0x1800c6e46  jz      short loc_1800C6E4C
0x1800c6e48  inc     ecx
0x1800c6e4a  jmp     short loc_1800C6E1A
0x1800c6e4c  mov     ecx, 18h
0x1800c6e51  call    sub_18009904C
0x1800c6e56  test    rax, rax
0x1800c6e59  jz      short loc_1800C6E85
0x1800c6e5b  mov     rdx, rdi
0x1800c6e5e  mov     rcx, rax
0x1800c6e61  call    sub_180096DEC
0x1800c6e66  mov     [rbx], rax
0x1800c6e69  mov     rdx, rax
0x1800c6e6c  test    rax, rax
0x1800c6e6f  jz      short loc_1800C6E8C
0x1800c6e71  mov     rcx, [rax]
0x1800c6e74  mov     rax, [rcx+8]
0x1800c6e78  mov     rcx, rdx
0x1800c6e7b  call    cs:__guard_dispatch_icall_fptr
0x1800c6e81  xor     eax, eax
0x1800c6e83  jmp     short loc_1800C6E98
0x1800c6e85  mov     qword ptr [rbx], 0
0x1800c6e8c  mov     eax, 8007000Eh
0x1800c6e91  jmp     short loc_1800C6E98
0x1800c6e93  mov     eax, 80040111h
0x1800c6e98  mov     rbx, [rsp+28h+arg_0]
0x1800c6e9d  add     rsp, 20h
0x1800c6ea1  pop     rdi
0x1800c6ea2  retn
```
