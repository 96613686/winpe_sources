# sqlite3PagerWrite

- ea: `0x1800217c0`
- end: `0x1800218b6`
- name: `sqlite3PagerWrite`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `25`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cea8`
- `0x18001e3c8`
- `0x18001ed0c`
- `0x18001f720`
- `0x180020e14`
- `0x1800214a0`
- `0x180021578`
- `0x1800216a0`
- `0x180021758`
- `0x1800224a0`
- `0x180023f14`
- `0x1800469e8`
- `0x18005f2ec`
- `0x180060eac`
- `0x180061f00`
- `0x180066070`
- `0x180069fec`
- `0x18006b7b4`
- `0x18007ae08`
- `0x18007ca48`
- `0x18007d23c`
- `0x180081b04`
- `0x1800821ec`
- `0x180085d38`
- `0x18008c010`

## callees

- `0x1800217c0`
- `0x1800218bc`
- `0x180021990`
- `0x180021a70`
- `0x18005f0bc`

## pseudocode

```c
__int64 __fastcall sqlite3PagerWrite(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // esi
  int v4; // ebp
  __int64 result; // rax
  int i; // r14d
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // r14d
  __int64 v10; // rax

  v2 = *(_QWORD *)(a1 + 40);
  if ( (*(_BYTE *)(a1 + 52) & 4) != 0 && (v3 = *(_DWORD *)(a1 + 48), *(_DWORD *)(v2 + 32) >= v3) )
  {
    v4 = *(_DWORD *)(v2 + 128);
    if ( v4 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v4 )
          return 0;
        v7 = 56LL * i;
        v8 = *(_QWORD *)(v2 + 120);
        if ( *(_DWORD *)(v7 + v8 + 24) >= v3 && !(unsigned int)sqlite3BitvecTestNotNull(*(_QWORD *)(v7 + v8 + 16), v3) )
          break;
      }
      v9 = i + 1;
      if ( v9 < v4 )
      {
        do
        {
          v10 = v9++;
          *(_DWORD *)(56 * v10 + *(_QWORD *)(v2 + 120) + 32) = 0;
        }
        while ( v9 < *(_DWORD *)(v2 + 128) );
      }
      return subjournalPage(a1);
    }
    else
    {
      return 0;
    }
  }
  else
  {
    result = *(unsigned int *)(v2 + 48);
    if ( !(_DWORD)result )
    {
      if ( *(_DWORD *)(v2 + 184) > *(_DWORD *)(v2 + 200) )
        return pagerWriteLargeSector(a1);
      else
        return pager_write(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800217c0  mov     [rsp+arg_10], rbx
0x1800217c5  mov     [rsp+arg_18], rsi
0x1800217ca  push    rdi
0x1800217cb  sub     rsp, 20h
0x1800217cf  test    byte ptr [rcx+34h], 4
0x1800217d3  mov     rbx, rcx
0x1800217d6  mov     rdi, [rcx+28h]
0x1800217da  jz      short loc_180021858
0x1800217dc  mov     esi, [rcx+30h]
0x1800217df  cmp     [rdi+20h], esi
0x1800217e2  jb      short loc_180021858
0x1800217e4  mov     [rsp+28h+arg_0], rbp
0x1800217e9  mov     ebp, [rdi+80h]
0x1800217ef  test    ebp, ebp
0x1800217f1  jnz     short loc_18002180A
0x1800217f3  xor     eax, eax
0x1800217f5  mov     rbp, [rsp+28h+arg_0]
0x1800217fa  mov     rbx, [rsp+28h+arg_10]
0x1800217ff  mov     rsi, [rsp+28h+arg_18]
0x180021804  add     rsp, 20h
0x180021808  pop     rdi
0x180021809  retn
0x18002180a  mov     [rsp+28h+arg_8], r14
0x18002180f  xor     r14d, r14d
0x180021812  cmp     r14d, ebp
0x180021815  jge     short loc_180021854
0x180021817  movsxd  rax, r14d
0x18002181a  imul    rcx, rax, 38h ; '8'
0x18002181e  mov     rax, [rdi+78h]
0x180021822  cmp     [rcx+rax+18h], esi
0x180021826  jb      short loc_18002184F
0x180021828  mov     rcx, [rcx+rax+10h]
0x18002182d  mov     edx, esi
0x18002182f  call    sqlite3BitvecTestNotNull
0x180021834  test    eax, eax
0x180021836  jnz     short loc_18002184F
0x180021838  inc     r14d
0x18002183b  cmp     r14d, ebp
0x18002183e  jl      short loc_180021895
0x180021840  mov     rcx, rbx
0x180021843  call    subjournalPage
0x180021848  mov     r14, [rsp+28h+arg_8]
0x18002184d  jmp     short loc_1800217F5
0x18002184f  inc     r14d
0x180021852  jmp     short loc_180021812
0x180021854  xor     eax, eax
0x180021856  jmp     short loc_180021848
0x180021858  mov     eax, [rdi+30h]
0x18002185b  test    eax, eax
0x18002185d  jnz     short loc_1800217FA
0x18002185f  mov     eax, [rdi+0C8h]
0x180021865  cmp     [rdi+0B8h], eax
0x18002186b  ja      short loc_180021881
0x18002186d  mov     rbx, [rsp+28h+arg_10]
0x180021872  mov     rsi, [rsp+28h+arg_18]
0x180021877  add     rsp, 20h
0x18002187b  pop     rdi
0x18002187c  jmp     pager_write
0x180021881  mov     rbx, [rsp+28h+arg_10]
0x180021886  mov     rsi, [rsp+28h+arg_18]
0x18002188b  add     rsp, 20h
0x18002188f  pop     rdi
0x180021890  jmp     pagerWriteLargeSector
0x180021895  movsxd  rax, r14d
0x180021898  inc     r14d
0x18002189b  imul    rcx, rax, 38h ; '8'
0x18002189f  mov     rax, [rdi+78h]
0x1800218a3  mov     dword ptr [rcx+rax+20h], 0
0x1800218ab  cmp     r14d, [rdi+80h]
0x1800218b2  jl      short loc_180021895
0x1800218b4  jmp     short loc_180021840
```
