# HtDestroyHandleTable

- ea: `0x180004a50`
- end: `0x180004b75`
- name: `HtDestroyHandleTable`
- size: `293`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004a50`
- `0x180004b80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004abc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004abc`

## pseudocode

```c
__int64 __fastcall HtDestroyHandleTable(_DWORD *a1)
{
  unsigned int v3; // ecx
  unsigned int v4; // edx
  unsigned int v5; // r8d
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rsi
  void (__fastcall *v10)(_QWORD); // rax
  LPVOID v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = a1;
  if ( !a1 || *a1 != 1950888524 )
    return 87;
  *a1 = 2021143116;
  v3 = 0xFFFFFFF;
  v4 = a1[18];
  if ( v4 > a1[21] + a1[24] )
  {
    v3 = a1[28];
    v5 = 0;
    a1[28] = 0xFFFFFFF;
    if ( v4 )
    {
      do
      {
        v6 = *((_QWORD *)a1 + 8);
        v7 = 32LL * v5;
        if ( *(_QWORD *)(v7 + v6) )
        {
          *(_QWORD *)(v7 + v6) = 0;
          v8 = *((_QWORD *)a1 + 8);
          *(_DWORD *)(v7 + v8 + 28) &= 0xFu;
          *(_DWORD *)(v7 + v8 + 28) |= 16 * v3;
          v3 = v5;
        }
        ++v5;
      }
      while ( v5 < a1[18] );
    }
  }
  for ( ; v3 != 0xFFFFFFF; v3 = *(_DWORD *)(v9 + 28) >> 4 )
  {
    v9 = *((_QWORD *)a1 + 8) + 32LL * v3;
    v10 = *(void (__fastcall **)(_QWORD))(v9 + 16);
    if ( v10 )
      v10(*(_QWORD *)(v9 + 8));
  }
  FreeMemory((LPVOID *)a1 + 8, (int)"HtDestroyHandleTable", 95);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 2));
  FreeMemory(&v11, (int)"HtDestroyHandleTable", 97);
  return 0;
}

```

## disassembly

```asm
0x180004a50  push    rbx
0x180004a52  sub     rsp, 20h
0x180004a56  mov     [rsp+28h+arg_0], rcx
0x180004a5b  mov     rbx, rcx
0x180004a5e  test    rcx, rcx
0x180004a61  jz      short loc_180004A6B
0x180004a63  cmp     dword ptr [rcx], 7448324Ch
0x180004a69  jz      short loc_180004A76
0x180004a6b  mov     eax, 57h ; 'W'
0x180004a70  add     rsp, 20h
0x180004a74  pop     rbx
0x180004a75  retn
0x180004a76  mov     dword ptr [rbx], 7878324Ch
0x180004a7c  mov     ecx, 0FFFFFFFh
0x180004a81  mov     eax, [rbx+60h]
0x180004a84  add     eax, [rbx+54h]
0x180004a87  mov     edx, [rbx+48h]
0x180004a8a  mov     [rsp+28h+arg_10], rdi
0x180004a8f  cmp     edx, eax
0x180004a91  ja      short loc_180004AE6
0x180004a93  lea     rdi, [rbx+40h]
0x180004a97  cmp     ecx, 0FFFFFFFh
0x180004a9d  jnz     loc_180004B3D
0x180004aa3  mov     r8d, 15Fh
0x180004aa9  lea     rdx, aHtdestroyhandl_0; "HtDestroyHandleTable"
0x180004ab0  mov     rcx, rdi
0x180004ab3  call    FreeMemory
0x180004ab8  lea     rcx, [rbx+8]; lpCriticalSection
0x180004abc  call    cs:__imp_DeleteCriticalSection
0x180004ac2  mov     r8d, 161h
0x180004ac8  lea     rdx, aHtdestroyhandl_0; "HtDestroyHandleTable"
0x180004acf  lea     rcx, [rsp+28h+arg_0]
0x180004ad4  call    FreeMemory
0x180004ad9  mov     rdi, [rsp+28h+arg_10]
0x180004ade  xor     eax, eax
0x180004ae0  add     rsp, 20h
0x180004ae4  pop     rbx
0x180004ae5  retn
0x180004ae6  mov     ecx, [rbx+70h]
0x180004ae9  xor     r8d, r8d
0x180004aec  mov     dword ptr [rbx+70h], 0FFFFFFFh
0x180004af3  test    edx, edx
0x180004af5  jz      short loc_180004A93
0x180004af7  nop     word ptr [rax+rax+00000000h]
0x180004b00  mov     rax, [rbx+40h]
0x180004b04  mov     edx, r8d
0x180004b07  shl     rdx, 5
0x180004b0b  cmp     qword ptr [rdx+rax], 0
0x180004b10  jnz     short loc_180004B20
0x180004b12  inc     r8d
0x180004b15  cmp     r8d, [rbx+48h]
0x180004b19  jb      short loc_180004B00
0x180004b1b  jmp     loc_180004A93
0x180004b20  mov     qword ptr [rdx+rax], 0
0x180004b28  mov     rax, [rbx+40h]
0x180004b2c  shl     ecx, 4
0x180004b2f  and     dword ptr [rdx+rax+1Ch], 0Fh
0x180004b34  or      [rdx+rax+1Ch], ecx
0x180004b38  mov     ecx, r8d
0x180004b3b  jmp     short loc_180004B12
0x180004b3d  mov     [rsp+28h+arg_8], rsi
0x180004b42  mov     esi, ecx
0x180004b44  shl     rsi, 5
0x180004b48  add     rsi, [rdi]
0x180004b4b  mov     rax, [rsi+10h]
0x180004b4f  test    rax, rax
0x180004b52  jz      short loc_180004B5D
0x180004b54  mov     rcx, [rsi+8]
0x180004b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5d  mov     ecx, [rsi+1Ch]
0x180004b60  shr     ecx, 4
0x180004b63  cmp     ecx, 0FFFFFFFh
0x180004b69  jnz     short loc_180004B42
0x180004b6b  mov     rsi, [rsp+28h+arg_8]
0x180004b70  jmp     loc_180004AA3
```
