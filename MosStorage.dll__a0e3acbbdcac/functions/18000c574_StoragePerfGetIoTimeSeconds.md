# StoragePerfGetIoTimeSeconds

- ea: `0x18000c574`
- end: `0x18000c691`
- name: `StoragePerfGetIoTimeSeconds`
- size: `285`
- prototype: `int __fastcall(unsigned int (__fastcall *)(void *, __int64, _QWORD, int *), void *, unsigned int, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c3dc`

## callees

- `0x18000c574`
- `0x18000c698`
- `0x18000c708`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c628`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000c5a8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000c5a8`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c5dc`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c5dc`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c604`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c604`

## pseudocode

```c
int __fastcall StoragePerfGetIoTimeSeconds(
        unsigned int (__fastcall *a1)(void *, __int64, _QWORD, int *),
        void *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  signed int LastError; // eax
  int v10; // r8d
  int v11; // ecx
  int Time; // eax
  int v14; // r8d
  _QWORD v15[3]; // [rsp+30h] [rbp-18h] BYREF
  int v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = 0;
  v15[0] = 0;
  if ( !SetFilePointerEx(a2, (LARGE_INTEGER)a3, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v10 = 123;
LABEL_7:
    v11 = LastError;
    return ZTraceReportOriginationNoThis(v11, "StoragePerfGetIoTimeSeconds", v10);
  }
  Time = StoragePerfGetTime(v15);
  if ( Time < 0 )
  {
    v14 = 126;
    return ZTraceReportPropagationNoThis(Time, "StoragePerfGetIoTimeSeconds", v14);
  }
  if ( !a1(a2, a5, a4, &v16) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v10 = 128;
    goto LABEL_7;
  }
  if ( v16 != a4 )
  {
    v10 = 129;
    v11 = -2147418113;
    return ZTraceReportOriginationNoThis(v11, "StoragePerfGetIoTimeSeconds", v10);
  }
  Time = StoragePerfTimeElapsed(v15[0], a6);
  if ( Time < 0 )
  {
    v14 = 131;
    return ZTraceReportPropagationNoThis(Time, "StoragePerfGetIoTimeSeconds", v14);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c574  mov     rax, rsp
0x18000c577  mov     [rax+8], rbx
0x18000c57b  mov     [rax+10h], rsi
0x18000c57f  push    rdi
0x18000c580  sub     rsp, 40h
0x18000c584  mov     rdi, rdx
0x18000c587  mov     dword ptr [rax+18h], 0
0x18000c58e  mov     edx, r8d; liDistanceToMove
0x18000c591  mov     ebx, r9d
0x18000c594  mov     rsi, rcx
0x18000c597  mov     qword ptr [rax-18h], 0
0x18000c59f  xor     r8d, r8d; lpNewFilePointer
0x18000c5a2  mov     rcx, rdi; hFile
0x18000c5a5  xor     r9d, r9d; dwMoveMethod
0x18000c5a8  call    cs:__imp_SetFilePointerEx
0x18000c5ae  test    eax, eax
0x18000c5b0  jnz     short loc_18000C5E7
0x18000c5b2  call    cs:__imp_GetLastError
0x18000c5b8  test    eax, eax
0x18000c5ba  jz      short loc_18000C5C8
0x18000c5bc  jle     short loc_18000C5CD
0x18000c5be  movzx   eax, ax
0x18000c5c1  or      eax, 80070000h
0x18000c5c6  jmp     short loc_18000C5CD
0x18000c5c8  mov     eax, 80390004h
0x18000c5cd  mov     r8d, 7Bh ; '{'
0x18000c5d3  mov     ecx, eax
0x18000c5d5  lea     rdx, aStorageperfget_3; "StoragePerfGetIoTimeSeconds"
0x18000c5dc  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c5e2  jmp     loc_18000C681
0x18000c5e7  lea     rcx, [rsp+48h+var_18]
0x18000c5ec  call    StoragePerfGetTime
0x18000c5f1  test    eax, eax
0x18000c5f3  jns     short loc_18000C60C
0x18000c5f5  mov     r8d, 7Eh ; '~'
0x18000c5fb  lea     rdx, aStorageperfget_3; "StoragePerfGetIoTimeSeconds"
0x18000c602  mov     ecx, eax
0x18000c604  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000c60a  jmp     short loc_18000C681
0x18000c60c  mov     rdx, [rsp+48h+arg_20]
0x18000c611  lea     r9, [rsp+48h+arg_10]
0x18000c616  mov     r8d, ebx
0x18000c619  mov     rcx, rdi
0x18000c61c  mov     rax, rsi
0x18000c61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c624  test    eax, eax
0x18000c626  jnz     short loc_18000C64B
0x18000c628  call    cs:__imp_GetLastError
0x18000c62e  test    eax, eax
0x18000c630  jz      short loc_18000C63E
0x18000c632  jle     short loc_18000C643
0x18000c634  movzx   eax, ax
0x18000c637  or      eax, 80070000h
0x18000c63c  jmp     short loc_18000C643
0x18000c63e  mov     eax, 80390004h
0x18000c643  mov     r8d, 80h
0x18000c649  jmp     short loc_18000C5D3
0x18000c64b  cmp     [rsp+48h+arg_10], ebx
0x18000c64f  jz      short loc_18000C661
0x18000c651  mov     r8d, 81h
0x18000c657  mov     ecx, 8000FFFFh
0x18000c65c  jmp     loc_18000C5D5
0x18000c661  mov     rdx, [rsp+48h+arg_28]
0x18000c666  mov     rcx, [rsp+48h+var_18]
0x18000c66b  call    StoragePerfTimeElapsed
0x18000c670  test    eax, eax
0x18000c672  jns     short loc_18000C67F
0x18000c674  mov     r8d, 83h
0x18000c67a  jmp     loc_18000C5FB
0x18000c67f  xor     eax, eax
0x18000c681  mov     rbx, [rsp+48h+arg_0]
0x18000c686  mov     rsi, [rsp+48h+arg_8]
0x18000c68b  add     rsp, 40h
0x18000c68f  pop     rdi
0x18000c690  retn
```
