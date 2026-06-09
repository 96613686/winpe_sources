# BfspServiceBootStl

- ea: `0x14000c8d8`
- end: `0x14000cc72`
- name: `BfspServiceBootStl`
- size: `922`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x140009fd4`

## callees

- `0x140002b7c`
- `0x14000bd28`
- `0x14000c8d8`
- `0x14000dba4`
- `0x14000e628`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000c934`
- `KERNEL32!SetLastError` at `0x14000c983`
- `KERNEL32!SetLastError` at `0x14000c934`
- `KERNEL32!SetLastError` at `0x14000c983`
- `KERNEL32!GetLastError` at `0x14000cb0f`
- `KERNEL32!GetLastError` at `0x14000cb0f`
- `KERNEL32!HeapFree` at `0x14000cc45`
- `KERNEL32!HeapFree` at `0x14000cc59`
- `KERNEL32!HeapFree` at `0x14000cc45`
- `KERNEL32!HeapFree` at `0x14000cc59`
- `KERNEL32!HeapAlloc` at `0x14000c923`
- `KERNEL32!HeapAlloc` at `0x14000c970`
- `KERNEL32!HeapAlloc` at `0x14000c923`
- `KERNEL32!HeapAlloc` at `0x14000c970`
- `KERNEL32!GetProcessHeap` at `0x14000c90e`
- `KERNEL32!GetProcessHeap` at `0x14000c961`
- `KERNEL32!GetProcessHeap` at `0x14000cc37`
- `KERNEL32!GetProcessHeap` at `0x14000cc4b`
- `KERNEL32!GetProcessHeap` at `0x14000c90e`
- `KERNEL32!GetProcessHeap` at `0x14000c961`
- `KERNEL32!GetProcessHeap` at `0x14000cc37`
- `KERNEL32!GetProcessHeap` at `0x14000cc4b`

## string_xrefs

- `0x14000cb18`: `Error copying %s to %s. Last Error = %#x`
- `0x14000cb38`: `Source Boot.stl (%s) does not exist. Will skip copying %s`
- `0x14000ca9c`: `Destination Boot.stl exists. Will copy both boot.stls (current and pending) to the destination.`
- `0x14000cc21`: `Source Pending Boot.stl (%s) does not exist. Will skip copying %s`

## pseudocode

