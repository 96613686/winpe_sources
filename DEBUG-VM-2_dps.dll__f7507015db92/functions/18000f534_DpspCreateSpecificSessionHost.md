# DpspCreateSpecificSessionHost

- ea: `0x18000f534`
- end: `0x18000f716`
- name: `DpspCreateSpecificSessionHost`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003020`
- `0x180006d08`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180008f10`
- `0x180009090`
- `0x18000a856`
- `0x18000f534`
- `0x180017818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6b4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f636`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f636`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f674`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f674`

## string_xrefs

- `0x18000f570`: `DpspCreateSpecificSessionHost`
- `0x18000f6e1`: `DpspCreateSpecificSessionHost`

## pseudocode

```c
__int64 __fastcall DpspCreateSpecificSessionHost(signed __int64 *a1, void *a2, int a3, int a4)
{
  signed __int64 v4; // rdi
  int v9; // r8d
  unsigned int v10; // ebx
  void *v11; // rax
  signed __int64 v12; // rax
  int Args; // eax
  PSID *v14; // rsi
  int v15; // r8d
  size_t LengthSid; // rbx
  void *v17; // rax
  signed __int64 v18; // rax
  signed int LastError; // eax

  v4 = 0;
  if ( !a1 )
  {
    v9 = 1931;
LABEL_3:
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"DpspCreateSpecificSessionHost",
      v9,
      (int)L"Error = %d",
      87);
    goto LABEL_23;
  }
  if ( !a2 )
  {
    v9 = 1932;
    goto LABEL_3;
  }
  v11 = (void *)WdipAlloc(144);
  v4 = (signed __int64)v11;
  if ( !v11 )
  {
    v10 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"DpspCreateSpecificSessionHost",
      1935,
      (int)L"Error = %d",
      14);
LABEL_23:
    WdipFree(v4);
    return v10;
  }
  memset_0(v11, 0, 0x90u);
  *(_DWORD *)(v4 + 52) = 4 * g_ulQueueSize;
  *(_DWORD *)(v4 + 40) = a3;
  *(_DWORD *)(v4 + 120) = a4;
  *(_DWORD *)(v4 + 44) = 0;
  v12 = _InterlockedExchangeAdd64(&g_ulConnectionId, 4u);
  *(_DWORD *)(v4 + 112) = 0;
  *(_QWORD *)(v4 + 8) = (v12 + 4) | 2;
  *(_QWORD *)(v4 + 24) = v4 + 16;
  *(_QWORD *)(v4 + 16) = v4 + 16;
  Args = WdipInitializeCriticalSection(v4 + 72);
  v14 = (PSID *)(v4 + 32);
  v10 = Args;
  if ( Args < 0 )
  {
    v15 = 1950;
LABEL_22:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (int)L"DpspCreateSpecificSessionHost",
      v15,
      (int)L"Error = %d",
      Args);
    WdipDeleteCriticalSection(v4 + 72);
    WdipFree(*v14);
    *v14 = 0;
    goto LABEL_23;
  }
  LengthSid = GetLengthSid(a2);
  v17 = (void *)WdipAlloc(LengthSid);
  *v14 = v17;
  if ( !v17 )
  {
    v10 = -2147024882;
    v15 = 1954;
    LOBYTE(Args) = 14;
    goto LABEL_22;
  }
  memset_0(v17, 0, LengthSid);
  if ( CopySid(LengthSid, *v14, a2) )
  {
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (v10 & 0x80000000) != 0 )
    {
      v15 = 1961;
      LOBYTE(Args) = v10;
      goto LABEL_22;
    }
  }
  v18 = g_pHostHead;
  *a1 = v4;
  do
  {
    *(_QWORD *)(v4 + 136) = v18;
    v18 = _InterlockedCompareExchange64(&g_pHostHead, v4, v18);
  }
  while ( v18 != *(_QWORD *)(v4 + 136) );
  return v10;
}

