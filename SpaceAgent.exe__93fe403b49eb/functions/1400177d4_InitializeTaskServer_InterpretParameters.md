# InitializeTaskServer_InterpretParameters

- ea: `0x1400177d4`
- end: `0x1400178c7`
- name: `InitializeTaskServer_InterpretParameters`
- size: `243`
- prototype: `__int64 __fastcall(HANDLE hSourceProcessHandle, int, const WCHAR **, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400174bc`

## callees

- `0x1400177d4`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1400177ec`
- `KERNEL32!GetCurrentProcess` at `0x1400177ec`
- `KERNEL32!CloseHandle` at `0x1400178a6`
- `KERNEL32!CloseHandle` at `0x1400178a6`
- `KERNEL32!DuplicateHandle` at `0x14001784d`
- `KERNEL32!DuplicateHandle` at `0x14001784d`
- `KERNEL32!SetLastError` at `0x14001787e`
- `KERNEL32!SetLastError` at `0x1400178b2`
- `KERNEL32!SetLastError` at `0x14001787e`
- `KERNEL32!SetLastError` at `0x1400178b2`
- `KERNEL32!GetLastError` at `0x140017864`
- `KERNEL32!GetLastError` at `0x140017884`
- `KERNEL32!GetLastError` at `0x140017864`
- `KERNEL32!GetLastError` at `0x140017884`
- `SHLWAPI!StrToIntExW` at `0x140017817`
- `SHLWAPI!StrToIntExW` at `0x140017817`

## pseudocode

```c
__int64 __fastcall InitializeTaskServer_InterpretParameters(
        HANDLE hSourceProcessHandle,
        int a2,
        const WCHAR **a3,
        __int64 a4)
{
  HANDLE CurrentProcess; // r15
  __int64 v9; // rbx
  const WCHAR *v10; // rcx
  unsigned int v11; // edi
  DWORD LastError; // esi
  DWORD v13; // ecx
  int piRet; // [rsp+88h] [rbp+10h] BYREF

  CurrentProcess = GetCurrentProcess();
  if ( a2 == 5 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = *a3;
      piRet = 0;
      v11 = StrToIntExW(v10, 1, &piRet);
      if ( !v11 )
        break;
      v11 = DuplicateHandle(hSourceProcessHandle, (HANDLE)piRet, CurrentProcess, (LPHANDLE)(a4 + 8 * v9), 0, 0, 2u);
      if ( !v11 )
        goto LABEL_10;
      v9 = (unsigned int)(v9 + 1);
      ++a3;
      if ( (unsigned int)v9 >= 5 )
      {
        LastError = GetLastError();
        goto LABEL_13;
      }
    }
    v13 = 87;
  }
  else
  {
    LODWORD(v9) = 0;
    v13 = 1359;
    v11 = 0;
  }
  SetLastError(v13);
LABEL_10:
  LastError = GetLastError();
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  while ( (_DWORD)v9 )
  {
    LODWORD(v9) = v9 - 1;
    CloseHandle(*(HANDLE *)(a4 + 8LL * (unsigned int)v9));
  }
LABEL_13:
  SetLastError(LastError);
  return v11;
}

```

## disassembly

```asm
0x1400177d4  push    rbx
0x1400177d6  push    rbp
0x1400177d7  push    rsi
0x1400177d8  push    rdi
0x1400177d9  push    r14
0x1400177db  push    r15
0x1400177dd  sub     rsp, 48h
0x1400177e1  mov     r14, r9
0x1400177e4  mov     rsi, r8
0x1400177e7  mov     ebx, edx
0x1400177e9  mov     rbp, rcx
0x1400177ec  call    cs:__imp_GetCurrentProcess
0x1400177f2  mov     r15, rax
0x1400177f5  cmp     ebx, 5
0x1400177f8  jnz     short loc_140017875
0x1400177fa  xor     ebx, ebx
0x1400177fc  mov     rcx, [rsi]; pszString
0x1400177ff  lea     r8, [rsp+78h+piRet]; piRet
0x140017807  mov     edx, 1; dwFlags
0x14001780c  mov     [rsp+78h+piRet], 0
0x140017817  call    cs:__imp_StrToIntExW
0x14001781d  mov     edi, eax
0x14001781f  test    eax, eax
0x140017821  jz      short loc_14001786E
0x140017823  movsxd  rdx, [rsp+78h+piRet]; hSourceHandle
0x14001782b  lea     r9, [r14+rbx*8]; lpTargetHandle
0x14001782f  mov     [rsp+78h+dwOptions], 2; dwOptions
0x140017837  mov     r8, r15; hTargetProcessHandle
0x14001783a  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x140017842  mov     rcx, rbp; hSourceProcessHandle
0x140017845  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x14001784d  call    cs:__imp_DuplicateHandle
0x140017853  mov     edi, eax
0x140017855  test    eax, eax
0x140017857  jz      short loc_140017884
0x140017859  inc     ebx
0x14001785b  add     rsi, 8
0x14001785f  cmp     ebx, 5
0x140017862  jb      short loc_1400177FC
0x140017864  call    cs:__imp_GetLastError
0x14001786a  mov     esi, eax
0x14001786c  jmp     short loc_1400178B0
0x14001786e  mov     ecx, 57h ; 'W'
0x140017873  jmp     short loc_14001787E
0x140017875  xor     ebx, ebx
0x140017877  mov     ecx, 54Fh; dwErrCode
0x14001787c  xor     edi, edi
0x14001787e  call    cs:__imp_SetLastError
0x140017884  call    cs:__imp_GetLastError
0x14001788a  xorps   xmm0, xmm0
0x14001788d  mov     esi, eax
0x14001788f  movups  xmmword ptr [r14], xmm0
0x140017893  xor     eax, eax
0x140017895  movups  xmmword ptr [r14+10h], xmm0
0x14001789a  mov     [r14+20h], rax
0x14001789e  jmp     short loc_1400178AC
0x1400178a0  dec     ebx
0x1400178a2  mov     rcx, [r14+rbx*8]; hObject
0x1400178a6  call    cs:__imp_CloseHandle
0x1400178ac  test    ebx, ebx
0x1400178ae  jnz     short loc_1400178A0
0x1400178b0  mov     ecx, esi; dwErrCode
0x1400178b2  call    cs:__imp_SetLastError
0x1400178b8  mov     eax, edi
0x1400178ba  add     rsp, 48h
0x1400178be  pop     r15
0x1400178c0  pop     r14
0x1400178c2  pop     rdi
0x1400178c3  pop     rsi
0x1400178c4  pop     rbp
0x1400178c5  pop     rbx
0x1400178c6  retn
```
