# jsonEachColumn

- ea: `0x180073ec0`
- end: `0x18007414c`
- name: `jsonEachColumn`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180055a4c`
- `0x18005ee00`
- `0x180067570`
- `0x180072c00`
- `0x180073ec0`
- `0x180074758`
- `0x180076974`
- `0x180077148`
- `0x18008f340`
- `0x18008f4f0`
- `0x18008f510`

## pseudocode

```c
__int64 __fastcall jsonEachColumn(__int64 a1, __int64 a2, int a3)
{
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // r9
  char *v14; // rdx
  int v15; // eax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 *v20; // rcx
  unsigned int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rbx
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // r8d
  __int64 v28; // r9
  _BYTE *v29; // rcx
  __int64 v31; // [rsp+40h] [rbp+8h] BYREF

  if ( !a3 )
  {
    v25 = *(_DWORD *)(a1 + 28);
    if ( !v25 )
    {
      if ( *(_DWORD *)(a1 + 20) == 1 )
        return 0;
      v26 = jsonEachPathLength();
      v27 = *(_DWORD *)(a1 + 20) - v26;
      if ( !v27 )
        return 0;
      v28 = *(_QWORD *)(a1 + 64);
      v29 = (_BYTE *)(v28 + v26 + 1);
      if ( *(_BYTE *)(v26 + v28) != 91 )
      {
        if ( *v29 == 34 )
        {
          v12 = v27 - 3;
          v14 = (char *)(v28 + v26 + 2);
        }
        else
        {
          v12 = v27 - 1;
          v14 = (char *)(v28 + v26 + 1);
        }
        v13 = -1;
        goto LABEL_14;
      }
      v31 = 0;
      LOBYTE(v28) = 1;
      sqlite3Atoi64(v29, &v31, v27 - 1, v28);
      v18 = v31;
LABEL_41:
      sqlite3_result_int64(a2, v18);
      return 0;
    }
    if ( *(_BYTE *)(a1 + 24) != 12 )
    {
      v18 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 24LL * (unsigned int)(v25 - 1) + 16);
      goto LABEL_41;
    }
    v21 = *(_DWORD *)(a1 + 12);
    v20 = (__int64 *)(a1 + 192);
LABEL_39:
    jsonReturnFromBlob(v20, v21, a2, 1);
    return 0;
  }
  v5 = a3 - 1;
  if ( !v5 )
  {
    v23 = jsonSkipLabel();
    v24 = v23;
    jsonReturnFromBlob((__int64 *)(a1 + 192), v23, a2, 1);
    if ( (*(_BYTE *)(v24 + *(_QWORD *)(a1 + 192)) & 0xFu) >= 0xB )
      sqlite3_result_subtype(a2, 74);
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v22 = jsonSkipLabel();
    v13 = 0;
    v14 = off_18009C050[*(_BYTE *)(v22 + *(_QWORD *)(a1 + 192)) & 0xF];
    goto LABEL_13;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v19 = jsonSkipLabel();
    v20 = (__int64 *)(a1 + 192);
    if ( (*(_BYTE *)(v19 + *(_QWORD *)(a1 + 192)) & 0xFu) >= 0xB )
      return 0;
    v21 = v19;
    goto LABEL_39;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v18 = *(unsigned int *)(a1 + 12);
    goto LABEL_41;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v17 = *(_DWORD *)(a1 + 28);
    if ( !v17 || !*(_BYTE *)(a1 + 25) )
      return 0;
    v18 = *(unsigned int *)(*(_QWORD *)(a1 + 40) + 24LL * (unsigned int)(v17 - 1));
    goto LABEL_41;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( !v11 )
    {
      v15 = jsonEachPathLength();
      sqlite3_result_text64(a2, *(_QWORD *)(a1 + 64), v15, -1, 1);
      return 0;
    }
    if ( v11 != 1 )
    {
      v12 = *(unsigned int *)(a1 + 20);
      v13 = 0;
      v14 = *(char **)(a1 + 64);
LABEL_14:
      sqlite3_result_text(a2, v14, v12, v13);
      return 0;
    }
    v14 = *(char **)(a1 + 208);
    v13 = -1;
    if ( !v14 )
    {
      sqlite3_result_blob(a2, *(_QWORD *)(a1 + 192), *(unsigned int *)(a1 + 200), -1);
      return 0;
    }
LABEL_13:
    v12 = 0xFFFFFFFFLL;
    goto LABEL_14;
  }
  v16 = *(_QWORD *)(a1 + 80);
  if ( *(_DWORD *)(a1 + 28) )
    jsonAppendPathName();
  sqlite3_result_text64(a2, *(_QWORD *)(a1 + 64), *(_QWORD *)(a1 + 80), -1, 1);
  *(_QWORD *)(a1 + 80) = v16;
  return 0;
}

