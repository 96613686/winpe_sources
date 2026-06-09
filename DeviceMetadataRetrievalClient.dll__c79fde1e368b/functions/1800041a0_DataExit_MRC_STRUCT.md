# DataExit(_MRC_STRUCT *)

- ea: `0x1800041a0`
- end: `0x18000431a`
- name: `?DataExit@@YAXPEAU_MRC_STRUCT@@@Z`
- size: `378`
- prototype: `void __fastcall(struct _MRC_STRUCT *lpMem)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004320`
- `0x180004d08`

## callees

- `0x180001520`
- `0x1800041a0`
- `0x18000bcd4`
- `0x18000eba8`
- `0x18000f33c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180004205`
- `KERNEL32!GetProcessHeap` at `0x180004222`
- `KERNEL32!GetProcessHeap` at `0x18000423f`
- `KERNEL32!GetProcessHeap` at `0x18000425c`
- `KERNEL32!GetProcessHeap` at `0x1800042a4`
- `KERNEL32!GetProcessHeap` at `0x1800042bf`
- `KERNEL32!GetProcessHeap` at `0x180004205`
- `KERNEL32!GetProcessHeap` at `0x180004222`
- `KERNEL32!GetProcessHeap` at `0x18000423f`
- `KERNEL32!GetProcessHeap` at `0x18000425c`
- `KERNEL32!GetProcessHeap` at `0x1800042a4`
- `KERNEL32!GetProcessHeap` at `0x1800042bf`
- `KERNEL32!HeapFree` at `0x180004213`
- `KERNEL32!HeapFree` at `0x180004230`
- `KERNEL32!HeapFree` at `0x18000424d`
- `KERNEL32!HeapFree` at `0x18000426a`
- `KERNEL32!HeapFree` at `0x1800042b2`
- `KERNEL32!HeapFree` at `0x1800042cd`
- `KERNEL32!HeapFree` at `0x180004213`
- `KERNEL32!HeapFree` at `0x180004230`
- `KERNEL32!HeapFree` at `0x18000424d`
- `KERNEL32!HeapFree` at `0x18000426a`
- `KERNEL32!HeapFree` at `0x1800042b2`
- `KERNEL32!HeapFree` at `0x1800042cd`
- `KERNEL32!CloseHandle` at `0x1800042df`
- `KERNEL32!CloseHandle` at `0x1800042df`
- `KERNEL32!DeleteCriticalSection` at `0x1800041c9`
- `KERNEL32!DeleteCriticalSection` at `0x1800041c9`
- `KERNEL32!ClosePrivateNamespace` at `0x1800042fe`
- `KERNEL32!ClosePrivateNamespace` at `0x1800042fe`

## pseudocode

```c
void __fastcall DataExit(struct _MRC_STRUCT *lpMem)
{
  __int64 v1; // rdi
  struct CHG_STRUCT *v3; // rcx
  void *v4; // rdi
  HANDLE ProcessHeap; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  _DWORD *v12; // rcx
  _DWORD *v13; // rcx
  void *v14; // rdi
  HANDLE v15; // rax
  HANDLE v16; // rax

  if ( lpMem )
  {
    v1 = *((_QWORD *)lpMem + 8);
    if ( v1 )
    {
      if ( *(_DWORD *)(v1 + 48) )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
        *(_DWORD *)(v1 + 48) = 0;
      }
      operator delete((void *)v1);
    }
    v3 = (struct CHG_STRUCT *)*((_QWORD *)lpMem + 7);
    if ( v3 )
    {
      if ( *(_DWORD *)v3 == 1128808740 )
        _ChgExit(v3);
      *((_QWORD *)lpMem + 7) = 0;
    }
    v4 = (void *)*((_QWORD *)lpMem + 1);
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    v6 = (void *)*((_QWORD *)lpMem + 2);
    if ( v6 )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
    v8 = (void *)*((_QWORD *)lpMem + 3);
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
    }
    v10 = (void *)*((_QWORD *)lpMem + 4);
    if ( v10 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
    v12 = (_DWORD *)*((_QWORD *)lpMem + 5);
    if ( v12 && *v12 == 1229866053 )
      IndexExit(v12);
    v13 = (_DWORD *)*((_QWORD *)lpMem + 6);
    if ( v13 && *v13 == 1396916558 )
      ScannerExit(v13);
    v14 = *(void **)lpMem;
    if ( *(_QWORD *)lpMem )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
      *(_QWORD *)lpMem = 0;
    }
    v16 = GetProcessHeap();
    HeapFree(v16, 0, lpMem);
    if ( g_hDmrcPrivateMutex )
    {
      CloseHandle(g_hDmrcPrivateMutex);
      g_hDmrcPrivateMutex = 0;
    }
    if ( g_hDmrcPrivateNamespace )
    {
      ClosePrivateNamespace(g_hDmrcPrivateNamespace, 0);
      g_hDmrcPrivateNamespace = 0;
    }
  }
}

```

## disassembly

