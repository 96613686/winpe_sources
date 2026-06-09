# FinalizeUninstallVolume_DeleteAccessPaths

- ea: `0x14001d894`
- end: `0x14001d95f`
- name: `FinalizeUninstallVolume_DeleteAccessPaths`
- size: `203`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001d7c0`

## callees

- `0x1400027fc`
- `0x14001d190`
- `0x14001d894`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001d931`
- `KERNEL32!HeapFree` at `0x14001d931`
- `KERNEL32!GetProcessHeap` at `0x14001d923`
- `KERNEL32!GetProcessHeap` at `0x14001d923`
- `KERNEL32!SetLastError` at `0x14001d944`
- `KERNEL32!SetLastError` at `0x14001d944`
- `KERNEL32!GetLastError` at `0x14001d8fc`
- `KERNEL32!GetLastError` at `0x14001d8fc`

## pseudocode

```c
__int64 __fastcall FinalizeUninstallVolume_DeleteAccessPaths(unsigned __int16 *a1)
{
  DWORD LastError; // edi
  unsigned int v3; // ebx
  unsigned __int16 *v4; // r14
  int v5; // eax
  unsigned __int64 v6; // rsi
  unsigned int v7; // eax
  HANDLE ProcessHeap; // rax
  BOOL v9; // eax
  unsigned __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  LastError = 0;
  v3 = 1;
  v4 = a1;
  if ( a1 )
  {
    while ( 1 )
    {
      v11 = 0;
      v5 = StringCchLengthW(v4, 0x8000u, &v11);
      if ( v5 < 0 )
        break;
      if ( !v11 )
        goto LABEL_10;
      v6 = v11 + 1;
      v7 = DeleteAccessPath(v4, v11 + 1);
      if ( v3 )
      {
        v3 = v7;
        LastError = GetLastError();
      }
      v4 += v6;
    }
    if ( v3 )
    {
      v3 = 0;
      LastError = (unsigned __int16)v5;
      if ( (v5 & 0x1FFF0000) != 0x70000 )
        LastError = v5;
    }
LABEL_10:
    ProcessHeap = GetProcessHeap();
    v9 = HeapFree(ProcessHeap, 0, a1);
    if ( v3 )
    {
      v3 = v9;
      LastError = 6;
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x14001d894  mov     [rsp+arg_8], rbx
0x14001d899  mov     [rsp+arg_10], rbp
0x14001d89e  push    rsi
0x14001d89f  push    rdi
0x14001d8a0  push    r14
0x14001d8a2  sub     rsp, 20h
0x14001d8a6  xor     edi, edi
0x14001d8a8  mov     rbp, rcx
0x14001d8ab  mov     ebx, 1
0x14001d8b0  mov     r14, rcx
0x14001d8b3  test    rcx, rcx
0x14001d8b6  jz      loc_14001D942
0x14001d8bc  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x14001d8c1  mov     [rsp+38h+arg_0], 0
0x14001d8ca  mov     edx, 8000h; unsigned __int64
0x14001d8cf  mov     rcx, r14; unsigned __int16 *
0x14001d8d2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001d8d7  mov     r8d, eax
0x14001d8da  test    eax, eax
0x14001d8dc  js      short loc_14001D90A
0x14001d8de  mov     rsi, [rsp+38h+arg_0]
0x14001d8e3  test    rsi, rsi
0x14001d8e6  jz      short loc_14001D923
0x14001d8e8  inc     rsi
0x14001d8eb  mov     rcx, r14; unsigned __int16 *
0x14001d8ee  mov     rdx, rsi; unsigned __int64
0x14001d8f1  call    ?DeleteAccessPath@@YAHPEBG_K@Z; DeleteAccessPath(ushort const *,unsigned __int64)
0x14001d8f6  test    ebx, ebx
0x14001d8f8  jz      short loc_14001D904
0x14001d8fa  mov     ebx, eax
0x14001d8fc  call    cs:__imp_GetLastError
0x14001d902  mov     edi, eax
0x14001d904  lea     r14, [r14+rsi*2]
0x14001d908  jmp     short loc_14001D8BC
0x14001d90a  test    ebx, ebx
0x14001d90c  jz      short loc_14001D923
0x14001d90e  xor     ebx, ebx
0x14001d910  movzx   edi, r8w
0x14001d914  and     eax, 1FFF0000h
0x14001d919  cmp     eax, 70000h
0x14001d91e  jz      short loc_14001D923
0x14001d920  mov     edi, r8d
0x14001d923  call    cs:__imp_GetProcessHeap
0x14001d929  mov     r8, rbp; lpMem
0x14001d92c  xor     edx, edx; dwFlags
0x14001d92e  mov     rcx, rax; hHeap
0x14001d931  call    cs:__imp_HeapFree
0x14001d937  test    ebx, ebx
0x14001d939  jz      short loc_14001D942
0x14001d93b  mov     ebx, eax
0x14001d93d  mov     edi, 6
0x14001d942  mov     ecx, edi; dwErrCode
0x14001d944  call    cs:__imp_SetLastError
0x14001d94a  mov     rbp, [rsp+38h+arg_10]
0x14001d94f  mov     eax, ebx
0x14001d951  mov     rbx, [rsp+38h+arg_8]
0x14001d956  add     rsp, 20h
0x14001d95a  pop     r14
0x14001d95c  pop     rdi
0x14001d95d  pop     rsi
0x14001d95e  retn
```
