# CommonUtil::HrFromErrno(int)

- ea: `0x14000429c`
- end: `0x1400042f4`
- name: `?HrFromErrno@CommonUtil@@YAJH@Z`
- size: `88`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140022ac4`

## callees

- `0x14000429c`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrFromErrno(CommonUtil *this)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx

  v1 = (_DWORD)this - 2;
  if ( !v1 )
    return 2147942402LL;
  v2 = v1 - 3;
  if ( !v2 )
    return 2147942430LL;
  v3 = v2 - 4;
  if ( !v3 )
    return 2147942406LL;
  v4 = v3 - 3;
  if ( !v4 )
    return 2147942414LL;
  v5 = v4 - 1;
  if ( !v5 )
    return 2147942405LL;
  v6 = v5 - 4;
  if ( !v6 )
    return 2147942480LL;
  v7 = v6 - 5;
  if ( !v7 )
    return 2147942414LL;
  if ( v7 == 6 )
    return 2147942439LL;
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x14000429c  sub     ecx, 2
0x14000429f  jz      short loc_1400042EE
0x1400042a1  sub     ecx, 3
0x1400042a4  jz      short loc_1400042E8
0x1400042a6  sub     ecx, 4
0x1400042a9  jz      short loc_1400042E2
0x1400042ab  sub     ecx, 3
0x1400042ae  jz      short loc_1400042D0
0x1400042b0  sub     ecx, 1
0x1400042b3  jz      short loc_1400042DC
0x1400042b5  sub     ecx, 4
0x1400042b8  jz      short loc_1400042D6
0x1400042ba  sub     ecx, 5
0x1400042bd  jz      short loc_1400042D0
0x1400042bf  cmp     ecx, 6
0x1400042c2  jz      short loc_1400042CA
0x1400042c4  mov     eax, 80004005h
0x1400042c9  retn
0x1400042ca  mov     eax, 80070027h
0x1400042cf  retn
0x1400042d0  mov     eax, 8007000Eh
0x1400042d5  retn
0x1400042d6  mov     eax, 80070050h
0x1400042db  retn
0x1400042dc  mov     eax, 80070005h
0x1400042e1  retn
0x1400042e2  mov     eax, 80070006h
0x1400042e7  retn
0x1400042e8  mov     eax, 8007001Eh
0x1400042ed  retn
0x1400042ee  mov     eax, 80070002h
0x1400042f3  retn
```
