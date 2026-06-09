# GenerateBuiltinVaultName(ushort * *)

- ea: `0x1800032f8`
- end: `0x180003675`
- name: `?GenerateBuiltinVaultName@@YAKPEAPEAG@Z`
- size: `893`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003270`
- `0x1800384b8`
- `0x18003c4e0`

## callees

- `0x180003140`
- `0x1800031f0`
- `0x1800032f8`
- `0x18000367c`
- `0x180003718`
- `0x18003a580`
- `0x18003af10`
- `0x18003b7d8`
- `0x18003b9ac`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800033b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800033b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000335a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000335a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000336f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000336f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003345`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GenerateBuiltinVaultName(unsigned __int16 **a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  unsigned int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rax
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 Buf1; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  BOOL (__stdcall *v14)(HANDLE); // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  _OWORD TokenInformation[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+90h] [rbp-70h]
  unsigned __int16 v19[520]; // [rsp+A0h] [rbp-60h] BYREF

  v11 = 0;
  memset_0(v19, 0, 0x402u);
  Buf1 = 0;
  v14 = CloseHandle;
  TokenHandle = 0;
  v16 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return LastError;
  }
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v18 = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    Buf1 = *((_QWORD *)&TokenInformation[0] + 1);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
      return LastError;
    }
  }
  if ( !memcmp_0(&Buf1, &qword_18005F3C8, 8u)
    || !memcmp_0(&Buf1, &qword_18005F3C0, 8u)
    || !memcmp_0(&Buf1, &qword_18005F3B8, 8u) )
  {
    LastError = GetFailsafeBuiltinVaultName(a1);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return LastError;
  }
  v11 = 513;
  v4 = VaultLoadResourceWithFormat(VaultGlobals::g_hModuleHandle, 0x2716u, v19, &v11);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, v4);
    goto LABEL_17;
  }
  if ( !a1 )
  {
    v7 = 87;
LABEL_14:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids,
        (unsigned int)v7);
LABEL_17:
    LastError = GetFailsafeBuiltinVaultName(a1);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return LastError;
  }
  v5 = -1;
  do
    ++v5;
  while ( v19[v5] );
  v6 = (unsigned int)(v5 + 1);
  if ( (unsigned int)v6 < (unsigned int)v5 || (v9 = v5 + 1, (unsigned __int64)(2 * v6) > 0xFFFFFFFF) )
  {
    v7 = 534;
    goto LABEL_14;
  }
  v10 = (unsigned __int16 *)(*((__int64 (__fastcall **)(void **, _QWORD))VaultGlobals::g_HeapAlloc[0] + 2))(
                              VaultGlobals::g_HeapAlloc,
                              (unsigned int)(2 * v6));
  *a1 = v10;
  if ( !v10 )
  {
    v7 = 14;
    goto LABEL_14;
  }
  v7 = StringCchCopyW(v10, v9, v19);
  if ( v7 < 0 )
  {
    (*((void (__fastcall **)(void **, _QWORD))VaultGlobals::g_HeapAlloc[0] + 1))(VaultGlobals::g_HeapAlloc, *a1);
    *a1 = 0;
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v7 = (unsigned __int16)v7;
    if ( v7 )
      goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, v19);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
  return 0;
}

