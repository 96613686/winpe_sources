# triggersReallyExist

- ea: `0x1800c1950`
- end: `0x1800c1b26`
- name: `triggersReallyExist`
- size: `470`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180071a90`
- `0x18007f3e0`
- `0x180084b20`
- `0x18009f4a0`

## callees

- `0x1800743d0`
- `0x180083e40`
- `0x18009e420`
- `0x1800c1950`

## string_xrefs

- `0x1800c1a6b`: `UPDATE`
- `0x1800c19e0`: `DELETE`
- `0x1800c1a3d`: `DELETE`
- `0x1800c1ace`: `DELETE`

## pseudocode

```c
__int64 __fastcall triggersReallyExist(_QWORD *a1, __int64 a2, int a3, int *a4, _DWORD *a5)
{
  int v5; // ebp
  _QWORD *v6; // rbx
  __int64 v7; // rsi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdi
  int v15; // r15d
  __int64 v16; // r14
  int v17; // esi
  int v18; // ebx
  const char *v19; // r8
  int v20; // eax
  __int64 result; // rax
  __int64 v22; // [rsp+20h] [rbp-48h]

  v5 = 0;
  v6 = a1;
  v7 = a2;
  v10 = sqlite3TriggerList();
  v22 = v10;
  v11 = v10;
  if ( v10 )
  {
    if ( (*(_DWORD *)(*v6 + 48LL) & 0x40000LL) == 0 )
    {
      v12 = *(_QWORD *)(v7 + 88);
      if ( v12 )
      {
        if ( v10 == v12 )
        {
          v11 = 0;
          goto LABEL_36;
        }
        if ( *(_QWORD *)(v10 + 64) )
        {
          do
          {
            v13 = *(_QWORD *)(v10 + 64);
            if ( v13 == v12 )
              break;
            v10 = *(_QWORD *)(v10 + 64);
          }
          while ( *(_QWORD *)(v13 + 64) );
          v11 = v22;
        }
        *(_QWORD *)(v10 + 64) = 0;
      }
    }
    v14 = v11;
    while ( 1 )
    {
      v15 = *(unsigned __int8 *)(v14 + 16);
      if ( v15 == a3 )
      {
        v16 = *(_QWORD *)(v14 + 32);
        if ( !v16 || !a4 )
          goto LABEL_32;
        v17 = *a4;
        v18 = 0;
        if ( *a4 > 0 )
        {
          while ( (int)sqlite3IdListIndex(v16, *(_QWORD *)&a4[8 * v18 + 4]) < 0 )
          {
            if ( ++v18 >= v17 )
              goto LABEL_18;
          }
          v6 = a1;
          v7 = a2;
          goto LABEL_32;
        }
LABEL_18:
        v7 = a2;
        v6 = a1;
      }
      if ( (_BYTE)v15 == 0x96 )
      {
        *(_BYTE *)(v14 + 16) = a3;
        if ( *(_BYTE *)(v7 + 63) == 1 )
        {
          if ( a3 != 127 )
          {
            v19 = "UPDATE";
            if ( a3 == 128 )
              v19 = "DELETE";
            sqlite3ErrorMsg(v6, "%s RETURNING is not available on virtual tables", v19);
          }
          *(_BYTE *)(v14 + 17) = 1;
          v20 = 1;
        }
        else
        {
          *(_BYTE *)(v14 + 17) = 2;
          v20 = 2;
        }
        goto LABEL_33;
      }
      if ( !*(_BYTE *)(v14 + 18) || (_BYTE)v15 != 127 || a3 != 129 || v6[21] )
        goto LABEL_34;
LABEL_32:
      v20 = *(unsigned __int8 *)(v14 + 17);
LABEL_33:
      v5 |= v20;
LABEL_34:
      v14 = *(_QWORD *)(v14 + 64);
      if ( !v14 )
      {
        v11 = v22;
        break;
      }
    }
  }
LABEL_36:
  if ( a5 )
    *a5 = v5;
  result = 0;
  if ( v5 )
    return v11;
  return result;
}

