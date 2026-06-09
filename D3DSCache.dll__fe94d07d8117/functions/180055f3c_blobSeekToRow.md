# blobSeekToRow

- ea: `0x180055f3c`
- end: `0x180056091`
- name: `blobSeekToRow`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180092ec0`
- `0x180093400`

## callees

- `0x180021aa0`
- `0x18002e150`
- `0x18003c8d4`
- `0x180042160`
- `0x180055f3c`
- `0x18008e178`
- `0x1800958b0`
- `0x180095c50`

## string_xrefs

- `0x180056007`: `cannot open value of type %s`

## pseudocode

```c
__int64 __fastcall blobSeekToRow(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rsi
  __int64 v7; // rbp
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 *v10; // rax
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rcx
  const char *v14; // r8
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  const char *v22; // rax

  v3 = *(_QWORD *)(a1 + 24);
  v7 = 0;
  sqlite3VdbeMemSetInt64(*(_QWORD *)(v3 + 104) + 56LL, a2, a3);
  if ( *(int *)(v3 + 48) <= 4 )
  {
    v8 = sqlite3_step(*(_QWORD *)(a1 + 24));
  }
  else
  {
    *(_DWORD *)(v3 + 48) = 4;
    v8 = sqlite3VdbeExec((__int64 *)v3);
  }
  v9 = v8;
  if ( v8 == 100 )
  {
    v10 = *(__int64 **)(v3 + 120);
    v11 = *(unsigned __int16 *)(a1 + 8);
    v12 = *v10;
    if ( *(_WORD *)(*v10 + 74) <= (unsigned __int16)v11 )
      goto LABEL_12;
    v13 = *(unsigned int *)(v12 + 4 * v11 + 120);
    if ( (unsigned int)v13 >= 0xC )
    {
      *(_DWORD *)(a1 + 4) = *(_DWORD *)(v12 + 4LL * ((int)v11 + *(__int16 *)(v12 + 72)) + 120);
      *(_DWORD *)a1 = sqlite3VdbeSerialTypeLen(v13);
      v16 = *(_QWORD *)(v15 + 48);
      *(_QWORD *)(a1 + 16) = v16;
      *(_BYTE *)(v16 + 1) |= 0x10u;
      v9 = 0;
      *(_BYTE *)(*(_QWORD *)(v16 + 8) + 19LL) = 1;
      goto LABEL_19;
    }
    if ( (_DWORD)v13 )
    {
      v14 = "real";
      if ( (_DWORD)v13 != 7 )
        v14 = "integer";
    }
    else
    {
LABEL_12:
      v14 = "null";
    }
    v7 = sqlite3MPrintf(*(_QWORD *)(a1 + 32), "cannot open value of type %s", v14);
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
    v7 = v20;
  }
LABEL_19:
  *a3 = v7;
  return v9;
}

```

## disassembly

```asm
0x180055f3c  push    rbx
0x180055f3e  push    rbp
0x180055f3f  push    rsi
0x180055f40  push    rdi
0x180055f41  push    r14
0x180055f43  push    r15
0x180055f45  sub     rsp, 28h
0x180055f49  mov     rsi, [rcx+18h]
0x180055f4d  mov     rbx, rcx
0x180055f50  mov     r15, r8
0x180055f53  mov     r14, rdx
0x180055f56  xor     ebp, ebp
0x180055f58  mov     rcx, [rsi+68h]
0x180055f5c  add     rcx, 38h ; '8'
0x180055f60  call    sqlite3VdbeMemSetInt64
0x180055f65  cmp     dword ptr [rsi+30h], 4
0x180055f69  jle     short loc_180055F7C
0x180055f6b  mov     rcx, rsi
0x180055f6e  mov     dword ptr [rsi+30h], 4
0x180055f75  call    sqlite3VdbeExec
0x180055f7a  jmp     short loc_180055F85
0x180055f7c  mov     rcx, [rbx+18h]
0x180055f80  call    sqlite3_step
0x180055f85  mov     edi, eax
0x180055f87  cmp     eax, 64h ; 'd'
0x180055f8a  jnz     loc_18005602C
0x180055f90  mov     rax, [rsi+78h]
0x180055f94  movzx   r9d, word ptr [rbx+8]
0x180055f99  mov     r8, [rax]
0x180055f9c  cmp     [r8+4Ah], r9w
0x180055fa1  jbe     short loc_180055FFC
0x180055fa3  mov     ecx, [r8+r9*4+78h]
0x180055fa8  cmp     ecx, 0Ch
0x180055fab  jnb     short loc_180055FC8
0x180055fad  test    ecx, ecx
0x180055faf  jz      short loc_180055FFC
0x180055fb1  cmp     ecx, 7
0x180055fb4  lea     r8, aReal_0; "real"
0x180055fbb  lea     rax, aInteger; "integer"
0x180055fc2  cmovnz  r8, rax
0x180055fc6  jmp     short loc_180056003
0x180055fc8  movsx   eax, word ptr [r8+48h]
0x180055fcd  add     eax, r9d
0x180055fd0  cdqe
0x180055fd2  mov     edx, [r8+rax*4+78h]
0x180055fd7  mov     [rbx+4], edx
0x180055fda  call    sqlite3VdbeSerialTypeLen
0x180055fdf  mov     [rbx], eax
0x180055fe1  mov     rax, [r8+30h]
0x180055fe5  mov     [rbx+10h], rax
0x180055fe9  or      byte ptr [rax+1], 10h
0x180055fed  mov     rax, [rax+8]
0x180055ff1  xor     edi, edi
0x180055ff3  mov     byte ptr [rax+13h], 1
0x180055ff7  jmp     loc_18005607F
0x180055ffc  lea     r8, aNull_3; "null"
0x180056003  mov     rcx, [rbx+20h]
0x180056007  lea     rdx, aCannotOpenValu; "cannot open value of type %s"
0x18005600e  call    sqlite3MPrintf
0x180056013  mov     rcx, [rbx+18h]
0x180056017  mov     rbp, rax
0x18005601a  mov     edi, 1
0x18005601f  call    sqlite3_finalize
0x180056024  mov     qword ptr [rbx+18h], 0
0x18005602c  mov     rcx, [rbx+18h]
0x180056030  test    rcx, rcx
0x180056033  jz      short loc_18005607F
0x180056035  call    sqlite3_finalize
0x18005603a  mov     rcx, [rbx+20h]
0x18005603e  mov     edi, eax
0x180056040  mov     qword ptr [rbx+18h], 0
0x180056048  test    eax, eax
0x18005604a  jnz     short loc_180056062
0x18005604c  mov     r8, r14
0x18005604f  lea     rdx, aNoSuchRowidLld; "no such rowid: %lld"
0x180056056  call    sqlite3MPrintf
0x18005605b  mov     edi, 1
0x180056060  jmp     short loc_18005607C
0x180056062  mov     rbx, rcx
0x180056065  call    sqlite3_errmsg
0x18005606a  mov     r8, rax
0x18005606d  lea     rdx, aS_10; "%s"
0x180056074  mov     rcx, rbx
0x180056077  call    sqlite3MPrintf
0x18005607c  mov     rbp, rax
0x18005607f  mov     [r15], rbp
0x180056082  mov     eax, edi
0x180056084  add     rsp, 28h
0x180056088  pop     r15
0x18005608a  pop     r14
0x18005608c  pop     rdi
0x18005608d  pop     rsi
0x18005608e  pop     rbp
0x18005608f  pop     rbx
0x180056090  retn
```
