# WofEnumEntries

- ea: `0x180004788`
- end: `0x1800049c9`
- name: `WofEnumEntries`
- size: `577`
- prototype: `HRESULT __stdcall(PCWSTR VolumeName, ULONG Provider, WofEnumEntryProc EnumProc, PVOID UserData)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800038dc`

## callees

- `0x1800040a8`
- `0x180004788`
- `0x180004c4c`
- `0x180004ca4`
- `0x180004fc8`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000482f`
- `KERNEL32!HeapFree` at `0x180004947`
- `KERNEL32!HeapFree` at `0x18000497d`
- `KERNEL32!HeapFree` at `0x18000482f`
- `KERNEL32!HeapFree` at `0x180004947`
- `KERNEL32!HeapFree` at `0x18000497d`
- `KERNEL32!HeapAlloc` at `0x180004846`
- `KERNEL32!HeapAlloc` at `0x180004846`
- `KERNEL32!GetProcessHeap` at `0x180004821`
- `KERNEL32!GetProcessHeap` at `0x180004838`
- `KERNEL32!GetProcessHeap` at `0x180004939`
- `KERNEL32!GetProcessHeap` at `0x18000496f`
- `KERNEL32!GetProcessHeap` at `0x180004821`
- `KERNEL32!GetProcessHeap` at `0x180004838`
- `KERNEL32!GetProcessHeap` at `0x180004939`
- `KERNEL32!GetProcessHeap` at `0x18000496f`
- `KERNEL32!GetLastError` at `0x1800047f8`
- `KERNEL32!GetLastError` at `0x1800047f8`
- `KERNEL32!CloseHandle` at `0x1800048ad`
- `KERNEL32!CloseHandle` at `0x180004993`
- `KERNEL32!CloseHandle` at `0x1800048ad`
- `KERNEL32!CloseHandle` at `0x180004993`

## pseudocode

```c
HRESULT __stdcall WofEnumEntries(PCWSTR VolumeName, ULONG Provider, WofEnumEntryProc EnumProc, PVOID UserData)
{
  void *v5; // rdi
  signed int LastError; // eax
  HRESULT v7; // ebx
  unsigned int *v8; // rsi
  HANDLE ProcessHeap; // rax
  unsigned int v10; // ebx
  HANDLE v11; // rax
  int v12; // eax
  int v13; // r15d
  unsigned int *i; // r14
  int v15; // eax
  void *v16; // r12
  BOOL v17; // eax
  int v18; // ebx
  HANDLE v19; // rax
  HANDLE v20; // rax
  SIZE_T dwBytes; // [rsp+40h] [rbp-39h] BYREF
  int v23[2]; // [rsp+48h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-29h] BYREF
  __int64 v25; // [rsp+58h] [rbp-21h]
  __int128 v26; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+70h] [rbp-9h]
  __int128 v28; // [rsp+80h] [rbp+7h]

  *(_QWORD *)v23 = 0;
  lpMem = 0;
  LODWORD(dwBytes) = 512;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( !VolumeName )
    return -2147024809;
  v5 = (void *)WofpOpenVolumeWithFlagsAndAttributes(VolumeName);
  if ( v5 == (void *)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v7;
  }
  v8 = 0;
  do
  {
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    v10 = dwBytes;
    v11 = GetProcessHeap();
    v8 = (unsigned int *)HeapAlloc(v11, 0, v10);
    if ( !v8 )
    {
      v7 = -2147024882;
      goto LABEL_26;
    }
    v23[0] = 1;
    v23[1] = 1;
    v12 = WofpDeviceIoControl((int)v5, 590623, (int)v23, 8, v8, dwBytes, (LPDWORD)&dwBytes);
    v7 = v12;
  }
  while ( v12 == -2147024662 );
  if ( v12 < 0 || !(_DWORD)dwBytes )
    goto LABEL_23;
  v13 = 0;
  CloseHandle(v5);
  v25 = -1;
  for ( i = v8; ; i = (unsigned int *)((char *)i + *i) )
  {
    v15 = WofpNormalizeFilePath((char *)i + i[8], &lpMem);
    if ( v15 < 0 )
    {
      if ( v13 >= 0 )
        v13 = v15;
      goto LABEL_19;
    }
    v16 = lpMem;
    LODWORD(v26) = 48;
    DWORD1(v26) = i[9];
    *((_QWORD *)&v26 + 1) = *((_QWORD *)i + 1);
    v27 = *((_OWORD *)i + 1);
    *((_QWORD *)&v28 + 1) = i[10];
    *(_QWORD *)&v28 = lpMem;
    v17 = (i[11] & 1) != 0;
    HIDWORD(v28) = v17;
    if ( (i[11] & 2) != 0 )
      HIDWORD(v28) = v17 | 2;
    v18 = EnumWIMCallback(&v26, UserData);
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v16);
    if ( !v18 )
      break;
