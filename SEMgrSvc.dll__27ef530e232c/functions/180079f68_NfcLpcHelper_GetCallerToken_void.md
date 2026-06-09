# NfcLpcHelper::GetCallerToken(void * *)

- ea: `0x180079f68`
- end: `0x18007a075`
- name: `?GetCallerToken@NfcLpcHelper@@SAJPEAPEAX@Z`
- size: `269`
- prototype: `static int(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070440`
- `0x18007a0d8`

## callees

- `0x18000c944`
- `0x18000c964`
- `0x180079f68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180079f83`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180079f83`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180079fa8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007a048`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180079fa8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007a048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079fd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079fec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079ffb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a012`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079fe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a05d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079fe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a05d`

## string_xrefs

- `0x180079f94`: `onecoreuap\ds\nfc\shared\nfccommon\lib\nfclpchelper.cpp`
- `0x18007a021`: `onecoreuap\ds\nfc\shared\nfccommon\lib\nfclpchelper.cpp`

## pseudocode

```c
__int64 __fastcall NfcLpcHelper::GetCallerToken(void **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HANDLE v5; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  hObject = 0;
  v2 = CoImpersonateClient();
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\nfclpchelper.cpp",
      (const char *)(unsigned int)v2,
      v9);
LABEL_3:
    CoRevertToSelf();
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v3;
  }
  v5 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  hObject = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
  {
    v3 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x10,
           (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\nfclpchelper.cpp",
           v8);
    goto LABEL_3;
  }
  *a1 = hObject;
  hObject = 0;
  CoRevertToSelf();
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180079f68  mov     [rsp+arg_0], rbx
0x180079f6d  mov     [rsp+arg_10], rsi
0x180079f72  push    rdi; int
0x180079f73  sub     rsp, 20h
0x180079f77  mov     rsi, rcx
0x180079f7a  mov     [rsp+28h+hObject], 0
0x180079f83  call    cs:__imp_CoImpersonateClient
0x180079f89  mov     ebx, eax
0x180079f8b  test    eax, eax
0x180079f8d  jns     short loc_180079FCA
0x180079f8f  mov     rcx, [rsp+28h]; this
0x180079f94  lea     r8, aOnecoreuapDsNf_4; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x180079f9b  mov     r9d, eax; char *
0x180079f9e  mov     edx, 0Fh; void *
0x180079fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079fa8  call    cs:__imp_CoRevertToSelf
0x180079fae  mov     rcx, [rsp+28h+hObject]; hObject
0x180079fb3  lea     rdx, [rcx-1]
0x180079fb7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180079fbb  ja      short loc_180079FC3
0x180079fbd  call    cs:__imp_CloseHandle
0x180079fc3  mov     eax, ebx
0x180079fc5  jmp     loc_18007A065
0x180079fca  mov     rdi, [rsp+28h+hObject]
0x180079fcf  lea     rax, [rdi-1]
0x180079fd3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180079fd7  ja      short loc_180079FF2
0x180079fd9  call    cs:__imp_GetLastError
0x180079fdf  mov     rcx, rdi; hObject
0x180079fe2  mov     ebx, eax
0x180079fe4  call    cs:__imp_CloseHandle
0x180079fea  mov     ecx, ebx; dwErrCode
0x180079fec  call    cs:__imp_SetLastError
0x180079ff2  mov     [rsp+28h+hObject], 0
0x180079ffb  call    cs:__imp_GetCurrentThread
0x18007a001  mov     edx, 8; DesiredAccess
0x18007a006  lea     r9, [rsp+28h+hObject]; TokenHandle
0x18007a00b  mov     rcx, rax; ThreadHandle
0x18007a00e  lea     r8d, [rdx-7]; OpenAsSelf
0x18007a012  call    cs:__imp_OpenThreadToken
0x18007a018  test    eax, eax
0x18007a01a  jnz     short loc_18007A037
0x18007a01c  mov     rcx, [rsp+28h]; this
0x18007a021  lea     r8, aOnecoreuapDsNf_4; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x18007a028  lea     edx, [rax+10h]; void *
0x18007a02b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a030  mov     ebx, eax
0x18007a032  jmp     loc_180079FA8
0x18007a037  mov     rax, [rsp+28h+hObject]
0x18007a03c  mov     [rsi], rax
0x18007a03f  mov     [rsp+28h+hObject], 0
0x18007a048  call    cs:__imp_CoRevertToSelf
0x18007a04e  mov     rcx, [rsp+28h+hObject]; hObject
0x18007a053  lea     rax, [rcx-1]
0x18007a057  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007a05b  ja      short loc_18007A063
0x18007a05d  call    cs:__imp_CloseHandle
0x18007a063  xor     eax, eax
0x18007a065  mov     rbx, [rsp+28h+arg_0]
0x18007a06a  mov     rsi, [rsp+28h+arg_10]
0x18007a06f  add     rsp, 20h
0x18007a073  pop     rdi
0x18007a074  retn
```
