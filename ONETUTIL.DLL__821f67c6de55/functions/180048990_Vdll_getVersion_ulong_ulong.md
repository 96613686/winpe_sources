# Vdll::getVersion(ulong *,ulong *)

- ea: `0x180048990`
- end: `0x180048ac4`
- name: `?getVersion@Vdll@@QEAADPEAK0@Z`
- size: `308`
- prototype: `char __fastcall(Vdll *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180048990`
- `0x180083790`
- `0x1800838f0`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!SearchPathA` at `0x1800489f6`
- `KERNEL32!SearchPathA` at `0x1800489f6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048a98`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180048a98`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180048a28`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180048a28`
- `VERSION!VerQueryValueA` at `0x180048a60`
- `VERSION!VerQueryValueA` at `0x180048a60`
- `VERSION!GetFileVersionInfoA` at `0x180048a40`
- `VERSION!GetFileVersionInfoA` at `0x180048a40`
- `VERSION!GetFileVersionInfoSizeA` at `0x180048a0a`
- `VERSION!GetFileVersionInfoSizeA` at `0x180048a0a`

## pseudocode

```c
bool __fastcall Vdll::getVersion(LPCSTR *this, unsigned int *a2, unsigned int *a3)
{
  DWORD FileVersionInfoSizeA; // ebp
  void *v7; // rax
  void *v8; // rdi
  BOOL FileVersionInfoA; // eax
  bool v10; // bp
  BOOL v11; // eax
  _DWORD *v12; // rcx
  DWORD dwHandle; // [rsp+30h] [rbp-158h] BYREF
  unsigned int puLen; // [rsp+34h] [rbp-154h] BYREF
  LPVOID v15; // [rsp+38h] [rbp-150h] BYREF
  LPSTR FilePart; // [rsp+40h] [rbp-148h] BYREF
  CHAR Buffer[272]; // [rsp+50h] [rbp-138h] BYREF

  if ( !a2 )
  {
    if ( !a3 )
      return 0;
    goto LABEL_5;
  }
  *a2 = 0;
  if ( a3 )
LABEL_5:
    *a3 = 0;
  if ( !SearchPathA(0, *this, 0, 0x105u, Buffer, &FilePart) )
    return 0;
  FileVersionInfoSizeA = GetFileVersionInfoSizeA(Buffer, &dwHandle);
  if ( !FileVersionInfoSizeA )
    return 0;
  if ( dword_1802B0018 )
    v7 = COWSAllocator::AllocCurrentHeap(FileVersionInfoSizeA);
  else
    v7 = malloc(FileVersionInfoSizeA);
  v8 = v7;
  FileVersionInfoA = GetFileVersionInfoA(Buffer, dwHandle, FileVersionInfoSizeA, v7);
  v10 = FileVersionInfoA;
  if ( FileVersionInfoA )
  {
    v11 = VerQueryValueA(v8, "\\", &v15, &puLen);
    v10 = v11;
    if ( v11 )
    {
      v12 = v15;
      if ( a2 )
        *a2 = *((_DWORD *)v15 + 2);
      if ( a3 )
        *a3 = v12[3];
    }
  }
  if ( dword_1802B0018 )
    COWSAllocator::Free(v8);
  else
    free(v8);
  return v10;
}

```

## disassembly

