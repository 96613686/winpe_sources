# CSecurity::GetSid(void)

- ea: `0x18006e2c0`
- end: `0x18006e61b`
- name: `?GetSid@CSecurity@@SAPEAXXZ`
- size: `859`
- prototype: `void *(void)`
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006d680`
- `0x18006d8b0`
- `0x18006db58`
- `0x18006df10`
- `0x180099d90`
- `0x1800dc800`
- `0x1800f11a8`
- `0x18016567c`
- `0x18018d440`

## callees

- `0x180005d10`
- `0x18004a900`
- `0x18005d800`
- `0x18006e2c0`
- `0x18006e630`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e4d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e4d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e314`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006e3bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006e3bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006e380`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006e380`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e306`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e36f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e306`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e36f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006e342`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006e3a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006e342`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006e3a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006e3e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006e3e6`

## string_xrefs

- `0x18006e532`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18006e55b`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18006e5c6`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *CSecurity::GetSid(void)
{
  void *v0; // rdi
  char *Token; // rbx
  CHeap *v2; // rcx
  DWORD v3; // esi
  CHeap *v4; // rcx
  void *Handle; // rax
  PSID *v6; // rsi
  DWORD LengthSid; // ebp
  CHeap *v8; // rcx
  CHeap *v9; // rcx
  void *v10; // rax
  void *v11; // rax
  CHeap *v12; // rcx
  CHeap *v13; // rcx
  void *v14; // rax
  PVOID *v15; // rcx
  __int64 v17; // rdx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp+10h] BYREF
  char *v20; // [rsp+70h] [rbp+18h]

  v0 = 0;
  Token = (char *)CSecurity::GetToken();
  v20 = Token;
  if ( !Token )
    goto LABEL_12;
  TokenInformationLength = 0;
  if ( GetTokenInformation(Token, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
      goto LABEL_13;
    v17 = 15;
LABEL_22:
    WPP_SF_(v15[2], v17, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
LABEL_12:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  if ( GetLastError() != 122 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) == 0 )
      goto LABEL_13;
    v17 = 14;
    goto LABEL_22;
  }
  v3 = TokenInformationLength;
  if ( CHeap::GetHandle(v2) )
  {
    Handle = CHeap::GetHandle(v4);
    v6 = (PSID *)HeapAlloc(Handle, 0, v3);
    if ( v6 )
    {
      ReturnLength = 0;
      if ( !GetTokenInformation(Token, TokenUser, v6, TokenInformationLength, &ReturnLength) )
      {
        v12 = (CHeap *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, 122);
        goto LABEL_10;
      }
      LengthSid = GetLengthSid(*v6);
      if ( CHeap::GetHandle(v8) )
      {
        v10 = CHeap::GetHandle(v9);
        v11 = HeapAlloc(v10, 0, LengthSid);
        v0 = v11;
        if ( v11 )
        {
          if ( !CopySid(LengthSid, v11, *v6) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
            WSManMemory::Free(v0, 0);
            v0 = 0;
          }
LABEL_10:
          if ( CHeap::GetHandle(v12) )
          {
            v14 = CHeap::GetHandle(v13);
            HeapFree(v14, 0, v6);
          }
          else
          {
            WSManError(
              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp",
              261,
              L"261",
              0x54Fu,
              0);
          }
          goto LABEL_12;
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
        v0 = 0;
      }
      SetLastError(0xEu);
      v12 = (CHeap *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
      goto LABEL_10;
    }
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  SetLastError(0xEu);
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_5b789da118f632ad9796e014c1252c4d_Traceguids,
      TokenInformationLength);
    goto LABEL_12;
  }
LABEL_13:
  if ( (unsigned __int64)(Token - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x1000000) != 0 )
      WPP_SF_q(v15[2], 12, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids, Token);
    CloseHandle(Token);
  }
  return v0;
}

```

## disassembly

