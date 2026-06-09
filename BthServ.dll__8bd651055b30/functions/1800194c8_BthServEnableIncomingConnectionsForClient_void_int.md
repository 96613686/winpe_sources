# BthServEnableIncomingConnectionsForClient(void *,int)

- ea: `0x1800194c8`
- end: `0x180019616`
- name: `?BthServEnableIncomingConnectionsForClient@@YAKPEAXH@Z`
- size: `334`
- prototype: `unsigned int __fastcall(void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011dec`
- `0x180012530`

## callees

- `0x180011194`
- `0x1800194c8`
- `0x180019768`
- `0x180019c14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001953c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001953c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019603`

## pseudocode

```c
__int64 __fastcall BthServEnableIncomingConnectionsForClient(_DWORD *a1, int a2)
{
  int v2; // ebx
  char v4; // di
  int v5; // edx
  int v6; // r8d
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  int v13; // [rsp+28h] [rbp-60h]

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sql(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  EnterCriticalSection(&stru_180044B60);
  v7 = a1[24];
  if ( v2 )
  {
    if ( !v7 )
    {
      v10 = dword_180044B8C;
      v9 = 0;
      if ( !dword_180044B8C )
      {
        v9 = BthServSetConnectable(1);
        if ( v9 )
          goto LABEL_19;
        v10 = dword_180044B8C;
      }
      dword_180044B8C = v10 + 1;
      ++a1[24];
      goto LABEL_19;
    }
    goto LABEL_14;
  }
  if ( !v7 )
  {
LABEL_14:
    v9 = 87;
    goto LABEL_19;
  }
  v8 = dword_180044B8C;
  if ( dword_180044B8C == 1 )
  {
    BthServSetConnectable(0);
    v8 = dword_180044B8C;
  }
  dword_180044B8C = v8 - 1;
  --a1[24];
  v9 = 0;
LABEL_19:
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = v4;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v12,
      v13,
      19,
      (__int64)WPP_1e105cb0c669395e076f5c19399c2c56_Traceguids);
  }
  LeaveCriticalSection(&stru_180044B60);
  return v9;
}

```

## disassembly

```asm
0x1800194c8  push    rbx
0x1800194ca  push    rbp
0x1800194cb  push    rsi
0x1800194cc  push    rdi
0x1800194cd  push    r14
0x1800194cf  sub     rsp, 60h
0x1800194d3  mov     ebx, edx
0x1800194d5  mov     rsi, rcx
0x1800194d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194df  lea     rbp, WPP_GLOBAL_Control
0x1800194e6  mov     edi, 1
0x1800194eb  cmp     rcx, rbp
0x1800194ee  jz      short loc_1800194FB
0x1800194f0  cmp     byte ptr [rcx+19h], 4
0x1800194f4  jb      short loc_1800194FB
0x1800194f6  mov     dl, dil
0x1800194f9  jmp     short loc_1800194FD
0x1800194fb  xor     dl, dl
0x1800194fd  lea     r14, WPP_RECORDER_INITIALIZED
0x180019504  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001950b  setnz   r8b
0x18001950f  test    dl, dl
0x180019511  jnz     short loc_180019518
0x180019513  test    r8b, r8b
0x180019516  jz      short loc_180019535
0x180019518  mov     r9, [rcx+28h]
0x18001951c  mov     rcx, [rcx+10h]
0x180019520  mov     [rsp+88h+var_38], ebx
0x180019524  mov     [rsp+88h+var_40], rsi
0x180019529  mov     [rsp+88h+var_58], 12h
0x180019530  call    WPP_RECORDER_AND_TRACE_SF_sql
0x180019535  lea     rcx, stru_180044B60; lpCriticalSection
0x18001953c  call    cs:__imp_EnterCriticalSection
0x180019542  mov     eax, [rsi+60h]
0x180019545  test    ebx, ebx
0x180019547  jnz     short loc_180019576
0x180019549  test    eax, eax
0x18001954b  jz      short loc_18001957A
0x18001954d  mov     eax, cs:dword_180044B8C
0x180019553  cmp     eax, edi
0x180019555  jnz     short loc_180019564
0x180019557  xor     ecx, ecx; int
0x180019559  call    ?BthServSetConnectable@@YAKH@Z; BthServSetConnectable(int)
0x18001955e  mov     eax, cs:dword_180044B8C
0x180019564  or      ecx, 0FFFFFFFFh
0x180019567  add     eax, ecx
0x180019569  mov     cs:dword_180044B8C, eax
0x18001956f  add     [rsi+60h], ecx
0x180019572  xor     ebx, ebx
0x180019574  jmp     short loc_1800195AB
0x180019576  test    eax, eax
0x180019578  jz      short loc_180019581
0x18001957a  mov     ebx, 57h ; 'W'
0x18001957f  jmp     short loc_1800195AB
0x180019581  mov     eax, cs:dword_180044B8C
0x180019587  xor     ebx, ebx
0x180019589  test    eax, eax
0x18001958b  jnz     short loc_1800195A0
0x18001958d  mov     ecx, edi; int
0x18001958f  call    ?BthServSetConnectable@@YAKH@Z; BthServSetConnectable(int)
0x180019594  mov     ebx, eax
0x180019596  test    eax, eax
0x180019598  jnz     short loc_1800195AB
0x18001959a  mov     eax, cs:dword_180044B8C
0x1800195a0  add     eax, edi
0x1800195a2  mov     cs:dword_180044B8C, eax
0x1800195a8  add     [rsi+60h], edi
0x1800195ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195b2  cmp     rcx, rbp
0x1800195b5  jz      short loc_1800195BD
0x1800195b7  cmp     byte ptr [rcx+19h], 4
0x1800195bb  jnb     short loc_1800195C0
0x1800195bd  xor     dil, dil
0x1800195c0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800195c7  setnz   r8b
0x1800195cb  test    dil, dil
0x1800195ce  jnz     short loc_1800195D5
0x1800195d0  test    r8b, r8b
0x1800195d3  jz      short loc_1800195FC
0x1800195d5  mov     r9, [rcx+28h]
0x1800195d9  lea     rax, WPP_1e105cb0c669395e076f5c19399c2c56_Traceguids
0x1800195e0  mov     rcx, [rcx+10h]
0x1800195e4  mov     dl, dil
0x1800195e7  mov     dword ptr [rsp+88h+var_40], ebx
0x1800195eb  mov     [rsp+88h+var_50], rax
0x1800195f0  mov     [rsp+88h+var_58], 13h
0x1800195f7  call    WPP_RECORDER_AND_TRACE_SF_sd
0x1800195fc  lea     rcx, stru_180044B60; lpCriticalSection
0x180019603  call    cs:__imp_LeaveCriticalSection
0x180019609  mov     eax, ebx
0x18001960b  add     rsp, 60h
0x18001960f  pop     r14
0x180019611  pop     rdi
0x180019612  pop     rsi
0x180019613  pop     rbp
0x180019614  pop     rbx
0x180019615  retn
```
