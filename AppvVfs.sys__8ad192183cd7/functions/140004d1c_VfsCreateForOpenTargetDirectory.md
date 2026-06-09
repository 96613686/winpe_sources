# VfsCreateForOpenTargetDirectory

- ea: `0x140004d1c`
- end: `0x140005024`
- name: `VfsCreateForOpenTargetDirectory`
- size: `776`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140003c00`

## callees

- `0x140004d1c`
- `0x14000e438`
- `0x14000eb14`
- `0x1400112f4`

## pseudocode

```c
__int64 __fastcall VfsCreateForOpenTargetDirectory(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _DWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  unsigned int v7; // eax
  __int64 result; // rax
  int v9; // r8d
  __int64 v10; // rcx
  void *v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rcx
  __int16 v14; // cx
  int v15; // edx
  unsigned __int16 v16; // ax
  __int16 v17; // ax
  __int64 v18; // rcx
  __int16 v19; // cx
  __int16 v20; // ax
  __int64 v21; // rcx
  __int16 v22; // cx
  struct _FLT_INSTANCE *v23; // r8
  __int64 v24[2]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v25[2]; // [rsp+90h] [rbp+27h] BYREF
  __int64 v26; // [rsp+D0h] [rbp+67h] BYREF

  *a3 = 0;
  Iopb = CallbackData->Iopb;
  *(_OWORD *)v24 = 0;
  *(_OWORD *)v25 = 0;
  v7 = Iopb->Parameters.Create.Options & 0xFF000000;
  LOBYTE(v26) = 0;
  if ( v7 != 0x1000000 )
    return 3221225485LL;
  if ( (*(_DWORD *)(a2 + 76) & 2) != 0 )
  {
    *a3 = 1;
    return 0;
  }
  v9 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  if ( (v9 & 0xD0156) != 0 )
  {
    v10 = *(_QWORD *)(a2 + 16);
    v11 = *(_DWORD *)(a2 + 72) == 1 ? *(void **)(v10 + 72) : *(void **)(v10 + 88);
    result = VfsAccessCheck(v11, (__int64)CallbackData, v9, 0);
    if ( (int)result < 0 )
      return result;
  }
  if ( (*(_DWORD *)(a2 + 76) & 0x10) == 0 )
  {
    *(_OWORD *)v24 = *(_OWORD *)(a2 + 32);
    v12 = (unsigned __int16)_mm_cvtsi128_si32(*(__m128i *)v24) >> 1;
    if ( v12 )
    {
      v13 = (unsigned __int16)(v12 - 1);
      if ( *(_WORD *)(v24[1] + 2 * v13) != 92 )
        goto LABEL_15;
      if ( (unsigned __int16)v13 > 1u )
      {
        LOWORD(v13) = v12 - 2;
LABEL_15:
        if ( (_WORD)v13 )
        {
          while ( *(_WORD *)(v24[1] + 2LL * (unsigned __int16)v13) != 92 )
          {
            LOWORD(v13) = v13 - 1;
            if ( !(_WORD)v13 )
              goto LABEL_21;
          }
          v14 = v13 + 1;
          if ( v14 )
            LOWORD(v24[0]) = 2 * v14;
        }
      }
    }
LABEL_21:
    result = VfsCreateShadow(
               CallbackData,
               1,
               0,
               0,
               *(PFLT_INSTANCE *)(a2 + 48),
               *(PFLT_INSTANCE *)(a2 + 24),
               (__int64)v24,
               1,
               1,
               0,
               1,
               1,
               *(_QWORD *)a2,
               *(_QWORD *)(a2 + 8),
               *(_QWORD *)(a2 + 16),
               &v26);
    if ( (int)result < 0 )
      return result;
    if ( (_BYTE)v26 )
      *(_DWORD *)(a2 + 76) |= 0x10u;
  }
  if ( (*(_DWORD *)(a2 + 76) & 0x10) == 0 )
  {
LABEL_50:
    *((_DWORD *)CallbackData->Iopb->TargetFileObject->FsContext2 + 32) = *(_DWORD *)(a2 + 76);
    VfsUpdateOpenTargetDirectoryFileName(CallbackData->Iopb->TargetFileObject);
    CallbackData->IoStatus.Information = 1;
    CallbackData->IoStatus.Status = 0;
    *a3 = 3;
    return 0;
  }
  v15 = *(_DWORD *)(a2 + 76) & 8;
  if ( v15 )
  {
    v16 = _mm_cvtsi128_si32(*(__m128i *)(a2 + 32));
    *(_OWORD *)v24 = *(_OWORD *)(a2 + 32);
    v17 = v16 >> 1;
    if ( v17 )
    {
      v18 = (unsigned __int16)(v17 - 1);
      if ( *(_WORD *)(v24[1] + 2 * v18) == 92 )
      {
        if ( (unsigned __int16)v18 <= 1u )
          goto LABEL_36;
        LOWORD(v18) = v17 - 2;
      }
      if ( (_WORD)v18 )
      {
        while ( *(_WORD *)(v24[1] + 2LL * (unsigned __int16)v18) != 92 )
        {
          LOWORD(v18) = v18 - 1;
          if ( !(_WORD)v18 )
            goto LABEL_36;
        }
        v19 = v18 + 1;
        if ( v19 )
          LOWORD(v24[0]) = 2 * v19;
      }
    }
  }
LABEL_36:
  *(_OWORD *)v25 = *(_OWORD *)(a2 + 56);
  v20 = (unsigned __int16)_mm_cvtsi128_si32(*(__m128i *)v25) >> 1;
  if ( !v20 )
    goto LABEL_46;
  v21 = (unsigned __int16)(v20 - 1);
  if ( *(_WORD *)(v25[1] + 2 * v21) == 92 )
  {
    if ( (unsigned __int16)v21 <= 1u )
      goto LABEL_46;
    LOWORD(v21) = v20 - 2;
  }
  if ( (_WORD)v21 )
  {
    while ( *(_WORD *)(v25[1] + 2LL * (unsigned __int16)v21) != 92 )
    {
      LOWORD(v21) = v21 - 1;
      if ( !(_WORD)v21 )
        goto LABEL_46;
    }
    v22 = v21 + 1;
    if ( v22 )
      LOWORD(v25[0]) = 2 * v22;
  }
LABEL_46:
  if ( v15 )
    v23 = *(struct _FLT_INSTANCE **)(a2 + 24);
  else
    v23 = 0;
  result = VfsCreateShadow(
             CallbackData,
             1,
             v23,
             (struct _FLT_INSTANCE *)((unsigned __int64)v24 & -(__int64)(v15 != 0)),
             0,
             *(PFLT_INSTANCE *)(a2 + 48),
             (__int64)v25,
             0,
             v15 != 0,
             0,
             1,
             0,
             *(_QWORD *)a2,
             *(_QWORD *)(a2 + 8),
             *(_QWORD *)(a2 + 16),
             &v26);
  if ( (int)result >= 0 )
    goto LABEL_50;
  return result;
}

