# CDownloadManager::WinHttpCallbackFn(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x18005f290`
- end: `0x18005f462`
- name: `?WinHttpCallbackFn@CDownloadManager@@KAXPEAX_KK0K@Z`
- size: `466`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18005c2c8`
- `0x18005c724`
- `0x18005f290`
- `0x18005f4e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f403`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005f403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f425`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f2c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f2c8`

## pseudocode

```c
void __fastcall CDownloadManager::WinHttpCallbackFn(
        HINTERNET hInternet,
        DWORD_PTR dwContext,
        DWORD dwInternetStatus,
        _DWORD *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  int v8; // ebp
  PVOID *v9; // rdx
  DWORD CurrentThreadId; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  int v15; // r8d
  __int64 v16; // rax
  void *v17; // rcx
  DWORD LastError; // ebx
  unsigned int v19; // eax

  v8 = (int)hInternet;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDDdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v13,
      CurrentThreadActivityIdPrefix,
      CurrentThreadId,
      v8,
      dwInternetStatus,
      dwContext);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( dwContext )
  {
    if ( *(_DWORD *)dwContext == g_dwDMObjectContext )
    {
      if ( dwInternetStatus != 2048 )
      {
        v15 = 0x4000;
        if ( dwInternetStatus != 0x4000 )
        {
          if ( dwInternetStatus == 0x10000 )
          {
            *(_DWORD *)(dwContext + 32) = *lpvStatusInformation;
            return;
          }
          v15 = 0x20000;
          if ( dwInternetStatus != 0x20000 )
          {
            v15 = 0x40000;
            if ( dwInternetStatus != 0x40000 )
            {
              v15 = 0x80000;
              if ( dwInternetStatus != 0x80000 )
              {
                if ( dwInternetStatus == 0x200000 )
                {
                  CDownloadManager::OnRequestError(
                    *(CDownloadManager **)(dwContext + 8),
                    (struct _DM_CONTEXT *)dwContext,
                    lpvStatusInformation,
                    (unsigned int)lpvStatusInformation);
                  return;
                }
                v15 = 0x400000;
                if ( dwInternetStatus != 0x400000 )
                  return;
              }
            }
          }
        }
        CDownloadManager::OnRequestComplete(
          *(CDownloadManager **)(dwContext + 8),
          (struct _DM_CONTEXT *)dwContext,
          v15,
          lpvStatusInformation,
          dwStatusInformationLength);
        return;
      }
      if ( lpvStatusInformation )
      {
        v16 = *(_QWORD *)(dwContext + 40);
        if ( v16 )
        {
          if ( v16 == *(_QWORD *)lpvStatusInformation )
          {
            v17 = *(void **)(dwContext + 120);
            if ( v17 )
            {
              if ( !SetEvent(v17)
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LastError = GetLastError();
                v19 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  58,
                  &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
                  v19,
                  LastError);
              }
            }
          }
        }
      }
    }
    else if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v14);
    }
  }
}

