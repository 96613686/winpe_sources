# CSecurity::BeginRevertToSelf(void * *,ulong)

- ea: `0x1800fe7a0`
- end: `0x1800fe8e0`
- name: `?BeginRevertToSelf@CSecurity@@SAHPEAPEAXK@Z`
- size: `320`
- prototype: `__int64 __fastcall(void **, DWORD DesiredAccess)`
- caller_count: `15`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009858c`
- `0x18009a418`
- `0x1800fbd00`
- `0x180113530`
- `0x180114750`
- `0x18012d6f0`
- `0x18012d8f4`
- `0x1801305bc`
- `0x1801307b8`
- `0x180131180`
- `0x1801312ec`
- `0x180155854`
- `0x18019bf20`
- `0x18019d1e0`
- `0x18019d760`

## callees

- `0x180005d10`
- `0x18002aee0`
- `0x1800fe7a0`
- `0x180112380`
- `0x1801123a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fe876`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fe876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe88d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe88d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe7e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe7e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe7f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe7f9`

## pseudocode

```c
__int64 __fastcall CSecurity::BeginRevertToSelf(void **a1, DWORD DesiredAccess)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 304, L"304", 0x54Fu, 0);
    return 0;
  }
  *a1 = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, DesiredAccess, 1, a1) )
  {
    if ( !(unsigned int)CSecurity::RevertToSelf() )
    {
      CloseHandle(*a1);
      *a1 = (void *)-1LL;
      return 0;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v8 = 21;
      goto LABEL_18;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, LastError);
      SetLastError(LastError);
      return 0;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v8 = 19;
LABEL_18:
      WPP_SF_(v7[2], v8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800fe7a0  mov     [rsp+arg_0], rbx
0x1800fe7a5  push    rdi
0x1800fe7a6  sub     rsp, 30h
0x1800fe7aa  mov     edi, edx
0x1800fe7ac  mov     rbx, rcx
0x1800fe7af  test    rcx, rcx
0x1800fe7b2  jnz     short loc_1800FE7DE
0x1800fe7b4  mov     [rsp+38h+var_18], rcx; struct IRequestContext *
0x1800fe7b9  lea     r8, a304; "304"
0x1800fe7c0  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x1800fe7c7  mov     r9d, 54Fh; unsigned int
0x1800fe7cd  mov     edx, 130h; unsigned int
0x1800fe7d2  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800fe7d7  xor     eax, eax
0x1800fe7d9  jmp     loc_1800FE8D5
0x1800fe7de  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800fe7e5  call    cs:__imp_GetCurrentThread
0x1800fe7eb  mov     r9, rbx; TokenHandle
0x1800fe7ee  mov     r8d, 1; OpenAsSelf
0x1800fe7f4  mov     rcx, rax; ThreadHandle
0x1800fe7f7  mov     edx, edi; DesiredAccess
0x1800fe7f9  call    cs:__imp_OpenThreadToken
0x1800fe7ff  test    eax, eax
0x1800fe801  jnz     short loc_1800FE881
0x1800fe803  call    cs:__imp_GetLastError
0x1800fe809  mov     ebx, eax
0x1800fe80b  cmp     eax, 3F0h
0x1800fe810  jnz     short loc_1800FE840
0x1800fe812  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe819  lea     rax, WPP_GLOBAL_Control
0x1800fe820  cmp     rcx, rax
0x1800fe823  jz      loc_1800FE8D0
0x1800fe829  test    dword ptr [rcx+1Ch], 400h
0x1800fe830  jz      loc_1800FE8D0
0x1800fe836  mov     edx, 13h
0x1800fe83b  jmp     loc_1800FE8C0
0x1800fe840  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe847  lea     rax, WPP_GLOBAL_Control
0x1800fe84e  cmp     rcx, rax
0x1800fe851  jz      short loc_1800FE874
0x1800fe853  test    dword ptr [rcx+1Ch], 400h
0x1800fe85a  jz      short loc_1800FE874
0x1800fe85c  mov     rcx, [rcx+10h]
0x1800fe860  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800fe867  mov     edx, 14h
0x1800fe86c  mov     r9d, ebx
0x1800fe86f  call    WPP_SF_d
0x1800fe874  mov     ecx, ebx; dwErrCode
0x1800fe876  call    cs:__imp_SetLastError
0x1800fe87c  jmp     loc_1800FE7D7
0x1800fe881  call    ?RevertToSelf@CSecurity@@SAHXZ; CSecurity::RevertToSelf(void)
0x1800fe886  test    eax, eax
0x1800fe888  jnz     short loc_1800FE89F
0x1800fe88a  mov     rcx, [rbx]; hObject
0x1800fe88d  call    cs:__imp_CloseHandle
0x1800fe893  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800fe89a  jmp     loc_1800FE7D7
0x1800fe89f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe8a6  lea     rax, WPP_GLOBAL_Control
0x1800fe8ad  cmp     rcx, rax
0x1800fe8b0  jz      short loc_1800FE8D0
0x1800fe8b2  test    dword ptr [rcx+1Ch], 400h
0x1800fe8b9  jz      short loc_1800FE8D0
0x1800fe8bb  mov     edx, 15h
0x1800fe8c0  mov     rcx, [rcx+10h]
0x1800fe8c4  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800fe8cb  call    WPP_SF_
0x1800fe8d0  mov     eax, 1
0x1800fe8d5  mov     rbx, [rsp+38h+arg_0]
0x1800fe8da  add     rsp, 30h
0x1800fe8de  pop     rdi
0x1800fe8df  retn
```
