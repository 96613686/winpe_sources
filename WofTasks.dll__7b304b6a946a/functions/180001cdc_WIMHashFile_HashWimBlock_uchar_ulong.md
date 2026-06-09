# WIMHashFile::HashWimBlock(uchar *,ulong)

- ea: `0x180001cdc`
- end: `0x180001e96`
- name: `?HashWimBlock@WIMHashFile@@AEAAJPEAEK@Z`
- size: `442`
- prototype: `__int64 __fastcall(WIMHashFile *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002474`

## callees

- `0x180001cdc`
- `0x180002a88`
- `0x1800051c0`

## import_xrefs

- `bcrypt!BCryptProcessMultiOperations` at `0x180001dd2`
- `bcrypt!BCryptProcessMultiOperations` at `0x180001e24`
- `bcrypt!BCryptProcessMultiOperations` at `0x180001dd2`
- `bcrypt!BCryptProcessMultiOperations` at `0x180001e24`

## pseudocode

```c
__int64 __fastcall WIMHashFile::HashWimBlock(WIMHashFile *this, unsigned __int8 *a2, unsigned int a3)
{
  unsigned int v3; // edi
  __int64 *v4; // r14
  __int64 *v5; // rbx
  unsigned int v7; // esi
  __int64 *v8; // r11
  unsigned int v9; // r9d
  unsigned int v10; // r10d
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // edx
  unsigned int v16; // edx
  __int64 v17; // rcx
  int v18; // eax
  _DWORD v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v21; // [rsp+38h] [rbp-C8h]
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+58h] [rbp-A8h]
  __int128 v24; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v25[128]; // [rsp+110h] [rbp+10h] BYREF

  v3 = a3;
  v4 = qword_18000D000;
  v5 = qword_18040D020;
  if ( a3 )
  {
    while ( 1 )
    {
      v7 = 4096;
      v8 = v4;
      if ( v3 < 0x1000 )
        v7 = v3;
      v9 = v7 >> 2;
      v10 = 0;
      do
      {
        if ( v10 == 3 )
          v9 = v7 - 3 * (v7 >> 2);
        v11 = 2 * v10;
        v12 = 3 * v11;
        v20[2 * v12] = v10;
        v13 = 3LL * (unsigned int)(v11 + 1);
        v22[v12 - 1] = v8;
        v14 = 32LL * v10;
        v20[2 * v13] = v10++;
        v20[2 * v12 + 1] = 1;
        LODWORD(v22[v12]) = v9;
        v20[2 * v13 + 1] = 2;
        v22[v13 - 1] = &v25[v14];
        v8 = (__int64 *)((char *)v8 + v9);
        LODWORD(v22[v13]) = 32;
      }
      while ( v10 < 4 );
      v15 = BCryptProcessMultiOperations(*((_QWORD *)this + 22), 1, v20);
      if ( v15 >= 0 )
      {
        v17 = *((_QWORD *)this + 22);
        v21 = v25;
        LODWORD(v22[0]) = 128;
        v22[2] = &v24;
        v23 = 32;
        v18 = BCryptProcessMultiOperations(v17, 1, v20);
        v16 = v18 | 0x10000000;
        if ( v18 >= 0 )
          v16 = 0;
      }
      else
      {
        v16 = v15 | 0x10000000;
      }
      if ( v16 )
        break;
      v4 = (__int64 *)((char *)v4 + v7);
      *(_OWORD *)v5 = v24;
      v5 += 2;
      v3 -= v7;
      if ( !v3 )
        return (unsigned int)File::Write(this, qword_18040D020, (unsigned int)v5 - (unsigned int)qword_18040D020);
    }
  }
  else
  {
    return (unsigned int)File::Write(this, qword_18040D020, (unsigned int)v5 - (unsigned int)qword_18040D020);
  }
  return v16;
}

```

## disassembly

