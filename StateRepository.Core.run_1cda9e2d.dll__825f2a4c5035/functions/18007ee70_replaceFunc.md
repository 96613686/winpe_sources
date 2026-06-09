# replaceFunc

- ea: `0x18007ee70`
- end: `0x18007f0a9`
- name: `replaceFunc`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000aac0`
- `0x180028540`
- `0x180047008`
- `0x180048d20`
- `0x180048d38`
- `0x180066e64`
- `0x180066ec0`
- `0x180068190`
- `0x18007ee70`
- `0x18008f510`
- `0x180099808`
- `0x180099814`

## pseudocode

```c
_BYTE *__fastcall replaceFunc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  _BYTE *result; // rax
  __int64 v8; // rdx
  _BYTE *v9; // r13
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r14
  __int64 v13; // rdx
  _BYTE *v14; // r12
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  size_t v20; // r15
  __int64 v21; // rdx
  __int64 v22; // rbx
  int v23; // ecx
  int v24; // esi
  int i; // ebp
  char *v26; // r9
  char v27; // r13
  int v28; // r13d
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // r13
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // [rsp+28h] [rbp-60h]
  __int64 v35; // [rsp+30h] [rbp-58h]
  void *Src; // [rsp+38h] [rbp-50h]
  _BYTE *v37; // [rsp+40h] [rbp-48h]
  int v38; // [rsp+A0h] [rbp+18h]
  int v39; // [rsp+A8h] [rbp+20h]

  v5 = sqlite3_context_db_handle(a1);
  LOBYTE(v6) = 1;
  v35 = v5;
  result = (_BYTE *)sqlite3ValueText(*a3, v6);
  v37 = result;
  v9 = result;
  if ( result )
  {
    LOBYTE(v8) = 1;
    v10 = sqlite3ValueBytes(*a3, v8);
    LOBYTE(v11) = 1;
    v12 = v10;
    result = (_BYTE *)sqlite3ValueText(a3[1], v11);
    v14 = result;
    if ( result )
    {
      if ( !*result )
      {
        v15 = -1;
        v16 = (unsigned int)v12;
        v17 = (__int64)v9;
        return (_BYTE *)sqlite3_result_text(a1, v17, v16, v15);
      }
      LOBYTE(v13) = 1;
      v18 = sqlite3ValueBytes(a3[1], v13);
      LOBYTE(v19) = 1;
      v20 = v18;
      result = (_BYTE *)sqlite3ValueText(a3[2], v19);
      Src = result;
      if ( result )
      {
        LOBYTE(v21) = 1;
        v39 = sqlite3ValueBytes(a3[2], v21);
        v34 = (int)v12 + 1;
        result = (_BYTE *)contextMalloc(a1);
        v22 = (__int64)result;
        if ( result )
        {
          v38 = 0;
          v23 = v12 - v20;
          v24 = 0;
          for ( i = 0; ; ++i )
          {
            v26 = &v9[i];
            if ( i > v23 )
              break;
            v27 = *v26;
            if ( *v26 == *v14 && !memcmp_0(v26, v14, v20) )
            {
              v28 = v39;
              if ( v39 > (int)v20 )
              {
                v29 = v39 - (int)v20 + v34;
                v34 = v29;
                if ( v29 - 1 > *(int *)(v35 + 136) )
                {
                  sqlite3_result_error_toobig(a1);
                  v33 = v22;
                  return (_BYTE *)sqlite3_free(v33);
                }
                v30 = v38++;
                if ( (v38 & v30) == 0 )
                {
                  v31 = v22;
                  v22 = sqlite3Realloc(v22, (int)v29 - v12 - 1 + v29);
                  if ( !v22 )
                  {
                    sqlite3_result_error_nomem(a1);
                    v33 = v31;
                    return (_BYTE *)sqlite3_free(v33);
                  }
                  v28 = v39;
                }
              }
              memcpy_0((void *)(v22 + v24), Src, v28);
              v32 = v28;
              i = v20 + i - 1;
            }
            else
            {
              *(_BYTE *)(v24 + v22) = v27;
              v32 = 1;
            }
            v9 = v37;
            v23 = v12 - v20;
            v24 += v32;
          }
          memcpy_0((void *)(v22 + v24), &v9[i], (int)v12 - i);
          v15 = (__int64)sqlite3_free;
          v17 = v22;
          v16 = (unsigned int)(v24 - i + v12);
          *(_BYTE *)((int)v16 + v22) = 0;
          return (_BYTE *)sqlite3_result_text(a1, v17, v16, v15);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007ee70  mov     [rsp+arg_0], rbx
0x18007ee75  push    rbp
0x18007ee76  push    rsi
0x18007ee77  push    rdi
0x18007ee78  push    r12
0x18007ee7a  push    r13
0x18007ee7c  push    r14
0x18007ee7e  push    r15
0x18007ee80  sub     rsp, 50h
0x18007ee84  mov     rbx, r8
0x18007ee87  mov     rdi, rcx
0x18007ee8a  call    sqlite3_context_db_handle
0x18007ee8f  mov     rcx, [rbx]
0x18007ee92  mov     dl, 1
0x18007ee94  mov     [rsp+88h+var_58], rax
0x18007ee99  call    sqlite3ValueText
0x18007ee9e  mov     [rsp+88h+var_48], rax
0x18007eea3  mov     r13, rax
0x18007eea6  test    rax, rax
0x18007eea9  jz      loc_18007F091
0x18007eeaf  mov     rcx, [rbx]
0x18007eeb2  mov     dl, 1
0x18007eeb4  call    sqlite3ValueBytes
0x18007eeb9  mov     rcx, [rbx+8]
0x18007eebd  mov     dl, 1
0x18007eebf  movsxd  r14, eax
0x18007eec2  call    sqlite3ValueText
0x18007eec7  mov     r12, rax
0x18007eeca  test    rax, rax
0x18007eecd  jz      loc_18007F091
0x18007eed3  cmp     byte ptr [rax], 0
0x18007eed6  jnz     short loc_18007EEE7
0x18007eed8  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007eedc  mov     r8d, r14d
0x18007eedf  mov     rdx, r13
0x18007eee2  jmp     loc_18007F089
0x18007eee7  mov     rcx, [rbx+8]
0x18007eeeb  mov     dl, 1
0x18007eeed  call    sqlite3ValueBytes
0x18007eef2  mov     rcx, [rbx+10h]
0x18007eef6  mov     dl, 1
0x18007eef8  movsxd  r15, eax
0x18007eefb  call    sqlite3ValueText
0x18007ef00  mov     [rsp+88h+Src], rax
0x18007ef05  test    rax, rax
0x18007ef08  jz      loc_18007F091
0x18007ef0e  mov     rcx, [rbx+10h]
0x18007ef12  mov     dl, 1
0x18007ef14  call    sqlite3ValueBytes
0x18007ef19  lea     ecx, [r14+1]
0x18007ef1d  mov     [rsp+88h+arg_18], eax
0x18007ef24  movsxd  rdx, ecx
0x18007ef27  mov     rcx, rdi
0x18007ef2a  mov     [rsp+88h+var_60], rdx
0x18007ef2f  call    contextMalloc
0x18007ef34  mov     rbx, rax
0x18007ef37  test    rax, rax
0x18007ef3a  jz      loc_18007F091
0x18007ef40  mov     ecx, r14d
0x18007ef43  mov     [rsp+88h+arg_10], 0
0x18007ef4e  sub     ecx, r15d
0x18007ef51  xor     esi, esi
0x18007ef53  mov     [rsp+88h+var_68], ecx
0x18007ef57  xor     ebp, ebp
0x18007ef59  movsxd  r9, ebp
0x18007ef5c  add     r9, r13
0x18007ef5f  cmp     ebp, ecx
0x18007ef61  jg      loc_18007F05C
0x18007ef67  mov     r13b, [r9]
0x18007ef6a  cmp     r13b, [r12]
0x18007ef6e  jnz     loc_18007F01F
0x18007ef74  mov     r8, r15; Size
0x18007ef77  mov     rdx, r12; Buf2
0x18007ef7a  mov     rcx, r9; Buf1
0x18007ef7d  call    memcmp_0
0x18007ef82  test    eax, eax
0x18007ef84  jnz     loc_18007F01F
0x18007ef8a  mov     r13d, [rsp+88h+arg_18]
0x18007ef92  cmp     r13d, r15d
0x18007ef95  jle     short loc_18007F002
0x18007ef97  mov     rdx, [rsp+88h+var_60]
0x18007ef9c  mov     eax, r13d
0x18007ef9f  sub     eax, r15d
0x18007efa2  cdqe
0x18007efa4  add     rdx, rax
0x18007efa7  mov     rax, [rsp+88h+var_58]
0x18007efac  mov     [rsp+88h+var_60], rdx
0x18007efb1  movsxd  rcx, dword ptr [rax+88h]
0x18007efb8  lea     rax, [rdx-1]
0x18007efbc  cmp     rax, rcx
0x18007efbf  jg      loc_18007F04A
0x18007efc5  mov     ecx, [rsp+88h+arg_10]
0x18007efcc  mov     eax, ecx
0x18007efce  inc     ecx
0x18007efd0  mov     [rsp+88h+arg_10], ecx
0x18007efd7  test    eax, ecx
0x18007efd9  jnz     short loc_18007F002
0x18007efdb  movsxd  rcx, edx
0x18007efde  mov     r13, rbx
0x18007efe1  sub     rcx, r14
0x18007efe4  dec     rcx
0x18007efe7  add     rdx, rcx
0x18007efea  mov     rcx, rbx
0x18007efed  call    sqlite3Realloc
0x18007eff2  mov     rbx, rax
0x18007eff5  test    rax, rax
0x18007eff8  jz      short loc_18007F03D
0x18007effa  mov     r13d, [rsp+88h+arg_18]
0x18007f002  mov     rdx, [rsp+88h+Src]; Src
0x18007f007  movsxd  rcx, esi
0x18007f00a  add     rcx, rbx; void *
0x18007f00d  movsxd  r8, r13d; Size
0x18007f010  call    memcpy_0
0x18007f015  dec     ebp
0x18007f017  mov     eax, r13d
0x18007f01a  add     ebp, r15d
0x18007f01d  jmp     short loc_18007F02B
0x18007f01f  movsxd  rax, esi
0x18007f022  mov     [rax+rbx], r13b
0x18007f026  mov     eax, 1
0x18007f02b  mov     r13, [rsp+88h+var_48]
0x18007f030  inc     ebp
0x18007f032  mov     ecx, [rsp+88h+var_68]
0x18007f036  add     esi, eax
0x18007f038  jmp     loc_18007EF59
0x18007f03d  mov     rcx, rdi
0x18007f040  call    sqlite3_result_error_nomem
0x18007f045  mov     rcx, r13
0x18007f048  jmp     short loc_18007F055
0x18007f04a  mov     rcx, rdi
0x18007f04d  call    sqlite3_result_error_toobig
0x18007f052  mov     rcx, rbx
0x18007f055  call    sqlite3_free
0x18007f05a  jmp     short loc_18007F091
0x18007f05c  mov     eax, r14d
0x18007f05f  movsxd  rcx, esi
0x18007f062  sub     eax, ebp
0x18007f064  add     rcx, rbx; void *
0x18007f067  movsxd  r8, eax; Size
0x18007f06a  mov     rdx, r9; Src
0x18007f06d  call    memcpy_0
0x18007f072  sub     esi, ebp
0x18007f074  lea     r9, sqlite3_free
0x18007f07b  mov     rdx, rbx
0x18007f07e  lea     r8d, [rsi+r14]
0x18007f082  movsxd  rax, r8d
0x18007f085  mov     byte ptr [rax+rbx], 0
0x18007f089  mov     rcx, rdi
0x18007f08c  call    sqlite3_result_text
0x18007f091  mov     rbx, [rsp+88h+arg_0]
0x18007f099  add     rsp, 50h
0x18007f09d  pop     r15
0x18007f09f  pop     r14
0x18007f0a1  pop     r13
0x18007f0a3  pop     r12
0x18007f0a5  pop     rdi
0x18007f0a6  pop     rsi
0x18007f0a7  pop     rbp
0x18007f0a8  retn
```
