# BdeSvcApipConversionEncryptEx

- ea: `0x18004d390`
- end: `0x18004d68c`
- name: `BdeSvcApipConversionEncryptEx`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18004d300`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180034070`
- `0x18004d390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d52a`
- `RPCRT4!RpcImpersonateClient` at `0x18004d4f4`
- `RPCRT4!RpcImpersonateClient` at `0x18004d4f4`
- `RPCRT4!RpcRevertToSelf` at `0x18004d610`
- `RPCRT4!RpcRevertToSelf` at `0x18004d610`
- `FVEAPI!FveConversionEncryptPendingRebootEx` at `0x18004d5d8`
- `FVEAPI!FveConversionEncryptPendingRebootEx` at `0x18004d5d8`
- `FVEAPI!FveConversionEncryptEx` at `0x18004d5af`
- `FVEAPI!FveConversionEncryptEx` at `0x18004d5af`
- `FVEAPI!FveOpenVolumeW` at `0x18004d579`
- `FVEAPI!FveOpenVolumeW` at `0x18004d579`
- `FVEAPI!FveCloseVolume` at `0x18004d630`
- `FVEAPI!FveCloseVolume` at `0x18004d630`

## pseudocode

```c
__int64 __fastcall BdeSvcApipConversionEncryptEx(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  PVOID *v7; // rcx
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  signed int LastError; // eax
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v17; // [rsp+20h] [rbp-28h] BYREF

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = -1;
  if ( (a4 & 0x10000) != 0 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
    {
      WPP_SF_(v7[2], 41, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 2147942487LL;
    v9 = -2147024809;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
    {
      v10 = 42;
LABEL_11:
      WPP_SF_d(v7[2], v10, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v8);
LABEL_50:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  if ( (a4 & 2) == 0 )
  {
    if ( (a4 & 4) != 0 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
      {
        WPP_SF_(v7[2], 45, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      v8 = 2147942487LL;
      v9 = -2147024809;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
      {
        v10 = 46;
        goto LABEL_11;
      }
      goto LABEL_51;
    }
    v11 = RpcImpersonateClient(0);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v11);
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v10 = 48;
        v8 = v9;
        goto LABEL_11;
      }
      goto LABEL_51;
    }
    v13 = FveOpenVolumeW(a2, 1, &v17);
    v9 = v13;
    if ( v13 >= 0 )
    {
      if ( a3 )
      {
        v13 = FveConversionEncryptPendingRebootEx(v17, a4);
        v9 = v13;
        if ( v13 >= 0 )
          goto LABEL_49;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_49;
        v15 = 51;
      }
      else
      {
        v13 = FveConversionEncryptEx(v17, a4);
        v9 = v13;
        if ( v13 >= 0 )
          goto LABEL_49;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_49;
        v15 = 50;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_49;
      v15 = 49;
    }
    WPP_SF_d(v14[2], v15, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v13);
LABEL_49:
    RpcRevertToSelf();
    goto LABEL_50;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
  {
    WPP_SF_(v7[2], 43, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = 2147942487LL;
  v9 = -2147024809;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
  {
    v10 = 44;
    goto LABEL_11;
  }
LABEL_51:
  if ( v17 != -1 )
  {
    FveCloseVolume(v17);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v17 = -1;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_(v7[2], 52, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x18004d390  mov     [rsp+arg_0], rbx
0x18004d395  mov     [rsp+arg_10], rbp
0x18004d39a  push    rsi
0x18004d39b  push    r14
0x18004d39d  push    r15
0x18004d39f  sub     rsp, 30h
0x18004d3a3  mov     rax, cs:__security_cookie
0x18004d3aa  xor     rax, rsp
0x18004d3ad  mov     [rsp+48h+var_20], rax
0x18004d3b2  mov     esi, r9d
0x18004d3b5  mov     ebp, r8d
0x18004d3b8  mov     rbx, rdx
0x18004d3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d3c2  lea     r14, WPP_GLOBAL_Control
0x18004d3c9  lea     r15, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004d3d0  cmp     rcx, r14
0x18004d3d3  jz      short loc_18004D3F3
0x18004d3d5  test    byte ptr [rcx+1Ch], 20h
0x18004d3d9  jz      short loc_18004D3F3
0x18004d3db  mov     rcx, [rcx+10h]
0x18004d3df  mov     edx, 28h ; '('
0x18004d3e4  mov     r8, r15
0x18004d3e7  call    WPP_SF_
0x18004d3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d3f3  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x18004d3fc  bt      esi, 10h
0x18004d400  jnb     short loc_18004D457
0x18004d402  cmp     rcx, r14
0x18004d405  jz      short loc_18004D425
0x18004d407  test    byte ptr [rcx+1Ch], 2
0x18004d40b  jz      short loc_18004D425
0x18004d40d  mov     rcx, [rcx+10h]
0x18004d411  mov     edx, 29h ; ')'
0x18004d416  mov     r8, r15
0x18004d419  call    WPP_SF_
0x18004d41e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d425  mov     r9d, 80070057h
0x18004d42b  mov     ebx, r9d
0x18004d42e  cmp     rcx, r14
0x18004d431  jz      loc_18004D623
0x18004d437  test    byte ptr [rcx+1Ch], 40h
0x18004d43b  jz      loc_18004D623
0x18004d441  mov     edx, 2Ah ; '*'
0x18004d446  mov     rcx, [rcx+10h]
0x18004d44a  mov     r8, r15
0x18004d44d  call    WPP_SF_d
0x18004d452  jmp     loc_18004D61C
0x18004d457  test    sil, 2
0x18004d45b  jz      short loc_18004D4A3
0x18004d45d  cmp     rcx, r14
0x18004d460  jz      short loc_18004D480
0x18004d462  test    byte ptr [rcx+1Ch], 2
0x18004d466  jz      short loc_18004D480
0x18004d468  mov     rcx, [rcx+10h]
0x18004d46c  mov     edx, 2Bh ; '+'
0x18004d471  mov     r8, r15
0x18004d474  call    WPP_SF_
0x18004d479  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d480  mov     r9d, 80070057h
0x18004d486  mov     ebx, r9d
0x18004d489  cmp     rcx, r14
0x18004d48c  jz      loc_18004D623
0x18004d492  test    byte ptr [rcx+1Ch], 40h
0x18004d496  jz      loc_18004D623
0x18004d49c  mov     edx, 2Ch ; ','
0x18004d4a1  jmp     short loc_18004D446
0x18004d4a3  test    sil, 4
0x18004d4a7  jz      short loc_18004D4F2
0x18004d4a9  cmp     rcx, r14
0x18004d4ac  jz      short loc_18004D4CC
0x18004d4ae  test    byte ptr [rcx+1Ch], 2
0x18004d4b2  jz      short loc_18004D4CC
0x18004d4b4  mov     rcx, [rcx+10h]
0x18004d4b8  mov     edx, 2Dh ; '-'
0x18004d4bd  mov     r8, r15
0x18004d4c0  call    WPP_SF_
0x18004d4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d4cc  mov     r9d, 80070057h
0x18004d4d2  mov     ebx, r9d
0x18004d4d5  cmp     rcx, r14
0x18004d4d8  jz      loc_18004D623
0x18004d4de  test    byte ptr [rcx+1Ch], 40h
0x18004d4e2  jz      loc_18004D623
0x18004d4e8  mov     edx, 2Eh ; '.'
0x18004d4ed  jmp     loc_18004D446
0x18004d4f2  xor     ecx, ecx; BindingHandle
0x18004d4f4  call    cs:__imp_RpcImpersonateClient
0x18004d4fb  nop     dword ptr [rax+rax+00h]
0x18004d500  test    eax, eax
0x18004d502  jz      short loc_18004D56C
0x18004d504  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d50b  cmp     rcx, r14
0x18004d50e  jz      short loc_18004D52A
0x18004d510  test    byte ptr [rcx+1Ch], 2
0x18004d514  jz      short loc_18004D52A
0x18004d516  mov     rcx, [rcx+10h]
0x18004d51a  mov     edx, 2Fh ; '/'
0x18004d51f  mov     r9d, eax
0x18004d522  mov     r8, r15
0x18004d525  call    WPP_SF_d
0x18004d52a  call    cs:__imp_GetLastError
0x18004d531  nop     dword ptr [rax+rax+00h]
0x18004d536  mov     ebx, eax
0x18004d538  test    eax, eax
0x18004d53a  jle     short loc_18004D545
0x18004d53c  movzx   ebx, ax
0x18004d53f  or      ebx, 80070000h
0x18004d545  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d54c  cmp     rcx, r14
0x18004d54f  jz      loc_18004D623
0x18004d555  test    byte ptr [rcx+1Ch], 40h
0x18004d559  jz      loc_18004D623
0x18004d55f  mov     edx, 30h ; '0'
0x18004d564  mov     r9d, ebx
0x18004d567  jmp     loc_18004D446
0x18004d56c  lea     r8, [rsp+48h+var_28]
0x18004d571  mov     edx, 1
0x18004d576  mov     rcx, rbx
0x18004d579  call    cs:__imp_FveOpenVolumeW
0x18004d580  nop     dword ptr [rax+rax+00h]
0x18004d585  mov     ebx, eax
0x18004d587  test    eax, eax
0x18004d589  jns     short loc_18004D5A4
0x18004d58b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d592  cmp     rcx, r14
0x18004d595  jz      short loc_18004D610
0x18004d597  test    byte ptr [rcx+1Ch], 2
0x18004d59b  jz      short loc_18004D610
0x18004d59d  mov     edx, 31h ; '1'
0x18004d5a2  jmp     short loc_18004D601
0x18004d5a4  mov     rcx, [rsp+48h+var_28]
0x18004d5a9  mov     edx, esi
0x18004d5ab  test    ebp, ebp
0x18004d5ad  jnz     short loc_18004D5D8
0x18004d5af  call    cs:__imp_FveConversionEncryptEx
0x18004d5b6  nop     dword ptr [rax+rax+00h]
0x18004d5bb  mov     ebx, eax
0x18004d5bd  test    eax, eax
0x18004d5bf  jns     short loc_18004D610
0x18004d5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5c8  cmp     rcx, r14
0x18004d5cb  jz      short loc_18004D610
0x18004d5cd  test    byte ptr [rcx+1Ch], 2
0x18004d5d1  jz      short loc_18004D610
0x18004d5d3  lea     edx, [rbp+32h]
0x18004d5d6  jmp     short loc_18004D601
0x18004d5d8  call    cs:__imp_FveConversionEncryptPendingRebootEx
0x18004d5df  nop     dword ptr [rax+rax+00h]
0x18004d5e4  mov     ebx, eax
0x18004d5e6  test    eax, eax
0x18004d5e8  jns     short loc_18004D610
0x18004d5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5f1  cmp     rcx, r14
0x18004d5f4  jz      short loc_18004D610
0x18004d5f6  test    byte ptr [rcx+1Ch], 2
0x18004d5fa  jz      short loc_18004D610
0x18004d5fc  mov     edx, 33h ; '3'
0x18004d601  mov     rcx, [rcx+10h]
0x18004d605  mov     r9d, eax
0x18004d608  mov     r8, r15
0x18004d60b  call    WPP_SF_d
0x18004d610  call    cs:__imp_RpcRevertToSelf
0x18004d617  nop     dword ptr [rax+rax+00h]
0x18004d61c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d623  cmp     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x18004d629  jz      short loc_18004D64C
0x18004d62b  mov     rcx, [rsp+48h+var_28]
0x18004d630  call    cs:__imp_FveCloseVolume
0x18004d637  nop     dword ptr [rax+rax+00h]
0x18004d63c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d643  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x18004d64c  cmp     rcx, r14
0x18004d64f  jz      short loc_18004D668
0x18004d651  test    byte ptr [rcx+1Ch], 20h
0x18004d655  jz      short loc_18004D668
0x18004d657  mov     rcx, [rcx+10h]
0x18004d65b  mov     edx, 34h ; '4'
0x18004d660  mov     r8, r15
0x18004d663  call    WPP_SF_
0x18004d668  mov     eax, ebx
0x18004d66a  mov     rcx, [rsp+48h+var_20]
0x18004d66f  xor     rcx, rsp; StackCookie
0x18004d672  call    __security_check_cookie
0x18004d677  mov     rbx, [rsp+48h+arg_0]
0x18004d67c  mov     rbp, [rsp+48h+arg_10]
0x18004d681  add     rsp, 30h
0x18004d685  pop     r15
0x18004d687  pop     r14
0x18004d689  pop     rsi
0x18004d68a  retn
```
