# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x180005f14`
- end: `0x1800061ef`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, _QWORD *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003c70`

## callees

- `0x180005f14`
- `0x1800062fc`
- `0x180006430`
- `0x1800065c0`
- `0x1800065ec`
- `0x18000a384`
- `0x180012844`
- `0x180027724`
- `0x18002c28c`
- `0x1800327e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f66`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005f5c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005f5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  void *v6; // rdx
  signed int LastError; // ebx
  __int64 v8; // rcx
  ARI::ProcessToken::SysAppId *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // ebx
  _WORD *v14; // rbx
  unsigned int v15; // esi
  int v16; // edx
  int v17; // ecx
  int v18; // eax
  __int64 v19; // rdx
  char *v20; // r14
  __int64 v21; // rax
  int v22; // ebx
  _WORD *v23; // rbx
  void *v24; // rdx
  int PackageFamilyName; // eax
  __int64 v26; // rdx
  void *v27; // rcx
  unsigned int *v28; // r9
  unsigned int v29; // eax
  __int64 v30; // r8
  bool *v31; // [rsp+20h] [rbp-28h]
  unsigned __int16 *v32; // [rsp+20h] [rbp-28h]
  unsigned __int16 *v33; // [rsp+20h] [rbp-28h]
  PVOID P[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  void *TokenHandle; // [rsp+80h] [rbp+38h] BYREF

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v8 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_7;
    }
    v8 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open(
                (HANDLE)v8,
                P,
                (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **)&P[1],
                v5,
                v31);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_7:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
    goto LABEL_10;
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)v31);
LABEL_10:
    if ( P[0] )
      ARI::Free(P[0], v6);
    return (unsigned int)LastError;
  }
  v10 = (ARI::ProcessToken::SysAppId *)P[1];
  v11 = *((_QWORD *)P[1] + 4);
  v12 = *(unsigned __int16 *)(v11 + 16) >> 1;
  v13 = v12 + 1;
  if ( (_DWORD)v12 == -1 )
  {
    v14 = (_WORD *)(2 * v12);
    memcpy_0(0, *(const void **)(v11 + 24), 2 * v12);
    *v14 = 0;
LABEL_17:
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)0x8000FFFFLL,
      (int)v31);
LABEL_18:
    ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)P);
    return (unsigned int)LastError;
  }
  LODWORD(TokenHandle) = 0;
  PackageFamilyName = ARI::ProcessToken::SysAppId::GetPackageFamilyName(
                        (ARI::ProcessToken::SysAppId *)P[1],
                        0,
                        (unsigned int)&TokenHandle,
                        0,
                        (unsigned __int16 *)v31);
  if ( PackageFamilyName != 122 )
  {
    if ( PackageFamilyName )
      goto LABEL_17;
    if ( !(v13 + (_DWORD)TokenHandle) )
    {
      v26 = (unsigned int)((_DWORD)TokenHandle - 1);
      *(_WORD *)(2 * v26) = 33;
      ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(
        v10,
        (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)~(_DWORD)v26,
        (unsigned int)&TokenHandle,
        (unsigned int *)(2 * v26 + 2),
        (unsigned __int16 *)v31);
      goto LABEL_17;
    }
  }
  v15 = v13 + (_DWORD)TokenHandle;
  TokenHandle = 0;
  CoTaskMemFree(0);
  v18 = _AllocStringWorker<CTCoAllocPolicy>(v17, v16, 0, v15, (_DWORD)v31, (__int64)&TokenHandle);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v18,
      (int)v32);
    v27 = TokenHandle;
LABEL_38:
    CoTaskMemFree(v27);
    goto LABEL_18;
  }
  v19 = *((_QWORD *)v10 + 4);
  v20 = (char *)TokenHandle;
  v21 = *(unsigned __int16 *)(v19 + 16) >> 1;
  v22 = v21 + 1;
  if ( (_DWORD)v21 != -1 )
  {
    v28 = (unsigned int *)TokenHandle;
    LODWORD(TokenHandle) = 0;
    v29 = ARI::ProcessToken::SysAppId::GetPackageFamilyName(
            v10,
            (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)v15,
            (unsigned int)&TokenHandle,
            v28,
            v32);
    if ( v29 != 122 )
    {
      if ( v29 )
      {
LABEL_37:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xAC,
                      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
                      (const char *)v29,
                      (unsigned int)v33);
        v27 = v20;
        goto LABEL_38;
      }
      if ( v15 >= v22 + (int)TokenHandle )
      {
        v30 = (unsigned int)((_DWORD)TokenHandle - 1);
        *(_WORD *)&v20[2 * v30] = 33;
        ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(
          v10,
          (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(v15 - (unsigned int)v30 - 1),
          (unsigned int)&TokenHandle,
          (unsigned int *)&v20[2 * (unsigned int)v30 + 2],
          v33);
        goto LABEL_23;
      }
    }
    v29 = 122;
    goto LABEL_37;
  }
  v23 = (_WORD *)(2 * v21);
  memcpy_0(0, *(const void **)(v19 + 24), 2 * v21);
  *v23 = 0;
LABEL_23:
  *a2 = v20;
  CoTaskMemFree(0);
  if ( P[0] )
    ARI::Free(P[0], v24);
  return 0;
}

```

