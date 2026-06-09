# DeleteLogActivityFile

- ea: `0x1400297b0`
- end: `0x1400299cb`
- name: `DeleteLogActivityFile`
- size: `539`
- prototype: `__int64 __fastcall(LPCWSTR pszLogFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002c820`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140028c3c`
- `0x1400292bc`
- `0x1400297b0`
- `0x14002d434`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002987f`
- `KERNEL32!GetLastError` at `0x1400298e4`
- `KERNEL32!GetLastError` at `0x14002987f`
- `KERNEL32!GetLastError` at `0x1400298e4`
- `KERNEL32!CloseHandle` at `0x14002986f`
- `KERNEL32!CloseHandle` at `0x14002986f`
- `KERNEL32!DeleteFileW` at `0x1400298d4`
- `KERNEL32!DeleteFileW` at `0x1400298d4`

## pseudocode

```c
__int64 __fastcall DeleteLogActivityFile(LPCWSTR pszLogFileName)
{
  unsigned int v1; // ebx
  const wchar_t *v2; // rdx
  WCHAR *v3; // rsi
  unsigned int v4; // ebx
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  HANDLE v7; // rcx
  HANDLE *v8; // rdi
  DWORD LastError; // eax
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  struct _SECURITY_ATTRIBUTES *v12; // r9
  DWORD v13; // eax
  ULONG v15; // [rsp+20h] [rbp-28h]
  ULONG v16; // [rsp+28h] [rbp-20h]

  v1 = (unsigned int)pszLogFileName;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v2 = L"InboxLOG.txt";
  if ( v1 )
    v2 = L"OutboxLOG.txt";
  v3 = (WCHAR *)BuildFullFileName(*(_QWORD *)&fDesiredAccess, v2);
  if ( !v3 )
  {
    v4 = 8;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 100;
LABEL_41:
      WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v7 = g_hOutboxActivityLogFile;
  v8 = &g_hInboxActivityLogFile;
  if ( v1 )
    v8 = &g_hOutboxActivityLogFile;
  else
    v7 = g_hInboxActivityLogFile;
  if ( !CloseHandle(v7) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v11 = 101;
    goto LABEL_20;
  }
  *v8 = (HANDLE)-1LL;
  if ( !DeleteFileW(v3) )
  {
    v13 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v13);
    }
  }
  LastError = (unsigned int)CreateLogFile((LPCWSTR)v1, fDesiredAccess, (DWORD)v8, v12, v15, v16);
  v4 = LastError;
  if ( LastError )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v11 = 103;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
    goto LABEL_42;
  }
  if ( !(unsigned int)SetFileToCurrentTime(*v8) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      goto LABEL_42;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_37;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, 0);
  }
  v5 = WPP_GLOBAL_Control;
LABEL_37:
  if ( v5 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 5u )
  {
    v6 = 105;
    goto LABEL_41;
  }
LABEL_42:
  pMemFree(v3);
  return v4;
}

```

## disassembly