LABEL_19:
    if ( !*i )
      break;
  }
  v5 = (void *)v25;
  v7 = 0;
  if ( v13 < 0 )
    v7 = v13;
LABEL_23:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v8);
  if ( v5 != (void *)-1LL )
LABEL_26:
    CloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x180004788  mov     [rsp-8+arg_8], rbx
0x18000478d  push    rbp
0x18000478e  push    rsi
0x18000478f  push    rdi
0x180004790  push    r12
0x180004792  push    r13
0x180004794  push    r14
0x180004796  push    r15
0x180004798  lea     rbp, [rsp-27h]
0x18000479d  sub     rsp, 0A0h
0x1800047a4  mov     rax, cs:__security_cookie
0x1800047ab  xor     rax, rsp
0x1800047ae  mov     [rbp+57h+var_40], rax
0x1800047b2  mov     qword ptr [rbp+57h+var_88], 0
0x1800047ba  xorps   xmm0, xmm0
0x1800047bd  mov     [rbp+57h+lpMem], 0
0x1800047c5  mov     r13, r9
0x1800047c8  mov     dword ptr [rbp+57h+dwBytes], 200h
0x1800047cf  movups  [rbp+57h+var_70], xmm0
0x1800047d3  movups  [rbp+57h+var_60], xmm0
0x1800047d7  movups  [rbp+57h+var_50], xmm0
0x1800047db  test    rcx, rcx
0x1800047de  jz      loc_18000499B
0x1800047e4  mov     r8d, 80h
0x1800047ea  call    WofpOpenVolumeWithFlagsAndAttributes
0x1800047ef  mov     rdi, rax
0x1800047f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800047f6  jnz     short loc_180004816
0x1800047f8  call    cs:__imp_GetLastError
0x1800047fe  mov     ebx, eax
0x180004800  test    eax, eax
0x180004802  jle     loc_1800049A0
0x180004808  movzx   ebx, ax
0x18000480b  or      ebx, 80070000h
0x180004811  jmp     loc_1800049A0
0x180004816  xor     esi, esi
0x180004818  lea     r14d, [rsi+1]
0x18000481c  test    rsi, rsi
0x18000481f  jz      short loc_180004835
0x180004821  call    cs:__imp_GetProcessHeap
0x180004827  mov     r8, rsi; lpMem
0x18000482a  xor     edx, edx; dwFlags
0x18000482c  mov     rcx, rax; hHeap
0x18000482f  call    cs:__imp_HeapFree
0x180004835  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x180004838  call    cs:__imp_GetProcessHeap
0x18000483e  mov     r8d, ebx; dwBytes
0x180004841  xor     edx, edx; dwFlags
0x180004843  mov     rcx, rax; hHeap
0x180004846  call    cs:__imp_HeapAlloc
0x18000484c  mov     rsi, rax
0x18000484f  test    rax, rax
0x180004852  jz      loc_18000498B
0x180004858  lea     rax, [rbp+57h+dwBytes]
0x18000485c  mov     [rbp+57h+var_88], r14d
0x180004860  mov     [rsp+0D0h+var_A0], rax; LPDWORD
0x180004865  lea     r8, [rbp+57h+var_88]; int
0x180004869  mov     eax, dword ptr [rbp+57h+dwBytes]
0x18000486c  mov     r9d, 8; int
0x180004872  mov     [rsp+0D0h+var_A8], eax; DWORD
0x180004876  mov     edx, 9031Fh; int
0x18000487b  mov     rcx, rdi; int
0x18000487e  mov     [rsp+0D0h+var_B0], rsi; LPVOID
0x180004883  mov     [rbp+57h+var_88+4], r14d
0x180004887  call    WofpDeviceIoControl
0x18000488c  mov     ebx, eax
0x18000488e  cmp     eax, 800700EAh
0x180004893  jz      short loc_18000481C
0x180004895  test    eax, eax
0x180004897  js      loc_18000496F
0x18000489d  cmp     dword ptr [rbp+57h+dwBytes], 0
0x1800048a1  jz      loc_18000496F
0x1800048a7  xor     r15d, r15d
0x1800048aa  mov     rcx, rdi; hObject
0x1800048ad  call    cs:__imp_CloseHandle
0x1800048b3  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFFh
0x1800048bb  lea     edi, [r15+1]
0x1800048bf  mov     r14, rsi
0x1800048c2  mov     ecx, [r14+20h]
0x1800048c6  lea     rdx, [rbp+57h+lpMem]
0x1800048ca  add     rcx, r14
0x1800048cd  call    WofpNormalizeFilePath
0x1800048d2  test    eax, eax
0x1800048d4  jns     short loc_1800048E0
0x1800048d6  test    r15d, r15d
0x1800048d9  js      short loc_180004951
0x1800048db  mov     r15d, eax
0x1800048de  jmp     short loc_180004951
0x1800048e0  mov     r12, [rbp+57h+lpMem]
0x1800048e4  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x1800048eb  mov     eax, [r14+24h]
0x1800048ef  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800048f2  mov     rax, [r14+8]
0x1800048f6  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800048fa  movups  xmm0, xmmword ptr [r14+10h]
0x1800048ff  movdqu  [rbp+57h+var_60], xmm0
0x180004904  mov     eax, [r14+28h]
0x180004908  mov     dword ptr [rbp+57h+var_50+8], eax
0x18000490b  xor     eax, eax
0x18000490d  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x180004910  mov     qword ptr [rbp+57h+var_50], r12
0x180004914  test    [r14+2Ch], dil
0x180004918  cmovnz  eax, edi
0x18000491b  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x18000491e  test    byte ptr [r14+2Ch], 2
0x180004923  jz      short loc_18000492B
0x180004925  or      eax, 2
0x180004928  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x18000492b  mov     rdx, r13
0x18000492e  lea     rcx, [rbp+57h+var_70]
0x180004932  call    EnumWIMCallback
0x180004937  mov     ebx, eax
0x180004939  call    cs:__imp_GetProcessHeap
0x18000493f  mov     r8, r12; lpMem
0x180004942  xor     edx, edx; dwFlags
0x180004944  mov     rcx, rax; hHeap
0x180004947  call    cs:__imp_HeapFree
0x18000494d  test    ebx, ebx
0x18000494f  jz      short loc_180004962
0x180004951  cmp     dword ptr [r14], 0
0x180004955  jz      short loc_180004962
0x180004957  mov     eax, [r14]
0x18000495a  add     r14, rax
0x18000495d  jmp     loc_1800048C2
0x180004962  mov     rdi, [rbp+57h+var_78]
0x180004966  xor     ebx, ebx
0x180004968  test    r15d, r15d
0x18000496b  cmovs   ebx, r15d
0x18000496f  call    cs:__imp_GetProcessHeap
0x180004975  mov     r8, rsi; lpMem
0x180004978  xor     edx, edx; dwFlags
0x18000497a  mov     rcx, rax; hHeap
0x18000497d  call    cs:__imp_HeapFree
0x180004983  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180004987  jz      short loc_1800049A0
0x180004989  jmp     short loc_180004990
0x18000498b  mov     ebx, 8007000Eh
0x180004990  mov     rcx, rdi; hObject
0x180004993  call    cs:__imp_CloseHandle
0x180004999  jmp     short loc_1800049A0
0x18000499b  mov     ebx, 80070057h
0x1800049a0  mov     eax, ebx
0x1800049a2  mov     rcx, [rbp+57h+var_40]
0x1800049a6  xor     rcx, rsp; StackCookie
0x1800049a9  call    __security_check_cookie
0x1800049ae  mov     rbx, [rsp+0D0h+arg_8]
0x1800049b6  add     rsp, 0A0h
0x1800049bd  pop     r15
0x1800049bf  pop     r14
0x1800049c1  pop     r13
0x1800049c3  pop     r12
0x1800049c5  pop     rdi
0x1800049c6  pop     rsi
0x1800049c7  pop     rbp
0x1800049c8  retn
```
