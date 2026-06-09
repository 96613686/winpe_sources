# CfCreatePlaceholders

- ea: `0x18000d7b0`
- end: `0x18000da5f`
- name: `CfCreatePlaceholders`
- size: `687`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x18000446c`
- `0x18000d7b0`
- `0x18000f6fc`
- `0x180010958`
- `0x180011514`
- `0x180011e18`
- `0x18001bb5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d8b0`
- `ntdll!RtlNtStatusToDosError` at `0x18000d8b0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000d853`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000d853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da1b`

## string_xrefs

- `0x18000d8cd`: `CreateFile on BaseDirectoryPath Failed`

## pseudocode

```c
__int64 __fastcall CfCreatePlaceholders(__int64 a1, __int64 a2, unsigned int a3, int a4, _DWORD *a5)
{
  int v7; // ebx
  void *v8; // r15
  const WCHAR *v9; // rdi
  const WCHAR *v10; // rsi
  __int64 v11; // rdx
  const wchar_t *v12; // r14
  NTSTATUS v13; // eax
  signed int v14; // eax
  int v15; // eax
  int v16; // eax
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h]
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  void *v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  unsigned __int64 UnbiasedTime; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v30; // [rsp+98h] [rbp-68h]
  unsigned int v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+B0h] [rbp-50h]
  _DWORD v34[6]; // [rsp+F0h] [rbp-10h] BYREF
  void *v35; // [rsp+108h] [rbp+8h]
  char v36[4]; // [rsp+190h] [rbp+90h] BYREF
  char v37; // [rsp+194h] [rbp+94h] BYREF
  char v38; // [rsp+394h] [rbp+294h] BYREF

  v26 = a2;
  v28 = a1;
  v23 = a4;
  hObject = (HANDLE)-1LL;
  memset_0(v34, 0, 0x98u);
  v7 = 0;
  v22 = 0;
  v21 = 0;
  v8 = 0;
  NumberOfBytesTransferred = 0;
  memset_0(v36, 0, 0x404u);
  UnbiasedTime = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v29, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( a5 )
    *a5 = 0;
  if ( !a3 )
    v7 = -2147024809;
  if ( v7 > -1 )
  {
    v13 = CfpCreateFile(a1, v11, 0, 7u, v19, 0x21u, v20, &hObject);
    v14 = RtlNtStatusToDosError(v13);
    v12 = 0;
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 > -1 )
    {
      v10 = (const WCHAR *)&v38;
      v9 = (const WCHAR *)&v37;
      if ( (int)CfpGetSyncRootInfoByHandle(hObject, 0) < 0 )
      {
        v10 = 0;
        v9 = 0;
      }
      v15 = BuildSetPlaceholderInfo(v26, a3, &v22, &v21);
      v8 = v22;
      v7 = v15;
      if ( v15 > -1 )
      {
        v34[2] = v23;
        v34[4] = v21;
        v34[1] = -1073741823;
        v34[0] = -1879048166;
        v35 = v22;
        v7 = IssueHsmControl((unsigned __int64)hObject, v34, 0x98u, 0, 0, &NumberOfBytesTransferred, 0);
        if ( v7 > -1 )
        {
          LODWORD(v22) = 0;
          v16 = ProcessReturnedSetPlaceholderInfo((_DWORD)v8, v21, v26, a3, (__int64)&v22);
          v7 = (int)v22;
          if ( a5 )
            *a5 = v16;
        }
        else
        {
          v12 = L"IssueHsmControl Failed";
        }
      }
      else
      {
        v12 = L"BuildSetPlaceholderInfo Failed";
      }
    }
    else
    {
      v12 = L"CreateFile on BaseDirectoryPath Failed";
    }
  }
  else
  {
    v12 = L"Invalid PlaceholderCount";
  }
  v33 = v23;
  v31 = a3;
  v32 = v28;
  v30 = v12;
  TlmLogApiReliability(0xFu, (unsigned __int64)hObject, v28, v9, v10, UnbiasedTime, &v29, v7);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d7b0  push    rbp
0x18000d7b2  push    rbx
0x18000d7b3  push    rsi
0x18000d7b4  push    rdi
0x18000d7b5  push    r12
0x18000d7b7  push    r13
0x18000d7b9  push    r14
0x18000d7bb  push    r15
0x18000d7bd  lea     rbp, [rsp-4B8h]
0x18000d7c5  sub     rsp, 5B8h
0x18000d7cc  mov     rax, cs:__security_cookie
0x18000d7d3  xor     rax, rsp
0x18000d7d6  mov     [rbp+4F0h+var_50], rax
0x18000d7dd  mov     r12, [rbp+4F0h+arg_20]
0x18000d7e4  mov     r13d, r8d
0x18000d7e7  mov     [rsp+5F0h+var_578], rdx
0x18000d7ec  mov     r14, rcx
0x18000d7ef  mov     [rbp+4F0h+var_568], rcx
0x18000d7f3  xor     edx, edx; Val
0x18000d7f5  mov     r8d, 98h; Size
0x18000d7fb  mov     [rsp+5F0h+var_590], r9d
0x18000d800  lea     rcx, [rbp+4F0h+var_500]; void *
0x18000d804  mov     [rsp+5F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000d80d  call    memset_0
0x18000d812  xor     ebx, ebx
0x18000d814  lea     rcx, [rbp+4F0h+var_460]; void *
0x18000d81b  xor     edx, edx; Val
0x18000d81d  mov     [rsp+5F0h+var_598], rbx
0x18000d822  mov     r8d, 404h; Size
0x18000d828  mov     [rsp+5F0h+var_5A0], ebx
0x18000d82c  mov     r15d, ebx
0x18000d82f  mov     [rsp+5F0h+NumberOfBytesTransferred], ebx
0x18000d833  call    memset_0
0x18000d838  xor     edx, edx; Val
0x18000d83a  mov     [rbp+4F0h+UnbiasedTime], rbx
0x18000d83e  lea     r8d, [rbx+58h]; Size
0x18000d842  mov     edi, ebx
0x18000d844  lea     rcx, [rbp+4F0h+var_560]; void *
0x18000d848  mov     esi, ebx
0x18000d84a  call    memset_0
0x18000d84f  lea     rcx, [rbp+4F0h+UnbiasedTime]; UnbiasedTime
0x18000d853  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000d859  test    r12, r12
0x18000d85c  jz      short loc_18000D862
0x18000d85e  mov     [r12], ebx
0x18000d862  test    r13d, r13d
0x18000d865  mov     eax, 57h ; 'W'
0x18000d86a  cmovz   ebx, eax
0x18000d86d  mov     eax, ebx
0x18000d86f  or      eax, 80070000h
0x18000d874  test    r13d, r13d
0x18000d877  cmovz   ebx, eax
0x18000d87a  cmp     ebx, 0FFFFFFFFh
0x18000d87d  jg      short loc_18000D88B
0x18000d87f  lea     r14, aInvalidPlaceho
0x18000d886  jmp     loc_18000D9CC
0x18000d88b  lea     rax, [rsp+5F0h+hObject]
0x18000d890  mov     r9d, 7
0x18000d896  mov     [rsp+5F0h+var_5B8], rax
0x18000d89b  xor     r8d, r8d
0x18000d89e  mov     rcx, r14
0x18000d8a1  mov     dword ptr [rsp+5F0h+lpNumberOfBytesTransferred], 21h ; '!'
0x18000d8a9  call    CfpCreateFile
0x18000d8ae  mov     ecx, eax; Status
0x18000d8b0  call    cs:__imp_RtlNtStatusToDosError
0x18000d8b6  xor     r14d, r14d
0x18000d8b9  mov     ebx, eax
0x18000d8bb  test    eax, eax
0x18000d8bd  jle     short loc_18000D8C8
0x18000d8bf  movzx   ebx, ax
0x18000d8c2  or      ebx, 80070000h
0x18000d8c8  cmp     ebx, 0FFFFFFFFh
0x18000d8cb  jg      short loc_18000D8D9
0x18000d8cd  lea     r14, aCreatefileOnBa
0x18000d8d4  jmp     loc_18000D9CC
0x18000d8d9  mov     rcx, [rsp+5F0h+hObject]; hFile
0x18000d8de  lea     r8, [rbp+4F0h+var_460]
0x18000d8e5  mov     r9d, 404h
0x18000d8eb  mov     qword ptr [rsp+5F0h+var_5D0], r14; __int64
0x18000d8f0  mov     edx, 2
0x18000d8f5  call    CfpGetSyncRootInfoByHandle
0x18000d8fa  mov     rcx, [rsp+5F0h+var_578]
0x18000d8ff  lea     rsi, [rbp+4F0h+var_25C]
0x18000d906  test    eax, eax
0x18000d908  lea     rdi, [rbp+4F0h+var_45C]
0x18000d90f  lea     r9, [rsp+5F0h+var_5A0]
0x18000d914  mov     edx, r13d
0x18000d917  lea     r8, [rsp+5F0h+var_598]
0x18000d91c  cmovs   rsi, r14
0x18000d920  cmovs   rdi, r14
0x18000d924  call    BuildSetPlaceholderInfo
0x18000d929  mov     r15, [rsp+5F0h+var_598]
0x18000d92e  mov     ebx, eax
0x18000d930  cmp     eax, 0FFFFFFFFh
0x18000d933  jg      short loc_18000D941
0x18000d935  lea     r14, aBuildsetplaceh
0x18000d93c  jmp     loc_18000D9CC
0x18000d941  mov     eax, [rsp+5F0h+var_590]
0x18000d945  lea     rdx, [rbp+4F0h+var_500]
0x18000d949  mov     rcx, [rsp+5F0h+hObject]; hFile
0x18000d94e  xor     r9d, r9d
0x18000d951  mov     [rbp+4F0h+var_4F8], eax
0x18000d954  mov     r8d, 98h
0x18000d95a  mov     eax, [rsp+5F0h+var_5A0]
0x18000d95e  mov     [rbp+4F0h+var_4F0], eax
0x18000d961  lea     rax, [rsp+5F0h+NumberOfBytesTransferred]
0x18000d966  mov     [rsp+5F0h+var_5C0], r14; __int64
0x18000d96b  mov     [rsp+5F0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000d970  mov     [rsp+5F0h+var_5D0], r14d; DWORD
0x18000d975  mov     [rbp+4F0h+var_4FC], 0C0000001h
0x18000d97c  mov     [rbp+4F0h+var_500], 9000001Ah
0x18000d983  mov     [rbp+4F0h+var_4E8], r15
0x18000d987  call    IssueHsmControl
0x18000d98c  mov     ebx, eax
0x18000d98e  cmp     eax, 0FFFFFFFFh
0x18000d991  jg      short loc_18000D99C
0x18000d993  lea     r14, aIssuehsmcontro
0x18000d99a  jmp     short loc_18000D9CC
0x18000d99c  mov     r8, [rsp+5F0h+var_578]
0x18000d9a1  lea     rax, [rsp+5F0h+var_598]
0x18000d9a6  mov     edx, [rsp+5F0h+var_5A0]
0x18000d9aa  mov     r9d, r13d
0x18000d9ad  mov     rcx, r15
0x18000d9b0  mov     qword ptr [rsp+5F0h+var_5D0], rax
0x18000d9b5  mov     dword ptr [rsp+5F0h+var_598], r14d
0x18000d9ba  call    ProcessReturnedSetPlaceholderInfo
0x18000d9bf  mov     ebx, dword ptr [rsp+5F0h+var_598]
0x18000d9c3  test    r12, r12
0x18000d9c6  jz      short loc_18000D9CC
0x18000d9c8  mov     [r12], eax
0x18000d9cc  mov     eax, [rsp+5F0h+var_590]
0x18000d9d0  mov     ecx, 0Fh
0x18000d9d5  mov     r8, [rbp+4F0h+var_568]
0x18000d9d9  mov     r9, rdi
0x18000d9dc  mov     rdx, [rsp+5F0h+hObject]
0x18000d9e1  mov     [rbp+4F0h+var_540], eax
0x18000d9e4  lea     rax, [rbp+4F0h+var_560]
0x18000d9e8  mov     dword ptr [rsp+5F0h+var_5B8], ebx
0x18000d9ec  mov     [rsp+5F0h+var_5C0], rax
0x18000d9f1  mov     rax, [rbp+4F0h+UnbiasedTime]
0x18000d9f5  mov     [rsp+5F0h+lpNumberOfBytesTransferred], rax
0x18000d9fa  mov     qword ptr [rsp+5F0h+var_5D0], rsi
0x18000d9ff  mov     [rbp+4F0h+var_550], r13d
0x18000da03  mov     [rbp+4F0h+var_548], r8
0x18000da07  mov     [rbp+4F0h+var_558], r14
0x18000da0b  call    TlmLogApiReliability
0x18000da10  mov     rcx, [rsp+5F0h+hObject]; hObject
0x18000da15  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000da19  jz      short loc_18000DA21
0x18000da1b  call    cs:__imp_CloseHandle
0x18000da21  test    r15, r15
0x18000da24  jz      short loc_18000DA3A
0x18000da26  call    cs:__imp_GetProcessHeap
0x18000da2c  mov     r8, r15; lpMem
0x18000da2f  xor     edx, edx; dwFlags
0x18000da31  mov     rcx, rax; hHeap
0x18000da34  call    cs:__imp_HeapFree
0x18000da3a  mov     eax, ebx
0x18000da3c  mov     rcx, [rbp+4F0h+var_50]
0x18000da43  xor     rcx, rsp; StackCookie
0x18000da46  call    __security_check_cookie
0x18000da4b  add     rsp, 5B8h
0x18000da52  pop     r15
0x18000da54  pop     r14
0x18000da56  pop     r13
0x18000da58  pop     r12
0x18000da5a  pop     rdi
0x18000da5b  pop     rsi
0x18000da5c  pop     rbx
0x18000da5d  pop     rbp
0x18000da5e  retn
```
