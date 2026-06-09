# IISTypeCopy(_iistype *,_iistype *)

- ea: `0x1800182bc`
- end: `0x1800183a5`
- name: `?IISTypeCopy@@YAJPEAU_iistype@@0@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _iistype *, struct _iistype *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800183ac`

## callees

- `0x1800182bc`
- `0x18001d652`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x18001835a`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18001835a`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018308`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018308`

## pseudocode

```c
__int64 __fastcall IISTypeCopy(struct _iistype *a1, struct _iistype *a2)
{
  int v4; // edx
  int v5; // eax
  LPWSTR v6; // rax
  unsigned int v7; // ebx
  size_t v8; // rbp
  void *v9; // rax

  v4 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 <= 6u )
  {
    if ( v4 != 6 )
    {
      if ( v4 != 1 )
      {
        if ( v4 == 2 )
        {
          *(_DWORD *)a2 = 2;
        }
        else
        {
          if ( v4 != 3 )
          {
            v5 = v4 - 4;
            if ( v4 == 4 )
            {
              *(_DWORD *)a2 = 4;
              goto LABEL_10;
            }
LABEL_17:
            if ( v5 != 1 )
              return (unsigned int)-2147467259;
LABEL_19:
            *(_DWORD *)a2 = v4;
            v8 = *((unsigned int *)a1 + 2);
            *((_DWORD *)a2 + 2) = v8;
            *((_QWORD *)a2 + 2) = 0;
            if ( (_DWORD)v8 )
            {
              v9 = AllocADsMem(v8);
              if ( !v9 )
                return (unsigned int)-2147024882;
              *((_QWORD *)a2 + 2) = v9;
              memcpy_0(v9, *((const void **)a1 + 2), v8);
            }
            return 0;
          }
          *(_DWORD *)a2 = 3;
        }
        goto LABEL_10;
      }
      *(_DWORD *)a2 = 1;
LABEL_27:
      v7 = 0;
      *((_DWORD *)a2 + 2) = *((_DWORD *)a1 + 2);
      return v7;
    }
LABEL_26:
    *(_DWORD *)a2 = v4;
    goto LABEL_27;
  }
  if ( v4 == 7 )
    goto LABEL_26;
  if ( v4 != 8 )
  {
    v5 = v4 - 9;
    if ( v4 == 9 )
      goto LABEL_19;
    goto LABEL_17;
  }
  *(_DWORD *)a2 = 8;
LABEL_10:
  v6 = AllocADsStr(*((LPCWSTR *)a1 + 1));
  v7 = 0;
  *((_QWORD *)a2 + 1) = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  return v7;
}

```

## disassembly

```asm
0x1800182bc  push    rbx
0x1800182be  push    rbp
0x1800182bf  push    rsi
0x1800182c0  push    rdi
0x1800182c1  sub     rsp, 28h
0x1800182c5  mov     rdi, rdx
0x1800182c8  mov     rsi, rcx
0x1800182cb  mov     edx, [rcx]
0x1800182cd  cmp     edx, 6
0x1800182d0  ja      short loc_180018329
0x1800182d2  jz      loc_180018390
0x1800182d8  mov     eax, edx
0x1800182da  sub     eax, 1
0x1800182dd  jz      short loc_180018321
0x1800182df  sub     eax, 1
0x1800182e2  jz      short loc_1800182FE
0x1800182e4  sub     eax, 1
0x1800182e7  jz      short loc_1800182F6
0x1800182e9  sub     eax, 1
0x1800182ec  jnz     short loc_18001833A
0x1800182ee  mov     dword ptr [rdi], 4
0x1800182f4  jmp     short loc_180018304
0x1800182f6  mov     dword ptr [rdi], 3
0x1800182fc  jmp     short loc_180018304
0x1800182fe  mov     dword ptr [rdi], 2
0x180018304  mov     rcx, [rcx+8]; pStr
0x180018308  call    cs:__imp_AllocADsStr
0x18001830e  xor     ebx, ebx
0x180018310  mov     ecx, 8007000Eh
0x180018315  test    rax, rax
0x180018318  mov     [rdi+8], rax
0x18001831c  cmovz   ebx, ecx
0x18001831f  jmp     short loc_18001839A
0x180018321  mov     dword ptr [rdi], 1
0x180018327  jmp     short loc_180018392
0x180018329  mov     eax, edx
0x18001832b  sub     eax, 7
0x18001832e  jz      short loc_180018390
0x180018330  sub     eax, 1
0x180018333  jz      short loc_180018385
0x180018335  sub     eax, 1
0x180018338  jz      short loc_180018346
0x18001833a  cmp     eax, 1
0x18001833d  jz      short loc_180018346
0x18001833f  mov     ebx, 80004005h
0x180018344  jmp     short loc_18001839A
0x180018346  xor     ebx, ebx
0x180018348  mov     [rdi], edx
0x18001834a  mov     ebp, [rcx+8]
0x18001834d  mov     [rdi+8], ebp
0x180018350  mov     [rdi+10h], rbx
0x180018354  test    ebp, ebp
0x180018356  jz      short loc_18001837F
0x180018358  mov     ecx, ebp; cb
0x18001835a  call    cs:__imp_AllocADsMem
0x180018360  test    rax, rax
0x180018363  jnz     short loc_18001836C
0x180018365  mov     ecx, 8007000Eh
0x18001836a  jmp     short loc_180018381
0x18001836c  mov     [rdi+10h], rax
0x180018370  mov     r8, rbp; Size
0x180018373  mov     rdx, [rsi+10h]; Src
0x180018377  mov     rcx, rax; void *
0x18001837a  call    memcpy_0
0x18001837f  mov     ecx, ebx
0x180018381  mov     ebx, ecx
0x180018383  jmp     short loc_18001839A
0x180018385  mov     dword ptr [rdi], 8
0x18001838b  jmp     loc_180018304
0x180018390  mov     [rdi], edx
0x180018392  mov     eax, [rcx+8]
0x180018395  xor     ebx, ebx
0x180018397  mov     [rdi+8], eax
0x18001839a  mov     eax, ebx
0x18001839c  add     rsp, 28h
0x1800183a0  pop     rdi
0x1800183a1  pop     rsi
0x1800183a2  pop     rbp
0x1800183a3  pop     rbx
0x1800183a4  retn
```
