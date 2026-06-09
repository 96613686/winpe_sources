# SusMakeDirectoryW(wchar_t const *,ulong,void *)

- ea: `0x14000ec6c`
- end: `0x14000ee60`
- name: `?SusMakeDirectoryW@@YAJPEB_WKPEAX@Z`
- size: `500`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000ee68`

## callees

- `0x140008de4`
- `0x14000e4f4`
- `0x14000ec6c`
- `0x140011dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed51`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000ee02`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000ee02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000ed46`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000ed46`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x14000edcf`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x14000edcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SusMakeDirectoryW(PCNZWCH lpString1, int a2, void *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  PCNZWCH v10; // rax
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // ebp
  unsigned int v16; // esi
  int v17; // eax
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !lpString1 )
  {
    v5 = -2147024809;
    v6 = 758;
    goto LABEL_3;
  }
  v8 = 0;
  v9 = 0x7FFFFFFF;
  v10 = lpString1;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
  {
    if ( ((0x7FFFFFFF - v9) & (unsigned __int64)-(__int64)(v9 != 0)) > 4
      && *lpString1 == 92
      && lpString1[1] == 92
      && lpString1[2] == 63
      && lpString1[3] == 92 )
    {
      v8 = 4;
    }
    if ( (unsigned int)HasLocalShortPathPrefix(&lpString1[v8]) )
      goto LABEL_18;
  }
  if ( VolumeUtil::HasVolumeIdPathPrefix(lpString1, (const wchar_t *)v8) )
  {
LABEL_18:
    FileAttributesW = GetFileAttributesW(lpString1);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v13 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v13 = (unsigned int)LastError;
      if ( (int)v13 < 0 )
      {
        if ( (_DWORD)v13 == -2147024894 || (_DWORD)v13 == -2147024893 )
          goto LABEL_29;
      }
      else
      {
        v13 = 2147549183LL;
      }
      v14 = 372;
    }
    else
    {
      if ( (FileAttributesW & 0x10) != 0 )
        return 0;
      v13 = 2147942667LL;
      v14 = 375;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
      (const char *)v13,
      v19);
LABEL_29:
    v15 = a2 + 1;
    v5 = 0;
    v16 = 0;
    if ( !a2 )
      v15 = 1;
    while ( v16 < v15 )
    {
      v17 = SHCreateDirectoryExW(0, lpString1, 0);
      if ( !v17 )
        return 0;
      if ( v17 != 5 && v17 != 32 )
      {
        if ( v17 == 80 || v17 == 183 )
          return 0;
        v5 = (unsigned __int16)v17 | 0x80070000;
        if ( v17 <= 0 )
          v5 = v17;
        break;
      }
      v5 = (unsigned __int16)v17 | 0x80070000;
      if ( a2-- )
        Sleep(0x1F4u);
      ++v16;
    }
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    v6 = 826;
    goto LABEL_3;
  }
  v5 = -2147024735;
  v6 = 766;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v5,
    v19);
  return v5;
}

```

## disassembly

