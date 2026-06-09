# FWStatusMessageFromStatusCode

- ea: `0x180018390`
- end: `0x1800185e3`
- name: `FWStatusMessageFromStatusCode`
- size: `595`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180005e0c`
- `0x180018390`
- `0x1800185ec`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800183cc`
- `ntdll!EtwEventWrite` at `0x180018491`
- `ntdll!EtwEventWrite` at `0x1800183cc`
- `ntdll!EtwEventWrite` at `0x180018491`
- `fwbase!FwBaseFree` at `0x18001846c`
- `fwbase!FwBaseFree` at `0x18001846c`
- `fwbase!FwGetStringIdForStatusCode` at `0x180018401`
- `fwbase!FwGetStringIdForStatusCode` at `0x180018401`
- `fwbase!FwLoadString` at `0x18001841d`
- `fwbase!FwLoadString` at `0x18001841d`
- `fwbase!FwHResultToWindowsError` at `0x18001842b`
- `fwbase!FwHResultToWindowsError` at `0x1800184f6`
- `fwbase!FwHResultToWindowsError` at `0x18001842b`
- `fwbase!FwHResultToWindowsError` at `0x1800184f6`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, a1);
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
        WPP_SF_d(v18, v16, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v17);
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
0x180018390  mov     [rsp+arg_18], rbx
0x180018395  push    rbp
0x180018396  push    rsi
0x180018397  push    rdi
0x180018398  sub     rsp, 30h
0x18001839c  mov     rax, cs:__security_cookie
0x1800183a3  xor     rax, rsp
0x1800183a6  mov     [rsp+48h+var_20], rax
0x1800183ab  mov     esi, ecx
0x1800183ad  mov     rbx, r8
0x1800183b0  mov     rcx, cs:g_Provider
0x1800183b7  mov     rdi, rdx
0x1800183ba  test    rcx, rcx
0x1800183bd  jz      short loc_1800183D8
0x1800183bf  xor     r9d, r9d
0x1800183c2  lea     rdx, MPS_CLNT_API_Enter_StatusMessageFromStatusCode
0x1800183c9  xor     r8d, r8d
0x1800183cc  call    cs:__imp_EtwEventWrite
0x1800183d3  nop     dword ptr [rax+rax+00h]
0x1800183d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800183df  lea     rbp, WPP_GLOBAL_Control
0x1800183e6  cmp     rax, rbp
0x1800183e9  jnz     loc_1800184BA
0x1800183ef  xor     ecx, ecx
0x1800183f1  mov     [rsp+48h+var_28], rcx
0x1800183f6  test    rbx, rbx
0x1800183f9  jz      loc_180018543
0x1800183ff  mov     ecx, esi
0x180018401  call    cs:__imp_FwGetStringIdForStatusCode
0x180018408  nop     dword ptr [rax+rax+00h]
0x18001840d  cmp     eax, 0FFFFFFFFh
0x180018410  jz      loc_180018569
0x180018416  lea     rdx, [rsp+48h+var_28]
0x18001841b  mov     ecx, eax
0x18001841d  call    cs:__imp_FwLoadString
0x180018424  nop     dword ptr [rax+rax+00h]
0x180018429  mov     ecx, eax
0x18001842b  call    cs:__imp_FwHResultToWindowsError
0x180018432  nop     dword ptr [rax+rax+00h]
0x180018437  mov     esi, eax
0x180018439  test    eax, eax
0x18001843b  jnz     loc_1800185BF
0x180018441  test    rdi, rdi
0x180018444  jnz     loc_1800184E5
0x18001844a  mov     rcx, [rsp+48h+var_28]
0x18001844f  test    rcx, rcx
0x180018452  jz      short loc_18001846C
0x180018454  test    rbx, rbx
0x180018457  jz      short loc_18001846C
0x180018459  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180018460  inc     rax
0x180018463  cmp     word ptr [rcx+rax*2], 0
0x180018468  jnz     short loc_180018460
0x18001846a  mov     [rbx], eax
0x18001846c  call    cs:__imp_FwBaseFree
0x180018473  nop     dword ptr [rax+rax+00h]
0x180018478  mov     rcx, cs:g_Provider
0x18001847f  test    rcx, rcx
0x180018482  jz      short loc_18001849D
0x180018484  xor     r9d, r9d
0x180018487  lea     rdx, MPS_CLNT_API_Exit_StatusMessageFromStatusCode
0x18001848e  xor     r8d, r8d
0x180018491  call    cs:__imp_EtwEventWrite
0x180018498  nop     dword ptr [rax+rax+00h]
0x18001849d  mov     eax, esi
0x18001849f  mov     rcx, [rsp+48h+var_20]
0x1800184a4  xor     rcx, rsp; StackCookie
0x1800184a7  call    __security_check_cookie
0x1800184ac  mov     rbx, [rsp+48h+arg_18]
0x1800184b1  add     rsp, 30h
0x1800184b5  pop     rdi
0x1800184b6  pop     rsi
0x1800184b7  pop     rbp
0x1800184b8  retn
0x1800184ba  test    byte ptr [rax+1Ch], 8
0x1800184be  jz      loc_1800183EF
0x1800184c4  mov     rcx, [rax+10h]
0x1800184c8  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800184cf  mov     edx, 0Ah
0x1800184d4  call    WPP_SF_
0x1800184d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800184e0  jmp     loc_1800183EF
0x1800184e5  mov     edx, [rbx]; unsigned __int64
0x1800184e7  mov     rcx, rdi; unsigned __int16 *
0x1800184ea  mov     r8, [rsp+48h+var_28]; unsigned __int16 *
0x1800184ef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800184f4  mov     ecx, eax
0x1800184f6  call    cs:__imp_FwHResultToWindowsError
0x1800184fd  nop     dword ptr [rax+rax+00h]
0x180018502  mov     esi, eax
0x180018504  test    eax, eax
0x180018506  jz      loc_18001844A
0x18001850c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018513  cmp     rcx, rbp
0x180018516  jz      loc_18001844A
0x18001851c  test    byte ptr [rcx+1Ch], 1
0x180018520  jz      loc_18001844A
0x180018526  mov     edx, 0Fh
0x18001852b  mov     r9d, eax
0x18001852e  mov     rcx, [rcx+10h]
0x180018532  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180018539  call    WPP_SF_d
0x18001853e  jmp     loc_18001844A
0x180018543  mov     esi, 57h ; 'W'
0x180018548  cmp     rax, rbp
0x18001854b  jz      loc_18001846C
0x180018551  test    byte ptr [rax+1Ch], 1
0x180018555  jz      loc_18001846C
0x18001855b  mov     rcx, [rax+10h]
0x18001855f  mov     edx, 0Bh
0x180018564  mov     r9d, esi
0x180018567  jmp     short loc_180018532
0x180018569  mov     rcx, cs:WPP_GLOBAL_Control
0x180018570  cmp     rcx, rbp
0x180018573  jz      short loc_18001859A
0x180018575  test    byte ptr [rcx+1Ch], 1
0x180018579  jz      short loc_18001859A
0x18001857b  mov     rcx, [rcx+10h]
0x18001857f  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180018586  mov     edx, 0Ch
0x18001858b  mov     r9d, esi
0x18001858e  call    WPP_SF_d
0x180018593  mov     rcx, cs:WPP_GLOBAL_Control
0x18001859a  mov     esi, 2
0x18001859f  cmp     rcx, rbp
0x1800185a2  jz      loc_18001844A
0x1800185a8  test    byte ptr [rcx+1Ch], 1
0x1800185ac  jz      loc_18001844A
0x1800185b2  mov     edx, 0Dh
0x1800185b7  mov     r9d, esi
0x1800185ba  jmp     loc_18001852E
0x1800185bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185c6  cmp     rcx, rbp
0x1800185c9  jz      loc_18001844A
0x1800185cf  test    byte ptr [rcx+1Ch], 1
0x1800185d3  jz      loc_18001844A
0x1800185d9  mov     edx, 0Eh
0x1800185de  jmp     loc_18001852B
```
