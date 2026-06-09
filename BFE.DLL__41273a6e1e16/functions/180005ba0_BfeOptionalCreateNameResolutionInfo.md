# BfeOptionalCreateNameResolutionInfo

- ea: `0x180005ba0`
- end: `0x180005f68`
- name: `BfeOptionalCreateNameResolutionInfo`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006ed0`

## callees

- `0x180005ba0`
- `0x180005f70`
- `0x1800087f0`
- `0x18000fb34`
- `0x180011510`
- `0x180013480`
- `0x1800135ac`
- `0x180036abc`
- `0x18004b49c`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180005f37`
- `ntdll!RtlEqualSid` at `0x180005f37`
- `ntdll!RtlInsertEntryHashTable` at `0x180005e34`
- `ntdll!RtlInsertEntryHashTable` at `0x180005e34`
- `ntdll!RtlLookupEntryHashTable` at `0x180005ccc`
- `ntdll!RtlLookupEntryHashTable` at `0x180005ccc`
- `ntdll!RtlGetNextEntryHashTable` at `0x180005f57`
- `ntdll!RtlGetNextEntryHashTable` at `0x180005f57`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005c6e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005c6e`

## string_xrefs

- `0x180005d5c`: `BfeOptionalCreateNameResolutionInfo`
- `0x180005ebb`: `RtlCreateHashTable`

## pseudocode

```c
__int64 __fastcall BfeOptionalCreateNameResolutionInfo(_QWORD *a1)
{
  _QWORD *v1; // rdx
  int v2; // r8d
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 inserted; // rbx
  __int64 v8; // rax
  unsigned __int8 *v9; // rbx
  __int64 v10; // rbp
  DWORD LengthSid; // r8d
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 i; // rax
  __int64 v17; // rdi
  int v18; // r8d
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  _QWORD *v22; // rdx
  __int64 v23; // rax
  int v24; // [rsp+30h] [rbp-58h] BYREF
  __int128 v25; // [rsp+38h] [rbp-50h] BYREF
  const char *v26; // [rsp+48h] [rbp-40h]
  __int64 v27; // [rsp+50h] [rbp-38h]
  int *v28; // [rsp+58h] [rbp-30h]
  __int64 v29; // [rsp+60h] [rbp-28h]

  v1 = (_QWORD *)*a1;
  v2 = 0;
  v4 = *(_QWORD *)(*a1 + 64LL) - *(_QWORD *)&FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data1;
  if ( !v4 )
    v4 = v1[9] - *(_QWORD *)FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data4;
  if ( !v4 )
    v2 = 1;
  v5 = v1[8] - *(_QWORD *)&FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data1;
  if ( !v5 )
    v5 = v1[9] - *(_QWORD *)FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data4;
  if ( !v5 || (inserted = 0, v2) )
  {
    v8 = v1[15];
    v25 = 0;
    v9 = *(unsigned __int8 **)(v8 + 32);
    v26 = 0;
    v10 = -1;
    LengthSid = GetLengthSid(v9);
    if ( !v9 )
      goto LABEL_14;
    v12 = 0;
    v13 = 0;
    if ( !LengthSid )
      goto LABEL_14;
    do
    {
      v14 = v9[v13];
      v13 = (unsigned int)(v13 + 1);
      v15 = 37 * v12 + v14;
      v12 = v15;
    }
    while ( (unsigned int)v13 < LengthSid );
    if ( !v15 )
LABEL_14:
      v12 = -1;
    for ( i = RtlLookupEntryHashTable(qword_1800F5EB8, v12, &v25); ; i = RtlGetNextEntryHashTable(qword_1800F5EB8, &v25) )
    {
      v17 = i;
      if ( !i )
      {
        inserted = BfeCreateAndInsertSidEntry(v9);
        if ( !inserted )
          goto LABEL_30;
LABEL_21:
        v19 = WPP_GLOBAL_Control;
        goto LABEL_22;
      }
      if ( RtlEqualSid(*(PSID *)(i + 24), v9) )
        break;
    }
    v21 = *(_QWORD *)(v17 + 32);
    v22 = (_QWORD *)(v17 + 32);
    if ( *(_QWORD *)(v21 + 8) != v17 + 32 )
      __fastfail(3u);
    a1[5] = v21;
    a1[6] = v22;
    *(_QWORD *)(v21 + 8) = a1 + 5;
    *v22 = a1 + 5;
    ++*(_DWORD *)(v17 + 48);
LABEL_30:
    a1[10] = BfeComputeNameHashSignature(*a1);
    if ( a1[10] )
      v10 = a1[10];
    else
      a1[10] = -1;
    if ( (unsigned __int8)RtlInsertEntryHashTable(qword_1800F5EE8, a1 + 8, v10, 0)
      || (v23 = WfpReportSysErrorAsNtStatus(v20, "RtlCreateHashTable", 3221225495LL), (inserted = v23) == 0) )
    {
      *((_DWORD *)a1 + 22) = 1;
      WfpRestructureHashtable(qword_1800F5EE8);
      a1[14] = BfeComputeAddressHashSignature(*a1);
      inserted = WfpHashtableInsert(qword_1800F5F18, a1 + 12);
      if ( !inserted )
      {
        *((_DWORD *)a1 + 30) = 1;
        WfpRestructureHashtable(qword_1800F5F18);
        return inserted;
      }
      goto LABEL_21;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, 0, (__int64)"WfpHashtableInsert", v23);
      v19 = WPP_GLOBAL_Control;
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v24 = inserted;
      v28 = &v24;
      v26 = "WfpHashtableInsert";
      v27 = 19;
      v29 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v18,
        3,
        (__int64)&v25);
      goto LABEL_21;
    }
