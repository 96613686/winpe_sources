# CfConvertToPlaceholder

- ea: `0x18000d560`
- end: `0x18000d7a6`
- name: `CfConvertToPlaceholder`
- size: `582`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800022ee`
- `0x180004628`
- `0x180004a10`
- `0x180004a68`
- `0x18000d560`
- `0x180011e18`
- `0x18001bb5c`
- `0x18001be5c`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000d5b2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000d5b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d617`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d775`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d617`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d775`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d625`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d625`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d783`

## string_xrefs

- `0x18000d5cf`: `CfpIsDirectory Failed`

## pseudocode

```c
__int64 __fastcall CfConvertToPlaceholder(
        unsigned __int64 hFile,
        void *a2,
        unsigned int a3,
        int a4,
        _QWORD *a5,
        struct _OVERLAPPED *a6)
{
  size_t v6; // r15
  _DWORD *v9; // rbx
  char v10; // r12
  int IsDirectory; // eax
  __int64 v12; // rdx
  char v13; // r13
  int v14; // edi
  const wchar_t *v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  HANDLE ProcessHeap; // rax
  int v19; // eax
  DWORD v20; // r8d
  _QWORD *v21; // r15
  HANDLE v22; // rax
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+48h] [rbp-51h] BYREF
  int v26; // [rsp+50h] [rbp-49h] BYREF
  const wchar_t *v27; // [rsp+58h] [rbp-41h]
  int v28; // [rsp+60h] [rbp-39h]
  char v29; // [rsp+64h] [rbp-35h]
  unsigned __int64 v30; // [rsp+68h] [rbp-31h]
  DWORD NumberOfBytesTransferred; // [rsp+F0h] [rbp+57h] BYREF
  void *Src; // [rsp+F8h] [rbp+5Fh]
  DWORD v33; // [rsp+108h] [rbp+6Fh] BYREF

  Src = a2;
  v6 = a3;
  NumberOfBytesTransferred = 0;
  v24 = 0;
  UnbiasedTime = 0;
  LOBYTE(v33) = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v26, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  IsDirectory = CfpIsDirectory(hFile, &v33);
  v13 = v33;
  v14 = IsDirectory;
  if ( IsDirectory > -1 )
  {
    LOBYTE(v12) = (_BYTE)v33 == 0;
    if ( (unsigned __int8)CfpReferenceProtectedHandle(hFile, v12) )
    {
      v16 = v6 + 20;
      v10 = 1;
      if ( (unsigned int)(v6 + 20) < 0x98 )
        v16 = 152;
      v33 = v16;
      v17 = v16;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, v17);
      v14 = v9 == 0 ? 8 : 0;
      if ( !v9 )
        v14 |= 0x80070000;
      if ( v14 > -1 )
      {
        v9[1] = -1073741822;
        *v9 = -1879048166;
        v9[2] = 0;
        if ( (a4 & 1) != 0 )
        {
          v9[2] = 1;
          v19 = 1;
        }
        else
        {
          v19 = 0;
        }
        if ( (a4 & 2) != 0 )
        {
          v19 |= 2u;
          v9[2] = v19;
        }
        if ( (a4 & 4) != 0 )
        {
          v19 |= 0x20u;
          v9[2] = v19;
        }
        if ( (a4 & 8) != 0 )
        {
          v19 |= 0x400u;
          v9[2] = v19;
        }
        if ( (a4 & 0x10) != 0 )
          v9[2] = v19 | 0x1000000;
        memcpy_0(v9 + 5, Src, v6);
        v20 = v33;
        v9[4] = v6;
        v21 = a5;
        v14 = IssueHsmControl(
                hFile,
                v9,
                v20,
                (void *)((unsigned __int64)&v24 & -(__int64)(a5 != 0)),
                a5 != 0 ? 8 : 0,
                &NumberOfBytesTransferred,
                a6);
        if ( v14 > -1 )
        {
          v15 = 0;
          if ( v21 )
            *v21 = v24;
        }
        else
        {
          v15 = L"IssueHsmControl Failed";
        }
      }
      else
      {
        v15 = L"hsmOp Memory allocation Failed";
      }
    }
    else
    {
      v14 = -2147024890;
      v15 = L"Invalid File Handle";
    }
  }
  else
  {
    v15 = L"CfpIsDirectory Failed";
  }
  v27 = v15;
  v28 = a4;
  v29 = v13;
  v30 = hFile;
  TlmLogApiReliability(0x10u, hFile, 0, 0, 0, UnbiasedTime, &v26, v14);
  if ( v10 )
    CfpReleaseProtectedHandle(hFile);
  if ( v9 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v9);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000d560  mov     [rsp-8+arg_10], rbx
0x18000d565  mov     [rsp-8+Src], rdx
0x18000d56a  push    rbp
0x18000d56b  push    rsi
0x18000d56c  push    rdi
0x18000d56d  push    r12
0x18000d56f  push    r13
0x18000d571  push    r14
0x18000d573  push    r15
0x18000d575  lea     rbp, [rsp-17h]
0x18000d57a  sub     rsp, 0B0h
0x18000d581  xor     eax, eax
0x18000d583  mov     r15d, r8d
0x18000d586  mov     r14, rcx
0x18000d589  mov     [rbp+47h+NumberOfBytesTransferred], eax
0x18000d58c  xor     edx, edx; Val
0x18000d58e  mov     [rbp+47h+var_A0], rax
0x18000d592  lea     rcx, [rbp+47h+var_90]; void *
0x18000d596  mov     [rbp+47h+UnbiasedTime], rax
0x18000d59a  lea     r8d, [rax+58h]; Size
0x18000d59e  mov     byte ptr [rbp+47h+arg_18], al
0x18000d5a1  mov     esi, r9d
0x18000d5a4  mov     ebx, eax
0x18000d5a6  mov     r12b, al
0x18000d5a9  call    memset_0
0x18000d5ae  lea     rcx, [rbp+47h+UnbiasedTime]; UnbiasedTime
0x18000d5b2  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000d5b8  lea     rdx, [rbp+47h+arg_18]
0x18000d5bc  mov     rcx, r14
0x18000d5bf  call    CfpIsDirectory
0x18000d5c4  mov     r13b, byte ptr [rbp+47h+arg_18]
0x18000d5c8  mov     edi, eax
0x18000d5ca  cmp     eax, 0FFFFFFFFh
0x18000d5cd  jg      short loc_18000D5DB
0x18000d5cf  lea     rcx, aCfpisdirectory; "CfpIsDirectory Failed"
0x18000d5d6  jmp     loc_18000D722
0x18000d5db  test    r13b, r13b
0x18000d5de  mov     rcx, r14
0x18000d5e1  setz    dl
0x18000d5e4  call    CfpReferenceProtectedHandle
0x18000d5e9  test    al, al
0x18000d5eb  jnz     short loc_18000D5FE
0x18000d5ed  mov     edi, 80070006h
0x18000d5f2  lea     rcx, aInvalidFileHan; "Invalid File Handle"
0x18000d5f9  jmp     loc_18000D722
0x18000d5fe  lea     eax, [r15+14h]
0x18000d602  mov     ecx, 98h
0x18000d607  cmp     eax, ecx
0x18000d609  mov     r12d, 1
0x18000d60f  cmovb   eax, ecx
0x18000d612  mov     [rbp+47h+arg_18], eax
0x18000d615  mov     ebx, eax
0x18000d617  call    cs:__imp_GetProcessHeap
0x18000d61d  mov     r8d, ebx; dwBytes
0x18000d620  xor     edx, edx; dwFlags
0x18000d622  mov     rcx, rax; hHeap
0x18000d625  call    cs:__imp_HeapAlloc
0x18000d62b  mov     rbx, rax
0x18000d62e  neg     rax
0x18000d631  sbb     edi, edi
0x18000d633  not     edi
0x18000d635  and     edi, 8
0x18000d638  mov     eax, edi
0x18000d63a  or      eax, 80070000h
0x18000d63f  test    rbx, rbx
0x18000d642  cmovz   edi, eax
0x18000d645  cmp     edi, 0FFFFFFFFh
0x18000d648  jg      short loc_18000D656
0x18000d64a  lea     rcx, aHsmopMemoryAll_0; "hsmOp Memory allocation Failed"
0x18000d651  jmp     loc_18000D722
0x18000d656  mov     dword ptr [rbx+4], 0C0000002h
0x18000d65d  mov     dword ptr [rbx], 9000001Ah
0x18000d663  mov     dword ptr [rbx+8], 0
0x18000d66a  test    r12b, sil
0x18000d66d  jnz     short loc_18000D673
0x18000d66f  xor     eax, eax
0x18000d671  jmp     short loc_18000D67A
0x18000d673  mov     [rbx+8], r12d
0x18000d677  mov     eax, r12d
0x18000d67a  test    sil, 2
0x18000d67e  jz      short loc_18000D686
0x18000d680  or      eax, 2
0x18000d683  mov     [rbx+8], eax
0x18000d686  test    sil, 4
0x18000d68a  jz      short loc_18000D692
0x18000d68c  or      eax, 20h
0x18000d68f  mov     [rbx+8], eax
0x18000d692  test    sil, 8
0x18000d696  jz      short loc_18000D69F
0x18000d698  bts     eax, 0Ah
0x18000d69c  mov     [rbx+8], eax
0x18000d69f  test    sil, 10h
0x18000d6a3  jz      short loc_18000D6AC
0x18000d6a5  bts     eax, 18h
0x18000d6a9  mov     [rbx+8], eax
0x18000d6ac  mov     rdx, [rbp+47h+Src]; Src
0x18000d6b0  lea     rcx, [rbx+14h]; void *
0x18000d6b4  mov     r8, r15; Size
0x18000d6b7  call    memcpy_0
0x18000d6bc  mov     r8d, [rbp+47h+arg_18]
0x18000d6c0  mov     rdx, rbx
0x18000d6c3  mov     [rbx+10h], r15d
0x18000d6c7  mov     r15, [rbp+47h+arg_20]
0x18000d6cb  mov     rax, r15
0x18000d6ce  neg     rax
0x18000d6d1  mov     rax, r15
0x18000d6d4  sbb     ecx, ecx
0x18000d6d6  and     ecx, 8
0x18000d6d9  neg     rax
0x18000d6dc  lea     rax, [rbp+47h+var_A0]
0x18000d6e0  sbb     r9, r9
0x18000d6e3  and     r9, rax
0x18000d6e6  mov     rax, [rbp+47h+arg_28]
0x18000d6ea  mov     [rsp+0E0h+var_B0], rax; __int64
0x18000d6ef  lea     rax, [rbp+47h+NumberOfBytesTransferred]
0x18000d6f3  mov     [rsp+0E0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000d6f8  mov     [rsp+0E0h+var_C0], ecx; DWORD
0x18000d6fc  mov     rcx, r14; hFile
0x18000d6ff  call    IssueHsmControl
0x18000d704  mov     edi, eax
0x18000d706  cmp     eax, 0FFFFFFFFh
0x18000d709  jg      short loc_18000D714
0x18000d70b  lea     rcx, aIssuehsmcontro; "IssueHsmControl Failed"
0x18000d712  jmp     short loc_18000D722
0x18000d714  xor     ecx, ecx
0x18000d716  test    r15, r15
0x18000d719  jz      short loc_18000D722
0x18000d71b  mov     rax, [rbp+47h+var_A0]
0x18000d71f  mov     [r15], rax
0x18000d722  mov     [rsp+0E0h+var_A8], edi
0x18000d726  lea     rax, [rbp+47h+var_90]
0x18000d72a  mov     [rsp+0E0h+var_B0], rax
0x18000d72f  xor     r9d, r9d
0x18000d732  mov     rax, [rbp+47h+UnbiasedTime]
0x18000d736  xor     r8d, r8d
0x18000d739  mov     [rbp+47h+var_88], rcx
0x18000d73d  mov     rdx, r14
0x18000d740  mov     [rsp+0E0h+lpNumberOfBytesTransferred], rax
0x18000d745  mov     ecx, 10h
0x18000d74a  mov     qword ptr [rsp+0E0h+var_C0], 0
0x18000d753  mov     [rbp+47h+var_80], esi
0x18000d756  mov     [rbp+47h+var_7C], r13b
0x18000d75a  mov     [rbp+47h+var_78], r14
0x18000d75e  call    TlmLogApiReliability
0x18000d763  test    r12b, r12b
0x18000d766  jz      short loc_18000D770
0x18000d768  mov     rcx, r14
0x18000d76b  call    CfpReleaseProtectedHandle
0x18000d770  test    rbx, rbx
0x18000d773  jz      short loc_18000D789
0x18000d775  call    cs:__imp_GetProcessHeap
0x18000d77b  mov     r8, rbx; lpMem
0x18000d77e  xor     edx, edx; dwFlags
0x18000d780  mov     rcx, rax; hHeap
0x18000d783  call    cs:__imp_HeapFree
0x18000d789  mov     rbx, [rsp+0E0h+arg_10]
0x18000d791  mov     eax, edi
0x18000d793  add     rsp, 0B0h
0x18000d79a  pop     r15
0x18000d79c  pop     r14
0x18000d79e  pop     r13
0x18000d7a0  pop     r12
0x18000d7a2  pop     rdi
0x18000d7a3  pop     rsi
0x18000d7a4  pop     rbp
0x18000d7a5  retn
```
