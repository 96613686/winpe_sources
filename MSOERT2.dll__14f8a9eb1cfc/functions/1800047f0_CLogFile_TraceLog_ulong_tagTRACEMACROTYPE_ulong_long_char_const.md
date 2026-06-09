# CLogFile::TraceLog(ulong,tagTRACEMACROTYPE,ulong,long,char const *)

- ea: `0x1800047f0`
- end: `0x1800048bf`
- name: `?TraceLog@CLogFile@@UEAAJKW4tagTRACEMACROTYPE@@KJPEBD@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800047f0`
- `0x180004b34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000485d`
- `KERNEL32!GetLastError` at `0x18000485d`
- `KERNEL32!GetCurrentThreadId` at `0x180004827`
- `KERNEL32!GetCurrentThreadId` at `0x180004865`
- `KERNEL32!GetCurrentThreadId` at `0x180004827`
- `KERNEL32!GetCurrentThreadId` at `0x180004865`

## pseudocode

```c
__int64 __fastcall CLogFile::TraceLog(__int64 a1, char a2, int a3, int a4, unsigned int a5, const char *a6)
{
  DWORD v8; // eax
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // r9d

  if ( a3 )
  {
    if ( a3 == 2 )
    {
      LastError = GetLastError();
      CurrentThreadId = GetCurrentThreadId();
      if ( a6 )
        WriteLogMsg(
          a1,
          2,
          "0x%08X: L(%d), Result: HRESULT(0x%08X) - GetLastError() = %d - %s",
          CurrentThreadId,
          a4,
          a5,
          LastError,
          a6);
      else
        WriteLogMsg(
          a1,
          2,
          "0x%08X: L(%d), Result: HRESULT(0x%08X) - GetLastError() = %d",
          CurrentThreadId,
          a4,
          a5,
          LastError);
    }
  }
  else if ( a6 && (a2 & 1) != 0 )
  {
    v8 = GetCurrentThreadId();
    WriteLogMsg(a1, 2, "0x%08X: L(%d), Info: %s", v8, a4, a6);
  }
  return a5;
}

```

## disassembly

```asm
0x1800047f0  push    rbx
0x1800047f2  push    rbp
0x1800047f3  push    rsi
0x1800047f4  push    rdi
0x1800047f5  push    r14
0x1800047f7  sub     rsp, 40h
0x1800047fb  mov     edi, [rsp+68h+arg_20]
0x180004802  mov     ebp, r9d
0x180004805  mov     r14, rcx
0x180004808  test    r8d, r8d
0x18000480b  jnz     short loc_18000484F
0x18000480d  mov     rbx, [rsp+68h+arg_28]
0x180004815  test    rbx, rbx
0x180004818  jz      loc_1800048B2
0x18000481e  test    dl, 1
0x180004821  jz      loc_1800048B2
0x180004827  call    cs:__imp_GetCurrentThreadId
0x18000482d  mov     [rsp+68h+var_40], rbx
0x180004832  lea     r8, a0x08xLDInfoS; "0x%08X: L(%d), Info: %s"
0x180004839  mov     r9d, eax
0x18000483c  mov     [rsp+68h+var_48], ebp
0x180004840  mov     edx, 2
0x180004845  mov     rcx, r14
0x180004848  call    ?WriteLogMsg@@YAJPEAVCLogFile@@W4LOGFILETYPE@@PEADZZ; WriteLogMsg(CLogFile *,LOGFILETYPE,char *,...)
0x18000484d  jmp     short loc_1800048B2
0x18000484f  cmp     r8d, 2
0x180004853  jnz     short loc_1800048B2
0x180004855  mov     rsi, [rsp+68h+arg_28]
0x18000485d  call    cs:__imp_GetLastError
0x180004863  mov     ebx, eax
0x180004865  call    cs:__imp_GetCurrentThreadId
0x18000486b  mov     edx, 2
0x180004870  mov     r9d, eax
0x180004873  mov     rcx, r14
0x180004876  test    rsi, rsi
0x180004879  jz      short loc_18000489A
0x18000487b  mov     [rsp+68h+var_30], rsi
0x180004880  lea     r8, a0x08xLDResultH_0; "0x%08X: L(%d), Result: HRESULT(0x%08X) "...
0x180004887  mov     [rsp+68h+var_38], ebx
0x18000488b  mov     dword ptr [rsp+68h+var_40], edi
0x18000488f  mov     [rsp+68h+var_48], ebp
0x180004893  call    ?WriteLogMsg@@YAJPEAVCLogFile@@W4LOGFILETYPE@@PEADZZ; WriteLogMsg(CLogFile *,LOGFILETYPE,char *,...)
0x180004898  jmp     short loc_1800048B2
0x18000489a  mov     [rsp+68h+var_38], ebx
0x18000489e  lea     r8, a0x08xLDResultH; "0x%08X: L(%d), Result: HRESULT(0x%08X) "...
0x1800048a5  mov     dword ptr [rsp+68h+var_40], edi
0x1800048a9  mov     [rsp+68h+var_48], ebp
0x1800048ad  call    ?WriteLogMsg@@YAJPEAVCLogFile@@W4LOGFILETYPE@@PEADZZ; WriteLogMsg(CLogFile *,LOGFILETYPE,char *,...)
0x1800048b2  mov     eax, edi
0x1800048b4  add     rsp, 40h
0x1800048b8  pop     r14
0x1800048ba  pop     rdi
0x1800048bb  pop     rsi
0x1800048bc  pop     rbp
0x1800048bd  pop     rbx
0x1800048be  retn
```