```c
__int64 __fastcall BfspServiceBootStl(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rax
  unsigned __int64 v6; // r12
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  char *v9; // rsi
  unsigned int v10; // ebx
  __int64 v11; // rax
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  __int64 v16; // rax
  char *v17; // r13
  unsigned __int16 *v18; // rdi
  __int64 v19; // r15
  const wchar_t *v20; // r12
  __int64 v21; // rbp
  __int64 v22; // rcx
  const wchar_t *v23; // r8
  __int64 v24; // rdx
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // rcx
  const wchar_t *v28; // r8
  __int64 v29; // rdx
  char *v30; // rax
  char *v31; // rcx
  __int64 v32; // rcx
  const wchar_t *v33; // r8
  __int64 v34; // rdx
  char *v35; // rax
  char *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  const wchar_t *v39; // rdx
  bool v40; // zf
  unsigned __int16 *v41; // rcx
  const wchar_t *v42; // rax
  char *v43; // rcx
  HANDLE v44; // rax
  HANDLE v45; // rax
  DWORD LastError; // [rsp+20h] [rbp-58h]
  unsigned __int64 v48; // [rsp+90h] [rbp+18h]
  int v49; // [rsp+90h] [rbp+18h]

  v2 = -1;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  v6 = v4 + 262;
  v7 = 2 * (v4 + 262);
  ProcessHeap = GetProcessHeap();
  v9 = (char *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a2 + 2 * v11) );
    v48 = v11 + 262;
    v12 = 2 * (v11 + 262);
    v13 = GetProcessHeap();
    v14 = (unsigned __int16 *)HeapAlloc(v13, 8u, v12);
    v10 = 0;
    v15 = v14;
    if ( !v14 )
    {
      SetLastError(8u);
LABEL_60:
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v9);
      return v10;
    }
    StringCchPrintfW((unsigned __int16 *)v9, v6, L"%s\\", a1);
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&v9[2 * v16] );
    v17 = &v9[2 * v16];
    StringCchPrintfW(v15, v48, L"%s\\", a2);
    do
      ++v2;
    while ( v15[v2] );
    v18 = &v15[v2];
    v19 = 2147483646;
    v20 = L"boot.stl";
    v21 = 261;
    v22 = 2147483646;
    v23 = L"boot.stl";
    v24 = 261;
    v25 = v18;
    do
    {
      if ( !v22 )
        break;
      if ( !*v23 )
        break;
      *v25++ = *v23++;
      --v22;
      --v24;
    }
    while ( v24 );
    v26 = v25 - 1;
    if ( v24 )
      v26 = v25;
    *v26 = 0;
    if ( (unsigned int)BfspFileExists(v15) )
    {
      BfspLogMessage(
        2,
        L"Destination Boot.stl exists. Will copy both boot.stls (current and pending) to the destination.");
      v49 = 0;
    }
    else
    {
      v27 = 2147483646;
      v28 = L"boot.pnd.stl";
      v29 = 261;
      v30 = v17;
      do
      {
        if ( !v27 )
          break;
        if ( !*v28 )
          break;
        *(_WORD *)v30 = *v28++;
        v30 += 2;
        --v27;
        --v29;
      }
      while ( v29 );
      v31 = v30 - 2;
      if ( v29 )
        v31 = v30;
      *(_WORD *)v31 = 0;
      BfspLogMessage(
        2,
        L"Destination Boot.stl does not exist. Will enforce Pending Boot.stl (%s) as Boot.stl. (%s)",
        v9,
        v15);
      v49 = 1;
    }
    v32 = 2147483646;
    v33 = L"boot.stl";
    v34 = 261;
    v35 = v17;
    do
    {
      if ( !v32 )
        break;
      if ( !*v33 )
        break;
      *(_WORD *)v35 = *v33++;
      v35 += 2;
      --v32;
      --v34;
    }
    while ( v34 );
    v36 = v35 - 2;
    if ( v34 )
      v36 = v35;
    *(_WORD *)v36 = 0;
    if ( (unsigned int)BfspFileExists((const WCHAR *)v9) )
    {
      v10 = BfspCopyFile((STRSAFE_LPCWSTR)v9, v15);
      if ( !v10 )
        goto LABEL_36;
    }
    else
    {
      BfspLogMessage(3, L"Source Boot.stl (%s) does not exist. Will skip copying %s", v9, L"boot.stl");
    }
    v37 = 2147483646;
    v38 = 261;
    if ( v49 )
    {
      do
      {
        if ( !v37 )
          break;
        if ( !*v20 )
          break;
        *v18++ = *v20++;
        --v37;
        --v38;
      }
      while ( v38 );
    }
    else
    {
      v39 = L"boot.pnd.stl";
      do
      {
        if ( !v37 )
          break;
        if ( !*v39 )
          break;
        *v18++ = *v39++;
        --v37;
        --v38;
      }
      while ( v38 );
    }
    v40 = v38 == 0;
    v41 = v18 - 1;
    v42 = L"boot.pnd.stl";
    if ( !v40 )
      v41 = v18;
    *v41 = 0;
    do
    {
      if ( !v19 )
        break;
      if ( !*v42 )
        break;
      *(_WORD *)v17 = *v42++;
      v17 += 2;
      --v19;
      --v21;
    }
    while ( v21 );
    v43 = v17 - 2;
    if ( v21 )
      v43 = v17;
    *(_WORD *)v43 = 0;
    if ( !(unsigned int)BfspFileExists((const WCHAR *)v9) )
    {
      BfspLogMessage(3, L"Source Pending Boot.stl (%s) does not exist. Will skip copying %s", v9, L"boot.pnd.stl");
      v10 = 1;
      goto LABEL_59;
    }
    v10 = BfspCopyFile((STRSAFE_LPCWSTR)v9, v15);
    if ( v10 )
    {
LABEL_59:
      v44 = GetProcessHeap();
      HeapFree(v44, 0, v15);
      goto LABEL_60;
    }
LABEL_36:
    LastError = GetLastError();
    BfspLogMessage(4, L"Error copying %s to %s. Last Error = %#x", v9, v15, LastError);
    goto LABEL_59;
  }
  SetLastError(8u);
  return 0;
}

```

## disassembly

