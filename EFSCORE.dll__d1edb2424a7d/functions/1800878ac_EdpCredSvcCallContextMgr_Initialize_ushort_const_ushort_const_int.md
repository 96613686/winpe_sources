# EdpCredSvcCallContextMgr::Initialize(ushort const *,ushort const *,int)

- ea: `0x1800878ac`
- end: `0x180087cda`
- name: `?Initialize@EdpCredSvcCallContextMgr@@QEAAJPEBG0H@Z`
- size: `1070`
- prototype: `int(EdpCredSvcCallContextMgr *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f290`
- `0x18000f3d0`
- `0x18000f4c0`
- `0x18000f5b0`
- `0x18000f6a0`
- `0x18000fae0`
- `0x18000fbc0`
- `0x180010770`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180082d60`
- `0x1800857a8`
- `0x180085ba0`
- `0x1800861ec`
- `0x1800878ac`
- `0x180089d38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bdf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180087bd1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180087bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087ba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087cb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087ba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087cb9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087b7d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087b7d`

## pseudocode

```c
__int64 __fastcall EdpCredSvcCallContextMgr::Initialize(EdpCredSvcCallContextMgr *this, char *a2, char *a3, int a4)
{
  bool v4; // zf
  unsigned int ImpersonationCtxAndRevertToSelf; // ebx
  int v10; // r8d
  int v11; // ecx
  char *v12; // rax
  int v13; // edx
  char *v14; // rax
  int v15; // edx
  int v16; // ecx
  int v17; // ecx
  HANDLE *v18; // rsi
  signed int LastError; // eax
  signed int v20; // eax
  char v22; // [rsp+20h] [rbp-58h]
  HANDLE ExistingTokenHandle; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+80h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 8) == 0;
  v24 = 0;
  ExistingTokenHandle = 0;
  if ( !v4 )
  {
    ImpersonationCtxAndRevertToSelf = -2147418113;
    v22 = 107;
    v10 = -2147418113;
LABEL_3:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 38, v22);
    goto LABEL_44;
  }
  if ( !a2 )
  {
    ImpersonationCtxAndRevertToSelf = -2147024809;
    v22 = 108;
    v10 = -2147024809;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 115);
  ImpersonationCtxAndRevertToSelf = EdpCredSvcShouldCheckCaller(&v24);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              ImpersonationCtxAndRevertToSelf,
              38,
              115) < 0 )
    goto LABEL_44;
  if ( !a4 )
  {
LABEL_15:
    if ( v24 )
      goto LABEL_40;
    goto LABEL_16;
  }
  if ( v24 )
  {
    if ( a3 )
    {
      v12 = a2;
      do
      {
        v11 = *(unsigned __int16 *)&v12[a3 - a2];
        v13 = *(unsigned __int16 *)v12 - v11;
        if ( v13 )
          break;
        v12 += 2;
      }
      while ( v11 );
      if ( v13 )
      {
        ImpersonationCtxAndRevertToSelf = -2147024891;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024891, 38, 126);
        goto LABEL_44;
      }
    }
    goto LABEL_15;
  }
