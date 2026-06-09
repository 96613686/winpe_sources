# ATL::CSimpleMap<ulong,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<ulong,WTL::CMessageLoop *>>::RemoveAt(int)

- ea: `0x180006b40`
- end: `0x180006c82`
- name: `?RemoveAt@?$CSimpleMap@KPEAVCMessageLoop@WTL@@V?$CSimpleMapEqualHelper@KPEAVCMessageLoop@WTL@@@ATL@@@ATL@@QEAAHH@Z`
- size: `322`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e70`
- `0x180016710`

## callees

- `0x1800025f2`
- `0x180003858`
- `0x180006b40`
- `0x180032ad4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180006c14`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180006c39`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180006c14`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180006c39`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006bd2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006c66`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006bd2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006c66`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleMap<unsigned long,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<unsigned long,WTL::CMessageLoop *>>::RemoveAt(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rdi
  int v6; // ecx
  __int64 v7; // rcx
  size_t v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax

  v4 = (int)a2;
  if ( (a2 & 0x80000000) != 0LL )
    return 0;
  v6 = *(_DWORD *)(a1 + 16);
  if ( (int)a2 >= v6 )
    return 0;
  if ( (_DWORD)a2 != v6 - 1 )
  {
    v7 = (unsigned int)(v6 - a2);
    v8 = 4LL * ((int)v7 - 1);
    if ( v8 )
    {
      a4 = *(_QWORD *)a1 + 4LL * (int)a2;
      if ( !a4 )
        goto LABEL_11;
      a2 = a4 + 4;
      if ( a4 == -4 )
        goto LABEL_11;
      if ( 4LL * (int)v7 < v8 )
      {
LABEL_23:
        *(_DWORD *)_o__errno(v7, a2, v8, a4) = 34;
LABEL_24:
        invalid_parameter_noinfo();
        ATL::AtlThrowImpl(-2147024809);
      }
      memmove_0((void *)(*(_QWORD *)a1 + 4 * v4), (const void *)a2, v8);
    }
    a2 = (unsigned int)(*(_DWORD *)(a1 + 16) - v4);
    v8 = 8LL * ((int)a2 - 1);
    if ( !v8 )
      goto LABEL_15;
    v7 = *(_QWORD *)(a1 + 8) + 8 * v4;
    if ( v7 )
    {
      a4 = v7 + 8;
      if ( v7 != -8 )
      {
        if ( 8LL * (int)a2 >= v8 )
        {
          memmove_0((void *)v7, (const void *)(v7 + 8), v8);
          goto LABEL_15;
        }
        goto LABEL_23;
      }
    }
LABEL_11:
    *(_DWORD *)_o__errno(v7, a2, v8, a4) = 22;
    goto LABEL_24;
  }
LABEL_15:
  v9 = _o__recalloc(*(_QWORD *)a1, *(_DWORD *)(a1 + 16) - 1, 4);
  if ( v9 || *(_DWORD *)(a1 + 16) == 1 )
    *(_QWORD *)a1 = v9;
  v10 = _o__recalloc(*(_QWORD *)(a1 + 8), *(_DWORD *)(a1 + 16) - 1, 8);
  if ( v10 || *(_DWORD *)(a1 + 16) == 1 )
    *(_QWORD *)(a1 + 8) = v10;
  --*(_DWORD *)(a1 + 16);
  return 1;
}

