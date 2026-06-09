# StartAddress

- ea: `0x18004b918`
- end: `0x18004bbc5`
- name: `StartAddress`
- size: `685`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001a1cc`
- `0x18001dbd0`
- `0x180022194`
- `0x180030320`
- `0x18004b578`
- `0x18004b918`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004bb3e`
- `KERNEL32!CloseHandle` at `0x18004bb3e`
- `KERNEL32!GetLastError` at `0x18004b9fe`
- `KERNEL32!GetLastError` at `0x18004ba38`
- `KERNEL32!GetLastError` at `0x18004b9fe`
- `KERNEL32!GetLastError` at `0x18004ba38`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18004b9f4`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18004b9f4`
- `ole32!CoInitializeEx` at `0x18004b969`
- `ole32!CoInitializeEx` at `0x18004b969`
- `ole32!CoUninitialize` at `0x18004ba6b`
- `ole32!CoUninitialize` at `0x18004baac`
- `ole32!CoUninitialize` at `0x18004ba6b`
- `ole32!CoUninitialize` at `0x18004baac`

## pseudocode

```c
__int64 __fastcall StartAddress(HANDLE *lpThreadParameter)
{
  HRESULT v3; // eax
  unsigned int v4; // r12d
  signed int LastError; // eax
  signed int v6; // eax
  __int64 v7; // r9
  unsigned __int64 v8; // r13
  void *v9; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+88h] [rbp+10h]
  unsigned __int64 CompletionKey; // [rsp+90h] [rbp+18h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+98h] [rbp+20h] BYREF

  if ( lpThreadParameter )
  {
    v3 = CoInitializeEx(0, 0);
    v4 = v3;
    v11 = v3;
    if ( v3 < 0 && off_1800A3660 != (_UNKNOWN *)&off_1800A3660 && (*((_BYTE *)off_1800A3660 + 28) & 2) != 0 )
      sub_18001A1CC(*((_QWORD *)off_1800A3660 + 2), 32, &stru_1800040F8, (unsigned int)v3);
    NumberOfBytesTransferred = 0;
    CompletionKey = 0;
    Overlapped = 0;
    while ( 1 )
    {
      if ( !GetQueuedCompletionStatus(
              lpThreadParameter[12],
              &NumberOfBytesTransferred,
              &CompletionKey,
              &Overlapped,
              0xFFFFFFFF) )
      {
        LastError = GetLastError();
        v4 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v4 = LastError;
        v11 = v4;
        if ( v4 != -2147023901 )
        {
          if ( off_1800A3660 != (_UNKNOWN *)&off_1800A3660 && (*((_BYTE *)off_1800A3660 + 28) & 1) != 0 )
          {
            v6 = GetLastError();
            v7 = (unsigned __int16)v6 | 0x80070000;
            if ( v6 <= 0 )
              v7 = (unsigned int)v6;
            sub_18001A1CC(*((_QWORD *)off_1800A3660 + 2), 36, &stru_1800040F8, v7);
          }
          goto LABEL_20;
        }
      }
      v8 = CompletionKey;
      if ( CompletionKey == -1 )
        break;
      if ( v4 == -2147023901 )
      {
        if ( off_1800A3660 != (_UNKNOWN *)&off_1800A3660 && (*((_BYTE *)off_1800A3660 + 28) & 4) != 0 )
          sub_18001DBD0(*((_QWORD *)off_1800A3660 + 2), 34, &stru_1800040F8);
        if ( v8 )
        {
          sub_180022194(v8 + 4472);
          sub_180022194(v8 + 4392);
          sub_180022194(v8 + 4312);
          sub_180022194(v8 + 4232);
          sub_180022194(v8 + 4152);
          v9 = *(void **)(v8 + 4136);
          if ( v9 )
          {
            CloseHandle(v9);
            *(_QWORD *)(v8 + 4136) = 0;
          }
          sub_180030320(qword_1800A4C20, v8, 0xFFFFFFFFLL);
        }
      }
      else
      {
        sub_18004B578(lpThreadParameter, CompletionKey, NumberOfBytesTransferred);
      }
    }
    if ( off_1800A3660 != (_UNKNOWN *)&off_1800A3660 && (*((_BYTE *)off_1800A3660 + 28) & 4) != 0 )
      sub_18001DBD0(*((_QWORD *)off_1800A3660 + 2), (unsigned int)(CompletionKey + 34), &stru_1800040F8);
LABEL_20:
    CoUninitialize();
    return 0;
  }
  else
  {
    if ( off_1800A3660 != (_UNKNOWN *)&off_1800A3660 && (*((_BYTE *)off_1800A3660 + 28) & 1) != 0 )
      sub_18001DBD0(*((_QWORD *)off_1800A3660 + 2), 31, &stru_1800040F8);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18004b918  push    rbx
0x18004b919  push    rsi
0x18004b91a  push    rdi
0x18004b91b  push    r12
0x18004b91d  push    r13
0x18004b91f  push    r14
0x18004b921  sub     rsp, 48h
0x18004b925  mov     r14, rcx
0x18004b928  xor     edi, edi
0x18004b92a  cmp     rcx, rdi
0x18004b92d  jnz     short loc_18004B965
0x18004b92f  lea     rsi, off_1800A3660
0x18004b936  mov     rcx, cs:off_1800A3660
0x18004b93d  cmp     rcx, rsi
0x18004b940  jz      short loc_18004B95B
0x18004b942  test    byte ptr [rcx+1Ch], 1
0x18004b946  jz      short loc_18004B95B
0x18004b948  lea     edx, [rdi+1Fh]
0x18004b94b  lea     r8, stru_1800040F8
0x18004b952  mov     rcx, [rcx+10h]
0x18004b956  call    sub_18001DBD0
0x18004b95b  mov     eax, 80070057h
0x18004b960  jmp     loc_18004BBB7
0x18004b965  xor     edx, edx; dwCoInit
0x18004b967  xor     ecx, ecx; pvReserved
0x18004b969  call    cs:CoInitializeEx
0x18004b96f  mov     r12d, eax
0x18004b972  mov     [rsp+78h+arg_8], eax
0x18004b979  cmp     eax, edi
0x18004b97b  jge     short loc_18004B9B0
0x18004b97d  lea     rsi, off_1800A3660
0x18004b984  mov     rcx, cs:off_1800A3660
0x18004b98b  cmp     rcx, rsi
0x18004b98e  jz      short loc_18004B9B7
0x18004b990  test    byte ptr [rcx+1Ch], 2
0x18004b994  jz      short loc_18004B9B7
0x18004b996  mov     edx, 20h ; ' '
0x18004b99b  mov     r9d, eax
0x18004b99e  lea     r8, stru_1800040F8
0x18004b9a5  mov     rcx, [rcx+10h]
0x18004b9a9  call    sub_18001A1CC
0x18004b9ae  jmp     short loc_18004B9B7
0x18004b9b0  lea     rsi, off_1800A3660
0x18004b9b7  mov     [rsp+78h+var_48], r14
0x18004b9bc  mov     [rsp+78h+NumberOfBytesTransferred], edi
0x18004b9c3  mov     [rsp+78h+CompletionKey], rdi
0x18004b9cb  mov     [rsp+78h+Overlapped], rdi
0x18004b9d3  or      [rsp+78h+var_58], 0FFFFFFFFh
0x18004b9d8  lea     r9, [rsp+78h+Overlapped]; lpOverlapped
0x18004b9e0  lea     r8, [rsp+78h+CompletionKey]; lpCompletionKey
0x18004b9e8  lea     rdx, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18004b9f0  mov     rcx, [r14+60h]; CompletionPort
0x18004b9f4  call    cs:GetQueuedCompletionStatus
0x18004b9fa  cmp     eax, edi
0x18004b9fc  jnz     short loc_18004BA78
0x18004b9fe  call    cs:GetLastError
0x18004ba04  movzx   r12d, ax
0x18004ba08  or      r12d, 80070000h
0x18004ba0f  cmp     eax, edi
0x18004ba11  cmovle  r12d, eax
0x18004ba15  mov     [rsp+78h+arg_8], r12d
0x18004ba1d  cmp     r12d, 800703E3h
0x18004ba24  jz      short loc_18004BA78
0x18004ba26  mov     rax, cs:off_1800A3660
0x18004ba2d  cmp     rax, rsi
0x18004ba30  jz      short loc_18004BA6B
0x18004ba32  test    byte ptr [rax+1Ch], 1
0x18004ba36  jz      short loc_18004BA6B
0x18004ba38  call    cs:GetLastError
0x18004ba3e  movzx   r9d, ax
0x18004ba42  or      r9d, 80070000h
0x18004ba49  cmp     eax, edi
0x18004ba4b  cmovle  r9d, eax
0x18004ba4f  mov     edx, 24h ; '$'
0x18004ba54  lea     r8, stru_1800040F8
0x18004ba5b  mov     rcx, cs:off_1800A3660
0x18004ba62  mov     rcx, [rcx+10h]
0x18004ba66  call    sub_18001A1CC
0x18004ba6b  call    cs:CoUninitialize
0x18004ba71  xor     eax, eax
0x18004ba73  jmp     loc_18004BBB7
0x18004ba78  mov     r13, [rsp+78h+CompletionKey]
0x18004ba80  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18004ba84  jnz     short loc_18004BAB9
0x18004ba86  mov     rcx, cs:off_1800A3660
0x18004ba8d  cmp     rcx, rsi
0x18004ba90  jz      short loc_18004BAAC
0x18004ba92  test    byte ptr [rcx+1Ch], 4
0x18004ba96  jz      short loc_18004BAAC
0x18004ba98  lea     edx, [r13+22h]
0x18004ba9c  lea     r8, stru_1800040F8
0x18004baa3  mov     rcx, [rcx+10h]
0x18004baa7  call    sub_18001DBD0
0x18004baac  call    cs:CoUninitialize
0x18004bab2  xor     eax, eax
0x18004bab4  jmp     loc_18004BBB7
0x18004bab9  cmp     r12d, 800703E3h
0x18004bac0  jnz     loc_18004BB60
0x18004bac6  mov     rcx, cs:off_1800A3660
0x18004bacd  cmp     rcx, rsi
0x18004bad0  jz      short loc_18004BAED
0x18004bad2  test    byte ptr [rcx+1Ch], 4
0x18004bad6  jz      short loc_18004BAED
0x18004bad8  mov     edx, 22h ; '"'
0x18004badd  lea     r8, stru_1800040F8
0x18004bae4  mov     rcx, [rcx+10h]
0x18004bae8  call    sub_18001DBD0
0x18004baed  cmp     r13, rdi
0x18004baf0  jz      loc_18004BBB2
0x18004baf6  lea     rcx, [r13+1178h]
0x18004bafd  call    sub_180022194
0x18004bb02  lea     rcx, [r13+1128h]
0x18004bb09  call    sub_180022194
0x18004bb0e  lea     rcx, [r13+10D8h]
0x18004bb15  call    sub_180022194
0x18004bb1a  lea     rcx, [r13+1088h]
0x18004bb21  call    sub_180022194
0x18004bb26  lea     rcx, [r13+1038h]
0x18004bb2d  call    sub_180022194
0x18004bb32  mov     rcx, [r13+1028h]; hObject
0x18004bb39  cmp     rcx, rdi
0x18004bb3c  jz      short loc_18004BB4B
0x18004bb3e  call    cs:CloseHandle
0x18004bb44  mov     [r13+1028h], rdi
0x18004bb4b  or      r8d, 0FFFFFFFFh
0x18004bb4f  mov     rdx, r13
0x18004bb52  lea     rcx, qword_1800A4C20
0x18004bb59  call    sub_180030320
0x18004bb5e  jmp     short loc_18004BBB2
0x18004bb60  mov     r8d, [rsp+78h+NumberOfBytesTransferred]
0x18004bb68  mov     rdx, r13
0x18004bb6b  mov     rcx, r14
0x18004bb6e  call    sub_18004B578
0x18004bb73  jmp     short loc_18004BBB2
0x18004bb75  lea     rsi, off_1800A3660
0x18004bb7c  mov     rcx, cs:off_1800A3660
0x18004bb83  cmp     rcx, rsi
0x18004bb86  jz      short loc_18004BBA3
0x18004bb88  test    byte ptr [rcx+1Ch], 1
0x18004bb8c  jz      short loc_18004BBA3
0x18004bb8e  mov     edx, 23h ; '#'
0x18004bb93  lea     r8, stru_1800040F8
0x18004bb9a  mov     rcx, [rcx+10h]
0x18004bb9e  call    sub_18001DBD0
0x18004bba3  xor     edi, edi
0x18004bba5  mov     r12d, [rsp+78h+arg_8]
0x18004bbad  mov     r14, [rsp+78h+var_48]
0x18004bbb2  jmp     loc_18004B9D3
0x18004bbb7  add     rsp, 48h
0x18004bbbb  pop     r14
0x18004bbbd  pop     r13
0x18004bbbf  pop     r12
0x18004bbc1  pop     rdi
0x18004bbc2  pop     rsi
0x18004bbc3  pop     rbx
0x18004bbc4  retn
0x18008df5c  push    rbp
0x18008df5d  push    rdi
0x18008df5e  sub     rsp, 38h
0x18008df62  mov     rbp, rdx
0x18008df65  mov     rax, [rcx]
0x18008df68  xor     edi, edi
0x18008df6a  cmp     dword ptr [rax], 0C0000005h
0x18008df70  setz    dil
0x18008df74  mov     eax, edi
0x18008df76  add     rsp, 38h
0x18008df7a  pop     rdi
0x18008df7b  pop     rbp
0x18008df7c  retn
```
