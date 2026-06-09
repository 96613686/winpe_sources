# SetServiceStartTypeOnline

- ea: `0x1800521a0`
- end: `0x1800523e0`
- name: `SetServiceStartTypeOnline`
- size: `576`
- prototype: `__int64 __fastcall(__int64, WCHAR *, __int64, DWORD, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1800523e8`

## callees

- `0x180012108`
- `0x18005097c`
- `0x1800521a0`
- `0x180052480`
- `0x180052620`
- `0x180052698`
- `0x180052944`
- `0x180052c28`
- `0x180052cc4`
- `0x180052fc8`
- `0x1800530a8`
- `0x180061548`
- `0x180065035`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800522f2`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180052387`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180052387`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005220b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005220b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800522e8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800522e8`

## pseudocode

```c
__int64 __fastcall SetServiceStartTypeOnline(__int64 a1, WCHAR *a2, __int64 a3, DWORD a4, __int64 a5)
{
  WCHAR *v6; // rbx
  const WCHAR *v8; // rdx
  SC_HANDLE v9; // rsi
  DWORD LastError; // eax
  int v11; // edi
  signed int v12; // edi
  _QWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+70h] [rbp-90h] BYREF
  SC_HANDLE hSCManager; // [rsp+140h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+148h] [rbp+48h] BYREF

  v14[1] = -2;
  v6 = a2;
  SafeScmHandle::SafeScmHandle((SafeScmHandle *)&hSCManager, (unsigned int)a2);
  if ( *((_QWORD *)v6 + 3) < 8u )
    v8 = v6;
  else
    v8 = *(const WCHAR **)v6;
  v9 = OpenServiceW(hSCManager, v8, 3u);
  v14[0] = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == 1060 )
      goto LABEL_26;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)v6 + 3) >= 8u )
          v6 = *(WCHAR **)v6;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids,
          (_DWORD)v6,
          LastError);
      }
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v11);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  QueryServiceStartType(v9);
  if ( (unsigned __int8)IsOkayToChangeServiceStart(v6) )
  {
    if ( !ChangeServiceConfigW(v9, 0xFFFFFFFF, a4, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v12 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)v6 + 3) >= 8u )
          v6 = *(WCHAR **)v6;
        WPP_SF_SDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids,
          (_DWORD)v6,
          a4,
          v12);
      }
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v12);
      throw (HResultException *)pExceptionObject;
    }
    TryOpenServiceKey(&hKey, a1, v6, 1);
    if ( hKey )
      RegFlushKey(hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    StartOrStopServiceOnline(v6, a4, a5);
  }
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v14);
  return wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hSCManager);
}

```

## disassembly

