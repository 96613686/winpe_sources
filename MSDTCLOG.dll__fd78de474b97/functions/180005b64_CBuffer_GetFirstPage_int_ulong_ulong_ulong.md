# CBuffer::GetFirstPage(int,ulong,ulong *,ulong *)

- ea: `0x180005b64`
- end: `0x180005bfc`
- name: `?GetFirstPage@CBuffer@@QEAAPEAU_RECORDPAGE@@HKPEAK0@Z`
- size: `152`
- prototype: `struct _RECORDPAGE *__fastcall(CBuffer *__hidden this, int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180002900`
- `0x18000b06c`
- `0x18000b2c8`
- `0x18000cec8`
- `0x18000d160`
- `0x18000d2f0`

## callees

- `0x180005b64`
- `0x180015010`

## pseudocode

```c
struct _RECORDPAGE *__fastcall CBuffer::GetFirstPage(
        CBuffer *this,
        __int64 a2,
        int a3,
        unsigned int *a4,
        unsigned int *a5)
{
  _DWORD *v5; // rbx
  unsigned int *v8; // r8
  unsigned int v9; // eax
  bool v10; // zf
  unsigned int *v11; // rsi
  unsigned __int8 *v12; // rdx
  unsigned int v13; // eax

  v5 = (_DWORD *)*((_QWORD *)this + 3);
  v8 = (unsigned int *)pulCRCTable;
  v9 = *((_DWORD *)this + 2) - 8;
  v10 = *((_DWORD *)this + 10) == 0;
  v11 = v5 + 2;
  *((_QWORD *)this + 7) = v5;
  *((_DWORD *)this + 16) = 0;
  v12 = (unsigned __int8 *)(v5 + 2);
  if ( v10 )
  {
    if ( lpCalcCRC(v9, v12, v8) != v5[1] )
      return 0;
    return (struct _RECORDPAGE *)v5;
  }
  v13 = lpCalcCRC(v9, v12, v8);
  if ( a5 )
  {
    if ( !a4 )
      goto LABEL_10;
    goto LABEL_9;
  }
  if ( a4 )
  {
LABEL_9:
    *a4 = *v11;
    if ( !a5 )
      return (struct _RECORDPAGE *)v5;
LABEL_10:
    *a5 = v13;
    return (struct _RECORDPAGE *)v5;
  }
  if ( *v11 != a3 || v13 != v5[1] || *v5 != 1146368594 )
    return 0;
  return (struct _RECORDPAGE *)v5;
}

```

## disassembly

```asm
0x180005b64  push    rbx
0x180005b66  push    rbp
0x180005b67  push    rsi
0x180005b68  push    rdi
0x180005b69  sub     rsp, 28h
0x180005b6d  mov     rbx, [rcx+18h]
0x180005b71  mov     ebp, r8d
0x180005b74  mov     eax, [rcx+8]
0x180005b77  mov     rdi, r9
0x180005b7a  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x180005b81  add     eax, 0FFFFFFF8h
0x180005b84  cmp     dword ptr [rcx+28h], 0
0x180005b88  lea     rsi, [rbx+8]
0x180005b8c  mov     [rcx+38h], rbx
0x180005b90  mov     dword ptr [rcx+40h], 0
0x180005b97  mov     rdx, rsi
0x180005b9a  mov     ecx, eax
0x180005b9c  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x180005ba3  jz      short loc_180005BE2
0x180005ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005baa  mov     rcx, [rsp+48h+arg_20]
0x180005baf  mov     edx, eax
0x180005bb1  test    rcx, rcx
0x180005bb4  jnz     short loc_180005BD0
0x180005bb6  test    rdi, rdi
0x180005bb9  jnz     short loc_180005BD5
0x180005bbb  cmp     [rsi], ebp
0x180005bbd  jnz     short loc_180005BCC
0x180005bbf  cmp     eax, [rbx+4]
0x180005bc2  jnz     short loc_180005BCC
0x180005bc4  cmp     dword ptr [rbx], 44543252h
0x180005bca  jz      short loc_180005BF0
0x180005bcc  xor     eax, eax
0x180005bce  jmp     short loc_180005BF3
0x180005bd0  test    rdi, rdi
0x180005bd3  jz      short loc_180005BDE
0x180005bd5  mov     eax, [rsi]
0x180005bd7  mov     [rdi], eax
0x180005bd9  test    rcx, rcx
0x180005bdc  jz      short loc_180005BF0
0x180005bde  mov     [rcx], edx
0x180005be0  jmp     short loc_180005BF0
0x180005be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be7  xor     ecx, ecx
0x180005be9  cmp     eax, [rbx+4]
0x180005bec  cmovnz  rbx, rcx
0x180005bf0  mov     rax, rbx
0x180005bf3  add     rsp, 28h
0x180005bf7  pop     rdi
0x180005bf8  pop     rsi
0x180005bf9  pop     rbp
0x180005bfa  pop     rbx
0x180005bfb  retn
```
