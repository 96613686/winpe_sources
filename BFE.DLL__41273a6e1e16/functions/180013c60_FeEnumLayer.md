# FeEnumLayer

- ea: `0x180013c60`
- end: `0x180013f56`
- name: `FeEnumLayer`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180028c58`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x1800135ac`
- `0x180013c60`
- `0x180015674`
- `0x1800197d0`
- `0x18001d588`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013dce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013f24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013dce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013f24`

## string_xrefs

- `0x180013d01`: `GetLayerFromIdRead`
- `0x180013cb4`: `FeAcquireWriteEngineLock`
- `0x180013f30`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall FeEnumLayer(unsigned __int16 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rbx
  __int64 v7; // rcx
  __int64 matched; // rdi
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // r8
  unsigned int i; // ebx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v16; // r8
  int v17; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-70h] BYREF
  const char *v19; // [rsp+48h] [rbp-60h]
  __int64 v20; // [rsp+50h] [rbp-58h]
  int *v21; // [rsp+58h] [rbp-50h]
  __int64 v22; // [rsp+60h] [rbp-48h]

  v4 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
  if ( *((_DWORD *)gWfpGlobal + 28) != 2
    || (matched = WfpReportSysErrorAsNtStatus(v7, "FeAcquireWriteEngineLock", 3221225473LL)) == 0 )
  {
    if ( (unsigned __int16)v4 >= *((_WORD *)gWfpGlobal + 156) )
    {
      v9 = 0;
      v10 = WfpReportSysErrorAsNtStatus(gWfpGlobal, "GetLayerFromIdRead", 3221225485LL);
      matched = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, 0, (__int64)"GetLayerFromIdRead", v10);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
        {
          v17 = matched;
          v21 = &v17;
          v19 = "GetLayerFromIdRead";
          v20 = 19;
          v22 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            &MICROSOFT_WFP_PROVIDER_Context,
            (__int64)WFP_USERMODE_ERROR,
            v11,
            3,
            (__int64)v18);
          goto LABEL_16;
        }
      }
      if ( matched )
        goto LABEL_16;
    }
    else
    {
      v9 = *((_QWORD *)gWfpGlobal + 38) + 176 * v4;
      matched = 0;
    }
    for ( i = 0; i < *(_DWORD *)(v9 + 112); ++i )
    {
      v13 = *(_QWORD *)(v9 + 144) + 16LL * i;
      v14 = *(int *)(v13 + 8);
      if ( (_DWORD)v14 != 4 )
      {
        matched = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD *, _DWORD))gWfpGlobal + 7 * v14 + 18))(
                    *(_QWORD *)v13,
                    a2,
                    0,
                    a4,
                    0);
        if ( matched )
          break;
      }
    }
LABEL_16:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
    if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
    {
      if ( matched )
      {
LABEL_21:
        FreeMatchBufListInternal(*a4);
        goto LABEL_22;
      }
      matched = SortMatchList(*a4);
    }
    if ( !matched )
      return matched;
    goto LABEL_21;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
  WfpReportError(matched, "FeAcquireReadEngineLock");
  FreeMatchBufListInternal(*a4);
LABEL_22:
  *a4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v16, 0, (__int64)"FeEnumLayer", matched);
  }
  if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
  {
    v17 = matched;
    v21 = &v17;
    v19 = "FeEnumLayer";
    v20 = 12;
    v22 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      &MICROSOFT_WFP_PROVIDER_Context,
      (__int64)WFP_USERMODE_ERROR,
      v16,
      3,
      (__int64)v18);
  }
  return matched;
}

```

## disassembly

