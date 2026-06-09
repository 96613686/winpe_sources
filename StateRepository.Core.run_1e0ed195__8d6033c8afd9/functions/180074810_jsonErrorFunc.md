# jsonErrorFunc

- ea: `0x180074810`
- end: `0x18007490e`
- name: `jsonErrorFunc`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180027a20`
- `0x180028540`
- `0x180048d20`
- `0x180048d38`
- `0x18005ee00`
- `0x180068190`
- `0x18006910e`
- `0x180073c34`
- `0x180074810`
- `0x180074d08`
- `0x1800764cc`
- `0x180078bb4`

## pseudocode

```c
__int64 __fastcall jsonErrorFunc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 result; // rax
  __int64 v15; // rdx
  __int64 i; // rcx
  char v17; // dl
  __int64 v18; // rax
  __int64 v19; // [rsp+20h] [rbp-58h] BYREF
  int v20; // [rsp+28h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-48h]
  __int64 v22; // [rsp+38h] [rbp-40h]
  int v23; // [rsp+40h] [rbp-38h]
  unsigned int v24; // [rsp+48h] [rbp-30h]
  char v25; // [rsp+4Fh] [rbp-29h]

  memset_0(&v19, 0, 0x48u);
  v5 = sqlite3_context_db_handle(a1);
  v6 = *a3;
  v22 = v5;
  v7 = jsonFuncArgMightBeBinary(v6);
  v9 = *a3;
  if ( v7 )
  {
    v10 = sqlite3_value_blob(v9);
    v11 = *a3;
    LOBYTE(v12) = 1;
    v19 = v10;
    v20 = sqlite3ValueBytes(v11, v12);
    v13 = (unsigned int)jsonbValidityCheck(&v19, 0, v20, 1u);
  }
  else
  {
    LOBYTE(v8) = 1;
    result = sqlite3ValueText(v9, v8);
    v21 = result;
    if ( !result )
      return result;
    LOBYTE(v15) = 1;
    v13 = 0;
    v23 = sqlite3ValueBytes(*a3, v15);
    if ( (unsigned int)jsonConvertTextToBlob((__int64)&v19, 0) )
    {
      if ( v25 )
      {
        v13 = -1;
      }
      else
      {
        for ( i = 0; (unsigned int)i < v24; v13 = v18 )
        {
          v17 = *(_BYTE *)(i + v21);
          if ( !v17 )
            break;
          i = (unsigned int)(i + 1);
          v18 = v13 + 1;
          if ( (v17 & 0xC0) == 0x80 )
            v18 = v13;
        }
        ++v13;
      }
    }
  }
  jsonParseReset(&v19);
  if ( v13 >= 0 )
    return sqlite3_result_int64(a1, v13);
  else
    return sqlite3_result_error_nomem(a1);
}

```

## disassembly

```asm
0x180074810  push    rbp
0x180074812  push    rbx
0x180074813  push    rsi
0x180074814  push    rdi
0x180074815  mov     rbp, rsp
0x180074818  sub     rsp, 78h
0x18007481c  xor     edx, edx; Val
0x18007481e  mov     rsi, r8
0x180074821  mov     rdi, rcx
0x180074824  lea     rcx, [rbp+var_58]; void *
0x180074828  lea     r8d, [rdx+48h]; Size
0x18007482c  call    memset_0
0x180074831  mov     rcx, rdi
0x180074834  call    sqlite3_context_db_handle
0x180074839  mov     rcx, [rsi]
0x18007483c  mov     [rbp+var_40], rax
0x180074840  call    jsonFuncArgMightBeBinary
0x180074845  mov     rcx, [rsi]
0x180074848  test    eax, eax
0x18007484a  jz      short loc_18007487A
0x18007484c  call    sqlite3_value_blob
0x180074851  mov     rcx, [rsi]
0x180074854  mov     dl, 1
0x180074856  mov     [rbp+var_58], rax
0x18007485a  call    sqlite3ValueBytes
0x18007485f  mov     r9d, 1
0x180074865  mov     [rbp+var_50], eax
0x180074868  mov     r8d, eax
0x18007486b  lea     rcx, [rbp+var_58]
0x18007486f  xor     edx, edx
0x180074871  call    jsonbValidityCheck
0x180074876  mov     ebx, eax
0x180074878  jmp     short loc_1800748E5
0x18007487a  mov     dl, 1
0x18007487c  call    sqlite3ValueText
0x180074881  mov     [rbp+var_48], rax
0x180074885  test    rax, rax
0x180074888  jz      short loc_180074905
0x18007488a  mov     rcx, [rsi]
0x18007488d  mov     dl, 1
0x18007488f  xor     ebx, ebx
0x180074891  call    sqlite3ValueBytes
0x180074896  xor     edx, edx
0x180074898  mov     [rbp+var_38], eax
0x18007489b  lea     rcx, [rbp+var_58]
0x18007489f  call    jsonConvertTextToBlob
0x1800748a4  test    eax, eax
0x1800748a6  jz      short loc_1800748E5
0x1800748a8  cmp     [rbp+var_29], bl
0x1800748ab  jz      short loc_1800748B3
0x1800748ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800748b1  jmp     short loc_1800748E5
0x1800748b3  mov     r8d, [rbp+var_30]
0x1800748b7  xor     ecx, ecx
0x1800748b9  test    r8d, r8d
0x1800748bc  jz      short loc_1800748E2
0x1800748be  mov     r9, [rbp+var_48]
0x1800748c2  mov     dl, [rcx+r9]
0x1800748c6  test    dl, dl
0x1800748c8  jz      short loc_1800748E2
0x1800748ca  inc     ecx
0x1800748cc  lea     rax, [rbx+1]
0x1800748d0  and     dl, 0C0h
0x1800748d3  cmp     dl, 80h
0x1800748d6  cmovz   rax, rbx
0x1800748da  mov     rbx, rax
0x1800748dd  cmp     ecx, r8d
0x1800748e0  jb      short loc_1800748C2
0x1800748e2  inc     rbx
0x1800748e5  lea     rcx, [rbp+var_58]
0x1800748e9  call    jsonParseReset
0x1800748ee  mov     rcx, rdi
0x1800748f1  test    rbx, rbx
0x1800748f4  jns     short loc_1800748FD
0x1800748f6  call    sqlite3_result_error_nomem
0x1800748fb  jmp     short loc_180074905
0x1800748fd  mov     rdx, rbx
0x180074900  call    sqlite3_result_int64
0x180074905  add     rsp, 78h
0x180074909  pop     rdi
0x18007490a  pop     rsi
0x18007490b  pop     rbx
0x18007490c  pop     rbp
0x18007490d  retn
```
