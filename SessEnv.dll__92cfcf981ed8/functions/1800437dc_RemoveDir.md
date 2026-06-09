# RemoveDir

- ea: `0x1800437dc`
- end: `0x1800439c1`
- name: `RemoveDir`
- size: `485`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800282f0`
- `0x1800437dc`

## callees

- `0x18001ad2c`
- `0x18001ad38`
- `0x1800437dc`
- `0x1800439c8`
- `0x180043a10`
- `0x180043ba4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180043838`
- `ntdll!RtlAllocateHeap` at `0x180043838`
- `ntdll!RtlFreeHeap` at `0x180043961`
- `ntdll!RtlFreeHeap` at `0x180043961`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043905`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043926`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043984`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800439a1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043905`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043926`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180043984`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800439a1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004398d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18004398d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004396a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004396a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043912`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043912`

## pseudocode

```c
__int64 __fastcall RemoveDir(wchar_t *a1)
{
  const wchar_t *v1; // rdi
  void *v2; // r15
  __int64 v3; // rbx
  __int64 v4; // r13
  unsigned int v5; // r14d
  wchar_t *Heap; // rax
  wchar_t *v7; // rsi
  __int64 v8; // r14
  const wchar_t *v9; // r8
  int v10; // edx
  int v11; // edx
  DWORD v12; // r14d
  DWORD FileAttributesW; // eax
  DWORD v14; // ebx

  v1 = a1;
  v2 = (void *)opendir(a1);
  if ( !v2 )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( v1[v3] );
  v4 = (unsigned int)(v3 + 264);
  v5 = v3 + 264;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v4);
  v7 = Heap;
  if ( !Heap )
    return 0;
  wcscpy_s(Heap, v5, v1);
  if ( v7[(unsigned int)v3] != 92 && v7[(unsigned int)v3] != 47 )
  {
    wcscat_s(v7, v5, L"\\");
    LODWORD(v3) = v3 + 1;
  }
  v8 = readdir(v2);
  if ( v8 )
  {
    do
    {
      v9 = (const wchar_t *)(v8 + 4);
      v10 = *(unsigned __int16 *)(v8 + 4) - 46;
      if ( *(_WORD *)(v8 + 4) == 46 )
        v10 = *(unsigned __int16 *)(v8 + 6);
      if ( v10 )
      {
        v11 = *v9 - 46;
        if ( *v9 == 46 )
        {
          v11 = *(unsigned __int16 *)(v8 + 6) - 46;
          if ( *(_WORD *)(v8 + 6) == 46 )
            v11 = *(unsigned __int16 *)(v8 + 8);
        }
        if ( v11 )
        {
          wcscpy_s(&v7[(unsigned int)v3], (unsigned int)(v4 - v3), v9);
          v12 = *(_DWORD *)v8;
          if ( (v12 & 0x10) != 0 )
          {
            RemoveDir(v7);
          }
          else if ( ((v12 & 1) == 0 || SetFileAttributesW(v7, v12 & 0xFFFFFFFE)) && !DeleteFileW(v7) && (v12 & 1) == 0 )
          {
            SetFileAttributesW(v7, v12);
          }
        }
      }
      v8 = readdir(v2);
    }
    while ( v8 );
    v1 = a1;
  }
  closedir(v2);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  FileAttributesW = GetFileAttributesW(v1);
  v14 = FileAttributesW;
  if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
    SetFileAttributesW(v1, FileAttributesW & 0xFFFFFFFE);
  if ( !RemoveDirectoryW(v1) && (v14 & 1) != 0 )
    SetFileAttributesW(v1, v14);
  return 1;
}

