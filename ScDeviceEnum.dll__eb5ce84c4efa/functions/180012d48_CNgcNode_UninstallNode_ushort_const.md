# CNgcNode::_UninstallNode(ushort const *)

- ea: `0x180012d48`
- end: `0x1800130a9`
- name: `?_UninstallNode@CNgcNode@@CAJPEBG@Z`
- size: `865`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011e74`
- `0x180012044`

## callees

- `0x180006d40`
- `0x1800071d4`
- `0x18000d8d0`
- `0x180011a18`
- `0x180011c0c`
- `0x180012d48`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013051`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012e9b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012f78`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013030`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001306e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012e9b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012f78`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013030`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001306e`
- `DEVOBJ!DevObjUninstallDevice` at `0x180012f8d`
- `DEVOBJ!DevObjUninstallDevice` at `0x180012f8d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180012dde`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180012dde`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180012ecd`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180012ecd`

## string_xrefs

- `0x180012d71`: `CNgcNode::_UninstallNode`

## pseudocode

```c
__int64 __fastcall CNgcNode::_UninstallNode(const unsigned __int16 *a1)
{
  __int64 DeviceInfoList; // rax
  signed int LastError; // ebx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  signed int v12; // [rsp+30h] [rbp-59h] BYREF
  void **v13; // [rsp+38h] [rbp-51h] BYREF
  __int64 v14; // [rsp+40h] [rbp-49h]
  int v15; // [rsp+48h] [rbp-41h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp-31h] BYREF
  _OWORD v18[3]; // [rsp+70h] [rbp-19h] BYREF
  char v19[32]; // [rsp+A0h] [rbp+17h] BYREF

  v17[0] = v19;
  v12 = 0;
  v17[1] = &v15;
  strcpy(v19, "CNgcNode::_UninstallNode");
  v17[2] = &v12;
  v15 = 0;
  lambda_935cff6244397f5889373b0a2c067785_::operator()(v17);
  v16 = v17;
  v15 = 1;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v14 = DeviceInfoList;
  v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = LastError;
    v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
    if ( v14 != -1 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v13) )
      {
        v5 = GetLastError();
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
        RaiseException(v5, 1u, 0, 0);
        __debugbreak();
      }
LABEL_42:
      v14 = -1;
    }
  }
  else
  {
    memset(v18, 0, sizeof(v18));
    LODWORD(v18[0]) = 48;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v18) )
    {
      if ( (unsigned int)DevObjUninstallDevice(v14, v18, 0, 0) )
      {
        LastError = v12;
        v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
        if ( v14 != -1 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v13) )
          {
            v10 = GetLastError();
            if ( v10 > 0 )
              v10 = (unsigned __int16)v10 | 0x80070000;
            RaiseException(v10, 1u, 0, 0);
            __debugbreak();
          }
          goto LABEL_42;
        }
      }
      else
      {
        LastError = GetLastError();
        WppTraceIndent(v8, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
            (_DWORD)WPP_pszIndent,
            LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v12 = LastError;
        v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
        if ( v14 != -1 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v13) )
          {
            v9 = GetLastError();
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
            RaiseException(v9, 1u, 0, 0);
            __debugbreak();
          }
          goto LABEL_42;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      WppTraceIndent(v6, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v12 = LastError;
      v13 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
      if ( v14 != -1 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v13) )
        {
          v7 = GetLastError();
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          RaiseException(v7, 1u, 0, 0);
          __debugbreak();
        }
        goto LABEL_42;
      }
    }
  }
  WppTraceUnwinder__lambda_935cff6244397f5889373b0a2c067785____::_WppTraceUnwinder__lambda_935cff6244397f5889373b0a2c067785____(&v16);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012d48  mov     [rsp-8+arg_8], rbx
0x180012d4d  mov     [rsp-8+arg_10], r12
0x180012d52  push    rbp
0x180012d53  push    r14
0x180012d55  push    r15
0x180012d57  lea     rbp, [rsp-47h]
0x180012d5c  sub     rsp, 0D0h
0x180012d63  mov     rax, cs:__security_cookie
0x180012d6a  xor     rax, rsp
0x180012d6d  mov     [rbp+57h+var_20], rax
0x180012d71  movups  xmm0, xmmword ptr cs:aCngcnodeUninst_0; "CNgcNode::_UninstallNode"
0x180012d78  lea     rax, [rbp+57h+var_40]
0x180012d7c  mov     rbx, rcx
0x180012d7f  movups  xmm1, xmmword ptr cs:aCngcnodeUninst_0+9; ":_UninstallNode"
0x180012d86  mov     [rbp+57h+var_88], rax
0x180012d8a  lea     rcx, [rbp+57h+var_88]
0x180012d8e  lea     rax, [rbp+57h+var_98]
0x180012d92  mov     [rbp+57h+var_B0], 0
0x180012d99  mov     [rbp+57h+var_80], rax
0x180012d9d  lea     rax, [rbp+57h+var_B0]
0x180012da1  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180012da5  mov     [rbp+57h+var_78], rax
0x180012da9  mov     [rbp+57h+var_98], 0
0x180012db0  movups  xmmword ptr [rbp+57h+var_40+9], xmm1
0x180012db4  call    _lambda_935cff6244397f5889373b0a2c067785___operator__
0x180012db9  lea     rax, [rbp+57h+var_88]
0x180012dbd  mov     [rsp+0E0h+var_C0], 0
0x180012dc6  mov     r15d, 1
0x180012dcc  mov     [rbp+57h+var_90], rax
0x180012dd0  xor     r9d, r9d
0x180012dd3  mov     [rbp+57h+var_98], r15d
0x180012dd7  xor     r8d, r8d
0x180012dda  xor     edx, edx
0x180012ddc  xor     ecx, ecx
0x180012dde  call    cs:__imp_DevObjCreateDeviceInfoList
0x180012de4  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012de8  lea     r12, ??_7?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable'
0x180012def  mov     [rbp+57h+var_A0], rax
0x180012df3  mov     [rbp+57h+var_A8], r12
0x180012df7  cmp     rax, r14
0x180012dfa  jnz     loc_180012EA2
0x180012e00  call    cs:__imp_GetLastError
0x180012e06  lea     edx, [r15+1]
0x180012e0a  mov     ebx, eax
0x180012e0c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e18  lea     rax, WPP_GLOBAL_Control
0x180012e1f  cmp     rcx, rax
0x180012e22  jz      short loc_180012E4F
0x180012e24  test    [rcx+1Ch], r15b
0x180012e28  jz      short loc_180012E4F
0x180012e2a  cmp     byte ptr [rcx+19h], 2
0x180012e2e  jb      short loc_180012E4F
0x180012e30  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012e37  lea     edx, [r15+14h]
0x180012e3b  mov     rcx, [rcx+10h]
0x180012e3f  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x180012e46  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180012e4a  call    WPP_SF_sd
0x180012e4f  test    ebx, ebx
0x180012e51  jle     short loc_180012E5C
0x180012e53  movzx   ebx, bx
0x180012e56  or      ebx, 80070000h
0x180012e5c  mov     [rbp+57h+var_B0], ebx
0x180012e5f  mov     [rbp+57h+var_A8], r12
0x180012e63  cmp     [rbp+57h+var_A0], r14
0x180012e67  jz      loc_180013079
0x180012e6d  lea     rcx, [rbp+57h+var_A8]
0x180012e71  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x180012e76  test    al, al
0x180012e78  jnz     loc_180013075
0x180012e7e  call    cs:__imp_GetLastError
0x180012e84  test    eax, eax
0x180012e86  jle     short loc_180012E90
0x180012e88  movzx   eax, ax
0x180012e8b  or      eax, 80070000h
0x180012e90  xor     r9d, r9d; lpArguments
0x180012e93  xor     r8d, r8d; nNumberOfArguments
0x180012e96  mov     edx, r15d; dwExceptionFlags
0x180012e99  mov     ecx, eax; dwExceptionCode
0x180012e9b  call    cs:__imp_RaiseException
0x180012ea1  int     3; Trap to Debugger
0x180012ea2  xorps   xmm0, xmm0
0x180012ea5  lea     rcx, [rbp+57h+var_70]
0x180012ea9  mov     [rsp+0E0h+var_C0], rcx
0x180012eae  xor     r9d, r9d
0x180012eb1  movups  [rbp+57h+var_70], xmm0
0x180012eb5  mov     rcx, rax
0x180012eb8  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x180012ebf  xor     r8d, r8d
0x180012ec2  mov     rdx, rbx
0x180012ec5  movups  [rbp+57h+var_60], xmm0
0x180012ec9  movups  [rbp+57h+var_50], xmm0
0x180012ecd  call    cs:__imp_DevObjOpenDeviceInfo
0x180012ed3  test    eax, eax
0x180012ed5  jnz     loc_180012F7F
0x180012edb  call    cs:__imp_GetLastError
0x180012ee1  mov     edx, 2
0x180012ee6  mov     ebx, eax
0x180012ee8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012eed  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ef4  lea     rax, WPP_GLOBAL_Control
0x180012efb  cmp     rcx, rax
0x180012efe  jz      short loc_180012F2C
0x180012f00  test    [rcx+1Ch], r15b
0x180012f04  jz      short loc_180012F2C
0x180012f06  cmp     byte ptr [rcx+19h], 2
0x180012f0a  jb      short loc_180012F2C
0x180012f0c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012f13  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x180012f1a  mov     rcx, [rcx+10h]
0x180012f1e  mov     edx, 16h
0x180012f23  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180012f27  call    WPP_SF_sd
0x180012f2c  test    ebx, ebx
0x180012f2e  jle     short loc_180012F39
0x180012f30  movzx   ebx, bx
0x180012f33  or      ebx, 80070000h
0x180012f39  mov     [rbp+57h+var_B0], ebx
0x180012f3c  mov     [rbp+57h+var_A8], r12
0x180012f40  cmp     [rbp+57h+var_A0], r14
0x180012f44  jz      loc_180013079
0x180012f4a  lea     rcx, [rbp+57h+var_A8]
0x180012f4e  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x180012f53  test    al, al
0x180012f55  jnz     loc_180013075
0x180012f5b  call    cs:__imp_GetLastError
0x180012f61  test    eax, eax
0x180012f63  jle     short loc_180012F6D
0x180012f65  movzx   eax, ax
0x180012f68  or      eax, 80070000h
0x180012f6d  xor     r9d, r9d; lpArguments
0x180012f70  xor     r8d, r8d; nNumberOfArguments
0x180012f73  mov     edx, r15d; dwExceptionFlags
0x180012f76  mov     ecx, eax; dwExceptionCode
0x180012f78  call    cs:__imp_RaiseException
0x180012f7e  int     3; Trap to Debugger
0x180012f7f  mov     rcx, [rbp+57h+var_A0]
0x180012f83  lea     rdx, [rbp+57h+var_70]
0x180012f87  xor     r9d, r9d
0x180012f8a  xor     r8d, r8d
0x180012f8d  call    cs:__imp_DevObjUninstallDevice
0x180012f93  test    eax, eax
0x180012f95  jnz     loc_180013037
0x180012f9b  call    cs:__imp_GetLastError
0x180012fa1  mov     edx, 2
0x180012fa6  mov     ebx, eax
0x180012fa8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fb4  lea     rax, WPP_GLOBAL_Control
0x180012fbb  cmp     rcx, rax
0x180012fbe  jz      short loc_180012FEC
0x180012fc0  test    [rcx+1Ch], r15b
0x180012fc4  jz      short loc_180012FEC
0x180012fc6  cmp     byte ptr [rcx+19h], 2
0x180012fca  jb      short loc_180012FEC
0x180012fcc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012fd3  lea     r8, WPP_b74ae1c4b2e3343dbdeda7c30d77c9e0_Traceguids
0x180012fda  mov     rcx, [rcx+10h]
0x180012fde  mov     edx, 17h
0x180012fe3  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180012fe7  call    WPP_SF_sd
0x180012fec  test    ebx, ebx
0x180012fee  jle     short loc_180012FF9
0x180012ff0  movzx   ebx, bx
0x180012ff3  or      ebx, 80070000h
0x180012ff9  mov     [rbp+57h+var_B0], ebx
0x180012ffc  mov     [rbp+57h+var_A8], r12
0x180013000  cmp     [rbp+57h+var_A0], r14
0x180013004  jz      short loc_180013079
0x180013006  lea     rcx, [rbp+57h+var_A8]
0x18001300a  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x18001300f  test    al, al
0x180013011  jnz     short loc_180013075
0x180013013  call    cs:__imp_GetLastError
0x180013019  test    eax, eax
0x18001301b  jle     short loc_180013025
0x18001301d  movzx   eax, ax
0x180013020  or      eax, 80070000h
0x180013025  xor     r9d, r9d; lpArguments
0x180013028  xor     r8d, r8d; nNumberOfArguments
0x18001302b  mov     edx, r15d; dwExceptionFlags
0x18001302e  mov     ecx, eax; dwExceptionCode
0x180013030  call    cs:__imp_RaiseException
0x180013036  int     3; Trap to Debugger
0x180013037  mov     ebx, [rbp+57h+var_B0]
0x18001303a  mov     [rbp+57h+var_A8], r12
0x18001303e  cmp     [rbp+57h+var_A0], r14
0x180013042  jz      short loc_180013079
0x180013044  lea     rcx, [rbp+57h+var_A8]
0x180013048  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x18001304d  test    al, al
0x18001304f  jnz     short loc_180013075
0x180013051  call    cs:__imp_GetLastError
0x180013057  test    eax, eax
0x180013059  jle     short loc_180013063
0x18001305b  movzx   eax, ax
0x18001305e  or      eax, 80070000h
0x180013063  xor     r9d, r9d; lpArguments
0x180013066  xor     r8d, r8d; nNumberOfArguments
0x180013069  mov     edx, r15d; dwExceptionFlags
0x18001306c  mov     ecx, eax; dwExceptionCode
0x18001306e  call    cs:__imp_RaiseException
0x180013074  int     3; Trap to Debugger
0x180013075  mov     [rbp+57h+var_A0], r14
0x180013079  lea     rcx, [rbp+57h+var_90]
0x18001307d  call    WppTraceUnwinder__lambda_935cff6244397f5889373b0a2c067785_______WppTraceUnwinder__lambda_935cff6244397f5889373b0a2c067785____
0x180013082  mov     eax, ebx
0x180013084  mov     rcx, [rbp+57h+var_20]
0x180013088  xor     rcx, rsp; StackCookie
0x18001308b  call    __security_check_cookie
0x180013090  lea     r11, [rsp+0E0h+var_10]
0x180013098  mov     rbx, [r11+28h]
0x18001309c  mov     r12, [r11+30h]
0x1800130a0  mov     rsp, r11
0x1800130a3  pop     r15
0x1800130a5  pop     r14
0x1800130a7  pop     rbp
0x1800130a8  retn
```
