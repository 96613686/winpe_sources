# _CheckSpecialCaller

- ea: `0x180020794`
- end: `0x180020a1e`
- name: `_CheckSpecialCaller`
- size: `650`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020030`

## callees

- `0x180003140`
- `0x180020794`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004b430`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020825`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002087c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020825`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002087c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800207df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800207df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800207f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800207f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002082f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002082f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckSpecialCaller(char *a1)
{
  HANDLE CurrentThread; // rax
  char v3; // di
  DWORD v4; // eax
  DWORD v5; // ebx
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-39h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-35h] BYREF
  __int64 Buf1; // [rsp+38h] [rbp-31h] BYREF
  BOOL (__stdcall *v12)(HANDLE); // [rsp+40h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  int v14; // [rsp+50h] [rbp-19h]
  _OWORD v15[3]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v16; // [rsp+88h] [rbp+1Fh]

  Buf1 = 0;
  TokenInformation = 0;
  v12 = CloseHandle;
  TokenHandle = 0;
  v14 = 0;
  CurrentThread = GetCurrentThread();
  v3 = 1;
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    ReturnLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength)
      && (v4 = GetLastError(), (v5 = v4) != 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids, v4);
    }
    else
    {
      if ( !TokenInformation )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids);
        *a1 = 1;
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
        return 0;
      }
      memset(v15, 0, sizeof(v15));
      v16 = 0;
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenStatistics, v15, 0x38u, &ReturnLength) )
      {
        Buf1 = *((_QWORD *)&v15[0] + 1);
        goto LABEL_8;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( !LastError )
      {
LABEL_8:
        if ( memcmp_0(&Buf1, &qword_18005F3C8, 8u) && memcmp_0(&Buf1, &qword_18005F3C0, 8u) )
        {
          if ( memcmp_0(&Buf1, &qword_18005F3B8, 8u) )
            v3 = 0;
        }
        *a1 = v3;
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids, LastError);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids, v8);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v12);
  }
  return v5;
}

