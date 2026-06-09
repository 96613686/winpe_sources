# FWStatusMessageFromStatusCode

- ea: `0x180018340`
- end: `0x180018570`
- name: `FWStatusMessageFromStatusCode`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180005954`
- `0x180018340`
- `0x180018578`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001837c`
- `ntdll!EtwEventWrite` at `0x18001842b`
- `ntdll!EtwEventWrite` at `0x18001837c`
- `ntdll!EtwEventWrite` at `0x18001842b`
- `fwbase!FwBaseFree` at `0x18001840c`
- `fwbase!FwBaseFree` at `0x18001840c`
- `fwbase!FwGetStringIdForStatusCode` at `0x1800183ab`
- `fwbase!FwGetStringIdForStatusCode` at `0x1800183ab`
- `fwbase!FwLoadString` at `0x1800183c1`
- `fwbase!FwLoadString` at `0x1800183c1`
- `fwbase!FwHResultToWindowsError` at `0x1800183c9`
- `fwbase!FwHResultToWindowsError` at `0x180018489`
- `fwbase!FwHResultToWindowsError` at `0x1800183c9`
- `fwbase!FwHResultToWindowsError` at `0x180018489`

## pseudocode

```c
__int64 __fastcall FWStatusMessageFromStatusCode(unsigned int a1, unsigned __int16 *a2, _DWORD *a3)
{
  FwPolicy2 *v6; // rax
  unsigned __int16 *v7; // rcx
  unsigned int StringIdForStatusCode; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rax
  unsigned int v14; // eax
  FwPolicy2 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rcx
  unsigned __int16 *v19; // [rsp+20h] [rbp-28h] BYREF

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_StatusMessageFromStatusCode, 0, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  v19 = 0;
  if ( !a3 )
  {
    v11 = 87;
    if ( v6 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 )
      goto LABEL_13;
    v18 = *((_QWORD *)v6 + 2);
    v16 = 11;
    v17 = 87;
    goto LABEL_24;
  }
  StringIdForStatusCode = FwGetStringIdForStatusCode(a1);
  if ( StringIdForStatusCode == -1 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, a1);
      v15 = WPP_GLOBAL_Control;
    }
    v11 = 2;
    if ( v15 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 1) == 0 )
      goto LABEL_8;
    v16 = 13;
    v17 = 2;
    goto LABEL_23;
  }
  v9 = FwLoadString(StringIdForStatusCode, &v19);
  v10 = FwHResultToWindowsError(v9);
  v11 = v10;
  if ( v10 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 14;
      goto LABEL_22;
    }
  }
  else if ( a2 )
  {
    v14 = StringCchCopyW(a2, (unsigned int)*a3, v19);
    v10 = FwHResultToWindowsError(v14);
    v11 = v10;
    if ( v10 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 15;
LABEL_22:
        v17 = v10;
LABEL_23:
        v18 = *((_QWORD *)v15 + 2);
LABEL_24:
        WPP_SF_d(v18, v16, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v17);
      }
    }
  }
LABEL_8:
  v7 = v19;
  if ( v19 && a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v19[v12] );
    *a3 = v12;
  }
LABEL_13:
  FwBaseFree(v7);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_StatusMessageFromStatusCode, 0, 0);
  return v11;
}

```

## disassembly

