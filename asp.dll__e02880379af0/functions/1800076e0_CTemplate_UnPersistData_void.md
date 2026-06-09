# CTemplate::UnPersistData(void)

- ea: `0x1800076e0`
- end: `0x18000788e`
- name: `?UnPersistData@CTemplate@@QEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CTemplate *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000a9d0`
- `0x1800108d0`
- `0x180012a20`

## callees

- `0x1800076e0`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18000786d`
- `ADVAPI32!SetThreadToken` at `0x18000786d`
- `ADVAPI32!RevertToSelf` at `0x18000774b`
- `ADVAPI32!RevertToSelf` at `0x18000774b`
- `ADVAPI32!OpenThreadToken` at `0x18000773d`
- `ADVAPI32!OpenThreadToken` at `0x18000773d`
- `KERNEL32!HeapAlloc` at `0x1800077d4`
- `KERNEL32!HeapAlloc` at `0x1800077d4`
- `KERNEL32!CreateFileA` at `0x18000777f`
- `KERNEL32!CreateFileA` at `0x18000777f`
- `KERNEL32!ReadFile` at `0x1800077fa`
- `KERNEL32!ReadFile` at `0x1800077fa`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x1800268d4`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x1800269c2`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x1800268d4`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x1800269c2`
- `KERNEL32!CloseHandle` at `0x18000780b`
- `KERNEL32!CloseHandle` at `0x180007880`
- `KERNEL32!CloseHandle` at `0x1800269b4`
- `KERNEL32!CloseHandle` at `0x18000780b`
- `KERNEL32!CloseHandle` at `0x180007880`
- `KERNEL32!CloseHandle` at `0x1800269b4`
- `KERNEL32!GetLastError` at `0x1800268ef`
- `KERNEL32!GetLastError` at `0x180026900`
- `KERNEL32!GetLastError` at `0x18002691e`
- `KERNEL32!GetLastError` at `0x180026973`
- `KERNEL32!GetLastError` at `0x180026981`
- `KERNEL32!GetLastError` at `0x1800269ce`
- `KERNEL32!GetLastError` at `0x1800268ef`
- `KERNEL32!GetLastError` at `0x180026900`
- `KERNEL32!GetLastError` at `0x18002691e`
- `KERNEL32!GetLastError` at `0x180026973`
- `KERNEL32!GetLastError` at `0x180026981`
- `KERNEL32!GetLastError` at `0x1800269ce`
- `KERNEL32!GetCurrentThread` at `0x18000771c`
- `KERNEL32!GetCurrentThread` at `0x18000771c`

## pseudocode

```c
__int64 __fastcall CTemplate::UnPersistData(CTemplate *this)
{
  signed int v2; // ebp
  HANDLE FileA; // rsi
  unsigned __int64 v4; // rax
  DWORD *v5; // rdi
  SIZE_T v6; // r8
  void *v7; // rax
  bool v8; // zf
  signed int v10; // eax
  signed int LastError; // eax
  signed int v12; // eax
  signed int v13; // eax
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+10h] BYREF
  HANDLE Thread; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  NumberOfBytesRead = 0;
  TokenHandle = 0;
  Thread = 0;
  if ( g_fIsWow64Process )
    Wow64EnableWow64FsRedirection(0);
  if ( *((_QWORD *)this + 8) )
  {
    *((_DWORD *)this + 98) &= ~0x1000u;
    goto LABEL_18;
  }
  Thread = GetCurrentThread();
  if ( OpenThreadToken(Thread, 0x2000Cu, 1, &TokenHandle) )
  {
    RevertToSelf();
    goto LABEL_6;
  }
  if ( GetLastError() == 1008 )
  {
LABEL_6:
    FileA = CreateFileA(*((LPCSTR *)this + 58), 0x80000000, 0, 0, 3u, 0, 0);
    if ( FileA == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v5 = (DWORD *)((char *)this + 72);
    }
    else
    {
      v4 = *((unsigned int *)this + 18);
      v5 = (DWORD *)((char *)this + 72);
      if ( v4 >= 0x4000 )
      {
        v6 = (v4 + 4095) & 0xFFFFFFFFFFFFF000uLL;
      }
      else if ( v4 >= 0x1000 )
      {
        v6 = (v4 + 1023) & 0xFFFFFFFFFFFFFC00uLL;
      }
      else if ( v4 < 0x400 )
      {
        v6 = (v4 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
      }
      else
      {
        v6 = (v4 + 255) & 0xFFFFFFFFFFFFFF00uLL;
      }
      v7 = HeapAlloc(CTemplate::sm_hLargeHeap, 0, v6);
      *((_QWORD *)this + 8) = v7;
      if ( !v7 )
      {
        v2 = -2147024882;
        goto LABEL_42;
      }
      if ( ReadFile(FileA, v7, *v5, &NumberOfBytesRead, 0) )
      {
        if ( CloseHandle(FileA) )
        {
          FileA = 0;
LABEL_15:
          if ( *v5 == NumberOfBytesRead )
          {
            *((_DWORD *)this + 98) &= ~0x1000u;
            v8 = v2 == 0;
            goto LABEL_17;
          }
          v2 = -2147467259;
LABEL_42:
          if ( FileA )
            CloseHandle(FileA);
          goto LABEL_18;
        }
        v12 = GetLastError();
        v2 = v12;
        if ( v12 > 0 )
          goto LABEL_38;
      }
      else
      {
        v12 = GetLastError();
        v2 = v12;
        if ( v12 > 0 )
LABEL_38:
          v2 = (unsigned __int16)v12 | 0x80070000;
      }
    }
    v8 = v2 == 0;
    if ( v2 < 0 )
    {
LABEL_17:
      if ( v8 )
        goto LABEL_18;
      goto LABEL_42;
    }
    goto LABEL_15;
  }
  v10 = GetLastError();
  v2 = v10;
  if ( v10 > 0 )
    v2 = (unsigned __int16)v10 | 0x80070000;
LABEL_18:
  if ( g_fIsWow64Process )
    Wow64EnableWow64FsRedirection(1u);
  if ( TokenHandle )
  {
    if ( !SetThreadToken(&Thread, TokenHandle) )
    {
      v13 = GetLastError();
      v2 = v13;
      if ( v13 > 0 )
        v2 = (unsigned __int16)v13 | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800076e0  mov     rax, rsp
0x1800076e3  push    rbp
0x1800076e4  sub     rsp, 60h
0x1800076e8  mov     [rax-10h], rbx
0x1800076ec  mov     rbx, rcx
0x1800076ef  mov     [rax-28h], r14
0x1800076f3  xor     r14d, r14d
0x1800076f6  cmp     cs:?g_fIsWow64Process@@3HA, r14d; int g_fIsWow64Process
0x1800076fd  mov     ebp, r14d
0x180007700  mov     [rax+8], r14d
0x180007704  mov     [rax+10h], r14
0x180007708  mov     [rax+18h], r14
0x18000770c  jnz     loc_1800268D2
0x180007712  cmp     [rbx+40h], rbp
0x180007716  jnz     loc_1800268E0
0x18000771c  call    cs:__imp_GetCurrentThread
0x180007722  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180007727  mov     edx, 2000Ch; DesiredAccess
0x18000772c  mov     rcx, rax; ThreadHandle
0x18000772f  mov     [rsp+68h+Thread], rax
0x180007737  mov     r8d, 1; OpenAsSelf
0x18000773d  call    cs:__imp_OpenThreadToken
0x180007743  test    eax, eax
0x180007745  jz      loc_1800268EF
0x18000774b  call    cs:__imp_RevertToSelf
0x180007751  mov     rcx, [rbx+1D0h]; lpFileName
0x180007758  xor     r9d, r9d; lpSecurityAttributes
0x18000775b  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180007760  xor     r8d, r8d; dwShareMode
0x180007763  mov     [rsp+68h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180007768  mov     edx, 80000000h; dwDesiredAccess
0x18000776d  mov     [rsp+68h+var_18], rsi
0x180007772  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000777a  mov     [rsp+68h+var_20], rdi
0x18000777f  call    cs:__imp_CreateFileA
0x180007785  mov     rsi, rax
0x180007788  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000778c  jz      loc_18002691E
0x180007792  mov     eax, [rbx+48h]
0x180007795  lea     rdi, [rbx+48h]
0x180007799  cmp     rax, 4000h
0x18000779f  jnb     loc_180026939
0x1800077a5  cmp     rax, 1000h
0x1800077ab  jnb     loc_18002694C
0x1800077b1  cmp     rax, 400h
0x1800077b7  jb      loc_18002695F
0x1800077bd  lea     r8, [rax+0FFh]
0x1800077c4  and     r8, 0FFFFFFFFFFFFFF00h; dwBytes
0x1800077cb  mov     rcx, cs:?sm_hLargeHeap@CTemplate@@2PEAXEA; hHeap
0x1800077d2  xor     edx, edx; dwFlags
0x1800077d4  call    cs:__imp_HeapAlloc
0x1800077da  mov     [rbx+40h], rax
0x1800077de  test    rax, rax
0x1800077e1  jz      loc_18002696C
0x1800077e7  mov     r8d, [rdi]; nNumberOfBytesToRead
0x1800077ea  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800077ef  mov     rdx, rax; lpBuffer
0x1800077f2  mov     qword ptr [rsp+68h+dwCreationDisposition], r14; lpOverlapped
0x1800077f7  mov     rcx, rsi; hFile
0x1800077fa  call    cs:__imp_ReadFile
0x180007800  test    eax, eax
0x180007802  jz      loc_180026973
0x180007808  mov     rcx, rsi; hObject
0x18000780b  call    cs:__imp_CloseHandle
0x180007811  test    eax, eax
0x180007813  jz      loc_180026981
0x180007819  mov     rsi, r14
0x18000781c  mov     eax, [rsp+68h+NumberOfBytesRead]
0x180007820  cmp     [rdi], eax
0x180007822  jnz     loc_1800269A3
0x180007828  and     dword ptr [rbx+188h], 0FFFFEFFFh
0x180007832  test    ebp, ebp
0x180007834  jnz     loc_1800269A8
0x18000783a  mov     rsi, [rsp+68h+var_18]
0x18000783f  mov     rdi, [rsp+68h+var_20]
0x180007844  cmp     cs:?g_fIsWow64Process@@3HA, 0; int g_fIsWow64Process
0x18000784b  mov     r14, [rsp+68h+var_28]
0x180007850  mov     rbx, [rsp+68h+var_10]
0x180007855  jnz     loc_1800269C0
0x18000785b  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180007860  test    rdx, rdx
0x180007863  jz      short loc_180007886
0x180007865  lea     rcx, [rsp+68h+Thread]; Thread
0x18000786d  call    cs:__imp_SetThreadToken
0x180007873  test    eax, eax
0x180007875  jz      loc_1800269CE
0x18000787b  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180007880  call    cs:__imp_CloseHandle
0x180007886  mov     eax, ebp
0x180007888  add     rsp, 60h
0x18000788c  pop     rbp
0x18000788d  retn
0x1800268d2  xor     ecx, ecx; Wow64FsEnableRedirection
0x1800268d4  call    cs:__imp_Wow64EnableWow64FsRedirection
0x1800268da  nop
0x1800268db  jmp     loc_180007712
0x1800268e0  and     dword ptr [rbx+188h], 0FFFFEFFFh
0x1800268ea  jmp     loc_180007844
0x1800268ef  call    cs:__imp_GetLastError
0x1800268f5  cmp     eax, 3F0h
0x1800268fa  jz      loc_180007751
0x180026900  call    cs:__imp_GetLastError
0x180026906  mov     ebp, eax
0x180026908  test    eax, eax
0x18002690a  jle     loc_180007844
0x180026910  movzx   ebp, ax
0x180026913  or      ebp, 80070000h
0x180026919  jmp     loc_180007844
0x18002691e  call    cs:__imp_GetLastError
0x180026924  mov     ebp, eax
0x180026926  test    eax, eax
0x180026928  jle     short loc_180026933
0x18002692a  movzx   ebp, ax
0x18002692d  or      ebp, 80070000h
0x180026933  lea     rdi, [rbx+48h]
0x180026937  jmp     short loc_180026996
0x180026939  lea     r8, [rax+0FFFh]
0x180026940  and     r8, 0FFFFFFFFFFFFF000h
0x180026947  jmp     loc_1800077CB
0x18002694c  lea     r8, [rax+3FFh]
0x180026953  and     r8, 0FFFFFFFFFFFFFC00h
0x18002695a  jmp     loc_1800077CB
0x18002695f  lea     r8, [rax+1Fh]
0x180026963  and     r8, 0FFFFFFFFFFFFFFE0h
0x180026967  jmp     loc_1800077CB
0x18002696c  mov     ebp, 8007000Eh
0x180026971  jmp     short loc_1800269A8
0x180026973  call    cs:__imp_GetLastError
0x180026979  mov     ebp, eax
0x18002697b  test    eax, eax
0x18002697d  jg      short loc_18002698D
0x18002697f  jmp     short loc_180026996
0x180026981  call    cs:__imp_GetLastError
0x180026987  mov     ebp, eax
0x180026989  test    eax, eax
0x18002698b  jle     short loc_180026996
0x18002698d  movzx   ebp, ax
0x180026990  or      ebp, 80070000h
0x180026996  test    ebp, ebp
0x180026998  js      loc_180007834
0x18002699e  jmp     loc_18000781C
0x1800269a3  mov     ebp, 80004005h
0x1800269a8  test    rsi, rsi
0x1800269ab  jz      loc_18000783A
0x1800269b1  mov     rcx, rsi; hObject
0x1800269b4  call    cs:__imp_CloseHandle
0x1800269ba  nop
0x1800269bb  jmp     loc_18000783A
0x1800269c0  mov     cl, 1; Wow64FsEnableRedirection
0x1800269c2  call    cs:__imp_Wow64EnableWow64FsRedirection
0x1800269c8  nop
0x1800269c9  jmp     loc_18000785B
0x1800269ce  call    cs:__imp_GetLastError
0x1800269d4  mov     ebp, eax
0x1800269d6  test    eax, eax
0x1800269d8  jle     loc_18000787B
0x1800269de  movzx   ebp, ax
0x1800269e1  or      ebp, 80070000h
0x1800269e7  jmp     loc_18000787B
```
