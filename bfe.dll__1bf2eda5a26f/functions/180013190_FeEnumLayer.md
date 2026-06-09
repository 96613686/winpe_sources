# FeEnumLayer

- ea: `0x180013190`
- end: `0x180013473`
- name: `FeEnumLayer`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180027478`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x180012b54`
- `0x180013190`
- `0x180014b78`
- `0x180018b74`
- `0x18001c7f4`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013447`

## string_xrefs

- `0x18001322b`: `GetLayerFromIdRead`
- `0x1800131de`: `FeAcquireWriteEngineLock`
- `0x18001344d`: `FeAcquireReadEngineLock`

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
  EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
  if ( *(_DWORD *)(MEMORY[0x1800EF368][58] + 112LL) != 2
    || (matched = WfpReportSysErrorAsNtStatus(v7, "FeAcquireWriteEngineLock", 3221225473LL)) == 0 )
  {
    if ( (unsigned __int16)v4 >= *(_WORD *)(MEMORY[0x1800EF368][58] + 312LL) )
    {
      v9 = 0;
      v10 = WfpReportSysErrorAsNtStatus(MEMORY[0x1800EF368][58], "GetLayerFromIdRead", 3221225485LL);
      matched = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, 0, (__int64)"GetLayerFromIdRead", v10);
        }
        if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
      v9 = *(_QWORD *)(MEMORY[0x1800EF368][58] + 304LL) + 176 * v4;
      matched = 0;
    }
    for ( i = 0; i < *(_DWORD *)(v9 + 112); ++i )
    {
      v13 = *(_QWORD *)(v9 + 144) + 16LL * i;
      v14 = *(int *)(v13 + 8);
      if ( (_DWORD)v14 != 4 )
      {
        matched = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD *, _DWORD))(56 * v14
                                                                                       + MEMORY[0x1800EF368][58]
                                                                                       + 144))(
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
    LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
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
  LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
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
  if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
0x180013190  push    rbx
0x180013192  push    rbp
0x180013193  push    rdi
0x180013194  push    r12
0x180013196  push    r14
0x180013198  push    r15
0x18001319a  sub     rsp, 78h
0x18001319e  mov     rax, cs:__security_cookie
0x1800131a5  xor     rax, rsp
0x1800131a8  mov     [rsp+0A8h+var_40], rax
0x1800131ad  movzx   ebx, cx
0x1800131b0  mov     r14, r9
0x1800131b3  mov     rcx, cs:1800EF538h
0x1800131ba  mov     rbp, rdx
0x1800131bd  add     rcx, 8; lpCriticalSection
0x1800131c1  call    cs:__imp_EnterCriticalSection
0x1800131c7  mov     rax, cs:1800EF538h
0x1800131ce  mov     r8d, [rax+70h]
0x1800131d2  cmp     r8d, 2
0x1800131d6  jnz     short loc_1800131F6
0x1800131d8  mov     r8d, 0C0000001h
0x1800131de  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x1800131e5  call    WfpReportSysErrorAsNtStatus
0x1800131ea  mov     rdi, rax
0x1800131ed  test    rax, rax
0x1800131f0  jnz     loc_18001343C
0x1800131f6  mov     rcx, cs:1800EF538h
0x1800131fd  lea     r12, WPP_GLOBAL_Control
0x180013204  mov     [rsp+0A8h+var_38], rsi
0x180013209  cmp     bx, [rcx+138h]
0x180013210  jnb     short loc_180013228
0x180013212  imul    rsi, rbx, 0B0h
0x180013219  add     rsi, [rcx+130h]
0x180013220  xor     r15d, r15d
0x180013223  mov     edi, r15d
0x180013226  jmp     short loc_18001328F
0x180013228  xor     r15d, r15d
0x18001322b  lea     rbx, aGetlayerfromid_0; "GetLayerFromIdRead"
0x180013232  mov     rdx, rbx
0x180013235  mov     r8d, 0C000000Dh
0x18001323b  mov     esi, r15d
0x18001323e  call    WfpReportSysErrorAsNtStatus
0x180013243  mov     rdi, rax
0x180013246  test    rax, rax
0x180013249  jz      short loc_18001328A
0x18001324b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013252  cmp     rcx, r12
0x180013255  jz      short loc_18001327D
0x180013257  cmp     byte ptr [rcx+19h], 2
0x18001325b  jb      short loc_18001327D
0x18001325d  test    byte ptr [rcx+1Ch], 1
0x180013261  jz      short loc_18001327D
0x180013263  mov     rcx, [rcx+10h]
0x180013267  mov     edx, 1Ah
0x18001326c  mov     [rsp+0A8h+var_80], edi
0x180013270  xor     r9d, r9d
0x180013273  mov     [rsp+0A8h+var_88], rbx
0x180013278  call    WPP_SF_Ssd
0x18001327d  cmp     cs:1800EF078h, r15d
0x180013284  jnz     loc_1800133E2
0x18001328a  test    rdi, rdi
0x18001328d  jnz     short loc_1800132ED
0x18001328f  mov     eax, [rsi+70h]
0x180013292  mov     ebx, r15d
0x180013295  test    eax, eax
0x180013297  jz      short loc_1800132ED
0x180013299  cmp     ebx, eax
0x18001329b  jnb     short loc_1800132E4
0x18001329d  mov     ecx, ebx
0x18001329f  shl     rcx, 4
0x1800132a3  add     rcx, [rsi+90h]
0x1800132aa  movsxd  rax, dword ptr [rcx+8]
0x1800132ae  cmp     eax, 4
0x1800132b1  jz      short loc_1800132E4
0x1800132b3  mov     rcx, [rcx]
0x1800132b6  mov     r9, r14
0x1800132b9  imul    rdx, rax, 38h ; '8'
0x1800132bd  mov     rax, cs:1800EF538h
0x1800132c4  xor     r8d, r8d
0x1800132c7  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800132cc  mov     rax, [rdx+rax+90h]
0x1800132d4  mov     rdx, rbp
0x1800132d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132dc  mov     rdi, rax
0x1800132df  test    rax, rax
0x1800132e2  jnz     short loc_1800132ED
0x1800132e4  mov     eax, [rsi+70h]
0x1800132e7  inc     ebx
0x1800132e9  cmp     ebx, eax
0x1800132eb  jb      short loc_18001329D
0x1800132ed  mov     rcx, cs:1800EF538h
0x1800132f4  add     rcx, 8; lpCriticalSection
0x1800132f8  call    cs:__imp_LeaveCriticalSection
0x1800132fe  test    byte ptr [rbp+8], 2
0x180013302  mov     rsi, [rsp+0A8h+var_38]
0x180013307  jz      short loc_180013319
0x180013309  test    rdi, rdi
0x18001330c  jnz     short loc_18001333C
0x18001330e  mov     rcx, [r14]
0x180013311  call    SortMatchList
0x180013316  mov     rdi, rax
0x180013319  test    rdi, rdi
0x18001331c  jnz     short loc_18001333C
0x18001331e  mov     rax, rdi
0x180013321  mov     rcx, [rsp+0A8h+var_40]
0x180013326  xor     rcx, rsp; StackCookie
0x180013329  call    __security_check_cookie
0x18001332e  add     rsp, 78h
0x180013332  pop     r15
0x180013334  pop     r14
0x180013336  pop     r12
0x180013338  pop     rdi
0x180013339  pop     rbp
0x18001333a  pop     rbx
0x18001333b  retn
0x18001333c  mov     rcx, [r14]
0x18001333f  call    FreeMatchBufListInternal
0x180013344  mov     rax, r15
0x180013347  mov     [r14], rax
0x18001334a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013351  lea     rbx, aFeenumlayer; "FeEnumLayer"
0x180013358  cmp     rcx, r12
0x18001335b  jz      short loc_180013383
0x18001335d  cmp     byte ptr [rcx+19h], 2
0x180013361  jb      short loc_180013383
0x180013363  test    byte ptr [rcx+1Ch], 1
0x180013367  jz      short loc_180013383
0x180013369  mov     rcx, [rcx+10h]
0x18001336d  mov     edx, 1Ah
0x180013372  mov     [rsp+0A8h+var_80], edi
0x180013376  xor     r9d, r9d
0x180013379  mov     [rsp+0A8h+var_88], rbx
0x18001337e  call    WPP_SF_Ssd
0x180013383  cmp     dword ptr cs:1800EF078h, 0
0x18001338a  jz      short loc_18001331E
0x18001338c  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180013393  jz      short loc_18001331E
0x180013395  lea     rax, [rsp+0A8h+var_78]
0x18001339a  mov     [rsp+0A8h+var_78], edi
0x18001339e  mov     [rsp+0A8h+var_50], rax
0x1800133a3  lea     rdx, WFP_USERMODE_ERROR
0x1800133aa  lea     rax, [rsp+0A8h+var_70]
0x1800133af  mov     [rsp+0A8h+var_60], rbx
0x1800133b4  mov     r9d, 3
0x1800133ba  mov     [rsp+0A8h+var_88], rax
0x1800133bf  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800133c6  mov     [rsp+0A8h+var_58], 0Ch
0x1800133cf  mov     [rsp+0A8h+var_48], 4
0x1800133d8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800133dd  jmp     loc_18001331E
0x1800133e2  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x1800133e9  jz      loc_18001328A
0x1800133ef  lea     rax, [rsp+0A8h+var_78]
0x1800133f4  mov     [rsp+0A8h+var_78], edi
0x1800133f8  mov     [rsp+0A8h+var_50], rax
0x1800133fd  lea     rdx, WFP_USERMODE_ERROR
0x180013404  lea     rax, [rsp+0A8h+var_70]
0x180013409  mov     [rsp+0A8h+var_60], rbx
0x18001340e  mov     r9d, 3
0x180013414  mov     [rsp+0A8h+var_88], rax
0x180013419  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180013420  mov     [rsp+0A8h+var_58], 13h
0x180013429  mov     [rsp+0A8h+var_48], 4
0x180013432  call    McGenEventWrite_EtwEventWriteTransfer
0x180013437  jmp     loc_1800132ED
0x18001343c  mov     rcx, cs:1800EF538h
0x180013443  add     rcx, 8; lpCriticalSection
0x180013447  call    cs:__imp_LeaveCriticalSection
0x18001344d  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x180013454  mov     rcx, rdi
0x180013457  call    WfpReportError
0x18001345c  mov     rcx, [r14]
0x18001345f  call    FreeMatchBufListInternal
0x180013464  xor     r15d, r15d
0x180013467  lea     r12, WPP_GLOBAL_Control
0x18001346e  jmp     loc_180013344
```
