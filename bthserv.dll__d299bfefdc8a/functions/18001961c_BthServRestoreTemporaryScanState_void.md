# BthServRestoreTemporaryScanState(void)

- ea: `0x18001961c`
- end: `0x180019762`
- name: `?BthServRestoreTemporaryScanState@@YAKXZ`
- size: `326`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c9d8`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001961c`
- `0x180019768`
- `0x180019958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001968d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001968d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001974f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001974f`

## pseudocode

```c
__int64 BthServRestoreTemporaryScanState(void)
{
  unsigned int v0; // edi
  char v1; // bl
  bool v2; // dl
  int v3; // edx
  int v4; // r8d
  _BYTE *v5; // rcx
  bool v6; // dl
  int v8; // [rsp+20h] [rbp-58h]
  int v9; // [rsp+28h] [rbp-50h]

  v0 = 0;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  EnterCriticalSection(&stru_180044B60);
  if ( !dword_180044B88 || (v0 = BthServSetDiscoverable(1)) == 0 )
  {
    if ( dword_180044B8C )
      v0 = BthServSetConnectable(1);
    goto LABEL_19;
  }
  v5 = WPP_GLOBAL_Control;
  v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_19:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 4u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = v1;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)v5 + 2),
      v3,
      v4,
      *((_QWORD *)v5 + 5),
      v8,
      v9,
      22,
      (__int64)WPP_1e105cb0c669395e076f5c19399c2c56_Traceguids);
  }
  LeaveCriticalSection(&stru_180044B60);
  return v0;
}

```

## disassembly

```asm
0x18001961c  push    rbx
0x18001961e  push    rbp
0x18001961f  push    rsi
0x180019620  push    rdi
0x180019621  push    r14
0x180019623  sub     rsp, 50h
0x180019627  xor     edi, edi
0x180019629  mov     rcx, cs:WPP_GLOBAL_Control
0x180019630  lea     rsi, WPP_GLOBAL_Control
0x180019637  lea     ebx, [rdi+1]
0x18001963a  cmp     rcx, rsi
0x18001963d  jz      short loc_180019649
0x18001963f  cmp     byte ptr [rcx+19h], 4
0x180019643  jb      short loc_180019649
0x180019645  mov     dl, bl
0x180019647  jmp     short loc_18001964B
0x180019649  xor     dl, dl
0x18001964b  lea     rbp, WPP_RECORDER_INITIALIZED
0x180019652  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180019659  lea     r14, WPP_1e105cb0c669395e076f5c19399c2c56_Traceguids
0x180019660  setnz   r8b
0x180019664  test    dl, dl
0x180019666  jnz     short loc_18001966D
0x180019668  test    r8b, r8b
0x18001966b  jz      short loc_180019686
0x18001966d  mov     r9, [rcx+28h]
0x180019671  mov     rcx, [rcx+10h]
0x180019675  mov     [rsp+78h+var_40], r14
0x18001967a  mov     [rsp+78h+var_48], 14h
0x180019681  call    WPP_RECORDER_AND_TRACE_SF_s
0x180019686  lea     rcx, stru_180044B60; lpCriticalSection
0x18001968d  call    cs:__imp_EnterCriticalSection
0x180019693  cmp     cs:dword_180044B88, edi
0x180019699  jz      short loc_1800196EF
0x18001969b  mov     ecx, ebx; int
0x18001969d  call    ?BthServSetDiscoverable@@YAKH@Z; BthServSetDiscoverable(int)
0x1800196a2  mov     edi, eax
0x1800196a4  test    eax, eax
0x1800196a6  jz      short loc_1800196EF
0x1800196a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196af  cmp     rcx, rsi
0x1800196b2  jz      short loc_1800196BE
0x1800196b4  cmp     byte ptr [rcx+19h], 3
0x1800196b8  jb      short loc_1800196BE
0x1800196ba  mov     dl, bl
0x1800196bc  jmp     short loc_1800196C0
0x1800196be  xor     dl, dl
0x1800196c0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1800196c7  setnz   r8b
0x1800196cb  test    dl, dl
0x1800196cd  jnz     short loc_1800196D4
0x1800196cf  test    r8b, r8b
0x1800196d2  jz      short loc_180019708
0x1800196d4  mov     r9, [rcx+28h]
0x1800196d8  mov     rcx, [rcx+10h]
0x1800196dc  mov     [rsp+78h+var_40], r14
0x1800196e1  mov     [rsp+78h+var_48], 15h
0x1800196e8  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800196ed  jmp     short loc_180019701
0x1800196ef  cmp     cs:dword_180044B8C, 0
0x1800196f6  jz      short loc_180019701
0x1800196f8  mov     ecx, ebx; int
0x1800196fa  call    ?BthServSetConnectable@@YAKH@Z; BthServSetConnectable(int)
0x1800196ff  mov     edi, eax
0x180019701  mov     rcx, cs:WPP_GLOBAL_Control
0x180019708  cmp     rcx, rsi
0x18001970b  jz      short loc_180019713
0x18001970d  cmp     byte ptr [rcx+19h], 4
0x180019711  jnb     short loc_180019715
0x180019713  xor     bl, bl
0x180019715  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001971c  setnz   r8b
0x180019720  test    bl, bl
0x180019722  jnz     short loc_180019729
0x180019724  test    r8b, r8b
0x180019727  jz      short loc_180019748
0x180019729  mov     r9, [rcx+28h]
0x18001972d  mov     dl, bl
0x18001972f  mov     rcx, [rcx+10h]
0x180019733  mov     [rsp+78h+var_30], edi
0x180019737  mov     [rsp+78h+var_40], r14
0x18001973c  mov     [rsp+78h+var_48], 16h
0x180019743  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180019748  lea     rcx, stru_180044B60; lpCriticalSection
0x18001974f  call    cs:__imp_LeaveCriticalSection
0x180019755  mov     eax, edi
0x180019757  add     rsp, 50h
0x18001975b  pop     r14
0x18001975d  pop     rdi
0x18001975e  pop     rsi
0x18001975f  pop     rbp
0x180019760  pop     rbx
0x180019761  retn
```