```

## disassembly

```asm
0x140004d1c  mov     [rsp-8+arg_8], rbx
0x140004d21  mov     [rsp-8+arg_10], rsi
0x140004d26  push    rbp
0x140004d27  push    rdi
0x140004d28  push    r12
0x140004d2a  push    r14
0x140004d2c  push    r15
0x140004d2e  lea     rbp, [rsp-37h]
0x140004d33  sub     rsp, 0A0h
0x140004d3a  xor     r15d, r15d
0x140004d3d  mov     rdi, rdx
0x140004d40  mov     [r8], r15d
0x140004d43  xorps   xmm0, xmm0
0x140004d46  mov     rdx, [rcx+10h]
0x140004d4a  xorps   xmm1, xmm1
0x140004d4d  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x140004d51  mov     r14, r8
0x140004d54  mov     rsi, rcx
0x140004d57  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x140004d5b  mov     eax, [rdx+20h]
0x140004d5e  and     eax, 0FF000000h
0x140004d63  mov     byte ptr [rbp+57h+arg_0], r15b
0x140004d67  cmp     eax, 1000000h
0x140004d6c  jz      short loc_140004D78
0x140004d6e  mov     eax, 0C000000Dh
0x140004d73  jmp     loc_140005007
0x140004d78  mov     eax, [rdi+4Ch]
0x140004d7b  test    al, 2
0x140004d7d  jz      short loc_140004D8B
0x140004d7f  mov     dword ptr [r8], 1
0x140004d86  jmp     loc_140005005
0x140004d8b  mov     rax, [rdx+18h]
0x140004d8f  mov     ebx, 1
0x140004d94  mov     r8d, [rax+10h]
0x140004d98  test    r8d, 0D0156h
0x140004d9f  jz      short loc_140004DC7
0x140004da1  mov     rcx, [rdi+10h]
0x140004da5  cmp     [rdi+48h], ebx
0x140004da8  jnz     short loc_140004DB0
0x140004daa  mov     rcx, [rcx+48h]
0x140004dae  jmp     short loc_140004DB4
0x140004db0  mov     rcx, [rcx+58h]; SecurityDescriptor
0x140004db4  xor     r9d, r9d
0x140004db7  mov     rdx, rsi
0x140004dba  call    VfsAccessCheck
0x140004dbf  test    eax, eax
0x140004dc1  js      loc_140005007
0x140004dc7  mov     eax, [rdi+4Ch]
0x140004dca  mov     r12d, 0FFFFh
0x140004dd0  test    al, 10h
0x140004dd2  jnz     loc_140004E9E
0x140004dd8  movups  xmm0, xmmword ptr [rdi+20h]
0x140004ddc  movd    eax, xmm0
0x140004de0  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x140004de4  shr     ax, 1
0x140004de7  jz      short loc_140004E29
0x140004de9  mov     rdx, [rbp+57h+var_40+8]
0x140004ded  sub     ax, bx
0x140004df0  movzx   ecx, ax
0x140004df3  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x140004df8  jnz     short loc_140004E03
0x140004dfa  cmp     cx, bx
0x140004dfd  jbe     short loc_140004E29
0x140004dff  add     cx, r12w
0x140004e03  test    cx, cx
0x140004e06  jz      short loc_140004E29
0x140004e08  movzx   eax, cx
0x140004e0b  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x140004e10  jz      short loc_140004E1A
0x140004e12  add     cx, r12w
0x140004e16  jnz     short loc_140004E08
0x140004e18  jmp     short loc_140004E29
0x140004e1a  add     cx, bx
0x140004e1d  test    cx, cx
0x140004e20  jz      short loc_140004E29
0x140004e22  add     cx, cx
0x140004e25  mov     word ptr [rbp+57h+var_40], cx
0x140004e29  lea     rax, [rbp+57h+arg_0]
0x140004e2d  xor     r9d, r9d
0x140004e30  mov     [rsp+0C0h+var_48], rax; __int64
0x140004e35  xor     r8d, r8d
0x140004e38  mov     rax, [rdi+10h]
0x140004e3c  mov     edx, ebx
0x140004e3e  mov     [rsp+0C0h+var_50], rax; __int64
0x140004e43  mov     rcx, rsi; CallbackData
0x140004e46  mov     rax, [rdi+8]
0x140004e4a  mov     [rsp+0C0h+var_58], rax; __int64
0x140004e4f  mov     rax, [rdi]
0x140004e52  mov     [rsp+0C0h+var_60], rax; __int64
0x140004e57  lea     rax, [rbp+57h+var_40]
0x140004e5b  mov     [rsp+0C0h+var_68], bl; char
0x140004e5f  mov     [rsp+0C0h+var_70], bl; char
0x140004e63  mov     [rsp+0C0h+var_78], r15b; char
0x140004e68  mov     [rsp+0C0h+var_80], bl; char
0x140004e6c  mov     [rsp+0C0h+var_88], bl; char
0x140004e70  mov     [rsp+0C0h+var_90], rax; __int64
0x140004e75  mov     rax, [rdi+18h]
0x140004e79  mov     [rsp+0C0h+TargetInstance], rax; TargetInstance
0x140004e7e  mov     rax, [rdi+30h]
0x140004e82  mov     [rsp+0C0h+var_A0], rax; PFLT_INSTANCE
0x140004e87  call    VfsCreateShadow
0x140004e8c  test    eax, eax
0x140004e8e  js      loc_140005007
0x140004e94  cmp     byte ptr [rbp+57h+arg_0], r15b
0x140004e98  jz      short loc_140004E9E
0x140004e9a  or      dword ptr [rdi+4Ch], 10h
0x140004e9e  mov     edx, [rdi+4Ch]
0x140004ea1  test    dl, 10h
0x140004ea4  jz      loc_140004FD4
0x140004eaa  and     edx, 8
0x140004ead  jz      short loc_140004F02
0x140004eaf  movups  xmm0, xmmword ptr [rdi+20h]
0x140004eb3  movd    eax, xmm0
0x140004eb7  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x140004ebb  shr     ax, 1
0x140004ebe  jz      short loc_140004F02
0x140004ec0  mov     r8, [rbp+57h+var_40+8]
0x140004ec4  sub     ax, bx
0x140004ec7  movzx   ecx, ax
0x140004eca  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x140004ed0  jnz     short loc_140004EDB
0x140004ed2  cmp     cx, bx
0x140004ed5  jbe     short loc_140004F02
0x140004ed7  add     cx, r12w
0x140004edb  test    cx, cx
0x140004ede  jz      short loc_140004F02
0x140004ee0  movzx   eax, cx
0x140004ee3  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140004ee9  jz      short loc_140004EF3
0x140004eeb  add     cx, r12w
0x140004eef  jnz     short loc_140004EE0
0x140004ef1  jmp     short loc_140004F02
0x140004ef3  add     cx, bx
0x140004ef6  test    cx, cx
0x140004ef9  jz      short loc_140004F02
0x140004efb  add     cx, cx
0x140004efe  mov     word ptr [rbp+57h+var_40], cx
0x140004f02  movups  xmm0, xmmword ptr [rdi+38h]
0x140004f06  movd    eax, xmm0
0x140004f0a  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x140004f0e  shr     ax, 1
0x140004f11  jz      short loc_140004F55
0x140004f13  mov     r8, [rbp+57h+var_30+8]
0x140004f17  sub     ax, bx
0x140004f1a  movzx   ecx, ax
0x140004f1d  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x140004f23  jnz     short loc_140004F2E
0x140004f25  cmp     cx, bx
0x140004f28  jbe     short loc_140004F55
0x140004f2a  add     cx, r12w
0x140004f2e  test    cx, cx
0x140004f31  jz      short loc_140004F55
0x140004f33  movzx   eax, cx
0x140004f36  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140004f3c  jz      short loc_140004F46
0x140004f3e  add     cx, r12w
0x140004f42  jnz     short loc_140004F33
0x140004f44  jmp     short loc_140004F55
0x140004f46  add     cx, bx
0x140004f49  test    cx, cx
0x140004f4c  jz      short loc_140004F55
0x140004f4e  add     cx, cx
0x140004f51  mov     word ptr [rbp+57h+var_30], cx
0x140004f55  mov     eax, edx
0x140004f57  neg     eax
0x140004f59  lea     rax, [rbp+57h+var_40]
0x140004f5d  sbb     r9, r9
0x140004f60  and     r9, rax
0x140004f63  test    edx, edx
0x140004f65  jz      short loc_140004F6D
0x140004f67  mov     r8, [rdi+18h]
0x140004f6b  jmp     short loc_140004F70
0x140004f6d  mov     r8, r15
0x140004f70  test    edx, edx
0x140004f72  lea     rax, [rbp+57h+arg_0]
0x140004f76  mov     [rsp+0C0h+var_48], rax; __int64
0x140004f7b  mov     edx, ebx
0x140004f7d  mov     rax, [rdi+10h]
0x140004f81  setnz   cl
0x140004f84  mov     [rsp+0C0h+var_50], rax; __int64
0x140004f89  mov     rax, [rdi+8]
0x140004f8d  mov     [rsp+0C0h+var_58], rax; __int64
0x140004f92  mov     rax, [rdi]
0x140004f95  mov     [rsp+0C0h+var_60], rax; __int64
0x140004f9a  lea     rax, [rbp+57h+var_30]
0x140004f9e  mov     [rsp+0C0h+var_68], r15b; char
0x140004fa3  mov     [rsp+0C0h+var_70], bl; char
0x140004fa7  mov     [rsp+0C0h+var_78], r15b; char
0x140004fac  mov     [rsp+0C0h+var_80], cl; char
0x140004fb0  mov     rcx, rsi; CallbackData
0x140004fb3  mov     [rsp+0C0h+var_88], r15b; char
0x140004fb8  mov     [rsp+0C0h+var_90], rax; __int64
0x140004fbd  mov     rax, [rdi+30h]
0x140004fc1  mov     [rsp+0C0h+TargetInstance], rax; TargetInstance
0x140004fc6  mov     [rsp+0C0h+var_A0], r15; PFLT_INSTANCE
0x140004fcb  call    VfsCreateShadow
0x140004fd0  test    eax, eax
0x140004fd2  js      short loc_140005007
0x140004fd4  mov     rax, [rsi+10h]
0x140004fd8  mov     rcx, [rax+8]
0x140004fdc  mov     eax, [rdi+4Ch]
0x140004fdf  mov     rdx, [rcx+20h]
0x140004fe3  mov     [rdx+80h], eax
0x140004fe9  mov     rcx, [rsi+10h]
0x140004fed  mov     rcx, [rcx+8]
0x140004ff1  call    VfsUpdateOpenTargetDirectoryFileName
0x140004ff6  mov     [rsi+20h], rbx
0x140004ffa  mov     [rsi+18h], r15d
0x140004ffe  mov     dword ptr [r14], 3
0x140005005  xor     eax, eax
0x140005007  lea     r11, [rsp+0C0h+var_20]
0x14000500f  mov     rbx, [r11+38h]
0x140005013  mov     rsi, [r11+40h]
0x140005017  mov     rsp, r11
0x14000501a  pop     r15
0x14000501c  pop     r14
0x14000501e  pop     r12
0x140005020  pop     rdi
0x140005021  pop     rbp
0x140005022  retn
```
