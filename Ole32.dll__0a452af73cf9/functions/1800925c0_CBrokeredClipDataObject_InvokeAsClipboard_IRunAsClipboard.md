# CBrokeredClipDataObject::InvokeAsClipboard(IRunAsClipboard *)

- ea: `0x1800925c0`
- end: `0x180092703`
- name: `?InvokeAsClipboard@CBrokeredClipDataObject@@UEAAJPEAUIRunAsClipboard@@@Z`
- size: `323`
- prototype: `HRESULT __fastcall(CBrokeredClipDataObject *this, IRunAsClipboard *pTarget)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18009000c`
- `0x1800925c0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009266a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800926a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009266a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800926a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180092660`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180092660`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180092647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180092647`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009269a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800926e7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009269a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800926e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800926f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800926f2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18009262e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18009262e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800925db`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18009268a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800926bd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800925db`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18009268a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800926bd`

## pseudocode

```c
HRESULT __fastcall CBrokeredClipDataObject::InvokeAsClipboard(CBrokeredClipDataObject *this, IRunAsClipboard *pTarget)
{
  signed int v4; // ebx
  HRESULT result; // eax
  HRESULT v6; // eax
  HANDLE CurrentThread; // rax
  char v8; // bp
  signed int LastError; // eax
  signed int v10; // eax
  void *hRevert; // [rsp+78h] [rbp+10h] BYREF

  if ( !pTarget )
  {
    v4 = -2147024809;
    RoOriginateError(2147942487LL, 0);
    return v4;
  }
  if ( !*(_QWORD *)&this->m_refs )
    return -2147024891;
  result = CheckCallerIntegrityLevelIsAtLeast((unsigned int)this);
  if ( result >= 0 )
  {
    v6 = CoSetProxyBlanket(
           pTarget,
           0xFFFFFFFF,
           0xFFFFFFFF,
           (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
           0,
           3u,
           (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
           0x800u);
    hRevert = 0;
    v4 = v6;
    if ( v6 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      v8 = 1;
      if ( OpenThreadToken(CurrentThread, 4u, 1, &hRevert) )
        goto LABEL_21;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError == 1008 )
        goto LABEL_21;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      RoOriginateError((unsigned int)v4, 0);
      if ( v4 >= 0 )
      {
LABEL_21:
        if ( SetThreadToken(0, *(HANDLE *)&this->m_refs) )
          goto LABEL_16;
        v10 = GetLastError();
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        RoOriginateError((unsigned int)v4, 0);
        v8 = 0;
        if ( v4 >= 0 )
        {
LABEL_16:
          v4 = ((__int64 (__fastcall *)(IRunAsClipboard *))pTarget->lpVtbl[1].QueryInterface)(pTarget);
          if ( v8 )
          {
            SetThreadToken(0, hRevert);
            CloseHandle(hRevert);
          }
        }
      }
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800925c0  push    rbx
0x1800925c2  push    rbp
0x1800925c3  push    rsi
0x1800925c4  push    rdi
0x1800925c5  sub     rsp, 48h
0x1800925c9  mov     rdi, pTarget
0x1800925cc  mov     rsi, this
0x1800925cf  test    pTarget, pTarget
0x1800925d2  jnz     short loc_1800925E6
0x1800925d4  mov     ebx, 80070057h
0x1800925d9  mov     ecx, ebx
0x1800925db  call    cs:__imp_RoOriginateError
0x1800925e1  jmp     loc_1800926F8
0x1800925e6  cmp     qword ptr [this+10h], 0
0x1800925eb  jnz     short loc_1800925F7
0x1800925ed  mov     eax, 80070005h
0x1800925f2  jmp     loc_1800926FA
0x1800925f7  call    ?CheckCallerIntegrityLevelIsAtLeast@@YAJK@Z; CheckCallerIntegrityLevelIsAtLeast(ulong)
0x1800925fc  test    eax, eax
0x1800925fe  js      loc_1800926FA
0x180092604  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18009260c  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180092610  mov     [rsp+68h+pAuthInfo], r9; pAuthInfo
0x180092615  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180092618  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180092620  mov     r8d, edx; dwAuthzSvc
0x180092623  mov     this, rdi; pProxy
0x180092626  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x18009262e  call    cs:__imp_CoSetProxyBlanket
0x180092634  mov     [rsp+68h+hRevert], 0
0x18009263d  mov     ebx, eax
0x18009263f  test    eax, eax
0x180092641  js      loc_1800926F8
0x180092647  call    cs:__imp_GetCurrentThread
0x18009264d  mov     ebp, 1
0x180092652  lea     r9, [rsp+68h+hRevert]; TokenHandle
0x180092657  mov     this, rax; ThreadHandle
0x18009265a  mov     r8d, ebp; OpenAsSelf
0x18009265d  lea     edx, [rbp+3]; DesiredAccess
0x180092660  call    cs:__imp_OpenThreadToken
0x180092666  test    eax, eax
0x180092668  jnz     short loc_180092694
0x18009266a  call    cs:__imp_GetLastError
0x180092670  mov     ebx, eax
0x180092672  cmp     eax, 3F0h
0x180092677  jz      short loc_180092694
0x180092679  test    eax, eax
0x18009267b  jle     short loc_180092686
0x18009267d  movzx   ebx, ax
0x180092680  or      ebx, 80070000h
0x180092686  xor     edx, edx
0x180092688  mov     ecx, ebx
0x18009268a  call    cs:__imp_RoOriginateError
0x180092690  test    ebx, ebx
0x180092692  js      short loc_1800926F8
0x180092694  mov     pTarget, [rsi+10h]; Token
0x180092698  xor     ecx, ecx; Thread
0x18009269a  call    cs:__imp_SetThreadToken
0x1800926a0  test    eax, eax
0x1800926a2  jnz     short loc_1800926CA
0x1800926a4  call    cs:__imp_GetLastError
0x1800926aa  mov     ebx, eax
0x1800926ac  test    eax, eax
0x1800926ae  jle     short loc_1800926B9
0x1800926b0  movzx   ebx, ax
0x1800926b3  or      ebx, 80070000h
0x1800926b9  xor     edx, edx
0x1800926bb  mov     ecx, ebx
0x1800926bd  call    cs:__imp_RoOriginateError
0x1800926c3  xor     bpl, bpl
0x1800926c6  test    ebx, ebx
0x1800926c8  js      short loc_1800926F8
0x1800926ca  mov     rax, [rdi]
0x1800926cd  mov     this, rdi
0x1800926d0  mov     rax, [rax+18h]
0x1800926d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800926d9  mov     ebx, eax
0x1800926db  test    bpl, bpl
0x1800926de  jz      short loc_1800926F8
0x1800926e0  mov     pTarget, [rsp+68h+hRevert]; Token
0x1800926e5  xor     ecx, ecx; Thread
0x1800926e7  call    cs:__imp_SetThreadToken
0x1800926ed  mov     this, [rsp+68h+hRevert]; hObject
0x1800926f2  call    cs:__imp_CloseHandle
0x1800926f8  mov     eax, ebx
0x1800926fa  add     rsp, 48h
0x1800926fe  pop     rdi
0x1800926ff  pop     rsi
0x180092700  pop     rbp
0x180092701  pop     rbx
0x180092702  retn
```
