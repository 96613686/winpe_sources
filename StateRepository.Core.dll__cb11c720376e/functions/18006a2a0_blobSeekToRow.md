# blobSeekToRow

- ea: `0x18006a2a0`
- end: `0x18006a3f5`
- name: `blobSeekToRow`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18008c9b0`
- `0x18008cf00`

## callees

- `0x180020d40`
- `0x1800256c4`
- `0x180029bd0`
- `0x18002a050`
- `0x1800303e0`
- `0x180048bd0`
- `0x18004d2f0`
- `0x18006a2a0`

## string_xrefs

- `0x18006a36b`: `cannot open value of type %s`

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
  unsigned int v13; // ecx
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
  sqlite3VdbeMemSetInt64(*(_QWORD *)(v3 + 104) + 56LL);
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
      goto LABEL_12;
    v13 = *(_DWORD *)(v12 + 4 * v11 + 120);
    if ( v13 >= 0xC )
    {
      *(_DWORD *)(a1 + 4) = *(_DWORD *)(v12 + 4LL * ((int)v11 + *(__int16 *)(v12 + 72)) + 120);
      *(_DWORD *)a1 = sqlite3VdbeSerialTypeLen();
      v16 = *(_QWORD *)(v15 + 48);
      *(_QWORD *)(a1 + 16) = v16;
      *(_BYTE *)(v16 + 1) |= 0x10u;
      v9 = 0;
      *(_BYTE *)(*(_QWORD *)(v16 + 8) + 19LL) = 1;
      goto LABEL_19;
    }
    if ( v13 )
    {
      v14 = "real";
      if ( v13 != 7 )
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
      v22 = (const char *)sqlite3_errmsg();
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
0x18006a2a0  push    rbx
0x18006a2a2  push    rbp
0x18006a2a3  push    rsi
0x18006a2a4  push    rdi
0x18006a2a5  push    r14
0x18006a2a7  push    r15
0x18006a2a9  sub     rsp, 28h
0x18006a2ad  mov     rsi, [rcx+18h]
0x18006a2b1  mov     rbx, rcx
0x18006a2b4  mov     r15, r8
0x18006a2b7  mov     r14, rdx
0x18006a2ba  xor     ebp, ebp
0x18006a2bc  mov     rcx, [rsi+68h]
0x18006a2c0  add     rcx, 38h ; '8'
0x18006a2c4  call    sqlite3VdbeMemSetInt64
0x18006a2c9  cmp     dword ptr [rsi+30h], 4
0x18006a2cd  jle     short loc_18006A2E0
0x18006a2cf  mov     rcx, rsi
0x18006a2d2  mov     dword ptr [rsi+30h], 4
0x18006a2d9  call    sqlite3VdbeExec
0x18006a2de  jmp     short loc_18006A2E9
0x18006a2e0  mov     rcx, [rbx+18h]
0x18006a2e4  call    sqlite3_step
0x18006a2e9  mov     edi, eax
0x18006a2eb  cmp     eax, 64h ; 'd'
0x18006a2ee  jnz     loc_18006A390
0x18006a2f4  mov     rax, [rsi+78h]
0x18006a2f8  movzx   r9d, word ptr [rbx+8]
0x18006a2fd  mov     r8, [rax]
0x18006a300  cmp     [r8+4Ah], r9w
0x18006a305  jbe     short loc_18006A360
0x18006a307  mov     ecx, [r8+r9*4+78h]
0x18006a30c  cmp     ecx, 0Ch
0x18006a30f  jnb     short loc_18006A32C
0x18006a311  test    ecx, ecx
0x18006a313  jz      short loc_18006A360
0x18006a315  cmp     ecx, 7
0x18006a318  lea     r8, aReal_0; "real"
0x18006a31f  lea     rax, aInteger; "integer"
0x18006a326  cmovnz  r8, rax
0x18006a32a  jmp     short loc_18006A367
0x18006a32c  movsx   eax, word ptr [r8+48h]
0x18006a331  add     eax, r9d
0x18006a334  cdqe
0x18006a336  mov     edx, [r8+rax*4+78h]
0x18006a33b  mov     [rbx+4], edx
0x18006a33e  call    sqlite3VdbeSerialTypeLen
0x18006a343  mov     [rbx], eax
0x18006a345  mov     rax, [r8+30h]
0x18006a349  mov     [rbx+10h], rax
0x18006a34d  or      byte ptr [rax+1], 10h
0x18006a351  mov     rax, [rax+8]
0x18006a355  xor     edi, edi
0x18006a357  mov     byte ptr [rax+13h], 1
0x18006a35b  jmp     loc_18006A3E3
0x18006a360  lea     r8, aNull_2; "null"
0x18006a367  mov     rcx, [rbx+20h]
0x18006a36b  lea     rdx, aCannotOpenValu; "cannot open value of type %s"
0x18006a372  call    sqlite3MPrintf
0x18006a377  mov     rcx, [rbx+18h]
0x18006a37b  mov     rbp, rax
0x18006a37e  mov     edi, 1
0x18006a383  call    sqlite3_finalize
0x18006a388  mov     qword ptr [rbx+18h], 0
0x18006a390  mov     rcx, [rbx+18h]
0x18006a394  test    rcx, rcx
0x18006a397  jz      short loc_18006A3E3
0x18006a399  call    sqlite3_finalize
0x18006a39e  mov     rcx, [rbx+20h]
0x18006a3a2  mov     edi, eax
0x18006a3a4  mov     qword ptr [rbx+18h], 0
0x18006a3ac  test    eax, eax
0x18006a3ae  jnz     short loc_18006A3C6
0x18006a3b0  mov     r8, r14
0x18006a3b3  lea     rdx, aNoSuchRowidLld; "no such rowid: %lld"
0x18006a3ba  call    sqlite3MPrintf
0x18006a3bf  mov     edi, 1
0x18006a3c4  jmp     short loc_18006A3E0
0x18006a3c6  mov     rbx, rcx
0x18006a3c9  call    sqlite3_errmsg
0x18006a3ce  mov     r8, rax
0x18006a3d1  lea     rdx, aS_7; "%s"
0x18006a3d8  mov     rcx, rbx
0x18006a3db  call    sqlite3MPrintf
0x18006a3e0  mov     rbp, rax
0x18006a3e3  mov     [r15], rbp
0x18006a3e6  mov     eax, edi
0x18006a3e8  add     rsp, 28h
0x18006a3ec  pop     r15
0x18006a3ee  pop     r14
0x18006a3f0  pop     rdi
0x18006a3f1  pop     rsi
0x18006a3f2  pop     rbp
0x18006a3f3  pop     rbx
0x18006a3f4  retn
```