```

## disassembly

```asm
0x180006b40  mov     [rsp+arg_0], rbx
0x180006b45  mov     [rsp+arg_8], rsi
0x180006b4a  push    rdi
0x180006b4b  sub     rsp, 20h
0x180006b4f  movsxd  rdi, edx
0x180006b52  mov     rbx, rcx
0x180006b55  test    edx, edx
0x180006b57  js      loc_180006C54
0x180006b5d  mov     ecx, [rcx+10h]
0x180006b60  cmp     edi, ecx
0x180006b62  jge     loc_180006C54
0x180006b68  lea     eax, [rcx-1]
0x180006b6b  cmp     edi, eax
0x180006b6d  jz      loc_180006C00
0x180006b73  sub     ecx, edi
0x180006b75  lea     eax, [rcx-1]
0x180006b78  movsxd  r8, eax
0x180006b7b  shl     r8, 2; Size
0x180006b7f  test    r8, r8
0x180006b82  jz      short loc_180006BB1
0x180006b84  mov     rax, [rbx]
0x180006b87  lea     r9, [rax+rdi*4]
0x180006b8b  test    r9, r9
0x180006b8e  jz      short loc_180006BD2
0x180006b90  lea     rdx, [r9+4]; Src
0x180006b94  test    rdx, rdx
0x180006b97  jz      short loc_180006BD2
0x180006b99  movsxd  rax, ecx
0x180006b9c  shl     rax, 2
0x180006ba0  cmp     rax, r8
0x180006ba3  jb      loc_180006C66
0x180006ba9  mov     rcx, r9; void *
0x180006bac  call    memmove_0
0x180006bb1  mov     edx, [rbx+10h]
0x180006bb4  sub     edx, edi
0x180006bb6  lea     eax, [rdx-1]
0x180006bb9  movsxd  r8, eax
0x180006bbc  shl     r8, 3; Size
0x180006bc0  test    r8, r8
0x180006bc3  jz      short loc_180006C00
0x180006bc5  mov     rax, [rbx+8]
0x180006bc9  lea     rcx, [rax+rdi*8]; void *
0x180006bcd  test    rcx, rcx
0x180006bd0  jnz     short loc_180006BE3
0x180006bd2  call    cs:__imp__o__errno
0x180006bd8  mov     dword ptr [rax], 16h
0x180006bde  jmp     loc_180006C72
0x180006be3  lea     r9, [rcx+8]
0x180006be7  test    r9, r9
0x180006bea  jz      short loc_180006BD2
0x180006bec  movsxd  rax, edx
0x180006bef  shl     rax, 3
0x180006bf3  cmp     rax, r8
0x180006bf6  jb      short loc_180006C66
0x180006bf8  mov     rdx, r9; Src
0x180006bfb  call    memmove_0
0x180006c00  mov     eax, [rbx+10h]
0x180006c03  mov     edi, 1
0x180006c08  mov     rcx, [rbx]
0x180006c0b  sub     eax, edi
0x180006c0d  movsxd  rdx, eax
0x180006c10  lea     r8d, [rdi+3]
0x180006c14  call    cs:__imp__o__recalloc
0x180006c1a  test    rax, rax
0x180006c1d  jnz     short loc_180006C24
0x180006c1f  cmp     [rbx+10h], edi
0x180006c22  jnz     short loc_180006C27
0x180006c24  mov     [rbx], rax
0x180006c27  mov     eax, [rbx+10h]
0x180006c2a  mov     r8d, 8
0x180006c30  mov     rcx, [rbx+8]
0x180006c34  sub     eax, edi
0x180006c36  movsxd  rdx, eax
0x180006c39  call    cs:__imp__o__recalloc
0x180006c3f  test    rax, rax
0x180006c42  jnz     short loc_180006C49
0x180006c44  cmp     [rbx+10h], edi
0x180006c47  jnz     short loc_180006C4D
0x180006c49  mov     [rbx+8], rax
0x180006c4d  dec     dword ptr [rbx+10h]
0x180006c50  mov     eax, edi
0x180006c52  jmp     short loc_180006C56
0x180006c54  xor     eax, eax
0x180006c56  mov     rbx, [rsp+28h+arg_0]
0x180006c5b  mov     rsi, [rsp+28h+arg_8]
0x180006c60  add     rsp, 20h
0x180006c64  pop     rdi
0x180006c65  retn
0x180006c66  call    cs:__imp__o__errno
0x180006c6c  mov     dword ptr [rax], 22h ; '"'
0x180006c72  call    _invalid_parameter_noinfo
0x180006c77  mov     ecx, 80070057h; int
0x180006c7c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
