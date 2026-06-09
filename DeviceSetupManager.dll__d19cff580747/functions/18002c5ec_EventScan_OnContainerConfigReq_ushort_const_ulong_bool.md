# EventScan::OnContainerConfigReq(ushort const *,ulong,bool)

- ea: `0x18002c5ec`
- end: `0x18002ca1a`
- name: `?OnContainerConfigReq@EventScan@@QEAAJPEBGK_N@Z`
- size: `1070`
- prototype: `int(EventScan *__hidden this, const unsigned __int16 *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002cb84`
- `0x18002cd38`

## callees

- `0x18000b740`
- `0x1800112a4`
- `0x18001580c`
- `0x18001777c`
- `0x18001985c`
- `0x18001af70`
- `0x18001b3f0`
- `0x18001bc4c`
- `0x18001bcb4`
- `0x180026414`
- `0x1800273d0`
- `0x18002748c`
- `0x18002c5ec`
- `0x18003f098`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002c632`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002c632`

## string_xrefs

- `0x18002c645`: `onecoreuap\base\devices\setup\dsm\service\eventscan.cpp`
- `0x18002c84a`: `onecoreuap\base\devices\setup\dsm\service\eventscan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall EventScan::OnContainerConfigReq(
        PSRWLOCK *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        char a4)
{
  HRESULT v8; // eax
  HRESULT v9; // edi
  HRESULT result; // eax
  unsigned int ContainerUINT; // edi
  unsigned int v12; // r12d
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // esi
  unsigned int v16; // ecx
  unsigned int v17; // r14d
  unsigned int v18; // eax
  int v19; // ebx
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-39h]
  int v22; // [rsp+20h] [rbp-39h]
  bool v23; // [rsp+30h] [rbp-29h] BYREF
  bool v24; // [rsp+31h] [rbp-28h] BYREF
  __int64 p_si128; // [rsp+40h] [rbp-19h] BYREF
  char *v26; // [rsp+48h] [rbp-11h] BYREF
  GUID iid; // [rsp+50h] [rbp-9h] BYREF
  __m128i si128; // [rsp+60h] [rbp+7h] BYREF
  int v29; // [rsp+70h] [rbp+17h]
  char v30; // [rsp+74h] [rbp+1Bh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  iid = 0;
  v8 = IIDFromString(a2, &iid);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\eventscan.cpp",
      (const char *)(unsigned int)v8,
      v21);
    return v9;
  }
  ContainerUINT = GetContainerUINT(a2, &DEVPKEY_DeviceSetup_DeviceState);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_L_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)&WPP_5f220cccee2e33150182d68011e709f6_Traceguids,
      ContainerUINT,
      (__int64)&iid);
  }
  if ( ContainerUINT - 4 <= 3 )
    return 0;
  if ( !IsCtaPolicyActive() )
    goto LABEL_35;
  v12 = a3 & 0xF;
  v13 = v12;
  if ( v12 > 3 )
    v13 = 3;
  if ( !v13 )
    v13 = 0;
  v14 = (unsigned __int8)a3 >> 4;
  if ( v14 > 3 )
    v14 = 3;
  if ( v13 >= v14 )
    v14 = v13;
  v15 = (a3 >> 8) & 0xF;
  v16 = v15;
  if ( v15 > 3 )
    v16 = 3;
  if ( v14 >= v16 )
    v16 = v14;
  v17 = (unsigned __int16)a3 >> 12;
  v18 = v17;
  if ( v17 > 3 )
    v18 = 3;
  if ( v16 >= v18 )
    v18 = v16;
  if ( v18 != 2 )
  {
LABEL_35:
    if ( a4 )
    {
      if ( dword_18005A520 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_18005A520);
        if ( dword_18005A520 == -1 )
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          v29 = 4;
          p_si128 = (__int64)&si128;
          v26 = &v30;
          std::vector<enum JobType>::vector<enum JobType>(&unk_18005A528, &p_si128);
          atexit(EventScan::OnContainerConfigReq_::_34_::_dynamic_atexit_destructor_for__jobs__);
          Init_thread_footer(&dword_18005A520);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_5f220cccee2e33150182d68011e709f6_Traceguids, &iid);
      }
      v19 = ContainerManager::PostJobs(this[3], 0);
      if ( v19 < 0 )
      {
        v20 = 478;
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\eventscan.cpp",
          (const char *)(unsigned int)v19,
          v22);
        return v19;
      }
    }
    else if ( ContainerUINT )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_5f220cccee2e33150182d68011e709f6_Traceguids, &iid);
      }
    }
    else
    {
      if ( dword_18005A540 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_18005A540);
        if ( dword_18005A540 == -1 )
        {
          p_si128 = 0x500000000LL;
          si128.m128i_i64[0] = (__int64)&p_si128;
          si128.m128i_i64[1] = (__int64)&v26;
          std::vector<enum JobType>::vector<enum JobType>(&unk_18005A548, &si128);
          atexit(EventScan::OnContainerConfigReq_::_45_::_dynamic_atexit_destructor_for__jobs__);
          Init_thread_footer(&dword_18005A540);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5f220cccee2e33150182d68011e709f6_Traceguids, &iid);
      }
      v19 = ContainerManager::PostJobs(this[3], 0);
      if ( v19 < 0 )
      {
        v20 = 496;
        goto LABEL_43;
      }
    }
    return 0;
  }
  v23 = 0;
  v24 = 0;
  result = QueryCtaAutoUpdatesEnabled(0, &v23, 0, &v24);
  if ( result >= 0 )
  {
    if ( !v23 || !v17 || (result = ContainerManager::RefreshContainer(this[3], &iid, 7, 0), result >= 0) )
    {
      if ( v24 && a4 && (v12 || v15) )
        return ContainerManager::RefreshContainer(this[3], &iid, 8, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c5ec  mov     [rsp-8+arg_10], rbx
0x18002c5f1  mov     [rsp-8+arg_18], rsi
0x18002c5f6  push    rbp
0x18002c5f7  push    rdi
0x18002c5f8  push    r12
0x18002c5fa  push    r14
0x18002c5fc  push    r15
0x18002c5fe  lea     rbp, [rsp-37h]
0x18002c603  sub     rsp, 90h
0x18002c60a  mov     rax, cs:__security_cookie
0x18002c611  xor     rax, rsp
0x18002c614  mov     [rbp+57h+var_30], rax
0x18002c618  mov     r15b, r9b
0x18002c61b  mov     r14d, r8d
0x18002c61e  mov     rsi, rdx
0x18002c621  mov     rbx, rcx
0x18002c624  xorps   xmm0, xmm0
0x18002c627  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18002c62b  lea     rdx, [rbp+57h+iid]; lpiid
0x18002c62f  mov     rcx, rsi; lpsz
0x18002c632  call    cs:__imp_IIDFromString
0x18002c638  mov     edi, eax
0x18002c63a  test    eax, eax
0x18002c63c  jns     short loc_18002C65D
0x18002c63e  mov     rcx, [rbp+5Fh]; this
0x18002c642  mov     r9d, eax; char *
0x18002c645  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002c64c  mov     edx, 195h; void *
0x18002c651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c656  mov     eax, edi
0x18002c658  jmp     loc_18002C922
0x18002c65d  lea     rdx, DEVPKEY_DeviceSetup_DeviceState; struct _DEVPROPKEY *
0x18002c664  mov     rcx, rsi; unsigned __int16 *
0x18002c667  call    ?GetContainerUINT@@YAIPEBGAEBU_DEVPROPKEY@@@Z; GetContainerUINT(ushort const *,_DEVPROPKEY const &)
0x18002c66c  mov     edi, eax
0x18002c66e  lea     r12, WPP_GLOBAL_Control
0x18002c675  mov     esi, 100h
0x18002c67a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c681  cmp     rcx, r12
0x18002c684  jz      short loc_18002C6B2
0x18002c686  test    [rcx+1Ch], esi
0x18002c689  jz      short loc_18002C6B2
0x18002c68b  cmp     byte ptr [rcx+19h], 4
0x18002c68f  jb      short loc_18002C6B2
0x18002c691  mov     edx, 24h ; '$'
0x18002c696  lea     rax, [rbp+57h+iid]
0x18002c69a  mov     qword ptr [rsp+0B0h+var_90], rax
0x18002c69f  mov     r9d, edi
0x18002c6a2  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c6a9  mov     rcx, [rcx+10h]
0x18002c6ad  call    WPP_SF_L_guid_
0x18002c6b2  lea     eax, [rdi-4]
0x18002c6b5  cmp     eax, 3
0x18002c6b8  jbe     loc_18002C920
0x18002c6be  call    ?IsCtaPolicyActive@@YA_NXZ; IsCtaPolicyActive(void)
0x18002c6c3  test    al, al
0x18002c6c5  jz      loc_18002C7BE
0x18002c6cb  mov     r12d, r14d
0x18002c6ce  and     r12d, 0Fh
0x18002c6d2  mov     ecx, r12d
0x18002c6d5  mov     edx, 3
0x18002c6da  cmp     r12d, edx
0x18002c6dd  cmova   ecx, edx
0x18002c6e0  xor     eax, eax
0x18002c6e2  test    ecx, ecx
0x18002c6e4  cmovz   ecx, eax
0x18002c6e7  mov     eax, r14d
0x18002c6ea  shr     eax, 4
0x18002c6ed  and     eax, 0Fh
0x18002c6f0  cmp     eax, edx
0x18002c6f2  cmova   eax, edx
0x18002c6f5  cmp     ecx, eax
0x18002c6f7  cmovnb  eax, ecx
0x18002c6fa  mov     esi, r14d
0x18002c6fd  shr     esi, 8
0x18002c700  and     esi, 0Fh
0x18002c703  mov     ecx, esi
0x18002c705  cmp     esi, edx
0x18002c707  cmova   ecx, edx
0x18002c70a  cmp     eax, ecx
0x18002c70c  cmovnb  ecx, eax
0x18002c70f  shr     r14d, 0Ch
0x18002c713  and     r14d, 0Fh
0x18002c717  mov     eax, r14d
0x18002c71a  cmp     r14d, edx
0x18002c71d  cmova   eax, edx
0x18002c720  cmp     ecx, eax
0x18002c722  cmovnb  eax, ecx
0x18002c725  cmp     eax, 2
0x18002c728  jnz     loc_18002C7B2
0x18002c72e  mov     [rbp+57h+var_80], 0
0x18002c732  mov     [rbp+57h+var_7F], 0
0x18002c736  lea     r9, [rbp+57h+var_7F]; bool *
0x18002c73a  xor     r8d, r8d; HKEY
0x18002c73d  lea     rdx, [rbp+57h+var_80]; bool *
0x18002c741  xor     ecx, ecx; HKEY
0x18002c743  call    ?QueryCtaAutoUpdatesEnabled@@YAJPEAUHKEY__@@PEA_N01@Z; QueryCtaAutoUpdatesEnabled(HKEY__ *,bool *,HKEY__ *,bool *)
0x18002c748  test    eax, eax
0x18002c74a  js      loc_18002C922
0x18002c750  cmp     [rbp+57h+var_80], 0
0x18002c754  jz      short loc_18002C778
0x18002c756  cmp     r14d, 1
0x18002c75a  jb      short loc_18002C778
0x18002c75c  xor     r9d, r9d
0x18002c75f  lea     r8d, [r9+7]
0x18002c763  lea     rdx, [rbp+57h+iid]
0x18002c767  mov     rcx, [rbx+18h]
0x18002c76b  call    ?RefreshContainer@ContainerManager@@QEAAJAEBU_GUID@@W4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::RefreshContainer(_GUID const &,DSM_REFRESH_TYPE,ushort const *)
0x18002c770  test    eax, eax
0x18002c772  js      loc_18002C922
0x18002c778  cmp     [rbp+57h+var_7F], 0
0x18002c77c  jz      loc_18002C922
0x18002c782  test    r15b, r15b
0x18002c785  jz      loc_18002C922
0x18002c78b  test    r12d, r12d
0x18002c78e  jnz     short loc_18002C799
0x18002c790  cmp     esi, 1
0x18002c793  jb      loc_18002C922
0x18002c799  xor     r9d, r9d
0x18002c79c  lea     r8d, [r9+8]
0x18002c7a0  lea     rdx, [rbp+57h+iid]
0x18002c7a4  mov     rcx, [rbx+18h]
0x18002c7a8  call    ?RefreshContainer@ContainerManager@@QEAAJAEBU_GUID@@W4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::RefreshContainer(_GUID const &,DSM_REFRESH_TYPE,ushort const *)
0x18002c7ad  jmp     loc_18002C922
0x18002c7b2  mov     esi, 100h
0x18002c7b7  lea     r12, WPP_GLOBAL_Control
0x18002c7be  test    r15b, r15b
0x18002c7c1  jz      loc_18002C864
0x18002c7c7  mov     edx, cs:_tls_index
0x18002c7cd  mov     rax, gs:58h
0x18002c7d6  mov     ecx, 4
0x18002c7db  mov     rax, [rax+rdx*8]
0x18002c7df  mov     eax, [rcx+rax]
0x18002c7e2  cmp     cs:dword_18005A520, eax
0x18002c7e8  jg      loc_18002C9AF
0x18002c7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7f5  cmp     rcx, r12
0x18002c7f8  jz      short loc_18002C81E
0x18002c7fa  test    [rcx+1Ch], esi
0x18002c7fd  jz      short loc_18002C81E
0x18002c7ff  cmp     byte ptr [rcx+19h], 4
0x18002c803  jb      short loc_18002C81E
0x18002c805  mov     edx, 25h ; '%'
0x18002c80a  lea     r9, [rbp+57h+iid]
0x18002c80e  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c815  mov     rcx, [rcx+10h]
0x18002c819  call    WPP_SF__guid_
0x18002c81e  mov     qword ptr [rsp+0B0h+var_90], 0; int
0x18002c827  lea     r8, unk_18005A528
0x18002c82e  lea     rdx, [rbp+57h+iid]
0x18002c832  mov     rcx, [rbx+18h]; SRWLock
0x18002c836  call    ?PostJobs@ContainerManager@@QEAAJAEBU_GUID@@AEBV?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@W4JobAttributes@@PEBG@Z; ContainerManager::PostJobs(_GUID const &,std::vector<JobType> const &,JobAttributes,ushort const *)
0x18002c83b  mov     ebx, eax
0x18002c83d  test    eax, eax
0x18002c83f  jns     loc_18002C920
0x18002c845  mov     edx, 1DEh; void *
0x18002c84a  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002c851  mov     r9d, ebx; char *
0x18002c854  mov     rcx, [rbp+5Fh]; this
0x18002c858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c85d  mov     eax, ebx
0x18002c85f  jmp     loc_18002C922
0x18002c864  test    edi, edi
0x18002c866  jnz     loc_18002C8F0
0x18002c86c  mov     edx, cs:_tls_index
0x18002c872  mov     rax, gs:58h
0x18002c87b  mov     ecx, 4
0x18002c880  mov     rax, [rax+rdx*8]
0x18002c884  mov     eax, [rcx+rax]
0x18002c887  cmp     cs:dword_18005A540, eax
0x18002c88d  jg      loc_18002C94A
0x18002c893  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c89a  cmp     rcx, r12
0x18002c89d  jz      short loc_18002C8C3
0x18002c89f  test    [rcx+1Ch], esi
0x18002c8a2  jz      short loc_18002C8C3
0x18002c8a4  cmp     byte ptr [rcx+19h], 4
0x18002c8a8  jb      short loc_18002C8C3
0x18002c8aa  mov     edx, 26h ; '&'
0x18002c8af  lea     r9, [rbp+57h+iid]
0x18002c8b3  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c8ba  mov     rcx, [rcx+10h]
0x18002c8be  call    WPP_SF__guid_
0x18002c8c3  mov     qword ptr [rsp+0B0h+var_90], 0; __int64
0x18002c8cc  lea     r8, unk_18005A548
0x18002c8d3  lea     rdx, [rbp+57h+iid]
0x18002c8d7  mov     rcx, [rbx+18h]; SRWLock
0x18002c8db  call    ?PostJobs@ContainerManager@@QEAAJAEBU_GUID@@AEBV?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@W4JobAttributes@@PEBG@Z; ContainerManager::PostJobs(_GUID const &,std::vector<JobType> const &,JobAttributes,ushort const *)
0x18002c8e0  mov     ebx, eax
0x18002c8e2  test    eax, eax
0x18002c8e4  jns     short loc_18002C920
0x18002c8e6  mov     edx, 1F0h
0x18002c8eb  jmp     loc_18002C84A
0x18002c8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8f7  cmp     rcx, r12
0x18002c8fa  jz      short loc_18002C920
0x18002c8fc  test    [rcx+1Ch], esi
0x18002c8ff  jz      short loc_18002C920
0x18002c901  cmp     byte ptr [rcx+19h], 4
0x18002c905  jb      short loc_18002C920
0x18002c907  mov     edx, 27h ; '''
0x18002c90c  lea     r9, [rbp+57h+iid]
0x18002c910  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c917  mov     rcx, [rcx+10h]
0x18002c91b  call    WPP_SF__guid_
0x18002c920  xor     eax, eax
0x18002c922  mov     rcx, [rbp+57h+var_30]
0x18002c926  xor     rcx, rsp; StackCookie
0x18002c929  call    __security_check_cookie
0x18002c92e  lea     r11, [rsp+0B0h+var_20]
0x18002c936  mov     rbx, [r11+40h]
0x18002c93a  mov     rsi, [r11+48h]
0x18002c93e  mov     rsp, r11
0x18002c941  pop     r15
0x18002c943  pop     r14
0x18002c945  pop     r12
0x18002c947  pop     rdi
0x18002c948  pop     rbp
0x18002c949  retn
0x18002c94a  lea     rcx, dword_18005A540
0x18002c951  call    _Init_thread_header
0x18002c956  cmp     cs:dword_18005A540, 0FFFFFFFFh
0x18002c95d  jnz     loc_18002C893
0x18002c963  mov     dword ptr [rbp+57h+var_70], 0
0x18002c96a  mov     dword ptr [rbp+57h+var_70+4], 5
0x18002c971  lea     rax, [rbp+57h+var_70]
0x18002c975  mov     qword ptr [rbp+57h+var_50], rax
0x18002c979  lea     rax, [rbp+57h+var_68]
0x18002c97d  mov     qword ptr [rbp+57h+var_50+8], rax
0x18002c981  lea     rdx, [rbp+57h+var_50]
0x18002c985  lea     rcx, unk_18005A548
0x18002c98c  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x18002c991  lea     rcx, _EventScan__OnContainerConfigReq____45____dynamic_atexit_destructor_for__jobs__; void (__cdecl *)()
0x18002c998  call    atexit
0x18002c99d  nop
0x18002c99e  lea     rcx, dword_18005A540
0x18002c9a5  call    _Init_thread_footer
0x18002c9aa  jmp     loc_18002C893
0x18002c9af  lea     rcx, dword_18005A520
0x18002c9b6  call    _Init_thread_header
0x18002c9bb  cmp     cs:dword_18005A520, 0FFFFFFFFh
0x18002c9c2  jnz     loc_18002C7EE
0x18002c9c8  movdqa  xmm0, cs:__xmm@00000005000000030000000200000000
0x18002c9d0  movdqu  [rbp+57h+var_50], xmm0
0x18002c9d5  mov     [rbp+57h+var_40], 4
0x18002c9dc  lea     rax, [rbp+57h+var_50]
0x18002c9e0  mov     [rbp+57h+var_70], rax
0x18002c9e4  lea     rax, [rbp+57h+var_3C]
0x18002c9e8  mov     [rbp+57h+var_68], rax
0x18002c9ec  lea     rdx, [rbp+57h+var_70]
0x18002c9f0  lea     rcx, unk_18005A528
0x18002c9f7  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x18002c9fc  lea     rcx, _EventScan__OnContainerConfigReq____34____dynamic_atexit_destructor_for__jobs__; void (__cdecl *)()
0x18002ca03  call    atexit
0x18002ca08  nop
0x18002ca09  lea     rcx, dword_18005A520
0x18002ca10  call    _Init_thread_footer
0x18002ca15  jmp     loc_18002C7EE
```
