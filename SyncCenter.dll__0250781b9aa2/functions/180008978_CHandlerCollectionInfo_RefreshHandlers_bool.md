# CHandlerCollectionInfo::RefreshHandlers(bool)

- ea: `0x180008978`
- end: `0x180008a8a`
- name: `?RefreshHandlers@CHandlerCollectionInfo@@QEAAJ_N@Z`
- size: `274`
- prototype: `__int64 __fastcall(CHandlerCollectionInfo *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015790`

## callees

- `0x180008978`
- `0x180008a90`
- `0x18000a714`
- `0x180012e54`
- `0x180016220`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x1800089fc`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x1800089fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008995`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008995`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a75`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180008a68`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180008a68`

## pseudocode

```c
__int64 __fastcall CHandlerCollectionInfo::RefreshHandlers(CHandlerCollectionInfo *this, char a2)
{
  UINT v3; // esi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  HRESULT Error; // ebx
  __int64 v7; // rcx
  DWORD dwindex; // [rsp+50h] [rbp+8h] BYREF
  HANDLE pHandles; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 6);
  pHandles = 0;
  EnterCriticalSection(v4);
  if ( *((_BYTE *)this + 64) )
  {
    Error = -2147483638;
  }
  else if ( *((_QWORD *)this + 5)
         || (CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create((char *)this + 40, 4),
             *((_QWORD *)this + 5)) )
  {
    v7 = *((_QWORD *)this + 7);
    _InterlockedExchange((volatile __int32 *)(v7 + 96), 0);
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 396));
    _InterlockedIncrement((volatile signed __int32 *)this + 4);
    v3 = SHCreateThreadWithHandle((WCHAR)CHandlerCollectionInfo::s_UpdateHandlersThreadProc);
    if ( v3 )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        CHandlerCollectionInfo::Release(this);
        CHandlerCache::Release(*((CHandlerCache **)this + 7));
        goto LABEL_11;
      }
    }
    *((_BYTE *)this + 64) = 1;
  }
  else
  {
    Error = -2147024882;
  }
LABEL_11:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 6));
  if ( Error >= 0 && v3 )
  {
    if ( a2 == 1 )
    {
      dwindex = 0;
      Error = CoWaitForMultipleHandles(0, 0x1D4C0u, 1u, &pHandles, &dwindex);
    }
    CloseHandle(pHandles);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180008978  mov     [rsp+arg_8], rbx
0x18000897d  push    rbp
0x18000897e  push    rsi
0x18000897f  push    rdi
0x180008980  sub     rsp, 30h
0x180008984  mov     rdi, rcx
0x180008987  xor     esi, esi
0x180008989  mov     rcx, [rcx+30h]; lpCriticalSection
0x18000898d  mov     bpl, dl
0x180008990  mov     [rsp+48h+pHandles], rsi
0x180008995  call    cs:__imp_EnterCriticalSection
0x18000899b  cmp     [rdi+40h], sil
0x18000899f  jz      short loc_1800089AB
0x1800089a1  mov     ebx, 8000000Ah
0x1800089a6  jmp     loc_180008A2E
0x1800089ab  lea     rbx, [rdi+28h]
0x1800089af  cmp     [rbx], rsi
0x1800089b2  jnz     short loc_1800089CD
0x1800089b4  mov     edx, 4
0x1800089b9  mov     rcx, rbx
0x1800089bc  call    ?Create@?$CDPA_Base@USYNCMGR_EVENTINFO@@V?$CTContainer_PolicyUnOwned@USYNCMGR_EVENTINFO@@@@@@QEAAHH@Z; CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create(int)
0x1800089c1  cmp     [rbx], rsi
0x1800089c4  jnz     short loc_1800089CD
0x1800089c6  mov     ebx, 8007000Eh
0x1800089cb  jmp     short loc_180008A2E
0x1800089cd  mov     rcx, [rdi+38h]
0x1800089d1  xor     eax, eax
0x1800089d3  xchg    eax, [rcx+60h]
0x1800089d6  lock inc dword ptr [rcx+18Ch]
0x1800089dd  lock inc dword ptr [rdi+10h]
0x1800089e1  xor     r9d, r9d
0x1800089e4  lea     rax, [rsp+48h+pHandles]
0x1800089e9  mov     rdx, rdi
0x1800089ec  mov     [rsp+48h+lpdwindex], rax
0x1800089f1  lea     rcx, ?s_UpdateHandlersThreadProc@CHandlerCollectionInfo@@CAKPEAX@Z; ch
0x1800089f8  lea     r8d, [r9+8]
0x1800089fc  call    cs:__imp_SHCreateThreadWithHandle
0x180008a02  mov     esi, eax
0x180008a04  test    eax, eax
0x180008a06  jz      short loc_180008A0C
0x180008a08  xor     ebx, ebx
0x180008a0a  jmp     short loc_180008A17
0x180008a0c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180008a11  mov     ebx, eax
0x180008a13  test    eax, eax
0x180008a15  js      short loc_180008A1D
0x180008a17  mov     byte ptr [rdi+40h], 1
0x180008a1b  jmp     short loc_180008A2E
0x180008a1d  mov     rcx, rdi; this
0x180008a20  call    ?Release@CHandlerCollectionInfo@@QEAAIXZ; CHandlerCollectionInfo::Release(void)
0x180008a25  mov     rcx, [rdi+38h]; this
0x180008a29  call    ?Release@CHandlerCache@@QEAAJXZ; CHandlerCache::Release(void)
0x180008a2e  mov     rcx, [rdi+30h]; lpCriticalSection
0x180008a32  call    cs:__imp_LeaveCriticalSection
0x180008a38  test    ebx, ebx
0x180008a3a  js      short loc_180008A7B
0x180008a3c  test    esi, esi
0x180008a3e  jz      short loc_180008A7B
0x180008a40  cmp     bpl, 1
0x180008a44  jnz     short loc_180008A70
0x180008a46  xor     ecx, ecx; dwFlags
0x180008a48  mov     [rsp+48h+dwindex], 0
0x180008a50  lea     rax, [rsp+48h+dwindex]
0x180008a55  mov     edx, 1D4C0h; dwTimeout
0x180008a5a  lea     r9, [rsp+48h+pHandles]; pHandles
0x180008a5f  mov     [rsp+48h+lpdwindex], rax; lpdwindex
0x180008a64  lea     r8d, [rcx+1]; cHandles
0x180008a68  call    cs:__imp_CoWaitForMultipleHandles
0x180008a6e  mov     ebx, eax
0x180008a70  mov     rcx, [rsp+48h+pHandles]; hObject
0x180008a75  call    cs:__imp_CloseHandle
0x180008a7b  mov     eax, ebx
0x180008a7d  mov     rbx, [rsp+48h+arg_8]
0x180008a82  add     rsp, 30h
0x180008a86  pop     rdi
0x180008a87  pop     rsi
0x180008a88  pop     rbp
0x180008a89  retn
```
