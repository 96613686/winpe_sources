# sqlite3CreateFunc

- ea: `0x180070370`
- end: `0x180070671`
- name: `sqlite3CreateFunc`
- size: `769`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800410f0`
- `0x180070370`
- `0x180089b1c`
- `0x1800a7dd0`

## callees

- `0x180070370`
- `0x1800716fc`
- `0x180073b98`
- `0x180078410`
- `0x180081230`
- `0x1800ca010`

## string_xrefs

- `0x180070573`: `unable to delete/modify user-function due to active statements`

## pseudocode

```c
__int64 __fastcall sqlite3CreateFunc(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11)
{
  __int64 v14; // rsi
  __int64 v15; // rax
  int v16; // ebx
  int v17; // r12d
  __int64 result; // rax
  char *Function; // rax
  __int64 v20; // r9
  __int64 i; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rdi
  int v26; // [rsp+20h] [rbp-88h]
  int v27; // [rsp+20h] [rbp-88h]

  if ( !a2 )
    return sqlite3MisuseError(182120);
  v14 = a6;
  if ( a6 )
  {
    if ( a8 )
      return sqlite3MisuseError(182120);
  }
  if ( (a8 == 0) != (a7 == 0) )
    return sqlite3MisuseError(182120);
  if ( (a9 == 0) != (a10 == 0) )
    return sqlite3MisuseError(182120);
  if ( a3 + 1 > 0x80 )
    return sqlite3MisuseError(182120);
  v15 = -1;
  do
    ++v15;
  while ( *(_BYTE *)(a2 + v15) );
  if ( ((unsigned int)v15 & 0x3FFFFFFF) > 0xFF )
    return sqlite3MisuseError(182120);
  v16 = a4 & 7;
  v17 = a4 & 0x1380800 ^ 0x200000;
  if ( v16 == 1 || v16 == 2 || v16 == 3 )
  {
LABEL_20:
    LOBYTE(a4) = v16;
    LOBYTE(v26) = 0;
    Function = (char *)sqlite3FindFunction(a1, a2, a3, a4, v26);
    if ( Function && (*((_DWORD *)Function + 1) & 3) == v16 && *Function == a3 )
    {
      if ( *(_DWORD *)(a1 + 216) )
      {
        sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify user-function due to active statements", v20);
        return 5;
      }
      for ( i = *(_QWORD *)(a1 + 8); i; i = *(_QWORD *)(i + 16) )
      {
        *(_DWORD *)(i + 200) &= ~2u;
        *(_DWORD *)(i + 200) |= 1u;
      }
    }
    else if ( !a6 && !a8 )
    {
      return 0;
    }
    LOBYTE(v20) = v16;
    LOBYTE(v27) = 1;
    v22 = sqlite3FindFunction(a1, a2, a3, v20, v27);
    v23 = v22;
    if ( !v22 )
      return 7;
    v24 = *(_QWORD *)(v22 + 64);
    if ( v24 )
    {
      if ( (*(_DWORD *)v24)-- == 1 )
      {
        (*(void (__fastcall **)(_QWORD))(v24 + 8))(*(_QWORD *)(v24 + 16));
        sqlite3DbFreeNN(a1);
      }
    }
    if ( a11 )
      ++*a11;
    *(_DWORD *)(v23 + 4) &= 3u;
    *(_DWORD *)(v23 + 4) |= v17;
    *(_QWORD *)(v23 + 40) = a9;
    if ( !a6 )
      v14 = a7;
    *(_QWORD *)(v23 + 48) = a10;
    *(_QWORD *)(v23 + 24) = v14;
    *(_QWORD *)(v23 + 8) = a5;
    *(_QWORD *)(v23 + 64) = a11;
    *(_QWORD *)(v23 + 32) = a8;
    *(_BYTE *)v23 = a3;
    return 0;
  }
  if ( v16 == 4 )
  {
    v16 = 2;
    goto LABEL_20;
  }
  if ( v16 != 5 )
  {
    v16 = 1;
    goto LABEL_20;
  }
  result = sqlite3CreateFunc(a1, a2, a3, (v17 | 1) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
  if ( !(_DWORD)result )
  {
    result = sqlite3CreateFunc(a1, a2, a3, (v17 | 2) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
    if ( !(_DWORD)result )
    {
      v16 = 3;
      goto LABEL_20;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180070370  push    rbx
0x180070372  push    rbp
0x180070373  push    rsi
0x180070374  push    rdi
0x180070375  push    r12
0x180070377  push    r13
0x180070379  push    r14
0x18007037b  push    r15
0x18007037d  sub     rsp, 68h
0x180070381  mov     ebx, r9d
0x180070384  mov     r13d, r8d
0x180070387  mov     rdi, rdx
0x18007038a  mov     rbp, rcx
0x18007038d  test    rdx, rdx
0x180070390  jz      loc_180070656
0x180070396  mov     rsi, [rsp+0A8h+arg_28]
0x18007039e  mov     r14, [rsp+0A8h+arg_38]
0x1800703a6  test    rsi, rsi
0x1800703a9  jz      short loc_1800703B4
0x1800703ab  test    r14, r14
0x1800703ae  jnz     loc_180070656
0x1800703b4  mov     rdx, [rsp+0A8h+arg_30]
0x1800703bc  xor     ecx, ecx
0x1800703be  test    rdx, rdx
0x1800703c1  setz    cl
0x1800703c4  xor     eax, eax
0x1800703c6  test    r14, r14
0x1800703c9  setz    al
0x1800703cc  cmp     eax, ecx
0x1800703ce  jnz     loc_180070656
0x1800703d4  mov     r8, [rsp+0A8h+arg_40]
0x1800703dc  xor     ecx, ecx
0x1800703de  mov     r10, [rsp+0A8h+arg_48]
0x1800703e6  test    r8, r8
0x1800703e9  setz    cl
0x1800703ec  xor     eax, eax
0x1800703ee  test    r10, r10
0x1800703f1  setz    al
0x1800703f4  cmp     ecx, eax
0x1800703f6  jnz     loc_180070656
0x1800703fc  lea     eax, [r13+1]
0x180070400  cmp     eax, 80h
0x180070405  ja      loc_180070656
0x18007040b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007040f  inc     rax
0x180070412  cmp     byte ptr [rdi+rax], 0
0x180070416  jnz     short loc_18007040F
0x180070418  and     eax, 3FFFFFFFh
0x18007041d  cmp     eax, 0FFh
0x180070422  ja      loc_180070656
0x180070428  mov     r15, [rsp+0A8h+arg_50]
0x180070430  mov     r12d, ebx
0x180070433  and     r12d, 1380800h
0x18007043a  and     ebx, 7
0x18007043d  mov     r11d, 200000h
0x180070443  mov     ecx, ebx
0x180070445  xor     r12d, r11d
0x180070448  sub     ecx, 1
0x18007044b  jz      loc_180070535
0x180070451  sub     ecx, 1
0x180070454  jz      loc_180070535
0x18007045a  sub     ecx, 1
0x18007045d  jz      loc_180070535
0x180070463  sub     ecx, 1
0x180070466  jz      loc_180070530
0x18007046c  cmp     ecx, 1
0x18007046f  jz      short loc_18007047B
0x180070471  mov     ebx, 1
0x180070476  jmp     loc_180070535
0x18007047b  mov     rax, [rsp+0A8h+arg_20]
0x180070483  mov     r9d, r12d
0x180070486  mov     [rsp+0A8h+var_58], r15
0x18007048b  or      r9d, 1
0x18007048f  mov     [rsp+0A8h+var_60], r10
0x180070494  xor     r9d, r11d
0x180070497  mov     [rsp+0A8h+var_68], r8
0x18007049c  mov     rcx, rbp
0x18007049f  mov     [rsp+0A8h+var_70], r14
0x1800704a4  mov     r8d, r13d
0x1800704a7  mov     [rsp+0A8h+var_78], rdx
0x1800704ac  mov     rdx, rdi
0x1800704af  mov     [rsp+0A8h+var_80], rsi
0x1800704b4  mov     [rsp+0A8h+var_88], rax
0x1800704b9  call    sqlite3CreateFunc
0x1800704be  test    eax, eax
0x1800704c0  jnz     loc_180070660
0x1800704c6  mov     rax, [rsp+0A8h+arg_48]
0x1800704ce  mov     r9d, r12d
0x1800704d1  mov     [rsp+0A8h+var_58], r15
0x1800704d6  or      r9d, 2
0x1800704da  mov     [rsp+0A8h+var_60], rax
0x1800704df  btc     r9d, 15h
0x1800704e4  mov     rax, [rsp+0A8h+arg_40]
0x1800704ec  mov     r8d, r13d
0x1800704ef  mov     [rsp+0A8h+var_68], rax
0x1800704f4  mov     rdx, rdi
0x1800704f7  mov     rax, [rsp+0A8h+arg_30]
0x1800704ff  mov     rcx, rbp
0x180070502  mov     [rsp+0A8h+var_70], r14
0x180070507  mov     [rsp+0A8h+var_78], rax
0x18007050c  mov     rax, [rsp+0A8h+arg_20]
0x180070514  mov     [rsp+0A8h+var_80], rsi
0x180070519  mov     [rsp+0A8h+var_88], rax
0x18007051e  call    sqlite3CreateFunc
0x180070523  test    eax, eax
0x180070525  jnz     loc_180070660
0x18007052b  lea     ebx, [rax+3]
0x18007052e  jmp     short loc_180070535
0x180070530  mov     ebx, 2
0x180070535  mov     r9b, bl
0x180070538  mov     byte ptr [rsp+0A8h+var_88], 0
0x18007053d  mov     r8d, r13d
0x180070540  mov     rdx, rdi
0x180070543  mov     rcx, rbp
0x180070546  call    sqlite3FindFunction
0x18007054b  mov     rcx, rax
0x18007054e  test    rax, rax
0x180070551  jz      short loc_1800705CE
0x180070553  mov     eax, [rax+4]
0x180070556  and     eax, 3
0x180070559  cmp     eax, ebx
0x18007055b  jnz     short loc_1800705CE
0x18007055d  movsx   eax, byte ptr [rcx]
0x180070560  cmp     eax, r13d
0x180070563  jnz     short loc_1800705CE
0x180070565  cmp     dword ptr [rbp+0D8h], 0
0x18007056c  jz      short loc_18007058B
0x18007056e  mov     ebx, 5
0x180070573  lea     r8, aUnableToDelete_0; "unable to delete/modify user-function d"...
0x18007057a  mov     edx, ebx
0x18007057c  mov     rcx, rbp
0x18007057f  call    sqlite3ErrorWithMsg
0x180070584  mov     eax, ebx
0x180070586  jmp     loc_180070660
0x18007058b  mov     rax, [rbp+8]
0x18007058f  jmp     short loc_1800705A3
0x180070591  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x180070598  or      dword ptr [rax+0C8h], 1
0x18007059f  mov     rax, [rax+10h]
0x1800705a3  test    rax, rax
0x1800705a6  jnz     short loc_180070591
0x1800705a8  mov     r9b, bl
0x1800705ab  mov     byte ptr [rsp+0A8h+var_88], 1
0x1800705b0  mov     r8d, r13d
0x1800705b3  mov     rdx, rdi
0x1800705b6  mov     rcx, rbp
0x1800705b9  call    sqlite3FindFunction
0x1800705be  mov     rbx, rax
0x1800705c1  test    rax, rax
0x1800705c4  jnz     short loc_1800705DF
0x1800705c6  lea     eax, [rbx+7]
0x1800705c9  jmp     loc_180070660
0x1800705ce  test    rsi, rsi
0x1800705d1  jnz     short loc_1800705A8
0x1800705d3  test    r14, r14
0x1800705d6  jnz     short loc_1800705A8
0x1800705d8  xor     eax, eax
0x1800705da  jmp     loc_180070660
0x1800705df  mov     rdi, [rax+40h]
0x1800705e3  test    rdi, rdi
0x1800705e6  jz      short loc_180070605
0x1800705e8  sub     dword ptr [rdi], 1
0x1800705eb  jnz     short loc_180070605
0x1800705ed  mov     rcx, [rdi+10h]
0x1800705f1  mov     rax, [rdi+8]
0x1800705f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800705fa  mov     rdx, rdi
0x1800705fd  mov     rcx, rbp
0x180070600  call    sqlite3DbFreeNN
0x180070605  test    r15, r15
0x180070608  jz      short loc_18007060D
0x18007060a  inc     dword ptr [r15]
0x18007060d  and     dword ptr [rbx+4], 3
0x180070611  mov     rax, [rsp+0A8h+arg_40]
0x180070619  or      [rbx+4], r12d
0x18007061d  mov     [rbx+28h], rax
0x180070621  test    rsi, rsi
0x180070624  mov     rax, [rsp+0A8h+arg_48]
0x18007062c  cmovz   rsi, [rsp+0A8h+arg_30]
0x180070635  mov     [rbx+30h], rax
0x180070639  mov     rax, [rsp+0A8h+arg_20]
0x180070641  mov     [rbx+18h], rsi
0x180070645  mov     [rbx+8], rax
0x180070649  mov     [rbx+40h], r15
0x18007064d  mov     [rbx+20h], r14
0x180070651  mov     [rbx], r13b
0x180070654  jmp     short loc_1800705D8
0x180070656  mov     ecx, 2C768h
0x18007065b  call    sqlite3MisuseError
0x180070660  add     rsp, 68h
0x180070664  pop     r15
0x180070666  pop     r14
0x180070668  pop     r13
0x18007066a  pop     r12
0x18007066c  pop     rdi
0x18007066d  pop     rsi
0x18007066e  pop     rbp
0x18007066f  pop     rbx
0x180070670  retn
```
