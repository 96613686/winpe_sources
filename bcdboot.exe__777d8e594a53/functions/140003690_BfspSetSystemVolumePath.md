# BfspSetSystemVolumePath

- ea: `0x140003690`
- end: `0x14000387c`
- name: `BfspSetSystemVolumePath`
- size: `492`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140001bc8`

## callees

- `0x140001738`
- `0x140003690`
- `0x1400265e2`
- `0x140026650`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x14000371a`
- `msvcrt!wcscpy_s` at `0x140003791`
- `msvcrt!wcscpy_s` at `0x14000371a`
- `msvcrt!wcscpy_s` at `0x140003791`
- `KERNEL32!HeapAlloc` at `0x14000381d`
- `KERNEL32!HeapAlloc` at `0x14000381d`
- `KERNEL32!GetProcessHeap` at `0x14000380c`
- `KERNEL32!GetProcessHeap` at `0x14000380c`
- `KERNEL32!QueryDosDeviceW` at `0x140003730`
- `KERNEL32!QueryDosDeviceW` at `0x140003730`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140003776`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140003776`
- `KERNEL32!GetVolumePathNameW` at `0x140003750`
- `KERNEL32!GetVolumePathNameW` at `0x140003750`

## pseudocode

```c
__int64 __fastcall BfspSetSystemVolumePath(LPCWSTR lpszFileName)
{
  unsigned int v2; // ebx
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rax
  SIZE_T v5; // rsi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  HANDLE ProcessHeap; // rax
  void *v11; // rax
  __int16 v13; // [rsp+2Eh] [rbp-D2h]
  wchar_t Destination; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v15; // [rsp+32h] [rbp-CEh]
  WCHAR szVolumeName[56]; // [rsp+240h] [rbp+140h] BYREF

  if ( !lpszFileName )
  {
    v2 = 0;
    BfspSystemPartitionName = 0;
    return v2;
  }
  if ( *lpszFileName == 92 )
  {
    v3 = -1;
    do
      ++v3;
    while ( lpszFileName[v3] );
    v4 = 2 * v3;
    if ( is_mul_ok(v3, 2u) )
    {
      v5 = v4 + 2;
      if ( v4 + 2 >= v4 )
      {
        v2 = 0;
        wcscpy_s(&Destination, 0x104u, lpszFileName);
        goto LABEL_25;
      }
    }
    return (unsigned int)-1073741675;
  }
  v6 = -1;
  if ( !QueryDosDeviceW(lpszFileName, &Destination, 0x104u) )
  {
    if ( !GetVolumePathNameW(lpszFileName, &Destination, 0x104u)
      || !GetVolumeNameForVolumeMountPointW(&Destination, szVolumeName, 0x32u) )
    {
      return (unsigned int)-1073741811;
    }
    wcscpy_s(&Destination, 0x104u, szVolumeName);
    v7 = -1;
    do
      ++v7;
    while ( *(&Destination + v7) );
    if ( v7 > 1 )
    {
      if ( v15 == 92 )
        v15 = 63;
      if ( *(&v13 + v7) == 92 )
      {
        v8 = 2 * v7 - 2;
        if ( v8 >= 0x208 )
          _report_rangecheckfailure();
        *(wchar_t *)((char *)&Destination + v8) = 0;
      }
    }
  }
  do
    ++v6;
  while ( *(&Destination + v6) );
  v9 = 2 * v6;
  if ( !is_mul_ok(v6, 2u) )
    return (unsigned int)-1073741675;
  v5 = v9 + 2;
  if ( v9 + 2 < v9 )
    return (unsigned int)-1073741675;
  v2 = 0;
LABEL_25:
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v5);
  BfspSystemPartitionName = v11;
  if ( v11 )
    memcpy_0(v11, &Destination, v5);
  else
    return (unsigned int)-1073741801;
  return v2;
}

```

## disassembly

