# UpdateMachineSecurityCache(void)

- ea: `0x1800386e0`
- end: `0x1800389b9`
- name: `?UpdateMachineSecurityCache@@YAXXZ`
- size: `729`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180037fa0`

## callees

- `0x180004d91`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18000f7e4`
- `0x1800138e4`
- `0x18002c61c`
- `0x1800386e0`
- `0x1800457e4`
- `0x18004599c`
- `0x180048980`
- `0x180095038`

## import_xrefs

- `msvcrt!free` at `0x18003899d`
- `msvcrt!free` at `0x18003899d`
- `ADVAPI32!GetLengthSid` at `0x1800388ec`
- `ADVAPI32!GetLengthSid` at `0x1800388ec`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800387ef`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800387ef`
- `mqsec!SetFalconKeyValue` at `0x18003890e`
- `mqsec!SetFalconKeyValue` at `0x18003890e`
- `mqsec!MQSec_UpdateLocalMachineSid` at `0x180038922`
- `mqsec!MQSec_UpdateLocalMachineSid` at `0x180038922`

## string_xrefs

- `0x180038907`: `security\MachineAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void UpdateMachineSecurityCache(void)
{
  PSECURITY_DESCRIPTOR v0; // rbx
  DWORD SecurityDescriptorLength; // eax
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // ebx
  PSID v6; // rbx
  int v7; // edi
  __int128 v8; // [rsp+40h] [rbp-39h] BYREF
  PSID pSid; // [rsp+50h] [rbp-29h]
  _BYTE pExceptionObject[32]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v11[8]; // [rsp+78h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp+7h]
  int v13; // [rsp+E0h] [rbp+67h] BYREF
  DWORD LengthSid; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v15; // [rsp+F0h] [rbp+77h] BYREF
  PSID v16; // [rsp+F8h] [rbp+7Fh]

  if ( !CQueueMgr::CanAccessDS() )
  {
    LogMsgHR(-1072824301, (wchar_t *)L"qmds", 0xAu);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, -1072824301);
    throw (bad_hresult *)pExceptionObject;
  }
  CQMDSSecureableObject::CQMDSSecureableObject(v11, 1, &CQueueMgr::m_guidQmQueue);
  v0 = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
  {
    LogMsgHR(-1072824319, (wchar_t *)L"qmds", 0x14u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, -1072824319);
    throw (bad_hresult *)pExceptionObject;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
  v2 = SetMachineSecurityCache(v0, SecurityDescriptorLength);
  v5 = v2;
  if ( v2 < 0 )
  {
    LogMsgHR(v2, (wchar_t *)L"qmds", 0x1Eu);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids, v5);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v5);
    throw (bad_hresult *)pExceptionObject;
  }
  v13 = 5206;
  v8 = 0;
  LOWORD(v8) = 1;
  pSid = 0;
  v6 = 0;
  v16 = 0;
  if ( g_szComputerDnsName && (v7 = ADGetObjectProperties(8, v3, v4, g_szComputerDnsName, 1, &v13, &v8), v7 >= 0)
    || (v7 = ADGetObjectProperties(8, v3, v4, g_szMachineName, 1, &v13, &v8), v7 >= 0) )
  {
    v6 = pSid;
    v16 = pSid;
    LengthSid = GetLengthSid(pSid);
    v15 = 3;
    if ( SetFalconKeyValue(L"security\\MachineAccount", &v15, v6, &LengthSid) )
    {
      v7 = -1072824319;
LABEL_25:
      LogMsgHR(v7, (wchar_t *)L"qmds", 0x28u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids,
          (unsigned int)v7);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
      throw (bad_hresult *)pExceptionObject;
    }
    MQSec_UpdateLocalMachineSid(v6);
  }
  else if ( v7 == -1072824263 )
  {
    v7 = 0;
  }
  if ( v7 < 0 )
    goto LABEL_25;
  free(v6);
  CQMDSSecureableObject::~CQMDSSecureableObject((CQMDSSecureableObject *)v11);
}

```

## disassembly

