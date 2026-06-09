# DSCSend

- ea: `0x18001aa48`
- end: `0x18001ada9`
- name: `DSCSend`
- size: `865`
- prototype: ``
- caller_count: `22`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bd5c`
- `0x18000f998`
- `0x1800124cc`
- `0x1800125d0`
- `0x180012c34`
- `0x180012de0`
- `0x180012f88`
- `0x18001313c`
- `0x180013500`
- `0x1800139e8`
- `0x180013bf8`
- `0x1800143e4`
- `0x18001462c`
- `0x1800146dc`
- `0x1800148ec`
- `0x180014988`
- `0x180014ad8`
- `0x180014d48`
- `0x180015264`
- `0x180015774`
- `0x1800158f4`
- `0x180015994`

## callees

- `0x180001ee0`
- `0x180016940`
- `0x18001aa48`
- `0x18001aeb4`
- `0x1800223e0`
- `0x18002df78`
- `0x180030bcc`
- `0x18005d010`

## pseudocode

```c
_BOOL8 DSCSend(__int64 a1, const char *a2, ...)
{
  va_list v2; // r9
  __int64 v4; // rsi
  unsigned int v5; // ecx
  __int64 *v6; // rdx
  __int16 v7; // r12
  __int64 v8; // r13
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // edi
  int v12; // ecx
  __int64 *v13; // r14
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // r15d
  __int64 v19; // r14
  __int64 v20; // rax
  int v21; // eax
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD, _QWORD); // rax
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  char v26[256]; // [rsp+40h] [rbp-C0h] BYREF
  va_list va; // [rsp+1B0h] [rbp+B0h] BYREF

  va_start(va, a2);
  va_copy(v2, va);
  v25 = 0;
  if ( (unsigned __int64)a2 >= 0x10000 )
  {
    if ( (int)OPVsprintf(v26, 256, a2, (__int64 *)va) > 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( v26[v4] );
LABEL_60:
      OPRawPortWrite(a1, v26, v4);
      return *(_DWORD *)(a1 + 3440) == 0;
    }
    return *(_DWORD *)(a1 + 3440) == 0;
  }
  v5 = 0;
  while ( 1 )
  {
    v6 = &qword_18005F3A0[2 * v5];
    if ( *(unsigned __int16 *)v6 == (_DWORD)a2 )
      break;
    if ( (int)++v5 >= 31 )
    {
      v6 = 0;
      break;
    }
  }
  v7 = *((_WORD *)v6 + 1);
  v4 = -1;
  v8 = v6[1];
  v25 = v8;
  if ( v7 == 1 && v8 && (int)OPVsprintf(v26, 256, v8, (__int64 *)va) > 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v26[v9] );
    OPRawPortWrite(a1, v26, v9);
  }
  if ( a2 == (const char *)5 )
  {
    v10 = 0;
  }
  else
  {
    if ( a2 != (const char *)6 )
      goto LABEL_21;
    v10 = 1;
  }
  RESSendResourceComments(a1, v10, 1, v2);
LABEL_21:
  v11 = 0;
  v12 = 0;
  v13 = *(__int64 **)(a1 + 2352);
  if ( v13 )
  {
    do
    {
      if ( *((unsigned __int16 *)v13 + 4) == (_DWORD)a2 )
      {
        v14 = *((unsigned __int16 *)v13 + 5);
        if ( v14 == *(_DWORD *)(a1 + 2172) || !(_WORD)v14 )
        {
          v15 = *((_DWORD *)v13 + 3);
          if ( v15 )
          {
            if ( !(unsigned int)OPRawPortWrite(a1, (char *)v13 + 16, v15) )
            {
              v11 = -1;
              goto LABEL_34;
            }
            v16 = (unsigned int)(*((_DWORD *)v13 + 3) - 1);
            if ( *((_BYTE *)v13 + v16 + 16) == 13 || (v12 = 1, *((_BYTE *)v13 + v16 + 16) == 10) )
              v12 = 0;
          }
          ++v11;
        }
      }
      v13 = (__int64 *)*v13;
    }
    while ( v13 );
    if ( v12 )
      OPRawPortWrite(a1, "\r\n", 2u);
  }
