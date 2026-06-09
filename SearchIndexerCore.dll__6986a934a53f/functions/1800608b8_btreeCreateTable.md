# btreeCreateTable

- ea: `0x1800608b8`
- end: `0x180060b31`
- name: `btreeCreateTable`
- size: `633`
- prototype: `__int64 __fastcall(__int64, unsigned int *, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x180060868`

## callees

- `0x18002619c`
- `0x18002625c`
- `0x1800263c0`
- `0x180027660`
- `0x180028090`
- `0x180032470`
- `0x18003747c`
- `0x18003753c`
- `0x180038f48`
- `0x18005f878`
- `0x1800608b8`
- `0x180060c4c`
- `0x1800630c4`
- `0x1800736cc`
- `0x1800750b0`
- `0x18008c7cc`

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
LABEL_4:
    zeroPage(v19, (a3 & 1) != 0 ? 13 : 10);
    sqlite3PagerUnref(*(_QWORD *)(v19 + 112));
    *a2 = v22;
    return 0;
  }
  v17 = 0;
  v20 = 0;
  invalidateAllOverflowCache(v3);
  sqlite3BtreeGetMeta(a1, 4, &v22);
  if ( v22 > *(_DWORD *)(v3 + 64) )
    return sqlite3ReportError(11, 80766, "database corruption");
  for ( i = v22 + 1; ; i = v11 + 1 )
  {
    v22 = i;
    v9 = ptrmapPageno(v3, i);
    if ( v10 != v9 && v10 != (unsigned int)dword_1800D085C / *(_DWORD *)(v3 + 52) + 1 )
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
      goto LABEL_26;
    }
    LOBYTE(v21) = 0;
    v18 = 0;
    v14 = saveAllCursors(v3, 0, 0);
    releasePage(v20);
    if ( v14 )
      return v14;
    result = btreeGetPage(v3, v22, &v19, 0);
    if ( (_DWORD)result )
      return result;
    v14 = ptrmapGet(v3, v22, &v21, &v18);
    if ( (unsigned __int8)(v21 - 1) <= 1u )
      v14 = sqlite3ReportError(11, 80814, "database corruption");
    if ( v14 )
      goto LABEL_23;
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
        goto LABEL_22;
      v13 = v22;
LABEL_26:
      LOBYTE(v12) = 1;
      ptrmapPut(v3, v13, v12, 0, (__int64)&v21);
      v14 = v21;
      if ( v21 )
        goto LABEL_23;
      updated = sqlite3BtreeUpdateMeta(a1, 4, v22);
      if ( !updated )
        goto LABEL_4;
LABEL_22:
      v14 = updated;
