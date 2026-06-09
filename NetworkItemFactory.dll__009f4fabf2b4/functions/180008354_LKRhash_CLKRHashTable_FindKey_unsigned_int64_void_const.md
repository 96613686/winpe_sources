# LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)

- ea: `0x180008354`
- end: `0x180008401`
- name: `?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003470`
- `0x180004074`
- `0x1800049f4`

## callees

- `0x180008354`
- `0x1800098d4`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRHashTable::FindKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // edx
  unsigned int v10; // ecx
  unsigned int v11; // edx

  result = *(unsigned int *)(a1 + 48);
  if ( !(_DWORD)result )
  {
    if ( a3 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64))(a1 + 40))(a2);
      v8 = (69069 * v7 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v7 + 12345) >> 16);
      v9 = *(_DWORD *)(a1 + 52);
      v10 = (69069 * v8 + 1) & 0xFFFF0000 | ((1048583 * v8 + 12345) >> 16);
      if ( v9 < 0 )
        v11 = v10 % *(_DWORD *)(a1 + 20);
      else
        v11 = v10 & v9;
      return LKRhash::CLKRLinearHashTable::_FindKey(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL * v11), a2, v8, a3);
    }
    else
    {
      return 4294967200LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008354  mov     [rsp+arg_0], rbx
0x180008359  mov     [rsp+arg_8], rsi
0x18000835e  push    rdi
0x18000835f  sub     rsp, 30h
0x180008363  mov     eax, [rcx+30h]
0x180008366  mov     rdi, r8
0x180008369  mov     rsi, rdx
0x18000836c  mov     rbx, rcx
0x18000836f  test    eax, eax
0x180008371  jnz     short loc_1800083F1
0x180008373  test    r8, r8
0x180008376  jnz     short loc_18000837E
0x180008378  lea     eax, [r8-60h]
0x18000837c  jmp     short loc_1800083F1
0x18000837e  mov     rax, [rbx+28h]
0x180008382  mov     rcx, rsi
0x180008385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000838a  imul    r8d, eax, 41C64E6Dh
0x180008391  mov     edx, 0FFFF0000h
0x180008396  imul    ecx, eax, 10DCDh
0x18000839c  mov     r9d, 3039h
0x1800083a2  add     r8d, r9d
0x1800083a5  inc     ecx
0x1800083a7  shr     r8d, 10h
0x1800083ab  and     ecx, edx
0x1800083ad  or      r8d, ecx
0x1800083b0  imul    ecx, r8d, 100007h
0x1800083b7  imul    eax, r8d, 10DCDh
0x1800083be  add     ecx, r9d
0x1800083c1  inc     eax
0x1800083c3  shr     ecx, 10h
0x1800083c6  and     eax, edx
0x1800083c8  mov     edx, [rbx+34h]
0x1800083cb  or      ecx, eax
0x1800083cd  test    edx, edx
0x1800083cf  js      short loc_1800083D5
0x1800083d1  and     edx, ecx
0x1800083d3  jmp     short loc_1800083DC
0x1800083d5  xor     edx, edx
0x1800083d7  mov     eax, ecx
0x1800083d9  div     dword ptr [rbx+14h]
0x1800083dc  mov     rcx, [rbx+18h]
0x1800083e0  mov     r9, rdi
0x1800083e3  mov     eax, edx
0x1800083e5  mov     rdx, rsi
0x1800083e8  mov     rcx, [rcx+rax*8]
0x1800083ec  call    ?_FindKey@CLKRLinearHashTable@LKRhash@@AEBA?AW4LK_RETCODE@2@_KKPEAPEBXPEAVCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CLKRLinearHashTable::_FindKey(unsigned __int64,ulong,void const * *,LKRhash::CLKRLinearHashTable_Iterator *)
0x1800083f1  mov     rbx, [rsp+38h+arg_0]
0x1800083f6  mov     rsi, [rsp+38h+arg_8]
0x1800083fb  add     rsp, 30h
0x1800083ff  pop     rdi
0x180008400  retn
```