```asm
0x18006e2c0  push    rbx
0x18006e2c2  push    rbp
0x18006e2c3  push    rsi
0x18006e2c4  push    rdi
0x18006e2c5  push    r15
0x18006e2c7  sub     rsp, 30h
0x18006e2cb  xor     edi, edi
0x18006e2cd  call    ?GetToken@CSecurity@@SAPEAXXZ; CSecurity::GetToken(void)
0x18006e2d2  mov     rbx, rax
0x18006e2d5  mov     [rsp+58h+arg_10], rax
0x18006e2da  lea     r15, WPP_GLOBAL_Control
0x18006e2e1  test    rax, rax
0x18006e2e4  jz      loc_18006E3ED
0x18006e2ea  mov     [rsp+58h+TokenInformationLength], edi
0x18006e2ee  lea     rax, [rsp+58h+TokenInformationLength]
0x18006e2f3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18006e2f8  xor     r9d, r9d; TokenInformationLength
0x18006e2fb  xor     r8d, r8d; TokenInformation
0x18006e2fe  lea     ebp, [rdi+1]
0x18006e301  mov     edx, ebp; TokenInformationClass
0x18006e303  mov     rcx, rbx; TokenHandle
0x18006e306  call    cs:__imp_GetTokenInformation
0x18006e30c  test    eax, eax
0x18006e30e  jnz     loc_18006E427
0x18006e314  call    cs:__imp_GetLastError
0x18006e31a  cmp     eax, 7Ah ; 'z'
0x18006e31d  jnz     loc_18006E5D7
0x18006e323  mov     esi, [rsp+58h+TokenInformationLength]
0x18006e327  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18006e32c  test    rax, rax
0x18006e32f  jz      loc_18006E517
0x18006e335  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18006e33a  mov     r8d, esi; dwBytes
0x18006e33d  xor     edx, edx; dwFlags
0x18006e33f  mov     rcx, rax; hHeap
0x18006e342  call    cs:__imp_HeapAlloc
0x18006e348  mov     rsi, rax
0x18006e34b  test    rax, rax
0x18006e34e  jz      loc_18006E4D0
0x18006e354  mov     [rsp+58h+arg_8], edi
0x18006e358  lea     rax, [rsp+58h+arg_8]
0x18006e35d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18006e362  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18006e367  mov     r8, rsi; TokenInformation
0x18006e36a  mov     edx, ebp; TokenInformationClass
0x18006e36c  mov     rcx, rbx; TokenHandle
0x18006e36f  call    cs:__imp_GetTokenInformation
0x18006e375  cmp     eax, ebp
0x18006e377  jnz     loc_18006E453
0x18006e37d  mov     rcx, [rsi]; pSid
0x18006e380  call    cs:__imp_GetLengthSid
0x18006e386  mov     ebp, eax
0x18006e388  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18006e38d  test    rax, rax
0x18006e390  jz      loc_18006E540
0x18006e396  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18006e39b  mov     r8d, ebp; dwBytes
0x18006e39e  xor     edx, edx; dwFlags
0x18006e3a0  mov     rcx, rax; hHeap
0x18006e3a3  call    cs:__imp_HeapAlloc
0x18006e3a9  mov     rdi, rax
0x18006e3ac  test    rax, rax
0x18006e3af  jz      loc_18006E48E
0x18006e3b5  mov     r8, [rsi]; pSourceSid
0x18006e3b8  mov     rdx, rax; pDestinationSid
0x18006e3bb  mov     ecx, ebp; nDestinationSidLength
0x18006e3bd  call    cs:__imp_CopySid
0x18006e3c3  test    eax, eax
0x18006e3c5  jz      loc_18006E56E
0x18006e3cb  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18006e3d0  test    rax, rax
0x18006e3d3  jz      loc_18006E5AB
0x18006e3d9  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18006e3de  mov     r8, rsi; lpMem
0x18006e3e1  xor     edx, edx; dwFlags
0x18006e3e3  mov     rcx, rax; hHeap
0x18006e3e6  call    cs:__imp_HeapFree
0x18006e3ec  nop
0x18006e3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e3f4  lea     rax, [rbx-1]
0x18006e3f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006e3fc  ja      short loc_18006E419
0x18006e3fe  cmp     rcx, r15
0x18006e401  jz      short loc_18006E410
0x18006e403  test    dword ptr [rcx+1Ch], 1000000h
0x18006e40a  jnz     loc_18006E5FE
0x18006e410  mov     rcx, rbx; hObject
0x18006e413  call    cs:__imp_CloseHandle
0x18006e419  mov     rax, rdi
0x18006e41c  add     rsp, 30h
0x18006e420  pop     r15
0x18006e422  pop     rdi
0x18006e423  pop     rsi
0x18006e424  pop     rbp
0x18006e425  pop     rbx
0x18006e426  retn
0x18006e427  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e42e  cmp     rcx, r15
0x18006e431  jz      short loc_18006E3F4
0x18006e433  test    dword ptr [rcx+1Ch], 10000000h
0x18006e43a  jz      short loc_18006E3F4
0x18006e43c  mov     edx, 0Fh
0x18006e441  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x18006e448  mov     rcx, [rcx+10h]
0x18006e44c  call    WPP_SF_
0x18006e451  jmp     short loc_18006E3ED
0x18006e453  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e45a  cmp     rcx, r15
0x18006e45d  jz      loc_18006E3CB
0x18006e463  test    dword ptr [rcx+1Ch], 10000000h
0x18006e46a  jz      loc_18006E3CB
0x18006e470  mov     edx, 0Ch
0x18006e475  lea     r9d, [rdx+6Eh]
0x18006e479  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x18006e480  mov     rcx, [rcx+10h]
0x18006e484  call    WPP_SF_d
0x18006e489  jmp     loc_18006E3CB
0x18006e48e  mov     ecx, 0Eh; dwErrCode
0x18006e493  call    cs:__imp_SetLastError
0x18006e499  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4a0  cmp     rcx, r15
0x18006e4a3  jz      loc_18006E3CB
0x18006e4a9  test    dword ptr [rcx+1Ch], 10000000h
0x18006e4b0  jz      loc_18006E3CB
0x18006e4b6  mov     edx, 0Bh
0x18006e4bb  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x18006e4c2  mov     rcx, [rcx+10h]
0x18006e4c6  call    WPP_SF_
0x18006e4cb  jmp     loc_18006E3CB
0x18006e4d0  mov     ecx, 0Eh; dwErrCode
0x18006e4d5  call    cs:__imp_SetLastError
0x18006e4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4e2  cmp     rcx, r15
0x18006e4e5  jz      loc_18006E3F4
0x18006e4eb  test    dword ptr [rcx+1Ch], 10000000h
0x18006e4f2  jz      loc_18006E3F4
0x18006e4f8  mov     edx, 0Dh
0x18006e4fd  mov     r9d, [rsp+58h+TokenInformationLength]
0x18006e502  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x18006e509  mov     rcx, [rcx+10h]
0x18006e50d  call    WPP_SF_d
0x18006e512  jmp     loc_18006E3ED
0x18006e517  mov     [rsp+58h+ReturnLength], 0; struct IRequestContext *
0x18006e520  mov     r9d, 54Fh; unsigned int
0x18006e526  lea     r8, a170; "170"
0x18006e52d  mov     edx, 0AAh; unsigned int
0x18006e532  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18006e539  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006e53e  jmp     short loc_18006E4D0
0x18006e540  mov     [rsp+58h+ReturnLength], 0; struct IRequestContext *
0x18006e549  mov     r9d, 54Fh; unsigned int
0x18006e54f  lea     r8, a170; "170"
0x18006e556  mov     edx, 0AAh; unsigned int
0x18006e55b  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18006e562  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006e567  xor     edi, edi
0x18006e569  jmp     loc_18006E48E
0x18006e56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e575  cmp     rcx, r15
0x18006e578  jz      short loc_18006E599
0x18006e57a  test    dword ptr [rcx+1Ch], 10000000h
0x18006e581  jz      short loc_18006E599
0x18006e583  mov     edx, 0Ah
0x18006e588  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x18006e58f  mov     rcx, [rcx+10h]
0x18006e593  call    WPP_SF_
0x18006e598  nop
0x18006e599  xor     edx, edx; int
0x18006e59b  mov     rcx, rdi; void *
0x18006e59e  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18006e5a3  nop
0x18006e5a4  xor     edi, edi
0x18006e5a6  jmp     loc_18006E3CB
0x18006e5ab  mov     [rsp+58h+ReturnLength], 0; struct IRequestContext *
0x18006e5b4  mov     r9d, 54Fh; unsigned int
0x18006e5ba  lea     r8, a261; "261"
0x18006e5c1  mov     edx, 105h; unsigned int
0x18006e5c6  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18006e5cd  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006e5d2  jmp     loc_18006E3ED
0x18006e5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e5de  cmp     rcx, r15
0x18006e5e1  jz      loc_18006E3F4
0x18006e5e7  test    dword ptr [rcx+1Ch], 10000000h
0x18006e5ee  jz      loc_18006E3F4
0x18006e5f4  mov     edx, 0Eh
0x18006e5f9  jmp     loc_18006E441
0x18006e5fe  mov     edx, 0Ch
0x18006e603  mov     r9, rbx
0x18006e606  lea     r8, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids
0x18006e60d  mov     rcx, [rcx+10h]
0x18006e611  call    WPP_SF_q
0x18006e616  jmp     loc_18006E410
```
