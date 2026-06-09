# IPxlatInterfaceMgr::Disable464xlat(unsigned __int64)

- ea: `0x18000f668`
- end: `0x18000f9e9`
- name: `?Disable464xlat@IPxlatInterfaceMgr@@QEAAK_K@Z`
- size: `897`
- prototype: `__int64 __fastcall(IPxlatInterfaceMgr *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c450`

## callees

- `0x180001d40`
- `0x180002110`
- `0x18000c224`
- `0x18000f668`
- `0x1800116bc`
- `0x180011f3c`
- `0x1800122a0`
- `0x180012388`
- `0x180012430`
- `0x1800132ac`
- `0x180013720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f961`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f961`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f6dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f96a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f992`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f6dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f96a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f6ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f6ce`

## string_xrefs

- `0x18000f8c9`: `Successfully deleted interface object`

## pseudocode

```c
__int64 __fastcall IPxlatInterfaceMgr::Disable464xlat(IPxlatInterfaceMgr *this, unsigned __int64 a2)
{
  int v4; // ecx
  unsigned int v5; // ebx
  const char *v6; // r8
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *v9; // rdi
  unsigned __int64 v10; // rbx
  char v11; // r9
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r8d
  __int64 v15; // rcx
  __int64 i; // rax
  __int64 **v17; // rcx
  __int64 *v18; // rax
  __int64 *j; // rcx
  __int64 *k; // rcx
  _QWORD *v21; // rax
  void *v22; // r15
  void *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // r8
  char v26; // al
  unsigned __int64 v28; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v29[12]; // [rsp+68h] [rbp-60h] BYREF
  int v30; // [rsp+74h] [rbp-54h]
  const char *v31; // [rsp+78h] [rbp-50h]
  __int64 v32; // [rsp+80h] [rbp-48h]
  __int64 *v33; // [rsp+88h] [rbp-40h]
  __int64 v34; // [rsp+90h] [rbp-38h]

  v4 = 0;
  v5 = 1722;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 0) )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v6 = "Disable464xlat: Interface manager is cleaning up";