```asm
0x1800386e0  push    rbp
0x1800386e2  push    rbx
0x1800386e3  push    rsi
0x1800386e4  push    rdi
0x1800386e5  lea     rbp, [rsp-3Fh]
0x1800386ea  sub     rsp, 0B8h
0x1800386f1  call    ?CanAccessDS@CQueueMgr@@SA_NXZ; CQueueMgr::CanAccessDS(void)
0x1800386f6  test    al, al
0x1800386f8  jnz     short loc_18003875F
0x1800386fa  mov     edi, 0Ah
0x1800386ff  mov     r8d, edi; unsigned __int16
0x180038702  lea     rdx, aQmds; "qmds"
0x180038709  mov     ebx, 0C00E0013h
0x18003870e  mov     ecx, ebx; int
0x180038710  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180038715  lea     rax, WPP_GLOBAL_Control
0x18003871c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038723  cmp     rcx, rax
0x180038726  jz      short loc_180038743
0x180038728  lea     esi, [rdi-9]
0x18003872b  test    [rcx+1Ch], sil
0x18003872f  jz      short loc_180038743
0x180038731  mov     edx, edi
0x180038733  lea     r8, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids
0x18003873a  mov     rcx, [rcx+10h]
0x18003873e  call    WPP_SF_
0x180038743  mov     edx, ebx; unsigned int
0x180038745  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180038749  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18003874e  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180038755  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180038759  call    _CxxThrowException_0
0x18003875f  mov     [rsp+0D0h+var_A8], 0
0x180038768  mov     esi, 1
0x18003876d  mov     [rsp+0D0h+var_B0], esi
0x180038771  lea     r8, ?m_guidQmQueue@CQueueMgr@@0U_GUID@@A; _GUID CQueueMgr::m_guidQmQueue
0x180038778  mov     edx, esi
0x18003877a  lea     rcx, [rbp+57h+var_58]
0x18003877e  call    ??0CQMDSSecureableObject@@QEAA@W4AD_OBJECT@@PEBU_GUID@@HHPEB_W@Z; CQMDSSecureableObject::CQMDSSecureableObject(AD_OBJECT,_GUID const *,int,int,wchar_t const *)
0x180038783  nop
0x180038784  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180038788  test    rbx, rbx
0x18003878b  jnz     short loc_1800387EC
0x18003878d  lea     r8d, [rsi+13h]; unsigned __int16
0x180038791  lea     rdx, aQmds; "qmds"
0x180038798  mov     edi, 0C00E0001h
0x18003879d  mov     ecx, edi; int
0x18003879f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800387a4  lea     rax, WPP_GLOBAL_Control
0x1800387ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387b2  cmp     rcx, rax
0x1800387b5  jz      short loc_1800387D0
0x1800387b7  test    [rcx+1Ch], sil
0x1800387bb  jz      short loc_1800387D0
0x1800387bd  lea     edx, [rsi+0Ah]
0x1800387c0  lea     r8, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids
0x1800387c7  mov     rcx, [rcx+10h]
0x1800387cb  call    WPP_SF_
0x1800387d0  mov     edx, edi; unsigned int
0x1800387d2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800387d6  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800387db  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x1800387e2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800387e6  call    _CxxThrowException_0
0x1800387ec  mov     rcx, rbx; pSecurityDescriptor
0x1800387ef  call    cs:__imp_GetSecurityDescriptorLength
0x1800387f5  mov     edx, eax; unsigned int
0x1800387f7  mov     rcx, rbx; void *
0x1800387fa  call    ?SetMachineSecurityCache@@YAJPEBXK@Z; SetMachineSecurityCache(void const *,ulong)
0x1800387ff  mov     ebx, eax
0x180038801  test    eax, eax
0x180038803  jns     short loc_180038866
0x180038805  mov     r8d, 1Eh; unsigned __int16
0x18003880b  lea     rdx, aQmds; "qmds"
0x180038812  mov     ecx, eax; int
0x180038814  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180038819  lea     rax, WPP_GLOBAL_Control
0x180038820  mov     rcx, cs:WPP_GLOBAL_Control
0x180038827  cmp     rcx, rax
0x18003882a  jz      short loc_18003884A
0x18003882c  test    [rcx+1Ch], sil
0x180038830  jz      short loc_18003884A
0x180038832  mov     edx, 0Ch
0x180038837  mov     r9d, ebx
0x18003883a  lea     r8, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids
0x180038841  mov     rcx, [rcx+10h]
0x180038845  call    WPP_SF_d
0x18003884a  mov     edx, ebx; unsigned int
0x18003884c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180038850  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180038855  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x18003885c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180038860  call    _CxxThrowException_0
0x180038866  mov     [rbp+57h+arg_0], 1456h
0x18003886d  xorps   xmm0, xmm0
0x180038870  xor     eax, eax
0x180038872  movups  [rbp+57h+var_90], xmm0
0x180038876  mov     word ptr [rbp+57h+var_90], si
0x18003887a  mov     [rbp+57h+pSid], rax
0x18003887e  xor     ebx, ebx
0x180038880  mov     [rbp+57h+arg_18], rbx
0x180038884  mov     r9, cs:?g_szComputerDnsName@@3V?$AP@_W@@A; AP<wchar_t> g_szComputerDnsName
0x18003888b  test    r9, r9
0x18003888e  jz      short loc_1800388B4
0x180038890  lea     rax, [rbp+57h+var_90]
0x180038894  mov     [rsp+0D0h+var_A0], rax
0x180038899  lea     rax, [rbp+57h+arg_0]
0x18003889d  mov     [rsp+0D0h+var_A8], rax
0x1800388a2  mov     [rsp+0D0h+var_B0], esi
0x1800388a6  lea     ecx, [rbx+8]
0x1800388a9  call    ?ADGetObjectProperties@@YAJW4AD_OBJECT@@PEB_W_N1KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectProperties(AD_OBJECT,wchar_t const *,bool,wchar_t const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x1800388ae  mov     edi, eax
0x1800388b0  test    eax, eax
0x1800388b2  jns     short loc_1800388E1
0x1800388b4  lea     rax, [rbp+57h+var_90]
0x1800388b8  mov     [rsp+0D0h+var_A0], rax
0x1800388bd  lea     rax, [rbp+57h+arg_0]
0x1800388c1  mov     [rsp+0D0h+var_A8], rax
0x1800388c6  mov     [rsp+0D0h+var_B0], esi
0x1800388ca  mov     r9, cs:?g_szMachineName@@3PEA_WEA; wchar_t * g_szMachineName
0x1800388d1  mov     ecx, 8
0x1800388d6  call    ?ADGetObjectProperties@@YAJW4AD_OBJECT@@PEB_W_N1KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectProperties(AD_OBJECT,wchar_t const *,bool,wchar_t const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x1800388db  mov     edi, eax
0x1800388dd  test    eax, eax
0x1800388df  js      short loc_18003892A
0x1800388e1  mov     rbx, [rbp+57h+pSid]
0x1800388e5  mov     [rbp+57h+arg_18], rbx
0x1800388e9  mov     rcx, rbx; pSid
0x1800388ec  call    cs:__imp_GetLengthSid
0x1800388f2  mov     [rbp+57h+arg_8], eax
0x1800388f5  mov     [rbp+57h+arg_10], 3
0x1800388fc  lea     r9, [rbp+57h+arg_8]
0x180038900  mov     r8, rbx
0x180038903  lea     rdx, [rbp+57h+arg_10]
0x180038907  lea     rcx, aSecurityMachin; "security\\MachineAccount"
0x18003890e  call    cs:__imp_?SetFalconKeyValue@@YAJPEB_WPEAKPEBX1@Z; SetFalconKeyValue(wchar_t const *,ulong *,void const *,ulong *)
0x180038914  test    eax, eax
0x180038916  jz      short loc_18003891F
0x180038918  mov     edi, 0C00E0001h
0x18003891d  jmp     short loc_180038939
0x18003891f  mov     rcx, rbx
0x180038922  call    cs:__imp_?MQSec_UpdateLocalMachineSid@@YAXPEAX@Z; MQSec_UpdateLocalMachineSid(void *)
0x180038928  jmp     short loc_180038935
0x18003892a  xor     eax, eax
0x18003892c  cmp     edi, 0C00E0039h
0x180038932  cmovz   edi, eax
0x180038935  test    edi, edi
0x180038937  jns     short loc_18003899A
0x180038939  mov     r8d, 28h ; '('; unsigned __int16
0x18003893f  lea     rdx, aQmds; "qmds"
0x180038946  mov     ecx, edi; int
0x180038948  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003894d  lea     rax, WPP_GLOBAL_Control
0x180038954  mov     rcx, cs:WPP_GLOBAL_Control
0x18003895b  cmp     rcx, rax
0x18003895e  jz      short loc_18003897E
0x180038960  test    [rcx+1Ch], sil
0x180038964  jz      short loc_18003897E
0x180038966  mov     edx, 0Dh
0x18003896b  mov     r9d, edi
0x18003896e  lea     r8, WPP_a89ec2e2b9d9354c8e6aafbcdab2ef85_Traceguids
0x180038975  mov     rcx, [rcx+10h]
0x180038979  call    WPP_SF_d
0x18003897e  mov     edx, edi; unsigned int
0x180038980  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180038984  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180038989  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180038990  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180038994  call    _CxxThrowException_0
0x18003899a  mov     rcx, rbx; Block
0x18003899d  call    cs:__imp_free
0x1800389a3  nop
0x1800389a4  lea     rcx, [rbp+57h+var_58]; this
0x1800389a8  call    ??1CQMDSSecureableObject@@QEAA@XZ; CQMDSSecureableObject::~CQMDSSecureableObject(void)
0x1800389ad  add     rsp, 0B8h
0x1800389b4  pop     rdi
0x1800389b5  pop     rsi
0x1800389b6  pop     rbx
0x1800389b7  pop     rbp
0x1800389b8  retn
```
