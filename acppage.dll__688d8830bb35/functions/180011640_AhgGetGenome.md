# AhgGetGenome

- ea: `0x180011640`
- end: `0x18001191b`
- name: `AhgGetGenome`
- size: `731`
- prototype: `__int64 __fastcall(unsigned __int64 *, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000bb48`

## callees

- `0x180010d10`
- `0x180011640`
- `0x180012224`
- `0x180015220`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180011723`
- `ntdll!RtlFreeHeap` at `0x1800118ce`
- `ntdll!RtlFreeHeap` at `0x180011723`
- `ntdll!RtlFreeHeap` at `0x1800118ce`
- `ntdll!RtlAllocateHeap` at `0x180011685`
- `ntdll!RtlAllocateHeap` at `0x180011685`
- `KERNEL32!GetLastError` at `0x18001178b`
- `KERNEL32!GetLastError` at `0x1800117e0`
- `KERNEL32!GetLastError` at `0x18001181f`
- `KERNEL32!GetLastError` at `0x18001178b`
- `KERNEL32!GetLastError` at `0x1800117e0`
- `KERNEL32!GetLastError` at `0x18001181f`
- `KERNEL32!CloseHandle` at `0x1800118ea`
- `KERNEL32!CloseHandle` at `0x1800118f9`
- `KERNEL32!CloseHandle` at `0x1800118ea`
- `KERNEL32!CloseHandle` at `0x1800118f9`
- `KERNEL32!CreateFileW` at `0x18001177c`
- `KERNEL32!CreateFileW` at `0x18001177c`
- `KERNEL32!UnmapViewOfFile` at `0x1800118dc`
- `KERNEL32!UnmapViewOfFile` at `0x1800118dc`
- `KERNEL32!CreateFileMappingW` at `0x1800117d2`
- `KERNEL32!CreateFileMappingW` at `0x1800117d2`
- `KERNEL32!MapViewOfFile` at `0x180011811`
- `KERNEL32!MapViewOfFile` at `0x180011811`

## string_xrefs

- `0x1800116a0`: `AhgGenomeCreate`
- `0x180011700`: `AhgGenomeCreate`
- `0x18001172e`: `Cannot create genome handle [%d]`
- `0x180011882`: `Cannot compute genome [%d]`

## pseudocode

```c
__int64 __fastcall AhgGetGenome(unsigned __int64 *a1, const WCHAR *a2)
{
  void *v2; // r15
  unsigned int v5; // esi
  _WORD *Heap; // rax
  void *v7; // rbx
  __int64 v8; // rcx
  const WCHAR *v9; // r8
  __int64 v10; // rdx
  _WORD *v11; // rcx
  const void *v12; // r12
  HANDLE FileW; // rax
  void *v14; // r14
  DWORD LastError; // eax
  const char *v16; // r9
  __int64 v17; // r8
  DWORD All; // edi
  HANDLE FileMappingW; // rax
  const void *v20; // rax
  int v22; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  *a1 = 0;
  v22 = 0;
  v5 = 8;
  v23 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x338u);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "AhgGenomeCreate", 172, "Out of memory");
LABEL_11:
    AslLogCallPrintf(1, "AhgGetGenome", 849, "Cannot create genome handle [%d]");
    return v5;
  }
  v8 = 2147483646;
  v9 = a2;
  v10 = 260;
  do
  {
    if ( !v8 )
      break;
    if ( !*v9 )
      break;
    *Heap++ = *v9++;
    --v8;
    --v10;
  }
  while ( v10 );
  v11 = Heap - 1;
  if ( v10 )
    v11 = Heap;
  *v11 = 0;
  if ( !v10 )
  {
    AslLogCallPrintf(1, "AhgGenomeCreate", 179, "Buffer overflow");
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v5 = 111;
    goto LABEL_11;
  }
  v12 = 0;
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v14 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v16 = "Bad file name [%d]";
    v17 = 866;
    All = LastError;
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 0x11000002u, 0, 0, 0);
    v2 = FileMappingW;
    if ( FileMappingW )
    {
      v20 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v12 = v20;
      if ( v20 )
      {
        All = AhgGenomeGetAll(v7, v14, v20);
        if ( All )
        {
          v16 = "Cannot get attributes [%d]";
          v17 = 903;
        }
        else
        {
          All = AhgGenomeCompute(&v22, &v23, v7);
          if ( !All )
          {
            *a1 = ((unsigned __int64)v23 << 32) | ((BYTE2(v22) | ((unsigned __int8)v22 << 8)) << 16);
            All = 0;
            goto LABEL_26;
          }
          v16 = "Cannot compute genome [%d]";
          v17 = 913;
        }
      }
      else
      {
        All = GetLastError();
        if ( All == 8 )
          goto LABEL_26;
        v16 = "Failed to map a view of file mapping [%d]";
        v17 = 892;
      }
    }
    else
    {
      All = GetLastError();
      if ( All == 8 )
        goto LABEL_26;
      v16 = "Failed to map file [%d]";
      v17 = 879;
    }
  }
  AslLogCallPrintf(1, "AhgGetGenome", v17, v16);