```asm
0x1400297b0  push    rbx
0x1400297b2  push    rsi
0x1400297b3  push    rdi
0x1400297b4  push    r14; fFlagsAndAttributes
0x1400297b6  push    r15; fCreateDisposition
0x1400297b8  sub     rsp, 20h
0x1400297bc  mov     ebx, ecx
0x1400297be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400297c5  lea     r14, WPP_GLOBAL_Control
0x1400297cc  lea     r15, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x1400297d3  cmp     rcx, r14
0x1400297d6  jz      short loc_1400297F5
0x1400297d8  test    byte ptr [rcx+1Ch], 4
0x1400297dc  jz      short loc_1400297F5
0x1400297de  cmp     byte ptr [rcx+19h], 5
0x1400297e2  jb      short loc_1400297F5
0x1400297e4  mov     rcx, [rcx+10h]
0x1400297e8  mov     edx, 63h ; 'c'
0x1400297ed  mov     r8, r15
0x1400297f0  call    WPP_SF_
0x1400297f5  mov     rcx, qword ptr cs:fDesiredAccess
0x1400297fc  lea     rax, aOutboxlogTxt; "OutboxLOG.txt"
0x140029803  test    ebx, ebx
0x140029805  lea     rdx, aInboxlogTxt; "InboxLOG.txt"
0x14002980c  cmovnz  rdx, rax
0x140029810  call    BuildFullFileName
0x140029815  mov     rsi, rax
0x140029818  test    rax, rax
0x14002981b  jnz     short loc_14002984C
0x14002981d  lea     ebx, [rax+8]
0x140029820  mov     rcx, cs:WPP_GLOBAL_Control
0x140029827  cmp     rcx, r14
0x14002982a  jz      loc_1400299B4
0x140029830  test    byte ptr [rcx+1Ch], 4
0x140029834  jz      loc_1400299B4
0x14002983a  cmp     byte ptr [rcx+19h], 2
0x14002983e  jb      loc_1400299B4
0x140029844  lea     edx, [rax+64h]
0x140029847  jmp     loc_1400299A8
0x14002984c  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x140029853  lea     rax, ?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002985a  test    ebx, ebx
0x14002985c  lea     rdi, ?g_hInboxActivityLogFile@@3PEAXEA; void * g_hInboxActivityLogFile
0x140029863  cmovz   rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; hObject
0x14002986b  cmovnz  rdi, rax
0x14002986f  call    cs:__imp_CloseHandle
0x140029876  nop     dword ptr [rax+rax+00h]
0x14002987b  test    eax, eax
0x14002987d  jnz     short loc_1400298CA
0x14002987f  call    cs:__imp_GetLastError
0x140029886  nop     dword ptr [rax+rax+00h]
0x14002988b  mov     ebx, eax
0x14002988d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029894  cmp     rcx, r14
0x140029897  jz      loc_1400299B4
0x14002989d  test    byte ptr [rcx+1Ch], 4
0x1400298a1  jz      loc_1400299B4
0x1400298a7  cmp     byte ptr [rcx+19h], 2
0x1400298ab  jb      loc_1400299B4
0x1400298b1  mov     edx, 65h ; 'e'
0x1400298b6  mov     rcx, [rcx+10h]
0x1400298ba  mov     r9d, eax
0x1400298bd  mov     r8, r15
0x1400298c0  call    WPP_SF_d
0x1400298c5  jmp     loc_1400299B4
0x1400298ca  mov     rcx, rsi; lpFileName
0x1400298cd  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1400298d4  call    cs:__imp_DeleteFileW
0x1400298db  nop     dword ptr [rax+rax+00h]
0x1400298e0  test    eax, eax
0x1400298e2  jnz     short loc_14002991C
0x1400298e4  call    cs:__imp_GetLastError
0x1400298eb  nop     dword ptr [rax+rax+00h]
0x1400298f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400298f7  cmp     rcx, r14
0x1400298fa  jz      short loc_14002991C
0x1400298fc  test    byte ptr [rcx+1Ch], 4
0x140029900  jz      short loc_14002991C
0x140029902  cmp     byte ptr [rcx+19h], 2
0x140029906  jb      short loc_14002991C
0x140029908  mov     rcx, [rcx+10h]
0x14002990c  mov     edx, 66h ; 'f'
0x140029911  mov     r9d, eax
0x140029914  mov     r8, r15
0x140029917  call    WPP_SF_d
0x14002991c  mov     rdx, qword ptr cs:fDesiredAccess; fDesiredAccess
0x140029923  mov     r8, rdi; dwShareMode
0x140029926  mov     ecx, ebx; pszLogFileName
0x140029928  call    CreateLogFile
0x14002992d  mov     ebx, eax
0x14002992f  test    eax, eax
0x140029931  jz      short loc_140029955
0x140029933  mov     rcx, cs:WPP_GLOBAL_Control
0x14002993a  cmp     rcx, r14
0x14002993d  jz      short loc_1400299B4
0x14002993f  test    byte ptr [rcx+1Ch], 4
0x140029943  jz      short loc_1400299B4
0x140029945  cmp     byte ptr [rcx+19h], 2
0x140029949  jb      short loc_1400299B4
0x14002994b  mov     edx, 67h ; 'g'
0x140029950  jmp     loc_1400298B6
0x140029955  mov     rcx, [rdi]; hFile
0x140029958  call    SetFileToCurrentTime
0x14002995d  test    eax, eax
0x14002995f  jnz     short loc_14002998B
0x140029961  mov     rcx, cs:WPP_GLOBAL_Control
0x140029968  cmp     rcx, r14
0x14002996b  jz      short loc_1400299B4
0x14002996d  test    byte ptr [rcx+1Ch], 4
0x140029971  jz      short loc_140029992
0x140029973  cmp     byte ptr [rcx+19h], 2
0x140029977  jb      short loc_140029992
0x140029979  mov     rcx, [rcx+10h]
0x14002997d  lea     edx, [rax+68h]
0x140029980  xor     r9d, r9d
0x140029983  mov     r8, r15
0x140029986  call    WPP_SF_d
0x14002998b  mov     rcx, cs:WPP_GLOBAL_Control
0x140029992  cmp     rcx, r14
0x140029995  jz      short loc_1400299B4
0x140029997  test    byte ptr [rcx+1Ch], 4
0x14002999b  jz      short loc_1400299B4
0x14002999d  cmp     byte ptr [rcx+19h], 5
0x1400299a1  jb      short loc_1400299B4
0x1400299a3  mov     edx, 69h ; 'i'
0x1400299a8  mov     rcx, [rcx+10h]
0x1400299ac  mov     r8, r15
0x1400299af  call    WPP_SF_
0x1400299b4  mov     rcx, rsi; lpMem
0x1400299b7  call    pMemFree
0x1400299bc  mov     eax, ebx
0x1400299be  add     rsp, 20h
0x1400299c2  pop     r15
0x1400299c4  pop     r14
0x1400299c6  pop     rdi
0x1400299c7  pop     rsi
0x1400299c8  pop     rbx
0x1400299c9  retn
```
