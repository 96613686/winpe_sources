# CFileStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x18000e4e0`
- end: `0x18000e609`
- name: `?CopyTo@CFileStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `297`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4e0`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CFileStream::CopyTo(
        CFileStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  DWORD v5; // r12d
  DWORD v6; // ebp
  DWORD LowPart; // ebx
  DWORD v10; // esi
  __int64 v11; // r8
  int v12; // ecx
  DWORD v13; // edi
  DWORD v15; // [rsp+30h] [rbp-1068h] BYREF
  struct IStream *v16; // [rsp+38h] [rbp-1060h]
  _BYTE v17[4096]; // [rsp+40h] [rbp-1058h] BYREF

  v5 = 0;
  v6 = 0;
  v16 = a2;
  LowPart = a3.LowPart;
  v10 = 4096;
  if ( a3.HighPart )
  {
    LowPart = -1;
  }
  else if ( a3.LowPart <= 0x1000 )
  {
    v12 = 0;
    v10 = a3.LowPart;
    goto LABEL_11;
  }
  do
  {
    v15 = LowPart;
    v11 = LowPart;
    if ( LowPart > v10 )
    {
      v11 = v10;
      v15 = v10;
    }
    v12 = (*(__int64 (__fastcall **)(CFileStream *, _BYTE *, __int64, DWORD *))(*(_QWORD *)this + 24LL))(
            this,
            v17,
            v11,
            &v15);
    if ( v12 < 0 )
      break;
    v13 = v15;
    if ( !v15 )
      break;
    v5 += v15;
    LowPart -= v15;
    do
    {
      if ( !v13 )
        break;
      v12 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, _QWORD, DWORD *))v16->lpVtbl->Write)(
              v16,
              v17,
              v13,
              &v15);
      if ( v12 < 0 )
        goto LABEL_12;
      v6 += v15;
      v13 -= v15;
    }
    while ( v15 );
LABEL_11:
    ;
  }
  while ( LowPart );
LABEL_12:
  if ( a4 )
  {
    a4->HighPart = 0;
    a4->LowPart = v5;
  }
  if ( a5 )
  {
    a5->HighPart = 0;
    a5->LowPart = v6;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e4e0  push    rbx
0x18000e4e2  push    rbp
0x18000e4e3  push    rsi
0x18000e4e4  push    rdi
0x18000e4e5  push    r12
0x18000e4e7  push    r13
0x18000e4e9  push    r14
0x18000e4eb  push    r15
0x18000e4ed  mov     eax, 1058h
0x18000e4f2  call    _alloca_probe
0x18000e4f7  sub     rsp, rax
0x18000e4fa  mov     rax, cs:__security_cookie
0x18000e501  xor     rax, rsp
0x18000e504  mov     [rsp+1098h+var_58], rax
0x18000e50c  mov     r14, [rsp+1098h+arg_20]
0x18000e514  mov     rax, r8
0x18000e517  shr     rax, 20h
0x18000e51b  xor     r12d, r12d
0x18000e51e  xor     ebp, ebp
0x18000e520  mov     [rsp+1098h+var_1060], rdx
0x18000e525  mov     r15, r9
0x18000e528  mov     rbx, r8
0x18000e52b  mov     r13, rcx
0x18000e52e  mov     esi, 1000h
0x18000e533  test    eax, eax
0x18000e535  jz      loc_18000E5FB
0x18000e53b  or      ebx, 0FFFFFFFFh
0x18000e53e  mov     [rsp+1098h+var_1068], ebx
0x18000e542  mov     r8d, ebx
0x18000e545  cmp     ebx, esi
0x18000e547  jbe     short loc_18000E550
0x18000e549  mov     r8d, esi
0x18000e54c  mov     [rsp+1098h+var_1068], esi
0x18000e550  mov     rax, [r13+0]
0x18000e554  lea     r9, [rsp+1098h+var_1068]
0x18000e559  lea     rdx, [rsp+1098h+var_1058]
0x18000e55e  mov     rcx, r13
0x18000e561  mov     rax, [rax+18h]
0x18000e565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e56a  mov     ecx, eax
0x18000e56c  test    eax, eax
0x18000e56e  js      short loc_18000E5B5
0x18000e570  mov     edi, [rsp+1098h+var_1068]
0x18000e574  test    edi, edi
0x18000e576  jz      short loc_18000E5B5
0x18000e578  add     r12d, edi
0x18000e57b  sub     ebx, edi
0x18000e57d  test    edi, edi
0x18000e57f  jz      short loc_18000E5B1
0x18000e581  mov     rcx, [rsp+1098h+var_1060]
0x18000e586  lea     r9, [rsp+1098h+var_1068]
0x18000e58b  mov     r8d, edi
0x18000e58e  lea     rdx, [rsp+1098h+var_1058]
0x18000e593  mov     rax, [rcx]
0x18000e596  mov     rax, [rax+20h]
0x18000e59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e59f  mov     ecx, eax
0x18000e5a1  test    eax, eax
0x18000e5a3  js      short loc_18000E5B5
0x18000e5a5  mov     eax, [rsp+1098h+var_1068]
0x18000e5a9  add     ebp, eax
0x18000e5ab  sub     edi, eax
0x18000e5ad  test    eax, eax
0x18000e5af  jnz     short loc_18000E57D
0x18000e5b1  test    ebx, ebx
0x18000e5b3  jnz     short loc_18000E53E
0x18000e5b5  test    r15, r15
0x18000e5b8  jz      short loc_18000E5C5
0x18000e5ba  mov     dword ptr [r15+4], 0
0x18000e5c2  mov     [r15], r12d
0x18000e5c5  test    r14, r14
0x18000e5c8  jz      short loc_18000E5D5
0x18000e5ca  mov     dword ptr [r14+4], 0
0x18000e5d2  mov     [r14], ebp
0x18000e5d5  mov     eax, ecx
0x18000e5d7  mov     rcx, [rsp+1098h+var_58]
0x18000e5df  xor     rcx, rsp; StackCookie
0x18000e5e2  call    __security_check_cookie
0x18000e5e7  add     rsp, 1058h
0x18000e5ee  pop     r15
0x18000e5f0  pop     r14
0x18000e5f2  pop     r13
0x18000e5f4  pop     r12
0x18000e5f6  pop     rdi
0x18000e5f7  pop     rsi
0x18000e5f8  pop     rbp
0x18000e5f9  pop     rbx
0x18000e5fa  retn
0x18000e5fb  cmp     ebx, esi
0x18000e5fd  ja      loc_18000E53E
0x18000e603  xor     ecx, ecx
0x18000e605  mov     esi, ebx
0x18000e607  jmp     short loc_18000E5B1
```