LABEL_26:
  v5 = All;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v12 )
    UnmapViewOfFile(v12);
  if ( v2 )
    CloseHandle(v2);
  if ( v14 != (void *)-1LL )
    CloseHandle(v14);
  return v5;
}

```

## disassembly

```asm
0x180011640  mov     rax, rsp
0x180011643  mov     [rax+10h], rbx
0x180011647  mov     [rax+20h], rsi
0x18001164b  push    rdi
0x18001164c  push    r12
0x18001164e  push    r13
0x180011650  push    r14
0x180011652  push    r15
0x180011654  sub     rsp, 40h
0x180011658  xor     r15d, r15d
0x18001165b  mov     r13, rcx
0x18001165e  mov     [rcx], r15
0x180011661  mov     rdi, rdx
0x180011664  mov     rcx, gs:60h
0x18001166d  mov     r8d, 338h; Size
0x180011673  mov     [rax+8], r15d
0x180011677  lea     esi, [r15+8]
0x18001167b  mov     [rax+18h], r15d
0x18001167f  mov     edx, esi; Flags
0x180011681  mov     rcx, [rcx+30h]; HeapHandle
0x180011685  call    cs:__imp_RtlAllocateHeap
0x18001168b  mov     rbx, rax
0x18001168e  test    rax, rax
0x180011691  jnz     short loc_1800116B1
0x180011693  lea     r9, aOutOfMemory; "Out of memory"
0x18001169a  mov     r8d, 0ACh
0x1800116a0  lea     rdx, aAhggenomecreat; "AhgGenomeCreate"
0x1800116a7  lea     ecx, [rsi-7]
0x1800116aa  call    AslLogCallPrintf
0x1800116af  jmp     short loc_18001172E
0x1800116b1  mov     ecx, 7FFFFFFEh
0x1800116b6  mov     r8, rdi
0x1800116b9  mov     edx, 104h
0x1800116be  test    rcx, rcx
0x1800116c1  jz      short loc_1800116E2
0x1800116c3  movzx   r9d, word ptr [r8]
0x1800116c7  test    r9w, r9w
0x1800116cb  jz      short loc_1800116E2
0x1800116cd  mov     [rax], r9w
0x1800116d1  add     r8, 2
0x1800116d5  add     rax, 2
0x1800116d9  dec     rcx
0x1800116dc  sub     rdx, 1
0x1800116e0  jnz     short loc_1800116BE
0x1800116e2  test    rdx, rdx
0x1800116e5  lea     rcx, [rax-2]
0x1800116e9  cmovnz  rcx, rax
0x1800116ed  mov     [rcx], r15w
0x1800116f1  jnz     short loc_180011755
0x1800116f3  lea     r9, aBufferOverflow; "Buffer overflow"
0x1800116fa  mov     r8d, 0B3h
0x180011700  lea     rdx, aAhggenomecreat; "AhgGenomeCreate"
0x180011707  mov     ecx, 1
0x18001170c  call    AslLogCallPrintf
0x180011711  mov     rcx, gs:60h
0x18001171a  mov     r8, rbx; P
0x18001171d  xor     edx, edx; Flags
0x18001171f  mov     rcx, [rcx+30h]; HeapHandle
0x180011723  call    cs:__imp_RtlFreeHeap
0x180011729  mov     esi, 6Fh ; 'o'
0x18001172e  lea     r9, aCannotCreateGe; "Cannot create genome handle [%d]"
0x180011735  mov     [rsp+68h+dwCreationDisposition], esi
0x180011739  mov     r8d, 351h
0x18001173f  lea     rdx, aAhggetgenome; "AhgGetGenome"
0x180011746  mov     ecx, 1
0x18001174b  call    AslLogCallPrintf
0x180011750  jmp     loc_1800118FF
0x180011755  xor     r9d, r9d; lpSecurityAttributes
0x180011758  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x18001175d  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180011765  mov     edx, 80000000h; dwDesiredAccess
0x18001176a  mov     rcx, rdi; lpFileName
0x18001176d  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180011775  mov     r12, r15
0x180011778  lea     r8d, [r9+7]; dwShareMode
0x18001177c  call    cs:__imp_CreateFileW
0x180011782  mov     r14, rax
0x180011785  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011789  jnz     short loc_1800117BA
0x18001178b  call    cs:__imp_GetLastError
0x180011791  lea     r9, aBadFileNameD; "Bad file name [%d]"
0x180011798  mov     r8d, 362h
0x18001179e  mov     edi, eax
0x1800117a0  lea     rdx, aAhggetgenome; "AhgGetGenome"
0x1800117a7  mov     [rsp+68h+dwCreationDisposition], eax
0x1800117ab  mov     ecx, 1
0x1800117b0  call    AslLogCallPrintf
0x1800117b5  jmp     loc_1800118BA
0x1800117ba  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r15; lpName
0x1800117bf  xor     r9d, r9d; dwMaximumSizeHigh
0x1800117c2  xor     edx, edx; lpFileMappingAttributes
0x1800117c4  mov     [rsp+68h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x1800117c9  mov     r8d, 11000002h; flProtect
0x1800117cf  mov     rcx, r14; hFile
0x1800117d2  call    cs:__imp_CreateFileMappingW
0x1800117d8  mov     r15, rax
0x1800117db  test    rax, rax
0x1800117de  jnz     short loc_1800117FF
0x1800117e0  call    cs:__imp_GetLastError
0x1800117e6  mov     edi, eax
0x1800117e8  cmp     eax, esi
0x1800117ea  jz      loc_1800118BA
0x1800117f0  lea     r9, aFailedToMapFil; "Failed to map file [%d]"
0x1800117f7  mov     r8d, 36Fh
0x1800117fd  jmp     short loc_1800117A0
0x1800117ff  xor     r9d, r9d; dwFileOffsetLow
0x180011802  mov     qword ptr [rsp+68h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180011807  xor     r8d, r8d; dwFileOffsetHigh
0x18001180a  mov     rcx, rax; hFileMappingObject
0x18001180d  lea     edx, [r9+4]; dwDesiredAccess
0x180011811  call    cs:__imp_MapViewOfFile
0x180011817  mov     r12, rax
0x18001181a  test    rax, rax
0x18001181d  jnz     short loc_180011841
0x18001181f  call    cs:__imp_GetLastError
0x180011825  mov     edi, eax
0x180011827  cmp     eax, esi
0x180011829  jz      loc_1800118BA
0x18001182f  lea     r9, aFailedToMapAVi; "Failed to map a view of file mapping [%"...
0x180011836  mov     r8d, 37Ch
0x18001183c  jmp     loc_1800117A0
0x180011841  mov     r8, rax
0x180011844  mov     rdx, r14
0x180011847  mov     rcx, rbx
0x18001184a  call    AhgGenomeGetAll
0x18001184f  mov     edi, eax
0x180011851  test    eax, eax
0x180011853  jz      short loc_180011867
0x180011855  lea     r9, aCannotGetAttri; "Cannot get attributes [%d]"
0x18001185c  mov     r8d, 387h
0x180011862  jmp     loc_1800117A0
0x180011867  mov     r8, rbx
0x18001186a  lea     rdx, [rsp+68h+arg_10]
0x180011872  lea     rcx, [rsp+68h+arg_0]
0x180011877  call    AhgGenomeCompute
0x18001187c  mov     edi, eax
0x18001187e  test    eax, eax
0x180011880  jz      short loc_180011894
0x180011882  lea     r9, aCannotComputeG; "Cannot compute genome [%d]"
0x180011889  mov     r8d, 391h
0x18001188f  jmp     loc_1800117A0
0x180011894  movzx   ecx, [rsp+68h+arg_0]
0x180011899  movzx   eax, [rsp+68h+arg_2]
0x18001189e  shl     ecx, 8
0x1800118a1  or      ecx, eax
0x1800118a3  mov     eax, [rsp+68h+arg_10]
0x1800118aa  shl     rax, 20h
0x1800118ae  shl     ecx, 10h
0x1800118b1  or      rcx, rax
0x1800118b4  mov     [r13+0], rcx
0x1800118b8  xor     edi, edi
0x1800118ba  mov     rcx, gs:60h
0x1800118c3  mov     r8, rbx; P
0x1800118c6  xor     edx, edx; Flags
0x1800118c8  mov     esi, edi
0x1800118ca  mov     rcx, [rcx+30h]; HeapHandle
0x1800118ce  call    cs:__imp_RtlFreeHeap
0x1800118d4  test    r12, r12
0x1800118d7  jz      short loc_1800118E2
0x1800118d9  mov     rcx, r12; lpBaseAddress
0x1800118dc  call    cs:__imp_UnmapViewOfFile
0x1800118e2  test    r15, r15
0x1800118e5  jz      short loc_1800118F0
0x1800118e7  mov     rcx, r15; hObject
0x1800118ea  call    cs:__imp_CloseHandle
0x1800118f0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800118f4  jz      short loc_1800118FF
0x1800118f6  mov     rcx, r14; hObject
0x1800118f9  call    cs:__imp_CloseHandle
0x1800118ff  lea     r11, [rsp+68h+var_28]
0x180011904  mov     eax, esi
0x180011906  mov     rbx, [r11+38h]
0x18001190a  mov     rsi, [r11+48h]
0x18001190e  mov     rsp, r11
0x180011911  pop     r15
0x180011913  pop     r14
0x180011915  pop     r13
0x180011917  pop     r12
0x180011919  pop     rdi
0x18001191a  retn
```