```

## disassembly

```asm
0x1800c1950  mov     rax, rsp
0x1800c1953  mov     [rax+10h], rdx
0x1800c1957  mov     [rax+8], rcx
0x1800c195b  push    rbp
0x1800c195c  sub     rsp, 60h
0x1800c1960  mov     [rax+18h], rbx
0x1800c1964  xor     ebp, ebp
0x1800c1966  mov     [rax-10h], rsi
0x1800c196a  mov     rbx, rcx
0x1800c196d  mov     [rax-20h], r12
0x1800c1971  mov     rsi, rdx
0x1800c1974  mov     [rax-28h], r13
0x1800c1978  mov     r12d, r8d
0x1800c197b  mov     r13, r9
0x1800c197e  call    sqlite3TriggerList
0x1800c1983  mov     [rsp+68h+var_48], rax
0x1800c1988  mov     rcx, rax
0x1800c198b  test    rax, rax
0x1800c198e  jz      loc_1800C1AF2
0x1800c1994  mov     r9, [rbx]
0x1800c1997  mov     r8d, [r9+30h]
0x1800c199b  bt      r8, 12h
0x1800c19a0  jb      short loc_1800C19DB
0x1800c19a2  mov     rdx, [rsi+58h]
0x1800c19a6  test    rdx, rdx
0x1800c19a9  jz      short loc_1800C19DB
0x1800c19ab  cmp     rax, rdx
0x1800c19ae  jnz     short loc_1800C19B7
0x1800c19b0  xor     ecx, ecx
0x1800c19b2  jmp     loc_1800C1AF2
0x1800c19b7  cmp     [rax+40h], rbp
0x1800c19bb  jz      short loc_1800C19D7
0x1800c19bd  nop     dword ptr [rax]
0x1800c19c0  mov     rcx, [rax+40h]
0x1800c19c4  cmp     rcx, rdx
0x1800c19c7  jz      short loc_1800C19D2
0x1800c19c9  mov     rax, rcx
0x1800c19cc  cmp     [rcx+40h], rbp
0x1800c19d0  jnz     short loc_1800C19C0
0x1800c19d2  mov     rcx, [rsp+68h+var_48]
0x1800c19d7  mov     [rax+40h], rbp
0x1800c19db  mov     [rsp+68h+var_18], rdi
0x1800c19e0  lea     rax, aDelete; "DELETE"
0x1800c19e7  mov     [rsp+68h+var_30], r14
0x1800c19ec  mov     rdi, rcx
0x1800c19ef  mov     [rsp+68h+var_38], r15
0x1800c19f4  movzx   r15d, byte ptr [rdi+10h]
0x1800c19f9  cmp     r15d, r12d
0x1800c19fc  jnz     short loc_1800C1A4E
0x1800c19fe  mov     r14, [rdi+20h]
0x1800c1a02  test    r14, r14
0x1800c1a05  jz      loc_1800C1AC4
0x1800c1a0b  test    r13, r13
0x1800c1a0e  jz      loc_1800C1AC4
0x1800c1a14  mov     esi, [r13+0]
0x1800c1a18  xor     ebx, ebx
0x1800c1a1a  test    esi, esi
0x1800c1a1c  jle     short loc_1800C1A44
0x1800c1a1e  xchg    ax, ax
0x1800c1a20  mov     edx, ebx
0x1800c1a22  mov     rcx, r14
0x1800c1a25  shl     rdx, 5
0x1800c1a29  mov     rdx, [rdx+r13+10h]
0x1800c1a2e  call    sqlite3IdListIndex
0x1800c1a33  test    eax, eax
0x1800c1a35  jns     short loc_1800C1A8F
0x1800c1a37  inc     ebx
0x1800c1a39  cmp     ebx, esi
0x1800c1a3b  jl      short loc_1800C1A20
0x1800c1a3d  lea     rax, aDelete; "DELETE"
0x1800c1a44  mov     rsi, [rsp+68h+arg_8]
0x1800c1a49  mov     rbx, [rsp+68h+arg_0]
0x1800c1a4e  cmp     r15b, 96h
0x1800c1a52  jnz     short loc_1800C1AA5
0x1800c1a54  mov     [rdi+10h], r12b
0x1800c1a58  cmp     byte ptr [rsi+3Fh], 1
0x1800c1a5c  jnz     short loc_1800C1A9B
0x1800c1a5e  cmp     r12d, 7Fh
0x1800c1a62  jz      short loc_1800C1A85
0x1800c1a64  cmp     r12d, 80h
0x1800c1a6b  lea     r8, aUpdate; "UPDATE"
0x1800c1a72  lea     rdx, aSReturningIsNo; "%s RETURNING is not available on virtua"...
0x1800c1a79  mov     rcx, rbx
0x1800c1a7c  cmovz   r8, rax
0x1800c1a80  call    sqlite3ErrorMsg
0x1800c1a85  mov     al, 1
0x1800c1a87  mov     [rdi+11h], al
0x1800c1a8a  movzx   eax, al
0x1800c1a8d  jmp     short loc_1800C1AC8
0x1800c1a8f  mov     rbx, [rsp+68h+arg_0]
0x1800c1a94  mov     rsi, [rsp+68h+arg_8]
0x1800c1a99  jmp     short loc_1800C1AC4
0x1800c1a9b  mov     al, 2
0x1800c1a9d  mov     [rdi+11h], al
0x1800c1aa0  movzx   eax, al
0x1800c1aa3  jmp     short loc_1800C1AC8
0x1800c1aa5  cmp     byte ptr [rdi+12h], 0
0x1800c1aa9  jz      short loc_1800C1ACA
0x1800c1aab  cmp     r15b, 7Fh
0x1800c1aaf  jnz     short loc_1800C1ACA
0x1800c1ab1  cmp     r12d, 81h
0x1800c1ab8  jnz     short loc_1800C1ACA
0x1800c1aba  cmp     qword ptr [rbx+0A8h], 0
0x1800c1ac2  jnz     short loc_1800C1ACA
0x1800c1ac4  movzx   eax, byte ptr [rdi+11h]
0x1800c1ac8  or      ebp, eax
0x1800c1aca  mov     rdi, [rdi+40h]
0x1800c1ace  lea     rax, aDelete; "DELETE"
0x1800c1ad5  test    rdi, rdi
0x1800c1ad8  jnz     loc_1800C19F4
0x1800c1ade  mov     r15, [rsp+68h+var_38]
0x1800c1ae3  mov     r14, [rsp+68h+var_30]
0x1800c1ae8  mov     rdi, [rsp+68h+var_18]
0x1800c1aed  mov     rcx, [rsp+68h+var_48]
0x1800c1af2  mov     rax, [rsp+68h+arg_20]
0x1800c1afa  mov     r13, [rsp+68h+var_28]
0x1800c1aff  mov     r12, [rsp+68h+var_20]
0x1800c1b04  mov     rsi, [rsp+68h+var_10]
0x1800c1b09  mov     rbx, [rsp+68h+arg_10]
0x1800c1b11  test    rax, rax
0x1800c1b14  jz      short loc_1800C1B18
0x1800c1b16  mov     [rax], ebp
0x1800c1b18  xor     eax, eax
0x1800c1b1a  test    ebp, ebp
0x1800c1b1c  cmovnz  rax, rcx
0x1800c1b20  add     rsp, 60h
0x1800c1b24  pop     rbp
0x1800c1b25  retn
```
