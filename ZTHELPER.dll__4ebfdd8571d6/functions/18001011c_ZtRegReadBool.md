# ZtRegReadBool

- ea: `0x18001011c`
- end: `0x1800101df`
- name: `ZtRegReadBool`
- size: `195`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800039e4`

## callees

- `0x18000f8f0`
- `0x18001011c`
- `0x180015694`
- `0x180016288`

## pseudocode

```c
__int64 __fastcall ZtRegReadBool(HKEY a1, const WCHAR *a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  int v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qSq(1035, 0xEu, (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, a1, a2, a3);
  if ( a3 )
    *a3 = 0;
  if ( a1 && a2 && a3 )
  {
    v7 = privateRegReadDwordValue(a1, a2, &v9);
    v6 = v7;
    if ( v7 == 2 )
    {
      v6 = 0;
    }
    else if ( !v7 )
    {
      *a3 = v9 != 0;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_Dl(a1, a2, a3, v6, v9 != 0);
  return v6;
}

```

## disassembly

```asm
0x18001011c  mov     rax, rsp
0x18001011f  mov     [rax+10h], rbx
0x180010123  mov     [rax+18h], rsi
0x180010127  push    rdi
0x180010128  sub     rsp, 30h
0x18001012c  mov     rdi, r8
0x18001012f  mov     dword ptr [rax+8], 0
0x180010136  mov     rbx, rdx
0x180010139  mov     rsi, rcx
0x18001013c  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010143  jz      short loc_180010166
0x180010145  mov     [rax-10h], r8
0x180010149  mov     edx, 0Eh
0x18001014e  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x180010155  mov     [rax-18h], rbx
0x180010159  mov     ecx, 40Bh
0x18001015e  mov     r9, rsi
0x180010161  call    WPP_SF_qSq
0x180010166  test    rdi, rdi
0x180010169  jz      short loc_180010171
0x18001016b  mov     dword ptr [rdi], 0
0x180010171  test    rsi, rsi
0x180010174  jnz     short loc_18001017D
0x180010176  mov     ebx, 57h ; 'W'
0x18001017b  jmp     short loc_1800101AF
0x18001017d  test    rbx, rbx
0x180010180  jz      short loc_180010176
0x180010182  test    rdi, rdi
0x180010185  jz      short loc_180010176
0x180010187  lea     r8, [rsp+38h+arg_0]
0x18001018c  mov     rdx, rbx
0x18001018f  mov     rcx, rsi
0x180010192  call    privateRegReadDwordValue
0x180010197  mov     ebx, eax
0x180010199  cmp     eax, 2
0x18001019c  jnz     short loc_1800101A2
0x18001019e  xor     ebx, ebx
0x1800101a0  jmp     short loc_1800101AF
0x1800101a2  test    eax, eax
0x1800101a4  jnz     short loc_1800101AF
0x1800101a6  cmp     [rsp+38h+arg_0], eax
0x1800101aa  setnz   al
0x1800101ad  mov     [rdi], eax
0x1800101af  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800101b6  jz      short loc_1800101CD
0x1800101b8  xor     eax, eax
0x1800101ba  mov     r9d, ebx
0x1800101bd  cmp     [rsp+38h+arg_0], eax
0x1800101c1  setnz   al
0x1800101c4  mov     [rsp+38h+var_18], eax
0x1800101c8  call    WPP_SF_Dl
0x1800101cd  mov     rsi, [rsp+38h+arg_10]
0x1800101d2  mov     eax, ebx
0x1800101d4  mov     rbx, [rsp+38h+arg_8]
0x1800101d9  add     rsp, 30h
0x1800101dd  pop     rdi
0x1800101de  retn
```
