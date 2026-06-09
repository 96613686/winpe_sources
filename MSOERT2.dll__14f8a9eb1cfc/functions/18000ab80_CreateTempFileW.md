# CreateTempFileW

- ea: `0x18000ab80`
- end: `0x18000ade5`
- name: `CreateTempFileW`
- size: `613`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a9f0`

## callees

- `0x180001c80`
- `0x180004640`
- `0x1800095a8`
- `0x18000a038`
- `0x18000a8dc`
- `0x18000ab80`
- `0x18000b5e0`
- `0x18000ff30`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000ad3f`
- `KERNEL32!CreateFileW` at `0x18000ad3f`
- `KERNEL32!GetTempPathW` at `0x18000abd4`
- `KERNEL32!GetTempPathW` at `0x18000abd4`
- `KERNEL32!GetTempFileNameW` at `0x18000ad0d`
- `KERNEL32!GetTempFileNameW` at `0x18000ad0d`
- `SHLWAPI!PathFindExtensionW` at `0x18000ac65`
- `SHLWAPI!PathFindExtensionW` at `0x18000ac65`
- `SHLWAPI!PathFindFileNameW` at `0x18000ac59`
- `SHLWAPI!PathFindFileNameW` at `0x18000ac59`

## pseudocode

```c
__int64 __fastcall CreateTempFileW(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 **a3, _QWORD *a4)
{
  __int64 v8; // rdx
  unsigned __int16 *v9; // rdi
  int UniqueFileNameW; // ebx
  __int64 v11; // rax
  int v12; // esi
  __int64 v13; // rax
  __int64 v14; // rax
  const unsigned __int16 *FileNameW; // rbx
  LPWSTR ExtensionW; // rax
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  HANDLE FileW; // rax
  unsigned __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-490h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-478h] BYREF
  unsigned __int16 v24[264]; // [rsp+250h] [rbp-268h] BYREF

  *a4 = -1;
  if ( !AthGetTempUniquePathW((unsigned int)a1, Buffer) && GetTempPathW(0x104u, Buffer) - 1 > 0x103 )
  {
    v9 = 0;
    goto LABEL_4;
  }
  v11 = -1;
  do
    ++v11;
  while ( Buffer[v11] );
  v12 = v11 + 260;
  if ( a1 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a1[v13] );
    v12 += v13;
  }
  if ( a2 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v12 += v14;
  }
  v9 = (unsigned __int16 *)PszAllocW(v12 + 1, v8);
  if ( !v9 )
    return (unsigned int)-2147024882;
  if ( !a1 )
    goto LABEL_28;
  FileNameW = PathFindFileNameW(a1);
  ExtensionW = PathFindExtensionW(a1);
  if ( a2 )
  {
    if ( ExtensionW )
      goto LABEL_37;
LABEL_22:
    v17 = 260;
    FileNameW = a1;
    goto LABEL_23;
  }
  if ( !ExtensionW )
  {
    a2 = L".dat";
    goto LABEL_22;
  }
  a2 = ExtensionW;
LABEL_37:
  if ( !FileNameW || ExtensionW < FileNameW )
    goto LABEL_22;
  v17 = ExtensionW - FileNameW + 1;
  if ( v17 > 0x104 )
    v17 = 260;
LABEL_23:
  StringCchCopyW(v24, v17, FileNameW);
  v18 = -1;
  do
    ++v18;
  while ( Buffer[v18] );
  if ( Buffer[v18 - 1] != 92 )
    StringCchCatW(Buffer, 0x104u, L"\\");
  LODWORD(dwFlagsAndAttributes) = v12;
  UniqueFileNameW = GenerateUniqueFileNameW(Buffer, v24, a2, 0, v9, dwFlagsAndAttributes);
  if ( UniqueFileNameW < 0 )
  {
LABEL_28:
    UniqueFileNameW = 0;
    if ( !GetTempFileNameW(Buffer, L"wbk", 0, v9) )
      goto LABEL_4;
  }
  FileW = CreateFileW(v9, 0xC0000000, 4u, 0, 3u, 0x100u, 0);
  *a4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *a3 = v9;
    v9 = 0;
    goto LABEL_31;
  }
LABEL_4:
  UniqueFileNameW = HrGetLastError();
LABEL_31:
  if ( UniqueFileNameW == -2147024891 )
    UniqueFileNameW = CreateLowILTempFileW(a3, a4);
  if ( v9 )
    ((void (__fastcall *)(LPMALLOC, unsigned __int16 *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
  return (unsigned int)UniqueFileNameW;
}

```

