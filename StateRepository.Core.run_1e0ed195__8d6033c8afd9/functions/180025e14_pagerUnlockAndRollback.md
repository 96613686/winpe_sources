# pagerUnlockAndRollback

- ea: `0x180025e14`
- end: `0x180025ea5`
- name: `pagerUnlockAndRollback`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180008f14`
- `0x180024df4`
- `0x1800257ac`
- `0x180025960`

## callees

- `0x1800245b8`
- `0x18002468c`
- `0x180024978`
- `0x180025e14`
- `0x180047b8c`
- `0x180047ba4`
- `0x18007ae78`

## pseudocode

```c
__int64 __fastcall pagerUnlockAndRollback(__int64 a1)
{
  unsigned __int8 v1; // al
  int v3; // edi
  char v4; // bl

  v1 = *(_BYTE *)(a1 + 21);
  if ( v1 == 6 )
  {
    if ( *(_BYTE *)(a1 + 9) == 4 && **(_QWORD **)(a1 + 80) )
    {
      v3 = *(_DWORD *)(a1 + 48);
      v4 = *(_BYTE *)(a1 + 22);
      *(_WORD *)(a1 + 21) = 1024;
      *(_DWORD *)(a1 + 48) = 0;
      pager_playback(a1, 1);
      *(_DWORD *)(a1 + 48) = v3;
      *(_BYTE *)(a1 + 22) = v4;
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
0x180025e14  mov     [rsp+arg_0], rbx
0x180025e19  mov     [rsp+arg_8], rsi
0x180025e1e  push    rdi
0x180025e1f  sub     rsp, 20h
0x180025e23  mov     al, [rcx+15h]
0x180025e26  mov     rsi, rcx
0x180025e29  cmp     al, 6
0x180025e2b  jz      short loc_180025E5B
0x180025e2d  test    al, al
0x180025e2f  jz      short loc_180025E8E
0x180025e31  cmp     al, 2
0x180025e33  jb      short loc_180025E49
0x180025e35  call    sqlite3BeginBenignMalloc
0x180025e3a  mov     rcx, rsi
0x180025e3d  call    sqlite3PagerRollback
0x180025e42  call    sqlite3EndBenignMalloc
0x180025e47  jmp     short loc_180025E8E
0x180025e49  cmp     byte ptr [rcx+8], 0
0x180025e4d  jnz     short loc_180025E8E
0x180025e4f  xor     r8d, r8d
0x180025e52  xor     edx, edx
0x180025e54  call    pager_end_transaction
0x180025e59  jmp     short loc_180025E8E
0x180025e5b  cmp     byte ptr [rcx+9], 4
0x180025e5f  jnz     short loc_180025E8E
0x180025e61  mov     rax, [rcx+50h]
0x180025e65  cmp     qword ptr [rax], 0
0x180025e69  jz      short loc_180025E8E
0x180025e6b  mov     edi, [rcx+30h]
0x180025e6e  mov     edx, 1
0x180025e73  mov     bl, [rcx+16h]
0x180025e76  mov     word ptr [rcx+15h], 400h
0x180025e7c  mov     dword ptr [rcx+30h], 0
0x180025e83  call    pager_playback
0x180025e88  mov     [rsi+30h], edi
0x180025e8b  mov     [rsi+16h], bl
0x180025e8e  mov     rcx, rsi
0x180025e91  mov     rbx, [rsp+28h+arg_0]
0x180025e96  mov     rsi, [rsp+28h+arg_8]
0x180025e9b  add     rsp, 20h
0x180025e9f  pop     rdi
0x180025ea0  jmp     pager_unlock
```
