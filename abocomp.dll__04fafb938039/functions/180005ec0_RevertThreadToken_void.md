# RevertThreadToken(void *)

- ea: `0x180005ec0`
- end: `0x180005f5f`
- name: `?RevertThreadToken@@YAXPEAX@Z`
- size: `159`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a070`

## callees

- `0x180001f90`
- `0x180005ec0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005f27`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005f27`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005eea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005eea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005ed2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005ed2`

## string_xrefs

- `0x180005f0d`: ` Could reset Callback thread to caller Impersonation, Error = %X`
- `0x180005f4a`: ` Could not revert Callback thread to caller Impersonation, Error = %X`

## pseudocode

```c
void __fastcall RevertThreadToken(HANDLE hObject)
{
  signed int LastError; // eax
  signed int v3; // eax
  void *Thread; // [rsp+30h] [rbp+8h] BYREF

  Thread = 0;
  Thread = GetCurrentThread();
  if ( hObject )
  {
    if ( !SetThreadToken(&Thread, hObject) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L" Could reset Callback thread to caller Impersonation, Error = %X",
        (unsigned int)LastError);
    }
    CloseHandle(hObject);
  }
  else if ( !RevertToSelf() )
  {
    v3 = GetLastError();
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    ABO_MAPPER_LOG::WriteLogEntry(
      g_pAboLog,
      L" Could not revert Callback thread to caller Impersonation, Error = %X",
      (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x180005ec0  push    rbx
0x180005ec2  sub     rsp, 20h
0x180005ec6  mov     rbx, rcx
0x180005ec9  mov     [rsp+28h+Thread], 0
0x180005ed2  call    cs:__imp_GetCurrentThread
0x180005ed8  mov     [rsp+28h+Thread], rax
0x180005edd  test    rbx, rbx
0x180005ee0  jz      short loc_180005F27
0x180005ee2  mov     rdx, rbx; Token
0x180005ee5  lea     rcx, [rsp+28h+Thread]; Thread
0x180005eea  call    cs:__imp_SetThreadToken
0x180005ef0  test    eax, eax
0x180005ef2  jnz     short loc_180005F1C
0x180005ef4  call    cs:__imp_GetLastError
0x180005efa  test    eax, eax
0x180005efc  jle     short loc_180005F06
0x180005efe  movzx   eax, ax
0x180005f01  or      eax, 80070000h
0x180005f06  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180005f0d  lea     rdx, aCouldResetCall; " Could reset Callback thread to caller "...
0x180005f14  mov     r8d, eax
0x180005f17  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180005f1c  mov     rcx, rbx; hObject
0x180005f1f  call    cs:__imp_CloseHandle
0x180005f25  jmp     short loc_180005F59
0x180005f27  call    cs:__imp_RevertToSelf
0x180005f2d  test    eax, eax
0x180005f2f  jnz     short loc_180005F59
0x180005f31  call    cs:__imp_GetLastError
0x180005f37  test    eax, eax
0x180005f39  jle     short loc_180005F43
0x180005f3b  movzx   eax, ax
0x180005f3e  or      eax, 80070000h
0x180005f43  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180005f4a  lea     rdx, aCouldNotRevert; " Could not revert Callback thread to ca"...
0x180005f51  mov     r8d, eax
0x180005f54  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180005f59  add     rsp, 20h
0x180005f5d  pop     rbx
0x180005f5e  retn
```