LABEL_22:
    if ( v19 != &WPP_GLOBAL_Control && *((_BYTE *)v19 + 25) >= 2u && (*((_BYTE *)v19 + 28) & 1) != 0 )
      WPP_SF_Ssd(v19[2], 26, v18, 0, (__int64)"BfeOptionalCreateNameResolutionInfo", inserted);
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v24 = inserted;
      v28 = &v24;
      v26 = "BfeOptionalCreateNameResolutionInfo";
      v27 = 36;
      v29 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v18,
        3,
        (__int64)&v25);
    }
  }
  return inserted;
}

```

## disassembly

```asm
0x180005ba0  push    rsi
0x180005ba2  sub     rsp, 80h
0x180005ba9  mov     rax, cs:__security_cookie
0x180005bb0  xor     rax, rsp
0x180005bb3  mov     [rsp+88h+var_20], rax
0x180005bb8  mov     rdx, [rcx]
0x180005bbb  xor     r8d, r8d
0x180005bbe  mov     rsi, rcx
0x180005bc1  mov     rax, [rdx+40h]
0x180005bc5  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data1
0x180005bcc  jnz     short loc_180005BD9
0x180005bce  mov     rax, [rdx+48h]
0x180005bd2  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data4
0x180005bd9  test    rax, rax
0x180005bdc  jz      loc_180005F25
0x180005be2  mov     rax, [rdx+40h]
0x180005be6  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data1
0x180005bed  jnz     short loc_180005BFA
0x180005bef  mov     rax, [rdx+48h]
0x180005bf3  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data4
0x180005bfa  mov     [rsp+88h+arg_8], rbx
0x180005c02  mov     [rsp+88h+arg_10], rbp
0x180005c0a  mov     [rsp+88h+var_10], rdi
0x180005c0f  mov     [rsp+88h+var_18], r14
0x180005c14  test    rax, rax
0x180005c17  jz      short loc_180005C54
0x180005c19  xor     ebx, ebx
0x180005c1b  test    r8d, r8d
0x180005c1e  jnz     short loc_180005C54
0x180005c20  mov     r14, [rsp+88h+var_18]
0x180005c25  mov     rax, rbx
0x180005c28  mov     rbx, [rsp+88h+arg_8]
0x180005c30  mov     rdi, [rsp+88h+var_10]
0x180005c35  mov     rbp, [rsp+88h+arg_10]
0x180005c3d  mov     rcx, [rsp+88h+var_20]
0x180005c42  xor     rcx, rsp; StackCookie
0x180005c45  call    __security_check_cookie
0x180005c4a  add     rsp, 80h
0x180005c51  pop     rsi
0x180005c52  retn
0x180005c54  mov     rax, [rdx+78h]
0x180005c58  xorps   xmm0, xmm0
0x180005c5b  movups  [rsp+88h+var_50], xmm0
0x180005c60  mov     rbx, [rax+20h]
0x180005c64  xor     eax, eax
0x180005c66  mov     rcx, rbx; pSid
0x180005c69  mov     [rsp+88h+var_40], rax
0x180005c6e  call    cs:__imp_GetLengthSid
0x180005c75  nop     dword ptr [rax+rax+00h]
0x180005c7a  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180005c81  mov     r8d, eax
0x180005c84  test    rbx, rbx
0x180005c87  jz      short loc_180005CBA
0x180005c89  xor     r9d, r9d
0x180005c8c  xor     eax, eax
0x180005c8e  test    r8d, r8d
0x180005c91  jz      short loc_180005CBA
0x180005c93  nop     dword ptr [rax+00h]
0x180005c97  nop     word ptr [rax+rax+00000000h]
0x180005ca0  movzx   edx, byte ptr [rax+rbx]
0x180005ca4  inc     eax
0x180005ca6  imul    rcx, r9, 25h ; '%'
0x180005caa  add     rdx, rcx
0x180005cad  mov     r9, rdx
0x180005cb0  cmp     eax, r8d
0x180005cb3  jb      short loc_180005CA0
0x180005cb5  test    rdx, rdx
0x180005cb8  jnz     short loc_180005CBD
0x180005cba  mov     r9, rbp
0x180005cbd  lea     r8, [rsp+88h+var_50]
0x180005cc2  mov     rdx, r9
0x180005cc5  lea     rcx, qword_1800F5EB8
0x180005ccc  call    cs:__imp_RtlLookupEntryHashTable
0x180005cd3  nop     dword ptr [rax+rax+00h]
0x180005cd8  lea     r14, WPP_GLOBAL_Control
0x180005cdf  mov     rdi, rax
0x180005ce2  test    rax, rax
0x180005ce5  jnz     loc_180005F30
0x180005ceb  mov     rdx, rsi
0x180005cee  mov     rcx, rbx; pSourceSid
0x180005cf1  call    BfeCreateAndInsertSidEntry
0x180005cf6  mov     rbx, rax
0x180005cf9  test    rax, rax
0x180005cfc  jz      loc_180005E0A
0x180005d02  jmp     short loc_180005D55
0x180005d04  test    cs:byte_1800F6115, 1
0x180005d0b  jz      short loc_180005D5C
0x180005d0d  lea     rax, [rsp+88h+var_58]
0x180005d12  mov     [rsp+88h+var_58], ebx
0x180005d16  mov     [rsp+88h+var_30], rax
0x180005d1b  lea     rdx, WFP_USERMODE_ERROR
0x180005d22  lea     rax, [rsp+88h+var_50]
0x180005d27  mov     [rsp+88h+var_40], rdi
0x180005d2c  mov     r9d, 3
0x180005d32  mov     [rsp+88h+var_68], rax
0x180005d37  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180005d3e  mov     [rsp+88h+var_38], 13h
0x180005d47  mov     [rsp+88h+var_28], 4
0x180005d50  call    McGenEventWrite_EtwEventWriteTransfer
0x180005d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d5c  lea     rdi, aBfeoptionalcre; "BfeOptionalCreateNameResolutionInfo"
0x180005d63  cmp     rcx, r14
0x180005d66  jz      short loc_180005D8E
0x180005d68  cmp     byte ptr [rcx+19h], 2
0x180005d6c  jb      short loc_180005D8E
0x180005d6e  test    byte ptr [rcx+1Ch], 1
0x180005d72  jz      short loc_180005D8E
0x180005d74  mov     rcx, [rcx+10h]
0x180005d78  mov     edx, 1Ah
0x180005d7d  mov     [rsp+88h+var_60], ebx
0x180005d81  xor     r9d, r9d
0x180005d84  mov     [rsp+88h+var_68], rdi
0x180005d89  call    WPP_SF_Ssd
0x180005d8e  cmp     cs:gWfpLogUserModeErrors, 0
0x180005d95  jz      loc_180005C20
0x180005d9b  test    cs:byte_1800F6115, 1
0x180005da2  jz      loc_180005C20
0x180005da8  lea     rax, [rsp+88h+var_58]
0x180005dad  mov     [rsp+88h+var_58], ebx
0x180005db1  mov     [rsp+88h+var_30], rax
0x180005db6  lea     rdx, WFP_USERMODE_ERROR
0x180005dbd  lea     rax, [rsp+88h+var_50]
0x180005dc2  mov     [rsp+88h+var_40], rdi
0x180005dc7  mov     r9d, 3
0x180005dcd  mov     [rsp+88h+var_68], rax
0x180005dd2  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180005dd9  mov     [rsp+88h+var_38], 24h ; '$'
0x180005de2  mov     [rsp+88h+var_28], 4
0x180005deb  call    McGenEventWrite_EtwEventWriteTransfer
0x180005df0  jmp     loc_180005C20
0x180005df5  lea     rax, [rsi+28h]
0x180005df9  mov     [rax], r8
0x180005dfc  mov     [rax+8], rdx
0x180005e00  mov     [r8+8], rax
0x180005e04  mov     [rdx], rax
0x180005e07  inc     dword ptr [rdi+30h]
0x180005e0a  mov     rcx, [rsi]
0x180005e0d  call    BfeComputeNameHashSignature
0x180005e12  lea     rdx, [rsi+40h]
0x180005e16  mov     [rsi+50h], rax
0x180005e1a  mov     rax, [rdx+10h]
0x180005e1e  test    rax, rax
0x180005e21  jnz     short loc_180005E97
0x180005e23  mov     [rdx+10h], rbp
0x180005e27  xor     r9d, r9d
0x180005e2a  lea     rcx, qword_1800F5EE8
0x180005e31  mov     r8, rbp
0x180005e34  call    cs:__imp_RtlInsertEntryHashTable
0x180005e3b  nop     dword ptr [rax+rax+00h]
0x180005e40  test    al, al
0x180005e42  jz      short loc_180005EB5
0x180005e44  lea     rcx, qword_1800F5EE8
0x180005e4b  mov     dword ptr [rsi+58h], 1
0x180005e52  call    WfpRestructureHashtable
0x180005e57  mov     rcx, [rsi]
0x180005e5a  call    BfeComputeAddressHashSignature
0x180005e5f  lea     rdx, [rsi+60h]
0x180005e63  mov     [rsi+70h], rax
0x180005e67  lea     rcx, qword_1800F5F18
0x180005e6e  call    WfpHashtableInsert
0x180005e73  mov     rbx, rax
0x180005e76  test    rax, rax
0x180005e79  jnz     loc_180005D55
0x180005e7f  lea     rcx, qword_1800F5F18
0x180005e86  mov     dword ptr [rsi+78h], 1
0x180005e8d  call    WfpRestructureHashtable
0x180005e92  jmp     loc_180005C20
0x180005e97  mov     rbp, rax
0x180005e9a  jmp     short loc_180005E27
0x180005e9c  mov     r8, [rdi+20h]
0x180005ea0  lea     rdx, [rdi+20h]
0x180005ea4  cmp     [r8+8], rdx
0x180005ea8  jz      loc_180005DF5
0x180005eae  mov     ecx, 3
0x180005eb3  int     29h; Win8: RtlFailFast(ecx)
0x180005eb5  mov     r8d, 0C0000017h
0x180005ebb  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x180005ec2  call    WfpReportSysErrorAsNtStatus
0x180005ec7  mov     rbx, rax
0x180005eca  test    rax, rax
0x180005ecd  jz      loc_180005E44
0x180005ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eda  lea     rdi, aWfphashtablein; "WfpHashtableInsert"
0x180005ee1  cmp     rcx, r14
0x180005ee4  jz      short loc_180005F13
0x180005ee6  cmp     byte ptr [rcx+19h], 2
0x180005eea  jb      short loc_180005F13
0x180005eec  test    byte ptr [rcx+1Ch], 1
0x180005ef0  jz      short loc_180005F13
0x180005ef2  mov     rcx, [rcx+10h]
0x180005ef6  mov     edx, 1Ah
0x180005efb  mov     [rsp+88h+var_60], ebx
0x180005eff  xor     r9d, r9d
0x180005f02  mov     [rsp+88h+var_68], rdi
0x180005f07  call    WPP_SF_Ssd
0x180005f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f13  cmp     cs:gWfpLogUserModeErrors, 0
0x180005f1a  jz      loc_180005D5C
0x180005f20  jmp     loc_180005D04
0x180005f25  mov     r8d, 1
0x180005f2b  jmp     loc_180005BE2
0x180005f30  mov     rcx, [rdi+18h]; Sid1
0x180005f34  mov     rdx, rbx; Sid2
0x180005f37  call    cs:__imp_RtlEqualSid
0x180005f3e  nop     dword ptr [rax+rax+00h]
0x180005f43  test    al, al
0x180005f45  jnz     loc_180005E9C
0x180005f4b  lea     rdx, [rsp+88h+var_50]
0x180005f50  lea     rcx, qword_1800F5EB8
0x180005f57  call    cs:__imp_RtlGetNextEntryHashTable
0x180005f5e  nop     dword ptr [rax+rax+00h]
0x180005f63  jmp     loc_180005CD8
```