```asm
0x180048990  mov     [rsp+arg_18], rbx
0x180048995  push    rbp
0x180048996  push    rsi
0x180048997  push    rdi
0x180048998  sub     rsp, 170h
0x18004899f  mov     rax, cs:__security_cookie
0x1800489a6  xor     rax, rsp
0x1800489a9  mov     [rsp+188h+var_28], rax
0x1800489b1  mov     rbx, r8
0x1800489b4  mov     rsi, rdx
0x1800489b7  test    rdx, rdx
0x1800489ba  jnz     short loc_1800489C8
0x1800489bc  test    rbx, rbx
0x1800489bf  jnz     short loc_1800489D0
0x1800489c1  xor     al, al
0x1800489c3  jmp     loc_180048AA1
0x1800489c8  and     dword ptr [rdx], 0
0x1800489cb  test    rbx, rbx
0x1800489ce  jz      short loc_1800489D4
0x1800489d0  and     dword ptr [r8], 0
0x1800489d4  mov     rdx, [rcx]; lpFileName
0x1800489d7  lea     rax, [rsp+188h+FilePart]
0x1800489dc  mov     [rsp+188h+lpFilePart], rax; lpFilePart
0x1800489e1  mov     r9d, 105h; nBufferLength
0x1800489e7  lea     rax, [rsp+188h+Buffer]
0x1800489ec  xor     r8d, r8d; lpExtension
0x1800489ef  xor     ecx, ecx; lpPath
0x1800489f1  mov     [rsp+188h+lpBuffer], rax; lpBuffer
0x1800489f6  call    cs:SearchPathA
0x1800489fc  test    eax, eax
0x1800489fe  jz      short loc_1800489C1
0x180048a00  lea     rdx, [rsp+188h+dwHandle]; lpdwHandle
0x180048a05  lea     rcx, [rsp+188h+Buffer]; lptstrFilename
0x180048a0a  call    cs:GetFileVersionInfoSizeA
0x180048a10  mov     ebp, eax
0x180048a12  test    eax, eax
0x180048a14  jz      short loc_1800489C1
0x180048a16  cmp     cs:dword_1802B0018, 0
0x180048a1d  mov     ecx, ebp; unsigned __int64
0x180048a1f  jz      short loc_180048A28
0x180048a21  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180048a26  jmp     short loc_180048A2E
0x180048a28  call    cs:malloc
0x180048a2e  mov     edx, [rsp+188h+dwHandle]; dwHandle
0x180048a32  lea     rcx, [rsp+188h+Buffer]; lptstrFilename
0x180048a37  mov     r9, rax; lpData
0x180048a3a  mov     r8d, ebp; dwLen
0x180048a3d  mov     rdi, rax
0x180048a40  call    cs:GetFileVersionInfoA
0x180048a46  mov     ebp, eax
0x180048a48  test    eax, eax
0x180048a4a  jz      short loc_180048A85
0x180048a4c  lea     r9, [rsp+188h+puLen]; puLen
0x180048a51  mov     rcx, rdi; pBlock
0x180048a54  lea     r8, [rsp+188h+var_150]; lplpBuffer
0x180048a59  lea     rdx, SubBlock; "\\"
0x180048a60  call    cs:VerQueryValueA
0x180048a66  mov     ebp, eax
0x180048a68  test    eax, eax
0x180048a6a  jz      short loc_180048A85
0x180048a6c  mov     rcx, [rsp+188h+var_150]
0x180048a71  test    rsi, rsi
0x180048a74  jz      short loc_180048A7B
0x180048a76  mov     eax, [rcx+8]
0x180048a79  mov     [rsi], eax
0x180048a7b  test    rbx, rbx
0x180048a7e  jz      short loc_180048A85
0x180048a80  mov     eax, [rcx+0Ch]
0x180048a83  mov     [rbx], eax
0x180048a85  cmp     cs:dword_1802B0018, 0
0x180048a8c  mov     rcx, rdi; void *
0x180048a8f  jz      short loc_180048A98
0x180048a91  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x180048a96  jmp     short loc_180048A9E
0x180048a98  call    cs:free
0x180048a9e  mov     al, bpl
0x180048aa1  mov     rcx, [rsp+188h+var_28]
0x180048aa9  xor     rcx, rsp
0x180048aac  call    sub_1801503E0
0x180048ab1  mov     rbx, [rsp+188h+arg_18]
0x180048ab9  add     rsp, 170h
0x180048ac0  pop     rdi
0x180048ac1  pop     rsi
0x180048ac2  pop     rbp
0x180048ac3  retn
```
