# I_ReaderMonitorAsyncGetStatusChange

- ea: `0x18001aab0`
- end: `0x18001ac55`
- name: `I_ReaderMonitorAsyncGetStatusChange`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001aab0`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001abf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001abf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ab1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ab1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab9b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001abfe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001abfe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ab90`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ab90`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorAsyncGetStatusChange(__int64 a1, __int64 a2, int a3)
{
  DWORD LastError; // ebx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  void *v9; // rdi
  PVOID v10; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v12; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  LastError = 8;
  v7 = HeapAlloc(hHeap, 8u, 0x18u);
  v9 = v7;
  if ( v7 )
  {
    *v7 = a1;
    v7[1] = a2;
    *((_DWORD *)v7 + 4) = a3;
    ThreadpoolWork = CreateThreadpoolWork(I_ReaderMonitorStatusChangeWorker, v7, (PTP_CALLBACK_ENVIRON)(a1 + 272));
    if ( ThreadpoolWork )
    {
      LastError = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      LastError = GetLastError();
      WppTraceIndent(v12, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          226,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          LastError);
      }
      HeapFree(hHeap, 0, v9);
    }
  }
  else
  {
    WppTraceIndent(v8, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        225,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
  }
  WppTraceIndent(v10, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      227,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001aab0  push    rbx
0x18001aab2  push    rbp
0x18001aab3  push    rsi
0x18001aab4  push    rdi
0x18001aab5  push    r13
0x18001aab7  push    r14
0x18001aab9  sub     rsp, 38h
0x18001aabd  mov     r14, rdx
0x18001aac0  mov     ebp, r8d
0x18001aac3  xor     edx, edx
0x18001aac5  mov     rsi, rcx
0x18001aac8  call    WppTraceIndent
0x18001aacd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aad4  lea     r13, WPP_GLOBAL_Control
0x18001aadb  cmp     rcx, r13
0x18001aade  jz      short loc_18001AB08
0x18001aae0  test    byte ptr [rcx+1Ch], 2
0x18001aae4  jz      short loc_18001AB08
0x18001aae6  cmp     byte ptr [rcx+19h], 5
0x18001aaea  jb      short loc_18001AB08
0x18001aaec  mov     r9, cs:WPP_pszIndent
0x18001aaf3  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001aafa  mov     rcx, [rcx+10h]
0x18001aafe  mov     edx, 0E0h
0x18001ab03  call    WPP_SF_s
0x18001ab08  mov     rcx, cs:hHeap; hHeap
0x18001ab0f  mov     ebx, 8
0x18001ab14  mov     edx, ebx; dwFlags
0x18001ab16  lea     r8d, [rbx+10h]; dwBytes
0x18001ab1a  call    cs:__imp_HeapAlloc
0x18001ab20  mov     rdi, rax
0x18001ab23  test    rax, rax
0x18001ab26  jnz     short loc_18001AB75
0x18001ab28  lea     edx, [rbx-6]
0x18001ab2b  call    WppTraceIndent
0x18001ab30  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab37  cmp     rcx, r13
0x18001ab3a  jz      loc_18001AC04
0x18001ab40  test    byte ptr [rcx+1Ch], 1
0x18001ab44  jz      loc_18001AC04
0x18001ab4a  cmp     byte ptr [rcx+19h], 2
0x18001ab4e  jb      loc_18001AC04
0x18001ab54  mov     r9, cs:WPP_pszIndent
0x18001ab5b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ab62  mov     rcx, [rcx+10h]
0x18001ab66  mov     edx, 0E1h
0x18001ab6b  call    WPP_SF_s
0x18001ab70  jmp     loc_18001AC04
0x18001ab75  lea     r8, [rsi+110h]; pcbe
0x18001ab7c  mov     [rax], rsi
0x18001ab7f  mov     rdx, rdi; pv
0x18001ab82  mov     [rax+8], r14
0x18001ab86  lea     rcx, I_ReaderMonitorStatusChangeWorker; pfnwk
0x18001ab8d  mov     [rax+10h], ebp
0x18001ab90  call    cs:__imp_CreateThreadpoolWork
0x18001ab96  test    rax, rax
0x18001ab99  jnz     short loc_18001ABF9
0x18001ab9b  call    cs:__imp_GetLastError
0x18001aba1  mov     edx, 2
0x18001aba6  mov     ebx, eax
0x18001aba8  call    WppTraceIndent
0x18001abad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abb4  cmp     rcx, r13
0x18001abb7  jz      short loc_18001ABE5
0x18001abb9  test    byte ptr [rcx+1Ch], 1
0x18001abbd  jz      short loc_18001ABE5
0x18001abbf  cmp     byte ptr [rcx+19h], 3
0x18001abc3  jb      short loc_18001ABE5
0x18001abc5  mov     r9, cs:WPP_pszIndent
0x18001abcc  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001abd3  mov     rcx, [rcx+10h]
0x18001abd7  mov     edx, 0E2h
0x18001abdc  mov     [rsp+68h+var_48], ebx
0x18001abe0  call    WPP_SF_sd
0x18001abe5  mov     rcx, cs:hHeap; hHeap
0x18001abec  mov     r8, rdi; lpMem
0x18001abef  xor     edx, edx; dwFlags
0x18001abf1  call    cs:__imp_HeapFree
0x18001abf7  jmp     short loc_18001AC04
0x18001abf9  xor     ebx, ebx
0x18001abfb  mov     rcx, rax; pwk
0x18001abfe  call    cs:__imp_SubmitThreadpoolWork
0x18001ac04  mov     edx, 1
0x18001ac09  call    WppTraceIndent
0x18001ac0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac15  cmp     rcx, r13
0x18001ac18  jz      short loc_18001AC46
0x18001ac1a  test    byte ptr [rcx+1Ch], 2
0x18001ac1e  jz      short loc_18001AC46
0x18001ac20  cmp     byte ptr [rcx+19h], 5
0x18001ac24  jb      short loc_18001AC46
0x18001ac26  mov     r9, cs:WPP_pszIndent
0x18001ac2d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ac34  mov     rcx, [rcx+10h]
0x18001ac38  mov     edx, 0E3h
0x18001ac3d  mov     [rsp+68h+var_48], ebx
0x18001ac41  call    WPP_SF_sd
0x18001ac46  mov     eax, ebx
0x18001ac48  add     rsp, 38h
0x18001ac4c  pop     r14
0x18001ac4e  pop     r13
0x18001ac50  pop     rdi
0x18001ac51  pop     rsi
0x18001ac52  pop     rbp
0x18001ac53  pop     rbx
0x18001ac54  retn
```