```asm
0x14000ec6c  mov     rax, rsp
0x14000ec6f  mov     [rax+8], rbx
0x14000ec73  mov     [rax+10h], rbp
0x14000ec77  mov     [rax+18h], rsi
0x14000ec7b  mov     [rax+20h], rdi
0x14000ec7f  push    r12
0x14000ec81  push    r14
0x14000ec83  push    r15; int
0x14000ec85  sub     rsp, 20h
0x14000ec89  xor     r15d, r15d
0x14000ec8c  mov     r14d, edx
0x14000ec8f  mov     rdi, rcx
0x14000ec92  test    rcx, rcx
0x14000ec95  jnz     short loc_14000ECBC
0x14000ec97  mov     ebx, 80070057h
0x14000ec9c  mov     edx, 2F6h; void *
0x14000eca1  mov     rcx, [rsp+38h]; this
0x14000eca6  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000ecad  mov     r9d, ebx; char *
0x14000ecb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ecb5  mov     eax, ebx
0x14000ecb7  jmp     loc_14000EE41
0x14000ecbc  mov     r8d, 7FFFFFFFh
0x14000ecc2  mov     rdx, r15
0x14000ecc5  mov     ecx, r8d
0x14000ecc8  mov     rax, rdi
0x14000eccb  mov     r12d, 1
0x14000ecd1  cmp     [rax], r15w
0x14000ecd5  jz      short loc_14000ECE0
0x14000ecd7  add     rax, 2
0x14000ecdb  sub     rcx, r12
0x14000ecde  jnz     short loc_14000ECD1
0x14000ece0  sub     r8, rcx
0x14000ece3  mov     rax, rcx
0x14000ece6  neg     rax
0x14000ece9  sbb     r9, r9
0x14000ecec  and     r9, r8
0x14000ecef  test    rcx, rcx
0x14000ecf2  jz      short loc_14000ED28
0x14000ecf4  mov     eax, 4
0x14000ecf9  cmp     r9, rax
0x14000ecfc  jbe     short loc_14000ED1B
0x14000ecfe  cmp     word ptr [rdi], 5Ch ; '\'
0x14000ed02  jnz     short loc_14000ED1B
0x14000ed04  cmp     word ptr [rdi+2], 5Ch ; '\'
0x14000ed09  jnz     short loc_14000ED1B
0x14000ed0b  cmp     word ptr [rdi+4], 3Fh ; '?'
0x14000ed10  jnz     short loc_14000ED1B
0x14000ed12  cmp     word ptr [rdi+6], 5Ch ; '\'
0x14000ed17  cmovz   rdx, rax
0x14000ed1b  lea     rcx, [rdi+rdx*2]; wchar_t *
0x14000ed1f  call    ?HasLocalShortPathPrefix@@YAHPEB_W@Z; HasLocalShortPathPrefix(wchar_t const *)
0x14000ed24  test    eax, eax
0x14000ed26  jnz     short loc_14000ED43
0x14000ed28  mov     rcx, rdi; lpString1
0x14000ed2b  call    ?HasVolumeIdPathPrefix@VolumeUtil@@YA_NPEB_W@Z; VolumeUtil::HasVolumeIdPathPrefix(wchar_t const *)
0x14000ed30  test    al, al
0x14000ed32  jnz     short loc_14000ED43
0x14000ed34  mov     ebx, 800700A1h
0x14000ed39  mov     edx, 2FEh
0x14000ed3e  jmp     loc_14000ECA1
0x14000ed43  mov     rcx, rdi; lpFileName
0x14000ed46  call    cs:__imp_GetFileAttributesW
0x14000ed4c  cmp     eax, 0FFFFFFFFh
0x14000ed4f  jnz     short loc_14000ED8E
0x14000ed51  call    cs:__imp_GetLastError
0x14000ed57  movzx   r9d, ax
0x14000ed5b  or      r9d, 80070000h
0x14000ed62  test    eax, eax
0x14000ed64  cmovle  r9d, eax
0x14000ed68  test    r9d, r9d
0x14000ed6b  js      short loc_14000ED75
0x14000ed6d  mov     r9d, 8000FFFFh
0x14000ed73  jmp     short loc_14000ED87
0x14000ed75  cmp     r9d, 80070002h
0x14000ed7c  jz      short loc_14000EDB2
0x14000ed7e  cmp     r9d, 80070003h
0x14000ed85  jz      short loc_14000EDB2
0x14000ed87  mov     edx, 174h
0x14000ed8c  jmp     short loc_14000EDA1
0x14000ed8e  test    al, 10h
0x14000ed90  jnz     loc_14000EE3F
0x14000ed96  mov     r9d, 8007010Bh; char *
0x14000ed9c  mov     edx, 177h; void *
0x14000eda1  mov     rcx, [rsp+38h]; this
0x14000eda6  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000edad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000edb2  test    r14d, r14d
0x14000edb5  lea     ebp, [r14+1]
0x14000edb9  mov     ebx, r15d
0x14000edbc  mov     esi, r15d
0x14000edbf  cmovz   ebp, r12d
0x14000edc3  cmp     esi, ebp
0x14000edc5  jnb     short loc_14000EE25
0x14000edc7  xor     r8d, r8d; psa
0x14000edca  mov     rdx, rdi; pszPath
0x14000edcd  xor     ecx, ecx; hwnd
0x14000edcf  call    cs:__imp_SHCreateDirectoryExW
0x14000edd5  mov     edx, eax
0x14000edd7  test    eax, eax
0x14000edd9  jz      short loc_14000EE37
0x14000eddb  sub     edx, 5
0x14000edde  jz      short loc_14000EDE5
0x14000ede0  sub     edx, 1Bh
0x14000ede3  jnz     short loc_14000EE0D
0x14000ede5  movzx   ebx, ax
0x14000ede8  or      ebx, 80070000h
0x14000edee  test    eax, eax
0x14000edf0  cmovle  ebx, eax
0x14000edf3  mov     eax, r14d
0x14000edf6  dec     r14d
0x14000edf9  test    eax, eax
0x14000edfb  jz      short loc_14000EE08
0x14000edfd  mov     ecx, 1F4h; dwMilliseconds
0x14000ee02  call    cs:__imp_Sleep
0x14000ee08  add     esi, r12d
0x14000ee0b  jmp     short loc_14000EDC3
0x14000ee0d  sub     edx, 30h ; '0'
0x14000ee10  jz      short loc_14000EE37
0x14000ee12  cmp     edx, 67h ; 'g'
0x14000ee15  jz      short loc_14000EE37
0x14000ee17  movzx   ebx, ax
0x14000ee1a  or      ebx, 80070000h
0x14000ee20  test    eax, eax
0x14000ee22  cmovle  ebx, eax
0x14000ee25  test    ebx, ebx
0x14000ee27  jns     loc_14000ECB5
0x14000ee2d  mov     edx, 33Ah
0x14000ee32  jmp     loc_14000ECA1
0x14000ee37  mov     ebx, r15d
0x14000ee3a  jmp     loc_14000ECB5
0x14000ee3f  xor     eax, eax
0x14000ee41  mov     rbx, [rsp+38h+arg_0]
0x14000ee46  mov     rbp, [rsp+38h+arg_8]
0x14000ee4b  mov     rsi, [rsp+38h+arg_10]
0x14000ee50  mov     rdi, [rsp+38h+arg_18]
0x14000ee55  add     rsp, 20h
0x14000ee59  pop     r15
0x14000ee5b  pop     r14
0x14000ee5d  pop     r12
0x14000ee5f  retn
```
