# CfUpdatePlaceholder

- ea: `0x18000e610`
- end: `0x18000ea29`
- name: `CfUpdatePlaceholder`
- size: `1049`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180010c9c`

## callees

- `0x1800022ee`
- `0x180004628`
- `0x180004a10`
- `0x180004a68`
- `0x18000e610`
- `0x180011e18`
- `0x18001bb5c`
- `0x18001be5c`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e66a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e66a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea0d`

## string_xrefs

- `0x18000e71b`: `Remove FileIdentity AND Non Null FileIdentity Not allowed`
- `0x18000e688`: `Failed IsDirectory check`

## pseudocode

```c
__int64 __fastcall CfUpdatePlaceholder(
        unsigned __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        void *Src,
        unsigned int a6,
        int a7,
        _QWORD *a8,
        struct _OVERLAPPED *a9)
{
  _DWORD *v9; // rsi
  char v12; // r12
  __int64 v13; // rdx
  int IsDirectory; // ebx
  const wchar_t *v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // edx
  int v18; // edi
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // ebx
  HANDLE ProcessHeap; // rax
  int v23; // r8d
  char *v24; // r9
  size_t v25; // rbx
  HANDLE v26; // rax
  DWORD NumberOfBytesTransferred[2]; // [rsp+48h] [rbp-91h] BYREF
  __int64 v29; // [rsp+50h] [rbp-89h]
  __int64 v30; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+60h] [rbp-79h] BYREF
  size_t Size; // [rsp+68h] [rbp-71h]
  int v33; // [rsp+78h] [rbp-61h] BYREF
  const wchar_t *v34; // [rsp+80h] [rbp-59h]
  int v35; // [rsp+88h] [rbp-51h]
  char v36; // [rsp+8Ch] [rbp-4Dh]
  char v37; // [rsp+8Dh] [rbp-4Ch]
  char v38; // [rsp+8Eh] [rbp-4Bh]

  v9 = 0;
  NumberOfBytesTransferred[1] = 0;
  UnbiasedTime = 0;
  v30 = 0;
  LOBYTE(NumberOfBytesTransferred[0]) = 0;
  v12 = 0;
  memset_0(&v33, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  IsDirectory = CfpIsDirectory(a1, NumberOfBytesTransferred);
  if ( IsDirectory <= -1 )
  {
    v15 = L"Failed IsDirectory check";
    goto LABEL_75;
  }
  LOBYTE(v13) = LOBYTE(NumberOfBytesTransferred[0]) == 0;
  if ( !(unsigned __int8)CfpReferenceProtectedHandle(a1, v13) )
  {
    IsDirectory = -2147024890;
    v15 = L"Invalid Handle";
    goto LABEL_75;
  }
  v12 = 1;
  if ( (a7 & 8) != 0 && (a7 & 0x10) != 0 )
    IsDirectory = 87;
  else
    IsDirectory = 0;
  if ( IsDirectory )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"Enable/Disable OnDemand Population Can't be ";
    goto LABEL_75;
  }
  if ( a3 && (a7 & 0x20) != 0 )
    IsDirectory = 87;
  else
    IsDirectory = 0;
  if ( IsDirectory )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"Remove FileIdentity AND Non Null FileIdentity Not allowed";
    goto LABEL_75;
  }
  IsDirectory = 87;
  if ( (a7 & 0x42) != 0x42 )
    IsDirectory = 0;
  if ( IsDirectory )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"Mark and Clear In Sync together not allowed";
    goto LABEL_75;
  }
  v16 = 0;
  v17 = a4 + 76;
  v18 = 4;
  Size = 16LL * a6;
  if ( (a7 & 4) == 0 )
    v16 = 16LL * a6;
  v19 = 152;
  v29 = 152;
  if ( (unsigned __int64)(a4 + 76) + v16 >= 0x98 )
  {
    v20 = 16 * a6;
    if ( (a7 & 4) != 0 )
      v20 = 0;
    v19 = v20 + v17;
    v29 = v20 + v17;
  }
  v21 = v19;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, v21);
  IsDirectory = v9 == 0 ? 8 : 0;
  if ( !v9 )
    IsDirectory |= 0x80070000;
  if ( IsDirectory <= -1 )
  {
    v15 = L"hsmOp Memory Allocation failed";
    goto LABEL_75;
  }
  v9[1] = -1073741821;
  v23 = 76;
  *v9 = -1879048166;
  v24 = (char *)(v9 + 19);
  v9[2] = 4;
  if ( (a7 & 8) != 0 )
  {
    v18 = 36;
  }
  else
  {
    if ( (a7 & 0x10) == 0 )
      goto LABEL_42;
    v18 = 68;
  }
  v9[2] = v18;
LABEL_42:
  if ( (a7 & 1) != 0 )
  {
    v18 |= 8u;
LABEL_46:
    v9[2] = v18;
    goto LABEL_47;
  }
  if ( (a7 & 2) != 0 )
  {
    v18 |= 1u;
    goto LABEL_46;
  }
LABEL_47:
  if ( (a7 & 0x40) != 0 )
  {
    v18 |= 0x100u;
    v9[2] = v18;
  }
  if ( (a7 & 0x20) != 0 )
  {
    v18 |= 0x80u;
    v9[2] = v18;
  }
  if ( (a7 & 0x80u) != 0 )
  {
    v18 |= 0x2000u;
    v9[2] = v18;
  }
  if ( (a7 & 0x100) != 0 )
  {
    v18 |= 0x10000u;
    v9[2] = v18;
  }
  if ( (a7 & 0x200) != 0 )
  {
    v18 |= 0x400u;
    v9[2] = v18;
  }
  if ( (a7 & 0x400) != 0 )
  {
    v18 |= 0x800000u;
    v9[2] = v18;
  }
  if ( (a7 & 4) != 0 )
  {
    v9[2] = v18 | 2;
  }
  else if ( Src && a6 )
  {
    v25 = Size;
    v9[17] = 76;
    v9[18] = (unsigned __int16)(16 * a6);
    memcpy_0(v9 + 19, Src, v25);
    v24 = (char *)v9 + v25 + 76;
    v23 = 16 * a6 + 76;
  }
  if ( a2 )
  {
    v9[14] = *(_DWORD *)(a2 + 32);
    *((_QWORD *)v9 + 3) = *(_QWORD *)(a2 + 40);
    *((_QWORD *)v9 + 4) = *(_QWORD *)a2;
    *((_QWORD *)v9 + 5) = *(_QWORD *)(a2 + 16);
    *((_QWORD *)v9 + 6) = *(_QWORD *)(a2 + 8);
    v36 = 1;
  }
  else
  {
    v9[2] |= 0x20000u;
  }
  if ( a8 )
  {
    *((_QWORD *)v9 + 2) = *a8;
    v37 = 1;
  }
  if ( a3 )
  {
    v9[15] = v23;
    v9[16] = a4;
    memcpy_0(v24, a3, a4);
    v38 = 1;
  }
  IsDirectory = IssueHsmControl(
                  a1,
                  v9,
                  v29,
                  (void *)((unsigned __int64)&v30 & -(__int64)(a8 != 0)),
                  a8 != 0 ? 8 : 0,
                  &NumberOfBytesTransferred[1],
                  a9);
  if ( IsDirectory > -1 )
  {
    v15 = 0;
    if ( a8 )
      *a8 = v30;
  }
  else
  {
    v15 = L"IssueHsmControl Failed";
  }
LABEL_75:
  v35 = a7;
  v34 = v15;
  TlmLogApiReliability(0x11u, a1, 0, 0, 0, UnbiasedTime, &v33, IsDirectory);
  if ( v12 )
    CfpReleaseProtectedHandle(a1);
  if ( v9 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v9);
  }
  return (unsigned int)IsDirectory;
}

```

