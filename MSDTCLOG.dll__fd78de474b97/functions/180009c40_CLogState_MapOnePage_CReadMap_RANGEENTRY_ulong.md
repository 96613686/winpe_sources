# CLogState::_MapOnePage(CReadMap &,_RANGEENTRY *,ulong *)

- ea: `0x180009c40`
- end: `0x180009ccf`
- name: `?_MapOnePage@CLogState@@AEAAHAEAVCReadMap@@PEAU_RANGEENTRY@@PEAK@Z`
- size: `143`
- prototype: `int(CLogState *__hidden this, struct CReadMap *, struct _RANGEENTRY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009178`

## callees

- `0x180009c40`
- `0x18000ce08`

## pseudocode

```c
__int64 __fastcall CLogState::_MapOnePage(
        CLogState *this,
        struct CReadMap *a2,
        struct _RANGEENTRY *a3,
        unsigned int *a4)
{
  unsigned int v4; // ebx
  unsigned int v5; // r10d
  unsigned int v6; // eax
  _DWORD *v8; // r8
  unsigned int v9; // r11d
  bool v11; // zf
  unsigned int v12; // eax
  int v13; // eax

  v4 = 8160 - *(_DWORD *)a3;
  v5 = *a4;
  *((_DWORD *)a3 + 3) = *((_DWORD *)this + 20);
  v6 = v5;
  if ( v4 < v5 )
    v5 = v4;
  *((_DWORD *)a3 + 1) = v5;
  *a4 = v6 - v5;
  CReadMap::AddRange(a2, a3);
  if ( v4 >= v9 )
    return 1;
  v8[2] += v8[3];
  v11 = *((_DWORD *)this + 26) == 0;
  v12 = v8[2];
  *v8 = 0;
  if ( !v11 && v12 >= *((_DWORD *)this + 14) )
  {
    v13 = *(_DWORD *)this;
    ++v8[4];
    v8[2] = v13;
  }
  return 0;
}

```

## disassembly

```asm
0x180009c40  mov     [rsp+arg_0], rbx
0x180009c45  mov     [rsp+arg_8], rsi
0x180009c4a  push    rdi
0x180009c4b  sub     rsp, 20h
0x180009c4f  mov     r11d, [r9]
0x180009c52  mov     rdi, rdx
0x180009c55  mov     eax, [rcx+50h]
0x180009c58  mov     ebx, 1FE0h
0x180009c5d  sub     ebx, [r8]
0x180009c60  mov     r10d, r11d
0x180009c63  mov     [r8+0Ch], eax
0x180009c67  cmp     ebx, r11d
0x180009c6a  mov     eax, r11d
0x180009c6d  mov     rsi, rcx
0x180009c70  cmovb   r10d, ebx
0x180009c74  mov     rdx, r8; struct _RANGEENTRY *
0x180009c77  sub     eax, r10d
0x180009c7a  mov     [r8+4], r10d
0x180009c7e  mov     rcx, rdi; this
0x180009c81  mov     [r9], eax
0x180009c84  call    ?AddRange@CReadMap@@QEAAXAEAU_RANGEENTRY@@@Z; CReadMap::AddRange(_RANGEENTRY &)
0x180009c89  cmp     ebx, r11d
0x180009c8c  jb      short loc_180009C95
0x180009c8e  mov     eax, 1
0x180009c93  jmp     short loc_180009CBF
0x180009c95  mov     eax, [r8+0Ch]
0x180009c99  add     [r8+8], eax
0x180009c9d  cmp     dword ptr [rsi+68h], 0
0x180009ca1  mov     eax, [r8+8]
0x180009ca5  mov     dword ptr [r8], 0
0x180009cac  jz      short loc_180009CBD
0x180009cae  cmp     eax, [rsi+38h]
0x180009cb1  jb      short loc_180009CBD
0x180009cb3  mov     eax, [rsi]
0x180009cb5  inc     dword ptr [r8+10h]
0x180009cb9  mov     [r8+8], eax
0x180009cbd  xor     eax, eax
0x180009cbf  mov     rbx, [rsp+28h+arg_0]
0x180009cc4  mov     rsi, [rsp+28h+arg_8]
0x180009cc9  add     rsp, 20h
0x180009ccd  pop     rdi
0x180009cce  retn
```
