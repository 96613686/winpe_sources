# blobSeekToRow

- ea: `0x14001f748`
- end: `0x14001f8b3`
- name: `blobSeekToRow`
- size: `363`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140087590`
- `0x140087b90`

## callees

- `0x14001f748`
- `0x140062bfc`
- `0x140074448`
- `0x14008a290`
- `0x14008abd0`
- `0x14008cfa0`

## string_xrefs

- `0x14001f829`: `cannot open value of type %s`

## pseudocode

```c
__int64 __fastcall blobSeekToRow(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 *v10; // rax
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rdx
  const char *v14; // r8
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  const char *v22; // rax

  v3 = *(_QWORD *)(a1 + 24);
  v4 = 0;
  *(_WORD *)(*(_QWORD *)(v3 + 104) + 76LL) = 4;
  *(_QWORD *)(*(_QWORD *)(v3 + 104) + 56LL) = a2;
  if ( *(int *)(v3 + 48) <= 4 )
  {
    v8 = sqlite3_step(*(_QWORD *)(a1 + 24));
  }
  else
  {
    *(_DWORD *)(v3 + 48) = 4;
    v8 = sqlite3VdbeExec(v3);
  }
  v9 = v8;
  if ( v8 == 100 )
  {
    v10 = *(__int64 **)(v3 + 120);
    v11 = *(unsigned __int16 *)(a1 + 8);
    v12 = *v10;
    if ( *(_WORD *)(*v10 + 74) <= (unsigned __int16)v11 )
      goto LABEL_15;
    v13 = *(unsigned int *)(v12 + 4 * v11 + 120);
    if ( (unsigned int)v13 >= 0xC )
    {
      *(_DWORD *)(a1 + 4) = *(_DWORD *)(v12 + 4LL * ((int)v11 + *(__int16 *)(v12 + 72)) + 120);
      if ( (unsigned int)v13 < 0x80 )
        v15 = *((unsigned __int8 *)qword_1400B27A0 + v13);
      else
        v15 = (unsigned int)(v13 - 12) >> 1;
      *(_DWORD *)a1 = v15;
      v16 = *(_QWORD *)(v12 + 48);
      *(_QWORD *)(a1 + 16) = v16;
      *(_BYTE *)(v16 + 1) |= 0x10u;
      v9 = 0;
      *(_BYTE *)(*(_QWORD *)(v16 + 8) + 19LL) = 1;
      goto LABEL_22;
    }
    if ( (_DWORD)v13 )
    {
      v14 = "real";
      if ( (_DWORD)v13 != 7 )
        v14 = "integer";
    }
    else
    {
LABEL_15:
      v14 = "null";
    }
    v4 = sqlite3MPrintf(*(_QWORD *)(a1 + 32), "cannot open value of type %s", v14);
    v9 = 1;
    sqlite3_finalize(*(_QWORD *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = 0;
  }
  v17 = *(_QWORD *)(a1 + 24);
  if ( v17 )
  {
    v18 = sqlite3_finalize(v17);
    v19 = *(_QWORD *)(a1 + 32);
    v9 = v18;
    *(_QWORD *)(a1 + 24) = 0;
    if ( v18 )
    {
      v21 = v19;
      v22 = (const char *)sqlite3_errmsg(v19);
      v20 = sqlite3MPrintf(v21, "%s", v22);
    }
    else
    {
      v20 = sqlite3MPrintf(v19, "no such rowid: %lld", a2);
      v9 = 1;
    }
    v4 = v20;
  }
LABEL_22:
  *a3 = v4;
  return v9;
}

```

## disassembly

```asm
0x14001f748  push    rbx
0x14001f74a  push    rbp
0x14001f74b  push    rsi
0x14001f74c  push    rdi
0x14001f74d  push    r14
0x14001f74f  push    r15
0x14001f751  sub     rsp, 28h
0x14001f755  mov     rsi, [rcx+18h]
0x14001f759  xor     ebp, ebp
0x14001f75b  mov     rbx, rcx
0x14001f75e  mov     r15, r8
0x14001f761  mov     r14, rdx
0x14001f764  mov     rax, [rsi+68h]
0x14001f768  lea     ecx, [rbp+4]
0x14001f76b  mov     [rax+4Ch], cx
0x14001f76f  mov     rax, [rsi+68h]
0x14001f773  mov     [rax+38h], rdx
0x14001f777  cmp     [rsi+30h], ecx
0x14001f77a  jle     short loc_14001F789
0x14001f77c  mov     [rsi+30h], ecx
0x14001f77f  mov     rcx, rsi
0x14001f782  call    sqlite3VdbeExec
0x14001f787  jmp     short loc_14001F792
0x14001f789  mov     rcx, [rbx+18h]
0x14001f78d  call    sqlite3_step
0x14001f792  mov     edi, eax
0x14001f794  cmp     eax, 64h ; 'd'
0x14001f797  jnz     loc_14001F84E
0x14001f79d  mov     rax, [rsi+78h]
0x14001f7a1  movzx   r9d, word ptr [rbx+8]
0x14001f7a6  mov     r8, [rax]
0x14001f7a9  cmp     [r8+4Ah], r9w
0x14001f7ae  jbe     short loc_14001F81E
0x14001f7b0  mov     edx, [r8+r9*4+78h]
0x14001f7b5  cmp     edx, 0Ch
0x14001f7b8  jnb     short loc_14001F7D5
0x14001f7ba  test    edx, edx
0x14001f7bc  jz      short loc_14001F81E
0x14001f7be  cmp     edx, 7
0x14001f7c1  lea     r8, aReal_0; "real"
0x14001f7c8  lea     rax, aInteger; "integer"
0x14001f7cf  cmovnz  r8, rax
0x14001f7d3  jmp     short loc_14001F825
0x14001f7d5  movsx   eax, word ptr [r8+48h]
0x14001f7da  add     eax, r9d
0x14001f7dd  cdqe
0x14001f7df  mov     ecx, [r8+rax*4+78h]
0x14001f7e4  mov     [rbx+4], ecx
0x14001f7e7  cmp     edx, 80h
0x14001f7ed  jb      short loc_14001F7F6
0x14001f7ef  add     edx, 0FFFFFFF4h
0x14001f7f2  shr     edx, 1
0x14001f7f4  jmp     short loc_14001F801
0x14001f7f6  lea     rcx, qword_1400B27A0
0x14001f7fd  movzx   edx, byte ptr [rdx+rcx]
0x14001f801  mov     [rbx], edx
0x14001f803  mov     rax, [r8+30h]
0x14001f807  mov     [rbx+10h], rax
0x14001f80b  or      byte ptr [rax+1], 10h
0x14001f80f  mov     rax, [rax+8]
0x14001f813  xor     edi, edi
0x14001f815  mov     byte ptr [rax+13h], 1
0x14001f819  jmp     loc_14001F8A1
0x14001f81e  lea     r8, aNull_3; "null"
0x14001f825  mov     rcx, [rbx+20h]
0x14001f829  lea     rdx, aCannotOpenValu; "cannot open value of type %s"
0x14001f830  call    sqlite3MPrintf
0x14001f835  mov     rcx, [rbx+18h]
0x14001f839  mov     rbp, rax
0x14001f83c  mov     edi, 1
0x14001f841  call    sqlite3_finalize
0x14001f846  mov     qword ptr [rbx+18h], 0
0x14001f84e  mov     rcx, [rbx+18h]
0x14001f852  test    rcx, rcx
0x14001f855  jz      short loc_14001F8A1
0x14001f857  call    sqlite3_finalize
0x14001f85c  mov     rcx, [rbx+20h]
0x14001f860  mov     edi, eax
0x14001f862  mov     qword ptr [rbx+18h], 0
0x14001f86a  test    eax, eax
0x14001f86c  jnz     short loc_14001F884
0x14001f86e  mov     r8, r14
0x14001f871  lea     rdx, aNoSuchRowidLld; "no such rowid: %lld"
0x14001f878  call    sqlite3MPrintf
0x14001f87d  mov     edi, 1
0x14001f882  jmp     short loc_14001F89E
0x14001f884  mov     rbx, rcx
0x14001f887  call    sqlite3_errmsg
0x14001f88c  mov     r8, rax
0x14001f88f  lea     rdx, aS_6; "%s"
0x14001f896  mov     rcx, rbx
0x14001f899  call    sqlite3MPrintf
0x14001f89e  mov     rbp, rax
0x14001f8a1  mov     [r15], rbp
0x14001f8a4  mov     eax, edi
0x14001f8a6  add     rsp, 28h
0x14001f8aa  pop     r15
0x14001f8ac  pop     r14
0x14001f8ae  pop     rdi
0x14001f8af  pop     rsi
0x14001f8b0  pop     rbp
0x14001f8b1  pop     rbx
0x14001f8b2  retn
```
