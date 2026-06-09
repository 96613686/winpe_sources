# blobSeekToRow

- ea: `0x18007a8f0`
- end: `0x18007aa45`
- name: `blobSeekToRow`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18009a580`
- `0x18009aab0`

## callees

- `0x1800205e0`
- `0x180023a80`
- `0x180028360`
- `0x1800286a4`
- `0x180031d80`
- `0x180040e00`
- `0x180050210`
- `0x18007a8f0`

## string_xrefs

- `0x18007a9bb`: `cannot open value of type %s`

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
0x18007a8f0  push    rbx
0x18007a8f2  push    rbp
0x18007a8f3  push    rsi
0x18007a8f4  push    rdi
0x18007a8f5  push    r14
0x18007a8f7  push    r15
0x18007a8f9  sub     rsp, 28h
0x18007a8fd  mov     rsi, [rcx+18h]
0x18007a901  mov     rbx, rcx
0x18007a904  mov     r15, r8
0x18007a907  mov     r14, rdx
0x18007a90a  xor     ebp, ebp
0x18007a90c  mov     rcx, [rsi+68h]
0x18007a910  add     rcx, 38h ; '8'
0x18007a914  call    sqlite3VdbeMemSetInt64
0x18007a919  cmp     dword ptr [rsi+30h], 4
0x18007a91d  jle     short loc_18007A930
0x18007a91f  mov     rcx, rsi
0x18007a922  mov     dword ptr [rsi+30h], 4
0x18007a929  call    sqlite3VdbeExec
0x18007a92e  jmp     short loc_18007A939
0x18007a930  mov     rcx, [rbx+18h]
0x18007a934  call    sqlite3_step
0x18007a939  mov     edi, eax
0x18007a93b  cmp     eax, 64h ; 'd'
0x18007a93e  jnz     loc_18007A9E0
0x18007a944  mov     rax, [rsi+78h]
0x18007a948  movzx   r9d, word ptr [rbx+8]
0x18007a94d  mov     r8, [rax]
0x18007a950  cmp     [r8+4Ah], r9w
0x18007a955  jbe     short loc_18007A9B0
0x18007a957  mov     ecx, [r8+r9*4+78h]
0x18007a95c  cmp     ecx, 0Ch
0x18007a95f  jnb     short loc_18007A97C
0x18007a961  test    ecx, ecx
0x18007a963  jz      short loc_18007A9B0
0x18007a965  cmp     ecx, 7
0x18007a968  lea     r8, aReal_0; "real"
0x18007a96f  lea     rax, aInteger; "integer"
0x18007a976  cmovnz  r8, rax
0x18007a97a  jmp     short loc_18007A9B7
0x18007a97c  movsx   eax, word ptr [r8+48h]
0x18007a981  add     eax, r9d
0x18007a984  cdqe
0x18007a986  mov     edx, [r8+rax*4+78h]
0x18007a98b  mov     [rbx+4], edx
0x18007a98e  call    sqlite3VdbeSerialTypeLen
0x18007a993  mov     [rbx], eax
0x18007a995  mov     rax, [r8+30h]
0x18007a999  mov     [rbx+10h], rax
0x18007a99d  or      byte ptr [rax+1], 10h
0x18007a9a1  mov     rax, [rax+8]
0x18007a9a5  xor     edi, edi
0x18007a9a7  mov     byte ptr [rax+13h], 1
0x18007a9ab  jmp     loc_18007AA33
0x18007a9b0  lea     r8, aNull_2; "null"
0x18007a9b7  mov     rcx, [rbx+20h]
0x18007a9bb  lea     rdx, aCannotOpenValu; "cannot open value of type %s"
0x18007a9c2  call    sqlite3MPrintf
0x18007a9c7  mov     rcx, [rbx+18h]
0x18007a9cb  mov     rbp, rax
0x18007a9ce  mov     edi, 1
0x18007a9d3  call    sqlite3_finalize
0x18007a9d8  mov     qword ptr [rbx+18h], 0
0x18007a9e0  mov     rcx, [rbx+18h]
0x18007a9e4  test    rcx, rcx
0x18007a9e7  jz      short loc_18007AA33
0x18007a9e9  call    sqlite3_finalize
0x18007a9ee  mov     rcx, [rbx+20h]
0x18007a9f2  mov     edi, eax
0x18007a9f4  mov     qword ptr [rbx+18h], 0
0x18007a9fc  test    eax, eax
0x18007a9fe  jnz     short loc_18007AA16
0x18007aa00  mov     r8, r14
0x18007aa03  lea     rdx, aNoSuchRowidLld; "no such rowid: %lld"
0x18007aa0a  call    sqlite3MPrintf
0x18007aa0f  mov     edi, 1
0x18007aa14  jmp     short loc_18007AA30
0x18007aa16  mov     rbx, rcx
0x18007aa19  call    sqlite3_errmsg
0x18007aa1e  mov     r8, rax
0x18007aa21  lea     rdx, aS_7; "%s"
0x18007aa28  mov     rcx, rbx
0x18007aa2b  call    sqlite3MPrintf
0x18007aa30  mov     rbp, rax
0x18007aa33  mov     [r15], rbp
0x18007aa36  mov     eax, edi
0x18007aa38  add     rsp, 28h
0x18007aa3c  pop     r15
0x18007aa3e  pop     r14
0x18007aa40  pop     rdi
0x18007aa41  pop     rsi
0x18007aa42  pop     rbp
0x18007aa43  pop     rbx
0x18007aa44  retn
```