```

## disassembly

```asm
0x1800437dc  mov     [rsp+arg_0], rcx
0x1800437e1  push    rbx
0x1800437e2  push    rbp
0x1800437e3  push    rsi
0x1800437e4  push    rdi
0x1800437e5  push    r12
0x1800437e7  push    r13
0x1800437e9  push    r14
0x1800437eb  push    r15
0x1800437ed  sub     rsp, 28h
0x1800437f1  mov     rdi, rcx
0x1800437f4  call    opendir
0x1800437f9  xor     ebp, ebp
0x1800437fb  mov     r15, rax
0x1800437fe  test    rax, rax
0x180043801  jz      loc_1800439AE
0x180043807  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004380b  inc     rbx
0x18004380e  cmp     [rdi+rbx*2], bp
0x180043812  jnz     short loc_18004380B
0x180043814  mov     rcx, gs:60h
0x18004381d  lea     r13d, [rbx+108h]
0x180043824  lea     r8, ds:0[r13*2]; Size
0x18004382c  mov     r14d, r13d
0x18004382f  mov     edx, 8; Flags
0x180043834  mov     rcx, [rcx+30h]; HeapHandle
0x180043838  call    cs:__imp_RtlAllocateHeap
0x18004383e  mov     rsi, rax
0x180043841  test    rax, rax
0x180043844  jz      loc_1800439AE
0x18004384a  mov     r8, rdi; Source
0x18004384d  mov     edx, r14d; SizeInWords
0x180043850  mov     rcx, rax; Destination
0x180043853  call    wcscpy_s
0x180043858  mov     ecx, ebx
0x18004385a  cmp     word ptr [rsi+rcx*2], 5Ch ; '\'
0x18004385f  jz      short loc_18004387C
0x180043861  cmp     word ptr [rsi+rcx*2], 2Fh ; '/'
0x180043866  jz      short loc_18004387C
0x180043868  lea     r8, Source; "\\"
0x18004386f  mov     edx, r14d; SizeInWords
0x180043872  mov     rcx, rsi; Destination
0x180043875  call    wcscat_s
0x18004387a  inc     ebx
0x18004387c  mov     eax, ebx
0x18004387e  mov     rcx, r15
0x180043881  lea     r12, [rsi+rax*2]
0x180043885  call    readdir
0x18004388a  mov     r14, rax
0x18004388d  test    rax, rax
0x180043890  jz      loc_180043947
0x180043896  mov     edi, 2Eh ; '.'
0x18004389b  lea     r8, [r14+4]; Source
0x18004389f  movzx   edx, word ptr [r8]
0x1800438a3  sub     edx, edi
0x1800438a5  jnz     short loc_1800438B1
0x1800438a7  movzx   edx, word ptr [r8+2]
0x1800438ac  movzx   ecx, bp
0x1800438af  sub     edx, ecx
0x1800438b1  test    edx, edx
0x1800438b3  jz      short loc_18004392E
0x1800438b5  movzx   edx, word ptr [r8]
0x1800438b9  sub     edx, edi
0x1800438bb  jnz     short loc_1800438D0
0x1800438bd  movzx   edx, word ptr [r8+2]
0x1800438c2  sub     edx, edi
0x1800438c4  jnz     short loc_1800438D0
0x1800438c6  movzx   edx, word ptr [r8+4]
0x1800438cb  movzx   ecx, bp
0x1800438ce  sub     edx, ecx
0x1800438d0  test    edx, edx
0x1800438d2  jz      short loc_18004392E
0x1800438d4  mov     edx, r13d
0x1800438d7  mov     rcx, r12; Destination
0x1800438da  sub     edx, ebx; SizeInWords
0x1800438dc  call    wcscpy_s
0x1800438e1  mov     r14d, [r14]
0x1800438e4  test    r14b, 10h
0x1800438e8  jz      short loc_1800438F4
0x1800438ea  mov     rcx, rsi
0x1800438ed  call    RemoveDir
0x1800438f2  jmp     short loc_18004392E
0x1800438f4  mov     ebp, r14d
0x1800438f7  and     ebp, 1
0x1800438fa  jz      short loc_18004390F
0x1800438fc  mov     edx, r14d
0x1800438ff  mov     rcx, rsi; lpFileName
0x180043902  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180043905  call    cs:__imp_SetFileAttributesW
0x18004390b  test    eax, eax
0x18004390d  jz      short loc_18004392C
0x18004390f  mov     rcx, rsi; lpFileName
0x180043912  call    cs:__imp_DeleteFileW
0x180043918  test    eax, eax
0x18004391a  jnz     short loc_18004392C
0x18004391c  test    ebp, ebp
0x18004391e  jnz     short loc_18004392C
0x180043920  mov     edx, r14d; dwFileAttributes
0x180043923  mov     rcx, rsi; lpFileName
0x180043926  call    cs:__imp_SetFileAttributesW
0x18004392c  xor     ebp, ebp
0x18004392e  mov     rcx, r15
0x180043931  call    readdir
0x180043936  mov     r14, rax
0x180043939  test    rax, rax
0x18004393c  jnz     loc_18004389B
0x180043942  mov     rdi, [rsp+68h+arg_0]
0x180043947  mov     rcx, r15; P
0x18004394a  call    closedir
0x18004394f  mov     rcx, gs:60h
0x180043958  mov     r8, rsi; P
0x18004395b  xor     edx, edx; Flags
0x18004395d  mov     rcx, [rcx+30h]; HeapHandle
0x180043961  call    cs:__imp_RtlFreeHeap
0x180043967  mov     rcx, rdi; lpFileName
0x18004396a  call    cs:__imp_GetFileAttributesW
0x180043970  mov     ebx, eax
0x180043972  cmp     eax, 0FFFFFFFFh
0x180043975  jz      short loc_18004398A
0x180043977  test    bl, 1
0x18004397a  jz      short loc_18004398A
0x18004397c  mov     edx, eax
0x18004397e  mov     rcx, rdi; lpFileName
0x180043981  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180043984  call    cs:__imp_SetFileAttributesW
0x18004398a  mov     rcx, rdi; lpPathName
0x18004398d  call    cs:__imp_RemoveDirectoryW
0x180043993  test    eax, eax
0x180043995  jnz     short loc_1800439A7
0x180043997  test    bl, 1
0x18004399a  jz      short loc_1800439A7
0x18004399c  mov     edx, ebx; dwFileAttributes
0x18004399e  mov     rcx, rdi; lpFileName
0x1800439a1  call    cs:__imp_SetFileAttributesW
0x1800439a7  mov     eax, 1
0x1800439ac  jmp     short loc_1800439B0
0x1800439ae  xor     eax, eax
0x1800439b0  add     rsp, 28h
0x1800439b4  pop     r15
0x1800439b6  pop     r14
0x1800439b8  pop     r13
0x1800439ba  pop     r12
0x1800439bc  pop     rdi
0x1800439bd  pop     rsi
0x1800439be  pop     rbp
0x1800439bf  pop     rbx
0x1800439c0  retn
```
