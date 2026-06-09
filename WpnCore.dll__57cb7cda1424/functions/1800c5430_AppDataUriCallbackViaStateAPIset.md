# AppDataUriCallbackViaStateAPIset

- ea: `0x1800c5430`
- end: `0x1800c5500`
- name: `AppDataUriCallbackViaStateAPIset`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800c5430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54e0`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800c54d8`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800c54d8`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800c5453`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800c5453`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x1800c54b2`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x1800c54b2`
- `api-ms-win-appmodel-state-l1-2-0!OpenState` at `0x1800c546d`
- `api-ms-win-appmodel-state-l1-2-0!OpenState` at `0x1800c546d`

## pseudocode

```c
__int64 __fastcall AppDataUriCallbackViaStateAPIset(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rsi
  int v10; // edi
  int v11; // edi
  int v12; // edi
  __int64 v13; // rdx
  signed int LastError; // eax
  signed int v15; // eax

  v7 = -2147024809;
  if ( a1 )
  {
    if ( !a3 )
      return v7;
    v8 = OpenStateExplicit(a3, a1);
  }
  else
  {
    if ( a3 )
      return v7;
    v8 = OpenState();
  }
  v9 = v8;
  if ( v8 )
  {
    v10 = a2 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 != 1 )
          {
LABEL_20:
            CloseState(v9);
            return v7;
          }
          v13 = 4;
        }
        else
        {
          v13 = 3;
        }
      }
      else
      {
        v13 = 2;
      }
    }
    else
    {
      v13 = 1;
    }
    if ( (unsigned int)GetStateFolder(v8, v13, a4, a5) )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_20;
  }
  v15 = GetLastError();
  v7 = v15;
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x1800c5430  push    rbx
0x1800c5432  push    rbp
0x1800c5433  push    rsi
0x1800c5434  push    rdi
0x1800c5435  sub     rsp, 28h
0x1800c5439  mov     rbp, r9
0x1800c543c  mov     edi, edx
0x1800c543e  mov     ebx, 80070057h
0x1800c5443  test    rcx, rcx
0x1800c5446  jz      short loc_1800C5464
0x1800c5448  test    r8, r8
0x1800c544b  jz      short loc_1800C545B
0x1800c544d  mov     rdx, rcx
0x1800c5450  mov     rcx, r8
0x1800c5453  call    cs:__imp_OpenStateExplicit
0x1800c5459  jmp     short loc_1800C5473
0x1800c545b  test    rcx, rcx
0x1800c545e  jnz     loc_1800C54F5
0x1800c5464  test    r8, r8
0x1800c5467  jnz     loc_1800C54F5
0x1800c546d  call    cs:__imp_OpenState
0x1800c5473  mov     rsi, rax
0x1800c5476  test    rax, rax
0x1800c5479  jz      short loc_1800C54E0
0x1800c547b  sub     edi, 1
0x1800c547e  jz      short loc_1800C54A2
0x1800c5480  sub     edi, 1
0x1800c5483  jz      short loc_1800C549B
0x1800c5485  sub     edi, 1
0x1800c5488  jz      short loc_1800C5494
0x1800c548a  cmp     edi, 1
0x1800c548d  jnz     short loc_1800C54D5
0x1800c548f  lea     edx, [rdi+3]
0x1800c5492  jmp     short loc_1800C54A7
0x1800c5494  mov     edx, 3
0x1800c5499  jmp     short loc_1800C54A7
0x1800c549b  mov     edx, 2
0x1800c54a0  jmp     short loc_1800C54A7
0x1800c54a2  mov     edx, 1
0x1800c54a7  mov     r9, [rsp+48h+arg_20]
0x1800c54ac  mov     r8, rbp
0x1800c54af  mov     rcx, rsi
0x1800c54b2  call    cs:__imp_GetStateFolder
0x1800c54b8  test    eax, eax
0x1800c54ba  jz      short loc_1800C54C0
0x1800c54bc  xor     ebx, ebx
0x1800c54be  jmp     short loc_1800C54D5
0x1800c54c0  call    cs:__imp_GetLastError
0x1800c54c6  mov     ebx, eax
0x1800c54c8  test    eax, eax
0x1800c54ca  jle     short loc_1800C54D5
0x1800c54cc  movzx   ebx, ax
0x1800c54cf  or      ebx, 80070000h
0x1800c54d5  mov     rcx, rsi
0x1800c54d8  call    cs:__imp_CloseState
0x1800c54de  jmp     short loc_1800C54F5
0x1800c54e0  call    cs:__imp_GetLastError
0x1800c54e6  mov     ebx, eax
0x1800c54e8  test    eax, eax
0x1800c54ea  jle     short loc_1800C54F5
0x1800c54ec  movzx   ebx, ax
0x1800c54ef  or      ebx, 80070000h
0x1800c54f5  mov     eax, ebx
0x1800c54f7  add     rsp, 28h
0x1800c54fb  pop     rdi
0x1800c54fc  pop     rsi
0x1800c54fd  pop     rbp
0x1800c54fe  pop     rbx
0x1800c54ff  retn
```