```

## disassembly

```asm
0x180020794  push    rbp
0x180020796  push    rbx
0x180020797  push    rsi
0x180020798  push    rdi
0x180020799  lea     rbp, [rsp-3Fh]
0x18002079e  sub     rsp, 0A8h
0x1800207a5  mov     rax, cs:__security_cookie
0x1800207ac  xor     rax, rsp
0x1800207af  mov     [rbp+57h+var_30], rax
0x1800207b3  mov     rsi, rcx
0x1800207b6  mov     [rbp+57h+Buf1], 0
0x1800207be  mov     [rbp+57h+TokenInformation], 0
0x1800207c5  mov     rax, cs:__imp_CloseHandle
0x1800207cc  mov     [rbp+57h+var_80], rax
0x1800207d0  mov     [rbp+57h+TokenHandle], 0
0x1800207d8  mov     [rbp+57h+var_70], 0
0x1800207df  call    cs:__imp_GetCurrentThread
0x1800207e5  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800207e9  mov     edi, 1
0x1800207ee  mov     r8d, edi; OpenAsSelf
0x1800207f1  lea     ebx, [rdi+0Bh]
0x1800207f4  mov     edx, ebx; DesiredAccess
0x1800207f6  mov     rcx, rax; ThreadHandle
0x1800207f9  call    cs:__imp_OpenThreadToken
0x1800207ff  test    eax, eax
0x180020801  jz      loc_180020914
0x180020807  mov     [rbp+57h+var_90], 0
0x18002080e  lea     rax, [rbp+57h+var_90]
0x180020812  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180020817  lea     r9d, [rdi+3]; TokenInformationLength
0x18002081b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002081f  mov     edx, ebx; TokenInformationClass
0x180020821  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180020825  call    cs:__imp_GetTokenInformation
0x18002082b  test    eax, eax
0x18002082d  jnz     short loc_18002083F
0x18002082f  call    cs:__imp_GetLastError
0x180020835  mov     ebx, eax
0x180020837  test    eax, eax
0x180020839  jnz     loc_18002095D
0x18002083f  cmp     [rbp+57h+TokenInformation], 0
0x180020843  jz      loc_18002099B
0x180020849  xorps   xmm0, xmm0
0x18002084c  xor     eax, eax
0x18002084e  movups  [rbp+57h+var_68], xmm0
0x180020852  movups  [rbp+57h+var_58], xmm0
0x180020856  movups  [rbp+57h+var_48], xmm0
0x18002085a  mov     [rbp+57h+var_38], rax
0x18002085e  mov     [rbp+57h+var_90], eax
0x180020861  lea     rax, [rbp+57h+var_90]
0x180020865  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002086a  mov     r9d, 38h ; '8'; TokenInformationLength
0x180020870  lea     r8, [rbp+57h+var_68]; TokenInformation
0x180020874  lea     edx, [r9-2Eh]; TokenInformationClass
0x180020878  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002087c  call    cs:__imp_GetTokenInformation
0x180020882  test    eax, eax
0x180020884  jz      short loc_180020890
0x180020886  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18002088a  mov     [rbp+57h+Buf1], rax
0x18002088e  jmp     short loc_1800208A0
0x180020890  call    cs:__imp_GetLastError
0x180020896  mov     ebx, eax
0x180020898  test    eax, eax
0x18002089a  jnz     loc_1800209DD
0x1800208a0  mov     ebx, 8
0x1800208a5  mov     r8d, ebx; Size
0x1800208a8  lea     rdx, qword_18005F3C8; Buf2
0x1800208af  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800208b3  call    memcmp_0
0x1800208b8  test    eax, eax
0x1800208ba  jz      short loc_1800208ED
0x1800208bc  mov     r8d, ebx; Size
0x1800208bf  lea     rdx, qword_18005F3C0; Buf2
0x1800208c6  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800208ca  call    memcmp_0
0x1800208cf  test    eax, eax
0x1800208d1  jz      short loc_1800208ED
0x1800208d3  mov     r8d, ebx; Size
0x1800208d6  lea     rdx, qword_18005F3B8; Buf2
0x1800208dd  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800208e1  call    memcmp_0
0x1800208e6  test    eax, eax
0x1800208e8  jz      short loc_1800208ED
0x1800208ea  xor     dil, dil
0x1800208ed  mov     [rsi], dil
0x1800208f0  lea     rcx, [rbp+57h+var_80]
0x1800208f4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800208f9  nop
0x1800208fa  xor     eax, eax
0x1800208fc  mov     rcx, [rbp+57h+var_30]
0x180020900  xor     rcx, rsp; StackCookie
0x180020903  call    __security_check_cookie
0x180020908  add     rsp, 0A8h
0x18002090f  pop     rdi
0x180020910  pop     rsi
0x180020911  pop     rbx
0x180020912  pop     rbp
0x180020913  retn
0x180020914  call    cs:__imp_GetLastError
0x18002091a  mov     ebx, eax
0x18002091c  lea     rdx, WPP_GLOBAL_Control
0x180020923  mov     rcx, cs:WPP_GLOBAL_Control
0x18002092a  cmp     rcx, rdx
0x18002092d  jnz     short loc_18002093D
0x18002092f  lea     rcx, [rbp+57h+var_80]
0x180020933  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020938  nop
0x180020939  mov     eax, ebx
0x18002093b  jmp     short loc_1800208FC
0x18002093d  test    byte ptr [rcx+1Ch], 2
0x180020941  jz      short loc_18002092F
0x180020943  mov     edx, 16h
0x180020948  mov     r9d, ebx
0x18002094b  lea     r8, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids
0x180020952  mov     rcx, [rcx+10h]
0x180020956  call    WPP_SF_d
0x18002095b  jmp     short loc_18002092F
0x18002095d  lea     rdx, WPP_GLOBAL_Control
0x180020964  mov     rcx, cs:WPP_GLOBAL_Control
0x18002096b  cmp     rcx, rdx
0x18002096e  jz      short loc_18002098F
0x180020970  test    byte ptr [rcx+1Ch], 2
0x180020974  jz      short loc_18002098F
0x180020976  mov     edx, 17h
0x18002097b  mov     r9d, ebx
0x18002097e  lea     r8, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids
0x180020985  mov     rcx, [rcx+10h]
0x180020989  call    WPP_SF_d
0x18002098e  nop
0x18002098f  lea     rcx, [rbp+57h+var_80]
0x180020993  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020998  nop
0x180020999  jmp     short loc_180020939
0x18002099b  lea     rdx, WPP_GLOBAL_Control
0x1800209a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209a9  cmp     rcx, rdx
0x1800209ac  jz      short loc_1800209CB
0x1800209ae  mov     ebx, 8
0x1800209b3  test    [rcx+1Ch], bl
0x1800209b6  jz      short loc_1800209CB
0x1800209b8  lea     edx, [rbx+10h]
0x1800209bb  lea     r8, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids
0x1800209c2  mov     rcx, [rcx+10h]
0x1800209c6  call    WPP_SF_
0x1800209cb  mov     [rsi], dil
0x1800209ce  lea     rcx, [rbp+57h+var_80]
0x1800209d2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800209d7  nop
0x1800209d8  jmp     loc_1800208FA
0x1800209dd  lea     rdx, WPP_GLOBAL_Control
0x1800209e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209eb  cmp     rcx, rdx
0x1800209ee  jz      short loc_180020A0F
0x1800209f0  test    byte ptr [rcx+1Ch], 2
0x1800209f4  jz      short loc_180020A0F
0x1800209f6  mov     edx, 19h
0x1800209fb  mov     r9d, ebx
0x1800209fe  lea     r8, WPP_fc3aaf5bf91a3534f189492db6bbf47b_Traceguids
0x180020a05  mov     rcx, [rcx+10h]
0x180020a09  call    WPP_SF_d
0x180020a0e  nop
0x180020a0f  lea     rcx, [rbp+57h+var_80]
0x180020a13  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020a18  nop
0x180020a19  jmp     loc_180020939
```