```asm
0x1800521a0  mov     rax, rsp
0x1800521a3  push    rbp
0x1800521a4  push    rsi
0x1800521a5  push    rdi
0x1800521a6  push    r12
0x1800521a8  push    r13
0x1800521aa  push    r14
0x1800521ac  push    r15
0x1800521ae  lea     rbp, [rsp-60h]
0x1800521b3  sub     rsp, 160h
0x1800521ba  mov     [rsp+190h+var_128], 0FFFFFFFFFFFFFFFEh
0x1800521c3  mov     [rax+18h], rbx
0x1800521c7  mov     rax, cs:__security_cookie
0x1800521ce  xor     rax, rsp
0x1800521d1  mov     [rbp+90h+var_40], rax
0x1800521d5  mov     r14d, r9d
0x1800521d8  mov     r13d, r8d
0x1800521db  mov     rbx, rdx
0x1800521de  mov     r15, rcx
0x1800521e1  mov     r12, [rbp+90h+arg_20]
0x1800521e8  lea     rcx, [rbp+90h+hSCManager]; this
0x1800521ec  call    ??0SafeScmHandle@@QEAA@K@Z; SafeScmHandle::SafeScmHandle(ulong)
0x1800521f1  nop
0x1800521f2  cmp     qword ptr [rbx+18h], 8
0x1800521f7  jb      short loc_1800521FE
0x1800521f9  mov     rdx, [rbx]
0x1800521fc  jmp     short loc_180052201
0x1800521fe  mov     rdx, rbx; lpServiceName
0x180052201  mov     r8d, 3; dwDesiredAccess
0x180052207  mov     rcx, [rbp+90h+hSCManager]; hSCManager
0x18005220b  call    cs:__imp_OpenServiceW
0x180052211  mov     rsi, rax
0x180052214  mov     [rsp+190h+var_130], rax
0x180052219  xor     edi, edi
0x18005221b  test    rax, rax
0x18005221e  jnz     short loc_180052296
0x180052220  call    cs:__imp_GetLastError
0x180052226  mov     edi, eax
0x180052228  cmp     eax, 424h
0x18005222d  jz      loc_1800523A5
0x180052233  test    eax, eax
0x180052235  jz      short loc_180052294
0x180052237  lea     rax, WPP_GLOBAL_Control
0x18005223e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052245  cmp     rcx, rax
0x180052248  jz      short loc_180052276
0x18005224a  cmp     byte ptr [rcx+19h], 2
0x18005224e  jb      short loc_180052276
0x180052250  cmp     qword ptr [rbx+18h], 8
0x180052255  jb      short loc_18005225A
0x180052257  mov     rbx, [rbx]
0x18005225a  mov     edx, 0Fh
0x18005225f  mov     dword ptr [rsp+190h+lpBinaryPathName], edi
0x180052263  mov     r9, rbx
0x180052266  lea     r8, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids
0x18005226d  mov     rcx, [rcx+10h]
0x180052271  call    WPP_SF_Sd
0x180052276  mov     edx, edi; int
0x180052278  lea     rcx, [rsp+190h+pExceptionObject]; this
0x18005227d  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180052282  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180052289  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x18005228e  call    _CxxThrowException_0
0x180052294  xor     edi, edi
0x180052296  mov     rdx, rbx
0x180052299  mov     rcx, rsi; hService
0x18005229c  call    QueryServiceStartType
0x1800522a1  mov     r9d, r14d
0x1800522a4  mov     r8d, r13d
0x1800522a7  mov     edx, eax
0x1800522a9  mov     rcx, rbx; String2
0x1800522ac  call    IsOkayToChangeServiceStart
0x1800522b1  test    al, al
0x1800522b3  jz      loc_1800523A5
0x1800522b9  mov     [rsp+190h+lpDisplayName], rdi; lpDisplayName
0x1800522be  mov     [rsp+190h+lpPassword], rdi; lpPassword
0x1800522c3  mov     [rsp+190h+lpServiceStartName], rdi; lpServiceStartName
0x1800522c8  mov     [rsp+190h+lpDependencies], rdi; lpDependencies
0x1800522cd  mov     [rsp+190h+lpdwTagId], rdi; lpdwTagId
0x1800522d2  mov     [rsp+190h+lpLoadOrderGroup], rdi; lpLoadOrderGroup
0x1800522d7  mov     [rsp+190h+lpBinaryPathName], rdi; lpBinaryPathName
0x1800522dc  or      edx, 0FFFFFFFFh; dwServiceType
0x1800522df  mov     r9d, edx; dwErrorControl
0x1800522e2  mov     r8d, r14d; dwStartType
0x1800522e5  mov     rcx, rsi; hService
0x1800522e8  call    cs:__imp_ChangeServiceConfigW
0x1800522ee  test    eax, eax
0x1800522f0  jnz     short loc_180052369
0x1800522f2  call    cs:__imp_GetLastError
0x1800522f8  mov     edi, eax
0x1800522fa  lea     rax, WPP_GLOBAL_Control
0x180052301  mov     rcx, cs:WPP_GLOBAL_Control
0x180052308  cmp     rcx, rax
0x18005230b  jz      short loc_18005233E
0x18005230d  cmp     byte ptr [rcx+19h], 2
0x180052311  jb      short loc_18005233E
0x180052313  cmp     qword ptr [rbx+18h], 8
0x180052318  jb      short loc_18005231D
0x18005231a  mov     rbx, [rbx]
0x18005231d  mov     edx, 10h
0x180052322  mov     dword ptr [rsp+190h+lpLoadOrderGroup], edi
0x180052326  mov     dword ptr [rsp+190h+lpBinaryPathName], r14d
0x18005232b  mov     r9, rbx
0x18005232e  lea     r8, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids
0x180052335  mov     rcx, [rcx+10h]
0x180052339  call    WPP_SF_SDD
0x18005233e  test    edi, edi
0x180052340  jle     short loc_18005234B
0x180052342  movzx   edi, di
0x180052345  or      edi, 80070000h
0x18005234b  mov     edx, edi; int
0x18005234d  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180052352  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180052357  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18005235e  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180052363  call    _CxxThrowException_0
0x180052369  mov     r9d, 1
0x18005236f  mov     r8, rbx
0x180052372  mov     rdx, r15
0x180052375  lea     rcx, [rbp+90h+hKey]
0x180052379  call    TryOpenServiceKey
0x18005237e  mov     rcx, [rbp+90h+hKey]; hKey
0x180052382  test    rcx, rcx
0x180052385  jz      short loc_18005238D
0x180052387  call    cs:__imp_RegFlushKey
0x18005238d  lea     rcx, [rbp+90h+hKey]
0x180052391  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052396  mov     r8, r12
0x180052399  mov     edx, r14d
0x18005239c  mov     rcx, rbx
0x18005239f  call    StartOrStopServiceOnline
0x1800523a4  nop
0x1800523a5  lea     rcx, [rsp+190h+var_130]
0x1800523aa  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800523af  nop
0x1800523b0  lea     rcx, [rbp+90h+hSCManager]
0x1800523b4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800523b9  mov     rcx, [rbp+90h+var_40]
0x1800523bd  xor     rcx, rsp; StackCookie
0x1800523c0  call    __security_check_cookie
0x1800523c5  mov     rbx, [rsp+190h+arg_10]
0x1800523cd  add     rsp, 160h
0x1800523d4  pop     r15
0x1800523d6  pop     r14
0x1800523d8  pop     r13
0x1800523da  pop     r12
0x1800523dc  pop     rdi
0x1800523dd  pop     rsi
0x1800523de  pop     rbp
0x1800523df  retn
```