LABEL_23:
      releasePage(v19);
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800608b8  mov     [rsp-28h+arg_8], rbx
0x1800608bd  push    rbp
0x1800608be  push    rsi
0x1800608bf  push    rdi
0x1800608c0  push    r14
0x1800608c2  push    r15
0x1800608c4  mov     rbp, rsp
0x1800608c7  sub     rsp, 50h
0x1800608cb  mov     rdi, [rcx+8]
0x1800608cf  mov     r14, rcx
0x1800608d2  mov     [rbp+var_18], 0
0x1800608da  mov     esi, r8d
0x1800608dd  mov     [rbp+arg_18], 0
0x1800608e4  mov     r15, rdx
0x1800608e7  mov     rcx, rdi
0x1800608ea  cmp     byte ptr [rdi+21h], 0
0x1800608ee  jnz     short loc_18006094F
0x1800608f0  mov     r9d, 1
0x1800608f6  mov     byte ptr [rsp+50h+var_30], 0
0x1800608fb  lea     r8, [rbp+arg_18]
0x1800608ff  lea     rdx, [rbp+var_18]
0x180060903  call    allocateBtreePage
0x180060908  test    eax, eax
0x18006090a  jz      short loc_180060920
0x18006090c  mov     rbx, [rsp+50h+arg_8]
0x180060914  add     rsp, 50h
0x180060918  pop     r15
0x18006091a  pop     r14
0x18006091c  pop     rdi
0x18006091d  pop     rsi
0x18006091e  pop     rbp
0x18006091f  retn
0x180060920  mov     rcx, [rbp+var_18]
0x180060924  and     sil, 1
0x180060928  neg     sil
0x18006092b  sbb     edx, edx
0x18006092d  and     edx, 3
0x180060930  add     edx, 0Ah
0x180060933  call    zeroPage
0x180060938  mov     rcx, [rbp+var_18]
0x18006093c  mov     rcx, [rcx+70h]
0x180060940  call    sqlite3PagerUnref
0x180060945  mov     eax, [rbp+arg_18]
0x180060948  mov     [r15], eax
0x18006094b  xor     eax, eax
0x18006094d  jmp     short loc_18006090C
0x18006094f  mov     [rbp+var_20], 0
0x180060956  mov     [rbp+var_10], 0
0x18006095e  call    invalidateAllOverflowCache
0x180060963  lea     r8, [rbp+arg_18]
0x180060967  mov     edx, 4
0x18006096c  mov     rcx, r14
0x18006096f  call    sqlite3BtreeGetMeta
0x180060974  mov     r10d, [rbp+arg_18]
0x180060978  cmp     r10d, [rdi+40h]
0x18006097c  jbe     short loc_180060999
0x18006097e  lea     r8, aDatabaseCorrup; "database corruption"
0x180060985  mov     edx, 13B7Eh
0x18006098a  mov     ecx, 0Bh
0x18006098f  call    sqlite3ReportError
0x180060994  jmp     loc_18006090C
0x180060999  inc     r10d
0x18006099c  mov     edx, r10d
0x18006099f  mov     [rbp+arg_18], r10d
0x1800609a3  mov     rcx, rdi
0x1800609a6  mov     r11d, r10d
0x1800609a9  call    ptrmapPageno
0x1800609ae  cmp     r10d, eax
0x1800609b1  jz      loc_180060AD7
0x1800609b7  mov     eax, cs:dword_1800D085C
0x1800609bd  xor     edx, edx
0x1800609bf  div     dword ptr [rdi+34h]
0x1800609c2  inc     eax
0x1800609c4  cmp     r10d, eax
0x1800609c7  jz      loc_180060AD7
0x1800609cd  mov     r9d, r10d
0x1800609d0  mov     byte ptr [rsp+50h+var_30], 1
0x1800609d5  lea     r8, [rbp+var_20]
0x1800609d9  mov     rcx, rdi
0x1800609dc  lea     rdx, [rbp+var_10]
0x1800609e0  call    allocateBtreePage
0x1800609e5  mov     [rbp+arg_0], eax
0x1800609e8  test    eax, eax
0x1800609ea  jnz     loc_18006090C
0x1800609f0  mov     edx, [rbp+arg_18]
0x1800609f3  cmp     [rbp+var_20], edx
0x1800609f6  jz      loc_180060AF2
0x1800609fc  xor     r8d, r8d
0x1800609ff  mov     byte ptr [rbp+arg_0], al
0x180060a02  xor     edx, edx
0x180060a04  mov     [rbp+var_1C], eax
0x180060a07  mov     rcx, rdi
0x180060a0a  call    saveAllCursors
0x180060a0f  mov     rcx, [rbp+var_10]
0x180060a13  mov     ebx, eax
0x180060a15  call    releasePage
0x180060a1a  test    ebx, ebx
0x180060a1c  jnz     loc_180060AEB
0x180060a22  mov     edx, [rbp+arg_18]
0x180060a25  lea     r8, [rbp+var_18]
0x180060a29  xor     r9d, r9d
0x180060a2c  mov     rcx, rdi
0x180060a2f  call    btreeGetPage
0x180060a34  test    eax, eax
0x180060a36  jnz     loc_18006090C
0x180060a3c  mov     edx, [rbp+arg_18]
0x180060a3f  lea     r9, [rbp+var_1C]
0x180060a43  lea     r8, [rbp+arg_0]
0x180060a47  mov     rcx, rdi
0x180060a4a  call    ptrmapGet
0x180060a4f  mov     ebx, eax
0x180060a51  mov     al, byte ptr [rbp+arg_0]
0x180060a54  dec     al
0x180060a56  cmp     al, 1
0x180060a58  ja      short loc_180060A72
0x180060a5a  lea     r8, aDatabaseCorrup; "database corruption"
0x180060a61  mov     edx, 13BAEh
0x180060a66  mov     ecx, 0Bh
0x180060a6b  call    sqlite3ReportError
0x180060a70  mov     ebx, eax
0x180060a72  test    ebx, ebx
0x180060a74  jnz     short loc_180060AE2
0x180060a76  mov     eax, [rbp+var_20]
0x180060a79  mov     rcx, rdi
0x180060a7c  mov     r9d, [rbp+var_1C]
0x180060a80  mov     r8b, byte ptr [rbp+arg_0]
0x180060a84  mov     rdx, [rbp+var_18]
0x180060a88  mov     [rsp+50h+var_28], ebx
0x180060a8c  mov     dword ptr [rsp+50h+var_30], eax
0x180060a90  call    relocatePage
0x180060a95  mov     rcx, [rbp+var_18]
0x180060a99  mov     ebx, eax
0x180060a9b  call    releasePage
0x180060aa0  test    ebx, ebx
0x180060aa2  jnz     short loc_180060AEB
0x180060aa4  mov     edx, [rbp+arg_18]
0x180060aa7  lea     r8, [rbp+var_18]
0x180060aab  xor     r9d, r9d
0x180060aae  mov     rcx, rdi
0x180060ab1  call    btreeGetPage
0x180060ab6  test    eax, eax
0x180060ab8  jnz     loc_18006090C
0x180060abe  mov     rcx, [rbp+var_18]
0x180060ac2  mov     rcx, [rcx+70h]
0x180060ac6  call    sqlite3PagerWrite
0x180060acb  mov     [rbp+arg_0], eax
0x180060ace  test    eax, eax
0x180060ad0  jnz     short loc_180060AE0
0x180060ad2  mov     edx, [rbp+arg_18]
0x180060ad5  jmp     short loc_180060AFA
0x180060ad7  lea     r10d, [r11+1]
0x180060adb  jmp     loc_18006099C
0x180060ae0  mov     ebx, eax
0x180060ae2  mov     rcx, [rbp+var_18]
0x180060ae6  call    releasePage
0x180060aeb  mov     eax, ebx
0x180060aed  jmp     loc_18006090C
0x180060af2  mov     rax, [rbp+var_10]
0x180060af6  mov     [rbp+var_18], rax
0x180060afa  lea     rax, [rbp+arg_0]
0x180060afe  xor     r9d, r9d
0x180060b01  mov     r8b, 1
0x180060b04  mov     [rsp+50h+var_30], rax
0x180060b09  mov     rcx, rdi
0x180060b0c  call    ptrmapPut
0x180060b11  mov     ebx, [rbp+arg_0]
0x180060b14  test    ebx, ebx
0x180060b16  jnz     short loc_180060AE2
0x180060b18  mov     r8d, [rbp+arg_18]
0x180060b1c  lea     edx, [rbx+4]
0x180060b1f  mov     rcx, r14
0x180060b22  call    sqlite3BtreeUpdateMeta
0x180060b27  test    eax, eax
0x180060b29  jz      loc_180060920
0x180060b2f  jmp     short loc_180060AE0
```
