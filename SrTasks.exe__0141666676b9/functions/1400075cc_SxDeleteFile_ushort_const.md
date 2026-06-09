# SxDeleteFile(ushort const *)

- ea: `0x1400075cc`
- end: `0x140007714`
- name: `?SxDeleteFile@@YAJPEBG@Z`
- size: `328`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140003dc4`

## callees

- `0x140002e1c`
- `0x1400054f4`
- `0x140006cc8`
- `0x1400074d8`
- `0x1400075cc`
- `0x14000771c`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140007665`
- `KERNEL32!DeleteFileW` at `0x1400076bb`
- `KERNEL32!DeleteFileW` at `0x140007665`
- `KERNEL32!DeleteFileW` at `0x1400076bb`
- `KERNEL32!GetLastError` at `0x14000767f`
- `KERNEL32!GetLastError` at `0x14000767f`

## string_xrefs

- `0x140007618`: `SxDeleteFile`

## pseudocode

```c
__int64 __fastcall SxDeleteFile(LPCWSTR lpFileName)
{
  __int16 v2; // ax
  int LastFailureAsHRESULT; // ebx
  __int16 v4; // ax
  unsigned int v5; // edx
  int v7; // [rsp+20h] [rbp-40h] BYREF
  __int16 v8; // [rsp+24h] [rbp-3Ch]
  __int16 v9; // [rsp+26h] [rbp-3Ah]
  unsigned int v10; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "SxDeleteFile", 0x51Fu, 1u);
  v10 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
  if ( DeleteFileW(lpFileName) )
  {
    v2 = 1319;
LABEL_9:
    LastFailureAsHRESULT = 0;
    v8 = v2;
    v7 = 0;
    goto LABEL_19;
  }
  if ( GetLastError() == 2 )
  {
    v2 = 1323;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = SxClearDifficultAttributes(lpFileName, &v10);
  v7 = LastFailureAsHRESULT;
  v4 = 1329;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_13;
  v8 = 1329;
  if ( !DeleteFileW(lpFileName) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v7 = LastFailureAsHRESULT;
    v4 = 1334;
LABEL_13:
    v5 = v10;
    v9 = v4;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = 0;
  v7 = 0;
  v5 = -1;
  v8 = 1334;
LABEL_17:
  if ( v5 != -1 )
  {
    SxSetFileAttributes(lpFileName, v5);
    LastFailureAsHRESULT = v7;
  }
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1400075cc  mov     [rsp-8+arg_0], rbx
0x1400075d1  mov     [rsp-8+arg_10], rdi
0x1400075d6  push    rbp
0x1400075d7  mov     rbp, rsp
0x1400075da  sub     rsp, 60h
0x1400075de  mov     rdi, rcx
0x1400075e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075e8  lea     rbx, WPP_GLOBAL_Control
0x1400075ef  cmp     rcx, rbx
0x1400075f2  jz      short loc_140007612
0x1400075f4  test    dword ptr [rcx+1Ch], 20000000h
0x1400075fb  jz      short loc_140007612
0x1400075fd  mov     rcx, [rcx+10h]
0x140007601  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x140007608  mov     edx, 29h ; ')'
0x14000760d  call    WPP_SF_
0x140007612  mov     r9d, 1; unsigned __int16
0x140007618  lea     rdx, aSxdeletefile; "SxDeleteFile"
0x14000761f  mov     r8d, 51Fh; unsigned __int16
0x140007625  lea     rcx, [rbp+var_40]; this
0x140007629  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000762e  mov     [rbp+arg_8], 0FFFFFFFFh
0x140007635  mov     rcx, cs:WPP_GLOBAL_Control
0x14000763c  cmp     rcx, rbx
0x14000763f  jz      short loc_140007662
0x140007641  test    dword ptr [rcx+1Ch], 10000000h
0x140007648  jz      short loc_140007662
0x14000764a  mov     rcx, [rcx+10h]
0x14000764e  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x140007655  mov     edx, 2Ah ; '*'
0x14000765a  mov     r9, rdi
0x14000765d  call    WPP_SF_S
0x140007662  mov     rcx, rdi; lpFileName
0x140007665  call    cs:__imp_DeleteFileW
0x14000766b  test    eax, eax
0x14000766d  jz      short loc_14000767F
0x14000766f  mov     eax, 527h
0x140007674  xor     ebx, ebx
0x140007676  mov     [rbp+var_3C], ax
0x14000767a  mov     [rbp+var_40], ebx
0x14000767d  jmp     short loc_1400076F7
0x14000767f  call    cs:__imp_GetLastError
0x140007685  cmp     eax, 2
0x140007688  jnz     short loc_140007691
0x14000768a  mov     eax, 52Bh
0x14000768f  jmp     short loc_140007674
0x140007691  lea     rdx, [rbp+arg_8]; unsigned int *
0x140007695  mov     rcx, rdi; lpFileName
0x140007698  call    ?SxClearDifficultAttributes@@YAJPEBGPEAK@Z; SxClearDifficultAttributes(ushort const *,ulong *)
0x14000769d  mov     ebx, eax
0x14000769f  mov     [rbp+var_40], eax
0x1400076a2  test    eax, eax
0x1400076a4  mov     eax, 531h
0x1400076a9  jns     short loc_1400076B4
0x1400076ab  mov     edx, [rbp+arg_8]
0x1400076ae  mov     [rbp+var_3A], ax
0x1400076b2  jmp     short loc_1400076E7
0x1400076b4  mov     rcx, rdi; lpFileName
0x1400076b7  mov     [rbp+var_3C], ax
0x1400076bb  call    cs:__imp_DeleteFileW
0x1400076c1  test    eax, eax
0x1400076c3  jnz     short loc_1400076D6
0x1400076c5  call    GetLastFailureAsHRESULT
0x1400076ca  mov     ebx, eax
0x1400076cc  mov     [rbp+var_40], eax
0x1400076cf  mov     eax, 536h
0x1400076d4  jmp     short loc_1400076AB
0x1400076d6  xor     ebx, ebx
0x1400076d8  mov     eax, 536h
0x1400076dd  mov     [rbp+var_40], ebx
0x1400076e0  or      edx, 0FFFFFFFFh; unsigned int
0x1400076e3  mov     [rbp+var_3C], ax
0x1400076e7  cmp     edx, 0FFFFFFFFh
0x1400076ea  jz      short loc_1400076F7
0x1400076ec  mov     rcx, rdi; lpFileName
0x1400076ef  call    ?SxSetFileAttributes@@YAJPEBGK@Z; SxSetFileAttributes(ushort const *,ulong)
0x1400076f4  mov     ebx, [rbp+var_40]
0x1400076f7  lea     rcx, [rbp+var_40]; this
0x1400076fb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140007700  lea     r11, [rsp+60h+var_s0]
0x140007705  mov     eax, ebx
0x140007707  mov     rbx, [r11+10h]
0x14000770b  mov     rdi, [r11+20h]
0x14000770f  mov     rsp, r11
0x140007712  pop     rbp
0x140007713  retn
```