## disassembly

```asm
0x18000e610  mov     rax, rsp
0x18000e613  mov     [rax+20h], r9d
0x18000e617  mov     [rax+18h], r8
0x18000e61b  mov     [rax+10h], rdx
0x18000e61f  mov     [rax+8], rcx
0x18000e623  push    rbp
0x18000e624  push    rbx
0x18000e625  push    rsi
0x18000e626  push    rdi
0x18000e627  push    r12
0x18000e629  push    r13
0x18000e62b  push    r14
0x18000e62d  push    r15
0x18000e62f  lea     rbp, [rax-47h]
0x18000e633  sub     rsp, 0D8h
0x18000e63a  xor     esi, esi
0x18000e63c  mov     rdi, r8
0x18000e63f  mov     rbx, rcx
0x18000e642  mov     [rsp+110h+NumberOfBytesTransferred+4], esi
0x18000e646  xor     edx, edx; Val
0x18000e648  mov     [rbp+3Fh+UnbiasedTime], rsi
0x18000e64c  lea     rcx, [rbp+3Fh+var_A0]; void *
0x18000e650  mov     [rsp+110h+var_C0], rsi
0x18000e655  lea     r8d, [rsi+58h]; Size
0x18000e659  mov     byte ptr [rsp+110h+NumberOfBytesTransferred], sil
0x18000e65e  xor     r12b, r12b
0x18000e661  call    memset_0
0x18000e666  lea     rcx, [rbp+3Fh+UnbiasedTime]; UnbiasedTime
0x18000e66a  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000e670  lea     rdx, [rsp+110h+NumberOfBytesTransferred]
0x18000e675  mov     rcx, rbx
0x18000e678  call    CfpIsDirectory
0x18000e67d  mov     r14d, [rbp+3Fh+arg_30]
0x18000e681  mov     ebx, eax
0x18000e683  cmp     eax, 0FFFFFFFFh
0x18000e686  jg      short loc_18000E694
0x18000e688  lea     rcx, aFailedIsdirect; "Failed IsDirectory check"
0x18000e68f  jmp     loc_18000E9AF
0x18000e694  cmp     byte ptr [rsp+110h+NumberOfBytesTransferred], sil
0x18000e699  mov     rcx, [rbp+3Fh+hFile]
0x18000e69d  setz    dl
0x18000e6a0  call    CfpReferenceProtectedHandle
0x18000e6a5  test    al, al
0x18000e6a7  jnz     short loc_18000E6BA
0x18000e6a9  mov     ebx, 80070006h
0x18000e6ae  lea     rcx, aInvalidHandle; "Invalid Handle"
0x18000e6b5  jmp     loc_18000E9AF
0x18000e6ba  mov     r12d, 1
0x18000e6c0  mov     r15d, r14d
0x18000e6c3  lea     edx, [r12+56h]
0x18000e6c8  and     r15d, 8
0x18000e6cc  jz      short loc_18000E6D8
0x18000e6ce  test    r14b, 10h
0x18000e6d2  jz      short loc_18000E6D8
0x18000e6d4  mov     ebx, edx
0x18000e6d6  jmp     short loc_18000E6DA
0x18000e6d8  xor     ebx, ebx
0x18000e6da  mov     eax, ebx
0x18000e6dc  mov     r8d, 80070000h
0x18000e6e2  or      eax, r8d
0x18000e6e5  test    ebx, ebx
0x18000e6e7  cmovnz  ebx, eax
0x18000e6ea  cmp     ebx, 0FFFFFFFFh
0x18000e6ed  jg      short loc_18000E6FB
0x18000e6ef  lea     rcx, aEnableDisableO; "Enable/Disable OnDemand Population Can'"...
0x18000e6f6  jmp     loc_18000E9AF
0x18000e6fb  test    rdi, rdi
0x18000e6fe  jz      short loc_18000E70A
0x18000e700  test    r14b, 20h
0x18000e704  jz      short loc_18000E70A
0x18000e706  mov     ebx, edx
0x18000e708  jmp     short loc_18000E70C
0x18000e70a  xor     ebx, ebx
0x18000e70c  mov     eax, ebx
0x18000e70e  or      eax, r8d
0x18000e711  test    ebx, ebx
0x18000e713  cmovnz  ebx, eax
0x18000e716  cmp     ebx, 0FFFFFFFFh
0x18000e719  jg      short loc_18000E727
0x18000e71b  lea     rcx, aRemoveFileiden; "Remove FileIdentity AND Non Null FileId"...
0x18000e722  jmp     loc_18000E9AF
0x18000e727  xor     eax, eax
0x18000e729  mov     cl, r14b
0x18000e72c  and     cl, 42h
0x18000e72f  mov     ebx, edx
0x18000e731  cmp     cl, 42h ; 'B'
0x18000e734  cmovnz  ebx, eax
0x18000e737  mov     eax, ebx
0x18000e739  or      eax, r8d
0x18000e73c  test    ebx, ebx
0x18000e73e  cmovnz  ebx, eax
0x18000e741  cmp     ebx, 0FFFFFFFFh
0x18000e744  jg      short loc_18000E752
0x18000e746  lea     rcx, aMarkAndClearIn; "Mark and Clear In Sync together not all"...
0x18000e74d  jmp     loc_18000E9AF
0x18000e752  mov     r13d, [rbp+3Fh+arg_28]
0x18000e756  xor     ecx, ecx
0x18000e758  mov     edx, dword ptr [rbp+3Fh+arg_18]
0x18000e75b  mov     r9d, r13d
0x18000e75e  shl     r9, 4
0x18000e762  add     edx, 4Ch ; 'L'
0x18000e765  mov     eax, edx
0x18000e767  mov     r8d, r14d
0x18000e76a  mov     edi, 4
0x18000e76f  mov     [rbp+3Fh+Size], r9
0x18000e773  and     r8d, edi
0x18000e776  test    r8d, r8d
0x18000e779  mov     [rbp+3Fh+arg_30], r8d
0x18000e77d  cmovz   rcx, r9
0x18000e781  add     rcx, rax
0x18000e784  mov     eax, 98h
0x18000e789  mov     [rsp+110h+var_C8], rax
0x18000e78e  cmp     rcx, rax
0x18000e791  jb      short loc_18000E7A7
0x18000e793  xor     eax, eax
0x18000e795  mov     rcx, r9
0x18000e798  test    r8d, r8d
0x18000e79b  cmovnz  rcx, rax
0x18000e79f  lea     eax, [rcx+rdx]
0x18000e7a2  mov     [rsp+110h+var_C8], rax
0x18000e7a7  mov     ebx, eax
0x18000e7a9  call    cs:__imp_GetProcessHeap
0x18000e7af  mov     r8d, ebx; dwBytes
0x18000e7b2  mov     edx, 8; dwFlags
0x18000e7b7  mov     rcx, rax; hHeap
0x18000e7ba  call    cs:__imp_HeapAlloc
0x18000e7c0  mov     rsi, rax
0x18000e7c3  neg     rax
0x18000e7c6  sbb     ebx, ebx
0x18000e7c8  not     ebx
0x18000e7ca  and     ebx, 8
0x18000e7cd  mov     eax, ebx
0x18000e7cf  or      eax, 80070000h
0x18000e7d4  test    rsi, rsi
0x18000e7d7  cmovz   ebx, eax
0x18000e7da  cmp     ebx, 0FFFFFFFFh
0x18000e7dd  jg      short loc_18000E7EB
0x18000e7df  lea     rcx, aHsmopMemoryAll; "hsmOp Memory Allocation failed"
0x18000e7e6  jmp     loc_18000E9AF
0x18000e7eb  mov     dword ptr [rsi+4], 0C0000003h
0x18000e7f2  mov     r8d, 4Ch ; 'L'
0x18000e7f8  mov     dword ptr [rsi], 9000001Ah
0x18000e7fe  lea     r9, [rsi+4Ch]
0x18000e802  mov     [rsi+8], edi
0x18000e805  test    r15d, r15d
0x18000e808  jz      short loc_18000E810
0x18000e80a  lea     edi, [r8-28h]
0x18000e80e  jmp     short loc_18000E81B
0x18000e810  test    r14b, 10h
0x18000e814  jz      short loc_18000E81E
0x18000e816  mov     edi, 44h ; 'D'
0x18000e81b  mov     [rsi+8], edi
0x18000e81e  test    r12b, r14b
0x18000e821  jz      short loc_18000E828
0x18000e823  or      edi, 8
0x18000e826  jmp     short loc_18000E831
0x18000e828  test    r14b, 2
0x18000e82c  jz      short loc_18000E834
0x18000e82e  or      edi, r12d
0x18000e831  mov     [rsi+8], edi
0x18000e834  mov     eax, 100h
0x18000e839  test    r14b, 40h
0x18000e83d  jz      short loc_18000E844
0x18000e83f  or      edi, eax
0x18000e841  mov     [rsi+8], edi
0x18000e844  test    r14b, 20h
0x18000e848  jz      short loc_18000E851
0x18000e84a  bts     edi, 7
0x18000e84e  mov     [rsi+8], edi
0x18000e851  test    r14b, r14b
0x18000e854  jns     short loc_18000E85D
0x18000e856  bts     edi, 0Dh
0x18000e85a  mov     [rsi+8], edi
0x18000e85d  test    eax, r14d
0x18000e860  jz      short loc_18000E869
0x18000e862  bts     edi, 10h
0x18000e866  mov     [rsi+8], edi
0x18000e869  mov     eax, 400h
0x18000e86e  bt      r14d, 9
0x18000e873  jnb     short loc_18000E87A
0x18000e875  or      edi, eax
0x18000e877  mov     [rsi+8], edi
0x18000e87a  test    eax, r14d
0x18000e87d  jz      short loc_18000E886
0x18000e87f  bts     edi, 17h
0x18000e883  mov     [rsi+8], edi
0x18000e886  cmp     [rbp+3Fh+arg_30], 0
0x18000e88a  jz      short loc_18000E894
0x18000e88c  or      edi, 2
0x18000e88f  mov     [rsi+8], edi
0x18000e892  jmp     short loc_18000E8D7
0x18000e894  mov     rdx, [rbp+3Fh+Src]; Src
0x18000e898  test    rdx, rdx
0x18000e89b  jz      short loc_18000E8D7
0x18000e89d  test    r13d, r13d
0x18000e8a0  jz      short loc_18000E8D7
0x18000e8a2  mov     rbx, [rbp+3Fh+Size]
0x18000e8a6  movzx   eax, r13w
0x18000e8aa  shl     ax, 4
0x18000e8ae  mov     rcx, r9; void *
0x18000e8b1  movzx   eax, ax
0x18000e8b4  mov     [rsi+44h], r8d
0x18000e8b8  mov     r8, rbx; Size
0x18000e8bb  mov     [rsi+48h], eax
0x18000e8be  call    memcpy_0
0x18000e8c3  lea     r9, [rbx+4Ch]
0x18000e8c7  shl     r13d, 4
0x18000e8cb  add     r9, rsi
0x18000e8ce  mov     r8d, 4Ch ; 'L'
0x18000e8d4  add     r8d, r13d
0x18000e8d7  mov     rcx, [rbp+3Fh+arg_8]
0x18000e8db  test    rcx, rcx
0x18000e8de  jz      short loc_18000E90B
0x18000e8e0  mov     eax, [rcx+20h]
0x18000e8e3  mov     [rsi+38h], eax
0x18000e8e6  mov     rax, [rcx+28h]
0x18000e8ea  mov     [rsi+18h], rax
0x18000e8ee  mov     rax, [rcx]
0x18000e8f1  mov     [rsi+20h], rax
0x18000e8f5  mov     rax, [rcx+10h]
0x18000e8f9  mov     [rsi+28h], rax
0x18000e8fd  mov     rax, [rcx+8]
0x18000e901  mov     [rsi+30h], rax
0x18000e905  mov     [rbp+3Fh+var_8C], r12b
0x18000e909  jmp     short loc_18000E910
0x18000e90b  bts     dword ptr [rsi+8], 11h
0x18000e910  mov     rdi, [rbp+3Fh+arg_38]
0x18000e917  test    rdi, rdi
0x18000e91a  jz      short loc_18000E927
0x18000e91c  mov     rax, [rdi]
0x18000e91f  mov     [rsi+10h], rax
0x18000e923  mov     [rbp+3Fh+var_8B], r12b
0x18000e927  mov     rdx, [rbp+3Fh+arg_10]; Src
0x18000e92b  test    rdx, rdx
0x18000e92e  jz      short loc_18000E949
0x18000e930  mov     eax, dword ptr [rbp+3Fh+arg_18]
0x18000e933  mov     rcx, r9; void *
0x18000e936  mov     [rsi+3Ch], r8d
0x18000e93a  mov     r8d, eax; Size
0x18000e93d  mov     [rsi+40h], eax
0x18000e940  call    memcpy_0
0x18000e945  mov     [rbp+3Fh+var_8A], r12b
0x18000e949  mov     r8d, dword ptr [rsp+110h+var_C8]
0x18000e94e  mov     rax, rdi
0x18000e951  neg     rax
0x18000e954  mov     rdx, rsi
0x18000e957  mov     rax, rdi
0x18000e95a  sbb     ecx, ecx
0x18000e95c  and     ecx, 8
0x18000e95f  neg     rax
0x18000e962  lea     rax, [rsp+110h+var_C0]
0x18000e967  sbb     r9, r9
0x18000e96a  and     r9, rax
0x18000e96d  mov     rax, [rbp+3Fh+arg_40]
0x18000e974  mov     [rsp+110h+var_E0], rax; __int64
0x18000e979  lea     rax, [rsp+110h+NumberOfBytesTransferred+4]
0x18000e97e  mov     [rsp+110h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000e983  mov     [rsp+110h+var_F0], ecx; DWORD
0x18000e987  mov     rcx, [rbp+3Fh+hFile]; hFile
0x18000e98b  call    IssueHsmControl
0x18000e990  mov     ebx, eax
0x18000e992  cmp     eax, 0FFFFFFFFh
0x18000e995  jg      short loc_18000E9A0
0x18000e997  lea     rcx, aIssuehsmcontro; "IssueHsmControl Failed"
0x18000e99e  jmp     short loc_18000E9AF
0x18000e9a0  xor     ecx, ecx
0x18000e9a2  test    rdi, rdi
0x18000e9a5  jz      short loc_18000E9AF
0x18000e9a7  mov     rax, [rsp+110h+var_C0]
0x18000e9ac  mov     [rdi], rax
0x18000e9af  mov     dword ptr [rsp+110h+var_D8], ebx
0x18000e9b3  lea     rax, [rbp+3Fh+var_A0]
0x18000e9b7  mov     [rsp+110h+var_E0], rax
0x18000e9bc  xor     r9d, r9d
0x18000e9bf  mov     rax, [rbp+3Fh+UnbiasedTime]
0x18000e9c3  xor     r8d, r8d
0x18000e9c6  mov     [rbp+3Fh+var_90], r14d
0x18000e9ca  mov     r14, [rbp+3Fh+hFile]
0x18000e9ce  mov     [rbp+3Fh+var_98], rcx
0x18000e9d2  mov     rdx, r14
0x18000e9d5  mov     [rsp+110h+lpNumberOfBytesTransferred], rax
0x18000e9da  mov     ecx, 11h
0x18000e9df  mov     qword ptr [rsp+110h+var_F0], 0
0x18000e9e8  call    TlmLogApiReliability
0x18000e9ed  test    r12b, r12b
0x18000e9f0  jz      short loc_18000E9FA
0x18000e9f2  mov     rcx, r14
0x18000e9f5  call    CfpReleaseProtectedHandle
0x18000e9fa  test    rsi, rsi
0x18000e9fd  jz      short loc_18000EA13
0x18000e9ff  call    cs:__imp_GetProcessHeap
0x18000ea05  mov     r8, rsi; lpMem
0x18000ea08  xor     edx, edx; dwFlags
0x18000ea0a  mov     rcx, rax; hHeap
0x18000ea0d  call    cs:__imp_HeapFree
0x18000ea13  mov     eax, ebx
0x18000ea15  add     rsp, 0D8h
0x18000ea1c  pop     r15
0x18000ea1e  pop     r14
0x18000ea20  pop     r13
  ... truncated ...
```
