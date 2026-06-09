# WdsCopyFileEx

- ea: `0x1400246b4`
- end: `0x140024937`
- name: `WdsCopyFileEx`
- size: `643`
- prototype: `__int64(unsigned __int16 *, unsigned __int16 *, DWORD (__stdcall *)(LARGE_INTEGER TotalFileSize, LARGE_INTEGER TotalBytesTransferred, LARGE_INTEGER StreamSize, LARGE_INTEGER StreamBytesTransferred, DWORD dwStreamNumber, DWORD dwCallbackReason, HANDLE hSourceFile, HANDLE hDestinationFile, LPVOID lpData), void *, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x140023c8c`

## callees

- `0x140022960`
- `0x140022c14`
- `0x140023dcc`
- `0x1400246b4`
- `0x140024940`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400248eb`
- `KERNEL32!HeapFree` at `0x140024910`
- `KERNEL32!HeapFree` at `0x1400248eb`
- `KERNEL32!HeapFree` at `0x140024910`
- `KERNEL32!GetProcessHeap` at `0x1400248d7`
- `KERNEL32!GetProcessHeap` at `0x1400248fc`
- `KERNEL32!GetProcessHeap` at `0x1400248d7`
- `KERNEL32!GetProcessHeap` at `0x1400248fc`
- `KERNEL32!CopyFileExW` at `0x140024766`
- `KERNEL32!CopyFileExW` at `0x140024766`
- `KERNEL32!GetLastError` at `0x140024785`
- `KERNEL32!GetLastError` at `0x140024851`
- `KERNEL32!GetLastError` at `0x14002489a`
- `KERNEL32!GetLastError` at `0x140024785`
- `KERNEL32!GetLastError` at `0x140024851`
- `KERNEL32!GetLastError` at `0x14002489a`
- `KERNEL32!Sleep` at `0x140024819`
- `KERNEL32!Sleep` at `0x140024819`
- `KERNEL32!SetFileAttributesW` at `0x14002483b`
- `KERNEL32!SetFileAttributesW` at `0x14002483b`
- `KERNEL32!SetLastError` at `0x1400246ec`
- `KERNEL32!SetLastError` at `0x1400248cb`
- `KERNEL32!SetLastError` at `0x1400246ec`
- `KERNEL32!SetLastError` at `0x1400248cb`

## string_xrefs

- `0x1400247ea`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`
- `0x140024869`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x1400248a9`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 WdsCopyFileEx(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        DWORD (__stdcall *a3)(LARGE_INTEGER TotalFileSize, LARGE_INTEGER TotalBytesTransferred, LARGE_INTEGER StreamSize, LARGE_INTEGER StreamBytesTransferred, DWORD dwStreamNumber, DWORD dwCallbackReason, HANDLE hSourceFile, HANDLE hDestinationFile, LPVOID lpData),
        void *a4,
        ...)
{
  char v4; // bl
  unsigned int v5; // edi
  DWORD v9; // r15d
  void *v10; // r13
  void *v11; // rbp
  unsigned int v12; // r14d
  DWORD LastError; // eax
  int v14; // r11d
  DWORD v15; // edi
  DWORD v16; // ebx
  DWORD v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  LPBOOL pbCancel; // [rsp+20h] [rbp-58h]
  LPBOOL pbCancela; // [rsp+20h] [rbp-58h]
  __int64 dwCopyFlags; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  __int64 dwMilliseconds; // [rsp+A0h] [rbp+28h] BYREF
  va_list dwMillisecondsa; // [rsp+A0h] [rbp+28h]
  __int64 v28; // [rsp+A8h] [rbp+30h] BYREF
  va_list va1; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(dwMillisecondsa, a4);
  dwMilliseconds = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v28 = va_arg(va2, _QWORD);
  v4 = v28;
  v5 = 0;
  if ( (v28 & 0xFFFFFFE0) != 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  else
  {
    v9 = v28 & 1 | 0x1000;
    if ( (v28 & 8) == 0 )
      v9 = v28 & 1;
    v10 = (void *)PrepareUnicodePathEx(a1);
    if ( v10 )
    {
      v11 = (void *)PrepareUnicodePathEx(a2);
      if ( v11 )
      {
        v12 = 0;
        while ( 1 )
        {
          v5 = CopyFileExW(a1, a2, a3, a4, 0, v9);
          if ( v5 )
            break;
          if ( (v4 & 2) == 0 )
            goto LABEL_26;
          LastError = GetLastError();
          LODWORD(v28) = v5;
          LODWORD(dwMilliseconds) = v5;
          ++v12;
          if ( (unsigned int)WdsGetCopyRetryData(LastError, (__int64 *)va1, (__int64 *)dwMillisecondsa) )
          {
            if ( v12 >= (unsigned int)v28 )
              goto LABEL_26;
            v15 = dwMilliseconds;
          }
          else
          {
            if ( v12 >= 2 )
              goto LABEL_26;
            v15 = 3000;
          }
          LODWORD(v23) = v15;
          LODWORD(dwCopyFlags) = v14;
          LibLog(
            &g_WdsLibLog,
            0x4000000,
            L"WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms",
            a1,
            a2,
            dwCopyFlags,
            v23);
          if ( v15 )
            Sleep(v15);
        }
        if ( (v4 & 4) != 0 )
        {
          v5 = SetFileAttributesW(a2, 0x80u);
          if ( !v5 )
          {
            v16 = GetLastError();
            if ( !v16 )
              v16 = 31;
            LODWORD(pbCancel) = v16;
            LibLog(
              &g_WdsLibLog,
              0x2000000,
              L"WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x",
              a2,
              pbCancel);
            if ( !(unsigned int)DeleteFileEx2((__int64)a2, 0) )
            {
              v17 = GetLastError();
              if ( !v17 )
                v17 = 31;
              LODWORD(pbCancela) = v17;
              LibLog(&g_WdsLibLog, 0x2000000, L"WdsCopyFileEx: Failed to delete %s. GLE = 0x%x", a2, pbCancela);
            }
            SetLastError(v16);
          }
        }
      }
LABEL_26:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
      if ( v11 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v11);
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x1400246b4  mov     [rsp+arg_0], rbx
0x1400246b9  mov     [rsp+lpData], r9
0x1400246be  mov     [rsp+lpProgressRoutine], r8
0x1400246c3  push    rbp
0x1400246c4  push    rsi
0x1400246c5  push    rdi
0x1400246c6  push    r12
0x1400246c8  push    r13
0x1400246ca  push    r14
0x1400246cc  push    r15
0x1400246ce  sub     rsp, 40h
0x1400246d2  mov     ebx, dword ptr [rsp+78h+arg_28]
0x1400246d9  xor     edi, edi
0x1400246db  mov     rsi, rdx
0x1400246de  mov     r12, rcx
0x1400246e1  test    ebx, 0FFFFFFE0h
0x1400246e7  jz      short loc_1400246FF
0x1400246e9  lea     ecx, [rdi+57h]; dwErrCode
0x1400246ec  call    cs:__imp_SetLastError
0x1400246f3  nop     dword ptr [rax+rax+00h]
0x1400246f8  xor     eax, eax
0x1400246fa  jmp     loc_14002491E
0x1400246ff  mov     ecx, ebx
0x140024701  and     ecx, 1
0x140024704  mov     r15d, ecx
0x140024707  bts     r15d, 0Ch
0x14002470c  test    bl, 8
0x14002470f  cmovz   r15d, ecx
0x140024713  xor     edx, edx
0x140024715  mov     rcx, r12; unsigned __int16 *
0x140024718  call    PrepareUnicodePathEx
0x14002471d  mov     r13, rax
0x140024720  test    rax, rax
0x140024723  jz      loc_14002491C
0x140024729  xor     edx, edx
0x14002472b  mov     rcx, rsi; unsigned __int16 *
0x14002472e  call    PrepareUnicodePathEx
0x140024733  mov     rbp, rax
0x140024736  test    rax, rax
0x140024739  jz      loc_1400248D7
0x14002473f  xor     r14d, r14d
0x140024742  mov     r9, [rsp+78h+lpData]; lpData
0x14002474a  mov     rdx, rsi; lpNewFileName
0x14002474d  mov     r8, [rsp+78h+lpProgressRoutine]; lpProgressRoutine
0x140024755  mov     rcx, r12; lpExistingFileName
0x140024758  mov     dword ptr [rsp+78h+dwCopyFlags], r15d; dwCopyFlags
0x14002475d  mov     [rsp+78h+pbCancel], 0; pbCancel
0x140024766  call    cs:__imp_CopyFileExW
0x14002476d  nop     dword ptr [rax+rax+00h]
0x140024772  mov     edi, eax
0x140024774  test    eax, eax
0x140024776  jnz     loc_14002482A
0x14002477c  test    bl, 2
0x14002477f  jz      loc_1400248D7
0x140024785  call    cs:__imp_GetLastError
0x14002478c  nop     dword ptr [rax+rax+00h]
0x140024791  lea     r8, [rsp+78h+dwMilliseconds]
0x140024799  mov     dword ptr [rsp+78h+arg_28], edi
0x1400247a0  mov     ecx, eax
0x1400247a2  mov     dword ptr [rsp+78h+dwMilliseconds], edi
0x1400247a9  lea     rdx, [rsp+78h+arg_28]
0x1400247b1  mov     r11d, eax
0x1400247b4  inc     r14d
0x1400247b7  call    WdsGetCopyRetryData
0x1400247bc  test    eax, eax
0x1400247be  jz      short loc_1400247D7
0x1400247c0  cmp     r14d, dword ptr [rsp+78h+arg_28]
0x1400247c8  jnb     loc_1400248D7
0x1400247ce  mov     edi, dword ptr [rsp+78h+dwMilliseconds]
0x1400247d5  jmp     short loc_1400247E6
0x1400247d7  cmp     r14d, 2
0x1400247db  jnb     loc_1400248D7
0x1400247e1  mov     edi, 0BB8h
0x1400247e6  mov     dword ptr [rsp+78h+var_48], edi
0x1400247ea  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x1400247f1  mov     dword ptr [rsp+78h+dwCopyFlags], r11d
0x1400247f6  lea     rcx, g_WdsLibLog
0x1400247fd  mov     r9, r12
0x140024800  mov     [rsp+78h+pbCancel], rsi
0x140024805  mov     edx, 4000000h
0x14002480a  call    LibLog
0x14002480f  test    edi, edi
0x140024811  jz      loc_140024742
0x140024817  mov     ecx, edi; dwMilliseconds
0x140024819  call    cs:__imp_Sleep
0x140024820  nop     dword ptr [rax+rax+00h]
0x140024825  jmp     loc_140024742
0x14002482a  test    bl, 4
0x14002482d  jz      loc_1400248D7
0x140024833  mov     edx, 80h; dwFileAttributes
0x140024838  mov     rcx, rsi; lpFileName
0x14002483b  call    cs:__imp_SetFileAttributesW
0x140024842  nop     dword ptr [rax+rax+00h]
0x140024847  mov     edi, eax
0x140024849  test    eax, eax
0x14002484b  jnz     loc_1400248D7
0x140024851  call    cs:__imp_GetLastError
0x140024858  nop     dword ptr [rax+rax+00h]
0x14002485d  lea     r15d, [rdi+1Fh]
0x140024861  mov     r14d, 2000000h
0x140024867  test    eax, eax
0x140024869  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x140024870  mov     ebx, eax
0x140024872  lea     rcx, g_WdsLibLog
0x140024879  cmovz   ebx, r15d
0x14002487d  mov     r9, rsi
0x140024880  mov     edx, r14d
0x140024883  mov     dword ptr [rsp+78h+pbCancel], ebx
0x140024887  call    LibLog
0x14002488c  xor     edx, edx
0x14002488e  mov     rcx, rsi
0x140024891  call    DeleteFileEx2
0x140024896  test    eax, eax
0x140024898  jnz     short loc_1400248C9
0x14002489a  call    cs:__imp_GetLastError
0x1400248a1  nop     dword ptr [rax+rax+00h]
0x1400248a6  mov     r9, rsi
0x1400248a9  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x1400248b0  test    eax, eax
0x1400248b2  lea     rcx, g_WdsLibLog
0x1400248b9  mov     edx, r14d
0x1400248bc  cmovz   eax, r15d
0x1400248c0  mov     dword ptr [rsp+78h+pbCancel], eax
0x1400248c4  call    LibLog
0x1400248c9  mov     ecx, ebx; dwErrCode
0x1400248cb  call    cs:__imp_SetLastError
0x1400248d2  nop     dword ptr [rax+rax+00h]
0x1400248d7  call    cs:__imp_GetProcessHeap
0x1400248de  nop     dword ptr [rax+rax+00h]
0x1400248e3  mov     r8, r13; lpMem
0x1400248e6  xor     edx, edx; dwFlags
0x1400248e8  mov     rcx, rax; hHeap
0x1400248eb  call    cs:__imp_HeapFree
0x1400248f2  nop     dword ptr [rax+rax+00h]
0x1400248f7  test    rbp, rbp
0x1400248fa  jz      short loc_14002491C
0x1400248fc  call    cs:__imp_GetProcessHeap
0x140024903  nop     dword ptr [rax+rax+00h]
0x140024908  mov     r8, rbp; lpMem
0x14002490b  xor     edx, edx; dwFlags
0x14002490d  mov     rcx, rax; hHeap
0x140024910  call    cs:__imp_HeapFree
0x140024917  nop     dword ptr [rax+rax+00h]
0x14002491c  mov     eax, edi
0x14002491e  mov     rbx, [rsp+78h+arg_0]
0x140024926  add     rsp, 40h
0x14002492a  pop     r15
0x14002492c  pop     r14
0x14002492e  pop     r13
0x140024930  pop     r12
0x140024932  pop     rdi
0x140024933  pop     rsi
0x140024934  pop     rbp
0x140024935  retn
```
