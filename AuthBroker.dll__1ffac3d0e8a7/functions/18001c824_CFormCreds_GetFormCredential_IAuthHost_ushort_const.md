# CFormCreds::GetFormCredential(IAuthHost *,ushort const *)

- ea: `0x18001c824`
- end: `0x18001c972`
- name: `?GetFormCredential@CFormCreds@@QEAAJPEAUIAuthHost@@PEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(CFormCreds *this, IAuthHost *pAuthHost, const wchar_t *lpcwszUrl)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012e20`

## callees

- `0x18001c090`
- `0x18001c7a4`
- `0x18001c824`
- `0x1800204e2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c90d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001c8ff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001c8ff`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001c927`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001c927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c95d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c95d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c85e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c8b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c85e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c8b2`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001c883`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001c883`

## pseudocode

```c
__int64 __fastcall CFormCreds::GetFormCredential(CFormCreds *this, IAuthHost *pAuthHost, const wchar_t *lpcwszUrl)
{
  void *v6; // rdi
  LPSTREAM *v7; // rax
  _GET_FORM_CREDENTIAL_PARAM *v8; // rsi
  int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // rdx
  wchar_t *v12; // rax
  HANDLE v13; // rax
  signed int LastError; // eax
  unsigned int dwThreadId; // [rsp+78h] [rbp+10h] BYREF

  dwThreadId = 0;
  v6 = 0;
  if ( !pAuthHost || !lpcwszUrl )
  {
    v9 = -2147024809;
    goto LABEL_16;
  }
  v7 = (LPSTREAM *)LocalAlloc(0x40u, 0x10u);
  v8 = (_GET_FORM_CREDENTIAL_PARAM *)v7;
  if ( !v7 )
  {
LABEL_4:
    v9 = -2147024882;
    goto $Cleanup_8;
  }
  v9 = CoMarshalInterThreadInterfaceInStream(&GUID_5de7918b_bfd7_4c1e_b4e0_b16d0a3ea76b, pAuthHost, v7);
  if ( v9 >= 0 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( lpcwszUrl[v11] );
    v12 = (wchar_t *)LocalAlloc(0x40u, 2 * v11 + 2);
    v8->lpwszUrl = v12;
    if ( !v12 )
      goto LABEL_4;
    do
      ++v10;
    while ( lpcwszUrl[v10] );
    memcpy_0(v12, lpcwszUrl, 2 * v10 + 2);
    v13 = CreateThread(0, 0, CFormCreds::GetFormCredentialThread, v8, 4u, &dwThreadId);
    v6 = v13;
    if ( v13 && ResumeThread(v13) != -1 )
    {
      CFormCreds::AddThread(this, v6);
      v6 = 0;
      v9 = 0;
LABEL_16:
      v8 = 0;
      goto $Cleanup_8;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
$Cleanup_8:
  FreeGetFormCredentialParam(v8);
  if ( v6 )
    CloseHandle(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c824  push    rbx
0x18001c826  push    rbp
0x18001c827  push    rsi
0x18001c828  push    rdi
0x18001c829  push    r14
0x18001c82b  push    r15
0x18001c82d  sub     rsp, 38h
0x18001c831  xor     r15d, r15d
0x18001c834  mov     rbp, lpcwszUrl
0x18001c837  mov     [rsp+68h+dwThreadId], r15d
0x18001c83c  mov     rbx, pAuthHost
0x18001c83f  mov     r14, this
0x18001c842  mov     edi, r15d
0x18001c845  test    pAuthHost, pAuthHost
0x18001c848  jz      loc_18001C945
0x18001c84e  test    lpcwszUrl, lpcwszUrl
0x18001c851  jz      loc_18001C945
0x18001c857  lea     edx, [r15+10h]; uBytes
0x18001c85b  lea     ecx, [pAuthHost+30h]; uFlags
0x18001c85e  call    cs:__imp_LocalAlloc
0x18001c864  mov     rsi, rax
0x18001c867  test    rax, rax
0x18001c86a  jnz     short loc_18001C876
0x18001c86c  mov     ebx, 8007000Eh
0x18001c871  jmp     $Cleanup_8
0x18001c876  mov     lpcwszUrl, rsi; ppStm
0x18001c879  lea     this, _GUID_5de7918b_bfd7_4c1e_b4e0_b16d0a3ea76b; riid
0x18001c880  mov     pAuthHost, rbx; pUnk
0x18001c883  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18001c889  mov     ebx, eax
0x18001c88b  test    eax, eax
0x18001c88d  js      $Cleanup_8
0x18001c893  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c897  mov     pAuthHost, rbx
0x18001c89a  inc     pAuthHost
0x18001c89d  cmp     [rbp+pAuthHost*2+0], r15w
0x18001c8a3  jnz     short loc_18001C89A
0x18001c8a5  lea     pAuthHost, ds:2[pAuthHost*2]; uBytes
0x18001c8ad  mov     ecx, 40h ; '@'; uFlags
0x18001c8b2  call    cs:__imp_LocalAlloc
0x18001c8b8  mov     [rsi+8], rax
0x18001c8bc  test    rax, rax
0x18001c8bf  jz      short loc_18001C86C
0x18001c8c1  inc     rbx
0x18001c8c4  cmp     [rbp+rbx*2+0], r15w
0x18001c8ca  jnz     short loc_18001C8C1
0x18001c8cc  lea     lpcwszUrl, ds:2[rbx*2]; Size
0x18001c8d4  mov     pAuthHost, rbp; Src
0x18001c8d7  mov     this, rax; void *
0x18001c8da  call    memcpy_0
0x18001c8df  lea     rax, [rsp+68h+dwThreadId]
0x18001c8e4  mov     r9, rsi; lpParameter
0x18001c8e7  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18001c8ec  lea     lpcwszUrl, ?GetFormCredentialThread@CFormCreds@@SAKPEAX@Z; lpStartAddress
0x18001c8f3  xor     edx, edx; dwStackSize
0x18001c8f5  mov     [rsp+68h+dwCreationFlags], 4; dwCreationFlags
0x18001c8fd  xor     ecx, ecx; lpThreadAttributes
0x18001c8ff  call    cs:__imp_CreateThread
0x18001c905  mov     rdi, rax
0x18001c908  test    rax, rax
0x18001c90b  jnz     short loc_18001C924
0x18001c90d  call    cs:__imp_GetLastError
0x18001c913  mov     ebx, eax
0x18001c915  test    eax, eax
0x18001c917  jle     short $Cleanup_8
0x18001c919  movzx   ebx, ax
0x18001c91c  or      ebx, 80070000h
0x18001c922  jmp     short $Cleanup_8
0x18001c924  mov     this, rdi; hThread
0x18001c927  call    cs:__imp_ResumeThread
0x18001c92d  cmp     eax, 0FFFFFFFFh
0x18001c930  jz      short loc_18001C90D
0x18001c932  mov     pAuthHost, rdi; hThreadHandle
0x18001c935  mov     this, r14; this
0x18001c938  call    ?AddThread@CFormCreds@@AEAAXPEAX@Z; CFormCreds::AddThread(void *)
0x18001c93d  mov     rdi, r15
0x18001c940  mov     ebx, r15d
0x18001c943  jmp     short loc_18001C94A
0x18001c945  mov     ebx, 80070057h
0x18001c94a  mov     rsi, r15
0x18001c94d  mov     this, rsi; pParam
0x18001c950  call    ?FreeGetFormCredentialParam@@YAXPEAU_GET_FORM_CREDENTIAL_PARAM@@@Z; FreeGetFormCredentialParam(_GET_FORM_CREDENTIAL_PARAM *)
0x18001c955  test    rdi, rdi
0x18001c958  jz      short loc_18001C963
0x18001c95a  mov     this, rdi; hObject
0x18001c95d  call    cs:__imp_CloseHandle
0x18001c963  mov     eax, ebx
0x18001c965  add     rsp, 38h
0x18001c969  pop     r15
0x18001c96b  pop     r14
0x18001c96d  pop     rdi
0x18001c96e  pop     rsi
0x18001c96f  pop     rbp
0x18001c970  pop     rbx
0x18001c971  retn
```