```asm
0x180013c60  push    rbx
0x180013c62  push    rbp
0x180013c63  push    rdi
0x180013c64  push    r12
0x180013c66  push    r14
0x180013c68  push    r15
0x180013c6a  sub     rsp, 78h
0x180013c6e  mov     rax, cs:__security_cookie
0x180013c75  xor     rax, rsp
0x180013c78  mov     [rsp+0A8h+var_40], rax
0x180013c7d  movzx   ebx, cx
0x180013c80  mov     r14, r9
0x180013c83  mov     rcx, cs:gWfpGlobal
0x180013c8a  mov     rbp, rdx
0x180013c8d  add     rcx, 8; lpCriticalSection
0x180013c91  call    cs:__imp_EnterCriticalSection
0x180013c98  nop     dword ptr [rax+rax+00h]
0x180013c9d  mov     rax, cs:gWfpGlobal
0x180013ca4  mov     r8d, [rax+70h]
0x180013ca8  cmp     r8d, 2
0x180013cac  jnz     short loc_180013CCC
0x180013cae  mov     r8d, 0C0000001h
0x180013cb4  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x180013cbb  call    WfpReportSysErrorAsNtStatus
0x180013cc0  mov     rdi, rax
0x180013cc3  test    rax, rax
0x180013cc6  jnz     loc_180013F19
0x180013ccc  mov     rcx, cs:gWfpGlobal
0x180013cd3  lea     r12, WPP_GLOBAL_Control
0x180013cda  mov     [rsp+0A8h+var_38], rsi
0x180013cdf  cmp     bx, [rcx+138h]
0x180013ce6  jnb     short loc_180013CFE
0x180013ce8  imul    rsi, rbx, 0B0h
0x180013cef  add     rsi, [rcx+130h]
0x180013cf6  xor     r15d, r15d
0x180013cf9  mov     edi, r15d
0x180013cfc  jmp     short loc_180013D65
0x180013cfe  xor     r15d, r15d
0x180013d01  lea     rbx, aGetlayerfromid_0; "GetLayerFromIdRead"
0x180013d08  mov     rdx, rbx
0x180013d0b  mov     r8d, 0C000000Dh
0x180013d11  mov     esi, r15d
0x180013d14  call    WfpReportSysErrorAsNtStatus
0x180013d19  mov     rdi, rax
0x180013d1c  test    rax, rax
0x180013d1f  jz      short loc_180013D60
0x180013d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d28  cmp     rcx, r12
0x180013d2b  jz      short loc_180013D53
0x180013d2d  cmp     byte ptr [rcx+19h], 2
0x180013d31  jb      short loc_180013D53
0x180013d33  test    byte ptr [rcx+1Ch], 1
0x180013d37  jz      short loc_180013D53
0x180013d39  mov     rcx, [rcx+10h]
0x180013d3d  mov     edx, 1Ah
0x180013d42  mov     [rsp+0A8h+var_80], edi
0x180013d46  xor     r9d, r9d
0x180013d49  mov     [rsp+0A8h+var_88], rbx
0x180013d4e  call    WPP_SF_Ssd
0x180013d53  cmp     cs:gWfpLogUserModeErrors, r15d
0x180013d5a  jnz     loc_180013EBF
0x180013d60  test    rdi, rdi
0x180013d63  jnz     short loc_180013DC3
0x180013d65  mov     eax, [rsi+70h]
0x180013d68  mov     ebx, r15d
0x180013d6b  test    eax, eax
0x180013d6d  jz      short loc_180013DC3
0x180013d6f  cmp     ebx, eax
0x180013d71  jnb     short loc_180013DBA
0x180013d73  mov     ecx, ebx
0x180013d75  shl     rcx, 4
0x180013d79  add     rcx, [rsi+90h]
0x180013d80  movsxd  rax, dword ptr [rcx+8]
0x180013d84  cmp     eax, 4
0x180013d87  jz      short loc_180013DBA
0x180013d89  mov     rcx, [rcx]
0x180013d8c  mov     r9, r14
0x180013d8f  imul    rdx, rax, 38h ; '8'
0x180013d93  mov     rax, cs:gWfpGlobal
0x180013d9a  xor     r8d, r8d
0x180013d9d  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180013da2  mov     rax, [rdx+rax+90h]
0x180013daa  mov     rdx, rbp
0x180013dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db2  mov     rdi, rax
0x180013db5  test    rax, rax
0x180013db8  jnz     short loc_180013DC3
0x180013dba  mov     eax, [rsi+70h]
0x180013dbd  inc     ebx
0x180013dbf  cmp     ebx, eax
0x180013dc1  jb      short loc_180013D73
0x180013dc3  mov     rcx, cs:gWfpGlobal
0x180013dca  add     rcx, 8; lpCriticalSection
0x180013dce  call    cs:__imp_LeaveCriticalSection
0x180013dd5  nop     dword ptr [rax+rax+00h]
0x180013dda  test    byte ptr [rbp+8], 2
0x180013dde  mov     rsi, [rsp+0A8h+var_38]
0x180013de3  jz      short loc_180013DF5
0x180013de5  test    rdi, rdi
0x180013de8  jnz     short loc_180013E19
0x180013dea  mov     rcx, [r14]
0x180013ded  call    SortMatchList
0x180013df2  mov     rdi, rax
0x180013df5  test    rdi, rdi
0x180013df8  jnz     short loc_180013E19
0x180013dfa  mov     rax, rdi
0x180013dfd  mov     rcx, [rsp+0A8h+var_40]
0x180013e02  xor     rcx, rsp; StackCookie
0x180013e05  call    __security_check_cookie
0x180013e0a  add     rsp, 78h
0x180013e0e  pop     r15
0x180013e10  pop     r14
0x180013e12  pop     r12
0x180013e14  pop     rdi
0x180013e15  pop     rbp
0x180013e16  pop     rbx
0x180013e17  retn
0x180013e19  mov     rcx, [r14]
0x180013e1c  call    FreeMatchBufListInternal
0x180013e21  mov     rax, r15
0x180013e24  mov     [r14], rax
0x180013e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e2e  lea     rbx, aFeenumlayer; "FeEnumLayer"
0x180013e35  cmp     rcx, r12
0x180013e38  jz      short loc_180013E60
0x180013e3a  cmp     byte ptr [rcx+19h], 2
0x180013e3e  jb      short loc_180013E60
0x180013e40  test    byte ptr [rcx+1Ch], 1
0x180013e44  jz      short loc_180013E60
0x180013e46  mov     rcx, [rcx+10h]
0x180013e4a  mov     edx, 1Ah
0x180013e4f  mov     [rsp+0A8h+var_80], edi
0x180013e53  xor     r9d, r9d
0x180013e56  mov     [rsp+0A8h+var_88], rbx
0x180013e5b  call    WPP_SF_Ssd
0x180013e60  cmp     cs:gWfpLogUserModeErrors, 0
0x180013e67  jz      short loc_180013DFA
0x180013e69  test    cs:byte_1800F6115, 1
0x180013e70  jz      short loc_180013DFA
0x180013e72  lea     rax, [rsp+0A8h+var_78]
0x180013e77  mov     [rsp+0A8h+var_78], edi
0x180013e7b  mov     [rsp+0A8h+var_50], rax
0x180013e80  lea     rdx, WFP_USERMODE_ERROR
0x180013e87  lea     rax, [rsp+0A8h+var_70]
0x180013e8c  mov     [rsp+0A8h+var_60], rbx
0x180013e91  mov     r9d, 3
0x180013e97  mov     [rsp+0A8h+var_88], rax
0x180013e9c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180013ea3  mov     [rsp+0A8h+var_58], 0Ch
0x180013eac  mov     [rsp+0A8h+var_48], 4
0x180013eb5  call    McGenEventWrite_EtwEventWriteTransfer
0x180013eba  jmp     loc_180013DFA
0x180013ebf  test    cs:byte_1800F6115, 1
0x180013ec6  jz      loc_180013D60
0x180013ecc  lea     rax, [rsp+0A8h+var_78]
0x180013ed1  mov     [rsp+0A8h+var_78], edi
0x180013ed5  mov     [rsp+0A8h+var_50], rax
0x180013eda  lea     rdx, WFP_USERMODE_ERROR
0x180013ee1  lea     rax, [rsp+0A8h+var_70]
0x180013ee6  mov     [rsp+0A8h+var_60], rbx
0x180013eeb  mov     r9d, 3
0x180013ef1  mov     [rsp+0A8h+var_88], rax
0x180013ef6  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180013efd  mov     [rsp+0A8h+var_58], 13h
0x180013f06  mov     [rsp+0A8h+var_48], 4
0x180013f0f  call    McGenEventWrite_EtwEventWriteTransfer
0x180013f14  jmp     loc_180013DC3
0x180013f19  mov     rcx, cs:gWfpGlobal
0x180013f20  add     rcx, 8; lpCriticalSection
0x180013f24  call    cs:__imp_LeaveCriticalSection
0x180013f2b  nop     dword ptr [rax+rax+00h]
0x180013f30  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x180013f37  mov     rcx, rdi
0x180013f3a  call    WfpReportError
0x180013f3f  mov     rcx, [r14]
0x180013f42  call    FreeMatchBufListInternal
0x180013f47  xor     r15d, r15d
0x180013f4a  lea     r12, WPP_GLOBAL_Control
0x180013f51  jmp     loc_180013E21
```
