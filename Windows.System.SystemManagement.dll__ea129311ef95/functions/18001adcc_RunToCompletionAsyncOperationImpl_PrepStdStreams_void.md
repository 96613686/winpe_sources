# RunToCompletionAsyncOperationImpl::PrepStdStreams(void)

- ea: `0x18001adcc`
- end: `0x18001aec7`
- name: `?PrepStdStreams@RunToCompletionAsyncOperationImpl@@AEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019d90`

## callees

- `0x18001adcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aea5`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001ae26`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001ae60`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001ae9b`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001ae26`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001ae60`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18001ae9b`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001ae0e`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001ae4c`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001ae86`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001ae0e`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001ae4c`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18001ae86`

## pseudocode

```c
__int64 __fastcall RunToCompletionAsyncOperationImpl::PrepStdStreams(void **this)
{
  HANDLE *v1; // rdi
  HANDLE *v3; // rdi
  unsigned int v4; // ebx
  signed int LastError; // eax
  _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+20h] [rbp-28h] BYREF

  v1 = this + 36;
  *(_QWORD *)&PipeAttributes.nLength = 24;
  *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
  PipeAttributes.lpSecurityDescriptor = 0;
  if ( !CreatePipe(this + 36, this + 38, &PipeAttributes, 0x2000u)
    || !SetHandleInformation(*v1, 1u, 0)
    || !CreatePipe(this + 40, this + 42, &PipeAttributes, 0x2000u)
    || !SetHandleInformation(this[40], 1u, 0)
    || (v3 = this + 46, !CreatePipe(this + 44, this + 46, &PipeAttributes, 0x2000u))
    || (v4 = 0, !SetHandleInformation(*v3, 1u, 0)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x18001adcc  mov     rax, rsp
0x18001adcf  mov     [rax+8], rbx
0x18001add3  push    rdi
0x18001add4  sub     rsp, 40h
0x18001add8  lea     rdi, [rcx+120h]
0x18001addf  mov     qword ptr [rax-28h], 18h
0x18001ade7  mov     rbx, rcx
0x18001adea  mov     qword ptr [rax-18h], 1
0x18001adf2  lea     rdx, [rcx+130h]; hWritePipe
0x18001adf9  mov     qword ptr [rax-20h], 0
0x18001ae01  mov     rcx, rdi; hReadPipe
0x18001ae04  lea     r8, [rax-28h]; lpPipeAttributes
0x18001ae08  mov     r9d, 2000h; nSize
0x18001ae0e  call    cs:__imp_CreatePipe
0x18001ae14  test    eax, eax
0x18001ae16  jz      loc_18001AEA5
0x18001ae1c  mov     rcx, [rdi]; hObject
0x18001ae1f  xor     r8d, r8d; dwFlags
0x18001ae22  lea     edx, [r8+1]; dwMask
0x18001ae26  call    cs:__imp_SetHandleInformation
0x18001ae2c  test    eax, eax
0x18001ae2e  jz      short loc_18001AEA5
0x18001ae30  lea     rdi, [rbx+140h]
0x18001ae37  mov     r9d, 2000h; nSize
0x18001ae3d  mov     rcx, rdi; hReadPipe
0x18001ae40  lea     rdx, [rbx+150h]; hWritePipe
0x18001ae47  lea     r8, [rsp+48h+PipeAttributes]; lpPipeAttributes
0x18001ae4c  call    cs:__imp_CreatePipe
0x18001ae52  test    eax, eax
0x18001ae54  jz      short loc_18001AEA5
0x18001ae56  mov     rcx, [rdi]; hObject
0x18001ae59  xor     r8d, r8d; dwFlags
0x18001ae5c  lea     edx, [r8+1]; dwMask
0x18001ae60  call    cs:__imp_SetHandleInformation
0x18001ae66  test    eax, eax
0x18001ae68  jz      short loc_18001AEA5
0x18001ae6a  lea     rdi, [rbx+170h]
0x18001ae71  mov     r9d, 2000h; nSize
0x18001ae77  mov     rdx, rdi; hWritePipe
0x18001ae7a  lea     rcx, [rbx+160h]; hReadPipe
0x18001ae81  lea     r8, [rsp+48h+PipeAttributes]; lpPipeAttributes
0x18001ae86  call    cs:__imp_CreatePipe
0x18001ae8c  test    eax, eax
0x18001ae8e  jz      short loc_18001AEA5
0x18001ae90  mov     rcx, [rdi]; hObject
0x18001ae93  xor     ebx, ebx
0x18001ae95  xor     r8d, r8d; dwFlags
0x18001ae98  lea     edx, [rbx+1]; dwMask
0x18001ae9b  call    cs:__imp_SetHandleInformation
0x18001aea1  test    eax, eax
0x18001aea3  jnz     short loc_18001AEBA
0x18001aea5  call    cs:__imp_GetLastError
0x18001aeab  mov     ebx, eax
0x18001aead  test    eax, eax
0x18001aeaf  jle     short loc_18001AEBA
0x18001aeb1  movzx   ebx, ax
0x18001aeb4  or      ebx, 80070000h
0x18001aeba  mov     eax, ebx
0x18001aebc  mov     rbx, [rsp+48h+arg_0]
0x18001aec1  add     rsp, 40h
0x18001aec5  pop     rdi
0x18001aec6  retn
```
