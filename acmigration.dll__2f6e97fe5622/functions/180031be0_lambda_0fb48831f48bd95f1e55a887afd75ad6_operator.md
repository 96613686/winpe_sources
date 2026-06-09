# _lambda_0fb48831f48bd95f1e55a887afd75ad6_::operator()

- ea: `0x180031be0`
- end: `0x180031e0e`
- name: `_lambda_0fb48831f48bd95f1e55a887afd75ad6_::operator()`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180033ac4`

## callees

- `0x180031be0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180031bf6`
- `KERNEL32!GetFileAttributesW` at `0x180031bf6`
- `KERNEL32!GetLastError` at `0x180031ced`
- `KERNEL32!GetLastError` at `0x180031ced`
- `ADVAPI32!OpenTraceW` at `0x180031cd6`
- `ADVAPI32!OpenTraceW` at `0x180031cd6`
- `ADVAPI32!ProcessTrace` at `0x180031d58`
- `ADVAPI32!ProcessTrace` at `0x180031d58`

## string_xrefs

- `0x180031d10`: `OpenTraceW failed for file: %ws [0x%x]`

## pseudocode

```c
__int64 __fastcall lambda_0fb48831f48bd95f1e55a887afd75ad6_::operator()(__int64 a1)
{
  const WCHAR *v2; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v4; // rcx
  __int64 result; // rax
  ULONG64 *v6; // rcx
  const WCHAR *v7; // rax
  unsigned int *v8; // rax
  int v9; // ecx
  _QWORD *v10; // rax

  v2 = *(const WCHAR **)a1;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  FileAttributesW = GetFileAttributesW(v2);
  v4 = *(const WCHAR **)a1;
  if ( FileAttributesW == -1 )
  {
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(const WCHAR **)v4;
    AslLogCallPrintf(
      1,
      "GetETWMatch::<lambda_0fb48831f48bd95f1e55a887afd75ad6>::operator ()",
      710,
      "ETW file not found: %ws",
      v4);
    return 2147942402LL;
  }
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const WCHAR **)v4;
  **(_QWORD **)(a1 + 8) = v4;
  *(_DWORD *)(*(_QWORD *)(a1 + 8) + 28LL) = 0x10000000;
  **(_QWORD **)(a1 + 16) = *(_QWORD *)(a1 + 24);
  *(_BYTE *)(*(_QWORD *)(a1 + 16) + 8LL) = **(_BYTE **)(a1 + 32);
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) = *(_QWORD *)(a1 + 40);
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) = **(_QWORD **)(a1 + 56);
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 40LL) = **(_QWORD **)(a1 + 64);
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL) = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 440LL) = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 424LL) = ETWEventRecordCallback;
  **(_QWORD **)(a1 + 80) = OpenTraceW(*(PEVENT_TRACE_LOGFILEW *)(a1 + 8));
  v6 = *(ULONG64 **)(a1 + 80);
  if ( *v6 == -1 )
  {
    **(_DWORD **)(a1 + 88) = GetLastError();
    v7 = *(const WCHAR **)a1;
    if ( *(_QWORD *)(*(_QWORD *)a1 + 24LL) > 7u )
      v7 = *(const WCHAR **)v7;
    AslLogCallPrintf(
      1,
      "GetETWMatch::<lambda_0fb48831f48bd95f1e55a887afd75ad6>::operator ()",
      735,
      "OpenTraceW failed for file: %ws [0x%x]",
      v7,
      **(_DWORD **)(a1 + 88));
    v8 = *(unsigned int **)(a1 + 88);
    goto LABEL_13;
  }
  **(_DWORD **)(a1 + 96) = ProcessTrace(v6, 1u, 0, 0);
  v9 = **(_DWORD **)(a1 + 96);
  if ( v9 )
  {
    AslLogCallPrintf(
      1,
      "GetETWMatch::<lambda_0fb48831f48bd95f1e55a887afd75ad6>::operator ()",
      742,
      "ProcessTrace failed. [0x%x]",
      v9);
    v8 = *(unsigned int **)(a1 + 96);
LABEL_13:
    result = *v8;
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( **(_DWORD **)(a1 + 48) )
  {
    if ( **(_DWORD **)(a1 + 72) )
    {
      ***(_DWORD ***)(a1 + 104) = 1;
      AslLogCallPrintf(
        3,
        "GetETWMatch::<lambda_0fb48831f48bd95f1e55a887afd75ad6>::operator ()",
        755,
        "All conditions met.");
    }
  }
  else
  {
    v10 = *(_QWORD **)(a1 + 40);
    if ( v10[3] > 7u )
      v10 = (_QWORD *)*v10;
    AslLogCallPrintf(
      3,
      "GetETWMatch::<lambda_0fb48831f48bd95f1e55a887afd75ad6>::operator ()",
      748,
      "No events found for provider: %ws",
      v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180031be0  push    rbx
0x180031be2  sub     rsp, 30h
0x180031be6  mov     rbx, rcx
0x180031be9  mov     rcx, [rcx]
0x180031bec  cmp     qword ptr [rcx+18h], 7
0x180031bf1  jbe     short loc_180031BF6
0x180031bf3  mov     rcx, [rcx]; lpFileName
0x180031bf6  call    cs:__imp_GetFileAttributesW
0x180031bfc  mov     rcx, [rbx]
0x180031bff  cmp     eax, 0FFFFFFFFh
0x180031c02  jnz     short loc_180031C3B
0x180031c04  cmp     qword ptr [rcx+18h], 7
0x180031c09  jbe     short loc_180031C0E
0x180031c0b  mov     rcx, [rcx]
0x180031c0e  mov     [rsp+38h+var_18], rcx
0x180031c13  lea     r9, aEtwFileNotFoun; "ETW file not found: %ws"
0x180031c1a  mov     ecx, 1
0x180031c1f  lea     rdx, aGetetwmatchLam; "GetETWMatch::<lambda_0fb48831f48bd95f1e"...
0x180031c26  mov     r8d, 2C6h
0x180031c2c  call    AslLogCallPrintf
0x180031c31  mov     eax, 80070002h
0x180031c36  jmp     loc_180031E08
0x180031c3b  cmp     qword ptr [rcx+18h], 7
0x180031c40  jbe     short loc_180031C45
0x180031c42  mov     rcx, [rcx]
0x180031c45  mov     rax, [rbx+8]
0x180031c49  mov     [rax], rcx
0x180031c4c  mov     rax, [rbx+8]
0x180031c50  mov     dword ptr [rax+1Ch], 10000000h
0x180031c57  mov     rcx, [rbx+10h]
0x180031c5b  mov     rax, [rbx+18h]
0x180031c5f  mov     [rcx], rax
0x180031c62  mov     rax, [rbx+20h]
0x180031c66  mov     rcx, [rbx+10h]
0x180031c6a  mov     al, [rax]
0x180031c6c  mov     [rcx+8], al
0x180031c6f  mov     rcx, [rbx+10h]
0x180031c73  mov     rax, [rbx+28h]
0x180031c77  mov     [rcx+10h], rax
0x180031c7b  mov     rcx, [rbx+10h]
0x180031c7f  mov     rax, [rbx+30h]
0x180031c83  mov     [rcx+18h], rax
0x180031c87  mov     rax, [rbx+38h]
0x180031c8b  mov     rcx, [rbx+10h]
0x180031c8f  mov     rax, [rax]
0x180031c92  mov     [rcx+20h], rax
0x180031c96  mov     rax, [rbx+40h]
0x180031c9a  mov     rcx, [rbx+10h]
0x180031c9e  mov     rax, [rax]
0x180031ca1  mov     [rcx+28h], rax
0x180031ca5  mov     rcx, [rbx+10h]
0x180031ca9  mov     rax, [rbx+48h]
0x180031cad  mov     [rcx+30h], rax
0x180031cb1  mov     rcx, [rbx+8]
0x180031cb5  mov     rax, [rbx+10h]
0x180031cb9  mov     [rcx+1B8h], rax
0x180031cc0  lea     rcx, ?ETWEventRecordCallback@@YAXPEAU_EVENT_RECORD@@@Z; ETWEventRecordCallback(_EVENT_RECORD *)
0x180031cc7  mov     rax, [rbx+8]
0x180031ccb  mov     [rax+1A8h], rcx
0x180031cd2  mov     rcx, [rbx+8]; Logfile
0x180031cd6  call    cs:__imp_OpenTraceW
0x180031cdc  mov     rcx, [rbx+50h]
0x180031ce0  mov     [rcx], rax
0x180031ce3  mov     rcx, [rbx+50h]; HandleArray
0x180031ce7  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180031ceb  jnz     short loc_180031D4E
0x180031ced  call    cs:__imp_GetLastError
0x180031cf3  mov     rcx, [rbx+58h]
0x180031cf7  mov     [rcx], eax
0x180031cf9  mov     rax, [rbx+58h]
0x180031cfd  mov     ecx, [rax]
0x180031cff  mov     rax, [rbx]
0x180031d02  cmp     qword ptr [rax+18h], 7
0x180031d07  jbe     short loc_180031D0C
0x180031d09  mov     rax, [rax]
0x180031d0c  mov     [rsp+38h+var_10], ecx
0x180031d10  lea     r9, aOpentracewFail; "OpenTraceW failed for file: %ws [0x%x]"
0x180031d17  mov     ecx, 1
0x180031d1c  mov     [rsp+38h+var_18], rax
0x180031d21  mov     r8d, 2DFh
0x180031d27  lea     rdx, aGetetwmatchLam; "GetETWMatch::<lambda_0fb48831f48bd95f1e"...
0x180031d2e  call    AslLogCallPrintf
0x180031d33  mov     rax, [rbx+58h]
0x180031d37  mov     eax, [rax]
0x180031d39  test    eax, eax
0x180031d3b  jle     loc_180031E08
0x180031d41  movzx   eax, ax
0x180031d44  or      eax, 80070000h
0x180031d49  jmp     loc_180031E08
0x180031d4e  xor     r9d, r9d; EndTime
0x180031d51  xor     r8d, r8d; StartTime
0x180031d54  lea     edx, [r9+1]; HandleCount
0x180031d58  call    cs:__imp_ProcessTrace
0x180031d5e  mov     rcx, [rbx+60h]
0x180031d62  mov     [rcx], eax
0x180031d64  mov     rax, [rbx+60h]
0x180031d68  mov     ecx, [rax]
0x180031d6a  test    ecx, ecx
0x180031d6c  jz      short loc_180031D96
0x180031d6e  mov     dword ptr [rsp+38h+var_18], ecx
0x180031d72  lea     r9, aProcesstraceFa; "ProcessTrace failed. [0x%x]"
0x180031d79  mov     ecx, 1
0x180031d7e  lea     rdx, aGetetwmatchLam; "GetETWMatch::<lambda_0fb48831f48bd95f1e"...
0x180031d85  mov     r8d, 2E6h
0x180031d8b  call    AslLogCallPrintf
0x180031d90  mov     rax, [rbx+60h]
0x180031d94  jmp     short loc_180031D37
0x180031d96  mov     rax, [rbx+30h]
0x180031d9a  cmp     dword ptr [rax], 0
0x180031d9d  jnz     short loc_180031DD2
0x180031d9f  mov     rax, [rbx+28h]
0x180031da3  cmp     qword ptr [rax+18h], 7
0x180031da8  jbe     short loc_180031DAD
0x180031daa  mov     rax, [rax]
0x180031dad  lea     r9, aNoEventsFoundF; "No events found for provider: %ws"
0x180031db4  mov     [rsp+38h+var_18], rax
0x180031db9  mov     r8d, 2ECh
0x180031dbf  lea     rdx, aGetetwmatchLam; "GetETWMatch::<lambda_0fb48831f48bd95f1e"...
0x180031dc6  mov     ecx, 3
0x180031dcb  call    AslLogCallPrintf
0x180031dd0  jmp     short loc_180031E06
0x180031dd2  mov     rax, [rbx+48h]
0x180031dd6  cmp     dword ptr [rax], 0
0x180031dd9  jz      short loc_180031E06
0x180031ddb  mov     rax, [rbx+68h]
0x180031ddf  lea     r9, aAllConditionsM; "All conditions met."
0x180031de6  mov     r8d, 2F3h
0x180031dec  lea     rdx, aGetetwmatchLam; "GetETWMatch::<lambda_0fb48831f48bd95f1e"...
0x180031df3  mov     rcx, [rax]
0x180031df6  mov     dword ptr [rcx], 1
0x180031dfc  mov     ecx, 3
0x180031e01  call    AslLogCallPrintf
0x180031e06  xor     eax, eax
0x180031e08  add     rsp, 30h
0x180031e0c  pop     rbx
0x180031e0d  retn
```
