# VfsCreateContextSetup

- ea: `0x140004484`
- end: `0x14000458f`
- name: `VfsCreateContextSetup`
- size: `267`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _OWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003c00`

## callees

- `0x1400034a0`
- `0x140004484`

## pseudocode

```c
__int64 __fastcall VfsCreateContextSetup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v10; // r11
  _DWORD *v11; // r10
  _QWORD *v12; // r14
  bool v13; // zf
  unsigned int v14; // ecx
  int v15; // edx
  __int64 result; // rax

  v10 = 0;
  v11 = (_DWORD *)(a7 + 76);
  v12 = (_QWORD *)(a7 + 16);
  v13 = (*(_BYTE *)(*(_QWORD *)(a3 + 16) + 6LL) & 4) == 0;
  *(_QWORD *)a7 = a1;
  if ( v13 )
    v10 = a6;
  *(_QWORD *)(a7 + 8) = a2;
  v14 = *v11 & 0xFFFFEFFF | *(_DWORD *)(*(_QWORD *)(a3 + 16) + 32LL) & 0x1000;
  *v11 = v14;
  v15 = v14
      ^ ((unsigned __int16)v14
       ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)(*(_QWORD *)(a3 + 16) + 32LL) << 13))
      & 0x2000;
  *v11 = v15;
  *v11 = v15 & 0xFFFFBFFF | ((*(_DWORD *)(*(_QWORD *)(a3 + 16) + 32LL) & 0x40) << 8);
  result = VfsCowQueryFileForUserAndPackage(
             a3,
             a1,
             a2,
             *(_QWORD *)(*(_QWORD *)(a3 + 16) + 16LL),
             a4,
             a5,
             v10,
             v12,
             a7 + 48,
             a7 + 56,
             a7 + 72,
             a7 + 76);
  if ( (int)result >= 0 )
  {
    if ( *v12 )
    {
      *(_QWORD *)(a7 + 24) = *(_QWORD *)(*(_QWORD *)(a3 + 16) + 16LL);
      *(_OWORD *)(a7 + 32) = *a5;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004484  push    rbx
0x140004486  push    rbp
0x140004487  push    rsi
0x140004488  push    rdi
0x140004489  push    r14
0x14000448b  push    r15
0x14000448d  sub     rsp, 68h
0x140004491  mov     rsi, [rsp+98h+arg_30]
0x140004499  mov     rdi, rcx
0x14000449c  mov     r15, [rsp+98h+arg_20]
0x1400044a4  mov     rbp, r8
0x1400044a7  mov     r8, rdx
0x1400044aa  mov     rbx, r9
0x1400044ad  mov     r11d, 0
0x1400044b3  lea     r10, [rsi+4Ch]
0x1400044b7  mov     rax, [rbp+10h]
0x1400044bb  lea     r14, [rsi+10h]
0x1400044bf  mov     [rsp+98h+var_40], r10
0x1400044c4  test    byte ptr [rax+6], 4
0x1400044c8  mov     [rsi], rcx
0x1400044cb  cmovz   r11, [rsp+98h+arg_28]
0x1400044d4  mov     [rsi+8], rdx
0x1400044d8  mov     rax, [rbp+10h]
0x1400044dc  mov     ecx, [rax+20h]
0x1400044df  mov     eax, [r10]
0x1400044e2  and     ecx, 1000h
0x1400044e8  btr     eax, 0Ch
0x1400044ec  or      ecx, eax
0x1400044ee  mov     [r10], ecx
0x1400044f1  mov     rax, [rbp+10h]
0x1400044f5  mov     edx, [rax+20h]
0x1400044f8  shl     edx, 0Dh
0x1400044fb  xor     edx, ecx
0x1400044fd  and     edx, 2000h
0x140004503  xor     edx, ecx
0x140004505  mov     [r10], edx
0x140004508  btr     edx, 0Eh
0x14000450c  mov     rax, [rbp+10h]
0x140004510  mov     ecx, [rax+20h]
0x140004513  lea     rax, [rsi+48h]
0x140004517  mov     [rsp+98h+var_48], rax
0x14000451c  and     ecx, 40h
0x14000451f  shl     ecx, 8
0x140004522  or      ecx, edx
0x140004524  lea     rdx, [rsi+30h]
0x140004528  mov     [r10], ecx
0x14000452b  lea     rcx, [rsi+38h]
0x14000452f  mov     r9, [rbp+10h]
0x140004533  mov     [rsp+98h+var_50], rcx
0x140004538  mov     rcx, rbp
0x14000453b  mov     [rsp+98h+var_58], rdx
0x140004540  mov     rdx, rdi
0x140004543  mov     [rsp+98h+var_60], r14
0x140004548  mov     r9, [r9+10h]
0x14000454c  mov     [rsp+98h+var_68], r11
0x140004551  mov     [rsp+98h+var_70], r15
0x140004556  mov     [rsp+98h+var_78], rbx
0x14000455b  call    VfsCowQueryFileForUserAndPackage
0x140004560  test    eax, eax
0x140004562  js      short loc_140004581
0x140004564  cmp     qword ptr [r14], 0
0x140004568  jz      short loc_14000457F
0x14000456a  mov     rax, [rbp+10h]
0x14000456e  mov     rcx, [rax+10h]
0x140004572  mov     [rsi+18h], rcx
0x140004576  movups  xmm0, xmmword ptr [r15]
0x14000457a  movdqu  xmmword ptr [rsi+20h], xmm0
0x14000457f  xor     eax, eax
0x140004581  add     rsp, 68h
0x140004585  pop     r15
0x140004587  pop     r14
0x140004589  pop     rdi
0x14000458a  pop     rsi
0x14000458b  pop     rbp
0x14000458c  pop     rbx
0x14000458d  retn
```