## disassembly

```asm
0x18000ab80  push    rbx
0x18000ab82  push    rbp
0x18000ab83  push    rsi
0x18000ab84  push    rdi
0x18000ab85  push    r12
0x18000ab87  push    r13
0x18000ab89  push    r14
0x18000ab8b  push    r15
0x18000ab8d  sub     rsp, 478h
0x18000ab94  mov     rax, cs:__security_cookie
0x18000ab9b  xor     rax, rsp
0x18000ab9e  mov     [rsp+4B8h+var_58], rax
0x18000aba6  mov     r14, rdx
0x18000aba9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000abad  lea     rdx, [rsp+4B8h+Buffer]; unsigned __int16 *
0x18000abb2  mov     [r9], rbx
0x18000abb5  mov     r12, r9
0x18000abb8  mov     r15, r8
0x18000abbb  mov     rbp, rcx
0x18000abbe  call    ?AthGetTempUniquePathW@@YAKKPEAG@Z; AthGetTempUniquePathW(ulong,ushort *)
0x18000abc3  xor     r13d, r13d
0x18000abc6  test    eax, eax
0x18000abc8  jnz     short loc_18000ABF2
0x18000abca  lea     rdx, [rsp+4B8h+Buffer]; lpBuffer
0x18000abcf  mov     ecx, 104h; nBufferLength
0x18000abd4  call    cs:__imp_GetTempPathW
0x18000abda  dec     eax
0x18000abdc  cmp     eax, 103h
0x18000abe1  jbe     short loc_18000ABF2
0x18000abe3  mov     edi, r13d
0x18000abe6  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000abeb  mov     ebx, eax
0x18000abed  jmp     loc_18000AD59
0x18000abf2  lea     rcx, [rsp+4B8h+Buffer]
0x18000abf7  mov     rax, rbx
0x18000abfa  inc     rax
0x18000abfd  cmp     [rcx+rax*2], r13w
0x18000ac02  jnz     short loc_18000ABFA
0x18000ac04  lea     esi, [rax+104h]
0x18000ac0a  test    rbp, rbp
0x18000ac0d  jz      short loc_18000AC1F
0x18000ac0f  mov     rax, rbx
0x18000ac12  inc     rax
0x18000ac15  cmp     [rbp+rax*2+0], r13w
0x18000ac1b  jnz     short loc_18000AC12
0x18000ac1d  add     esi, eax
0x18000ac1f  test    r14, r14
0x18000ac22  jz      short loc_18000AC33
0x18000ac24  mov     rax, rbx
0x18000ac27  inc     rax
0x18000ac2a  cmp     [r14+rax*2], r13w
0x18000ac2f  jnz     short loc_18000AC27
0x18000ac31  add     esi, eax
0x18000ac33  lea     ecx, [rsi+1]
0x18000ac36  call    PszAllocW
0x18000ac3b  mov     rdi, rax
0x18000ac3e  test    rax, rax
0x18000ac41  jnz     short loc_18000AC4D
0x18000ac43  mov     ebx, 8007000Eh
0x18000ac48  jmp     loc_18000AD89
0x18000ac4d  test    rbp, rbp
0x18000ac50  jz      loc_18000ACF8
0x18000ac56  mov     rcx, rbp; pszPath
0x18000ac59  call    cs:__imp_PathFindFileNameW
0x18000ac5f  mov     rcx, rbp; pszPath
0x18000ac62  mov     rbx, rax
0x18000ac65  call    cs:__imp_PathFindExtensionW
0x18000ac6b  test    r14, r14
0x18000ac6e  jnz     loc_18000ADAF
0x18000ac74  test    rax, rax
0x18000ac77  jz      short loc_18000AC81
0x18000ac79  mov     r14, rax
0x18000ac7c  jmp     loc_18000ADB8
0x18000ac81  lea     r14, c_wszDotDat; ".dat"
0x18000ac88  mov     edx, 104h; unsigned __int64
0x18000ac8d  mov     rbx, rbp
0x18000ac90  mov     ebp, edx
0x18000ac92  mov     r8, rbx; unsigned __int16 *
0x18000ac95  lea     rcx, [rsp+4B8h+var_268]; unsigned __int16 *
0x18000ac9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aca2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aca6  lea     r11, [rsp+4B8h+Buffer]
0x18000acab  inc     rax
0x18000acae  cmp     [r11+rax*2], r13w
0x18000acb3  jnz     short loc_18000ACAB
0x18000acb5  cmp     [rsp+rax*2+4B8h+var_47A], 5Ch ; '\'
0x18000acbb  jz      short loc_18000ACD1
0x18000acbd  lea     r8, asc_180016C34; "\\"
0x18000acc4  mov     rdx, rbp; unsigned __int64
0x18000acc7  lea     rcx, [rsp+4B8h+Buffer]; unsigned __int16 *
0x18000accc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000acd1  mov     dword ptr [rsp+4B8h+dwFlagsAndAttributes], esi; unsigned __int64
0x18000acd5  lea     rdx, [rsp+4B8h+var_268]; unsigned __int16 *
0x18000acdd  xor     r9d, r9d; int
0x18000ace0  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rdi; unsigned __int16 *
0x18000ace5  mov     r8, r14; unsigned __int16 *
0x18000ace8  lea     rcx, [rsp+4B8h+Buffer]; unsigned __int16 *
0x18000aced  call    GenerateUniqueFileNameW
0x18000acf2  mov     ebx, eax
0x18000acf4  test    eax, eax
0x18000acf6  jns     short loc_18000AD1B
0x18000acf8  mov     r9, rdi; lpTempFileName
0x18000acfb  lea     rdx, aWbk_0; "wbk"
0x18000ad02  xor     r8d, r8d; uUnique
0x18000ad05  lea     rcx, [rsp+4B8h+Buffer]; lpPathName
0x18000ad0a  mov     ebx, r13d
0x18000ad0d  call    cs:__imp_GetTempFileNameW
0x18000ad13  test    eax, eax
0x18000ad15  jz      loc_18000ABE6
0x18000ad1b  xor     r9d, r9d; lpSecurityAttributes
0x18000ad1e  mov     [rsp+4B8h+hTemplateFile], r13; hTemplateFile
0x18000ad23  mov     dword ptr [rsp+4B8h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18000ad2b  mov     edx, 0C0000000h; dwDesiredAccess
0x18000ad30  mov     rcx, rdi; lpFileName
0x18000ad33  mov     [rsp+4B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ad3b  lea     r8d, [r9+4]; dwShareMode
0x18000ad3f  call    cs:__imp_CreateFileW
0x18000ad45  mov     [r12], rax
0x18000ad49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ad4d  jz      loc_18000ABE6
0x18000ad53  mov     [r15], rdi
0x18000ad56  mov     rdi, r13
0x18000ad59  cmp     ebx, 80070005h
0x18000ad5f  jnz     short loc_18000AD6E
0x18000ad61  mov     rdx, r12
0x18000ad64  mov     rcx, r15
0x18000ad67  call    CreateLowILTempFileW
0x18000ad6c  mov     ebx, eax
0x18000ad6e  test    rdi, rdi
0x18000ad71  jz      short loc_18000AD89
0x18000ad73  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000ad7a  mov     rdx, rdi
0x18000ad7d  mov     rax, [rcx]
0x18000ad80  mov     rax, [rax+28h]
0x18000ad84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad89  mov     eax, ebx
0x18000ad8b  mov     rcx, [rsp+4B8h+var_58]
0x18000ad93  xor     rcx, rsp; StackCookie
0x18000ad96  call    __security_check_cookie
0x18000ad9b  add     rsp, 478h
0x18000ada2  pop     r15
0x18000ada4  pop     r14
0x18000ada6  pop     r13
0x18000ada8  pop     r12
0x18000adaa  pop     rdi
0x18000adab  pop     rsi
0x18000adac  pop     rbp
0x18000adad  pop     rbx
0x18000adae  retn
0x18000adaf  test    rax, rax
0x18000adb2  jz      loc_18000AC88
0x18000adb8  test    rbx, rbx
0x18000adbb  jz      loc_18000AC88
0x18000adc1  cmp     rax, rbx
0x18000adc4  jb      loc_18000AC88
0x18000adca  sub     rax, rbx
0x18000adcd  mov     ebp, 104h
0x18000add2  sar     rax, 1
0x18000add5  lea     rdx, [rax+1]
0x18000add9  cmp     rdx, rbp
0x18000addc  cmova   rdx, rbp
0x18000ade0  jmp     loc_18000AC92
```
