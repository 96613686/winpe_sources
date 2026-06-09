# LKRhash::CLKRHashTable::DeleteKey(unsigned __int64)

- ea: `0x1800082bc`
- end: `0x18000834e`
- name: `?DeleteKey@CLKRHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@_K@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800049f4`
- `0x18000531c`

## callees

- `0x1800082bc`
- `0x1800091b0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRHashTable::DeleteKey(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // r8d
  int v7; // edx
  unsigned int v8; // ecx
  unsigned int v9; // edx

  result = *(unsigned int *)(a1 + 48);
  if ( !(_DWORD)result )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(a1 + 40))(a2);
    v6 = (69069 * v5 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v5 + 12345) >> 16);
    v7 = *(_DWORD *)(a1 + 52);
    v8 = (69069 * v6 + 1) & 0xFFFF0000 | ((1048583 * v6 + 12345) >> 16);
    if ( v7 < 0 )
      v9 = v8 % *(_DWORD *)(a1 + 20);
    else
      v9 = v8 & v7;
    return LKRhash::CLKRLinearHashTable::_DeleteKey(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL * v9), a2, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800082bc  mov     [rsp+arg_0], rbx
0x1800082c1  push    rdi
0x1800082c2  sub     rsp, 20h
0x1800082c6  mov     eax, [rcx+30h]
0x1800082c9  mov     rdi, rdx
0x1800082cc  mov     rbx, rcx
0x1800082cf  test    eax, eax
0x1800082d1  jnz     short loc_180008343
0x1800082d3  mov     rax, [rbx+28h]
0x1800082d7  mov     rcx, rdx
0x1800082da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082df  imul    r8d, eax, 41C64E6Dh
0x1800082e6  mov     edx, 0FFFF0000h
0x1800082eb  imul    ecx, eax, 10DCDh
0x1800082f1  mov     r9d, 3039h
0x1800082f7  add     r8d, r9d
0x1800082fa  inc     ecx
0x1800082fc  shr     r8d, 10h
0x180008300  and     ecx, edx
0x180008302  or      r8d, ecx
0x180008305  imul    ecx, r8d, 100007h
0x18000830c  imul    eax, r8d, 10DCDh
0x180008313  add     ecx, r9d
0x180008316  inc     eax
0x180008318  shr     ecx, 10h
0x18000831b  and     eax, edx
0x18000831d  mov     edx, [rbx+34h]
0x180008320  or      ecx, eax
0x180008322  test    edx, edx
0x180008324  js      short loc_18000832A
0x180008326  and     edx, ecx
0x180008328  jmp     short loc_180008331
0x18000832a  xor     edx, edx
0x18000832c  mov     eax, ecx
0x18000832e  div     dword ptr [rbx+14h]
0x180008331  mov     rcx, [rbx+18h]
0x180008335  mov     eax, edx
0x180008337  mov     rdx, rdi
0x18000833a  mov     rcx, [rcx+rax*8]
0x18000833e  call    ?_DeleteKey@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@_KK@Z; LKRhash::CLKRLinearHashTable::_DeleteKey(unsigned __int64,ulong)
0x180008343  mov     rbx, [rsp+28h+arg_0]
0x180008348  add     rsp, 20h
0x18000834c  pop     rdi
0x18000834d  retn
```