```

## disassembly

```asm
0x18000f534  push    rbx
0x18000f536  push    rbp
0x18000f537  push    rsi
0x18000f538  push    rdi
0x18000f539  push    r13
0x18000f53b  push    r14
0x18000f53d  push    r15
0x18000f53f  sub     rsp, 30h
0x18000f543  xor     edi, edi
0x18000f545  mov     ebx, r9d
0x18000f548  mov     esi, r8d
0x18000f54b  mov     rbp, rdx
0x18000f54e  mov     r14, rcx
0x18000f551  test    rcx, rcx
0x18000f554  jnz     short loc_18000F588
0x18000f556  mov     r8d, 78Bh; int
0x18000f55c  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000f564  mov     ebx, 80070057h
0x18000f569  lea     r9, aErrorD; "Error = %d"
0x18000f570  lea     rdx, aDpspcreatespec; "DpspCreateSpecificSessionHost"
0x18000f577  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f57e  call    WdipTraceError
0x18000f583  jmp     loc_18000F70C
0x18000f588  test    rbp, rbp
0x18000f58b  jnz     short loc_18000F595
0x18000f58d  mov     r8d, 78Ch
0x18000f593  jmp     short loc_18000F55C
0x18000f595  mov     r15d, 90h
0x18000f59b  mov     ecx, r15d
0x18000f59e  call    WdipAlloc
0x18000f5a3  mov     rdi, rax
0x18000f5a6  test    rax, rax
0x18000f5a9  jnz     short loc_18000F5C0
0x18000f5ab  mov     ebx, 8007000Eh
0x18000f5b0  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000f5b8  mov     r8d, 78Fh
0x18000f5be  jmp     short loc_18000F569
0x18000f5c0  mov     r8, r15; Size
0x18000f5c3  xor     edx, edx; Val
0x18000f5c5  mov     rcx, rdi; void *
0x18000f5c8  call    memset_0
0x18000f5cd  mov     eax, cs:?g_ulQueueSize@@3KA; ulong g_ulQueueSize
0x18000f5d3  shl     eax, 2
0x18000f5d6  mov     [rdi+34h], eax
0x18000f5d9  mov     eax, 4
0x18000f5de  mov     [rdi+28h], esi
0x18000f5e1  mov     [rdi+78h], ebx
0x18000f5e4  mov     dword ptr [rdi+2Ch], 0
0x18000f5eb  lock xadd cs:g_ulConnectionId, rax
0x18000f5f4  add     rax, 4
0x18000f5f8  mov     dword ptr [rdi+70h], 0
0x18000f5ff  or      rax, 2
0x18000f603  lea     rcx, [rdi+48h]
0x18000f607  mov     [rdi+8], rax
0x18000f60b  lea     rax, [rdi+10h]
0x18000f60f  mov     [rax+8], rax
0x18000f613  mov     [rax], rax
0x18000f616  call    WdipInitializeCriticalSection
0x18000f61b  lea     rsi, [rdi+20h]
0x18000f61f  mov     ebx, eax
0x18000f621  test    eax, eax
0x18000f623  jns     short loc_18000F633
0x18000f625  mov     r8d, 79Eh
0x18000f62b  movzx   eax, ax
0x18000f62e  jmp     loc_18000F6D6
0x18000f633  mov     rcx, rbp; pSid
0x18000f636  call    cs:__imp_GetLengthSid
0x18000f63c  mov     ecx, eax
0x18000f63e  mov     ebx, eax
0x18000f640  call    WdipAlloc
0x18000f645  mov     [rsi], rax
0x18000f648  test    rax, rax
0x18000f64b  jnz     short loc_18000F65F
0x18000f64d  mov     ebx, 8007000Eh
0x18000f652  mov     r8d, 7A2h
0x18000f658  mov     eax, 0Eh
0x18000f65d  jmp     short loc_18000F6D6
0x18000f65f  mov     r8, rbx; Size
0x18000f662  xor     edx, edx; Val
0x18000f664  mov     rcx, rax; void *
0x18000f667  call    memset_0
0x18000f66c  mov     rdx, [rsi]; pDestinationSid
0x18000f66f  mov     r8, rbp; pSourceSid
0x18000f672  mov     ecx, ebx; nDestinationSidLength
0x18000f674  call    cs:__imp_CopySid
0x18000f67a  test    eax, eax
0x18000f67c  jz      short loc_18000F6B4
0x18000f67e  xor     ebx, ebx
0x18000f680  mov     rax, cs:g_pHostHead
0x18000f687  mov     [r14], rdi
0x18000f68a  mov     [rdi+88h], rax
0x18000f691  lock cmpxchg cs:g_pHostHead, rdi
0x18000f69a  cmp     rax, [rdi+88h]
0x18000f6a1  jnz     short loc_18000F68A
0x18000f6a3  mov     eax, ebx
0x18000f6a5  add     rsp, 30h
0x18000f6a9  pop     r15
0x18000f6ab  pop     r14
0x18000f6ad  pop     r13
0x18000f6af  pop     rdi
0x18000f6b0  pop     rsi
0x18000f6b1  pop     rbp
0x18000f6b2  pop     rbx
0x18000f6b3  retn
0x18000f6b4  call    cs:__imp_GetLastError
0x18000f6ba  mov     ebx, eax
0x18000f6bc  test    eax, eax
0x18000f6be  jle     short loc_18000F6C9
0x18000f6c0  movzx   ebx, ax
0x18000f6c3  or      ebx, 80070000h
0x18000f6c9  test    ebx, ebx
0x18000f6cb  jns     short loc_18000F680
0x18000f6cd  mov     r8d, 7A9h; int
0x18000f6d3  movzx   eax, bx
0x18000f6d6  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f6dd  mov     dword ptr [rsp+68h+Args], eax; Args
0x18000f6e1  lea     rdx, aDpspcreatespec; "DpspCreateSpecificSessionHost"
0x18000f6e8  lea     r9, aErrorD; "Error = %d"
0x18000f6ef  call    WdipTraceError
0x18000f6f4  lea     rcx, [rdi+48h]
0x18000f6f8  call    WdipDeleteCriticalSection
0x18000f6fd  mov     rcx, [rsi]
0x18000f700  call    WdipFree
0x18000f705  mov     qword ptr [rsi], 0
0x18000f70c  mov     rcx, rdi
0x18000f70f  call    WdipFree
0x18000f714  jmp     short loc_18000F6A3
```
