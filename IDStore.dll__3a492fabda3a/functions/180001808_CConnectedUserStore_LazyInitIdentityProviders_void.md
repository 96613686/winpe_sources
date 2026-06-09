# CConnectedUserStore::LazyInitIdentityProviders(void)

- ea: `0x180001808`
- end: `0x180001b7f`
- name: `?LazyInitIdentityProviders@CConnectedUserStore@@AEAAJXZ`
- size: `887`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001064`
- `0x180016bb8`
- `0x180016d1c`

## callees

- `0x180001808`
- `0x180001b88`
- `0x180003560`
- `0x18000dff0`
- `0x18001448c`
- `0x1800144b4`
- `0x1800144f4`
- `0x180017620`
- `0x1800191ac`
- `0x180019722`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800019a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800019a0`
- `ntdll!RtlEnterCriticalSection` at `0x1800018b8`
- `ntdll!RtlEnterCriticalSection` at `0x1800018b8`
- `ntdll!RtlLeaveCriticalSection` at `0x180001b0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180001b0e`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::LazyInitIdentityProviders(CConnectedUserStore *this, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  int v6; // eax
  CIdentityProfileHandler *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rsi
  void *v11; // rax
  unsigned int v12; // esi
  unsigned int v13; // r14d
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  void (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // ebx
  unsigned int v23; // [rsp+30h] [rbp-48h] BYREF
  int v24; // [rsp+34h] [rbp-44h] BYREF
  __int64 v25; // [rsp+38h] [rbp-40h] BYREF
  void (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-38h] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-30h] BYREF
  __int128 v28; // [rsp+58h] [rbp-20h] BYREF

  v24 = 0;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  v27[1] = "CConnectedUserStore::LazyInitIdentityProviders";
  v27[0] = &v24;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::LazyInitIdentityProviders");
  }
  if ( *((_QWORD *)this + 21) )
  {
    CLogBlock::~CLogBlock((CLogBlock *)v27, a2, a3);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v26);
    return 0;
  }
  v5 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
  if ( *((_QWORD *)this + 21) )
    goto LABEL_12;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 23) + 24LL))(
         *((_QWORD *)this + 23),
         &v23);
  v24 = v6;
  if ( v6 >= 0 )
  {
    if ( !v23 )
    {
      v24 = 0;
      v5 = -1;
      v23 = 0;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
        goto LABEL_14;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids);
      goto LABEL_12;
    }
    v11 = CoTaskMemAlloc(32LL * v23);
    v5 = (__int64)v11;
    if ( !v11 )
    {
      v24 = -2147024882;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_43;
      }
      v8 = 94;
      v9 = 2147942414LL;
      goto LABEL_11;
    }
    memset_0(v11, 0, 32LL * v23);
    v12 = 0;
    v28 = 0;
    v13 = 0;
    if ( !v23 )
      goto LABEL_12;
    do
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)this + 23) + 32LL))(
              *((_QWORD *)this + 23),
              v13,
              &v28,
              &v26);
      v24 = v14;
      if ( v14 >= 0 )
      {
        ATL::CComQIPtr<IConnectedIdentityProvider,&__s_GUID const _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1>::operator=(
          &v25,
          v26,
          v16);
        v17 = v26;
        if ( v26 )
        {
          v26 = 0;
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v17)[2])(v17);
        }
        if ( v25 )
        {
          v18 = 32LL * v12;
          *(_OWORD *)(v18 + v5) = v28;
          v19 = v25;
          v25 = 0;
          *(_QWORD *)(v18 + v5 + 24) = v19;
          ++v12;
        }
        v7 = WPP_GLOBAL_Control;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, v13, v14);
          v7 = WPP_GLOBAL_Control;
        }
        v24 = 0;
      }
      ++v13;
    }
    while ( v13 < v23 );
    if ( v12 < v23 )
    {
      if ( v7 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)v7 + 2), 96, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v12, v23);
        v7 = WPP_GLOBAL_Control;
      }
      v23 = v12;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v8 = 92;
      v9 = (unsigned int)v6;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v9);
