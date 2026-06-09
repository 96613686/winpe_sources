# HrCopyStreamCB

- ea: `0x18000ee10`
- end: `0x18000ef43`
- name: `HrCopyStreamCB`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ee10`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrCopyStreamCB(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  unsigned int v6; // ebx
  int v9; // ecx
  __int64 v10; // r8
  unsigned int v11; // edx
  unsigned int v13; // [rsp+30h] [rbp-1058h] BYREF
  _DWORD v14[3]; // [rsp+34h] [rbp-1054h] BYREF
  _BYTE v15[4096]; // [rsp+40h] [rbp-1048h] BYREF

  v13 = 0;
  v6 = a3;
  v14[0] = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a1 || !a2 || HIDWORD(a3) && a3 != -1 )
    return 2147942487LL;
  v9 = 0;
  if ( (_DWORD)a3 )
  {
    do
    {
      v10 = v6;
      if ( v6 > 0x1000 )
        v10 = 4096;
      v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, unsigned int *))(*(_QWORD *)a1 + 24LL))(
             a1,
             v15,
             v10,
             &v13);
      if ( v9 < 0 )
        break;
      if ( !v13 )
        break;
      v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _DWORD *))(*(_QWORD *)a2 + 32LL))(a2, v15, v13, v14);
      if ( v9 < 0 )
        break;
      v11 = v13;
      if ( a4 )
        *(_DWORD *)a4 += v13;
      if ( a5 )
        *(_DWORD *)a5 += v14[0];
      v6 -= v11;
    }
    while ( v6 );
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ee10  push    rbx
0x18000ee12  push    rsi
0x18000ee13  push    rdi
0x18000ee14  push    r12
0x18000ee16  push    r14
0x18000ee18  push    r15
0x18000ee1a  mov     eax, 1058h
0x18000ee1f  call    _alloca_probe
0x18000ee24  sub     rsp, rax
0x18000ee27  mov     rax, cs:__security_cookie
0x18000ee2e  xor     rax, rsp
0x18000ee31  mov     [rsp+1088h+var_48], rax
0x18000ee39  mov     rdi, [rsp+1088h+arg_20]
0x18000ee41  mov     rax, r8
0x18000ee44  shr     rax, 20h
0x18000ee48  mov     rsi, r9
0x18000ee4b  mov     [rsp+1088h+var_1058], 0
0x18000ee53  mov     rbx, r8
0x18000ee56  mov     [rsp+1088h+var_1054], 0
0x18000ee5e  mov     r14, rdx
0x18000ee61  mov     r15, rcx
0x18000ee64  test    r9, r9
0x18000ee67  jz      short loc_18000EE70
0x18000ee69  mov     qword ptr [r9], 0
0x18000ee70  test    rdi, rdi
0x18000ee73  jz      short loc_18000EE7C
0x18000ee75  mov     qword ptr [rdi], 0
0x18000ee7c  test    r15, r15
0x18000ee7f  jz      loc_18000EF1D
0x18000ee85  test    r14, r14
0x18000ee88  jz      loc_18000EF1D
0x18000ee8e  test    eax, eax
0x18000ee90  jz      short loc_18000EEA1
0x18000ee92  or      ecx, 0FFFFFFFFh
0x18000ee95  cmp     eax, ecx
0x18000ee97  jnz     loc_18000EF1D
0x18000ee9d  cmp     ebx, ecx
0x18000ee9f  jnz     short loc_18000EF1D
0x18000eea1  xor     ecx, ecx
0x18000eea3  test    ebx, ebx
0x18000eea5  jz      short loc_18000EF19
0x18000eea7  mov     r12d, 1000h
0x18000eead  mov     rax, [r15]
0x18000eeb0  lea     r9, [rsp+1088h+var_1058]
0x18000eeb5  mov     r8d, ebx
0x18000eeb8  lea     rdx, [rsp+1088h+var_1048]
0x18000eebd  cmp     ebx, r12d
0x18000eec0  mov     rcx, r15
0x18000eec3  mov     rax, [rax+18h]
0x18000eec7  cmova   r8d, r12d
0x18000eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed0  mov     ecx, eax
0x18000eed2  test    eax, eax
0x18000eed4  js      short loc_18000EF19
0x18000eed6  mov     r8d, [rsp+1088h+var_1058]
0x18000eedb  test    r8d, r8d
0x18000eede  jz      short loc_18000EF19
0x18000eee0  mov     rax, [r14]
0x18000eee3  lea     r9, [rsp+1088h+var_1054]
0x18000eee8  lea     rdx, [rsp+1088h+var_1048]
0x18000eeed  mov     rcx, r14
0x18000eef0  mov     rax, [rax+20h]
0x18000eef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef9  mov     ecx, eax
0x18000eefb  test    eax, eax
0x18000eefd  js      short loc_18000EF19
0x18000eeff  mov     edx, [rsp+1088h+var_1058]
0x18000ef03  test    rsi, rsi
0x18000ef06  jz      short loc_18000EF0A
0x18000ef08  add     [rsi], edx
0x18000ef0a  test    rdi, rdi
0x18000ef0d  jz      short loc_18000EF15
0x18000ef0f  mov     eax, [rsp+1088h+var_1054]
0x18000ef13  add     [rdi], eax
0x18000ef15  sub     ebx, edx
0x18000ef17  jnz     short loc_18000EEAD
0x18000ef19  mov     eax, ecx
0x18000ef1b  jmp     short loc_18000EF22
0x18000ef1d  mov     eax, 80070057h
0x18000ef22  mov     rcx, [rsp+1088h+var_48]
0x18000ef2a  xor     rcx, rsp; StackCookie
0x18000ef2d  call    __security_check_cookie
0x18000ef32  add     rsp, 1058h
0x18000ef39  pop     r15
0x18000ef3b  pop     r14
0x18000ef3d  pop     r12
0x18000ef3f  pop     rdi
0x18000ef40  pop     rsi
0x18000ef41  pop     rbx
0x18000ef42  retn
```
