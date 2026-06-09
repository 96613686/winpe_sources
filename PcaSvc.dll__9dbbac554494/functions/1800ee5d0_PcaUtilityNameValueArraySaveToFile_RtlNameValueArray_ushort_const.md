# PcaUtilityNameValueArraySaveToFile(RtlNameValueArray &,ushort const *)

- ea: `0x1800ee5d0`
- end: `0x1800ee7ae`
- name: `?PcaUtilityNameValueArraySaveToFile@@YAKAEAVRtlNameValueArray@@PEBG@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct RtlNameValueArray *this, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800243a4`
- `0x1800b01c8`

## callees

- `0x180007b3c`
- `0x18000cb44`
- `0x180011140`
- `0x180012920`
- `0x1800212b0`
- `0x1800ee5d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee73d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee73d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee748`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ee755`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ee780`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ee755`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ee780`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ee6de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ee6de`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ee728`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ee728`

## string_xrefs

- `0x1800ee69c`: `Failed to write name [%d]`

## pseudocode

```c
__int64 __fastcall PcaUtilityNameValueArraySaveToFile(struct RtlNameValueArray *this, LPCWSTR lpFileName)
{
  ULONGLONG v2; // rdi
  ULONGLONG v5; // rcx
  const unsigned __int16 **v6; // rdx
  unsigned int v7; // eax
  unsigned __int64 v8; // rbx
  const unsigned __int16 *Value; // rax
  int v10; // r8d
  const char *v11; // r9
  HANDLE FileW; // rsi
  char *v13; // rdi
  DWORD v14; // r8d
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-50h]
  PVOID ProcessHeap; // [rsp+40h] [rbp-30h] BYREF
  __int128 v18; // [rsp+48h] [rbp-28h]
  __int64 v19; // [rsp+58h] [rbp-18h]
  LPCVOID lpBuffer[2]; // [rsp+60h] [rbp-10h]
  ULONGLONG pullResult; // [rsp+A0h] [rbp+30h] BYREF

  v2 = 0;
  v19 = 4096;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v18 = 0;
  *(_OWORD *)lpBuffer = 0;
  while ( v2 < *((_QWORD *)this + 2) )
  {
    v5 = *((_QWORD *)this + 1);
    pullResult = 0;
    if ( ULongLongMult(v5, v2, &pullResult) < 0
      || (v6 = (const unsigned __int16 **)(*((_QWORD *)this + 5) + pullResult),
          (unsigned __int64)v6 < *((_QWORD *)this + 5)) )
    {
      v6 = 0;
    }
    v7 = RtlMemoryStream::WriteString((RtlMemoryStream *)&ProcessHeap, *v6, L"=");
    LODWORD(v8) = v7;
    if ( v7 )
    {
      v10 = 1412;
LABEL_10:
      v11 = "Failed to write name [%d]";
LABEL_24:
      dwCreationDisposition[0] = v7;
      AslLogCallPrintf(
        1,
        (unsigned int)"PcaUtilityNameValueArraySaveToFile",
        v10,
        (_DWORD)v11,
        *(_QWORD *)dwCreationDisposition);
      DeleteFileW(lpFileName);
      goto LABEL_26;
    }
    Value = RtlNameValueArray::GetValue(this, v2);
    v7 = RtlMemoryStream::WriteString((RtlMemoryStream *)&ProcessHeap, Value, L"\r\n");
    LODWORD(v8) = v7;
    if ( v7 )
    {
      v10 = 1418;
      goto LABEL_10;
    }
    ++v2;
  }
  LODWORD(pullResult) = 0;
  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(v8) = GetLastError();
  }
  else
  {
    v13 = (char *)lpBuffer[1];
    v8 = v18;
    while ( v8 )
    {
      v14 = v8;
      if ( v8 >= 0xFFFFFFFF )
        v14 = -1;
      if ( !WriteFile(FileW, v13, v14, (LPDWORD)&pullResult, 0) )
      {
        LODWORD(v8) = GetLastError();
        break;
      }
      v8 -= (unsigned int)pullResult;
      v13 += (unsigned int)pullResult;
    }
    CloseHandle(FileW);
  }
  if ( (_DWORD)v8 )
  {
    DeleteFileW(lpFileName);
    v10 = 1425;
    v11 = "Failed to save stream to file [%d]";
    v7 = v8;
    goto LABEL_24;
  }
  LODWORD(v8) = 0;