LABEL_12:
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v24 >= 0 )
  {
LABEL_14:
    v10 = v5;
    if ( v7 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)v7 + 2), 97, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v23);
    *((_DWORD *)this + 44) = v23;
    v5 = 0;
    v23 = 0;
    goto LABEL_44;
  }
LABEL_43:
  *((_DWORD *)this + 44) = 0;
  v10 = 0;
LABEL_44:
  *((_QWORD *)this + 21) = v10;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CoTaskMemFree((LPVOID)v5);
  v22 = v24;
  CLogBlock::~CLogBlock((CLogBlock *)v27, v20, v21);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v26)[2])(v26);
  return v22;
}

```

## disassembly

```asm
0x180001808  push    rbp
0x18000180a  push    rbx
0x18000180b  push    rsi
0x18000180c  push    rdi
0x18000180d  push    r12
0x18000180f  push    r13
0x180001811  push    r14
0x180001813  push    r15
0x180001815  mov     rbp, rsp
0x180001818  sub     rsp, 78h
0x18000181c  mov     rax, cs:__security_cookie
0x180001823  xor     rax, rsp
0x180001826  mov     [rbp+var_10], rax
0x18000182a  mov     rdi, rcx
0x18000182d  xor     r12d, r12d
0x180001830  mov     [rbp+var_44], r12d
0x180001834  mov     [rbp+var_38], r12
0x180001838  mov     [rbp+var_40], r12
0x18000183c  mov     [rbp+var_48], r12d
0x180001840  lea     r9, aCconnecteduser_5; "CConnectedUserStore::LazyInitIdentityPr"...
0x180001847  mov     [rbp+var_28], r9
0x18000184b  lea     rax, [rbp+var_44]
0x18000184f  mov     [rbp+var_30], rax
0x180001853  lea     r13, WPP_GLOBAL_Control
0x18000185a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001861  cmp     rcx, r13
0x180001864  jz      short loc_18000187E
0x180001866  test    dword ptr [rcx+1Ch], 400h
0x18000186d  jz      short loc_18000187E
0x18000186f  lea     edx, [r12+0Ah]
0x180001874  mov     rcx, [rcx+10h]
0x180001878  call    WPP_SF_s
0x18000187d  nop
0x18000187e  cmp     [rdi+0A8h], r12
0x180001885  jz      short loc_1800018AB
0x180001887  lea     rcx, [rbp+var_30]; this
0x18000188b  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180001890  nop
0x180001891  lea     rcx, [rbp+var_40]
0x180001895  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000189a  nop
0x18000189b  lea     rcx, [rbp+var_38]
0x18000189f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800018a4  xor     eax, eax
0x1800018a6  jmp     loc_180001B62
0x1800018ab  mov     rbx, r12
0x1800018ae  lea     r15, [rdi+80h]
0x1800018b5  mov     rcx, r15; CriticalSection
0x1800018b8  call    cs:__imp_RtlEnterCriticalSection
0x1800018be  cmp     [rdi+0A8h], r12
0x1800018c5  jnz     short loc_18000190F
0x1800018c7  mov     rcx, [rdi+0B8h]
0x1800018ce  mov     rax, [rcx]
0x1800018d1  lea     rdx, [rbp+var_48]
0x1800018d5  mov     rax, [rax+18h]
0x1800018d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018de  mov     [rbp+var_44], eax
0x1800018e1  test    eax, eax
0x1800018e3  jns     short loc_18000195C
0x1800018e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018ec  cmp     rcx, r13
0x1800018ef  jz      short loc_180001916
0x1800018f1  test    byte ptr [rcx+1Ch], 4
0x1800018f5  jz      short loc_180001916
0x1800018f7  mov     edx, 5Ch ; '\'
0x1800018fc  mov     r9d, eax
0x1800018ff  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180001906  mov     rcx, [rcx+10h]
0x18000190a  call    WPP_SF_d
0x18000190f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001916  cmp     [rbp+var_44], r12d
0x18000191a  jl      loc_180001AFA
0x180001920  mov     rsi, rbx
0x180001923  cmp     rcx, r13
0x180001926  jz      short loc_180001947
0x180001928  test    byte ptr [rcx+1Ch], 10h
0x18000192c  jz      short loc_180001947
0x18000192e  mov     edx, 61h ; 'a'
0x180001933  mov     r9d, [rbp+var_48]
0x180001937  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000193e  mov     rcx, [rcx+10h]
0x180001942  call    WPP_SF_d
0x180001947  mov     eax, [rbp+var_48]
0x18000194a  mov     [rdi+0B0h], eax
0x180001950  mov     rbx, r12
0x180001953  mov     [rbp+var_48], r12d
0x180001957  jmp     loc_180001B04
0x18000195c  mov     eax, [rbp+var_48]
0x18000195f  test    eax, eax
0x180001961  jnz     short loc_180001999
0x180001963  mov     [rbp+var_44], r12d
0x180001967  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000196b  mov     [rbp+var_48], r12d
0x18000196f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001976  cmp     rcx, r13
0x180001979  jz      short loc_180001920
0x18000197b  test    byte ptr [rcx+1Ch], 8
0x18000197f  jz      short loc_180001920
0x180001981  lea     edx, [rax+5Dh]
0x180001984  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000198b  mov     rcx, [rcx+10h]
0x18000198f  call    WPP_SF_
0x180001994  jmp     loc_18000190F
0x180001999  mov     rcx, rax
0x18000199c  shl     rcx, 5; cb
0x1800019a0  call    cs:__imp_CoTaskMemAlloc
0x1800019a6  mov     rbx, rax
0x1800019a9  test    rax, rax
0x1800019ac  jnz     short loc_1800019DD
0x1800019ae  mov     [rbp+var_44], 8007000Eh
0x1800019b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019bc  cmp     rcx, r13
0x1800019bf  jz      loc_180001AFA
0x1800019c5  test    byte ptr [rcx+1Ch], 4
0x1800019c9  jz      loc_180001AFA
0x1800019cf  lea     edx, [rax+5Eh]
0x1800019d2  mov     r9d, 8007000Eh
0x1800019d8  jmp     loc_1800018FF
0x1800019dd  mov     r8d, [rbp+var_48]
0x1800019e1  shl     r8, 5; Size
0x1800019e5  xor     edx, edx; Val
0x1800019e7  mov     rcx, rbx; void *
0x1800019ea  call    memset_0
0x1800019ef  mov     esi, r12d
0x1800019f2  xorps   xmm0, xmm0
0x1800019f5  movups  [rbp+var_20], xmm0
0x1800019f9  mov     r14d, r12d
0x1800019fc  cmp     [rbp+var_48], r12d
0x180001a00  jbe     loc_18000190F
0x180001a06  mov     rcx, [rdi+0B8h]
0x180001a0d  mov     rax, [rcx]
0x180001a10  lea     r9, [rbp+var_38]
0x180001a14  lea     r8, [rbp+var_20]
0x180001a18  mov     edx, r14d
0x180001a1b  mov     rax, [rax+20h]
0x180001a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a24  mov     [rbp+var_44], eax
0x180001a27  test    eax, eax
0x180001a29  jns     short loc_180001A5A
0x180001a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a32  cmp     rcx, r13
0x180001a35  jz      short loc_180001A54
0x180001a37  test    byte ptr [rcx+1Ch], 4
0x180001a3b  jz      short loc_180001A54
0x180001a3d  mov     [rsp+78h+var_58], eax
0x180001a41  mov     r9d, r14d
0x180001a44  mov     rcx, [rcx+10h]
0x180001a48  call    WPP_SF_Dd
0x180001a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a54  mov     [rbp+var_44], r12d
0x180001a58  jmp     short loc_180001AAD
0x180001a5a  mov     rdx, [rbp+var_38]
0x180001a5e  lea     rcx, [rbp+var_40]
0x180001a62  call    ??4?$CComQIPtr@UIConnectedIdentityProvider@@$1?_GUID_b7417b54_e08c_429b_96c8_678d1369ecb1@@3U__s_GUID@@B@ATL@@QEAAPEAUIConnectedIdentityProvider@@PEAUIUnknown@@@Z; ATL::CComQIPtr<IConnectedIdentityProvider,&__s_GUID const _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1>::operator=(IUnknown *)
0x180001a67  nop
0x180001a68  mov     rcx, [rbp+var_38]
0x180001a6c  test    rcx, rcx
0x180001a6f  jz      short loc_180001A82
0x180001a71  mov     [rbp+var_38], r12
0x180001a75  mov     rax, [rcx]
0x180001a78  mov     rax, [rax+10h]
0x180001a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a81  nop
0x180001a82  cmp     [rbp+var_40], r12
0x180001a86  jz      short loc_180001AA6
0x180001a88  mov     ecx, esi
0x180001a8a  shl     rcx, 5
0x180001a8e  movups  xmm0, [rbp+var_20]
0x180001a92  movdqu  xmmword ptr [rcx+rbx], xmm0
0x180001a97  mov     rax, [rbp+var_40]
0x180001a9b  mov     [rbp+var_40], r12
0x180001a9f  mov     [rcx+rbx+18h], rax
0x180001aa4  inc     esi
0x180001aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001aad  inc     r14d
0x180001ab0  mov     eax, [rbp+var_48]
0x180001ab3  cmp     r14d, eax
0x180001ab6  jb      loc_180001A06
0x180001abc  cmp     esi, eax
0x180001abe  jnb     loc_180001916
0x180001ac4  cmp     rcx, r13
0x180001ac7  jz      short loc_180001AF2
0x180001ac9  test    byte ptr [rcx+1Ch], 8
0x180001acd  jz      short loc_180001AF2
0x180001acf  mov     edx, 60h ; '`'
0x180001ad4  mov     [rsp+78h+var_58], eax
0x180001ad8  mov     r9d, esi
0x180001adb  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180001ae2  mov     rcx, [rcx+10h]
0x180001ae6  call    WPP_SF_DD
0x180001aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001af2  mov     [rbp+var_48], esi
0x180001af5  jmp     loc_180001916
0x180001afa  mov     [rdi+0B0h], r12d
0x180001b01  mov     rsi, r12
0x180001b04  mov     [rdi+0A8h], rsi
0x180001b0b  mov     rcx, r15; CriticalSection
0x180001b0e  call    cs:__imp_RtlLeaveCriticalSection
0x180001b14  lea     rax, [rbx-1]
0x180001b18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001b1c  ja      short loc_180001B27
0x180001b1e  mov     rcx, rbx; pv
0x180001b21  call    cs:__imp_CoTaskMemFree
0x180001b27  mov     ebx, [rbp+var_44]
0x180001b2a  lea     rcx, [rbp+var_30]; this
0x180001b2e  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180001b33  nop
0x180001b34  mov     rcx, [rbp+var_40]
0x180001b38  test    rcx, rcx
0x180001b3b  jz      short loc_180001B4A
0x180001b3d  mov     rax, [rcx]
0x180001b40  mov     rax, [rax+10h]
0x180001b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b49  nop
0x180001b4a  mov     rcx, [rbp+var_38]
0x180001b4e  test    rcx, rcx
0x180001b51  jz      short loc_180001B60
0x180001b53  mov     rdx, [rcx]
0x180001b56  mov     rax, [rdx+10h]
0x180001b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b5f  nop
0x180001b60  mov     eax, ebx
0x180001b62  mov     rcx, [rbp+var_10]
0x180001b66  xor     rcx, rsp; StackCookie
0x180001b69  call    __security_check_cookie
0x180001b6e  add     rsp, 78h
0x180001b72  pop     r15
0x180001b74  pop     r14
0x180001b76  pop     r13
0x180001b78  pop     r12
0x180001b7a  pop     rdi
0x180001b7b  pop     rsi
0x180001b7c  pop     rbx
0x180001b7d  pop     rbp
0x180001b7e  retn
```