```asm
0x180018340  mov     [rsp+arg_18], rbx
0x180018345  push    rbp
0x180018346  push    rsi
0x180018347  push    rdi
0x180018348  sub     rsp, 30h
0x18001834c  mov     rax, cs:__security_cookie
0x180018353  xor     rax, rsp
0x180018356  mov     [rsp+48h+var_20], rax
0x18001835b  mov     esi, ecx
0x18001835d  mov     rbx, r8
0x180018360  mov     rcx, cs:g_Provider
0x180018367  mov     rdi, rdx
0x18001836a  test    rcx, rcx
0x18001836d  jz      short loc_180018382
0x18001836f  xor     r9d, r9d
0x180018372  lea     rdx, MPS_CLNT_API_Enter_StatusMessageFromStatusCode
0x180018379  xor     r8d, r8d
0x18001837c  call    cs:__imp_EtwEventWrite
0x180018382  mov     rax, cs:WPP_GLOBAL_Control
0x180018389  lea     rbp, WPP_GLOBAL_Control
0x180018390  cmp     rax, rbp
0x180018393  jnz     loc_18001844D
0x180018399  xor     ecx, ecx
0x18001839b  mov     [rsp+48h+var_28], rcx
0x1800183a0  test    rbx, rbx
0x1800183a3  jz      loc_1800184D0
0x1800183a9  mov     ecx, esi
0x1800183ab  call    cs:__imp_FwGetStringIdForStatusCode
0x1800183b1  cmp     eax, 0FFFFFFFFh
0x1800183b4  jz      loc_1800184F6
0x1800183ba  lea     rdx, [rsp+48h+var_28]
0x1800183bf  mov     ecx, eax
0x1800183c1  call    cs:__imp_FwLoadString
0x1800183c7  mov     ecx, eax
0x1800183c9  call    cs:__imp_FwHResultToWindowsError
0x1800183cf  mov     esi, eax
0x1800183d1  test    eax, eax
0x1800183d3  jnz     loc_18001854C
0x1800183d9  test    rdi, rdi
0x1800183dc  jnz     loc_180018478
0x1800183e2  mov     rcx, [rsp+48h+var_28]
0x1800183e7  test    rcx, rcx
0x1800183ea  jz      short loc_18001840C
0x1800183ec  test    rbx, rbx
0x1800183ef  jz      short loc_18001840C
0x1800183f1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800183f8  nop     dword ptr [rax+rax+00000000h]
0x180018400  inc     rax
0x180018403  cmp     word ptr [rcx+rax*2], 0
0x180018408  jnz     short loc_180018400
0x18001840a  mov     [rbx], eax
0x18001840c  call    cs:__imp_FwBaseFree
0x180018412  mov     rcx, cs:g_Provider
0x180018419  test    rcx, rcx
0x18001841c  jz      short loc_180018431
0x18001841e  xor     r9d, r9d
0x180018421  lea     rdx, MPS_CLNT_API_Exit_StatusMessageFromStatusCode
0x180018428  xor     r8d, r8d
0x18001842b  call    cs:__imp_EtwEventWrite
0x180018431  mov     eax, esi
0x180018433  mov     rcx, [rsp+48h+var_20]
0x180018438  xor     rcx, rsp; StackCookie
0x18001843b  call    __security_check_cookie
0x180018440  mov     rbx, [rsp+48h+arg_18]
0x180018445  add     rsp, 30h
0x180018449  pop     rdi
0x18001844a  pop     rsi
0x18001844b  pop     rbp
0x18001844c  retn
0x18001844d  test    byte ptr [rax+1Ch], 8
0x180018451  jz      loc_180018399
0x180018457  mov     rcx, [rax+10h]
0x18001845b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180018462  mov     edx, 0Ah
0x180018467  call    WPP_SF_
0x18001846c  mov     rax, cs:WPP_GLOBAL_Control
0x180018473  jmp     loc_180018399
0x180018478  mov     edx, [rbx]; unsigned __int64
0x18001847a  mov     rcx, rdi; unsigned __int16 *
0x18001847d  mov     r8, [rsp+48h+var_28]; unsigned __int16 *
0x180018482  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018487  mov     ecx, eax
0x180018489  call    cs:__imp_FwHResultToWindowsError
0x18001848f  mov     esi, eax
0x180018491  test    eax, eax
0x180018493  jz      loc_1800183E2
0x180018499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184a0  cmp     rcx, rbp
0x1800184a3  jz      loc_1800183E2
0x1800184a9  test    byte ptr [rcx+1Ch], 1
0x1800184ad  jz      loc_1800183E2
0x1800184b3  mov     edx, 0Fh
0x1800184b8  mov     r9d, eax
0x1800184bb  mov     rcx, [rcx+10h]
0x1800184bf  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800184c6  call    WPP_SF_d
0x1800184cb  jmp     loc_1800183E2
0x1800184d0  mov     esi, 57h ; 'W'
0x1800184d5  cmp     rax, rbp
0x1800184d8  jz      loc_18001840C
0x1800184de  test    byte ptr [rax+1Ch], 1
0x1800184e2  jz      loc_18001840C
0x1800184e8  mov     rcx, [rax+10h]
0x1800184ec  mov     edx, 0Bh
0x1800184f1  mov     r9d, esi
0x1800184f4  jmp     short loc_1800184BF
0x1800184f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184fd  cmp     rcx, rbp
0x180018500  jz      short loc_180018527
0x180018502  test    byte ptr [rcx+1Ch], 1
0x180018506  jz      short loc_180018527
0x180018508  mov     rcx, [rcx+10h]
0x18001850c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180018513  mov     edx, 0Ch
0x180018518  mov     r9d, esi
0x18001851b  call    WPP_SF_d
0x180018520  mov     rcx, cs:WPP_GLOBAL_Control
0x180018527  mov     esi, 2
0x18001852c  cmp     rcx, rbp
0x18001852f  jz      loc_1800183E2
0x180018535  test    byte ptr [rcx+1Ch], 1
0x180018539  jz      loc_1800183E2
0x18001853f  mov     edx, 0Dh
0x180018544  mov     r9d, esi
0x180018547  jmp     loc_1800184BB
0x18001854c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018553  cmp     rcx, rbp
0x180018556  jz      loc_1800183E2
0x18001855c  test    byte ptr [rcx+1Ch], 1
0x180018560  jz      loc_1800183E2
0x180018566  mov     edx, 0Eh
0x18001856b  jmp     loc_1800184B8
```
