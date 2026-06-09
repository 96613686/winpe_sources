# AppActivation::PrepareHostManagementForActivate(Execution::IHamHacksForViewActivation *)

- ea: `0x18002baa0`
- end: `0x18002bff7`
- name: `?PrepareHostManagementForActivate@AppActivation@@UEAAJPEAUIHamHacksForViewActivation@Execution@@@Z`
- size: `1367`
- prototype: `__int64 __fastcall(AppActivation *__hidden this, struct Execution::IHamHacksForViewActivation *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18002baa0`
- `0x18002c4b0`
- `0x180044360`
- `0x180044514`
- `0x18005ae90`
- `0x18005b37c`
- `0x18005ba40`
- `0x1800a0010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18002bc53`
- `ntdll!RtlCopySid` at `0x18002bc53`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002bb18`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002befb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002bb18`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002befb`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x18002bb44`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x18002bc98`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x18002bb44`
- `RMCLIENT!HamPopulateActivityPropertiesByClass` at `0x18002bc98`
- `RMCLIENT!HamStartActivityAsync` at `0x18002bdc3`
- `RMCLIENT!HamStartActivityAsync` at `0x18002bdc3`
- `RMCLIENT!HamCreateActivity` at `0x18002bd94`
- `RMCLIENT!HamCreateActivity` at `0x18002bd94`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppActivation::PrepareHostManagementForActivate(
        LARGE_INTEGER *this,
        struct Execution::IHamHacksForViewActivation *a2)
{
  LONG HighPart; // edi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  LARGE_INTEGER v10; // r14
  __int16 *QuadPart; // rbx
  DWORD LowPart; // r12d
  void *v13; // r13
  __int64 v14; // rcx
  int inited; // eax
  int v16; // edi
  __int64 v17; // rcx
  __int64 v18; // rdx
  _WORD *v19; // r8
  __int16 v20; // ax
  int v21; // eax
  __int64 v22; // rdi
  _QWORD *v23; // rax
  HamActivityWrapper *v24; // rbx
  unsigned int v25; // r15d
  _QWORD *v26; // r14
  int Activity; // edi
  __int64 v28; // r9
  __int64 v29; // rdx
  int v30; // eax
  LARGE_INTEGER v31; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  int v33[2]; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  LARGE_INTEGER v35; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-B8h] BYREF
  LARGE_INTEGER v37; // [rsp+50h] [rbp-B0h]
  _DWORD v38[78]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v39; // [rsp+198h] [rbp+98h]
  __int64 v40; // [rsp+1A0h] [rbp+A0h]
  int v41; // [rsp+1D0h] [rbp+D0h]
  _DWORD v42[78]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int16 v43; // [rsp+328h] [rbp+228h]
  __int64 v44; // [rsp+330h] [rbp+230h]
  int v45; // [rsp+360h] [rbp+260h]
  _BYTE v46[464]; // [rsp+380h] [rbp+280h] BYREF
  char DestinationSid[68]; // [rsp+550h] [rbp+450h] BYREF
  DWORD v48; // [rsp+594h] [rbp+494h]
  int v49; // [rsp+598h] [rbp+498h]
  LARGE_INTEGER v50; // [rsp+5A0h] [rbp+4A0h]
  wil::details::in1diag3 *retaddr; // [rsp+5F8h] [rbp+4F8h]

  if ( (this[12].HighPart & 0x10000) != 0 )
    return 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  memset_0(v38, 0, 0x188u);
  HighPart = this[12].HighPart;
  v6 = HamPopulateActivityPropertiesByClass(L"WaitForTerminate", 0, 0, v38);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_NtStatus(
      retaddr,
      (void *)7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationactivity.cpp",
      (const char *)(unsigned int)v6,
      v32);
  }
  else if ( (HighPart & 0x2000000) != 0 )
  {
    v38[67] = 0;
    v38[68] = 300;
    v38[0] = v38[0] & 0xFE7FBE7F | 0x1000080;
    if ( (HighPart & 0x1000) != 0 )
    {
      v40 |= 0x20uLL;
      v41 &= 0xFFFFFFFC;
    }
  }
  else
  {
    v38[0] |= 0x100000u;
    if ( (HighPart & 0x2000) != 0 || (HighPart & 0x11001) == 0 )
      v39 |= 0xC1u;
  }
  *(LARGE_INTEGER *)v33 = this[9];
  v7 = (*(__int64 (__fastcall **)(struct Execution::IHamHacksForViewActivation *, LARGE_INTEGER, _QWORD, LARGE_INTEGER))(*(_QWORD *)a2 + 40LL))(
         a2,
         this[14],
         this[11].LowPart,
         this[5]);
  v8 = v7;
  if ( v7 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&this[26]);
    v9 = this[12].HighPart;
    v37 = this[8];
    v10 = this[9];
    QuadPart = (__int16 *)this[5].QuadPart;
    LowPart = this[11].LowPart;
    v13 = (void *)this[14].QuadPart;
    inited = wil::init_once_nothrow__lambda_229667101e80dd97992435660d7f8331___(v14, 0);
    v16 = inited;
    if ( inited < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)inited,
        v33[0]);
    }
    else
    {
      memset_0(v46, 0, 0x228u);
      v17 = 2147483646;
      v18 = 232;
      v19 = v46;
      while ( v17 )
      {
        v20 = *QuadPart;
        if ( !*QuadPart )
          break;
        ++QuadPart;
        *v19++ = v20;
        --v17;
        if ( !--v18 )
        {
          --v19;
          break;
        }
      }
      *v19 = 0;
      RtlCopySid(0x44u, DestinationSid, v13);
      v48 = LowPart;
      v49 = 2;
      v50 = v10;
      memset_0(v42, 0, 0x188u);
      v21 = HamPopulateActivityPropertiesByClass(L"Activation", 0, 0, v42);
      if ( v21 >= 0 )
      {
        if ( (v9 & 0x2000000) != 0 )
        {
          v42[67] = 0;
          v42[68] = 300;
          v42[0] = v42[0] & 0xFE7FBE7F | 0x1000080;
          if ( (v9 & 0x1000) != 0 )
          {
            v44 |= 0x20uLL;
            v45 &= 0xFFFFFFFC;
          }
        }
        else
        {
          v42[0] |= 0x100000u;
          if ( (v9 & 0x2000) != 0 || (v9 & 0x11001) == 0 )
            v43 |= 0xC1u;
        }
LABEL_18:
        v35.QuadPart = 0;
        v22 = qword_1800D2598;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
        v23 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
        v24 = (HamActivityWrapper *)v23;
        if ( v23 )
        {
          *v23 = &HamActivityWrapper::`vftable';
          v23[1] = 0;
          v23[2] = 0;
          v23[3] = v22;
          v23[4] = -1;
          *((_DWORD *)v23 + 10) = 0;
          *(_QWORD *)((char *)v23 + 44) = 4;
          v23[7] = 0;
          v23[8] = 0;
          *((_DWORD *)v23 + 18) = 0;
          *((_DWORD *)v23 + 19) = 6912;
          v23[10] = -1;
          v23[11] = v37.QuadPart;
          *((_DWORD *)v23 + 24) = 1;
          v35.QuadPart = (LONGLONG)v23;
          v25 = (v9 >> 21) & 1;
          v23[10] = v50.QuadPart;
          v26 = v23 + 4;
          v33[0] = (_DWORD)v23 + 32;
          Activity = HamCreateActivity(v23[3], v23, v46, v42);
          if ( Activity >= 0 )
          {
            (*(void (__fastcall **)(HamActivityWrapper *))(*(_QWORD *)v24 + 8LL))(v24);
            *((_DWORD *)v24 + 10) = 1;
            Activity = HamStartActivityAsync(*((_QWORD *)v24 + 3), *v26, v25, 0);
            if ( Activity >= 0 )
            {
              v31 = v35;
              if ( v35.QuadPart )
              {
                (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v35.QuadPart + 8LL))(v35);
                v31 = v35;
              }
              this[26] = v31;
              if ( v31.QuadPart )
              {
                v35.QuadPart = 0;
                (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v31.QuadPart + 16LL))(v31);
              }
              goto LABEL_34;
            }
            HamActivityWrapper::Close(v24);
          }
          v28 = (unsigned int)Activity;
          v29 = 162;
        }
        else
        {
          v35.QuadPart = 0;
          v28 = 3221225495LL;
          v29 = 150;
        }
        v16 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v29,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
                (const char *)v28,
                v33[0]);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
        if ( v16 < 0 )
          goto LABEL_27;
LABEL_34:
        v35.QuadPart = 0;
        QueryPerformanceCounter(&v35);
        this[38].QuadPart += v35.QuadPart - PerformanceCount.QuadPart;
        return 0;
      }
      v30 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)7,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationactivity.cpp",
              (const char *)(unsigned int)v21,
              v33[0]);
      v16 = v30;
      if ( v30 >= 0 )
        goto LABEL_18;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v30,
        v33[0]);
    }
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v16,
      v34);
    return (unsigned int)v16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14B,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
    (const char *)(unsigned int)v7,
    v33[0]);
  return v8;
}

```

## disassembly

```asm
0x18002baa0  mov     [rsp-8+arg_10], rbx
0x18002baa5  push    rbp
0x18002baa6  push    rsi
0x18002baa7  push    rdi
0x18002baa8  push    r12
0x18002baaa  push    r13
0x18002baac  push    r14
0x18002baae  push    r15
0x18002bab0  lea     rbp, [rsp-4C0h]
0x18002bab8  sub     rsp, 5C0h
0x18002babf  mov     rax, cs:__security_cookie
0x18002bac6  xor     rax, rsp
0x18002bac9  mov     [rbp+4F0h+var_40], rax
0x18002bad0  mov     rbx, rdx
0x18002bad3  mov     rsi, rcx
0x18002bad6  test    dword ptr [rcx+64h], 10000h
0x18002badd  jz      short loc_18002BB0B
0x18002badf  xor     eax, eax
0x18002bae1  mov     rcx, [rbp+4F0h+var_40]
0x18002bae8  xor     rcx, rsp; StackCookie
0x18002baeb  call    __security_check_cookie
0x18002baf0  mov     rbx, [rsp+5F0h+arg_10]
0x18002baf8  add     rsp, 5C0h
0x18002baff  pop     r15
0x18002bb01  pop     r14
0x18002bb03  pop     r13
0x18002bb05  pop     r12
0x18002bb07  pop     rdi
0x18002bb08  pop     rsi
0x18002bb09  pop     rbp
0x18002bb0a  retn
0x18002bb0b  xor     r14d, r14d
0x18002bb0e  mov     qword ptr [rsp+5F0h+PerformanceCount], r14
0x18002bb13  lea     rcx, [rsp+5F0h+PerformanceCount]; lpPerformanceCount
0x18002bb18  call    cs:__imp_QueryPerformanceCounter
0x18002bb1e  xor     edx, edx; Val
0x18002bb20  mov     r8d, 188h; Size
0x18002bb26  lea     rcx, [rsp+5F0h+var_590]; void *
0x18002bb2b  call    memset_0
0x18002bb30  mov     edi, [rsi+64h]
0x18002bb33  lea     r9, [rsp+5F0h+var_590]
0x18002bb38  xor     r8d, r8d
0x18002bb3b  xor     edx, edx
0x18002bb3d  lea     rcx, aWaitfortermina; "WaitForTerminate"
0x18002bb44  call    cs:__imp_HamPopulateActivityPropertiesByClass
0x18002bb4a  mov     ecx, 0C1h
0x18002bb4f  test    eax, eax
0x18002bb51  js      loc_18002BE6E
0x18002bb57  bt      edi, 19h
0x18002bb5b  jb      loc_18002BF30
0x18002bb61  or      [rsp+5F0h+var_590], 100000h
0x18002bb69  bt      edi, 0Dh
0x18002bb6d  jnb     loc_18002BF6B
0x18002bb73  or      [rbp+4F0h+var_458], cx
0x18002bb7a  mov     rax, [rbx]
0x18002bb7d  lea     rcx, [rsp+5F0h+var_590]
0x18002bb82  mov     [rsp+5F0h+var_5C8], rcx
0x18002bb87  mov     rdx, [rsi+48h]
0x18002bb8b  mov     qword ptr [rsp+5F0h+var_5D0], rdx; int
0x18002bb90  mov     r9, [rsi+28h]
0x18002bb94  mov     r8d, [rsi+58h]
0x18002bb98  mov     rdx, [rsi+70h]
0x18002bb9c  mov     rcx, rbx
0x18002bb9f  mov     rax, [rax+28h]
0x18002bba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bba8  mov     ebx, eax
0x18002bbaa  test    eax, eax
0x18002bbac  js      loc_18002BE8E
0x18002bbb2  lea     rcx, [rsi+0D0h]
0x18002bbb9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002bbbe  mov     r15d, [rsi+64h]
0x18002bbc2  mov     rax, [rsi+40h]
0x18002bbc6  mov     [rsp+5F0h+var_5A0], rax
0x18002bbcb  mov     r14, [rsi+48h]
0x18002bbcf  mov     rbx, [rsi+28h]
0x18002bbd3  mov     r12d, [rsi+58h]
0x18002bbd7  mov     r13, [rsi+70h]
0x18002bbdb  xor     edx, edx
0x18002bbdd  call    wil__init_once_nothrow__lambda_229667101e80dd97992435660d7f8331___
0x18002bbe2  mov     edi, eax
0x18002bbe4  test    eax, eax
0x18002bbe6  js      loc_18002BF7C
0x18002bbec  xor     edx, edx; Val
0x18002bbee  mov     r8d, 228h; Size
0x18002bbf4  lea     rcx, [rbp+4F0h+var_270]; void *
0x18002bbfb  call    memset_0
0x18002bc00  mov     ecx, 7FFFFFFEh
0x18002bc05  mov     edx, 0E8h
0x18002bc0a  lea     r8, [rbp+4F0h+var_270]
0x18002bc11  test    rcx, rcx
0x18002bc14  jz      short loc_18002BC3E
0x18002bc16  movzx   eax, word ptr [rbx]
0x18002bc19  test    ax, ax
0x18002bc1c  jz      short loc_18002BC39
0x18002bc1e  add     rbx, 2
0x18002bc22  mov     [r8], ax
0x18002bc26  add     r8, 2
0x18002bc2a  dec     rcx
0x18002bc2d  sub     rdx, 1
0x18002bc31  jnz     short loc_18002BC11
0x18002bc33  sub     r8, 2
0x18002bc37  jmp     short loc_18002BC3E
0x18002bc39  test    rdx, rdx
0x18002bc3c  jz      short loc_18002BC33
0x18002bc3e  xor     eax, eax
0x18002bc40  mov     [r8], ax
0x18002bc44  mov     r8, r13; SourceSid
0x18002bc47  lea     rdx, [rbp+4F0h+DestinationSid]; DestinationSid
0x18002bc4e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18002bc53  call    cs:__imp_RtlCopySid
0x18002bc59  mov     [rbp+4F0h+var_5C], r12d
0x18002bc60  mov     [rbp+4F0h+var_58], 2
0x18002bc6a  mov     [rbp+4F0h+var_50], r14
0x18002bc71  xor     edx, edx; Val
0x18002bc73  mov     r8d, 188h; Size
0x18002bc79  lea     rcx, [rbp+4F0h+var_400]; void *
0x18002bc80  call    memset_0
0x18002bc85  lea     r9, [rbp+4F0h+var_400]
0x18002bc8c  xor     r8d, r8d
0x18002bc8f  xor     edx, edx
0x18002bc91  lea     rcx, aActivation; "Activation"
0x18002bc98  call    cs:__imp_HamPopulateActivityPropertiesByClass
0x18002bc9e  test    eax, eax
0x18002bca0  js      loc_18002BE0C
0x18002bca6  bt      r15d, 19h
0x18002bcab  jb      loc_18002BF9C
0x18002bcb1  or      [rbp+4F0h+var_400], 100000h
0x18002bcbb  bt      r15d, 0Dh
0x18002bcc0  jnb     loc_18002BFE5
0x18002bcc6  mov     eax, 0C1h
0x18002bccb  or      [rbp+4F0h+var_2C8], ax
0x18002bcd2  mov     qword ptr [rsp+5F0h+var_5B0], 0
0x18002bcdb  mov     rdi, cs:qword_1800D2598
0x18002bce2  lea     rcx, [rsp+5F0h+var_5B0]
0x18002bce7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002bcec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002bcf3  mov     ecx, 68h ; 'h'; unsigned __int64
0x18002bcf8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002bcfd  mov     rbx, rax
0x18002bd00  test    rax, rax
0x18002bd03  jz      loc_18002BF17
0x18002bd09  lea     rax, ??_7HamActivityWrapper@@6B@; const HamActivityWrapper::`vftable'
0x18002bd10  mov     [rbx], rax
0x18002bd13  xor     eax, eax
0x18002bd15  mov     [rbx+8], rax
0x18002bd19  mov     [rbx+10h], rax
0x18002bd1d  mov     [rbx+18h], rdi
0x18002bd21  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18002bd29  mov     [rbx+28h], eax
0x18002bd2c  mov     qword ptr [rbx+2Ch], 4
0x18002bd34  mov     [rbx+38h], rax
0x18002bd38  mov     [rbx+40h], rax
0x18002bd3c  mov     [rbx+48h], eax
0x18002bd3f  mov     dword ptr [rbx+4Ch], 1B00h
0x18002bd46  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x18002bd4e  mov     rax, [rsp+5F0h+var_5A0]
0x18002bd53  mov     [rbx+58h], rax
0x18002bd57  mov     dword ptr [rbx+60h], 1
0x18002bd5e  mov     qword ptr [rsp+5F0h+var_5B0], rbx
0x18002bd63  shr     r15d, 15h
0x18002bd67  and     r15d, 1
0x18002bd6b  mov     rax, [rbp+4F0h+var_50]
0x18002bd72  mov     [rbx+50h], rax
0x18002bd76  lea     r14, [rbx+20h]
0x18002bd7a  mov     qword ptr [rsp+5F0h+var_5D0], r14; int
0x18002bd7f  lea     r9, [rbp+4F0h+var_400]
0x18002bd86  lea     r8, [rbp+4F0h+var_270]
0x18002bd8d  mov     rdx, rbx
0x18002bd90  mov     rcx, [rbx+18h]
0x18002bd94  call    cs:__imp_HamCreateActivity
0x18002bd9a  mov     edi, eax
0x18002bd9c  test    eax, eax
0x18002bd9e  js      short loc_18002BDDB
0x18002bda0  mov     rax, [rbx]
0x18002bda3  mov     rcx, rbx
0x18002bda6  mov     rax, [rax+8]
0x18002bdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdaf  mov     dword ptr [rbx+28h], 1
0x18002bdb6  xor     r9d, r9d
0x18002bdb9  mov     r8d, r15d
0x18002bdbc  mov     rdx, [r14]
0x18002bdbf  mov     rcx, [rbx+18h]
0x18002bdc3  call    cs:__imp_HamStartActivityAsync
0x18002bdc9  mov     edi, eax
0x18002bdcb  test    eax, eax
0x18002bdcd  jns     loc_18002BEB0
0x18002bdd3  mov     rcx, rbx; this
0x18002bdd6  call    ?Close@HamActivityWrapper@@QEAAXXZ; HamActivityWrapper::Close(void)
0x18002bddb  mov     r9d, edi; char *
0x18002bdde  mov     edx, 0A2h; void *
0x18002bde3  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002bdea  mov     rcx, [rbp+4F8h]; this
0x18002bdf1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002bdf6  mov     edi, eax
0x18002bdf8  lea     rcx, [rsp+5F0h+var_5B0]
0x18002bdfd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002be02  test    edi, edi
0x18002be04  jns     loc_18002BEED
0x18002be0a  jmp     short loc_18002BE4C
0x18002be0c  mov     rcx, [rbp+4F8h]; this
0x18002be13  mov     r9d, eax; char *
0x18002be16  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002be1d  mov     edx, 7; void *
0x18002be22  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002be27  mov     edi, eax
0x18002be29  test    eax, eax
0x18002be2b  jns     loc_18002BCD2
0x18002be31  mov     rcx, [rbp+4F8h]; this
0x18002be38  mov     r9d, eax; char *
0x18002be3b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002be42  mov     edx, 93h; void *
0x18002be47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be4c  mov     rcx, [rbp+4F8h]; this
0x18002be53  mov     r9d, edi; char *
0x18002be56  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002be5d  mov     edx, 14Dh; void *
0x18002be62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be67  mov     eax, edi
0x18002be69  jmp     loc_18002BAE1
0x18002be6e  mov     rcx, [rbp+4F8h]; this
0x18002be75  mov     r9d, eax; char *
0x18002be78  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002be7f  mov     edx, 7; void *
0x18002be84  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002be89  jmp     loc_18002BB7A
0x18002be8e  mov     rcx, [rbp+4F8h]; this
0x18002be95  mov     r9d, ebx; char *
0x18002be98  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002be9f  mov     edx, 14Bh; void *
0x18002bea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bea9  mov     eax, ebx
0x18002beab  jmp     loc_18002BAE1
0x18002beb0  mov     rcx, qword ptr [rsp+5F0h+var_5B0]
0x18002beb5  test    rcx, rcx
0x18002beb8  jz      short loc_18002BECB
0x18002beba  mov     rax, [rcx]
0x18002bebd  mov     rax, [rax+8]
0x18002bec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bec6  mov     rcx, qword ptr [rsp+5F0h+var_5B0]
0x18002becb  mov     [rsi+0D0h], rcx
0x18002bed2  test    rcx, rcx
0x18002bed5  jz      short loc_18002BEED
0x18002bed7  mov     qword ptr [rsp+5F0h+var_5B0], 0
0x18002bee0  mov     rax, [rcx]
0x18002bee3  mov     rax, [rax+10h]
0x18002bee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002beec  nop
0x18002beed  mov     qword ptr [rsp+5F0h+var_5B0], 0
0x18002bef6  lea     rcx, [rsp+5F0h+var_5B0]; lpPerformanceCount
0x18002befb  call    cs:__imp_QueryPerformanceCounter
0x18002bf01  mov     rax, qword ptr [rsp+5F0h+var_5B0]
0x18002bf06  sub     rax, qword ptr [rsp+5F0h+PerformanceCount]
0x18002bf0b  add     [rsi+130h], rax
0x18002bf12  jmp     loc_18002BADF
0x18002bf17  mov     qword ptr [rsp+5F0h+var_5B0], 0
0x18002bf20  mov     r9d, 0C0000017h
0x18002bf26  mov     edx, 96h
0x18002bf2b  jmp     loc_18002BDE3
0x18002bf30  mov     [rbp+4F0h+var_484], r14d
0x18002bf34  mov     [rbp+4F0h+var_480], 12Ch
0x18002bf3b  mov     eax, [rsp+5F0h+var_590]
0x18002bf3f  and     eax, 0FF7FBEFFh
0x18002bf44  or      eax, 1000080h
0x18002bf49  mov     [rsp+5F0h+var_590], eax
0x18002bf4d  bt      edi, 0Ch
0x18002bf51  jnb     loc_18002BB7A
0x18002bf57  or      [rbp+4F0h+var_450], 20h
0x18002bf5f  and     [rbp+4F0h+var_420], 0FFFFFFFCh
0x18002bf66  jmp     loc_18002BB7A
0x18002bf6b  test    edi, 11001h
0x18002bf71  jnz     loc_18002BB7A
0x18002bf77  jmp     loc_18002BB73
0x18002bf7c  mov     rcx, [rbp+4F8h]; this
0x18002bf83  mov     r9d, eax; char *
0x18002bf86  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002bf8d  mov     edx, 8Dh; void *
0x18002bf92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bf97  jmp     loc_18002BE4C
0x18002bf9c  mov     [rbp+4F0h+var_2F4], 0
0x18002bfa6  mov     [rbp+4F0h+var_2F0], 12Ch
0x18002bfb0  mov     eax, [rbp+4F0h+var_400]
0x18002bfb6  and     eax, 0FF7FBEFFh
0x18002bfbb  or      eax, 1000080h
0x18002bfc0  mov     [rbp+4F0h+var_400], eax
0x18002bfc6  bt      r15d, 0Ch
0x18002bfcb  jnb     loc_18002BCD2
0x18002bfd1  or      [rbp+4F0h+var_2C0], 20h
0x18002bfd9  and     [rbp+4F0h+var_290], 0FFFFFFFCh
0x18002bfe0  jmp     loc_18002BCD2
0x18002bfe5  test    r15d, 11001h
0x18002bfec  jnz     loc_18002BCD2
0x18002bff2  jmp     loc_18002BCC6
```
