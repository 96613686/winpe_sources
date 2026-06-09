# AAMHamActivityStartAsync

- ea: `0x18002c000`
- end: `0x18002c422`
- name: `AAMHamActivityStartAsync`
- size: `1058`
- prototype: `__int64 __usercall@<rax>(PSID SourceSid@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032ed4`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18002c000`
- `0x18002c4b0`
- `0x180044408`
- `0x180044514`
- `0x18005ae90`
- `0x18005b37c`
- `0x18005ba40`
- `0x1800839ec`
- `0x1800a0010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18002c0f0`
- `ntdll!RtlCopySid` at `0x18002c0f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002c059`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002c059`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c38c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c3c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c38c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c3c0`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x18002c131`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x18002c131`
- `RMCLIENT!HamStartActivityAsync` at `0x18002c257`
- `RMCLIENT!HamStartActivityAsync` at `0x18002c257`
- `RMCLIENT!HamCreateActivity` at `0x18002c228`
- `RMCLIENT!HamCreateActivity` at `0x18002c228`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AAMHamActivityStartAsync(
        PSID SourceSid,
        int a2,
        __int16 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        _QWORD *a7)
{
  const char *v11; // r9
  int LastError; // edi
  __int64 v13; // rax
  __int64 v14; // rcx
  _WORD *v15; // r8
  __int16 v16; // dx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rsi
  _QWORD *v20; // rax
  HamActivityWrapper *v21; // rdi
  unsigned int v22; // ebx
  _QWORD *v23; // r14
  int Activity; // esi
  __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int v27; // ebx
  int v28; // eax
  _QWORD *v30; // rcx
  int v31; // eax
  int v32; // [rsp+20h] [rbp-E0h]
  _QWORD *v33; // [rsp+30h] [rbp-D0h] BYREF
  WINBOOL fPending; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v35[78]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v36; // [rsp+178h] [rbp+78h]
  __int64 v37; // [rsp+180h] [rbp+80h]
  int v38; // [rsp+1B0h] [rbp+B0h]
  _BYTE v39[464]; // [rsp+1D0h] [rbp+D0h] BYREF
  char DestinationSid[68]; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v41; // [rsp+3E4h] [rbp+2E4h]
  int v42; // [rsp+3E8h] [rbp+2E8h]
  __int64 v43; // [rsp+3F0h] [rbp+2F0h]
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+358h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&stru_1800D2398, 0, &fPending, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v11);
    if ( LastError >= 0 )
      goto LABEL_3;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)LastError,
      v32);
    return (unsigned int)LastError;
  }
  if ( fPending )
  {
    v31 = lambda_229667101e80dd97992435660d7f8331_::operator()();
    LastError = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"wil",
        (const char *)(unsigned int)v31,
        v32);
      InitOnceComplete(&stru_1800D2398, 4u, 0);
      goto LABEL_30;
    }
    InitOnceComplete(&stru_1800D2398, 0, 0);
  }
LABEL_3:
  memset_0(v39, 0, 0x228u);
  v13 = 2147483646;
  v14 = 232;
  v15 = v39;
  while ( v13 )
  {
    v16 = *a3;
    if ( !*a3 )
      break;
    ++a3;
    *v15++ = v16;
    --v13;
    if ( !--v14 )
    {
      --v15;
      break;
    }
  }
  *v15 = 0;
  RtlCopySid(0x44u, DestinationSid, SourceSid);
  v41 = a2;
  v42 = 2;
  v43 = a4;
  memset_0(v35, 0, 0x188u);
  v17 = HamPopulateActivityPropertiesByClass(L"Activation", 0, 0, v35);
  if ( v17 < 0 )
  {
    v28 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)7,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationactivity.cpp",
            (const char *)(unsigned int)v17,
            v32);
    v27 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v28,
        v32);
      return v27;
    }
    v18 = a6;
  }
  else
  {
    v18 = a6;
    if ( (a6 & 0x2000000) != 0 )
    {
      v35[67] = 0;
      v35[68] = 300;
      v35[0] = v35[0] & 0xFE7FBE7F | 0x1000080;
      if ( (a6 & 0x1000) != 0 )
      {
        v37 |= 0x20uLL;
        v38 &= 0xFFFFFFFC;
      }
    }
    else
    {
      v35[0] |= 0x100000u;
      if ( (a6 & 0x2000) != 0 || (a6 & 0x11001) == 0 )
        v36 |= 0xC1u;
    }
  }
  v33 = 0;
  v19 = qword_1800D2598;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v20 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = (HamActivityWrapper *)v20;
  if ( !v20 )
  {
    v33 = 0;
    v25 = 3221225495LL;
    v26 = 150;
    goto LABEL_17;
  }
  *v20 = &HamActivityWrapper::`vftable';
  v20[1] = 0;
  v20[2] = 0;
  v20[3] = v19;
  v20[4] = -1;
  *((_DWORD *)v20 + 10) = 0;
  *(_QWORD *)((char *)v20 + 44) = 4;
  v20[7] = 0;
  v20[8] = 0;
  *((_DWORD *)v20 + 18) = 0;
  *((_DWORD *)v20 + 19) = 6912;
  v20[10] = -1;
  v20[11] = a5;
  *((_DWORD *)v20 + 24) = 1;
  v33 = v20;
  v22 = (v18 >> 21) & 1;
  v20[10] = v43;
  v23 = v20 + 4;
  v32 = (_DWORD)v20 + 32;
  Activity = HamCreateActivity(v20[3], v20, v39, v35);
  if ( Activity < 0 )
  {
LABEL_16:
    v25 = (unsigned int)Activity;
    v26 = 162;
LABEL_17:
    v27 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v26,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
            (const char *)v25,
            v32);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
    return v27;
  }
  (*(void (__fastcall **)(HamActivityWrapper *))(*(_QWORD *)v21 + 8LL))(v21);
  *((_DWORD *)v21 + 10) = 1;
  Activity = HamStartActivityAsync(*((_QWORD *)v21 + 3), *v23, v22, 0);
  if ( Activity < 0 )
  {
    HamActivityWrapper::Close(v21);
    goto LABEL_16;
  }
  v30 = v33;
  if ( v33 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v33 + 8LL))(v33);
    v30 = v33;
  }
  *a7 = v30;
  if ( v30 )
  {
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c000  push    rbp
0x18002c002  push    rbx
0x18002c003  push    rsi
0x18002c004  push    rdi
0x18002c005  push    r12
0x18002c007  push    r13
0x18002c009  push    r14
0x18002c00b  push    r15
0x18002c00d  lea     rbp, [rsp-318h]
0x18002c015  sub     rsp, 418h
0x18002c01c  mov     rax, cs:__security_cookie
0x18002c023  xor     rax, rsp
0x18002c026  mov     [rbp+350h+var_50], rax
0x18002c02d  mov     rsi, r9
0x18002c030  mov     rbx, r8
0x18002c033  mov     r14d, edx
0x18002c036  mov     r15, rcx
0x18002c039  mov     r12, [rbp+350h+arg_30]
0x18002c040  xor     r13d, r13d
0x18002c043  mov     [rsp+450h+fPending], r13d
0x18002c048  xor     r9d, r9d; lpContext
0x18002c04b  lea     r8, [rsp+450h+fPending]; fPending
0x18002c050  xor     edx, edx; dwFlags
0x18002c052  lea     rcx, stru_1800D2398; lpInitOnce
0x18002c059  call    cs:__imp___std_init_once_begin_initialize
0x18002c05f  test    eax, eax
0x18002c061  jnz     loc_18002C34C
0x18002c067  mov     rcx, [rbp+358h]; this
0x18002c06e  lea     r8, aWil; "wil"
0x18002c075  mov     edx, 37Ah; void *
0x18002c07a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c07f  mov     edi, eax
0x18002c081  test    eax, eax
0x18002c083  js      loc_18002C392
0x18002c089  xor     edx, edx; Val
0x18002c08b  mov     r8d, 228h; Size
0x18002c091  lea     rcx, [rbp+350h+var_280]; void *
0x18002c098  call    memset_0
0x18002c09d  mov     eax, 7FFFFFFEh
0x18002c0a2  mov     ecx, 0E8h
0x18002c0a7  lea     r8, [rbp+350h+var_280]
0x18002c0ae  xchg    ax, ax
0x18002c0b0  test    rax, rax
0x18002c0b3  jz      short loc_18002C0DD
0x18002c0b5  movzx   edx, word ptr [rbx]
0x18002c0b8  test    dx, dx
0x18002c0bb  jz      short loc_18002C0D8
0x18002c0bd  add     rbx, 2
0x18002c0c1  mov     [r8], dx
0x18002c0c5  add     r8, 2
0x18002c0c9  dec     rax
0x18002c0cc  sub     rcx, 1
0x18002c0d0  jnz     short loc_18002C0B0
0x18002c0d2  sub     r8, 2
0x18002c0d6  jmp     short loc_18002C0DD
0x18002c0d8  test    rcx, rcx
0x18002c0db  jz      short loc_18002C0D2
0x18002c0dd  mov     [r8], r13w
0x18002c0e1  mov     r8, r15; SourceSid
0x18002c0e4  lea     rdx, [rbp+350h+DestinationSid]; DestinationSid
0x18002c0eb  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18002c0f0  call    cs:__imp_RtlCopySid
0x18002c0f6  mov     [rbp+350h+var_6C], r14d
0x18002c0fd  mov     [rbp+350h+var_68], 2
0x18002c107  mov     [rbp+350h+var_60], rsi
0x18002c10e  xor     edx, edx; Val
0x18002c110  mov     r8d, 188h; Size
0x18002c116  lea     rcx, [rsp+450h+var_410]; void *
0x18002c11b  call    memset_0
0x18002c120  lea     r9, [rsp+450h+var_410]
0x18002c125  xor     r8d, r8d
0x18002c128  xor     edx, edx
0x18002c12a  lea     rcx, aActivation; "Activation"
0x18002c131  call    cs:__imp_HamPopulateActivityPropertiesByClass
0x18002c137  test    eax, eax
0x18002c139  js      loc_18002C298
0x18002c13f  mov     ebx, [rbp+350h+arg_28]
0x18002c145  bt      ebx, 19h
0x18002c149  jb      loc_18002C3D6
0x18002c14f  or      [rsp+450h+var_410], 100000h
0x18002c157  bt      ebx, 0Dh
0x18002c15b  jnb     loc_18002C411
0x18002c161  mov     eax, 0C1h
0x18002c166  or      [rbp+350h+var_2D8], ax
0x18002c16a  mov     [rsp+450h+var_420], r13
0x18002c16f  mov     rsi, cs:qword_1800D2598
0x18002c176  lea     rcx, [rsp+450h+var_420]
0x18002c17b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c180  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c187  mov     ecx, 68h ; 'h'; unsigned __int64
0x18002c18c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c191  mov     rdi, rax
0x18002c194  test    rax, rax
0x18002c197  jz      loc_18002C337
0x18002c19d  lea     rax, ??_7HamActivityWrapper@@6B@; const HamActivityWrapper::`vftable'
0x18002c1a4  mov     [rdi], rax
0x18002c1a7  xor     eax, eax
0x18002c1a9  mov     [rdi+8], rax
0x18002c1ad  mov     [rdi+10h], rax
0x18002c1b1  mov     [rdi+18h], rsi
0x18002c1b5  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x18002c1bd  mov     [rdi+28h], r13d
0x18002c1c1  mov     qword ptr [rdi+2Ch], 4
0x18002c1c9  mov     [rdi+38h], r13
0x18002c1cd  mov     [rdi+40h], r13
0x18002c1d1  mov     [rdi+48h], r13d
0x18002c1d5  mov     dword ptr [rdi+4Ch], 1B00h
0x18002c1dc  mov     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x18002c1e4  mov     rax, [rbp+350h+arg_20]
0x18002c1eb  mov     [rdi+58h], rax
0x18002c1ef  mov     dword ptr [rdi+60h], 1
0x18002c1f6  mov     [rsp+450h+var_420], rdi
0x18002c1fb  shr     ebx, 15h
0x18002c1fe  and     ebx, 1
0x18002c201  mov     rax, [rbp+350h+var_60]
0x18002c208  mov     [rdi+50h], rax
0x18002c20c  lea     r14, [rdi+20h]
0x18002c210  mov     qword ptr [rsp+450h+var_430], r14; int
0x18002c215  lea     r9, [rsp+450h+var_410]
0x18002c21a  lea     r8, [rbp+350h+var_280]
0x18002c221  mov     rdx, rdi
0x18002c224  mov     rcx, [rdi+18h]
0x18002c228  call    cs:__imp_HamCreateActivity
0x18002c22e  mov     esi, eax
0x18002c230  test    eax, eax
0x18002c232  js      short loc_18002C26F
0x18002c234  mov     rax, [rdi]
0x18002c237  mov     rcx, rdi
0x18002c23a  mov     rax, [rax+8]
0x18002c23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c243  mov     dword ptr [rdi+28h], 1
0x18002c24a  xor     r9d, r9d
0x18002c24d  mov     r8d, ebx
0x18002c250  mov     rdx, [r14]
0x18002c253  mov     rcx, [rdi+18h]
0x18002c257  call    cs:__imp_HamStartActivityAsync
0x18002c25d  mov     esi, eax
0x18002c25f  test    eax, eax
0x18002c261  jns     loc_18002C2FD
0x18002c267  mov     rcx, rdi; this
0x18002c26a  call    ?Close@HamActivityWrapper@@QEAAXXZ; HamActivityWrapper::Close(void)
0x18002c26f  mov     r9d, esi; char *
0x18002c272  mov     edx, 0A2h; void *
0x18002c277  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c27e  mov     rcx, [rbp+358h]; this
0x18002c285  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c28a  mov     ebx, eax
0x18002c28c  lea     rcx, [rsp+450h+var_420]
0x18002c291  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002c296  jmp     short loc_18002C2D8
0x18002c298  mov     rcx, [rbp+358h]; this
0x18002c29f  mov     r9d, eax; char *
0x18002c2a2  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c2a9  mov     edx, 7; void *
0x18002c2ae  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c2b3  mov     ebx, eax
0x18002c2b5  test    eax, eax
0x18002c2b7  jns     loc_18002C3CB
0x18002c2bd  mov     rcx, [rbp+358h]; this
0x18002c2c4  mov     r9d, eax; char *
0x18002c2c7  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c2ce  mov     edx, 93h; void *
0x18002c2d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c2d8  mov     eax, ebx
0x18002c2da  mov     rcx, [rbp+350h+var_50]
0x18002c2e1  xor     rcx, rsp; StackCookie
0x18002c2e4  call    __security_check_cookie
0x18002c2e9  add     rsp, 418h
0x18002c2f0  pop     r15
0x18002c2f2  pop     r14
0x18002c2f4  pop     r13
0x18002c2f6  pop     r12
0x18002c2f8  pop     rdi
0x18002c2f9  pop     rsi
0x18002c2fa  pop     rbx
0x18002c2fb  pop     rbp
0x18002c2fc  retn
0x18002c2fd  mov     rcx, [rsp+450h+var_420]
0x18002c302  test    rcx, rcx
0x18002c305  jz      short loc_18002C318
0x18002c307  mov     rax, [rcx]
0x18002c30a  mov     rax, [rax+8]
0x18002c30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c313  mov     rcx, [rsp+450h+var_420]
0x18002c318  mov     [r12], rcx
0x18002c31c  test    rcx, rcx
0x18002c31f  jz      short loc_18002C333
0x18002c321  mov     [rsp+450h+var_420], r13
0x18002c326  mov     rax, [rcx]
0x18002c329  mov     rax, [rax+10h]
0x18002c32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c332  nop
0x18002c333  xor     eax, eax
0x18002c335  jmp     short loc_18002C2DA
0x18002c337  mov     [rsp+450h+var_420], r13
0x18002c33c  mov     r9d, 0C0000017h
0x18002c342  mov     edx, 96h
0x18002c347  jmp     loc_18002C277
0x18002c34c  cmp     [rsp+450h+fPending], r13d
0x18002c351  jz      loc_18002C089
0x18002c357  call    _lambda_229667101e80dd97992435660d7f8331___operator__
0x18002c35c  mov     edi, eax
0x18002c35e  test    eax, eax
0x18002c360  jns     short loc_18002C3B4
0x18002c362  mov     rcx, [rbp+358h]; this
0x18002c369  mov     r9d, eax; char *
0x18002c36c  lea     r8, aWil; "wil"
0x18002c373  mov     edx, 37Fh; void *
0x18002c378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c37d  xor     r8d, r8d; lpContext
0x18002c380  mov     edx, 4; dwFlags
0x18002c385  lea     rcx, stru_1800D2398; lpInitOnce
0x18002c38c  call    cs:__imp_InitOnceComplete
0x18002c392  mov     rcx, [rbp+358h]; this
0x18002c399  mov     r9d, edi; char *
0x18002c39c  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c3a3  mov     edx, 8Dh; void *
0x18002c3a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3ad  mov     eax, edi
0x18002c3af  jmp     loc_18002C2DA
0x18002c3b4  xor     r8d, r8d; lpContext
0x18002c3b7  xor     edx, edx; dwFlags
0x18002c3b9  lea     rcx, stru_1800D2398; lpInitOnce
0x18002c3c0  call    cs:__imp_InitOnceComplete
0x18002c3c6  jmp     loc_18002C089
0x18002c3cb  mov     ebx, [rbp+350h+arg_28]
0x18002c3d1  jmp     loc_18002C16A
0x18002c3d6  mov     [rbp+350h+var_304], r13d
0x18002c3da  mov     [rbp+350h+var_300], 12Ch
0x18002c3e1  mov     eax, [rsp+450h+var_410]
0x18002c3e5  and     eax, 0FF7FBEFFh
0x18002c3ea  or      eax, 1000080h
0x18002c3ef  mov     [rsp+450h+var_410], eax
0x18002c3f3  bt      ebx, 0Ch
0x18002c3f7  jnb     loc_18002C16A
0x18002c3fd  or      [rbp+350h+var_2D0], 20h
0x18002c405  and     [rbp+350h+var_2A0], 0FFFFFFFCh
0x18002c40c  jmp     loc_18002C16A
0x18002c411  test    ebx, 11001h
0x18002c417  jnz     loc_18002C16A
0x18002c41d  jmp     loc_18002C161
```
