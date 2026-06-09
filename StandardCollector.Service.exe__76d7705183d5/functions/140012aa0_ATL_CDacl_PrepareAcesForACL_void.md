# ATL::CDacl::PrepareAcesForACL(void)

- ea: `0x140012aa0`
- end: `0x140012d45`
- name: `?PrepareAcesForACL@CDacl@ATL@@EEBAXXZ`
- size: `677`
- prototype: `void __fastcall(ATL::CDacl *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140002e74`
- `0x140012aa0`
- `0x140014c70`

## pseudocode

```c
void __fastcall ATL::CDacl::PrepareAcesForACL(ATL::CDacl *this)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // r13
  _BYTE *v4; // rbx
  unsigned __int64 v5; // rax
  unsigned __int64 i; // rbp
  _BYTE *v7; // rsi
  unsigned __int64 v8; // rsi
  __int64 j; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _BYTE *v12; // r12
  char v13; // al
  __int64 v14; // rax
  _QWORD *v15; // r14
  _QWORD *v16; // r12
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  _BYTE *v19; // rsi
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  __int64 v21; // [rsp+20h] [rbp-48h]
  _BYTE v22[16]; // [rsp+30h] [rbp-38h] BYREF

  v2 = 1;
  v3 = *((_QWORD *)this + 4);
  v4 = 0;
  v5 = 4;
  if ( v3 <= 4 )
    goto LABEL_4;
  do
  {
    v2 = v5;
    v5 = 3 * v5 + 1;
  }
  while ( v5 < v3 );
  if ( v2 )
  {
LABEL_4:
    while ( 1 )
    {
      for ( i = v2 - 1; i < v3; ++i )
      {
        if ( i >= *((_QWORD *)this + 4) )
          goto LABEL_53;
        v7 = (_BYTE *)(*((_QWORD *)this + 3) + 8 * i);
        if ( v4 != *(_BYTE **)v7 )
        {
          if ( v4 )
            (**(void (__fastcall ***)(_BYTE *, __int64))v4)(v4, 1);
          v4 = *(_BYTE **)v7;
LABEL_12:
          *(_QWORD *)v7 = 0;
          goto LABEL_13;
        }
        if ( v22 != v7 )
          goto LABEL_12;
LABEL_13:
        v8 = i;
        if ( i < v2 )
          goto LABEL_39;
        for ( j = -(__int64)v2; ; j = -(__int64)v2 )
        {
          if ( v8 - v2 >= *((_QWORD *)this + 4) )
            goto LABEL_53;
          _mm_lfence();
          v10 = 8 * v8;
          v11 = 8 * v8 + 8 * j;
          v21 = v11;
          v12 = *(_BYTE **)(v11 + *((_QWORD *)this + 3));
          if ( (v12[132] & 0x10) != 0 )
          {
            if ( (v4[132] & 0x10) == 0 )
              goto LABEL_27;
          }
          else if ( (v4[132] & 0x10) != 0 )
          {
            goto LABEL_39;
          }
          v13 = v4[144];
          if ( !v12[144] )
            break;
          if ( v13 )
            goto LABEL_24;
LABEL_27:
          if ( v8 - v2 >= *((_QWORD *)this + 4) )
            goto LABEL_53;
          v14 = *((_QWORD *)this + 3);
          v15 = (_QWORD *)(v14 + v11);
          if ( v8 >= *((_QWORD *)this + 4) )
            goto LABEL_53;
          v16 = (_QWORD *)(v10 + v14);
          v17 = *(void (__fastcall ****)(_QWORD, __int64))(v10 + v14);
          if ( v17 == (void (__fastcall ***)(_QWORD, __int64))*v15 )
          {
            if ( v16 != v15 )
              *v15 = 0;
          }
          else
          {
            if ( v17 )
              (**v17)(v17, 1);
            *v16 = 0;
            v18 = (void (__fastcall ***)(_QWORD, __int64))*v15;
            *v15 = 0;
            *v16 = v18;
          }
          v8 -= v2;
          if ( v8 < v2 )
            goto LABEL_39;
        }
        if ( v13 )
          goto LABEL_39;
LABEL_24:
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 32LL))(*(_QWORD *)(v11 + *((_QWORD *)this + 3)))
          && !(*(unsigned __int8 (__fastcall **)(_BYTE *))(*(_QWORD *)v4 + 32LL))(v4) )
        {
          v11 = v21;
          v10 = 8 * v8;
          goto LABEL_27;
        }
        if ( !(*(unsigned __int8 (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 32LL))(v12) )
          (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v4 + 32LL))(v4);
LABEL_39:
        if ( v8 >= *((_QWORD *)this + 4) )
LABEL_53:
          ATL::AtlThrowImpl(-2147024809);
        _mm_lfence();
        v19 = (_BYTE *)(*((_QWORD *)this + 3) + 8 * v8);
        v20 = *(void (__fastcall ****)(_QWORD, __int64))v19;
        if ( *(_BYTE **)v19 == v4 )
        {
          if ( v19 != v22 )
            goto LABEL_46;
        }
        else
        {
          if ( v20 )
            (**v20)(v20, 1);
          *(_QWORD *)v19 = v4;
LABEL_46:
          v4 = 0;
        }
      }
      v2 /= 3u;
      if ( !v2 )
      {
        if ( v4 )
          (**(void (__fastcall ***)(_BYTE *, __int64))v4)(v4, 1);
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x140012aa0  mov     [rsp+arg_8], rbx
0x140012aa5  mov     [rsp+arg_10], rbp
0x140012aaa  mov     [rsp+arg_18], rsi
0x140012aaf  push    rdi
0x140012ab0  push    r12
0x140012ab2  push    r13
0x140012ab4  push    r14
0x140012ab6  push    r15
0x140012ab8  sub     rsp, 40h
0x140012abc  mov     r15, rcx
0x140012abf  mov     edi, 1
0x140012ac4  mov     r13, [rcx+20h]
0x140012ac8  xor     ebx, ebx
0x140012aca  lea     eax, [rdi+3]
0x140012acd  cmp     r13, rax
0x140012ad0  jbe     short loc_140012AEA
0x140012ad2  mov     rdi, rax
0x140012ad5  lea     rax, [rax+rax*2]
0x140012ad9  inc     rax
0x140012adc  cmp     rax, r13
0x140012adf  jb      short loc_140012AD2
0x140012ae1  test    rdi, rdi
0x140012ae4  jz      loc_140012D1C
0x140012aea  lea     rbp, [rdi-1]
0x140012aee  jmp     loc_140012CE0
0x140012af3  cmp     rbp, [r15+20h]
0x140012af7  jnb     loc_140012D3A
0x140012afd  mov     rax, [r15+18h]
0x140012b01  lea     rsi, [rax+rbp*8]
0x140012b05  cmp     rbx, [rsi]
0x140012b08  jnz     short loc_140012B16
0x140012b0a  lea     rax, [rsp+68h+var_38]
0x140012b0f  cmp     rax, rsi
0x140012b12  jz      short loc_140012B39
0x140012b14  jmp     short loc_140012B32
0x140012b16  test    rbx, rbx
0x140012b19  jz      short loc_140012B2F
0x140012b1b  mov     rax, [rbx]
0x140012b1e  mov     edx, 1
0x140012b23  mov     rcx, rbx
0x140012b26  mov     rax, [rax]
0x140012b29  call    cs:__guard_dispatch_icall_fptr
0x140012b2f  mov     rbx, [rsi]
0x140012b32  mov     qword ptr [rsi], 0
0x140012b39  mov     rsi, rbp
0x140012b3c  cmp     rbp, rdi
0x140012b3f  jb      loc_140012C96
0x140012b45  mov     rax, rdi
0x140012b48  neg     rax
0x140012b4b  mov     [rsp+68h+var_40], rax
0x140012b50  mov     r14, rsi
0x140012b53  sub     r14, rdi
0x140012b56  cmp     r14, [r15+20h]
0x140012b5a  jnb     loc_140012D3A
0x140012b60  lfence
0x140012b63  lea     rdx, ds:0[rsi*8]
0x140012b6b  lea     rcx, [rdx+rax*8]
0x140012b6f  mov     [rsp+68h+var_48], rcx
0x140012b74  mov     rax, [r15+18h]
0x140012b78  mov     r12, [rcx+rax]
0x140012b7c  movzx   eax, byte ptr [rbx+84h]
0x140012b83  and     eax, 10h
0x140012b86  test    byte ptr [r12+84h], 10h
0x140012b8f  jz      short loc_140012B97
0x140012b91  test    eax, eax
0x140012b93  jz      short loc_140012BFC
0x140012b95  jmp     short loc_140012B9F
0x140012b97  test    eax, eax
0x140012b99  jnz     loc_140012C96
0x140012b9f  mov     al, [rbx+90h]
0x140012ba5  cmp     byte ptr [r12+90h], 0
0x140012bae  jz      short loc_140012BB6
0x140012bb0  test    al, al
0x140012bb2  jz      short loc_140012BFC
0x140012bb4  jmp     short loc_140012BBE
0x140012bb6  test    al, al
0x140012bb8  jnz     loc_140012C96
0x140012bbe  mov     rax, [r12]
0x140012bc2  mov     rcx, r12
0x140012bc5  mov     rax, [rax+20h]
0x140012bc9  call    cs:__guard_dispatch_icall_fptr
0x140012bcf  test    al, al
0x140012bd1  jz      loc_140012C71
0x140012bd7  mov     rax, [rbx]
0x140012bda  mov     rcx, rbx
0x140012bdd  mov     rax, [rax+20h]
0x140012be1  call    cs:__guard_dispatch_icall_fptr
0x140012be7  test    al, al
0x140012be9  jnz     loc_140012C71
0x140012bef  mov     rcx, [rsp+68h+var_48]
0x140012bf4  lea     rdx, ds:0[rsi*8]
0x140012bfc  cmp     r14, [r15+20h]
0x140012c00  jnb     loc_140012D3A
0x140012c06  mov     rax, [r15+18h]
0x140012c0a  lea     r14, [rax+rcx]
0x140012c0e  cmp     rsi, [r15+20h]
0x140012c12  jnb     loc_140012D3A
0x140012c18  lea     r12, [rdx+rax]
0x140012c1c  mov     rcx, [r12]
0x140012c20  cmp     rcx, [r14]
0x140012c23  jnz     short loc_140012C33
0x140012c25  cmp     r12, r14
0x140012c28  jz      short loc_140012C5F
0x140012c2a  mov     qword ptr [r14], 0
0x140012c31  jmp     short loc_140012C5F
0x140012c33  test    rcx, rcx
0x140012c36  jz      short loc_140012C49
0x140012c38  mov     rax, [rcx]
0x140012c3b  mov     edx, 1
0x140012c40  mov     rax, [rax]
0x140012c43  call    cs:__guard_dispatch_icall_fptr
0x140012c49  mov     qword ptr [r12], 0
0x140012c51  mov     rax, [r14]
0x140012c54  mov     qword ptr [r14], 0
0x140012c5b  mov     [r12], rax
0x140012c5f  sub     rsi, rdi
0x140012c62  cmp     rsi, rdi
0x140012c65  jb      short loc_140012C96
0x140012c67  mov     rax, [rsp+68h+var_40]
0x140012c6c  jmp     loc_140012B50
0x140012c71  mov     rax, [r12]
0x140012c75  mov     rcx, r12
0x140012c78  mov     rax, [rax+20h]
0x140012c7c  call    cs:__guard_dispatch_icall_fptr
0x140012c82  test    al, al
0x140012c84  jnz     short loc_140012C96
0x140012c86  mov     rax, [rbx]
0x140012c89  mov     rcx, rbx
0x140012c8c  mov     rax, [rax+20h]
0x140012c90  call    cs:__guard_dispatch_icall_fptr
0x140012c96  cmp     rsi, [r15+20h]
0x140012c9a  jnb     loc_140012D3A
0x140012ca0  lfence
0x140012ca3  mov     rax, [r15+18h]
0x140012ca7  lea     rsi, [rax+rsi*8]
0x140012cab  mov     r14, rbx
0x140012cae  mov     rcx, [rsi]
0x140012cb1  cmp     rcx, rbx
0x140012cb4  jnz     short loc_140012CC2
0x140012cb6  lea     rax, [rsp+68h+var_38]
0x140012cbb  cmp     rsi, rax
0x140012cbe  jz      short loc_140012CDD
0x140012cc0  jmp     short loc_140012CDB
0x140012cc2  test    rcx, rcx
0x140012cc5  jz      short loc_140012CD8
0x140012cc7  mov     rax, [rcx]
0x140012cca  mov     edx, 1
0x140012ccf  mov     rax, [rax]
0x140012cd2  call    cs:__guard_dispatch_icall_fptr
0x140012cd8  mov     [rsi], r14
0x140012cdb  xor     ebx, ebx
0x140012cdd  inc     rbp
0x140012ce0  cmp     rbp, r13
0x140012ce3  jb      loc_140012AF3
0x140012ce9  mov     rax, 0AAAAAAAAAAAAAAABh
0x140012cf3  mul     rdi
0x140012cf6  mov     rdi, rdx
0x140012cf9  shr     rdi, 1
0x140012cfc  jnz     loc_140012AEA
0x140012d02  test    rbx, rbx
0x140012d05  jz      short loc_140012D1C
0x140012d07  mov     rax, [rbx]
0x140012d0a  mov     edx, 1
0x140012d0f  mov     rcx, rbx
0x140012d12  mov     rax, [rax]
0x140012d15  call    cs:__guard_dispatch_icall_fptr
0x140012d1b  nop
0x140012d1c  lea     r11, [rsp+68h+var_28]
0x140012d21  mov     rbx, [r11+38h]
0x140012d25  mov     rbp, [r11+40h]
0x140012d29  mov     rsi, [r11+48h]
0x140012d2d  mov     rsp, r11
0x140012d30  pop     r15
0x140012d32  pop     r14
0x140012d34  pop     r13
0x140012d36  pop     r12
0x140012d38  pop     rdi
0x140012d39  retn
0x140012d3a  mov     ecx, 80070057h; int
0x140012d3f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