LABEL_16:
  if ( a3 )
  {
    v14 = a2;
    do
    {
      v15 = *(unsigned __int16 *)&v14[a3 - a2];
      v11 = *(unsigned __int16 *)v14 - v15;
      if ( v11 )
        break;
      v14 += 2;
    }
    while ( v15 );
    if ( v11 )
    {
      fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 161);
      ImpersonationCtxAndRevertToSelf = CDplService::DuplicateSvcString(
                                          (const unsigned __int16 *)a3,
                                          0xFFFFFFFFFFFFFFFFuLL,
                                          0xFFFFFFFFFFFFFFFFuLL,
                                          1,
                                          (unsigned __int16 **)this + 3);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  ImpersonationCtxAndRevertToSelf,
                  38,
                  161) >= 0 )
      {
        fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 169);
        ImpersonationCtxAndRevertToSelf = EdpCredSvcQuerySessionUserTokenBySid(
                                            *((const unsigned __int16 **)this + 3),
                                            &ExistingTokenHandle);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    ImpersonationCtxAndRevertToSelf,
                    38,
                    169) >= 0 )
        {
          if ( ImpersonationCtxAndRevertToSelf == 1 || !ExistingTokenHandle )
          {
            ImpersonationCtxAndRevertToSelf = -2147023651;
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023651, 38, 178);
            goto LABEL_44;
          }
          fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 186);
          ImpersonationCtxAndRevertToSelf = EdpCredSvcGetImpersonationCtxAndRevertToSelf((void **)this + 1);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      ImpersonationCtxAndRevertToSelf,
                      38,
                      186) < 0 )
            goto LABEL_44;
          v18 = (HANDLE *)((char *)this + 16);
          if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, (PHANDLE)this + 2) )
          {
            LastError = GetLastError();
            ImpersonationCtxAndRevertToSelf = LastError;
            if ( LastError > 0 )
              ImpersonationCtxAndRevertToSelf = (unsigned __int16)LastError | 0x80070000;
            if ( *v18 )
            {
              CloseHandle(*v18);
              *v18 = 0;
            }
            EdpCredSvcRestoreImpersonationCtx((void **)this + 1);
            v22 = -56;
LABEL_32:
            v10 = ImpersonationCtxAndRevertToSelf;
            goto LABEL_3;
          }
          if ( !SetThreadToken(0, *v18) )
          {
            v20 = GetLastError();
            ImpersonationCtxAndRevertToSelf = v20;
            if ( v20 > 0 )
              ImpersonationCtxAndRevertToSelf = (unsigned __int16)v20 | 0x80070000;
            if ( *v18 )
            {
              CloseHandle(*v18);
              *v18 = 0;
            }
            EdpCredSvcRestoreImpersonationCtx((void **)this + 1);
            v22 = -44;
            goto LABEL_32;
          }
          goto LABEL_43;
        }
      }
      goto LABEL_44;
    }
  }
LABEL_40:
  fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 143);
  if ( !a3 )
    a3 = a2;
  ImpersonationCtxAndRevertToSelf = CDplService::DuplicateSvcString(
                                      (const unsigned __int16 *)a3,
                                      0xFFFFFFFFFFFFFFFFuLL,
                                      0xFFFFFFFFFFFFFFFFuLL,
                                      1,
                                      (unsigned __int16 **)this + 3);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              ImpersonationCtxAndRevertToSelf,
              38,
              143) >= 0 )
LABEL_43:
    *((_DWORD *)this + 8) = 1;
LABEL_44:
  if ( ExistingTokenHandle )
    CloseHandle(ExistingTokenHandle);
  return ImpersonationCtxAndRevertToSelf;
}