LABEL_34:
  if ( v7 != 2 || !v11 )
  {
    v17 = *(_QWORD *)(a1 + 3464);
    v24 = 0;
    v18 = *(_DWORD *)(v17 + 8);
    v19 = v17 + 24;
    if ( v18 )
    {
      while ( 1 )
      {
        v20 = *(_QWORD *)(v19 + 32);
        if ( v20 )
        {
          *(_QWORD *)(a1 + 32) = v20;
          *(_QWORD *)(a1 + 8) = *(_QWORD *)(v19 + 40);
          *(_QWORD *)(a1 + 48) = *(_QWORD *)(v19 + 56);
          v24 = 50;
          if ( *(_QWORD *)(v19 + 72) )
          {
            if ( (unsigned int)HComOEMCommand(v19, a1, (_DWORD)a2, 0, 0, (__int64)&v24) == -2147467263 )
              goto LABEL_49;
            v21 = v24;
          }
          else
          {
            if ( *(char *)(v19 + 100) >= 0 )
              v22 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))PGetOemEntrypointAddress(v19, 7);
            else
              v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(v19 + 160);
            if ( !v22 )
              goto LABEL_49;
            v21 = v22(a1, (unsigned int)a2, 0, 0);
            v24 = v21;
          }
          if ( v21 != 50 )
          {
            v11 = v21 != 0 ? -1 : 1;
            if ( v7 == 2 )
            {
LABEL_50:
              v8 = v25;
              break;
            }
          }
        }
LABEL_49:
        v19 += 176;
        if ( !--v18 )
          goto LABEL_50;
      }
    }
  }
  if ( a2 == (const char *)3 && v11 > 0 )
    *(_DWORD *)(a1 + 2164) = 1;
  if ( (!v7 || v7 == 2 && !v11) && v8 && (int)OPVsprintf(v26, 256, v8, (__int64 *)va) > 0 )
  {
    do
      ++v4;
    while ( v26[v4] );
    goto LABEL_60;
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x18001aa48  mov     [rsp-8+arg_8], rdx
0x18001aa4d  mov     [rsp-8+arg_10], r8
0x18001aa52  mov     [rsp-8+arg_18], r9
0x18001aa57  push    rbp
0x18001aa58  push    rbx
0x18001aa59  push    rsi
0x18001aa5a  push    rdi
0x18001aa5b  push    r12
0x18001aa5d  push    r13
0x18001aa5f  push    r14
0x18001aa61  push    r15
0x18001aa63  lea     rbp, [rsp-58h]
0x18001aa68  sub     rsp, 158h
0x18001aa6f  mov     rax, cs:__security_cookie
0x18001aa76  xor     rax, rsp
0x18001aa79  mov     [rbp+90h+var_50], rax
0x18001aa7d  xor     r14d, r14d
0x18001aa80  lea     r9, [rbp+90h+arg_10]
0x18001aa87  mov     [rsp+190h+var_158], r14
0x18001aa8c  mov     rbx, rcx
0x18001aa8f  cmp     rdx, 10000h
0x18001aa96  jb      short loc_18001AAC9
0x18001aa98  mov     r8, rdx
0x18001aa9b  lea     rcx, [rsp+190h+var_150]
0x18001aaa0  mov     edx, 100h
0x18001aaa5  call    OPVsprintf
0x18001aaaa  test    eax, eax
0x18001aaac  jle     loc_18001AD7C
0x18001aab2  lea     rax, [rsp+190h+var_150]
0x18001aab7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001aabb  inc     rsi
0x18001aabe  cmp     [rax+rsi], r14b
0x18001aac2  jnz     short loc_18001AABB
0x18001aac4  jmp     loc_18001AD6C
0x18001aac9  mov     ecx, r14d
0x18001aacc  mov     r8d, 1
0x18001aad2  mov     eax, ecx
0x18001aad4  lea     rdx, qword_18005F3A0
0x18001aadb  shl     rax, 4
0x18001aadf  add     rdx, rax
0x18001aae2  movzx   eax, word ptr [rdx]
0x18001aae5  cmp     eax, dword ptr [rbp+90h+arg_8]
0x18001aaeb  jz      short loc_18001AAF8
0x18001aaed  add     ecx, r8d
0x18001aaf0  cmp     ecx, 1Fh
0x18001aaf3  jl      short loc_18001AAD2
0x18001aaf5  mov     rdx, r14
0x18001aaf8  movzx   r12d, word ptr [rdx+2]
0x18001aafd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001ab01  mov     r13, [rdx+8]
0x18001ab05  mov     [rsp+190h+var_158], r13
0x18001ab0a  cmp     r12w, r8w
0x18001ab0e  jnz     short loc_18001AB4F
0x18001ab10  test    r13, r13
0x18001ab13  jz      short loc_18001AB4F
0x18001ab15  mov     r8, r13
0x18001ab18  lea     rcx, [rsp+190h+var_150]
0x18001ab1d  mov     edx, 100h
0x18001ab22  call    OPVsprintf
0x18001ab27  test    eax, eax
0x18001ab29  jle     short loc_18001AB49
0x18001ab2b  lea     rax, [rsp+190h+var_150]
0x18001ab30  mov     r8, rsi
0x18001ab33  inc     r8
0x18001ab36  cmp     [rax+r8], r14b
0x18001ab3a  jnz     short loc_18001AB33
0x18001ab3c  lea     rdx, [rsp+190h+var_150]
0x18001ab41  mov     rcx, rbx
0x18001ab44  call    OPRawPortWrite
0x18001ab49  mov     r8d, 1
0x18001ab4f  cmp     [rbp+90h+arg_8], 5
0x18001ab57  jnz     short loc_18001AB5D
0x18001ab59  xor     edx, edx
0x18001ab5b  jmp     short loc_18001AB6A
0x18001ab5d  cmp     [rbp+90h+arg_8], 6
0x18001ab65  jnz     short loc_18001AB72
0x18001ab67  mov     edx, r8d
0x18001ab6a  mov     rcx, rbx
0x18001ab6d  call    RESSendResourceComments
0x18001ab72  mov     r15d, dword ptr [rbp+90h+arg_8]
0x18001ab79  mov     edi, r14d
0x18001ab7c  mov     ecx, r14d
0x18001ab7f  xor     edx, edx
0x18001ab81  mov     r14, [rbx+930h]
0x18001ab88  test    r14, r14
0x18001ab8b  jz      short loc_18001AC04
0x18001ab8d  movzx   eax, word ptr [r14+8]
0x18001ab92  cmp     eax, r15d
0x18001ab95  jnz     short loc_18001ABE5
0x18001ab97  movzx   eax, word ptr [r14+0Ah]
0x18001ab9c  cmp     eax, [rbx+87Ch]
0x18001aba2  jz      short loc_18001ABA9
0x18001aba4  test    ax, ax
0x18001aba7  jnz     short loc_18001ABE5
0x18001aba9  mov     r8d, [r14+0Ch]
0x18001abad  test    r8d, r8d
0x18001abb0  jz      short loc_18001ABE3
0x18001abb2  lea     rdx, [r14+10h]
0x18001abb6  mov     rcx, rbx
0x18001abb9  call    OPRawPortWrite
0x18001abbe  xor     edx, edx
0x18001abc0  test    eax, eax
0x18001abc2  jz      loc_18001ACA1
0x18001abc8  mov     eax, [r14+0Ch]
0x18001abcc  dec     eax
0x18001abce  cmp     byte ptr [rax+r14+10h], 0Dh
0x18001abd4  jz      short loc_18001ABE1
0x18001abd6  cmp     byte ptr [rax+r14+10h], 0Ah
0x18001abdc  lea     ecx, [rdx+1]
0x18001abdf  jnz     short loc_18001ABE3
0x18001abe1  mov     ecx, edx
0x18001abe3  inc     edi
0x18001abe5  mov     r14, [r14]
0x18001abe8  test    r14, r14
0x18001abeb  jnz     short loc_18001AB8D
0x18001abed  test    ecx, ecx
0x18001abef  jz      short loc_18001AC04
0x18001abf1  lea     r8d, [r14+2]
0x18001abf5  mov     rcx, rbx
0x18001abf8  lea     rdx, gstrCRLF; "\r\n"
0x18001abff  call    OPRawPortWrite
0x18001ac04  mov     eax, 2
0x18001ac09  xor     r14d, r14d
0x18001ac0c  cmp     r12w, ax
0x18001ac10  jnz     short loc_18001AC1A
0x18001ac12  test    edi, edi
0x18001ac14  jnz     loc_18001AD14
0x18001ac1a  mov     rax, [rbx+0D88h]
0x18001ac21  mov     [rsp+190h+var_160], r14d
0x18001ac26  mov     r15d, [rax+8]
0x18001ac2a  lea     r14, [rax+18h]
0x18001ac2e  test    r15d, r15d
0x18001ac31  jz      loc_18001AD0C
0x18001ac37  mov     r13d, 2
0x18001ac3d  mov     rax, [r14+20h]
0x18001ac41  test    rax, rax
0x18001ac44  jz      loc_18001ACF6
0x18001ac4a  mov     [rbx+20h], rax
0x18001ac4e  mov     rax, [r14+28h]
0x18001ac52  mov     [rbx+8], rax
0x18001ac56  mov     rax, [r14+38h]
0x18001ac5a  mov     [rbx+30h], rax
0x18001ac5e  mov     [rsp+190h+var_160], 32h ; '2'
0x18001ac66  cmp     qword ptr [r14+48h], 0
0x18001ac6b  jz      short loc_18001ACA8
0x18001ac6d  mov     r8d, dword ptr [rbp+90h+arg_8]
0x18001ac74  lea     rax, [rsp+190h+var_160]
0x18001ac79  mov     [rsp+190h+var_168], rax
0x18001ac7e  xor     r9d, r9d
0x18001ac81  mov     rdx, rbx
0x18001ac84  mov     [rsp+190h+var_170], 0
0x18001ac8c  mov     rcx, r14
0x18001ac8f  call    HComOEMCommand
0x18001ac94  cmp     eax, 80004001h
0x18001ac99  jz      short loc_18001ACF6
0x18001ac9b  mov     eax, [rsp+190h+var_160]
0x18001ac9f  jmp     short loc_18001ACE2
0x18001aca1  mov     edi, esi
0x18001aca3  jmp     loc_18001AC04
0x18001aca8  cmp     byte ptr [r14+64h], 0
0x18001acad  jge     short loc_18001ACB8
0x18001acaf  mov     rax, [r14+0A0h]
0x18001acb6  jmp     short loc_18001ACC5
0x18001acb8  mov     edx, 7
0x18001acbd  mov     rcx, r14
0x18001acc0  call    PGetOemEntrypointAddress
0x18001acc5  test    rax, rax
0x18001acc8  jz      short loc_18001ACF6
0x18001acca  mov     edx, dword ptr [rbp+90h+arg_8]
0x18001acd0  xor     r9d, r9d
0x18001acd3  xor     r8d, r8d
0x18001acd6  mov     rcx, rbx
0x18001acd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acde  mov     [rsp+190h+var_160], eax
0x18001ace2  cmp     eax, 32h ; '2'
0x18001ace5  jz      short loc_18001ACF6
0x18001ace7  neg     eax
0x18001ace9  sbb     edi, edi
0x18001aceb  and     edi, 0FFFFFFFEh
0x18001acee  inc     edi
0x18001acf0  cmp     r12w, r13w
0x18001acf4  jz      short loc_18001AD07
0x18001acf6  add     r14, 0B0h
0x18001acfd  add     r15d, 0FFFFFFFFh
0x18001ad01  jnz     loc_18001AC3D
0x18001ad07  mov     r13, [rsp+190h+var_158]
0x18001ad0c  mov     eax, 2
0x18001ad11  xor     r14d, r14d
0x18001ad14  cmp     [rbp+90h+arg_8], 3
0x18001ad1c  jnz     short loc_18001AD2C
0x18001ad1e  test    edi, edi
0x18001ad20  jle     short loc_18001AD2C
0x18001ad22  mov     dword ptr [rbx+874h], 1
0x18001ad2c  test    r12w, r12w
0x18001ad30  jz      short loc_18001AD3C
0x18001ad32  cmp     r12w, ax
0x18001ad36  jnz     short loc_18001AD7C
0x18001ad38  test    edi, edi
0x18001ad3a  jnz     short loc_18001AD7C
0x18001ad3c  test    r13, r13
0x18001ad3f  jz      short loc_18001AD7C
0x18001ad41  lea     r9, [rbp+90h+arg_10]
0x18001ad48  mov     r8, r13
0x18001ad4b  mov     edx, 100h
0x18001ad50  lea     rcx, [rsp+190h+var_150]
0x18001ad55  call    OPVsprintf
0x18001ad5a  test    eax, eax
0x18001ad5c  jle     short loc_18001AD7C
0x18001ad5e  lea     rax, [rsp+190h+var_150]
0x18001ad63  inc     rsi
0x18001ad66  cmp     [rax+rsi], r14b
0x18001ad6a  jnz     short loc_18001AD63
0x18001ad6c  mov     r8d, esi
0x18001ad6f  lea     rdx, [rsp+190h+var_150]
0x18001ad74  mov     rcx, rbx
0x18001ad77  call    OPRawPortWrite
0x18001ad7c  cmp     [rbx+0D70h], r14d
0x18001ad83  mov     eax, r14d
0x18001ad86  setz    al
0x18001ad89  mov     rcx, [rbp+90h+var_50]
0x18001ad8d  xor     rcx, rsp; StackCookie
0x18001ad90  call    __security_check_cookie
0x18001ad95  add     rsp, 158h
0x18001ad9c  pop     r15
0x18001ad9e  pop     r14
0x18001ada0  pop     r13
0x18001ada2  pop     r12
0x18001ada4  pop     rdi
0x18001ada5  pop     rsi
0x18001ada6  pop     rbx
0x18001ada7  pop     rbp
0x18001ada8  retn
```
