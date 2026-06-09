# CSpCluster::_GetDriveLetterMask(ulong *)

- ea: `0x18004dc5c`
- end: `0x18004dfba`
- name: `?_GetDriveLetterMask@CSpCluster@@AEAA?AV_status_t@@PEAK@Z`
- size: `862`
- prototype: `struct _status_t __high(unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180047a08`
- `0x18004be24`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006290`
- `0x18000e43c`
- `0x18000f050`
- `0x18000f3bc`
- `0x18004dc5c`
- `0x18005064c`

## import_xrefs

- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceTypeControl` at `0x18004de11`
- `ext-ms-win-cluster-clusapi-l1-1-2!ClusterResourceTypeControl` at `0x18004de11`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18004ddca`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18004ddca`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18004dda3`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterEnum` at `0x18004dda3`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004de37`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004de6c`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004de37`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x18004de6c`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterCloseEnum` at `0x18004de7a`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterCloseEnum` at `0x18004de7a`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterOpenEnum` at `0x18004dd09`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterOpenEnum` at `0x18004dd09`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterGetEnumCount` at `0x18004dd71`
- `ext-ms-win-cluster-clusapi-l1-1-1!ClusterGetEnumCount` at `0x18004dd71`

## pseudocode

```c
_status_t *__fastcall CSpCluster::_GetDriveLetterMask(__int64 a1, _status_t *a2, char *a3, int a4)
{
  struct _HCLUSENUM *v6; // rsi
  struct _HNODE *v7; // rdi
  struct _HCLUSTER *v8; // rcx
  struct _HCLUSENUM *v9; // rax
  signed int LastError; // ecx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rdx
  int *v14; // rax
  int v15; // r12d
  DWORD v16; // r15d
  DWORD EnumCount; // r13d
  signed int v18; // eax
  int v19; // r8d
  int v20; // r9d
  signed int v21; // ecx
  signed int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int *lpOutBuffer; // [rsp+30h] [rbp-49h]
  int v28; // [rsp+50h] [rbp-29h] BYREF
  int v29; // [rsp+54h] [rbp-25h] BYREF
  char *v30; // [rsp+58h] [rbp-21h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-19h] BYREF
  int OutBuffer; // [rsp+64h] [rbp-15h] BYREF
  const char *v33; // [rsp+68h] [rbp-11h] BYREF
  DWORD dwType; // [rsp+70h] [rbp-9h] BYREF
  WCHAR szName[16]; // [rsp+78h] [rbp-1h] BYREF

  v30 = a3;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v28 = 2468;
    v33 = "CSpCluster::_GetDriveLetterMask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_180304CBB,
      (_DWORD)a3,
      a4,
      (__int64)&v33,
      (__int64)&v28);
  }
  v6 = 0;
  cchName = 16;
  OutBuffer = 0;
  dwType = 0;
  v7 = 0;
  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  wil::EnterCriticalSection(&v33, a1 + 8);
  v8 = *(struct _HCLUSTER **)(a1 + 72);
  if ( !v8 )
  {
    *(_DWORD *)a2 = -2147019846;
    goto LABEL_19;
  }
  v9 = ClusterOpenEnum(v8, 1u);
  v6 = v9;
  if ( !v9 )
  {
    LastError = _status_t::GetLastError(a2);
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_19;
    v28 = LastError;
    lpOutBuffer = &v28;
    v13 = byte_1803046A3;
    v14 = &v29;
    v29 = 2492;
    goto LABEL_8;
  }
  v15 = -1;
  v16 = 0;
  EnumCount = ClusterGetEnumCount(v9);
  if ( EnumCount )
  {
    while ( 1 )
    {
      cchName = 16;
      v18 = ClusterEnum(v6, v16, &dwType, szName, &cchName);
      v21 = v18;
      if ( v18 > 0 )
        v21 = (unsigned __int16)v18 | 0x80070000;
      *(_DWORD *)a2 = v21;
      if ( v21 < 0 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v29 = v21;
          v28 = 2510;
          v30 = "CSpCluster::_GetDriveLetterMask";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v21,
            (unsigned int)byte_180302F91,
            v19,
            v20,
            (__int64)&v30,
            (__int64)&v28,
            (__int64)&v29);
        }
        v7 = 0;
        goto LABEL_19;
      }
      v7 = OpenClusterNode(*(HCLUSTER *)(a1 + 72), szName);
      if ( !v7 )
        break;
      v22 = ClusterResourceTypeControl(
              *(HCLUSTER *)(a1 + 72),
              L"Physical Disk",
              v7,
              0x20001EDu,
              0,
              0,
              &OutBuffer,
              4u,
              0);
      LastError = v22;
      if ( v22 > 0 )
        LastError = (unsigned __int16)v22 | 0x80070000;
      *(_DWORD *)a2 = LastError;
      if ( LastError < 0 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_19;
        v29 = LastError;
        lpOutBuffer = &v29;
        v14 = &v28;
        v28 = 2534;
        v13 = (char *)&unk_180305610;
        goto LABEL_8;
      }
      v15 &= OutBuffer;
      CloseClusterNode(v7);
      if ( ++v16 >= EnumCount )
        goto LABEL_18;
    }
    LastError = _status_t::GetLastError(a2);
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_19;
    v29 = LastError;
    lpOutBuffer = &v29;
    v14 = &v28;
    v28 = 2518;
    v13 = byte_18030104B;