```

## disassembly

```asm
0x1800878ac  mov     rax, rsp
0x1800878af  mov     [rax+10h], rbx
0x1800878b3  mov     [rax+18h], rbp
0x1800878b7  push    rsi
0x1800878b8  push    rdi
0x1800878b9  push    r12
0x1800878bb  push    r14
0x1800878bd  push    r15
0x1800878bf  sub     rsp, 50h
0x1800878c3  cmp     dword ptr [rcx+20h], 0
0x1800878c7  mov     r15d, r9d
0x1800878ca  mov     rsi, r8
0x1800878cd  mov     dword ptr [rax+8], 0
0x1800878d4  mov     r14, rdx
0x1800878d7  mov     qword ptr [rax-38h], 0
0x1800878df  mov     rbp, rcx
0x1800878e2  jz      short loc_180087914
0x1800878e4  mov     ebx, 8000FFFFh
0x1800878e9  mov     dword ptr [rax-58h], 146Bh
0x1800878f0  mov     r8d, 8000FFFFh
0x1800878f6  mov     r9d, 26h ; '&'
0x1800878fc  mov     rcx, cs:g_hPublisher
0x180087903  lea     rdx, EFS_TRACE_ERROR
0x18008790a  call    fnEfsLogTrace1
0x18008790f  jmp     loc_180087CAF
0x180087914  test    r14, r14
0x180087917  jnz     short loc_18008792E
0x180087919  mov     ebx, 80070057h
0x18008791e  mov     dword ptr [rsp+78h+var_58], 146Ch
0x180087926  mov     r8d, 80070057h
0x18008792c  jmp     short loc_1800878F6
0x18008792e  mov     edi, 26h ; '&'
0x180087933  lea     r8, sourceString
0x18008793a  mov     r12d, 1473h
0x180087940  lea     rdx, EFS_TRACE_START_EVENT
0x180087947  mov     r9d, edi
0x18008794a  mov     dword ptr [rsp+78h+var_58], r12d
0x18008794f  call    fnEfsLogTrace1Strings
0x180087954  lea     rcx, [rsp+78h+arg_0]; int *
0x18008795c  call    ?EdpCredSvcShouldCheckCaller@@YAJPEAH@Z; EdpCredSvcShouldCheckCaller(int *)
0x180087961  mov     rcx, cs:g_hPublisher
0x180087968  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008796f  mov     [rsp+78h+var_48], r12d
0x180087974  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008797b  lea     r12, sourceString
0x180087982  mov     [rsp+78h+var_50], edi
0x180087986  mov     r9, r12
0x180087989  mov     dword ptr [rsp+78h+var_58], eax
0x18008798d  mov     ebx, eax
0x18008798f  call    fnEfsLogTrace1String1Dword
0x180087994  test    eax, eax
0x180087996  js      loc_180087CAF
0x18008799c  mov     r9d, [rsp+78h+arg_0]
0x1800879a4  test    r15d, r15d
0x1800879a7  jz      short loc_1800879EF
0x1800879a9  test    r9d, r9d
0x1800879ac  jz      short loc_1800879F8
0x1800879ae  test    rsi, rsi
0x1800879b1  jz      short loc_1800879EF
0x1800879b3  mov     r8, rsi
0x1800879b6  mov     rax, r14
0x1800879b9  sub     r8, r14
0x1800879bc  movzx   edx, word ptr [rax]
0x1800879bf  movzx   ecx, word ptr [rax+r8]
0x1800879c4  sub     edx, ecx
0x1800879c6  jnz     short loc_1800879D0
0x1800879c8  add     rax, 2
0x1800879cc  test    ecx, ecx
0x1800879ce  jnz     short loc_1800879BC
0x1800879d0  test    edx, edx
0x1800879d2  jz      short loc_1800879EF
0x1800879d4  mov     ebx, 80070005h
0x1800879d9  mov     dword ptr [rsp+78h+var_58], 147Eh
0x1800879e1  mov     r9d, edi
0x1800879e4  mov     r8d, 80070005h
0x1800879ea  jmp     loc_1800878FC
0x1800879ef  test    r9d, r9d
0x1800879f2  jnz     loc_180087C36
0x1800879f8  test    rsi, rsi
0x1800879fb  jz      loc_180087C36
0x180087a01  mov     r8, rsi
0x180087a04  mov     rax, r14
0x180087a07  sub     r8, r14
0x180087a0a  movzx   ecx, word ptr [rax]
0x180087a0d  movzx   edx, word ptr [rax+r8]
0x180087a12  sub     ecx, edx
0x180087a14  jnz     short loc_180087A1E
0x180087a16  add     rax, 2
0x180087a1a  test    edx, edx
0x180087a1c  jnz     short loc_180087A0A
0x180087a1e  test    ecx, ecx
0x180087a20  jz      loc_180087C36
0x180087a26  mov     r12d, 14A1h
0x180087a2c  lea     r8, sourceString
0x180087a33  mov     r9d, edi
0x180087a36  mov     dword ptr [rsp+78h+var_58], r12d
0x180087a3b  lea     rdx, EFS_TRACE_START_EVENT
0x180087a42  call    fnEfsLogTrace1Strings
0x180087a47  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180087a4b  lea     r15, [rbp+18h]
0x180087a4f  mov     r14d, 1
0x180087a55  mov     [rsp+78h+var_58], r15; unsigned __int16 **
0x180087a5a  mov     r8, rdx; unsigned __int64
0x180087a5d  mov     r9d, r14d; int
0x180087a60  mov     rcx, rsi; unsigned __int16 *
0x180087a63  call    ?DuplicateSvcString@CDplService@@SAJPEBG_K1HPEAPEAG@Z; CDplService::DuplicateSvcString(ushort const *,unsigned __int64,unsigned __int64,int,ushort * *)
0x180087a68  mov     rcx, cs:g_hPublisher
0x180087a6f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180087a76  mov     [rsp+78h+var_48], r12d
0x180087a7b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180087a82  lea     r12, sourceString
0x180087a89  mov     [rsp+78h+var_50], edi
0x180087a8d  mov     r9, r12
0x180087a90  mov     dword ptr [rsp+78h+var_58], eax
0x180087a94  mov     ebx, eax
0x180087a96  call    fnEfsLogTrace1String1Dword
0x180087a9b  test    eax, eax
0x180087a9d  js      loc_180087CAF
0x180087aa3  mov     esi, 14A9h
0x180087aa8  lea     rdx, EFS_TRACE_START_EVENT
0x180087aaf  mov     r9d, edi
0x180087ab2  mov     dword ptr [rsp+78h+var_58], esi
0x180087ab6  mov     r8, r12
0x180087ab9  call    fnEfsLogTrace1Strings
0x180087abe  mov     rcx, [r15]; unsigned __int16 *
0x180087ac1  lea     rdx, [rsp+78h+ExistingTokenHandle]; void **
0x180087ac6  call    ?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z; EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)
0x180087acb  mov     rcx, cs:g_hPublisher
0x180087ad2  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180087ad9  mov     [rsp+78h+var_48], esi
0x180087add  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180087ae4  mov     [rsp+78h+var_50], edi
0x180087ae8  mov     r9, r12
0x180087aeb  mov     dword ptr [rsp+78h+var_58], eax
0x180087aef  mov     ebx, eax
0x180087af1  call    fnEfsLogTrace1String1Dword
0x180087af6  test    eax, eax
0x180087af8  js      loc_180087CAF
0x180087afe  cmp     ebx, r14d
0x180087b01  jz      loc_180087C1B
0x180087b07  cmp     [rsp+78h+ExistingTokenHandle], 0
0x180087b0d  jz      loc_180087C1B
0x180087b13  mov     esi, 14BAh
0x180087b18  lea     rdx, EFS_TRACE_START_EVENT
0x180087b1f  mov     r9d, edi
0x180087b22  mov     dword ptr [rsp+78h+var_58], esi
0x180087b26  mov     r8, r12
0x180087b29  call    fnEfsLogTrace1Strings
0x180087b2e  lea     r15, [rbp+8]
0x180087b32  mov     rcx, r15; void **
0x180087b35  call    ?EdpCredSvcGetImpersonationCtxAndRevertToSelf@@YAJPEAPEAX@Z; EdpCredSvcGetImpersonationCtxAndRevertToSelf(void * *)
0x180087b3a  mov     rcx, cs:g_hPublisher
0x180087b41  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180087b48  mov     [rsp+78h+var_48], esi
0x180087b4c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180087b53  mov     [rsp+78h+var_50], edi
0x180087b57  mov     r9, r12
0x180087b5a  mov     dword ptr [rsp+78h+var_58], eax
0x180087b5e  mov     ebx, eax
0x180087b60  call    fnEfsLogTrace1String1Dword
0x180087b65  test    eax, eax
0x180087b67  js      loc_180087CAF
0x180087b6d  mov     rcx, [rsp+78h+ExistingTokenHandle]; ExistingTokenHandle
0x180087b72  lea     rsi, [rbp+10h]
0x180087b76  mov     r8, rsi; DuplicateTokenHandle
0x180087b79  lea     edx, [r14+1]; ImpersonationLevel
0x180087b7d  call    cs:__imp_DuplicateToken
0x180087b83  test    eax, eax
0x180087b85  jnz     short loc_180087BCC
0x180087b87  call    cs:__imp_GetLastError
0x180087b8d  mov     ebx, eax
0x180087b8f  test    eax, eax
0x180087b91  jle     short loc_180087B9C
0x180087b93  movzx   ebx, ax
0x180087b96  or      ebx, 80070000h
0x180087b9c  mov     rcx, [rsi]; hObject
0x180087b9f  test    rcx, rcx
0x180087ba2  jz      short loc_180087BB1
0x180087ba4  call    cs:__imp_CloseHandle
0x180087baa  mov     qword ptr [rsi], 0
0x180087bb1  mov     rcx, r15; void **
0x180087bb4  call    ?EdpCredSvcRestoreImpersonationCtx@@YAXPEAPEAX@Z; EdpCredSvcRestoreImpersonationCtx(void * *)
0x180087bb9  mov     dword ptr [rsp+78h+var_58], 14C8h
0x180087bc1  mov     r9d, edi
0x180087bc4  mov     r8d, ebx
0x180087bc7  jmp     loc_1800878FC
0x180087bcc  mov     rdx, [rsi]; Token
0x180087bcf  xor     ecx, ecx; Thread
0x180087bd1  call    cs:__imp_SetThreadToken
0x180087bd7  test    eax, eax
0x180087bd9  jnz     loc_180087CAB
0x180087bdf  call    cs:__imp_GetLastError
0x180087be5  mov     ebx, eax
0x180087be7  test    eax, eax
0x180087be9  jle     short loc_180087BF4
0x180087beb  movzx   ebx, ax
0x180087bee  or      ebx, 80070000h
0x180087bf4  mov     rcx, [rsi]; hObject
0x180087bf7  test    rcx, rcx
0x180087bfa  jz      short loc_180087C09
0x180087bfc  call    cs:__imp_CloseHandle
0x180087c02  mov     qword ptr [rsi], 0
0x180087c09  mov     rcx, r15; void **
0x180087c0c  call    ?EdpCredSvcRestoreImpersonationCtx@@YAXPEAPEAX@Z; EdpCredSvcRestoreImpersonationCtx(void * *)
0x180087c11  mov     dword ptr [rsp+78h+var_58], 14D4h
0x180087c19  jmp     short loc_180087BC1
0x180087c1b  mov     ebx, 800704DDh
0x180087c20  mov     dword ptr [rsp+78h+var_58], 14B2h
0x180087c28  mov     r9d, edi
0x180087c2b  mov     r8d, 800704DDh
0x180087c31  jmp     loc_1800878FC
0x180087c36  mov     r15d, 148Fh
0x180087c3c  lea     rdx, EFS_TRACE_START_EVENT
0x180087c43  mov     r9d, edi
0x180087c46  mov     dword ptr [rsp+78h+var_58], r15d
0x180087c4b  mov     r8, r12
0x180087c4e  call    fnEfsLogTrace1Strings
0x180087c53  lea     rax, [rbp+18h]
0x180087c57  test    rsi, rsi
0x180087c5a  mov     [rsp+78h+var_58], rax; unsigned __int16 **
0x180087c5f  cmovz   rsi, r14
0x180087c63  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180087c67  mov     r14d, 1
0x180087c6d  mov     r8, rdx; unsigned __int64
0x180087c70  mov     r9d, r14d; int
0x180087c73  mov     rcx, rsi; unsigned __int16 *
0x180087c76  call    ?DuplicateSvcString@CDplService@@SAJPEBG_K1HPEAPEAG@Z; CDplService::DuplicateSvcString(ushort const *,unsigned __int64,unsigned __int64,int,ushort * *)
0x180087c7b  mov     rcx, cs:g_hPublisher
0x180087c82  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180087c89  mov     [rsp+78h+var_48], r15d
0x180087c8e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180087c95  mov     [rsp+78h+var_50], edi
0x180087c99  mov     r9, r12
0x180087c9c  mov     dword ptr [rsp+78h+var_58], eax
0x180087ca0  mov     ebx, eax
0x180087ca2  call    fnEfsLogTrace1String1Dword
0x180087ca7  test    eax, eax
0x180087ca9  js      short loc_180087CAF
0x180087cab  mov     [rbp+20h], r14d
0x180087caf  mov     rcx, [rsp+78h+ExistingTokenHandle]; hObject
0x180087cb4  test    rcx, rcx
0x180087cb7  jz      short loc_180087CBF
0x180087cb9  call    cs:__imp_CloseHandle
0x180087cbf  lea     r11, [rsp+78h+var_28]
0x180087cc4  mov     eax, ebx
0x180087cc6  mov     rbx, [r11+38h]
0x180087cca  mov     rbp, [r11+40h]
0x180087cce  mov     rsp, r11
0x180087cd1  pop     r15
0x180087cd3  pop     r14
0x180087cd5  pop     r12
0x180087cd7  pop     rdi
0x180087cd8  pop     rsi
0x180087cd9  retn
```