```asm
0x1800041a0  test    rcx, rcx
0x1800041a3  jz      locret_180004319
0x1800041a9  mov     [rsp+arg_0], rbx
0x1800041ae  push    rdi
0x1800041af  sub     rsp, 20h
0x1800041b3  mov     rdi, [rcx+40h]
0x1800041b7  mov     rbx, rcx
0x1800041ba  test    rdi, rdi
0x1800041bd  jz      short loc_1800041DE
0x1800041bf  cmp     dword ptr [rdi+30h], 0
0x1800041c3  jz      short loc_1800041D6
0x1800041c5  lea     rcx, [rdi+8]; lpCriticalSection
0x1800041c9  call    cs:__imp_DeleteCriticalSection
0x1800041cf  mov     dword ptr [rdi+30h], 0
0x1800041d6  mov     rcx, rdi; Block
0x1800041d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800041de  mov     rcx, [rbx+38h]; Block
0x1800041e2  test    rcx, rcx
0x1800041e5  jz      short loc_1800041FC
0x1800041e7  cmp     dword ptr [rcx], 43484124h
0x1800041ed  jnz     short loc_1800041F4
0x1800041ef  call    ?_ChgExit@@YAXPEAUCHG_STRUCT@@@Z; _ChgExit(CHG_STRUCT *)
0x1800041f4  mov     qword ptr [rbx+38h], 0
0x1800041fc  mov     rdi, [rbx+8]
0x180004200  test    rdi, rdi
0x180004203  jz      short loc_180004219
0x180004205  call    cs:__imp_GetProcessHeap
0x18000420b  mov     r8, rdi; lpMem
0x18000420e  xor     edx, edx; dwFlags
0x180004210  mov     rcx, rax; hHeap
0x180004213  call    cs:__imp_HeapFree
0x180004219  mov     rdi, [rbx+10h]
0x18000421d  test    rdi, rdi
0x180004220  jz      short loc_180004236
0x180004222  call    cs:__imp_GetProcessHeap
0x180004228  mov     r8, rdi; lpMem
0x18000422b  xor     edx, edx; dwFlags
0x18000422d  mov     rcx, rax; hHeap
0x180004230  call    cs:__imp_HeapFree
0x180004236  mov     rdi, [rbx+18h]
0x18000423a  test    rdi, rdi
0x18000423d  jz      short loc_180004253
0x18000423f  call    cs:__imp_GetProcessHeap
0x180004245  mov     r8, rdi; lpMem
0x180004248  xor     edx, edx; dwFlags
0x18000424a  mov     rcx, rax; hHeap
0x18000424d  call    cs:__imp_HeapFree
0x180004253  mov     rdi, [rbx+20h]
0x180004257  test    rdi, rdi
0x18000425a  jz      short loc_180004270
0x18000425c  call    cs:__imp_GetProcessHeap
0x180004262  mov     r8, rdi; lpMem
0x180004265  xor     edx, edx; dwFlags
0x180004267  mov     rcx, rax; hHeap
0x18000426a  call    cs:__imp_HeapFree
0x180004270  mov     rcx, [rbx+28h]; lpMem
0x180004274  test    rcx, rcx
0x180004277  jz      short loc_180004286
0x180004279  cmp     dword ptr [rcx], 494E4445h
0x18000427f  jnz     short loc_180004286
0x180004281  call    _IndexExit
0x180004286  mov     rcx, [rbx+30h]; void *
0x18000428a  test    rcx, rcx
0x18000428d  jz      short loc_18000429C
0x18000428f  cmp     dword ptr [rcx], 5343414Eh
0x180004295  jnz     short loc_18000429C
0x180004297  call    _ScannerExit
0x18000429c  mov     rdi, [rbx]
0x18000429f  test    rdi, rdi
0x1800042a2  jz      short loc_1800042BF
0x1800042a4  call    cs:__imp_GetProcessHeap
0x1800042aa  mov     r8, rdi; lpMem
0x1800042ad  xor     edx, edx; dwFlags
0x1800042af  mov     rcx, rax; hHeap
0x1800042b2  call    cs:__imp_HeapFree
0x1800042b8  mov     qword ptr [rbx], 0
0x1800042bf  call    cs:__imp_GetProcessHeap
0x1800042c5  mov     r8, rbx; lpMem
0x1800042c8  xor     edx, edx; dwFlags
0x1800042ca  mov     rcx, rax; hHeap
0x1800042cd  call    cs:__imp_HeapFree
0x1800042d3  mov     rcx, cs:?g_hDmrcPrivateMutex@@3PEAXEA; hObject
0x1800042da  test    rcx, rcx
0x1800042dd  jz      short loc_1800042F0
0x1800042df  call    cs:__imp_CloseHandle
0x1800042e5  mov     cs:?g_hDmrcPrivateMutex@@3PEAXEA, 0; void * g_hDmrcPrivateMutex
0x1800042f0  mov     rcx, cs:?g_hDmrcPrivateNamespace@@3PEAXEA; Handle
0x1800042f7  test    rcx, rcx
0x1800042fa  jz      short loc_18000430F
0x1800042fc  xor     edx, edx; Flags
0x1800042fe  call    cs:__imp_ClosePrivateNamespace
0x180004304  mov     cs:?g_hDmrcPrivateNamespace@@3PEAXEA, 0; void * g_hDmrcPrivateNamespace
0x18000430f  mov     rbx, [rsp+28h+arg_0]
0x180004314  add     rsp, 20h
0x180004318  pop     rdi
0x180004319  retn
```
