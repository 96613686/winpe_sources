# pagerUnlockAndRollback

- ea: `0x180026804`
- end: `0x180026895`
- name: `pagerUnlockAndRollback`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180026410`
- `0x180028104`
- `0x180036690`
- `0x180040ecc`
- `0x180046508`
- `0x180046ca4`

## callees

- `0x180026804`
- `0x18003f890`
- `0x18003f8b0`
- `0x180040258`
- `0x180041314`
- `0x1800487ec`
- `0x18008a350`

## pseudocode

```c
__int64 __fastcall pagerUnlockAndRollback(__int64 a1)
{
  unsigned __int8 v1; // al
  int v4; // edi
  char v5; // bl

  v1 = *(_BYTE *)(a1 + 21);
  if ( v1 == 6 )
  {
    if ( *(_BYTE *)(a1 + 9) == 4 && **(_QWORD **)(a1 + 80) )
    {
      v4 = *(_DWORD *)(a1 + 48);
      v5 = *(_BYTE *)(a1 + 22);
      *(_WORD *)(a1 + 21) = 1024;
      *(_DWORD *)(a1 + 48) = 0;
      pager_playback(a1, 1);
      *(_DWORD *)(a1 + 48) = v4;
      *(_BYTE *)(a1 + 22) = v5;
    }
  }
  else if ( v1 )
  {
    if ( v1 < 2u )
    {
      if ( !*(_BYTE *)(a1 + 8) )
        pager_end_transaction(a1, 0, 0);
    }
    else
    {
      sqlite3BeginBenignMalloc();
      sqlite3PagerRollback(a1);
      sqlite3EndBenignMalloc();
    }
  }
  return pager_unlock(a1);
}

```

## disassembly

```asm
0x180026804  mov     [rsp+arg_0], rbx
0x180026809  mov     [rsp+arg_8], rsi
0x18002680e  push    rdi
0x18002680f  sub     rsp, 20h
0x180026813  mov     al, [rcx+15h]
0x180026816  mov     rsi, rcx
0x180026819  cmp     al, 6
0x18002681b  jz      short loc_180026860
0x18002681d  test    al, al
0x18002681f  jz      short loc_180026837
0x180026821  cmp     al, 2
0x180026823  jb      short loc_18002684E
0x180026825  call    sqlite3BeginBenignMalloc
0x18002682a  mov     rcx, rsi
0x18002682d  call    sqlite3PagerRollback
0x180026832  call    sqlite3EndBenignMalloc
0x180026837  mov     rcx, rsi
0x18002683a  mov     rbx, [rsp+28h+arg_0]
0x18002683f  mov     rsi, [rsp+28h+arg_8]
0x180026844  add     rsp, 20h
0x180026848  pop     rdi
0x180026849  jmp     pager_unlock
0x18002684e  cmp     byte ptr [rcx+8], 0
0x180026852  jnz     short loc_180026837
0x180026854  xor     r8d, r8d
0x180026857  xor     edx, edx
0x180026859  call    pager_end_transaction
0x18002685e  jmp     short loc_180026837
0x180026860  cmp     byte ptr [rcx+9], 4
0x180026864  jnz     short loc_180026837
0x180026866  mov     rax, [rcx+50h]
0x18002686a  cmp     qword ptr [rax], 0
0x18002686e  jz      short loc_180026837
0x180026870  mov     edi, [rcx+30h]
0x180026873  mov     edx, 1
0x180026878  mov     bl, [rcx+16h]
0x18002687b  mov     word ptr [rcx+15h], 400h
0x180026881  mov     dword ptr [rcx+30h], 0
0x180026888  call    pager_playback
0x18002688d  mov     [rsi+30h], edi
0x180026890  mov     [rsi+16h], bl
0x180026893  jmp     short loc_180026837
```
