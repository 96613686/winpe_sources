# WriteStemSnap

- ea: `0x18004dcf8`
- end: `0x18004de79`
- name: `WriteStemSnap`
- size: `385`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18004d3a8`
- `0x18004e4fc`

## callees

- `0x18004b108`
- `0x18004b5fc`
- `0x18004b690`
- `0x18004ba24`
- `0x18004dcf8`

## pseudocode

```c
__int64 __fastcall WriteStemSnap(_DWORD *a1, int a2)
{
  int *v2; // r14
  __int64 result; // rax
  signed int v6; // r9d
  signed int v7; // r9d

  v2 = a1 + 444;
  WriteBlendArrayLine((__int64)a1, (__int64)"StdHW", (__int64)(a1 + 444), a1[443], a2, 1, 1u);
  result = WriteBlendArrayLine((__int64)a1, (__int64)"StdVW", (__int64)(a1 + 461), a1[460], a2, 1, 1u);
  if ( a1[1249] )
  {
    PutString((__int64)a1, (__int64)"/StemSnapH [ ");
    PutBlendArray((__int64)a1, (__int64)(a1 + 1250), a1[1249], a2, 1, 1u);
    PutString((__int64)a1, (__int64)"] ");
    v6 = a1[1249];
    if ( v6 <= 2 || a1[122] )
      result = PutString((__int64)a1, (__int64)"def\r\n");
    else
      result = PutStemSnapBugFix((__int64)a1, *v2, (__int64)(a1 + 1250), v6);
  }
  if ( a1[1442] )
  {
    PutString((__int64)a1, (__int64)"/StemSnapV [ ");
    PutBlendArray((__int64)a1, (__int64)(a1 + 1443), a1[1442], a2, 1, 1u);
    PutString((__int64)a1, (__int64)"] ");
    v7 = a1[1442];
    if ( v7 <= 2 || a1[122] )
      return PutString((__int64)a1, (__int64)"def\r\n");
    else
      return PutStemSnapBugFix((__int64)a1, a1[461], (__int64)(a1 + 1443), v7);
  }
  return result;
}

```

## disassembly

```asm
0x18004dcf8  push    rbx
0x18004dcfa  push    rsi
0x18004dcfb  push    rdi
0x18004dcfc  push    r14
0x18004dcfe  push    r15
0x18004dd00  sub     rsp, 40h
0x18004dd04  mov     r9d, [rcx+6ECh]
0x18004dd0b  lea     r14, [rcx+6F0h]
0x18004dd12  mov     r15d, 1
0x18004dd18  mov     esi, edx
0x18004dd1a  mov     [rsp+68h+var_38], r15d
0x18004dd1f  mov     r8, r14
0x18004dd22  mov     [rsp+68h+var_40], r15d
0x18004dd27  mov     rbx, rcx
0x18004dd2a  mov     [rsp+68h+var_48], edx
0x18004dd2e  lea     rdx, aStdhw; "StdHW"
0x18004dd35  call    WriteBlendArrayLine
0x18004dd3a  mov     r9d, [rbx+730h]
0x18004dd41  lea     r8, [rbx+734h]
0x18004dd48  mov     [rsp+68h+var_38], r15d
0x18004dd4d  lea     rdx, aStdvw; "StdVW"
0x18004dd54  mov     [rsp+68h+var_40], r15d
0x18004dd59  mov     rcx, rbx
0x18004dd5c  mov     [rsp+68h+var_48], esi
0x18004dd60  call    WriteBlendArrayLine
0x18004dd65  cmp     dword ptr [rbx+1384h], 0
0x18004dd6c  jz      short loc_18004DDE7
0x18004dd6e  lea     rdx, aStemsnaph; "/StemSnapH [ "
0x18004dd75  mov     rcx, rbx
0x18004dd78  call    PutString
0x18004dd7d  mov     r8d, [rbx+1384h]
0x18004dd84  lea     rdi, [rbx+1388h]
0x18004dd8b  mov     rdx, rdi
0x18004dd8e  mov     [rsp+68h+var_40], r15d
0x18004dd93  mov     r9d, esi
0x18004dd96  mov     [rsp+68h+var_48], r15d
0x18004dd9b  mov     rcx, rbx
0x18004dd9e  call    PutBlendArray
0x18004dda3  lea     rdx, asc_1800650E0; "] "
0x18004ddaa  mov     rcx, rbx
0x18004ddad  call    PutString
0x18004ddb2  mov     r9d, [rbx+1384h]
0x18004ddb9  cmp     r9d, 2
0x18004ddbd  jle     short loc_18004DDD8
0x18004ddbf  cmp     dword ptr [rbx+1E8h], 0
0x18004ddc6  jnz     short loc_18004DDD8
0x18004ddc8  mov     edx, [r14]
0x18004ddcb  mov     r8, rdi
0x18004ddce  mov     rcx, rbx
0x18004ddd1  call    PutStemSnapBugFix
0x18004ddd6  jmp     short loc_18004DDE7
0x18004ddd8  lea     rdx, aDef_0; "def\r\n"
0x18004dddf  mov     rcx, rbx
0x18004dde2  call    PutString
0x18004dde7  cmp     dword ptr [rbx+1688h], 0
0x18004ddee  jz      short loc_18004DE6C
0x18004ddf0  lea     rdx, aStemsnapv; "/StemSnapV [ "
0x18004ddf7  mov     rcx, rbx
0x18004ddfa  call    PutString
0x18004ddff  mov     r8d, [rbx+1688h]
0x18004de06  lea     rdi, [rbx+168Ch]
0x18004de0d  mov     rdx, rdi
0x18004de10  mov     [rsp+68h+var_40], r15d
0x18004de15  mov     r9d, esi
0x18004de18  mov     [rsp+68h+var_48], r15d
0x18004de1d  mov     rcx, rbx
0x18004de20  call    PutBlendArray
0x18004de25  lea     rdx, asc_1800650E0; "] "
0x18004de2c  mov     rcx, rbx
0x18004de2f  call    PutString
0x18004de34  mov     r9d, [rbx+1688h]
0x18004de3b  cmp     r9d, 2
0x18004de3f  jle     short loc_18004DE5D
0x18004de41  cmp     dword ptr [rbx+1E8h], 0
0x18004de48  jnz     short loc_18004DE5D
0x18004de4a  mov     edx, [rbx+734h]
0x18004de50  mov     r8, rdi
0x18004de53  mov     rcx, rbx
0x18004de56  call    PutStemSnapBugFix
0x18004de5b  jmp     short loc_18004DE6C
0x18004de5d  lea     rdx, aDef_0; "def\r\n"
0x18004de64  mov     rcx, rbx
0x18004de67  call    PutString
0x18004de6c  add     rsp, 40h
0x18004de70  pop     r15
0x18004de72  pop     r14
0x18004de74  pop     rdi
0x18004de75  pop     rsi
0x18004de76  pop     rbx
0x18004de77  retn
```
