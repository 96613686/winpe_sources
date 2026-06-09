# SdbpCreateSearchPathPartsFromPath

- ea: `0x1400517e4`
- end: `0x140051919`
- name: `SdbpCreateSearchPathPartsFromPath`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400516bc`

## callees

- `0x140004553`
- `0x14003e364`
- `0x1400517e4`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140051810`
- `ntoskrnl!wcschr` at `0x140051810`

## string_xrefs

- `0x1400518f3`: `SdbpCreateSearchPathPartsFromPath`
- `0x1400518e6`: `Failed to allocate search path parts`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchPathPartsFromPath(const wchar_t *a1, _QWORD *a2)
{
  const wchar_t *v3; // rdi
  int i; // ebx
  wchar_t *v5; // rax
  _DWORD *Pool2_0; // rax
  _DWORD *v7; // r9
  unsigned int v8; // r10d
  __int64 v9; // rax
  _WORD *v10; // r8
  const wchar_t *j; // rdx
  wchar_t v12; // ax
  __int64 v14; // rcx

  v3 = a1;
  if ( a1 )
  {
    for ( i = *a1 != 0; ; ++i )
    {
      v5 = wcschr(a1, 0x3Bu);
      if ( !v5 )
        break;
      a1 = v5 + 1;
    }
    Pool2_0 = (_DWORD *)ExAllocatePool2_0(256, 48LL * (unsigned int)(i - 1) + 56, 1953517633);
    v7 = Pool2_0;
    if ( Pool2_0 )
    {
      *Pool2_0 = i;
      v8 = 0;
      v9 = -1;
      v10 = 0;
      do
        ++v9;
      while ( v3[v9] );
      for ( j = &v3[v9]; ; --j )
      {
        if ( j < v3 )
        {
          *a2 = v7;
          return 1;
        }
        v12 = *j;
        if ( *j == 92 )
          break;
        if ( v12 != 59 )
          goto LABEL_11;
LABEL_16:
        if ( v10 )
        {
          if ( v12 == 59 )
            ++j;
          v14 = 6LL * v8++;
          v7[2 * v14 + 4] = v10 - j + 1;
          v10 = 0;
          *(_QWORD *)&v7[2 * v14 + 2] = j;
        }
LABEL_12:
        ;
      }
      if ( !v10 )
        v10 = j;
LABEL_11:
      if ( v3 != j )
        goto LABEL_12;
      goto LABEL_16;
    }
    AslLogCallPrintf(1, "SdbpCreateSearchPathPartsFromPath", 3282, "Failed to allocate search path parts");
  }
  else
  {
    AslLogCallPrintf(1, "SdbpCreateSearchPathPartsFromPath", 3253, "Invalid argument");
  }
  return 0;
}

```

## disassembly

```asm
0x1400517e4  push    rbx
0x1400517e6  push    rbp
0x1400517e7  push    rdi
0x1400517e8  push    r14
0x1400517ea  push    r15
0x1400517ec  sub     rsp, 20h
0x1400517f0  xor     ebp, ebp
0x1400517f2  mov     r14, rdx
0x1400517f5  mov     rdi, rcx
0x1400517f8  test    rcx, rcx
0x1400517fb  jz      loc_1400518D7
0x140051801  cmp     [rcx], bp
0x140051804  lea     r15d, [rbp+3Bh]
0x140051808  mov     ebx, ebp
0x14005180a  setnz   bl
0x14005180d  mov     edx, r15d; Ch
0x140051810  call    cs:__imp_wcschr
0x140051817  nop     dword ptr [rax+rax+00h]
0x14005181c  test    rax, rax
0x14005181f  jnz     loc_140051908
0x140051825  lea     eax, [rbx-1]
0x140051828  mov     ecx, 100h
0x14005182d  lea     rdx, [rax+rax*2]
0x140051831  mov     r8d, 74705041h
0x140051837  shl     rdx, 4
0x14005183b  add     rdx, 38h ; '8'
0x14005183f  call    ExAllocatePool2_0
0x140051844  mov     r9, rax
0x140051847  test    rax, rax
0x14005184a  jz      loc_1400518E6
0x140051850  mov     [rax], ebx
0x140051852  mov     r10d, ebp
0x140051855  or      rax, 0FFFFFFFFFFFFFFFFh
0x140051859  mov     r8, rbp
0x14005185c  inc     rax
0x14005185f  cmp     [rdi+rax*2], bp
0x140051863  jnz     short loc_14005185C
0x140051865  lea     rdx, [rdi+rax*2]
0x140051869  cmp     rdx, rdi
0x14005186c  jb      short loc_140051888
0x14005186e  movzx   eax, word ptr [rdx]
0x140051871  cmp     ax, 5Ch ; '\'
0x140051875  jz      short loc_14005189D
0x140051877  cmp     ax, r15w
0x14005187b  jz      short loc_1400518A7
0x14005187d  cmp     rdi, rdx
0x140051880  jz      short loc_1400518A7
0x140051882  sub     rdx, 2
0x140051886  jmp     short loc_140051869
0x140051888  mov     [r14], r9
0x14005188b  mov     eax, 1
0x140051890  add     rsp, 20h
0x140051894  pop     r15
0x140051896  pop     r14
0x140051898  pop     rdi
0x140051899  pop     rbp
0x14005189a  pop     rbx
0x14005189b  retn
0x14005189d  test    r8, r8
0x1400518a0  jnz     short loc_14005187D
0x1400518a2  mov     r8, rdx
0x1400518a5  jmp     short loc_14005187D
0x1400518a7  test    r8, r8
0x1400518aa  jz      short loc_140051882
0x1400518ac  cmp     ax, r15w
0x1400518b0  jz      short loc_140051913
0x1400518b2  sub     r8, rdx
0x1400518b5  mov     eax, r10d
0x1400518b8  sar     r8, 1
0x1400518bb  inc     r8d
0x1400518be  lea     rcx, [rax+rax*2]
0x1400518c2  add     rcx, rcx
0x1400518c5  inc     r10d
0x1400518c8  mov     [r9+rcx*8+10h], r8d
0x1400518cd  mov     r8, rbp
0x1400518d0  mov     [r9+rcx*8+8], rdx
0x1400518d5  jmp     short loc_140051882
0x1400518d7  lea     r9, aInvalidArgumen; "Invalid argument"
0x1400518de  mov     r8d, 0CB5h
0x1400518e4  jmp     short loc_1400518F3
0x1400518e6  lea     r9, aFailedToAlloca_11; "Failed to allocate search path parts"
0x1400518ed  mov     r8d, 0CD2h
0x1400518f3  lea     rdx, aSdbpcreatesear; "SdbpCreateSearchPathPartsFromPath"
0x1400518fa  mov     ecx, 1
0x1400518ff  call    AslLogCallPrintf
0x140051904  xor     eax, eax
0x140051906  jmp     short loc_140051890
0x140051908  inc     ebx
0x14005190a  lea     rcx, [rax+2]
0x14005190e  jmp     loc_14005180D
0x140051913  add     rdx, 2
0x140051917  jmp     short loc_1400518B2
```