LABEL_26:
  RtlArray<unsigned short *>::~RtlArray<unsigned short *>(&ProcessHeap);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ee5d0  mov     [rsp-28h+arg_8], rbx
0x1800ee5d5  mov     [rsp-28h+arg_10], rsi
0x1800ee5da  push    rbp
0x1800ee5db  push    rdi
0x1800ee5dc  push    r13
0x1800ee5de  push    r14
0x1800ee5e0  push    r15
0x1800ee5e2  mov     rbp, rsp
0x1800ee5e5  sub     rsp, 70h
0x1800ee5e9  mov     rax, gs:60h
0x1800ee5f2  xor     edi, edi
0x1800ee5f4  xorps   xmm0, xmm0
0x1800ee5f7  mov     [rbp+var_18], 1000h
0x1800ee5ff  xorps   xmm1, xmm1
0x1800ee602  mov     r15, rdx
0x1800ee605  mov     rsi, rcx
0x1800ee608  mov     r8, [rax+30h]
0x1800ee60c  lea     r14d, [rdi+1]
0x1800ee610  mov     [rbp+var_30], r8
0x1800ee614  movdqu  [rbp+var_28], xmm0
0x1800ee619  movdqu  xmmword ptr [rbp+lpBuffer], xmm1
0x1800ee61e  cmp     rdi, [rsi+10h]
0x1800ee622  jnb     loc_1800EE6B0
0x1800ee628  mov     rcx, [rsi+8]; ullMultiplicand
0x1800ee62c  lea     r8, [rbp+pullResult]; pullResult
0x1800ee630  mov     rdx, rdi; ullMultiplier
0x1800ee633  mov     [rbp+pullResult], 0
0x1800ee63b  call    ULongLongMult
0x1800ee640  test    eax, eax
0x1800ee642  js      short loc_1800EE652
0x1800ee644  mov     rdx, [rbp+pullResult]
0x1800ee648  add     rdx, [rsi+28h]
0x1800ee64c  cmp     rdx, [rsi+28h]
0x1800ee650  jnb     short loc_1800EE654
0x1800ee652  xor     edx, edx
0x1800ee654  mov     rdx, [rdx]; unsigned __int16 *
0x1800ee657  lea     r8, asc_18010C8A8; "="
0x1800ee65e  lea     rcx, [rbp+var_30]; this
0x1800ee662  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1800ee667  mov     ebx, eax
0x1800ee669  test    eax, eax
0x1800ee66b  jnz     short loc_1800EE6A8
0x1800ee66d  mov     rdx, rdi; unsigned __int64
0x1800ee670  mov     rcx, rsi; this
0x1800ee673  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x1800ee678  mov     rdx, rax; unsigned __int16 *
0x1800ee67b  lea     r8, asc_18010E264; "\r\n"
0x1800ee682  lea     rcx, [rbp+var_30]; this
0x1800ee686  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1800ee68b  mov     ebx, eax
0x1800ee68d  test    eax, eax
0x1800ee68f  jnz     short loc_1800EE696
0x1800ee691  add     rdi, r14
0x1800ee694  jmp     short loc_1800EE61E
0x1800ee696  mov     r8d, 58Ah
0x1800ee69c  lea     r9, aFailedToWriteN; "Failed to write name [%d]"
0x1800ee6a3  jmp     loc_1800EE76A
0x1800ee6a8  mov     r8d, 584h
0x1800ee6ae  jmp     short loc_1800EE69C
0x1800ee6b0  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800ee6b9  xor     r9d, r9d; lpSecurityAttributes
0x1800ee6bc  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ee6c4  xor     r8d, r8d; dwShareMode
0x1800ee6c7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800ee6cc  mov     [rsp+70h+dwCreationDisposition], 2; dwCreationDisposition
0x1800ee6d4  mov     rcx, r15; lpFileName
0x1800ee6d7  mov     dword ptr [rbp+pullResult], 0
0x1800ee6de  call    cs:__imp_CreateFileW
0x1800ee6e4  mov     rsi, rax
0x1800ee6e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ee6eb  jnz     short loc_1800EE6F7
0x1800ee6ed  call    cs:__imp_GetLastError
0x1800ee6f3  mov     ebx, eax
0x1800ee6f5  jmp     short loc_1800EE74E
0x1800ee6f7  mov     rdi, [rbp+lpBuffer+8]
0x1800ee6fb  mov     r13d, 0FFFFFFFFh
0x1800ee701  mov     rbx, qword ptr [rbp+var_28]
0x1800ee705  test    rbx, rbx
0x1800ee708  jz      short loc_1800EE745
0x1800ee70a  mov     r8d, ebx
0x1800ee70d  cmp     rbx, r13
0x1800ee710  jb      short loc_1800EE715
0x1800ee712  mov     r8d, r13d; nNumberOfBytesToWrite
0x1800ee715  lea     r9, [rbp+pullResult]; lpNumberOfBytesWritten
0x1800ee719  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800ee722  mov     rdx, rdi; lpBuffer
0x1800ee725  mov     rcx, rsi; hFile
0x1800ee728  call    cs:__imp_WriteFile
0x1800ee72e  test    eax, eax
0x1800ee730  jz      short loc_1800EE73D
0x1800ee732  mov     eax, dword ptr [rbp+pullResult]
0x1800ee735  sub     rbx, rax
0x1800ee738  add     rdi, rax
0x1800ee73b  jmp     short loc_1800EE705
0x1800ee73d  call    cs:__imp_GetLastError
0x1800ee743  mov     ebx, eax
0x1800ee745  mov     rcx, rsi; hObject
0x1800ee748  call    cs:__imp_CloseHandle
0x1800ee74e  test    ebx, ebx
0x1800ee750  jz      short loc_1800EE788
0x1800ee752  mov     rcx, r15; lpFileName
0x1800ee755  call    cs:__imp_DeleteFileW
0x1800ee75b  mov     r8d, 591h
0x1800ee761  lea     r9, aFailedToSaveSt; "Failed to save stream to file [%d]"
0x1800ee768  mov     eax, ebx
0x1800ee76a  lea     rdx, aPcautilityname_1; "PcaUtilityNameValueArraySaveToFile"
0x1800ee771  mov     [rsp+70h+dwCreationDisposition], eax
0x1800ee775  mov     ecx, r14d
0x1800ee778  call    AslLogCallPrintf
0x1800ee77d  mov     rcx, r15; lpFileName
0x1800ee780  call    cs:__imp_DeleteFileW
0x1800ee786  jmp     short loc_1800EE78A
0x1800ee788  xor     ebx, ebx
0x1800ee78a  lea     rcx, [rbp+var_30]
0x1800ee78e  call    ??1?$RtlArray@PEAG@@QEAA@XZ; RtlArray<ushort *>::~RtlArray<ushort *>(void)
0x1800ee793  lea     r11, [rsp+70h+var_s0]
0x1800ee798  mov     eax, ebx
0x1800ee79a  mov     rbx, [r11+38h]
0x1800ee79e  mov     rsi, [r11+40h]
0x1800ee7a2  mov     rsp, r11
0x1800ee7a5  pop     r15
0x1800ee7a7  pop     r14
0x1800ee7a9  pop     r13
0x1800ee7ab  pop     rdi
0x1800ee7ac  pop     rbp
0x1800ee7ad  retn
```