```

## disassembly

```asm
0x1800032f8  mov     [rsp-8+arg_8], rbx
0x1800032fd  mov     [rsp-8+arg_10], rsi
0x180003302  push    rbp
0x180003303  push    rdi
0x180003304  push    r14
0x180003306  lea     rbp, [rsp-3C0h]
0x18000330e  sub     rsp, 4C0h
0x180003315  mov     rax, cs:__security_cookie
0x18000331c  xor     rax, rsp
0x18000331f  mov     [rbp+3D0h+var_20], rax
0x180003326  mov     rdi, rcx
0x180003329  xor     esi, esi
0x18000332b  mov     [rsp+4D0h+var_4A0], esi
0x18000332f  xor     edx, edx; Val
0x180003331  mov     r8d, 402h; Size
0x180003337  lea     rcx, [rbp+3D0h+var_430]; void *
0x18000333b  call    memset_0
0x180003340  mov     [rsp+4D0h+Buf1], rsi
0x180003345  mov     rax, cs:__imp_CloseHandle
0x18000334c  mov     [rsp+4D0h+var_488], rax
0x180003351  mov     [rsp+4D0h+TokenHandle], rsi
0x180003356  mov     [rsp+4D0h+var_478], esi
0x18000335a  call    cs:__imp_GetCurrentThread
0x180003360  lea     r9, [rsp+4D0h+TokenHandle]; TokenHandle
0x180003365  lea     edx, [rsi+0Ch]; DesiredAccess
0x180003368  lea     r8d, [rsi+1]; OpenAsSelf
0x18000336c  mov     rcx, rax; ThreadHandle
0x18000336f  call    cs:__imp_OpenThreadToken
0x180003375  test    eax, eax
0x180003377  jz      loc_1800035CB
0x18000337d  xorps   xmm0, xmm0
0x180003380  xor     eax, eax
0x180003382  movups  [rsp+4D0h+TokenInformation], xmm0
0x180003387  movups  [rsp+4D0h+var_460], xmm0
0x18000338c  movups  [rbp+3D0h+var_450], xmm0
0x180003390  mov     [rbp+3D0h+var_440], rax
0x180003394  mov     [rsp+4D0h+var_490], esi
0x180003398  lea     rax, [rsp+4D0h+var_490]
0x18000339d  mov     [rsp+4D0h+ReturnLength], rax; ReturnLength
0x1800033a2  lea     r9d, [rsi+38h]; TokenInformationLength
0x1800033a6  lea     r8, [rsp+4D0h+TokenInformation]; TokenInformation
0x1800033ab  lea     edx, [rsi+0Ah]; TokenInformationClass
0x1800033ae  mov     rcx, [rsp+4D0h+TokenHandle]; TokenHandle
0x1800033b3  call    cs:__imp_GetTokenInformation
0x1800033b9  test    eax, eax
0x1800033bb  jz      short loc_1800033C9
0x1800033bd  mov     rax, qword ptr [rsp+4D0h+TokenInformation+8]
0x1800033c2  mov     [rsp+4D0h+Buf1], rax
0x1800033c7  jmp     short loc_1800033D9
0x1800033c9  call    cs:__imp_GetLastError
0x1800033cf  mov     ebx, eax
0x1800033d1  test    eax, eax
0x1800033d3  jnz     loc_1800035E3
0x1800033d9  mov     r14d, 8
0x1800033df  mov     r8d, r14d; Size
0x1800033e2  lea     rdx, qword_18005F3C8; Buf2
0x1800033e9  lea     rcx, [rsp+4D0h+Buf1]; Buf1
0x1800033ee  call    memcmp_0
0x1800033f3  test    eax, eax
0x1800033f5  jz      loc_180003506
0x1800033fb  mov     r8d, r14d; Size
0x1800033fe  lea     rdx, qword_18005F3C0; Buf2
0x180003405  lea     rcx, [rsp+4D0h+Buf1]; Buf1
0x18000340a  call    memcmp_0
0x18000340f  test    eax, eax
0x180003411  jz      loc_180003506
0x180003417  mov     r8d, r14d; Size
0x18000341a  lea     rdx, qword_18005F3B8; Buf2
0x180003421  lea     rcx, [rsp+4D0h+Buf1]; Buf1
0x180003426  call    memcmp_0
0x18000342b  test    eax, eax
0x18000342d  jz      loc_180003506
0x180003433  mov     [rsp+4D0h+var_4A0], 201h
0x18000343b  lea     r9, [rsp+4D0h+var_4A0]; unsigned int *
0x180003440  lea     r8, [rbp+3D0h+var_430]; unsigned __int16 *
0x180003444  mov     edx, 2716h; unsigned int
0x180003449  mov     rcx, cs:?g_hModuleHandle@VaultGlobals@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180003450  call    ?VaultLoadResourceWithFormat@@YAKPEAUHINSTANCE__@@KPEAGPEAKZZ; VaultLoadResourceWithFormat(HINSTANCE__ *,ulong,ushort *,ulong *,...)
0x180003455  test    eax, eax
0x180003457  jnz     short loc_1800034B1
0x180003459  test    rdi, rdi
0x18000345c  jz      loc_180003643
0x180003462  lea     rcx, [rbp+3D0h+var_430]
0x180003466  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000346a  inc     rax
0x18000346d  cmp     [rcx+rax*2], si
0x180003471  jnz     short loc_18000346A
0x180003473  lea     ecx, [rax+1]
0x180003476  cmp     ecx, eax
0x180003478  jnb     loc_18000351D
0x18000347e  mov     ebx, 216h
0x180003483  lea     rcx, WPP_GLOBAL_Control
0x18000348a  mov     rax, cs:WPP_GLOBAL_Control
0x180003491  cmp     rax, rcx
0x180003494  jnz     loc_18000364D
0x18000349a  mov     rcx, rdi; unsigned __int16 **
0x18000349d  call    ?GetFailsafeBuiltinVaultName@@YAKPEAPEAG@Z; GetFailsafeBuiltinVaultName(ushort * *)
0x1800034a2  mov     ebx, eax
0x1800034a4  lea     rcx, [rsp+4D0h+var_488]
0x1800034a9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800034ae  nop
0x1800034af  jmp     short loc_1800034DD
0x1800034b1  lea     rcx, WPP_GLOBAL_Control
0x1800034b8  mov     r10, cs:WPP_GLOBAL_Control
0x1800034bf  cmp     r10, rcx
0x1800034c2  jnz     loc_1800035F3
0x1800034c8  mov     rcx, rdi; unsigned __int16 **
0x1800034cb  call    ?GetFailsafeBuiltinVaultName@@YAKPEAPEAG@Z; GetFailsafeBuiltinVaultName(ushort * *)
0x1800034d0  mov     ebx, eax
0x1800034d2  lea     rcx, [rsp+4D0h+var_488]
0x1800034d7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800034dc  nop
0x1800034dd  mov     eax, ebx
0x1800034df  mov     rcx, [rbp+3D0h+var_20]
0x1800034e6  xor     rcx, rsp; StackCookie
0x1800034e9  call    __security_check_cookie
0x1800034ee  lea     r11, [rsp+4D0h+var_10]
0x1800034f6  mov     rbx, [r11+28h]
0x1800034fa  mov     rsi, [r11+30h]
0x1800034fe  mov     rsp, r11
0x180003501  pop     r14
0x180003503  pop     rdi
0x180003504  pop     rbp
0x180003505  retn
0x180003506  mov     rcx, rdi; unsigned __int16 **
0x180003509  call    ?GetFailsafeBuiltinVaultName@@YAKPEAPEAG@Z; GetFailsafeBuiltinVaultName(ushort * *)
0x18000350e  mov     ebx, eax
0x180003510  lea     rcx, [rsp+4D0h+var_488]
0x180003515  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000351a  nop
0x18000351b  jmp     short loc_1800034DD
0x18000351d  mov     ebx, ecx
0x18000351f  lea     rax, [rcx+rcx]
0x180003523  mov     ecx, 0FFFFFFFFh
0x180003528  cmp     rax, rcx
0x18000352b  ja      loc_18000347E
0x180003531  mov     edx, eax
0x180003533  mov     rax, cs:?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x18000353a  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x180003541  mov     rax, [rax+10h]
0x180003545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354a  mov     [rdi], rax
0x18000354d  test    rax, rax
0x180003550  jz      loc_18000361B
0x180003556  lea     r8, [rbp+3D0h+var_430]; unsigned __int16 *
0x18000355a  mov     edx, ebx; unsigned __int64
0x18000355c  mov     rcx, rax; unsigned __int16 *
0x18000355f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003564  mov     ebx, eax
0x180003566  test    eax, eax
0x180003568  jns     short loc_1800035A0
0x18000356a  mov     rax, cs:?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x180003571  mov     rdx, [rdi]
0x180003574  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x18000357b  mov     rax, [rax+8]
0x18000357f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003584  mov     [rdi], rsi
0x180003587  mov     eax, ebx
0x180003589  and     eax, 1FFF0000h
0x18000358e  cmp     eax, 70000h
0x180003593  jnz     short loc_180003598
0x180003595  movzx   ebx, bx
0x180003598  test    ebx, ebx
0x18000359a  jnz     loc_180003483
0x1800035a0  lea     rcx, WPP_GLOBAL_Control
0x1800035a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800035ae  cmp     rax, rcx
0x1800035b1  jz      short loc_1800035B9
0x1800035b3  test    [rax+1Ch], r14b
0x1800035b7  jnz     short loc_180003625
0x1800035b9  lea     rcx, [rsp+4D0h+var_488]
0x1800035be  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800035c3  nop
0x1800035c4  xor     eax, eax
0x1800035c6  jmp     loc_1800034DF
0x1800035cb  call    cs:__imp_GetLastError
0x1800035d1  mov     ebx, eax
0x1800035d3  lea     rcx, [rsp+4D0h+var_488]
0x1800035d8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800035dd  nop
0x1800035de  jmp     loc_1800034DD
0x1800035e3  lea     rcx, [rsp+4D0h+var_488]
0x1800035e8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800035ed  nop
0x1800035ee  jmp     loc_1800034DD
0x1800035f3  test    byte ptr [r10+1Ch], 2
0x1800035f8  jz      loc_1800034C8
0x1800035fe  mov     edx, 0Bh
0x180003603  mov     r9d, eax
0x180003606  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x18000360d  mov     rcx, [r10+10h]
0x180003611  call    WPP_SF_d
0x180003616  jmp     loc_1800034C8
0x18000361b  mov     ebx, 0Eh
0x180003620  jmp     loc_180003483
0x180003625  mov     edx, 0Dh
0x18000362a  lea     r9, [rbp+3D0h+var_430]
0x18000362e  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180003635  mov     rcx, [rax+10h]
0x180003639  call    WPP_SF_S
0x18000363e  jmp     loc_1800035B9
0x180003643  mov     ebx, 57h ; 'W'
0x180003648  jmp     loc_180003483
0x18000364d  test    byte ptr [rax+1Ch], 2
0x180003651  jz      loc_18000349A
0x180003657  mov     edx, 0Ch
0x18000365c  mov     r9d, ebx
0x18000365f  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180003666  mov     rcx, [rax+10h]
0x18000366a  call    WPP_SF_d
0x18000366f  jmp     loc_18000349A
```