## disassembly

```asm
0x180005f14  push    rbp
0x180005f16  push    rbx
0x180005f17  push    rsi
0x180005f18  push    rdi
0x180005f19  push    r14
0x180005f1b  push    r15
0x180005f1d  mov     rbp, rsp
0x180005f20  sub     rsp, 48h
0x180005f24  xorps   xmm0, xmm0
0x180005f27  mov     qword ptr [rdx], 0
0x180005f2e  movdqu  xmmword ptr [rbp+P], xmm0
0x180005f33  mov     r15, rdx
0x180005f36  mov     [rbp+TokenHandle], 0
0x180005f3e  mov     rbx, rcx
0x180005f41  call    cs:__imp_GetCurrentProcess
0x180005f47  cmp     rbx, rax
0x180005f4a  jz      loc_1800060DD
0x180005f50  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180005f54  mov     edx, 8; DesiredAccess
0x180005f59  mov     rcx, rbx; ProcessHandle
0x180005f5c  call    cs:__imp_OpenProcessToken
0x180005f62  test    eax, eax
0x180005f64  jnz     short loc_180005F72
0x180005f66  call    cs:__imp_GetLastError
0x180005f6c  mov     ebx, eax
0x180005f6e  test    eax, eax
0x180005f70  jnz     short loc_180005F95
0x180005f72  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180005f76  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x180005f7a  lea     rdx, [rbp+P]; void *
0x180005f7e  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x180005f83  mov     rcx, [rbp+TokenHandle]; hObject
0x180005f87  mov     ebx, eax
0x180005f89  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180005f8d  jz      short loc_180005F95
0x180005f8f  call    cs:__imp_CloseHandle
0x180005f95  test    ebx, ebx
0x180005f97  jg      loc_18000604C
0x180005f9d  cmp     ebx, 80070490h
0x180005fa3  jnz     short loc_180005FC1
0x180005fa5  mov     rcx, [rbp+P]; P
0x180005fa9  test    rcx, rcx
0x180005fac  jnz     loc_180006042
0x180005fb2  mov     eax, ebx
0x180005fb4  add     rsp, 48h
0x180005fb8  pop     r15
0x180005fba  pop     r14
0x180005fbc  pop     rdi
0x180005fbd  pop     rsi
0x180005fbe  pop     rbx
0x180005fbf  pop     rbp
0x180005fc0  retn
0x180005fc1  cmp     ebx, 80070005h
0x180005fc7  jz      short loc_180005FA5
0x180005fc9  test    ebx, ebx
0x180005fcb  js      short loc_180006025
0x180005fcd  mov     rdi, [rbp+P+8]
0x180005fd1  mov     rdx, [rdi+20h]
0x180005fd5  movzx   eax, word ptr [rdx+10h]
0x180005fd9  shr     eax, 1
0x180005fdb  lea     ebx, [rax+1]
0x180005fde  test    ebx, ebx
0x180005fe0  jnz     loc_1800060ED
0x180005fe6  mov     rdx, [rdx+18h]; Src
0x180005fea  lea     rbx, [rax+rax]
0x180005fee  mov     r8, rbx; Size
0x180005ff1  xor     ecx, ecx; void *
0x180005ff3  call    memcpy_0
0x180005ff8  xor     eax, eax
0x180005ffa  mov     [rbx], ax
0x180005ffd  mov     rcx, [rbp+30h]; this
0x180006001  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180006008  mov     ebx, 8000FFFFh
0x18000600d  mov     edx, 0A8h; void *
0x180006012  mov     r9d, ebx; char *
0x180006015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000601a  lea     rcx, [rbp+P]; this
0x18000601e  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180006023  jmp     short loc_180005FB2
0x180006025  mov     rcx, [rbp+30h]; this
0x180006029  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180006030  mov     r9d, ebx; char *
0x180006033  mov     edx, 0A5h; void *
0x180006038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000603d  jmp     loc_180005FA5
0x180006042  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180006047  jmp     loc_180005FB2
0x18000604c  movzx   ebx, bx
0x18000604f  or      ebx, 80070000h
0x180006055  jmp     loc_180005F9D
0x18000605a  lea     esi, [rbx+rcx]
0x18000605d  mov     [rbp+TokenHandle], 0
0x180006065  xor     ecx, ecx; pv
0x180006067  call    cs:__imp_CoTaskMemFree
0x18000606d  lea     rax, [rbp+TokenHandle]
0x180006071  mov     r9d, esi
0x180006074  xor     r8d, r8d
0x180006077  mov     [rsp+48h+var_20], rax
0x18000607c  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180006081  mov     ebx, eax
0x180006083  test    eax, eax
0x180006085  js      loc_18000614C
0x18000608b  mov     rdx, [rdi+20h]
0x18000608f  mov     r14, [rbp+TokenHandle]
0x180006093  movzx   eax, word ptr [rdx+10h]
0x180006097  shr     eax, 1
0x180006099  lea     ebx, [rax+1]
0x18000609c  test    ebx, ebx
0x18000609e  jnz     loc_18000616A
0x1800060a4  mov     rdx, [rdx+18h]; Src
0x1800060a8  lea     rbx, [rax+rax]
0x1800060ac  mov     r8, rbx; Size
0x1800060af  xor     ecx, ecx; void *
0x1800060b1  call    memcpy_0
0x1800060b6  xor     eax, eax
0x1800060b8  mov     [rbx], ax
0x1800060bb  xor     ecx, ecx; pv
0x1800060bd  mov     [r15], r14
0x1800060c0  call    cs:__imp_CoTaskMemFree
0x1800060c6  mov     rcx, [rbp+P]; P
0x1800060ca  test    rcx, rcx
0x1800060cd  jnz     short loc_1800060D6
0x1800060cf  xor     eax, eax
0x1800060d1  jmp     loc_180005FB4
0x1800060d6  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800060db  jmp     short loc_1800060CF
0x1800060dd  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x1800060e4  mov     [rbp+TokenHandle], rcx
0x1800060e8  jmp     loc_180005F76
0x1800060ed  xor     r9d, r9d; unsigned int *
0x1800060f0  mov     dword ptr [rbp+TokenHandle], 0
0x1800060f7  lea     r8, [rbp+TokenHandle]; unsigned int
0x1800060fb  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800060fd  mov     rcx, rdi; this
0x180006100  call    ?GetPackageFamilyName@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetPackageFamilyName(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x180006105  mov     ecx, dword ptr [rbp+TokenHandle]
0x180006108  cmp     eax, 7Ah ; 'z'
0x18000610b  jz      loc_18000605A
0x180006111  test    eax, eax
0x180006113  jnz     loc_180005FFD
0x180006119  lea     eax, [rbx+rcx]
0x18000611c  test    eax, eax
0x18000611e  jnz     loc_18000605A
0x180006124  lea     edx, [rcx-1]
0x180006127  mov     rcx, rdi; this
0x18000612a  mov     word ptr ds:0[rdx*2], 21h ; '!'
0x180006134  lea     r9, ds:2[rdx*2]; unsigned int *
0x18000613c  not     edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x18000613e  lea     r8, [rbp+TokenHandle]; unsigned int
0x180006142  call    ?GetPackageRelativeApplicationId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x180006147  jmp     loc_180005FFD
0x18000614c  mov     rcx, [rbp+30h]; this
0x180006150  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180006157  mov     r9d, eax; char *
0x18000615a  mov     edx, 0ABh; void *
0x18000615f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006164  mov     rcx, [rbp+TokenHandle]
0x180006168  jmp     short loc_1800061E4
0x18000616a  mov     r9, r14; unsigned int *
0x18000616d  mov     dword ptr [rbp+TokenHandle], 0
0x180006174  lea     r8, [rbp+TokenHandle]; unsigned int
0x180006178  mov     edx, esi; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x18000617a  mov     rcx, rdi; this
0x18000617d  call    ?GetPackageFamilyName@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetPackageFamilyName(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x180006182  cmp     eax, 7Ah ; 'z'
0x180006185  jz      short loc_1800061C2
0x180006187  test    eax, eax
0x180006189  jnz     short loc_1800061C7
0x18000618b  mov     r8d, dword ptr [rbp+TokenHandle]
0x18000618f  lea     eax, [rbx+r8]
0x180006193  cmp     esi, eax
0x180006195  jb      short loc_1800061C2
0x180006197  dec     r8d
0x18000619a  mov     rcx, rdi; this
0x18000619d  mov     eax, r8d
0x1800061a0  sub     esi, r8d
0x1800061a3  inc     rax
0x1800061a6  mov     word ptr [r14+r8*2], 21h ; '!'
0x1800061ad  lea     r8, [rbp+TokenHandle]; unsigned int
0x1800061b1  lea     edx, [rsi-1]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800061b4  lea     r9, [r14+rax*2]; unsigned int *
0x1800061b8  call    ?GetPackageRelativeApplicationId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800061bd  jmp     loc_1800060BB
0x1800061c2  mov     eax, 7Ah ; 'z'
0x1800061c7  mov     rcx, [rbp+30h]; this
0x1800061cb  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800061d2  mov     r9d, eax; char *
0x1800061d5  mov     edx, 0ACh; void *
0x1800061da  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800061df  mov     ebx, eax
0x1800061e1  mov     rcx, r14; pv
0x1800061e4  call    cs:__imp_CoTaskMemFree
0x1800061ea  jmp     loc_18000601A
```
