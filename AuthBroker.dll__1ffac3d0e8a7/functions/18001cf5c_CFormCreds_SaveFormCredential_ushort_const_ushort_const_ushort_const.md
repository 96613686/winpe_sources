# CFormCreds::SaveFormCredential(ushort const *,ushort const *,ushort const *)

- ea: `0x18001cf5c`
- end: `0x18001d142`
- name: `?SaveFormCredential@CFormCreds@@QEAAJPEBG00@Z`
- size: `486`
- prototype: `HRESULT __fastcall(CFormCreds *this, const wchar_t *lpcwszUrl, const wchar_t *lpcwszUserName, const wchar_t *lpcwszPassword)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013d9c`

## callees

- `0x18001c090`
- `0x18001c7e4`
- `0x18001cf5c`
- `0x1800204e2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d0d9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d0cb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d0cb`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001d0f3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001d0f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d129`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cfa7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cfde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d02a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d074`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cfa7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cfde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d02a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d074`

## pseudocode

```c
__int64 __fastcall CFormCreds::SaveFormCredential(
        CFormCreds *this,
        const wchar_t *lpcwszUrl,
        const wchar_t *lpcwszUserName,
        const wchar_t *lpcwszPassword)
{
  void *v8; // rsi
  _SAVE_FORM_CREDENTIAL_PARAM *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rbx
  __int64 v12; // rdx
  wchar_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  wchar_t *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  wchar_t *v19; // rax
  HANDLE v20; // rax
  signed int LastError; // eax
  unsigned int dwThreadId; // [rsp+88h] [rbp+10h] BYREF

  dwThreadId = 0;
  v8 = 0;
  if ( !lpcwszUrl || !lpcwszUserName || !lpcwszPassword )
  {
    v10 = -2147024809;
    goto LABEL_26;
  }
  v9 = (_SAVE_FORM_CREDENTIAL_PARAM *)LocalAlloc(0x40u, 0x28u);
  if ( !v9 )
    goto LABEL_5;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( lpcwszUrl[v12] );
  v13 = (wchar_t *)LocalAlloc(0x40u, 2 * v12 + 2);
  v9->lpwszUrl = v13;
  if ( !v13 )
    goto LABEL_5;
  v14 = -1;
  do
    ++v14;
  while ( lpcwszUrl[v14] );
  memcpy_0(v13, lpcwszUrl, 2 * v14 + 2);
  v15 = -1;
  do
    ++v15;
  while ( lpcwszUserName[v15] );
  v16 = (wchar_t *)LocalAlloc(0x40u, 2 * v15 + 2);
  v9->lpwszUserName = v16;
  if ( !v16 )
    goto LABEL_5;
  v17 = -1;
  do
    ++v17;
  while ( lpcwszUserName[v17] );
  memcpy_0(v16, lpcwszUserName, 2 * v17 + 2);
  v18 = -1;
  do
    ++v18;
  while ( lpcwszPassword[v18] );
  v19 = (wchar_t *)LocalAlloc(0x40u, 2 * v18 + 2);
  v9->lpwszPassword = v19;
  if ( !v19 )
  {
LABEL_5:
    v10 = -2147024882;
    goto $Cleanup_11;
  }
  do
    ++v11;
  while ( lpcwszPassword[v11] );
  memcpy_0(v19, lpcwszPassword, 2 * v11 + 2);
  v9->pThis = this;
  v20 = CreateThread(0, 0, CFormCreds::SaveFormCredentialThread, v9, 4u, &dwThreadId);
  v8 = v20;
  if ( v20 && ResumeThread(v20) != -1 )
  {
    CFormCreds::AddThread(this, v8);
    v8 = 0;
    v10 = 0;
LABEL_26:
    v9 = 0;
    goto $Cleanup_11;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
$Cleanup_11:
  FreeSaveFormCredentialParam(v9);
  if ( v8 )
    CloseHandle(v8);
  return v10;
}

```

## disassembly

```asm
0x18001cf5c  mov     rax, rsp
0x18001cf5f  push    rbx
0x18001cf60  push    rbp
0x18001cf61  push    rsi
0x18001cf62  push    rdi
0x18001cf63  push    r12
0x18001cf65  push    r13
0x18001cf67  push    r14
0x18001cf69  push    r15
0x18001cf6b  sub     rsp, 38h
0x18001cf6f  xor     r13d, r13d
0x18001cf72  mov     r15, lpcwszPassword
0x18001cf75  mov     [rax+10h], r13d
0x18001cf79  mov     r14, lpcwszUserName
0x18001cf7c  mov     rbp, lpcwszUrl
0x18001cf7f  mov     r12, this
0x18001cf82  mov     esi, r13d
0x18001cf85  test    lpcwszUrl, lpcwszUrl
0x18001cf88  jz      loc_18001D111
0x18001cf8e  test    lpcwszUserName, lpcwszUserName
0x18001cf91  jz      loc_18001D111
0x18001cf97  test    lpcwszPassword, lpcwszPassword
0x18001cf9a  jz      loc_18001D111
0x18001cfa0  lea     edx, [r13+28h]; uBytes
0x18001cfa4  lea     ecx, [lpcwszUrl+18h]; uFlags
0x18001cfa7  call    cs:__imp_LocalAlloc
0x18001cfad  mov     rdi, rax
0x18001cfb0  test    rax, rax
0x18001cfb3  jnz     short loc_18001CFBF
0x18001cfb5  mov     ebx, 8007000Eh
0x18001cfba  jmp     $Cleanup_11
0x18001cfbf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001cfc3  mov     lpcwszUrl, rbx
0x18001cfc6  inc     lpcwszUrl
0x18001cfc9  cmp     [rbp+lpcwszUrl*2+0], r13w
0x18001cfcf  jnz     short loc_18001CFC6
0x18001cfd1  lea     lpcwszUrl, ds:2[lpcwszUrl*2]; uBytes
0x18001cfd9  mov     ecx, 40h ; '@'; uFlags
0x18001cfde  call    cs:__imp_LocalAlloc
0x18001cfe4  mov     [rdi+8], rax
0x18001cfe8  test    rax, rax
0x18001cfeb  jz      short loc_18001CFB5
0x18001cfed  mov     lpcwszUserName, rbx
0x18001cff0  inc     lpcwszUserName
0x18001cff3  cmp     [rbp+lpcwszUserName*2+0], r13w
0x18001cff9  jnz     short loc_18001CFF0
0x18001cffb  lea     lpcwszUserName, ds:2[lpcwszUserName*2]; Size
0x18001d003  mov     lpcwszUrl, rbp; Src
0x18001d006  mov     this, rax; void *
0x18001d009  call    memcpy_0
0x18001d00e  mov     lpcwszUrl, rbx
0x18001d011  inc     lpcwszUrl
0x18001d014  cmp     [r14+lpcwszUrl*2], r13w
0x18001d019  jnz     short loc_18001D011
0x18001d01b  mov     ebp, 40h ; '@'
0x18001d020  lea     lpcwszUrl, ds:2[lpcwszUrl*2]; uBytes
0x18001d028  mov     ecx, ebp; uFlags
0x18001d02a  call    cs:__imp_LocalAlloc
0x18001d030  mov     [rdi+10h], rax
0x18001d034  test    rax, rax
0x18001d037  jz      loc_18001CFB5
0x18001d03d  mov     lpcwszUserName, rbx
0x18001d040  inc     lpcwszUserName
0x18001d043  cmp     [r14+lpcwszUserName*2], r13w
0x18001d048  jnz     short loc_18001D040
0x18001d04a  lea     lpcwszUserName, ds:2[lpcwszUserName*2]; Size
0x18001d052  mov     lpcwszUrl, r14; Src
0x18001d055  mov     this, rax; void *
0x18001d058  call    memcpy_0
0x18001d05d  mov     lpcwszUrl, rbx
0x18001d060  inc     lpcwszUrl
0x18001d063  cmp     [r15+lpcwszUrl*2], r13w
0x18001d068  jnz     short loc_18001D060
0x18001d06a  lea     lpcwszUrl, ds:2[lpcwszUrl*2]; uBytes
0x18001d072  mov     ecx, ebp; uFlags
0x18001d074  call    cs:__imp_LocalAlloc
0x18001d07a  mov     [rdi+18h], rax
0x18001d07e  test    rax, rax
0x18001d081  jz      loc_18001CFB5
0x18001d087  inc     rbx
0x18001d08a  cmp     [r15+rbx*2], r13w
0x18001d08f  jnz     short loc_18001D087
0x18001d091  lea     lpcwszUserName, ds:2[rbx*2]; Size
0x18001d099  mov     lpcwszUrl, r15; Src
0x18001d09c  mov     this, rax; void *
0x18001d09f  call    memcpy_0
0x18001d0a4  lea     rax, [rsp+78h+dwThreadId]
0x18001d0ac  mov     [rdi+20h], r12
0x18001d0b0  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18001d0b5  lea     lpcwszUserName, ?SaveFormCredentialThread@CFormCreds@@SAKPEAX@Z; lpStartAddress
0x18001d0bc  mov     lpcwszPassword, rdi; lpParameter
0x18001d0bf  mov     [rsp+78h+dwCreationFlags], 4; dwCreationFlags
0x18001d0c7  xor     edx, edx; dwStackSize
0x18001d0c9  xor     ecx, ecx; lpThreadAttributes
0x18001d0cb  call    cs:__imp_CreateThread
0x18001d0d1  mov     rsi, rax
0x18001d0d4  test    rax, rax
0x18001d0d7  jnz     short loc_18001D0F0
0x18001d0d9  call    cs:__imp_GetLastError
0x18001d0df  mov     ebx, eax
0x18001d0e1  test    eax, eax
0x18001d0e3  jle     short $Cleanup_11
0x18001d0e5  movzx   ebx, ax
0x18001d0e8  or      ebx, 80070000h
0x18001d0ee  jmp     short $Cleanup_11
0x18001d0f0  mov     this, rsi; hThread
0x18001d0f3  call    cs:__imp_ResumeThread
0x18001d0f9  cmp     eax, 0FFFFFFFFh
0x18001d0fc  jz      short loc_18001D0D9
0x18001d0fe  mov     lpcwszUrl, rsi; hThreadHandle
0x18001d101  mov     this, r12; this
0x18001d104  call    ?AddThread@CFormCreds@@AEAAXPEAX@Z; CFormCreds::AddThread(void *)
0x18001d109  mov     rsi, r13
0x18001d10c  mov     ebx, r13d
0x18001d10f  jmp     short loc_18001D116
0x18001d111  mov     ebx, 80070057h
0x18001d116  mov     rdi, r13
0x18001d119  mov     this, rdi; pParam
0x18001d11c  call    ?FreeSaveFormCredentialParam@@YAXPEAU_SAVE_FORM_CREDENTIAL_PARAM@@@Z; FreeSaveFormCredentialParam(_SAVE_FORM_CREDENTIAL_PARAM *)
0x18001d121  test    rsi, rsi
0x18001d124  jz      short loc_18001D12F
0x18001d126  mov     this, rsi; hObject
0x18001d129  call    cs:__imp_CloseHandle
0x18001d12f  mov     eax, ebx
0x18001d131  add     rsp, 38h
0x18001d135  pop     r15
0x18001d137  pop     r14
0x18001d139  pop     r13
0x18001d13b  pop     r12
0x18001d13d  pop     rdi
0x18001d13e  pop     rsi
0x18001d13f  pop     rbp
0x18001d140  pop     rbx
0x18001d141  retn
```