```

## disassembly

```asm
0x18005f290  push    rbx
0x18005f292  push    rbp
0x18005f293  push    rsi
0x18005f294  push    rdi
0x18005f295  push    r12
0x18005f297  push    r14
0x18005f299  sub     rsp, 48h
0x18005f29d  mov     r14, r9
0x18005f2a0  mov     esi, r8d
0x18005f2a3  mov     rdi, rdx
0x18005f2a6  mov     rbp, rcx
0x18005f2a9  mov     rdx, cs:WPP_GLOBAL_Control
0x18005f2b0  lea     r12, WPP_GLOBAL_Control
0x18005f2b7  cmp     rdx, r12
0x18005f2ba  jz      short loc_18005F2FF
0x18005f2bc  test    byte ptr [rdx+1Ch], 1
0x18005f2c0  jz      short loc_18005F2FF
0x18005f2c2  cmp     byte ptr [rdx+19h], 4
0x18005f2c6  jb      short loc_18005F2FF
0x18005f2c8  call    cs:__imp_GetCurrentThreadId
0x18005f2ce  mov     ebx, eax
0x18005f2d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005f2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f2dc  mov     r9d, eax
0x18005f2df  mov     [rsp+78h+var_40], edi
0x18005f2e3  mov     [rsp+78h+var_48], esi
0x18005f2e7  mov     [rsp+78h+var_50], ebp
0x18005f2eb  mov     rcx, [rcx+10h]
0x18005f2ef  mov     [rsp+78h+var_58], ebx
0x18005f2f3  call    WPP_SF_DDDdD
0x18005f2f8  mov     rdx, cs:WPP_GLOBAL_Control
0x18005f2ff  test    rdi, rdi
0x18005f302  jz      loc_18005F455
0x18005f308  mov     eax, cs:?g_dwDMObjectContext@@3KA; ulong g_dwDMObjectContext
0x18005f30e  cmp     [rdi], eax
0x18005f310  jz      short loc_18005F358
0x18005f312  cmp     rdx, r12
0x18005f315  jz      loc_18005F455
0x18005f31b  test    byte ptr [rdx+1Ch], 1
0x18005f31f  jz      loc_18005F455
0x18005f325  cmp     byte ptr [rdx+19h], 2
0x18005f329  jb      loc_18005F455
0x18005f32f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005f334  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f33b  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005f342  mov     edx, 39h ; '9'
0x18005f347  mov     r9d, eax
0x18005f34a  mov     rcx, [rcx+10h]
0x18005f34e  call    WPP_SF_D
0x18005f353  jmp     loc_18005F455
0x18005f358  cmp     esi, 800h
0x18005f35e  jz      loc_18005F3E7
0x18005f364  mov     r8d, 4000h
0x18005f36a  cmp     esi, r8d
0x18005f36d  jz      short loc_18005F3AF
0x18005f36f  cmp     esi, 10000h
0x18005f375  jz      short loc_18005F3DF
0x18005f377  mov     r8d, 20000h
0x18005f37d  cmp     esi, r8d
0x18005f380  jz      short loc_18005F3AF
0x18005f382  mov     r8d, 40000h
0x18005f388  cmp     esi, r8d
0x18005f38b  jz      short loc_18005F3AF
0x18005f38d  mov     r8d, 80000h
0x18005f393  cmp     esi, r8d
0x18005f396  jz      short loc_18005F3AF
0x18005f398  cmp     esi, 200000h
0x18005f39e  jz      short loc_18005F3CE
0x18005f3a0  mov     r8d, 400000h; unsigned int
0x18005f3a6  cmp     esi, r8d
0x18005f3a9  jnz     loc_18005F455
0x18005f3af  mov     eax, [rsp+78h+dwStatusInformationLength]
0x18005f3b6  mov     r9, r14; void *
0x18005f3b9  mov     rcx, [rdi+8]; this
0x18005f3bd  mov     rdx, rdi; struct _DM_CONTEXT *
0x18005f3c0  mov     [rsp+78h+var_58], eax; unsigned int
0x18005f3c4  call    ?OnRequestComplete@CDownloadManager@@IEAAXPEAU_DM_CONTEXT@@KPEAXK@Z; CDownloadManager::OnRequestComplete(_DM_CONTEXT *,ulong,void *,ulong)
0x18005f3c9  jmp     loc_18005F455
0x18005f3ce  mov     rcx, [rdi+8]; this
0x18005f3d2  mov     r8, r14; void *
0x18005f3d5  mov     rdx, rdi; struct _DM_CONTEXT *
0x18005f3d8  call    ?OnRequestError@CDownloadManager@@IEAAXPEAU_DM_CONTEXT@@PEAXK@Z; CDownloadManager::OnRequestError(_DM_CONTEXT *,void *,ulong)
0x18005f3dd  jmp     short loc_18005F455
0x18005f3df  mov     eax, [r14]
0x18005f3e2  mov     [rdi+20h], eax
0x18005f3e5  jmp     short loc_18005F455
0x18005f3e7  test    r14, r14
0x18005f3ea  jz      short loc_18005F455
0x18005f3ec  mov     rax, [rdi+28h]
0x18005f3f0  test    rax, rax
0x18005f3f3  jz      short loc_18005F455
0x18005f3f5  cmp     rax, [r14]
0x18005f3f8  jnz     short loc_18005F455
0x18005f3fa  mov     rcx, [rdi+78h]; hEvent
0x18005f3fe  test    rcx, rcx
0x18005f401  jz      short loc_18005F455
0x18005f403  call    cs:__imp_SetEvent
0x18005f409  test    eax, eax
0x18005f40b  jnz     short loc_18005F455
0x18005f40d  mov     rax, cs:WPP_GLOBAL_Control
0x18005f414  cmp     rax, r12
0x18005f417  jz      short loc_18005F455
0x18005f419  test    byte ptr [rax+1Ch], 1
0x18005f41d  jz      short loc_18005F455
0x18005f41f  cmp     byte ptr [rax+19h], 2
0x18005f423  jb      short loc_18005F455
0x18005f425  call    cs:__imp_GetLastError
0x18005f42b  mov     ebx, eax
0x18005f42d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005f432  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f439  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005f440  mov     edx, 3Ah ; ':'
0x18005f445  mov     [rsp+78h+var_58], ebx
0x18005f449  mov     r9d, eax
0x18005f44c  mov     rcx, [rcx+10h]
0x18005f450  call    WPP_SF_Dd
0x18005f455  add     rsp, 48h
0x18005f459  pop     r14
0x18005f45b  pop     r12
0x18005f45d  pop     rdi
0x18005f45e  pop     rsi
0x18005f45f  pop     rbp
0x18005f460  pop     rbx
0x18005f461  retn
```
