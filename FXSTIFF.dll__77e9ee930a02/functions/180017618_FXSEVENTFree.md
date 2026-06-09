# FXSEVENTFree

- ea: `0x180017618`
- end: `0x18001773b`
- name: `FXSEVENTFree`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ee54`

## callees

- `0x180009f04`
- `0x180009f34`
- `0x18000f08c`
- `0x18000f1c8`
- `0x180017618`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800176cf`
- `KERNEL32!DeleteCriticalSection` at `0x1800176cf`
- `KERNEL32!GetLastError` at `0x180017689`
- `KERNEL32!GetLastError` at `0x180017689`
- `ADVAPI32!DeregisterEventSource` at `0x180017663`
- `ADVAPI32!DeregisterEventSource` at `0x180017663`

## pseudocode

```c
__int64 FXSEVENTFree()
{
  DWORD LastError; // eax
  unsigned int i; // ebx

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
  if ( byte_180071CF8 )
  {
    DeleteCriticalSection(&stru_180071930);
    byte_180071CF8 = 0;
  }
  for ( i = 0; i < dword_180071960; ++i )
    pMemFree(*((LPVOID *)gs_pFaxCategory + 2 * i));
  pMemFree(gs_pFaxCategory);
  gs_pFaxCategory = 0;
  dword_180071960 = 0;
  return HeapCleanup();
}

```

## disassembly

```asm
0x180017618  mov     [rsp+arg_0], rbx
0x18001761d  push    rsi
0x18001761e  sub     rsp, 20h
0x180017622  mov     rcx, cs:WPP_GLOBAL_Control
0x180017629  lea     rsi, WPP_GLOBAL_Control
0x180017630  mov     bl, 2
0x180017632  cmp     rcx, rsi
0x180017635  jz      short loc_180017657
0x180017637  test    [rcx+1Ch], bl
0x18001763a  jz      short loc_180017657
0x18001763c  cmp     byte ptr [rcx+19h], 5
0x180017640  jb      short loc_180017657
0x180017642  mov     rcx, [rcx+10h]
0x180017646  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x18001764d  mov     edx, 0Ah
0x180017652  call    WPP_SF_
0x180017657  mov     rcx, cs:hEventLog; hEventLog
0x18001765e  test    rcx, rcx
0x180017661  jz      short loc_1800176BF
0x180017663  call    cs:__imp_DeregisterEventSource
0x18001766a  nop     dword ptr [rax+rax+00h]
0x18001766f  test    eax, eax
0x180017671  jnz     short loc_1800176B4
0x180017673  mov     rax, cs:WPP_GLOBAL_Control
0x18001767a  cmp     rax, rsi
0x18001767d  jz      short loc_1800176B4
0x18001767f  test    [rax+1Ch], bl
0x180017682  jz      short loc_1800176B4
0x180017684  cmp     [rax+19h], bl
0x180017687  jb      short loc_1800176B4
0x180017689  call    cs:__imp_GetLastError
0x180017690  nop     dword ptr [rax+rax+00h]
0x180017695  mov     rcx, cs:WPP_GLOBAL_Control
0x18001769c  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x1800176a3  mov     edx, 0Bh
0x1800176a8  mov     r9d, eax
0x1800176ab  mov     rcx, [rcx+10h]
0x1800176af  call    WPP_SF_d
0x1800176b4  mov     cs:hEventLog, 0
0x1800176bf  cmp     cs:byte_180071CF8, 0
0x1800176c6  jz      short loc_1800176E2
0x1800176c8  lea     rcx, stru_180071930; lpCriticalSection
0x1800176cf  call    cs:__imp_DeleteCriticalSection
0x1800176d6  nop     dword ptr [rax+rax+00h]
0x1800176db  mov     cs:byte_180071CF8, 0
0x1800176e2  xor     ebx, ebx
0x1800176e4  cmp     cs:dword_180071960, ebx
0x1800176ea  jbe     short loc_18001770B
0x1800176ec  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x1800176f3  mov     eax, ebx
0x1800176f5  add     rax, rax
0x1800176f8  mov     rcx, [rcx+rax*8]; lpMem
0x1800176fc  call    pMemFree
0x180017701  inc     ebx
0x180017703  cmp     ebx, cs:dword_180071960
0x180017709  jb      short loc_1800176EC
0x18001770b  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; lpMem
0x180017712  call    pMemFree
0x180017717  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, 0; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x180017722  mov     cs:dword_180071960, 0
0x18001772c  mov     rbx, [rsp+28h+arg_0]
0x180017731  add     rsp, 20h
0x180017735  pop     rsi
0x180017736  jmp     HeapCleanup
```