LABEL_8:
    v30 = "CSpCluster::_GetDriveLetterMask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      LastError,
      (_DWORD)v13,
      v11,
      v12,
      (__int64)&v30,
      (__int64)v14,
      (__int64)lpOutBuffer);
    goto LABEL_19;
  }
LABEL_18:
  v7 = 0;
  *(_DWORD *)v30 = v15;
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
    &v33,
    0);
  if ( v7 )
    CloseClusterNode(v7);
  if ( v6 )
    ClusterCloseEnum(v6);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v29 = 2564;
    v30 = "CSpCluster::_GetDriveLetterMask";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)byte_180305945,
      v24,
      v25,
      (__int64)&v30,
      (__int64)&v29);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
  return a2;
}

```

## disassembly

```asm
0x18004dc5c  mov     [rsp-8+arg_18], rbx
0x18004dc61  push    rbp
0x18004dc62  push    rsi
0x18004dc63  push    rdi
0x18004dc64  push    r12
0x18004dc66  push    r13
0x18004dc68  push    r14
0x18004dc6a  push    r15
0x18004dc6c  lea     rbp, [rsp-27h]
0x18004dc71  sub     rsp, 0A0h
0x18004dc78  mov     rax, cs:__security_cookie
0x18004dc7f  xor     rax, rsp
0x18004dc82  mov     [rbp+57h+var_38], rax
0x18004dc86  mov     eax, cs:dword_180397B68
0x18004dc8c  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004dc93  mov     [rbp+57h+var_78], r8
0x18004dc97  mov     rbx, rdx
0x18004dc9a  mov     r14, rcx
0x18004dc9d  cmp     eax, 5
0x18004dca0  jbe     short loc_18004DCCB
0x18004dca2  lea     rax, [rbp+57h+var_80]
0x18004dca6  mov     [rbp+57h+var_80], 9A4h
0x18004dcad  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004dcb2  lea     rdx, byte_180304CBB
0x18004dcb9  lea     rax, [rbp+57h+var_68]
0x18004dcbd  mov     [rbp+57h+var_68], r15
0x18004dcc1  mov     [rsp+0D0h+lpcchName], rax
0x18004dcc6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004dccb  xor     esi, esi
0x18004dccd  mov     [rbp+57h+cchName], 10h
0x18004dcd4  lea     rdx, [r14+8]
0x18004dcd8  mov     [rbp+57h+OutBuffer], esi
0x18004dcdb  lea     rcx, [rbp+57h+var_68]
0x18004dcdf  mov     [rbp+57h+dwType], esi
0x18004dce2  mov     edi, esi
0x18004dce4  mov     [rbx], rsi
0x18004dce7  mov     [rbx+8], sil
0x18004dceb  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004dcf0  mov     rcx, [r14+48h]; hCluster
0x18004dcf4  test    rcx, rcx
0x18004dcf7  jnz     short loc_18004DD04
0x18004dcf9  mov     dword ptr [rbx], 800713BAh
0x18004dcff  jmp     loc_18004DE59
0x18004dd04  mov     edx, 1; dwType
0x18004dd09  call    cs:__imp_ClusterOpenEnum
0x18004dd0f  mov     rsi, rax
0x18004dd12  test    rax, rax
0x18004dd15  jnz     short loc_18004DD6A
0x18004dd17  mov     rcx, rbx; this
0x18004dd1a  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004dd1f  mov     ecx, eax
0x18004dd21  mov     eax, cs:dword_180397B68
0x18004dd27  cmp     eax, 2
0x18004dd2a  jbe     loc_18004DE59
0x18004dd30  lea     rax, [rbp+57h+var_80]
0x18004dd34  mov     [rbp+57h+var_80], ecx
0x18004dd37  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004dd3c  lea     rdx, byte_1803046A3
0x18004dd43  lea     rax, [rbp+57h+var_7C]
0x18004dd47  mov     [rbp+57h+var_7C], 9BCh
0x18004dd4e  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004dd53  lea     rax, [rbp+57h+var_78]
0x18004dd57  mov     [rsp+0D0h+lpcchName], rax
0x18004dd5c  mov     [rbp+57h+var_78], r15
0x18004dd60  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004dd65  jmp     loc_18004DE59
0x18004dd6a  mov     rcx, rsi; hEnum
0x18004dd6d  or      r12d, 0FFFFFFFFh
0x18004dd71  call    cs:__imp_ClusterGetEnumCount
0x18004dd77  xor     r15d, r15d
0x18004dd7a  mov     r13d, eax
0x18004dd7d  test    eax, eax
0x18004dd7f  jz      loc_18004DE49
0x18004dd85  lea     rax, [rbp+57h+cchName]
0x18004dd89  mov     [rbp+57h+cchName], 10h
0x18004dd90  lea     r9, [rbp+57h+szName]; lpszName
0x18004dd94  mov     [rsp+0D0h+lpcchName], rax; lpcchName
0x18004dd99  lea     r8, [rbp+57h+dwType]; lpdwType
0x18004dd9d  mov     edx, r15d; dwIndex
0x18004dda0  mov     rcx, rsi; hEnum
0x18004dda3  call    cs:__imp_ClusterEnum
0x18004dda9  mov     ecx, eax
0x18004ddab  test    eax, eax
0x18004ddad  jle     short loc_18004DDB8
0x18004ddaf  movzx   ecx, ax
0x18004ddb2  or      ecx, 80070000h
0x18004ddb8  mov     [rbx], ecx
0x18004ddba  test    ecx, ecx
0x18004ddbc  js      loc_18004DF63
0x18004ddc2  mov     rcx, [r14+48h]; hCluster
0x18004ddc6  lea     rdx, [rbp+57h+szName]; lpszNodeName
0x18004ddca  call    cs:__imp_OpenClusterNode
0x18004ddd0  xor     ecx, ecx
0x18004ddd2  mov     rdi, rax
0x18004ddd5  test    rax, rax
0x18004ddd8  jz      loc_18004DF20
0x18004ddde  mov     [rsp+0D0h+lpBytesReturned], rcx; lpBytesReturned
0x18004dde3  lea     rax, [rbp+57h+OutBuffer]
0x18004dde7  mov     [rsp+0D0h+nOutBufferSize], 4; nOutBufferSize
0x18004ddef  lea     rdx, szResourceTypeName; "Physical Disk"
0x18004ddf6  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x18004ddfb  mov     r9d, 20001EDh; dwControlCode
0x18004de01  mov     [rsp+0D0h+nInBufferSize], ecx; nInBufferSize
0x18004de05  mov     r8, rdi; hHostNode
0x18004de08  mov     [rsp+0D0h+lpcchName], rcx; lpInBuffer
0x18004de0d  mov     rcx, [r14+48h]; hCluster
0x18004de11  call    cs:__imp_ClusterResourceTypeControl
0x18004de17  mov     ecx, eax
0x18004de19  test    eax, eax
0x18004de1b  jle     short loc_18004DE26
0x18004de1d  movzx   ecx, ax
0x18004de20  or      ecx, 80070000h
0x18004de26  mov     [rbx], ecx
0x18004de28  test    ecx, ecx
0x18004de2a  js      loc_18004DEE7
0x18004de30  and     r12d, [rbp+57h+OutBuffer]
0x18004de34  mov     rcx, rdi; hNode
0x18004de37  call    cs:__imp_CloseClusterNode
0x18004de3d  inc     r15d
0x18004de40  cmp     r15d, r13d
0x18004de43  jb      loc_18004DD85
0x18004de49  mov     rax, [rbp+57h+var_78]
0x18004de4d  xor     edi, edi
0x18004de4f  mov     [rax], r12d
0x18004de52  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004de59  xor     edx, edx
0x18004de5b  lea     rcx, [rbp+57h+var_68]
0x18004de5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18004de64  test    rdi, rdi
0x18004de67  jz      short loc_18004DE72
0x18004de69  mov     rcx, rdi; hNode
0x18004de6c  call    cs:__imp_CloseClusterNode
0x18004de72  test    rsi, rsi
0x18004de75  jz      short loc_18004DE80
0x18004de77  mov     rcx, rsi; hEnum
0x18004de7a  call    cs:__imp_ClusterCloseEnum
0x18004de80  mov     eax, cs:dword_180397B68
0x18004de86  cmp     eax, 5
0x18004de89  jbe     short loc_18004DEB4
0x18004de8b  lea     rax, [rbp+57h+var_7C]
0x18004de8f  mov     [rbp+57h+var_7C], 0A04h
0x18004de96  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004de9b  lea     rdx, byte_180305945
0x18004dea2  lea     rax, [rbp+57h+var_78]
0x18004dea6  mov     [rbp+57h+var_78], r15
0x18004deaa  mov     [rsp+0D0h+lpcchName], rax
0x18004deaf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004deb4  lea     rcx, [rbp+57h+var_68]
0x18004deb8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004debd  mov     rax, rbx
0x18004dec0  mov     rcx, [rbp+57h+var_38]
0x18004dec4  xor     rcx, rsp; StackCookie
0x18004dec7  call    __security_check_cookie
0x18004decc  mov     rbx, [rsp+0D0h+arg_18]
0x18004ded4  add     rsp, 0A0h
0x18004dedb  pop     r15
0x18004dedd  pop     r14
0x18004dedf  pop     r13
0x18004dee1  pop     r12
0x18004dee3  pop     rdi
0x18004dee4  pop     rsi
0x18004dee5  pop     rbp
0x18004dee6  retn
0x18004dee7  mov     eax, cs:dword_180397B68
0x18004deed  cmp     eax, 2
0x18004def0  jbe     loc_18004DE52
0x18004def6  lea     rax, [rbp+57h+var_7C]
0x18004defa  mov     [rbp+57h+var_7C], ecx
0x18004defd  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004df02  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004df09  lea     rax, [rbp+57h+var_80]
0x18004df0d  mov     [rbp+57h+var_80], 9E6h
0x18004df14  lea     rdx, unk_180305610
0x18004df1b  jmp     loc_18004DD4E
0x18004df20  mov     rcx, rbx; this
0x18004df23  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004df28  mov     ecx, eax
0x18004df2a  mov     eax, cs:dword_180397B68
0x18004df30  cmp     eax, 2
0x18004df33  jbe     loc_18004DE52
0x18004df39  lea     rax, [rbp+57h+var_7C]
0x18004df3d  mov     [rbp+57h+var_7C], ecx
0x18004df40  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004df45  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004df4c  lea     rax, [rbp+57h+var_80]
0x18004df50  mov     [rbp+57h+var_80], 9D6h
0x18004df57  lea     rdx, byte_18030104B
0x18004df5e  jmp     loc_18004DD4E
0x18004df63  mov     eax, cs:dword_180397B68
0x18004df69  cmp     eax, 2
0x18004df6c  jbe     short loc_18004DFAC
0x18004df6e  lea     rax, [rbp+57h+var_7C]
0x18004df72  mov     [rbp+57h+var_7C], ecx
0x18004df75  mov     [rsp+0D0h+lpOutBuffer], rax
0x18004df7a  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004df81  lea     rax, [rbp+57h+var_80]
0x18004df85  mov     [rbp+57h+var_80], 9CEh
0x18004df8c  mov     qword ptr [rsp+0D0h+nInBufferSize], rax
0x18004df91  lea     rdx, byte_180302F91
0x18004df98  lea     rax, [rbp+57h+var_78]
0x18004df9c  mov     [rbp+57h+var_78], r15
0x18004dfa0  mov     [rsp+0D0h+lpcchName], rax
0x18004dfa5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004dfaa  jmp     short loc_18004DFB3
0x18004dfac  lea     r15, aCspclusterGetd_1; "CSpCluster::_GetDriveLetterMask"
0x18004dfb3  xor     edi, edi
0x18004dfb5  jmp     loc_18004DE59
```