```asm
0x140003690  mov     [rsp-8+arg_8], rbx
0x140003695  mov     [rsp-8+arg_10], rsi
0x14000369a  push    rbp
0x14000369b  push    rdi
0x14000369c  push    r15
0x14000369e  lea     rbp, [rsp-1C0h]
0x1400036a6  sub     rsp, 2C0h
0x1400036ad  mov     rax, cs:__security_cookie
0x1400036b4  xor     rax, rsp
0x1400036b7  mov     [rbp+1D0h+var_20], rax
0x1400036be  xor     r15d, r15d
0x1400036c1  mov     rdi, rcx
0x1400036c4  test    rcx, rcx
0x1400036c7  jnz     short loc_1400036D8
0x1400036c9  mov     ebx, r15d
0x1400036cc  mov     cs:BfspSystemPartitionName, r15
0x1400036d3  jmp     loc_14000384D
0x1400036d8  cmp     word ptr [rcx], 5Ch ; '\'
0x1400036dc  jnz     short loc_140003725
0x1400036de  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400036e2  inc     rbx
0x1400036e5  cmp     [rcx+rbx*2], r15w
0x1400036ea  jnz     short loc_1400036E2
0x1400036ec  mov     eax, 2
0x1400036f1  mul     rbx
0x1400036f4  test    rdx, rdx
0x1400036f7  jnz     loc_140003848
0x1400036fd  lea     rsi, [rax+2]
0x140003701  cmp     rsi, rax
0x140003704  jb      loc_140003848
0x14000370a  mov     r8, rdi; Source
0x14000370d  lea     rcx, [rsp+2D0h+Destination]; Destination
0x140003712  mov     edx, 104h; SizeInWords
0x140003717  mov     ebx, r15d
0x14000371a  call    cs:__imp_wcscpy_s
0x140003720  jmp     loc_14000380C
0x140003725  mov     r8d, 104h; ucchMax
0x14000372b  lea     rdx, [rsp+2D0h+Destination]; lpTargetPath
0x140003730  call    cs:__imp_QueryDosDeviceW
0x140003736  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000373a  test    eax, eax
0x14000373c  jnz     loc_1400037E4
0x140003742  mov     r8d, 104h; cchBufferLength
0x140003748  lea     rdx, [rsp+2D0h+Destination]; lpszVolumePathName
0x14000374d  mov     rcx, rdi; lpszFileName
0x140003750  call    cs:__imp_GetVolumePathNameW
0x140003756  test    eax, eax
0x140003758  jnz     short loc_140003764
0x14000375a  mov     ebx, 0C000000Dh
0x14000375f  jmp     loc_14000384D
0x140003764  mov     r8d, 32h ; '2'; cchBufferLength
0x14000376a  lea     rdx, [rbp+1D0h+szVolumeName]; lpszVolumeName
0x140003771  lea     rcx, [rsp+2D0h+Destination]; lpszVolumeMountPoint
0x140003776  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14000377c  test    eax, eax
0x14000377e  jz      short loc_14000375A
0x140003780  lea     r8, [rbp+1D0h+szVolumeName]; Source
0x140003787  mov     edx, 104h; SizeInWords
0x14000378c  lea     rcx, [rsp+2D0h+Destination]; Destination
0x140003791  call    cs:__imp_wcscpy_s
0x140003797  lea     rcx, [rsp+2D0h+Destination]
0x14000379c  mov     rax, rbx
0x14000379f  inc     rax
0x1400037a2  cmp     [rcx+rax*2], r15w
0x1400037a7  jnz     short loc_14000379F
0x1400037a9  cmp     rax, 1
0x1400037ad  jbe     short loc_1400037E4
0x1400037af  cmp     [rsp+2D0h+var_29E], 5Ch ; '\'
0x1400037b5  jnz     short loc_1400037C1
0x1400037b7  mov     ecx, 3Fh ; '?'
0x1400037bc  mov     [rsp+2D0h+var_29E], cx
0x1400037c1  cmp     [rsp+rax*2+2D0h+var_2A2], 5Ch ; '\'
0x1400037c7  jnz     short loc_1400037E4
0x1400037c9  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1400037d1  cmp     rcx, 208h
0x1400037d8  jnb     loc_140003876
0x1400037de  mov     [rsp+rcx+2D0h+Destination], r15w
0x1400037e4  lea     rax, [rsp+2D0h+Destination]
0x1400037e9  inc     rbx
0x1400037ec  cmp     [rax+rbx*2], r15w
0x1400037f1  jnz     short loc_1400037E9
0x1400037f3  mov     eax, 2
0x1400037f8  mul     rbx
0x1400037fb  test    rdx, rdx
0x1400037fe  jnz     short loc_140003848
0x140003800  lea     rsi, [rax+2]
0x140003804  cmp     rsi, rax
0x140003807  jb      short loc_140003848
0x140003809  mov     ebx, r15d
0x14000380c  call    cs:__imp_GetProcessHeap
0x140003812  mov     r8, rsi; dwBytes
0x140003815  mov     edx, 8; dwFlags
0x14000381a  mov     rcx, rax; hHeap
0x14000381d  call    cs:__imp_HeapAlloc
0x140003823  mov     cs:BfspSystemPartitionName, rax
0x14000382a  test    rax, rax
0x14000382d  jnz     short loc_140003836
0x14000382f  mov     ebx, 0C0000017h
0x140003834  jmp     short loc_14000384D
0x140003836  mov     r8, rsi; Size
0x140003839  lea     rdx, [rsp+2D0h+Destination]; Src
0x14000383e  mov     rcx, rax; void *
0x140003841  call    memcpy_0
0x140003846  jmp     short loc_14000384D
0x140003848  mov     ebx, 0C0000095h
0x14000384d  mov     eax, ebx
0x14000384f  mov     rcx, [rbp+1D0h+var_20]
0x140003856  xor     rcx, rsp; StackCookie
0x140003859  call    __security_check_cookie
0x14000385e  lea     r11, [rsp+2D0h+var_10]
0x140003866  mov     rbx, [r11+28h]
0x14000386a  mov     rsi, [r11+30h]
0x14000386e  mov     rsp, r11
0x140003871  pop     r15
0x140003873  pop     rdi
0x140003874  pop     rbp
0x140003875  retn
0x140003876  call    __report_rangecheckfailure
```