```asm
0x180001cdc  mov     [rsp-8+arg_8], rbx
0x180001ce1  mov     [rsp-8+arg_10], rsi
0x180001ce6  push    rbp
0x180001ce7  push    rdi
0x180001ce8  push    r12
0x180001cea  push    r14
0x180001cec  push    r15
0x180001cee  lea     rbp, [rsp-0A0h]
0x180001cf6  sub     rsp, 1A0h
0x180001cfd  mov     rax, cs:__security_cookie
0x180001d04  xor     rax, rsp
0x180001d07  mov     [rbp+0C0h+var_30], rax
0x180001d0e  lea     r12, qword_18040D020
0x180001d15  mov     edi, r8d
0x180001d18  lea     r14, qword_18000D000
0x180001d1f  mov     rbx, r12
0x180001d22  mov     r15, rcx
0x180001d25  test    r8d, r8d
0x180001d28  jz      loc_180001E56
0x180001d2e  mov     esi, 1000h
0x180001d33  mov     r11, r14
0x180001d36  cmp     edi, esi
0x180001d38  cmovb   esi, edi
0x180001d3b  mov     r8d, esi
0x180001d3e  shr     r8d, 2
0x180001d42  mov     r9d, r8d
0x180001d45  xor     r10d, r10d
0x180001d48  cmp     r10d, 3
0x180001d4c  jnz     short loc_180001D58
0x180001d4e  lea     eax, [r8+r8*2]
0x180001d52  mov     r9d, esi
0x180001d55  sub     r9d, eax
0x180001d58  lea     edx, [r10+r10]
0x180001d5c  lea     rcx, [rdx+rdx*2]
0x180001d60  lea     eax, [rdx+1]
0x180001d63  mov     [rsp+rcx*8+1C0h+var_190], r10d
0x180001d68  lea     rdx, [rax+rax*2]
0x180001d6c  mov     [rsp+rcx*8+1C0h+var_188], r11
0x180001d71  mov     eax, r10d
0x180001d74  shl     rax, 5
0x180001d78  mov     [rsp+rdx*8+1C0h+var_190], r10d
0x180001d7d  inc     r10d
0x180001d80  mov     [rsp+rcx*8+1C0h+var_18C], 1
0x180001d88  mov     [rsp+rcx*8+1C0h+var_180], r9d
0x180001d8d  lea     rax, [rbp+rax+0C0h+var_B0]
0x180001d92  mov     [rsp+rdx*8+1C0h+var_18C], 2
0x180001d9a  mov     [rsp+rdx*8+1C0h+var_188], rax
0x180001d9f  mov     eax, r9d
0x180001da2  add     r11, rax
0x180001da5  mov     [rsp+rdx*8+1C0h+var_180], 20h ; ' '
0x180001dad  cmp     r10d, 4
0x180001db1  jb      short loc_180001D48
0x180001db3  mov     rcx, [r15+0B0h]
0x180001dba  lea     r8, [rsp+1C0h+var_190]
0x180001dbf  mov     r9d, 0C0h
0x180001dc5  mov     [rsp+1C0h+var_1A0], 0
0x180001dcd  mov     edx, 1
0x180001dd2  call    cs:__imp_BCryptProcessMultiOperations
0x180001dd8  mov     edx, eax
0x180001dda  test    eax, eax
0x180001ddc  jns     short loc_180001DE4
0x180001dde  bts     edx, 1Ch
0x180001de2  jmp     short loc_180001E39
0x180001de4  mov     rcx, [r15+0B0h]
0x180001deb  lea     rax, [rbp+0C0h+var_B0]
0x180001def  mov     r9d, 30h ; '0'
0x180001df5  mov     [rsp+1C0h+var_188], rax
0x180001dfa  lea     rax, [rbp+0C0h+var_D0]
0x180001dfe  mov     [rsp+1C0h+var_180], 80h
0x180001e06  lea     r8, [rsp+1C0h+var_190]
0x180001e0b  mov     [rsp+1C0h+var_170], rax
0x180001e10  mov     [rsp+1C0h+var_168], 20h ; ' '
0x180001e18  lea     edx, [r9-2Fh]
0x180001e1c  mov     [rsp+1C0h+var_1A0], 0
0x180001e24  call    cs:__imp_BCryptProcessMultiOperations
0x180001e2a  mov     edx, eax
0x180001e2c  mov     ecx, eax
0x180001e2e  bts     edx, 1Ch
0x180001e32  xor     eax, eax
0x180001e34  test    ecx, ecx
0x180001e36  cmovns  edx, eax
0x180001e39  test    edx, edx
0x180001e3b  jnz     short loc_180001E69
0x180001e3d  movups  xmm0, [rbp+0C0h+var_D0]
0x180001e41  mov     eax, esi
0x180001e43  add     r14, rax
0x180001e46  movdqu  xmmword ptr [rbx], xmm0
0x180001e4a  add     rbx, 10h
0x180001e4e  sub     edi, esi
0x180001e50  jnz     loc_180001D2E
0x180001e56  sub     ebx, r12d
0x180001e59  mov     rdx, r12; void *
0x180001e5c  mov     r8d, ebx; unsigned int
0x180001e5f  mov     rcx, r15; this
0x180001e62  call    ?Write@File@@QEAAJPEAXK@Z; File::Write(void *,ulong)
0x180001e67  mov     edx, eax
0x180001e69  mov     eax, edx
0x180001e6b  mov     rcx, [rbp+0C0h+var_30]
0x180001e72  xor     rcx, rsp; StackCookie
0x180001e75  call    __security_check_cookie
0x180001e7a  lea     r11, [rsp+1C0h+var_20]
0x180001e82  mov     rbx, [r11+38h]
0x180001e86  mov     rsi, [r11+40h]
0x180001e8a  mov     rsp, r11
0x180001e8d  pop     r15
0x180001e8f  pop     r14
0x180001e91  pop     r12
0x180001e93  pop     rdi
0x180001e94  pop     rbp
0x180001e95  retn
```
