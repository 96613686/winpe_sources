# btreeCreateTable

- ea: `0x180023f14`
- end: `0x180024187`
- name: `btreeCreateTable`
- size: `627`
- prototype: `__int64 __fastcall(__int64, unsigned int *, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x180024190`

## callees

- `0x18001f720`
- `0x1800217c0`
- `0x180021cb8`
- `0x180022288`
- `0x18002395c`
- `0x180023f14`
- `0x180024414`
- `0x180024dd8`
- `0x18004d270`
- `0x18005f2ec`
- `0x180060134`
- `0x18006622c`
- `0x18006636c`
- `0x18006641c`
- `0x18007ca48`
- `0x18007d23c`

## pseudocode

```c
__int64 __fastcall btreeCreateTable(__int64 a1, unsigned int *a2, char a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  unsigned int i; // r10d
  int v9; // eax
  int v10; // r10d
  int v11; // r11d
  int v12; // r8d
  unsigned int v13; // edx
  unsigned int v14; // ebx
  int v15; // r8d
  unsigned int updated; // eax
  int v17; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v22; // [rsp+98h] [rbp+48h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v19 = 0;
  v22 = 0;
  if ( !*(_BYTE *)(v3 + 33) )
  {
    result = allocateBtreePage(v3, (unsigned int)&v19, (unsigned int)&v22, 1, 0);
    if ( (_DWORD)result )
      return result;
    goto LABEL_26;
  }
  v17 = 0;
  v20 = 0;
  invalidateAllOverflowCache(v3);
  sqlite3BtreeGetMeta(a1, 4, &v22);
  if ( v22 > *(_DWORD *)(v3 + 64) )
    return sqlite3ReportError(11, 80663, "database corruption");
  for ( i = v22 + 1; ; i = v11 + 1 )
  {
    v22 = i;
    v9 = ptrmapPageno(v3, i);
    if ( v10 != v9 && v10 != (unsigned int)dword_1800B561C / *(_DWORD *)(v3 + 52) + 1 )
      break;
  }
  result = allocateBtreePage(v3, (unsigned int)&v20, (unsigned int)&v17, v10, 1);
  v21 = result;
  if ( !(_DWORD)result )
  {
    v13 = v22;
    if ( v17 == v22 )
    {
      v19 = v20;
      goto LABEL_21;
    }
    LOBYTE(v21) = 0;
    v18 = 0;
    v14 = saveAllCursors(v3, 0, 0);
    releasePage(v20);
    if ( v14 )
      return v14;
    result = btreeGetPage(v3, v22, &v19, 0);
    if ( !(_DWORD)result )
    {
      v14 = ptrmapGet(v3, v22, &v21, &v18);
      if ( (unsigned __int8)(v21 - 1) <= 1u )
        v14 = sqlite3ReportError(11, 80711, "database corruption");
      if ( v14 )
        goto LABEL_24;
      LOBYTE(v15) = v21;
      v14 = relocatePage(v3, v19, v15, v18, v17, 0);
      releasePage(v19);
      if ( v14 )
        return v14;
      result = btreeGetPage(v3, v22, &v19, 0);
      if ( !(_DWORD)result )
      {
        updated = sqlite3PagerWrite(*(_QWORD *)(v19 + 112));
        v21 = updated;
        if ( updated )
          goto LABEL_23;
        v13 = v22;
LABEL_21:
        LOBYTE(v12) = 1;
        ptrmapPut(v3, v13, v12, 0, (__int64)&v21);
        v14 = v21;
        if ( v21 )
        {
LABEL_24:
          releasePage(v19);
          return v14;
        }
        updated = sqlite3BtreeUpdateMeta(a1, 4, v22);
        if ( updated )
        {
LABEL_23:
          v14 = updated;
          goto LABEL_24;
        }
LABEL_26:
        zeroPage(v19, (a3 & 1) != 0 ? 13 : 10);
        sqlite3PagerUnref(*(_QWORD *)(v19 + 112));
        *a2 = v22;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023f14  mov     [rsp-28h+arg_8], rbx
0x180023f19  push    rbp
0x180023f1a  push    rsi
0x180023f1b  push    rdi
0x180023f1c  push    r14
0x180023f1e  push    r15
0x180023f20  mov     rbp, rsp
0x180023f23  sub     rsp, 50h
0x180023f27  mov     rdi, [rcx+8]
0x180023f2b  mov     r14, rcx
0x180023f2e  mov     [rbp+var_18], 0
0x180023f36  mov     esi, r8d
0x180023f39  mov     [rbp+arg_18], 0
0x180023f40  mov     r15, rdx
0x180023f43  mov     rcx, rdi
0x180023f46  cmp     byte ptr [rdi+21h], 0
0x180023f4a  jz      loc_18002412A
0x180023f50  mov     [rbp+var_20], 0
0x180023f57  mov     [rbp+var_10], 0
0x180023f5f  call    invalidateAllOverflowCache
0x180023f64  lea     r8, [rbp+arg_18]
0x180023f68  mov     edx, 4
0x180023f6d  mov     rcx, r14
0x180023f70  call    sqlite3BtreeGetMeta
0x180023f75  mov     r10d, [rbp+arg_18]
0x180023f79  cmp     r10d, [rdi+40h]
0x180023f7d  jbe     short loc_180023F9A
0x180023f7f  lea     r8, aDatabaseCorrup; "database corruption"
0x180023f86  mov     edx, 13B17h
0x180023f8b  mov     ecx, 0Bh
0x180023f90  call    sqlite3ReportError
0x180023f95  jmp     loc_180024173
0x180023f9a  inc     r10d
0x180023f9d  mov     edx, r10d
0x180023fa0  mov     [rbp+arg_18], r10d
0x180023fa4  mov     rcx, rdi
0x180023fa7  mov     r11d, r10d
0x180023faa  call    ptrmapPageno
0x180023faf  cmp     r10d, eax
0x180023fb2  jz      short loc_180023FC6
0x180023fb4  mov     eax, cs:dword_1800B561C
0x180023fba  xor     edx, edx
0x180023fbc  div     dword ptr [rdi+34h]
0x180023fbf  inc     eax
0x180023fc1  cmp     r10d, eax
0x180023fc4  jnz     short loc_180023FCC
0x180023fc6  lea     r10d, [r11+1]
0x180023fca  jmp     short loc_180023F9D
0x180023fcc  mov     r9d, r10d
0x180023fcf  mov     byte ptr [rsp+50h+var_30], 1
0x180023fd4  lea     r8, [rbp+var_20]
0x180023fd8  mov     rcx, rdi
0x180023fdb  lea     rdx, [rbp+var_10]
0x180023fdf  call    allocateBtreePage
0x180023fe4  mov     [rbp+arg_0], eax
0x180023fe7  test    eax, eax
0x180023fe9  jnz     loc_180024173
0x180023fef  mov     edx, [rbp+arg_18]
0x180023ff2  cmp     [rbp+var_20], edx
0x180023ff5  jz      loc_1800240E1
0x180023ffb  xor     r8d, r8d
0x180023ffe  mov     byte ptr [rbp+arg_0], al
0x180024001  xor     edx, edx
0x180024003  mov     [rbp+var_1C], eax
0x180024006  mov     rcx, rdi
0x180024009  call    saveAllCursors
0x18002400e  mov     rcx, [rbp+var_10]
0x180024012  mov     ebx, eax
0x180024014  call    releasePage
0x180024019  test    ebx, ebx
0x18002401b  jz      short loc_180024024
0x18002401d  mov     eax, ebx
0x18002401f  jmp     loc_180024173
0x180024024  mov     edx, [rbp+arg_18]
0x180024027  lea     r8, [rbp+var_18]
0x18002402b  xor     r9d, r9d
0x18002402e  mov     rcx, rdi
0x180024031  call    btreeGetPage
0x180024036  test    eax, eax
0x180024038  jnz     loc_180024173
0x18002403e  mov     edx, [rbp+arg_18]
0x180024041  lea     r9, [rbp+var_1C]
0x180024045  lea     r8, [rbp+arg_0]
0x180024049  mov     rcx, rdi
0x18002404c  call    ptrmapGet
0x180024051  mov     ebx, eax
0x180024053  mov     al, byte ptr [rbp+arg_0]
0x180024056  dec     al
0x180024058  cmp     al, 1
0x18002405a  ja      short loc_180024074
0x18002405c  lea     r8, aDatabaseCorrup; "database corruption"
0x180024063  mov     edx, 13B47h
0x180024068  mov     ecx, 0Bh
0x18002406d  call    sqlite3ReportError
0x180024072  mov     ebx, eax
0x180024074  test    ebx, ebx
0x180024076  jnz     loc_18002411C
0x18002407c  mov     eax, [rbp+var_20]
0x18002407f  mov     rcx, rdi
0x180024082  mov     r9d, [rbp+var_1C]
0x180024086  mov     r8b, byte ptr [rbp+arg_0]
0x18002408a  mov     rdx, [rbp+var_18]
0x18002408e  mov     [rsp+50h+var_28], ebx
0x180024092  mov     dword ptr [rsp+50h+var_30], eax
0x180024096  call    relocatePage
0x18002409b  mov     rcx, [rbp+var_18]
0x18002409f  mov     ebx, eax
0x1800240a1  call    releasePage
0x1800240a6  test    ebx, ebx
0x1800240a8  jnz     loc_18002401D
0x1800240ae  mov     edx, [rbp+arg_18]
0x1800240b1  lea     r8, [rbp+var_18]
0x1800240b5  xor     r9d, r9d
0x1800240b8  mov     rcx, rdi
0x1800240bb  call    btreeGetPage
0x1800240c0  test    eax, eax
0x1800240c2  jnz     loc_180024173
0x1800240c8  mov     rcx, [rbp+var_18]
0x1800240cc  mov     rcx, [rcx+70h]
0x1800240d0  call    sqlite3PagerWrite
0x1800240d5  mov     [rbp+arg_0], eax
0x1800240d8  test    eax, eax
0x1800240da  jnz     short loc_18002411A
0x1800240dc  mov     edx, [rbp+arg_18]
0x1800240df  jmp     short loc_1800240E9
0x1800240e1  mov     rax, [rbp+var_10]
0x1800240e5  mov     [rbp+var_18], rax
0x1800240e9  lea     rax, [rbp+arg_0]
0x1800240ed  xor     r9d, r9d
0x1800240f0  mov     r8b, 1
0x1800240f3  mov     [rsp+50h+var_30], rax
0x1800240f8  mov     rcx, rdi
0x1800240fb  call    ptrmapPut
0x180024100  mov     ebx, [rbp+arg_0]
0x180024103  test    ebx, ebx
0x180024105  jnz     short loc_18002411C
0x180024107  mov     r8d, [rbp+arg_18]
0x18002410b  lea     edx, [rbx+4]
0x18002410e  mov     rcx, r14
0x180024111  call    sqlite3BtreeUpdateMeta
0x180024116  test    eax, eax
0x180024118  jz      short loc_180024146
0x18002411a  mov     ebx, eax
0x18002411c  mov     rcx, [rbp+var_18]
0x180024120  call    releasePage
0x180024125  jmp     loc_18002401D
0x18002412a  mov     r9d, 1
0x180024130  mov     byte ptr [rsp+50h+var_30], 0
0x180024135  lea     r8, [rbp+arg_18]
0x180024139  lea     rdx, [rbp+var_18]
0x18002413d  call    allocateBtreePage
0x180024142  test    eax, eax
0x180024144  jnz     short loc_180024173
0x180024146  mov     rcx, [rbp+var_18]
0x18002414a  and     sil, 1
0x18002414e  neg     sil
0x180024151  sbb     edx, edx
0x180024153  and     edx, 3
0x180024156  add     edx, 0Ah
0x180024159  call    zeroPage
0x18002415e  mov     rcx, [rbp+var_18]
0x180024162  mov     rcx, [rcx+70h]
0x180024166  call    sqlite3PagerUnref
0x18002416b  mov     eax, [rbp+arg_18]
0x18002416e  mov     [r15], eax
0x180024171  xor     eax, eax
0x180024173  mov     rbx, [rsp+50h+arg_8]
0x18002417b  add     rsp, 50h
0x18002417f  pop     r15
0x180024181  pop     r14
0x180024183  pop     rdi
0x180024184  pop     rsi
0x180024185  pop     rbp
0x180024186  retn
```
