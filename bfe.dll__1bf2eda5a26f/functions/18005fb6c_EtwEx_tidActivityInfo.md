# EtwEx_tidActivityInfo

- ea: `0x18005fb6c`
- end: `0x18005fc56`
- name: `EtwEx_tidActivityInfo`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025910`
- `0x180044e54`

## callees

- `0x180058b30`
- `0x18005fb6c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18005fc10`
- `ntdll!EtwEventWrite` at `0x18005fc10`
- `ntdll!EtwEventActivityIdControl` at `0x18005fbc5`
- `ntdll!EtwEventActivityIdControl` at `0x18005fc32`
- `ntdll!EtwEventActivityIdControl` at `0x18005fbc5`
- `ntdll!EtwEventActivityIdControl` at `0x18005fc32`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(__int64 a1, _WORD *a2, __int128 *a3)
{
  __int64 v3; // rdi
  __int128 *v5; // r9
  __int64 v6; // r8
  unsigned int v7; // edi
  int v9; // [rsp+20h] [rbp-30h] BYREF
  __int128 v10; // [rsp+28h] [rbp-28h] BYREF
  int *v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]

  v3 = MEMORY[0x1800EF368][0];
  v9 = 0;
  if ( *a2 == 0xEA61 )
  {
    v10 = 0;
    if ( a3 )
      v10 = *a3;
    EtwEventActivityIdControl(2, &v10);
  }
  if ( MEMORY[0x1800EF094][180] )
  {
    *((_QWORD *)&v10 + 1) = 16;
    *(_QWORD *)&v10 = &qword_1800F2668[15];
    v5 = &v10;
    v12 = 4;
    v11 = &v9;
    v6 = 2;
  }
  else
  {
    v5 = 0;
    v6 = 0;
  }
  v7 = EtwEventWrite(v3, a2, v6, v5);
  if ( *a2 == 0xEA62 )
  {
    v10 = 0;
    EtwEventActivityIdControl(2, &v10);
  }
  return v7;
}

```

## disassembly

```asm
0x18005fb6c  mov     [rsp-8+arg_0], rbx
0x18005fb71  mov     [rsp-8+arg_18], rdi
0x18005fb76  push    rbp
0x18005fb77  mov     rbp, rsp
0x18005fb7a  sub     rsp, 50h
0x18005fb7e  mov     rax, cs:__security_cookie
0x18005fb85  xor     rax, rsp
0x18005fb88  mov     [rbp+var_8], rax
0x18005fb8c  mov     rdi, cs:1800EF368h
0x18005fb93  mov     eax, 0EA61h
0x18005fb98  mov     rbx, rdx
0x18005fb9b  mov     [rbp+var_30], 0
0x18005fba2  cmp     [rdx], ax
0x18005fba5  jnz     short loc_18005FBCB
0x18005fba7  xorps   xmm0, xmm0
0x18005fbaa  movups  [rbp+var_28], xmm0
0x18005fbae  test    r8, r8
0x18005fbb1  jz      short loc_18005FBBC
0x18005fbb3  movups  xmm0, xmmword ptr [r8]
0x18005fbb7  movdqu  [rbp+var_28], xmm0
0x18005fbbc  lea     rdx, [rbp+var_28]
0x18005fbc0  mov     ecx, 2
0x18005fbc5  call    cs:__imp_EtwEventActivityIdControl
0x18005fbcb  mov     eax, cs:1800EF364h
0x18005fbd1  mov     rdx, rbx
0x18005fbd4  mov     rcx, rdi
0x18005fbd7  test    eax, eax
0x18005fbd9  jz      short loc_18005FC0A
0x18005fbdb  lea     rax, qword_1800F2668+78h
0x18005fbe2  mov     qword ptr [rbp+var_28+8], 10h
0x18005fbea  mov     qword ptr [rbp+var_28], rax
0x18005fbee  lea     r9, [rbp+var_28]
0x18005fbf2  lea     rax, [rbp+var_30]
0x18005fbf6  mov     [rbp+var_10], 4
0x18005fbfe  mov     [rbp+var_18], rax
0x18005fc02  mov     r8d, 2
0x18005fc08  jmp     short loc_18005FC10
0x18005fc0a  xor     r9d, r9d
0x18005fc0d  xor     r8d, r8d
0x18005fc10  call    cs:__imp_EtwEventWrite
0x18005fc16  mov     edi, eax
0x18005fc18  mov     eax, 0EA62h
0x18005fc1d  cmp     [rbx], ax
0x18005fc20  jnz     short loc_18005FC38
0x18005fc22  xorps   xmm0, xmm0
0x18005fc25  lea     rdx, [rbp+var_28]
0x18005fc29  mov     ecx, 2
0x18005fc2e  movups  [rbp+var_28], xmm0
0x18005fc32  call    cs:__imp_EtwEventActivityIdControl
0x18005fc38  mov     eax, edi
0x18005fc3a  mov     rcx, [rbp+var_8]
0x18005fc3e  xor     rcx, rsp; StackCookie
0x18005fc41  call    __security_check_cookie
0x18005fc46  mov     rbx, [rsp+50h+arg_0]
0x18005fc4b  mov     rdi, [rsp+50h+arg_18]
0x18005fc50  add     rsp, 50h
0x18005fc54  pop     rbp
0x18005fc55  retn
```
