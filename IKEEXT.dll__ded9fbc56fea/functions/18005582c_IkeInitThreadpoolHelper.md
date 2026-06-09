# IkeInitThreadpoolHelper

- ea: `0x18005582c`
- end: `0x180055933`
- name: `IkeInitThreadpoolHelper`
- size: `263`
- prototype: `__int64 __fastcall(DWORD cthrdMost, DWORD cthrdMic)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180055440`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x18005582c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005586b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005586b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005585d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005585d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180055891`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180055891`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005589c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005589c`

## string_xrefs

- `0x180055846`: `IkeInitThreadpoolHelper`
- `0x18005590c`: `IkeInitThreadpoolHelper`
- `0x180055918`: `IkeInitThreadpoolHelper`
- `0x180055871`: `CreateThreadpool`
- `0x1800558ac`: `SetThreadpoolThreadMinimum`

## pseudocode

```c
__int64 __fastcall IkeInitThreadpoolHelper(DWORD cthrdMost, DWORD cthrdMic, struct _TP_POOL **a3, __int64 a4)
{
  struct _TP_POOL *Threadpool; // rax
  struct _TP_POOL *v9; // rdi
  DWORD LastError; // eax
  __int64 v11; // rcx
  const char *v12; // rdx
  __int64 v13; // rbx
  __int128 v15; // [rsp+20h] [rbp-58h]
  __int128 v16; // [rsp+50h] [rbp-28h]
  __int64 v17; // [rsp+60h] [rbp-18h]

  DWORD1(v15) = 0;
  TraceLogHelper("IkeInitThreadpoolHelper", 1);
  Threadpool = CreateThreadpool(0);
  v9 = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMaximum(Threadpool, cthrdMost);
    if ( SetThreadpoolThreadMinimum(v9, cthrdMic) )
    {
      *a3 = v9;
      v13 = 0;
      LODWORD(v15) = 3;
      *((_QWORD *)&v15 + 1) = v9;
      *(_OWORD *)a4 = v15;
      *(_OWORD *)(a4 + 16) = 0u;
      *(_QWORD *)&v16 = 0;
      *(_OWORD *)(a4 + 32) = 0;
      *((_QWORD *)&v16 + 1) = 0x100000000LL;
      LODWORD(v17) = 72;
      *(_OWORD *)(a4 + 48) = v16;
      *(_QWORD *)(a4 + 64) = v17;
      goto LABEL_7;
    }
    LastError = GetLastError();
    v12 = "SetThreadpoolThreadMinimum";
  }
  else
  {
    LastError = GetLastError();
    v12 = "CreateThreadpool";
  }
  v13 = WfpReportSysErrorAsWinError(v11, v12, LastError, 1);
LABEL_7:
  TraceLogHelper("IkeInitThreadpoolHelper", 0);
  return IkeReturnError(v13, "IkeInitThreadpoolHelper");
}

```

## disassembly

```asm
0x18005582c  push    rbp
0x18005582e  push    rbx
0x18005582f  push    rsi
0x180055830  push    rdi
0x180055831  push    r14
0x180055833  push    r15
0x180055835  mov     rbp, rsp
0x180055838  sub     rsp, 78h
0x18005583c  xor     eax, eax
0x18005583e  mov     ebx, edx
0x180055840  mov     r14d, ecx
0x180055843  mov     dword ptr [rbp+var_58+4], eax
0x180055846  lea     rcx, aIkeinitthreadp; "IkeInitThreadpoolHelper"
0x18005584d  mov     rsi, r9
0x180055850  mov     r15, r8
0x180055853  lea     edx, [rax+1]
0x180055856  call    TraceLogHelper
0x18005585b  xor     ecx, ecx; reserved
0x18005585d  call    cs:__imp_CreateThreadpool
0x180055863  mov     rdi, rax
0x180055866  test    rax, rax
0x180055869  jnz     short loc_18005588B
0x18005586b  call    cs:__imp_GetLastError
0x180055871  lea     rdx, aCreatethreadpo_1; "CreateThreadpool"
0x180055878  mov     r9d, 1
0x18005587e  mov     r8d, eax
0x180055881  call    WfpReportSysErrorAsWinError
0x180055886  mov     rbx, rax
0x180055889  jmp     short loc_18005590A
0x18005588b  mov     edx, r14d; cthrdMost
0x18005588e  mov     rcx, rdi; ptpp
0x180055891  call    cs:__imp_SetThreadpoolThreadMaximum
0x180055897  mov     edx, ebx; cthrdMic
0x180055899  mov     rcx, rdi; ptpp
0x18005589c  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800558a2  test    eax, eax
0x1800558a4  jnz     short loc_1800558B5
0x1800558a6  call    cs:__imp_GetLastError
0x1800558ac  lea     rdx, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x1800558b3  jmp     short loc_180055878
0x1800558b5  mov     [r15], rdi
0x1800558b8  xor     ebx, ebx
0x1800558ba  mov     dword ptr [rbp+var_58], 3
0x1800558c1  xorps   xmm2, xmm2
0x1800558c4  mov     qword ptr [rbp+var_58+8], rdi
0x1800558c8  movaps  xmm0, [rbp+var_58]
0x1800558cc  movups  xmmword ptr [rsi], xmm0
0x1800558cf  mov     qword ptr [rbp+var_48], rbx
0x1800558d3  mov     qword ptr [rbp+var_48+8], rbx
0x1800558d7  movaps  xmm1, [rbp+var_48]
0x1800558db  movups  xmmword ptr [rsi+10h], xmm1
0x1800558df  mov     qword ptr [rbp+var_28], rbx
0x1800558e3  movups  xmmword ptr [rsi+20h], xmm2
0x1800558e7  mov     dword ptr [rbp+var_28+8], ebx
0x1800558ea  mov     dword ptr [rbp+var_28+0Ch], 1
0x1800558f1  movaps  xmm0, [rbp+var_28]
0x1800558f5  mov     dword ptr [rbp+var_18], 48h ; 'H'
0x1800558fc  movsd   xmm1, [rbp+var_18]
0x180055901  movups  xmmword ptr [rsi+30h], xmm0
0x180055905  movsd   qword ptr [rsi+40h], xmm1
0x18005590a  xor     edx, edx
0x18005590c  lea     rcx, aIkeinitthreadp; "IkeInitThreadpoolHelper"
0x180055913  call    TraceLogHelper
0x180055918  lea     rdx, aIkeinitthreadp; "IkeInitThreadpoolHelper"
0x18005591f  mov     rcx, rbx
0x180055922  add     rsp, 78h
0x180055926  pop     r15
0x180055928  pop     r14
0x18005592a  pop     rdi
0x18005592b  pop     rsi
0x18005592c  pop     rbx
0x18005592d  pop     rbp
0x18005592e  jmp     IkeReturnError
```
