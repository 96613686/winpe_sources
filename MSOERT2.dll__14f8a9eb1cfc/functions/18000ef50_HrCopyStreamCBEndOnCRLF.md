# HrCopyStreamCBEndOnCRLF

- ea: `0x18000ef50`
- end: `0x18000f0ab`
- name: `HrCopyStreamCBEndOnCRLF`
- size: `347`
- prototype: `__int64 __fastcall(__int64, __int64, int, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ef50`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrCopyStreamCBEndOnCRLF(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  int v5; // r10d
  int v6; // r9d
  int v8; // edi
  unsigned int v11; // ebx
  _DWORD v13[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = 0;
  v6 = 0;
  v13[0] = 0;
  v8 = 0;
  do
  {
    v11 = a3 - v8;
    if ( (unsigned int)(a3 - v8) < 0x1000 )
    {
      if ( !v11 )
        break;
    }
    else
    {
      v11 = 4096;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _DWORD *))(*(_QWORD *)a1 + 24LL))(a1, v14, v11, v13);
    if ( v5 < 0 )
      goto LABEL_15;
    if ( !v13[0] )
      goto LABEL_15;
    v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, v14, v13[0], 0);
    if ( v5 < 0 )
      goto LABEL_15;
    v6 = v13[0];
    v8 += v13[0];
  }
  while ( v13[0] == v11 );
  if ( (unsigned int)(v6 - 1) <= 0xFFE && v14[v6] != 10 )
  {
    do
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, _DWORD *))(*(_QWORD *)a1 + 24LL))(a1, v14, 1, v13);
      if ( v5 < 0 )
        break;
      if ( !v13[0] )
        break;
      v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, v14, 1, 0);
      if ( v5 < 0 )
        break;
      ++v8;
    }
    while ( v14[0] != 10 );
  }
LABEL_15:
  if ( a4 )
    *a4 = v8;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ef50  push    rbp
0x18000ef52  push    rbx
0x18000ef53  push    rsi
0x18000ef54  push    rdi
0x18000ef55  push    r12
0x18000ef57  push    r14
0x18000ef59  push    r15
0x18000ef5b  lea     rbp, [rsp-0F50h]
0x18000ef63  mov     eax, 1050h
0x18000ef68  call    _alloca_probe
0x18000ef6d  sub     rsp, rax
0x18000ef70  mov     rax, cs:__security_cookie
0x18000ef77  xor     rax, rsp
0x18000ef7a  mov     [rbp+0F80h+var_40], rax
0x18000ef81  mov     rsi, r9
0x18000ef84  xor     r10d, r10d
0x18000ef87  xor     r9d, r9d
0x18000ef8a  mov     r12d, r8d
0x18000ef8d  mov     [rsp+1080h+var_1050], r9d
0x18000ef92  xor     edi, edi
0x18000ef94  mov     r15, rdx
0x18000ef97  mov     r14, rcx
0x18000ef9a  mov     ebx, r12d
0x18000ef9d  sub     ebx, edi
0x18000ef9f  cmp     ebx, 1000h
0x18000efa5  jb      short loc_18000EFAE
0x18000efa7  mov     ebx, 1000h
0x18000efac  jmp     short loc_18000EFB2
0x18000efae  test    ebx, ebx
0x18000efb0  jz      short loc_18000F012
0x18000efb2  mov     rax, [r14]
0x18000efb5  lea     r9, [rsp+1080h+var_1050]
0x18000efba  mov     r8d, ebx
0x18000efbd  lea     rdx, [rsp+1080h+var_1040]
0x18000efc2  mov     rcx, r14
0x18000efc5  mov     rax, [rax+18h]
0x18000efc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efce  mov     r10d, eax
0x18000efd1  test    eax, eax
0x18000efd3  js      loc_18000F080
0x18000efd9  mov     r8d, [rsp+1080h+var_1050]
0x18000efde  test    r8d, r8d
0x18000efe1  jz      loc_18000F080
0x18000efe7  mov     rax, [r15]
0x18000efea  lea     rdx, [rsp+1080h+var_1040]
0x18000efef  xor     r9d, r9d
0x18000eff2  mov     rcx, r15
0x18000eff5  mov     rax, [rax+20h]
0x18000eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000effe  mov     r10d, eax
0x18000f001  test    eax, eax
0x18000f003  js      short loc_18000F080
0x18000f005  mov     r9d, [rsp+1080h+var_1050]
0x18000f00a  add     edi, r9d
0x18000f00d  cmp     r9d, ebx
0x18000f010  jz      short loc_18000EF9A
0x18000f012  lea     eax, [r9-1]
0x18000f016  cmp     eax, 0FFEh
0x18000f01b  ja      short loc_18000F080
0x18000f01d  mov     eax, r9d
0x18000f020  cmp     [rsp+rax+1080h+var_1040], 0Ah
0x18000f025  jz      short loc_18000F080
0x18000f027  mov     ebx, 1
0x18000f02c  mov     rax, [r14]
0x18000f02f  lea     r9, [rsp+1080h+var_1050]
0x18000f034  mov     r8d, ebx
0x18000f037  lea     rdx, [rsp+1080h+var_1040]
0x18000f03c  mov     rcx, r14
0x18000f03f  mov     rax, [rax+18h]
0x18000f043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f048  mov     r10d, eax
0x18000f04b  test    eax, eax
0x18000f04d  js      short loc_18000F080
0x18000f04f  cmp     [rsp+1080h+var_1050], 0
0x18000f054  jz      short loc_18000F080
0x18000f056  mov     rax, [r15]
0x18000f059  lea     rdx, [rsp+1080h+var_1040]
0x18000f05e  xor     r9d, r9d
0x18000f061  mov     r8d, ebx
0x18000f064  mov     rcx, r15
0x18000f067  mov     rax, [rax+20h]
0x18000f06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f070  mov     r10d, eax
0x18000f073  test    eax, eax
0x18000f075  js      short loc_18000F080
0x18000f077  add     edi, ebx
0x18000f079  cmp     [rsp+1080h+var_1040], 0Ah
0x18000f07e  jnz     short loc_18000F02C
0x18000f080  test    rsi, rsi
0x18000f083  jz      short loc_18000F087
0x18000f085  mov     [rsi], edi
0x18000f087  mov     eax, r10d
0x18000f08a  mov     rcx, [rbp+0F80h+var_40]
0x18000f091  xor     rcx, rsp; StackCookie
0x18000f094  call    __security_check_cookie
0x18000f099  add     rsp, 1050h
0x18000f0a0  pop     r15
0x18000f0a2  pop     r14
0x18000f0a4  pop     r12
0x18000f0a6  pop     rdi
0x18000f0a7  pop     rsi
0x18000f0a8  pop     rbx
0x18000f0a9  pop     rbp
0x18000f0aa  retn
```
