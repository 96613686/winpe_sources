# _CReader::PowerDownTimeoutCallback_::_1_::catch$1

- ea: `0x1800327f5`
- end: `0x180032889`
- name: `_CReader::PowerDownTimeoutCallback_::_1_::catch$1`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800075d0`
- `0x180028b78`
- `0x18003261b`
- `0x1800327f5`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180032865`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180032865`

## pseudocode

```c
__int64 __fastcall CReader::PowerDownTimeoutCallback_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( *(_DWORD *)(a2 + 32) != 1460 )
    throw;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
  }
  SetThreadpoolTimer(*(PTP_TIMER *)(a2 + 96), (PFILETIME)(*(_QWORD *)(a2 + 88) + 720LL), 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800327f5  mov     [rsp+arg_8], rdx
0x1800327fa  push    rbp
0x1800327fb  sub     rsp, 20h
0x1800327ff  mov     rbp, rdx
0x180032802  cmp     dword ptr [rbp+20h], 5B4h
0x180032809  jnz     short loc_180032878
0x18003280b  mov     edx, 2
0x180032810  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032815  lea     rax, WPP_GLOBAL_Control
0x18003281c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032823  cmp     rcx, rax
0x180032826  jz      short loc_180032850
0x180032828  test    byte ptr [rcx+1Ch], 10h
0x18003282c  jz      short loc_180032850
0x18003282e  cmp     byte ptr [rcx+19h], 4
0x180032832  jb      short loc_180032850
0x180032834  mov     edx, 10h
0x180032839  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032840  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x180032847  mov     rcx, [rcx+10h]
0x18003284b  call    WPP_SF_s
0x180032850  mov     rdx, [rbp+58h]
0x180032854  add     rdx, 2D0h; pftDueTime
0x18003285b  xor     r9d, r9d; msWindowLength
0x18003285e  xor     r8d, r8d; msPeriod
0x180032861  mov     rcx, [rbp+60h]; pti
0x180032865  call    cs:__imp_SetThreadpoolTimer
0x18003286b  nop
0x18003286c  mov     rax, 0
0x180032876  jmp     short loc_180032882
0x180032878  xor     edx, edx; pThrowInfo
0x18003287a  xor     ecx, ecx; pExceptionObject
0x18003287c  call    _CxxThrowException_0
0x180032882  add     rsp, 20h
0x180032886  pop     rbp
0x180032887  retn
```
