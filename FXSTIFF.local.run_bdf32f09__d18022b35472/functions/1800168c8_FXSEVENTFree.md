# FXSEVENTFree

- ea: `0x1800168c8`
- end: `0x180016a02`
- name: `FXSEVENTFree`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e7e4`

## callees

- `0x180009a7c`
- `0x180009aa4`
- `0x18000eac0`
- `0x1800168c8`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x1800169e6`
- `KERNEL32!HeapDestroy` at `0x1800169e6`
- `KERNEL32!GetProcessHeap` at `0x1800169d4`
- `KERNEL32!GetProcessHeap` at `0x1800169d4`
- `KERNEL32!DeleteCriticalSection` at `0x180016973`
- `KERNEL32!DeleteCriticalSection` at `0x180016973`
- `KERNEL32!GetLastError` at `0x180016933`
- `KERNEL32!GetLastError` at `0x180016933`
- `ADVAPI32!DeregisterEventSource` at `0x180016913`
- `ADVAPI32!DeregisterEventSource` at `0x180016913`

## pseudocode

```c
int FXSEVENTFree()
{
  DWORD LastError; // eax
  unsigned int i; // ebx
  HANDLE ProcessHeap; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
  }
  if ( hEventLog )
  {
    if ( !DeregisterEventSource(hEventLog)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids, LastError);
    }
    hEventLog = 0;
  }
  if ( byte_180070CD8 )
  {
    DeleteCriticalSection(&stru_180070928);
    byte_180070CD8 = 0;
  }
  for ( i = 0; i < dword_180070958; ++i )
    pMemFree(*((LPVOID *)gs_pFaxCategory + 2 * i));
  LODWORD(ProcessHeap) = pMemFree(gs_pFaxCategory);
  gs_pFaxCategory = 0;
  dword_180070958 = 0;
  if ( hHeap )
  {
    ProcessHeap = GetProcessHeap();
    if ( hHeap != ProcessHeap )
      LODWORD(ProcessHeap) = HeapDestroy(hHeap);
    hHeap = 0;
  }
  return (int)ProcessHeap;
}

```

## disassembly

```asm
0x1800168c8  mov     [rsp+arg_0], rbx
0x1800168cd  push    rsi
0x1800168ce  sub     rsp, 20h
0x1800168d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168d9  lea     rsi, WPP_GLOBAL_Control
0x1800168e0  mov     bl, 2
0x1800168e2  cmp     rcx, rsi
0x1800168e5  jz      short loc_180016907
0x1800168e7  test    [rcx+1Ch], bl
0x1800168ea  jz      short loc_180016907
0x1800168ec  cmp     byte ptr [rcx+19h], 5
0x1800168f0  jb      short loc_180016907
0x1800168f2  mov     rcx, [rcx+10h]
0x1800168f6  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x1800168fd  mov     edx, 0Ah
0x180016902  call    WPP_SF_
0x180016907  mov     rcx, cs:hEventLog; hEventLog
0x18001690e  test    rcx, rcx
0x180016911  jz      short loc_180016963
0x180016913  call    cs:__imp_DeregisterEventSource
0x180016919  test    eax, eax
0x18001691b  jnz     short loc_180016958
0x18001691d  mov     rax, cs:WPP_GLOBAL_Control
0x180016924  cmp     rax, rsi
0x180016927  jz      short loc_180016958
0x180016929  test    [rax+1Ch], bl
0x18001692c  jz      short loc_180016958
0x18001692e  cmp     [rax+19h], bl
0x180016931  jb      short loc_180016958
0x180016933  call    cs:__imp_GetLastError
0x180016939  mov     rcx, cs:WPP_GLOBAL_Control
0x180016940  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x180016947  mov     edx, 0Bh
0x18001694c  mov     r9d, eax
0x18001694f  mov     rcx, [rcx+10h]
0x180016953  call    WPP_SF_d
0x180016958  mov     cs:hEventLog, 0
0x180016963  cmp     cs:byte_180070CD8, 0
0x18001696a  jz      short loc_180016980
0x18001696c  lea     rcx, stru_180070928; lpCriticalSection
0x180016973  call    cs:__imp_DeleteCriticalSection
0x180016979  mov     cs:byte_180070CD8, 0
0x180016980  xor     ebx, ebx
0x180016982  cmp     cs:dword_180070958, ebx
0x180016988  jbe     short loc_1800169A9
0x18001698a  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x180016991  mov     eax, ebx
0x180016993  add     rax, rax
0x180016996  mov     rcx, [rcx+rax*8]; lpMem
0x18001699a  call    pMemFree
0x18001699f  inc     ebx
0x1800169a1  cmp     ebx, cs:dword_180070958
0x1800169a7  jb      short loc_18001698A
0x1800169a9  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; lpMem
0x1800169b0  call    pMemFree
0x1800169b5  cmp     cs:hHeap, 0
0x1800169bd  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, 0; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x1800169c8  mov     cs:dword_180070958, 0
0x1800169d2  jz      short loc_1800169F7
0x1800169d4  call    cs:__imp_GetProcessHeap
0x1800169da  mov     rcx, cs:hHeap; hHeap
0x1800169e1  cmp     rcx, rax
0x1800169e4  jz      short loc_1800169EC
0x1800169e6  call    cs:__imp_HeapDestroy
0x1800169ec  mov     cs:hHeap, 0
0x1800169f7  mov     rbx, [rsp+28h+arg_0]
0x1800169fc  add     rsp, 20h
0x180016a00  pop     rsi
0x180016a01  retn
```