```asm
0x14000c8d8  push    rbx
0x14000c8da  push    rbp
0x14000c8db  push    rsi
0x14000c8dc  push    rdi
0x14000c8dd  push    r12
0x14000c8df  push    r13
0x14000c8e1  push    r14
0x14000c8e3  push    r15
0x14000c8e5  sub     rsp, 38h
0x14000c8e9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c8ed  mov     r15, rdx
0x14000c8f0  mov     rax, rdi
0x14000c8f3  xor     r14d, r14d
0x14000c8f6  mov     rbp, rcx
0x14000c8f9  inc     rax
0x14000c8fc  cmp     [rcx+rax*2], r14w
0x14000c901  jnz     short loc_14000C8F9
0x14000c903  lea     r12, [rax+106h]
0x14000c90a  lea     rbx, [r12+r12]
0x14000c90e  call    cs:__imp_GetProcessHeap
0x14000c914  mov     r13d, 8
0x14000c91a  mov     r8, rbx; dwBytes
0x14000c91d  mov     rcx, rax; hHeap
0x14000c920  mov     edx, r13d; dwFlags
0x14000c923  call    cs:__imp_HeapAlloc
0x14000c929  mov     rsi, rax
0x14000c92c  test    rax, rax
0x14000c92f  jnz     short loc_14000C942
0x14000c931  mov     ecx, r13d; dwErrCode
0x14000c934  call    cs:__imp_SetLastError
0x14000c93a  mov     ebx, r14d
0x14000c93d  jmp     loc_14000CC5F
0x14000c942  mov     rax, rdi
0x14000c945  inc     rax
0x14000c948  cmp     [r15+rax*2], r14w
0x14000c94d  jnz     short loc_14000C945
0x14000c94f  add     rax, 106h
0x14000c955  mov     [rsp+78h+arg_10], rax
0x14000c95d  lea     rbx, [rax+rax]
0x14000c961  call    cs:__imp_GetProcessHeap
0x14000c967  mov     r8, rbx; dwBytes
0x14000c96a  mov     edx, r13d; dwFlags
0x14000c96d  mov     rcx, rax; hHeap
0x14000c970  call    cs:__imp_HeapAlloc
0x14000c976  xor     ebx, ebx
0x14000c978  mov     r14, rax
0x14000c97b  test    rax, rax
0x14000c97e  jnz     short loc_14000C98E
0x14000c980  mov     ecx, r13d; dwErrCode
0x14000c983  call    cs:__imp_SetLastError
0x14000c989  jmp     loc_14000CC4B
0x14000c98e  mov     r9, rbp
0x14000c991  lea     r8, aS_1; "%s\\"
0x14000c998  mov     rdx, r12; unsigned __int64
0x14000c99b  mov     rcx, rsi; unsigned __int16 *
0x14000c99e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c9a3  mov     rax, rdi
0x14000c9a6  inc     rax
0x14000c9a9  cmp     [rsi+rax*2], bx
0x14000c9ad  jnz     short loc_14000C9A6
0x14000c9af  mov     rdx, [rsp+78h+arg_10]; unsigned __int64
0x14000c9b7  lea     r8, aS_1; "%s\\"
0x14000c9be  mov     r9, r15
0x14000c9c1  lea     r13, [rsi+rax*2]
0x14000c9c5  mov     rcx, r14; unsigned __int16 *
0x14000c9c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000c9cd  inc     rdi
0x14000c9d0  cmp     [r14+rdi*2], bx
0x14000c9d5  jnz     short loc_14000C9CD
0x14000c9d7  lea     rdi, [r14+rdi*2]
0x14000c9db  mov     r15d, 7FFFFFFEh
0x14000c9e1  lea     r12, aBootStl; "boot.stl"
0x14000c9e8  mov     ebp, 105h
0x14000c9ed  mov     ecx, r15d
0x14000c9f0  mov     r8, r12
0x14000c9f3  mov     edx, ebp
0x14000c9f5  mov     rax, rdi
0x14000c9f8  test    rcx, rcx
0x14000c9fb  jz      short loc_14000CA1C
0x14000c9fd  movzx   r9d, word ptr [r8]
0x14000ca01  test    r9w, r9w
0x14000ca05  jz      short loc_14000CA1C
0x14000ca07  mov     [rax], r9w
0x14000ca0b  add     r8, 2
0x14000ca0f  add     rax, 2
0x14000ca13  dec     rcx
0x14000ca16  sub     rdx, 1
0x14000ca1a  jnz     short loc_14000C9F8
0x14000ca1c  test    rdx, rdx
0x14000ca1f  lea     rcx, [rax-2]
0x14000ca23  cmovnz  rcx, rax
0x14000ca27  mov     [rcx], bx
0x14000ca2a  mov     rcx, r14
0x14000ca2d  call    BfspFileExists
0x14000ca32  test    eax, eax
0x14000ca34  jnz     short loc_14000CA9C
0x14000ca36  mov     rcx, r15
0x14000ca39  lea     r8, aBootPndStl; "boot.pnd.stl"
0x14000ca40  mov     rdx, rbp
0x14000ca43  mov     rax, r13
0x14000ca46  test    rcx, rcx
0x14000ca49  jz      short loc_14000CA6A
0x14000ca4b  movzx   r9d, word ptr [r8]
0x14000ca4f  test    r9w, r9w
0x14000ca53  jz      short loc_14000CA6A
0x14000ca55  mov     [rax], r9w
0x14000ca59  add     r8, 2
0x14000ca5d  add     rax, 2
0x14000ca61  dec     rcx
0x14000ca64  sub     rdx, 1
0x14000ca68  jnz     short loc_14000CA46
0x14000ca6a  test    rdx, rdx
0x14000ca6d  lea     rcx, [rax-2]
0x14000ca71  mov     r9, r14
0x14000ca74  lea     rdx, aDestinationBoo; "Destination Boot.stl does not exist. Wi"...
0x14000ca7b  cmovnz  rcx, rax
0x14000ca7f  mov     r8, rsi
0x14000ca82  mov     [rcx], bx
0x14000ca85  mov     ecx, 2
0x14000ca8a  call    BfspLogMessage
0x14000ca8f  mov     dword ptr [rsp+78h+arg_10], 1
0x14000ca9a  jmp     short loc_14000CAB4
0x14000ca9c  lea     rdx, aDestinationBoo_0; "Destination Boot.stl exists. Will copy "...
0x14000caa3  mov     ecx, 2
0x14000caa8  call    BfspLogMessage
0x14000caad  mov     dword ptr [rsp+78h+arg_10], ebx
0x14000cab4  mov     rcx, r15
0x14000cab7  mov     r8, r12
0x14000caba  mov     rdx, rbp
0x14000cabd  mov     rax, r13
0x14000cac0  test    rcx, rcx
0x14000cac3  jz      short loc_14000CAE4
0x14000cac5  movzx   r9d, word ptr [r8]
0x14000cac9  test    r9w, r9w
0x14000cacd  jz      short loc_14000CAE4
0x14000cacf  mov     [rax], r9w
0x14000cad3  add     r8, 2
0x14000cad7  add     rax, 2
0x14000cadb  dec     rcx
0x14000cade  sub     rdx, 1
0x14000cae2  jnz     short loc_14000CAC0
0x14000cae4  test    rdx, rdx
0x14000cae7  lea     rcx, [rax-2]
0x14000caeb  cmovnz  rcx, rax
0x14000caef  mov     [rcx], bx
0x14000caf2  mov     rcx, rsi
0x14000caf5  call    BfspFileExists
0x14000cafa  test    eax, eax
0x14000cafc  jz      short loc_14000CB35
0x14000cafe  mov     rdx, r14; lpFileName
0x14000cb01  mov     rcx, rsi; pszSrc
0x14000cb04  call    BfspCopyFile
0x14000cb09  mov     ebx, eax
0x14000cb0b  test    eax, eax
0x14000cb0d  jnz     short loc_14000CB4E
0x14000cb0f  call    cs:__imp_GetLastError
0x14000cb15  mov     r9, r14
0x14000cb18  lea     rdx, aErrorCopyingST; "Error copying %s to %s. Last Error = %#"...
0x14000cb1f  mov     r8, rsi
0x14000cb22  mov     [rsp+78h+var_58], eax
0x14000cb26  mov     ecx, 4
0x14000cb2b  call    BfspLogMessage
0x14000cb30  jmp     loc_14000CC37
0x14000cb35  mov     r9, r12
0x14000cb38  lea     rdx, aSourceBootStlS; "Source Boot.stl (%s) does not exist. Wi"...
0x14000cb3f  mov     r8, rsi
0x14000cb42  mov     ecx, 3
0x14000cb47  call    BfspLogMessage
0x14000cb4c  jmp     short loc_14000CB50
0x14000cb4e  xor     ebx, ebx
0x14000cb50  mov     rcx, r15
0x14000cb53  mov     rax, rbp
0x14000cb56  cmp     dword ptr [rsp+78h+arg_10], ebx
0x14000cb5d  jz      short loc_14000CB84
0x14000cb5f  test    rcx, rcx
0x14000cb62  jz      short loc_14000CBAF
0x14000cb64  movzx   edx, word ptr [r12]
0x14000cb69  test    dx, dx
0x14000cb6c  jz      short loc_14000CBAF
0x14000cb6e  mov     [rdi], dx
0x14000cb71  add     r12, 2
0x14000cb75  add     rdi, 2
0x14000cb79  dec     rcx
0x14000cb7c  sub     rax, 1
0x14000cb80  jnz     short loc_14000CB5F
0x14000cb82  jmp     short loc_14000CBAF
0x14000cb84  lea     rdx, aBootPndStl; "boot.pnd.stl"
0x14000cb8b  test    rcx, rcx
0x14000cb8e  jz      short loc_14000CBAF
0x14000cb90  movzx   r8d, word ptr [rdx]
0x14000cb94  test    r8w, r8w
0x14000cb98  jz      short loc_14000CBAF
0x14000cb9a  mov     [rdi], r8w
0x14000cb9e  add     rdx, 2
0x14000cba2  add     rdi, 2
0x14000cba6  dec     rcx
0x14000cba9  sub     rax, 1
0x14000cbad  jnz     short loc_14000CB8B
0x14000cbaf  test    rax, rax
0x14000cbb2  lea     rcx, [rdi-2]
0x14000cbb6  lea     rax, aBootPndStl; "boot.pnd.stl"
0x14000cbbd  cmovnz  rcx, rdi
0x14000cbc1  mov     [rcx], bx
0x14000cbc4  test    r15, r15
0x14000cbc7  jz      short loc_14000CBE7
0x14000cbc9  movzx   ecx, word ptr [rax]
0x14000cbcc  test    cx, cx
0x14000cbcf  jz      short loc_14000CBE7
0x14000cbd1  mov     [r13+0], cx
0x14000cbd6  add     rax, 2
0x14000cbda  add     r13, 2
0x14000cbde  dec     r15
0x14000cbe1  sub     rbp, 1
0x14000cbe5  jnz     short loc_14000CBC4
0x14000cbe7  test    rbp, rbp
0x14000cbea  lea     rcx, [r13-2]
0x14000cbee  cmovnz  rcx, r13
0x14000cbf2  mov     [rcx], bx
0x14000cbf5  mov     rcx, rsi
0x14000cbf8  call    BfspFileExists
0x14000cbfd  test    eax, eax
0x14000cbff  jz      short loc_14000CC17
0x14000cc01  mov     rdx, r14; lpFileName
0x14000cc04  mov     rcx, rsi; pszSrc
0x14000cc07  call    BfspCopyFile
0x14000cc0c  mov     ebx, eax
0x14000cc0e  test    eax, eax
0x14000cc10  jnz     short loc_14000CC37
0x14000cc12  jmp     loc_14000CB0F
0x14000cc17  lea     r9, aBootPndStl; "boot.pnd.stl"
0x14000cc1e  mov     r8, rsi
0x14000cc21  lea     rdx, aSourcePendingB; "Source Pending Boot.stl (%s) does not e"...
0x14000cc28  mov     ecx, 3
0x14000cc2d  call    BfspLogMessage
0x14000cc32  mov     ebx, 1
0x14000cc37  call    cs:__imp_GetProcessHeap
0x14000cc3d  mov     r8, r14; lpMem
0x14000cc40  xor     edx, edx; dwFlags
0x14000cc42  mov     rcx, rax; hHeap
0x14000cc45  call    cs:__imp_HeapFree
0x14000cc4b  call    cs:__imp_GetProcessHeap
0x14000cc51  mov     r8, rsi; lpMem
0x14000cc54  xor     edx, edx; dwFlags
0x14000cc56  mov     rcx, rax; hHeap
0x14000cc59  call    cs:__imp_HeapFree
0x14000cc5f  mov     eax, ebx
0x14000cc61  add     rsp, 38h
0x14000cc65  pop     r15
0x14000cc67  pop     r14
0x14000cc69  pop     r13
0x14000cc6b  pop     r12
0x14000cc6d  pop     rdi
0x14000cc6e  pop     rsi
0x14000cc6f  pop     rbp
0x14000cc70  pop     rbx
0x14000cc71  retn
```
