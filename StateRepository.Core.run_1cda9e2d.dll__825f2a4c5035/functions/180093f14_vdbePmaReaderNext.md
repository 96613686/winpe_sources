# vdbePmaReaderNext

- ea: `0x180093f14`
- end: `0x180094019`
- name: `vdbePmaReaderNext`
- size: `261`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x18004e72c`
- `0x1800937d8`
- `0x180093864`
- `0x1800939bc`
- `0x180093e24`

## callees

- `0x18004cc58`
- `0x1800878e0`
- `0x18009359c`
- `0x180093b5c`
- `0x180093ca8`
- `0x180093d90`
- `0x180093f14`
- `0x180094020`

## pseudocode

```c
__int64 __fastcall vdbePmaReaderNext(_QWORD *a1)
{
  __int64 v1; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // esi
  _OWORD *v5; // rbp
  __int128 v6; // xmm0
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1[1];
  v9 = 0;
  if ( *a1 >= v1 )
  {
    v3 = (_QWORD *)a1[9];
    v4 = 0;
    if ( !v3 )
      goto LABEL_16;
    if ( *((_DWORD *)v3 + 8) )
    {
      v5 = v3 + 5;
      v4 = vdbeSorterJoinThread(*v3);
      if ( !v4 )
      {
        v6 = *(_OWORD *)(v3 + 7);
        *(_OWORD *)(v3 + 7) = *v5;
        *v5 = v6;
        if ( v3[6] == v3[2] )
        {
          *((_DWORD *)v3 + 7) = 1;
LABEL_11:
          if ( !*((_DWORD *)v3 + 7) )
          {
            result = vdbePmaReaderSeek(*v3, a1, v5, v3[2]);
            if ( (_DWORD)result )
              return result;
            goto LABEL_13;
          }
LABEL_16:
          vdbePmaReaderClear(a1);
          return v4;
        }
        v4 = sqlite3ThreadCreate((__int64 **)*v3, (__int64 (__fastcall *)(__int64))vdbeIncrPopulateThread, (__int64)v3);
      }
    }
    else
    {
      v5 = v3 + 5;
      v4 = vdbeIncrPopulate(a1[9]);
      *(_OWORD *)(v3 + 5) = *(_OWORD *)(v3 + 7);
      if ( v3[6] == v3[2] )
        *((_DWORD *)v3 + 7) = 1;
    }
    if ( v4 )
      goto LABEL_16;
    goto LABEL_11;
  }
LABEL_13:
  result = vdbePmaReadVarint(a1, &v9);
  if ( !(_DWORD)result )
  {
    v8 = v9;
    *((_DWORD *)a1 + 5) = v9;
    return vdbePmaReadBlob(a1, v8, a1 + 5);
  }
  return result;
}

```

## disassembly

```asm
0x180093f14  push    rbx
0x180093f16  push    rbp
0x180093f17  push    rsi
0x180093f18  push    rdi
0x180093f19  sub     rsp, 28h
0x180093f1d  mov     rax, [rcx+8]
0x180093f21  mov     rdi, rcx
0x180093f24  mov     [rsp+48h+arg_0], 0
0x180093f2d  cmp     [rcx], rax
0x180093f30  jl      loc_180093FDF
0x180093f36  mov     rbx, [rcx+48h]
0x180093f3a  xor     esi, esi
0x180093f3c  test    rbx, rbx
0x180093f3f  jz      loc_18009400D
0x180093f45  cmp     [rbx+20h], esi
0x180093f48  jz      short loc_180093F97
0x180093f4a  mov     rcx, [rbx]
0x180093f4d  call    vdbeSorterJoinThread
0x180093f52  lea     rbp, [rbx+28h]
0x180093f56  mov     esi, eax
0x180093f58  test    eax, eax
0x180093f5a  jnz     short loc_180093FBF
0x180093f5c  movups  xmm1, xmmword ptr [rbp+0]
0x180093f60  movups  xmm0, xmmword ptr [rbx+38h]
0x180093f64  movdqu  xmmword ptr [rbx+38h], xmm1
0x180093f69  movdqu  xmmword ptr [rbp+0], xmm0
0x180093f6e  mov     rax, [rbx+10h]
0x180093f72  cmp     [rbx+30h], rax
0x180093f76  jnz     short loc_180093F81
0x180093f78  mov     dword ptr [rbx+1Ch], 1
0x180093f7f  jmp     short loc_180093FC3
0x180093f81  mov     rcx, [rbx]
0x180093f84  lea     rdx, vdbeIncrPopulateThread
0x180093f8b  mov     r8, rbx
0x180093f8e  call    sqlite3ThreadCreate
0x180093f93  mov     esi, eax
0x180093f95  jmp     short loc_180093FBF
0x180093f97  mov     rcx, rbx
0x180093f9a  call    vdbeIncrPopulate
0x180093f9f  movups  xmm0, xmmword ptr [rbx+38h]
0x180093fa3  lea     rbp, [rbx+28h]
0x180093fa7  mov     esi, eax
0x180093fa9  movdqu  xmmword ptr [rbp+0], xmm0
0x180093fae  mov     rax, [rbx+10h]
0x180093fb2  cmp     [rbx+30h], rax
0x180093fb6  jnz     short loc_180093FBF
0x180093fb8  mov     dword ptr [rbx+1Ch], 1
0x180093fbf  test    esi, esi
0x180093fc1  jnz     short loc_18009400D
0x180093fc3  cmp     dword ptr [rbx+1Ch], 0
0x180093fc7  jnz     short loc_18009400D
0x180093fc9  mov     r9, [rbx+10h]
0x180093fcd  mov     r8, rbp
0x180093fd0  mov     rcx, [rbx]
0x180093fd3  mov     rdx, rdi
0x180093fd6  call    vdbePmaReaderSeek
0x180093fdb  test    eax, eax
0x180093fdd  jnz     short loc_180094004
0x180093fdf  lea     rdx, [rsp+48h+arg_0]
0x180093fe4  mov     rcx, rdi
0x180093fe7  call    vdbePmaReadVarint
0x180093fec  test    eax, eax
0x180093fee  jnz     short loc_180094004
0x180093ff0  mov     rdx, [rsp+48h+arg_0]
0x180093ff5  lea     r8, [rdi+28h]
0x180093ff9  mov     rcx, rdi
0x180093ffc  mov     [rdi+14h], edx
0x180093fff  call    vdbePmaReadBlob
0x180094004  add     rsp, 28h
0x180094008  pop     rdi
0x180094009  pop     rsi
0x18009400a  pop     rbp
0x18009400b  pop     rbx
0x18009400c  retn
0x18009400d  mov     rcx, rdi; void *
0x180094010  call    vdbePmaReaderClear
0x180094015  mov     eax, esi
0x180094017  jmp     short loc_180094004
```