```

## disassembly

```asm
0x180073ec0  mov     [rsp+arg_8], rbx
0x180073ec5  mov     [rsp+arg_10], rsi
0x180073eca  push    rdi
0x180073ecb  sub     rsp, 30h
0x180073ecf  mov     rsi, rdx
0x180073ed2  mov     rdi, rcx
0x180073ed5  test    r8d, r8d
0x180073ed8  jz      loc_180074086
0x180073ede  sub     r8d, 1
0x180073ee2  jz      loc_180074040
0x180073ee8  sub     r8d, 1
0x180073eec  jz      loc_180074018
0x180073ef2  sub     r8d, 1
0x180073ef6  jz      loc_180073FED
0x180073efc  sub     r8d, 1
0x180073f00  jz      loc_180073FE5
0x180073f06  sub     r8d, 1
0x180073f0a  jz      loc_180073FBE
0x180073f10  sub     r8d, 1
0x180073f14  jz      short loc_180073F8D
0x180073f16  sub     r8d, 1
0x180073f1a  jz      short loc_180073F6B
0x180073f1c  cmp     r8d, 1
0x180073f20  jz      short loc_180073F2F
0x180073f22  mov     r8d, [rcx+14h]
0x180073f26  xor     r9d, r9d
0x180073f29  mov     rdx, [rcx+40h]
0x180073f2d  jmp     short loc_180073F5E
0x180073f2f  mov     rdx, [rcx+0D0h]
0x180073f36  or      r9, 0FFFFFFFFFFFFFFFFh
0x180073f3a  test    rdx, rdx
0x180073f3d  jnz     short loc_180073F5A
0x180073f3f  mov     r8d, [rcx+0C8h]
0x180073f46  mov     rdx, [rcx+0C0h]
0x180073f4d  mov     rcx, rsi
0x180073f50  call    sqlite3_result_blob
0x180073f55  jmp     loc_18007413A
0x180073f5a  or      r8d, 0FFFFFFFFh
0x180073f5e  mov     rcx, rsi
0x180073f61  call    sqlite3_result_text
0x180073f66  jmp     loc_18007413A
0x180073f6b  call    jsonEachPathLength
0x180073f70  mov     rdx, [rdi+40h]
0x180073f74  or      r9, 0FFFFFFFFFFFFFFFFh
0x180073f78  mov     r8d, eax
0x180073f7b  mov     rcx, rsi
0x180073f7e  mov     [rsp+38h+var_18], 1
0x180073f83  call    sqlite3_result_text64
0x180073f88  jmp     loc_18007413A
0x180073f8d  cmp     dword ptr [rcx+1Ch], 0
0x180073f91  mov     rbx, [rcx+50h]
0x180073f95  jz      short loc_180073F9C
0x180073f97  call    jsonAppendPathName
0x180073f9c  mov     r8, [rdi+50h]
0x180073fa0  or      r9, 0FFFFFFFFFFFFFFFFh
0x180073fa4  mov     rdx, [rdi+40h]
0x180073fa8  mov     rcx, rsi
0x180073fab  mov     [rsp+38h+var_18], 1
0x180073fb0  call    sqlite3_result_text64
0x180073fb5  mov     [rdi+50h], rbx
0x180073fb9  jmp     loc_18007413A
0x180073fbe  mov     eax, [rcx+1Ch]
0x180073fc1  test    eax, eax
0x180073fc3  jz      loc_18007413A
0x180073fc9  cmp     byte ptr [rcx+19h], 0
0x180073fcd  jz      loc_18007413A
0x180073fd3  dec     eax
0x180073fd5  lea     rdx, [rax+rax*2]
0x180073fd9  mov     rax, [rcx+28h]
0x180073fdd  mov     edx, [rax+rdx*8]
0x180073fe0  jmp     loc_180074132
0x180073fe5  mov     edx, [rcx+0Ch]
0x180073fe8  jmp     loc_180074132
0x180073fed  call    jsonSkipLabel
0x180073ff2  lea     rcx, [rdi+0C0h]
0x180073ff9  mov     r8d, eax
0x180073ffc  mov     rdx, [rcx]
0x180073fff  mov     r9b, [r8+rdx]
0x180074003  and     r9b, 0Fh
0x180074007  cmp     r9b, 0Bh
0x18007400b  jnb     loc_18007413A
0x180074011  mov     edx, eax
0x180074013  jmp     loc_180074113
0x180074018  call    jsonSkipLabel
0x18007401d  mov     ecx, eax
0x18007401f  mov     rax, [rdi+0C0h]
0x180074026  movzx   edx, byte ptr [rcx+rax]
0x18007402a  lea     rax, off_18009C050; "null"
0x180074031  and     edx, 0Fh
0x180074034  xor     r9d, r9d
0x180074037  mov     rdx, [rax+rdx*8]
0x18007403b  jmp     loc_180073F5A
0x180074040  call    jsonSkipLabel
0x180074045  mov     r9d, 1
0x18007404b  mov     ebx, eax
0x18007404d  mov     r8, rsi
0x180074050  lea     rcx, [rdi+0C0h]
0x180074057  mov     edx, eax
0x180074059  call    jsonReturnFromBlob
0x18007405e  mov     rax, [rdi+0C0h]
0x180074065  mov     dl, [rbx+rax]
0x180074068  and     dl, 0Fh
0x18007406b  cmp     dl, 0Bh
0x18007406e  jb      loc_18007413A
0x180074074  mov     edx, 4Ah ; 'J'
0x180074079  mov     rcx, rsi
0x18007407c  call    sqlite3_result_subtype
0x180074081  jmp     loc_18007413A
0x180074086  mov     eax, [rcx+1Ch]
0x180074089  test    eax, eax
0x18007408b  jnz     short loc_180074103
0x18007408d  cmp     dword ptr [rcx+14h], 1
0x180074091  jz      loc_18007413A
0x180074097  call    jsonEachPathLength
0x18007409c  mov     r8d, [rdi+14h]
0x1800740a0  sub     r8d, eax
0x1800740a3  jz      loc_18007413A
0x1800740a9  mov     r9, [rdi+40h]
0x1800740ad  lea     ecx, [rax+1]
0x1800740b0  mov     edx, eax
0x1800740b2  add     rcx, r9
0x1800740b5  cmp     byte ptr [rdx+r9], 5Bh ; '['
0x1800740ba  jnz     short loc_1800740DC
0x1800740bc  dec     r8d
0x1800740bf  mov     [rsp+38h+arg_0], 0
0x1800740c8  mov     r9b, 1
0x1800740cb  lea     rdx, [rsp+38h+arg_0]
0x1800740d0  call    sqlite3Atoi64
0x1800740d5  mov     rdx, [rsp+38h+arg_0]
0x1800740da  jmp     short loc_180074132
0x1800740dc  cmp     byte ptr [rcx], 22h ; '"'
0x1800740df  jnz     short loc_1800740F4
0x1800740e1  lea     edx, [rax+2]
0x1800740e4  add     r8d, 0FFFFFFFDh
0x1800740e8  add     rdx, r9
0x1800740eb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800740ef  jmp     loc_180073F5E
0x1800740f4  dec     r8d
0x1800740f7  mov     rdx, rcx
0x1800740fa  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800740fe  jmp     loc_180073F5E
0x180074103  cmp     byte ptr [rcx+18h], 0Ch
0x180074107  jnz     short loc_180074123
0x180074109  mov     edx, [rdi+0Ch]
0x18007410c  add     rcx, 0C0h
0x180074113  mov     r8, rsi
0x180074116  mov     r9d, 1
0x18007411c  call    jsonReturnFromBlob
0x180074121  jmp     short loc_18007413A
0x180074123  mov     rdx, [rcx+28h]
0x180074127  dec     eax
0x180074129  lea     rax, [rax+rax*2]
0x18007412d  mov     rdx, [rdx+rax*8+10h]
0x180074132  mov     rcx, rsi
0x180074135  call    sqlite3_result_int64
0x18007413a  mov     rbx, [rsp+38h+arg_8]
0x18007413f  xor     eax, eax
0x180074141  mov     rsi, [rsp+38h+arg_10]
0x180074146  add     rsp, 30h
0x18007414a  pop     rdi
0x18007414b  retn
```