LABEL_52:
      McTemplateU0sqx_EventWriteTransfer(v4, a2, (_DWORD)v6, v5, a2);
      return v5;
    }
    return v5;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *(_BYTE *)this )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v6 = "Disable464xlat: RPC is blocked";
      goto LABEL_52;
    }
    return v5;
  }
  v7 = (__int64 *)*((_QWORD *)this + 16);
  v8 = (__int64 *)v7[1];
  v30 = 0;
  v9 = v7;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( v8[4] >= a2 )
    {
      v9 = v8;
      v8 = (__int64 *)*v8;
    }
    else
    {
      v8 = (__int64 *)v8[2];
    }
  }
  if ( *((_BYTE *)v9 + 25) || a2 < v9[4] || v7 == v9 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v5 = 1168;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v6 = "Disable464xlat: 464xlat is not enabled on this interface";
      goto LABEL_52;
    }
    return v5;
  }
  v10 = v9[5];
  v9[5] = 0;
  v28 = v10;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl'::`2'::impl) )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 4) != 0 )
    {
      v11 = *(_BYTE *)(v10 + 69);
      v12 = 16;
      if ( v11 )
      {
        v13 = v10 + 53;
        v14 = 16;
      }
      else
      {
        v13 = 0;
        v14 = 0;
      }
      if ( *(_BYTE *)(v10 + 52) )
      {
        v15 = v10 + 36;
      }
      else
      {
        v15 = 0;
        v12 = 0;
      }
      McTemplateU0qxqqbr3qqbr6q_EventWriteTransfer(
        v15,
        (unsigned int)IPXLATCFG_DISABLE_XLAT_EVENT,
        0,
        *(_QWORD *)v10,
        *(_DWORD *)(v10 + 32),
        v12,
        v15,
        *(_BYTE *)(v10 + 52),
        v14,
        v13,
        v11);
    }
  }
  else if ( (Microsoft_Windows_IPxlatCfgEnableBits & 4) != 0 )
  {
    McTemplateU0xqb16qb16q_EventWriteTransfer(
      v10 + 53,
      (unsigned int)IPXLATCFG_DISABLE_XLAT_EVENT_OLD,
      *(_QWORD *)v10,
      *(_DWORD *)(v10 + 32),
      v10 + 36,
      *(_BYTE *)(v10 + 52),
      v10 + 53,
      *(_BYTE *)(v10 + 69));
  }
  for ( i = *((_QWORD *)this + 13); i != *((_QWORD *)this + 14); i += 8 )
  {
    if ( *(_DWORD *)i == *(_DWORD *)(v10 + 132) )
    {
      *(_BYTE *)(i + 4) = 1;
      break;
    }
  }
  IPxlatInterface::Cleanup((IPxlatInterface *)v10);
  v17 = (__int64 **)v9[2];
  if ( *((_BYTE *)v17 + 25) )
  {
    v18 = v9;
    for ( j = (__int64 *)v9[1]; !*((_BYTE *)j + 25) && v18 == (__int64 *)j[2]; j = (__int64 *)j[1] )
      v18 = j;
  }
  else
  {
    for ( k = *v17; !*((_BYTE *)k + 25); k = (__int64 *)*k )
      ;
  }
  v21 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Extract(
          (_QWORD *)this + 16,
          v9);
  v22 = v21;
  v23 = (void *)v21[5];
  if ( v23 )
  {
    IPxlatInterface::~IPxlatInterface((IPxlatInterface *)v21[5]);
    operator delete(v23);
  }
  operator delete(v22);
  v26 = Microsoft_Windows_IPxlatCfgEnableBits;
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    v28 = a2;
    v31 = "Successfully deleted interface object";
    v32 = 38;
    v33 = (__int64 *)&v28;
    v34 = 8;
    McGenEventWrite_EventWriteTransfer(v24, IPXLATCFG_INTERFACE_INFO_EVENT, v25, 3, v29);
    v26 = Microsoft_Windows_IPxlatCfgEnableBits;
  }
  if ( !*((_QWORD *)this + 17) )
  {
    if ( (v26 & 2) != 0 )
    {
      v31 = "464xlat is now disabled on all interfaces";
      v32 = 42;
      McGenEventWrite_EventWriteTransfer(v24, IPXLATCFG_INFO_EVENT, v25, 2, v29);
    }
    SetEvent(*((HANDLE *)this + 5));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( v10 )
  {
    IPxlatInterface::~IPxlatInterface((IPxlatInterface *)v10);
    operator delete((void *)v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f668  mov     [rsp+arg_8], rbx
0x18000f66d  mov     [rsp+arg_10], rsi
0x18000f672  push    rdi
0x18000f673  push    r12
0x18000f675  push    r13
0x18000f677  push    r14
0x18000f679  push    r15
0x18000f67b  sub     rsp, 0A0h
0x18000f682  mov     rax, cs:__security_cookie
0x18000f689  xor     rax, rsp
0x18000f68c  mov     [rsp+0C8h+var_30], rax
0x18000f694  mov     r14, rdx
0x18000f697  mov     rsi, rcx
0x18000f69a  xor     r13d, r13d
0x18000f69d  mov     ecx, r13d
0x18000f6a0  xor     eax, eax
0x18000f6a2  mov     ebx, 6BAh
0x18000f6a7  lock cmpxchg [rsi+4], ecx
0x18000f6ac  jnz     short loc_18000F6C7
0x18000f6ae  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000f6b5  jz      loc_18000F9BA
0x18000f6bb  lea     r8, aDisable464xlat_1; "Disable464xlat: Interface manager is cl"...
0x18000f6c2  jmp     loc_18000F9AD
0x18000f6c7  lea     r12, [rsi+38h]
0x18000f6cb  mov     rcx, r12; lpCriticalSection
0x18000f6ce  call    cs:__imp_EnterCriticalSection
0x18000f6d4  cmp     [rsi], r13b
0x18000f6d7  jz      short loc_18000F6FB
0x18000f6d9  mov     rcx, r12; lpCriticalSection
0x18000f6dc  call    cs:__imp_LeaveCriticalSection
0x18000f6e2  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000f6e9  jz      loc_18000F9BA
0x18000f6ef  lea     r8, aDisable464xlat; "Disable464xlat: RPC is blocked"
0x18000f6f6  jmp     loc_18000F9AD
0x18000f6fb  lea     r15, [rsi+80h]
0x18000f702  mov     rcx, [r15]
0x18000f705  mov     rax, [rcx+8]
0x18000f709  xor     edx, edx
0x18000f70b  mov     [rsp+0C8h+var_54], edx
0x18000f70f  mov     rdi, rcx
0x18000f712  jmp     short loc_18000F726
0x18000f714  cmp     [rax+20h], r14
0x18000f718  jnb     short loc_18000F720
0x18000f71a  mov     rax, [rax+10h]
0x18000f71e  jmp     short loc_18000F726
0x18000f720  mov     rdi, rax
0x18000f723  mov     rax, [rax]
0x18000f726  cmp     [rax+19h], r13b
0x18000f72a  jz      short loc_18000F714
0x18000f72c  cmp     [rdi+19h], r13b
0x18000f730  jnz     loc_18000F98F
0x18000f736  cmp     r14, [rdi+20h]
0x18000f73a  jb      loc_18000F98F
0x18000f740  cmp     rcx, rdi
0x18000f743  jz      loc_18000F98F
0x18000f749  mov     rbx, [rdi+28h]
0x18000f74d  mov     [rdi+28h], r13
0x18000f751  mov     [rsp+0C8h+var_68], rbx
0x18000f756  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl(void)'::`2'::impl
0x18000f75d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled(void)
0x18000f762  test    al, al
0x18000f764  jz      short loc_18000F7E0
0x18000f766  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 4
0x18000f76d  jz      loc_18000F81E
0x18000f773  movzx   r9d, byte ptr [rbx+45h]
0x18000f778  mov     eax, 10h
0x18000f77d  test    r9b, r9b
0x18000f780  jnz     short loc_18000F78A
0x18000f782  mov     rdx, r13
0x18000f785  mov     r8d, r13d
0x18000f788  jmp     short loc_18000F791
0x18000f78a  lea     rdx, [rbx+35h]
0x18000f78e  mov     r8d, eax
0x18000f791  movzx   r10d, byte ptr [rbx+34h]
0x18000f796  cmp     [rbx+34h], r13b
0x18000f79a  jnz     short loc_18000F7A4
0x18000f79c  mov     rcx, r13
0x18000f79f  mov     eax, r13d
0x18000f7a2  jmp     short loc_18000F7A8
0x18000f7a4  lea     rcx, [rbx+24h]
0x18000f7a8  mov     [rsp+0C8h+var_78], r9d
0x18000f7ad  mov     [rsp+0C8h+var_80], rdx
0x18000f7b2  mov     [rsp+0C8h+var_88], r8d
0x18000f7b7  mov     [rsp+0C8h+var_90], r10d
0x18000f7bc  mov     [rsp+0C8h+var_98], rcx
0x18000f7c1  mov     [rsp+0C8h+var_A0], eax
0x18000f7c5  mov     eax, [rbx+20h]
0x18000f7c8  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18000f7cc  mov     r9, [rbx]
0x18000f7cf  xor     r8d, r8d
0x18000f7d2  lea     rdx, IPXLATCFG_DISABLE_XLAT_EVENT
0x18000f7d9  call    McTemplateU0qxqqbr3qqbr6q_EventWriteTransfer
0x18000f7de  jmp     short loc_18000F81E
0x18000f7e0  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 4
0x18000f7e7  jz      short loc_18000F81E
0x18000f7e9  movzx   eax, byte ptr [rbx+45h]
0x18000f7ed  lea     rcx, [rbx+35h]
0x18000f7f1  movzx   edx, byte ptr [rbx+34h]
0x18000f7f5  lea     r8, [rbx+24h]
0x18000f7f9  mov     [rsp+0C8h+var_90], eax
0x18000f7fd  mov     [rsp+0C8h+var_98], rcx
0x18000f802  mov     [rsp+0C8h+var_A0], edx
0x18000f806  mov     [rsp+0C8h+var_A8], r8
0x18000f80b  mov     r9d, [rbx+20h]
0x18000f80f  mov     r8, [rbx]
0x18000f812  lea     rdx, IPXLATCFG_DISABLE_XLAT_EVENT_OLD
0x18000f819  call    McTemplateU0xqb16qb16q_EventWriteTransfer
0x18000f81e  mov     rax, [rsi+68h]
0x18000f822  cmp     rax, [rsi+70h]
0x18000f826  jz      short loc_18000F83C
0x18000f828  mov     ecx, [rbx+84h]
0x18000f82e  cmp     [rax], ecx
0x18000f830  jz      short loc_18000F838
0x18000f832  add     rax, 8
0x18000f836  jmp     short loc_18000F822
0x18000f838  mov     byte ptr [rax+4], 1
0x18000f83c  mov     rcx, rbx; this
0x18000f83f  call    ?Cleanup@IPxlatInterface@@QEAAXXZ; IPxlatInterface::Cleanup(void)
0x18000f844  mov     rcx, [rdi+10h]
0x18000f848  cmp     [rcx+19h], r13b
0x18000f84c  jz      short loc_18000F86C
0x18000f84e  mov     rax, rdi
0x18000f851  mov     rcx, [rdi+8]
0x18000f855  jmp     short loc_18000F864
0x18000f857  cmp     rax, [rcx+10h]
0x18000f85b  jnz     short loc_18000F881
0x18000f85d  mov     rax, rcx
0x18000f860  mov     rcx, [rcx+8]
0x18000f864  cmp     [rcx+19h], r13b
0x18000f868  jz      short loc_18000F857
0x18000f86a  jmp     short loc_18000F881
0x18000f86c  mov     rcx, [rcx]
0x18000f86f  cmp     [rcx+19h], r13b
0x18000f873  jnz     short loc_18000F881
0x18000f875  mov     rax, [rcx]
0x18000f878  mov     rcx, rax
0x18000f87b  cmp     [rax+19h], r13b
0x18000f87f  jz      short loc_18000F875
0x18000f881  mov     rdx, rdi
0x18000f884  mov     rcx, r15
0x18000f887  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>,std::_Iterator_base0>)
0x18000f88c  mov     r15, rax
0x18000f88f  mov     rdi, [rax+28h]
0x18000f893  test    rdi, rdi
0x18000f896  jz      short loc_18000F8AD
0x18000f898  mov     rcx, rdi; this
0x18000f89b  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000f8a0  mov     edx, 0E8h; unsigned __int64
0x18000f8a5  mov     rcx, rdi; void *
0x18000f8a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f8ad  mov     edx, 30h ; '0'; unsigned __int64
0x18000f8b2  mov     rcx, r15; void *
0x18000f8b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f8ba  mov     eax, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x18000f8c0  test    al, 2
0x18000f8c2  jz      short loc_18000F91C
0x18000f8c4  mov     [rsp+0C8h+var_68], r14
0x18000f8c9  lea     rax, aSuccessfullyDe; "Successfully deleted interface object"
0x18000f8d0  mov     [rsp+0C8h+var_50], rax
0x18000f8d5  mov     [rsp+0C8h+var_48], 26h ; '&'
0x18000f8e1  lea     rax, [rsp+0C8h+var_68]
0x18000f8e6  mov     [rsp+0C8h+var_40], rax
0x18000f8ee  mov     [rsp+0C8h+var_38], 8
0x18000f8fa  lea     rax, [rsp+0C8h+var_60]
0x18000f8ff  mov     [rsp+0C8h+var_A8], rax
0x18000f904  mov     r9d, 3
0x18000f90a  lea     rdx, IPXLATCFG_INTERFACE_INFO_EVENT
0x18000f911  call    McGenEventWrite_EventWriteTransfer
0x18000f916  mov     eax, cs:Microsoft_Windows_IPxlatCfgEnableBits
0x18000f91c  cmp     [rsi+88h], r13
0x18000f923  jnz     short loc_18000F967
0x18000f925  test    al, 2
0x18000f927  jz      short loc_18000F95D
0x18000f929  lea     rax, a464xlatIsNowDi; "464xlat is now disabled on all interfac"...
0x18000f930  mov     [rsp+0C8h+var_50], rax
0x18000f935  mov     [rsp+0C8h+var_48], 2Ah ; '*'
0x18000f941  lea     rax, [rsp+0C8h+var_60]
0x18000f946  mov     [rsp+0C8h+var_A8], rax
0x18000f94b  mov     r9d, 2
0x18000f951  lea     rdx, IPXLATCFG_INFO_EVENT
0x18000f958  call    McGenEventWrite_EventWriteTransfer
0x18000f95d  mov     rcx, [rsi+28h]; hEvent
0x18000f961  call    cs:__imp_SetEvent
0x18000f967  mov     rcx, r12; lpCriticalSection
0x18000f96a  call    cs:__imp_LeaveCriticalSection
0x18000f970  nop
0x18000f971  test    rbx, rbx
0x18000f974  jz      short loc_18000F98B
0x18000f976  mov     rcx, rbx; this
0x18000f979  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000f97e  mov     edx, 0E8h; unsigned __int64
0x18000f983  mov     rcx, rbx; void *
0x18000f986  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f98b  xor     eax, eax
0x18000f98d  jmp     short loc_18000F9BC
0x18000f98f  mov     rcx, r12; lpCriticalSection
0x18000f992  call    cs:__imp_LeaveCriticalSection
0x18000f998  mov     ebx, 490h
0x18000f99d  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000f9a4  jz      short loc_18000F9BA
0x18000f9a6  lea     r8, aDisable464xlat_2; "Disable464xlat: 464xlat is not enabled "...
0x18000f9ad  mov     [rsp+0C8h+var_A8], r14
0x18000f9b2  mov     r9d, ebx
0x18000f9b5  call    McTemplateU0sqx_EventWriteTransfer
0x18000f9ba  mov     eax, ebx
0x18000f9bc  mov     rcx, [rsp+0C8h+var_30]
0x18000f9c4  xor     rcx, rsp; StackCookie
0x18000f9c7  call    __security_check_cookie
0x18000f9cc  lea     r11, [rsp+0C8h+var_28]
0x18000f9d4  mov     rbx, [r11+38h]
0x18000f9d8  mov     rsi, [r11+40h]
0x18000f9dc  mov     rsp, r11
0x18000f9df  pop     r15
0x18000f9e1  pop     r14
0x18000f9e3  pop     r13
0x18000f9e5  pop     r12
0x18000f9e7  pop     rdi
0x18000f9e8  retn
```
