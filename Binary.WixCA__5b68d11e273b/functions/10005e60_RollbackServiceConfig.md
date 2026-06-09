# RollbackServiceConfig

- ea: `0x10005e60`
- end: `0x10006208`
- name: `RollbackServiceConfig`
- size: `936`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1000530d`
- `0x1000570f`
- `0x10005e60`
- `0x1000a952`
- `0x1000ad15`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e662`
- `0x1000ee5c`
- `0x1000ef44`
- `0x1000efcc`
- `0x1000f6f2`
- `0x1000f8ce`
- `0x1000f9cc`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x10006104`
- `ADVAPI32!CloseServiceHandle` at `0x1000616c`
- `ADVAPI32!CloseServiceHandle` at `0x1000617a`
- `ADVAPI32!CloseServiceHandle` at `0x10006104`
- `ADVAPI32!CloseServiceHandle` at `0x1000616c`
- `ADVAPI32!CloseServiceHandle` at `0x1000617a`
- `ADVAPI32!OpenSCManagerW` at `0x10005ebb`
- `ADVAPI32!OpenSCManagerW` at `0x10005ebb`
- `KERNEL32!GetLastError` at `0x10005ec8`
- `KERNEL32!GetLastError` at `0x10005ec8`
- `KERNEL32!LocalFree` at `0x10006161`
- `KERNEL32!LocalFree` at `0x10006161`
- `KERNEL32!FormatMessageW` at `0x10005ef1`
- `KERNEL32!FormatMessageW` at `0x10005ef1`

## string_xrefs

- `0x10005f8c`: `Failed to read encoding key from CustomActionData.`
- `0x10005fad`: `Failed to open rollback CustomAction script.`
- `0x10006139`: `Failed to get service: %ls`
- `0x10005f1c`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\serviceconfig.cpp`
- `0x1000612c`: `Failed to configure service: %ls`
- `0x10005e6b`: `RollbackServiceConfig`
- `0x10005ead`: `Failed to initialize 'RollbackServiceConfig'.`
- `0x10005fc9`: `Failed to read rollback script into CustomAction data.`
- `0x100060a2`: `Reconfiguring Service: %ls`

## pseudocode

```c
int __stdcall RollbackServiceConfig(MSIHANDLE hInstall)
{
  int v1; // edi
  SC_HANDLE v2; // ebx
  int v3; // esi
  int LastError; // eax
  int v5; // eax
  _WORD *v6; // eax
  int v7; // eax
  LPVOID lpMem; // [esp+Ch] [ebp-3Ch] BYREF
  int v10; // [esp+10h] [ebp-38h] BYREF
  int v11; // [esp+14h] [ebp-34h] BYREF
  int v12; // [esp+18h] [ebp-30h] BYREF
  int v13; // [esp+1Ch] [ebp-2Ch] BYREF
  int v14; // [esp+20h] [ebp-28h] BYREF
  int v15; // [esp+24h] [ebp-24h] BYREF
  int v16; // [esp+28h] [ebp-20h] BYREF
  SC_HANDLE hSCManager; // [esp+2Ch] [ebp-1Ch]
  WCHAR Buffer[2]; // [esp+30h] [ebp-18h] BYREF
  SC_HANDLE hSCObject; // [esp+34h] [ebp-14h] BYREF
  int v20; // [esp+38h] [ebp-10h] BYREF
  DWORD pcchValueBuf; // [esp+3Ch] [ebp-Ch] BYREF
  LPCWSTR lpServiceName; // [esp+40h] [ebp-8h] BYREF
  wchar_t SubStr[2]; // [esp+44h] [ebp-4h] BYREF

  v1 = 0;
  v2 = 0;
  pcchValueBuf = 0;
  *(_DWORD *)SubStr = 0;
  v20 = 0;
  lpMem = 0;
  lpServiceName = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v11 = 0;
  v10 = 0;
  *(_DWORD *)Buffer = 0;
  hSCManager = 0;
  hSCObject = 0;
  v3 = sub_1000D51F(hInstall, (int)"RollbackServiceConfig");
  if ( v3 >= 0 )
  {
    hSCManager = OpenSCManagerW(0, 0, 1u);
    if ( hSCManager )
    {
      v3 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
      if ( v3 >= 0 )
      {
        sub_1000D9AB(0, "CustomActionData: %ls");
        *(_DWORD *)SubStr = pcchValueBuf;
        v5 = sub_1000EFCC((wchar_t)SubStr, (int)&v20);
        v3 = v5;
        if ( v20 )
        {
          if ( v5 >= 0 )
          {
            v3 = sub_1000F8CE(1, 1, 0, v20, &lpMem);
            if ( v3 >= 0 )
            {
              v3 = sub_1000F9CC(lpMem, &pcchValueBuf);
              if ( v3 >= 0 )
              {
                v6 = (_WORD *)pcchValueBuf;
                *(_DWORD *)SubStr = pcchValueBuf;
                while ( v6 && *v6 )
                {
                  v3 = sub_1000EFCC((wchar_t)SubStr, (int)&lpServiceName);
                  if ( v3 < 0
                    || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v12), v3 < 0)
                    || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v13), v3 < 0)
                    || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v14), v3 < 0)
                    || (v3 = sub_1000EF44((wchar_t)SubStr, (int)&v11), v3 < 0)
                    || (v3 = sub_1000EF44((wchar_t)SubStr, (int)&v10), v3 < 0)
                    || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v15), v3 < 0)
                    || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v16), v3 < 0) )
                  {
                    sub_1000DA66(v3, "failed to process CustomActionData");
                    break;
                  }
                  sub_1000D9AB(1, "Reconfiguring Service: %ls");
                  v7 = sub_1000570F(hSCManager, lpServiceName, 0x12u, (int)&hSCObject);
                  v3 = v7;
                  if ( v7 < 0 )
                  {
                    sub_1000DA66(v7, "Failed to get service: %ls");
                    v2 = hSCObject;
                    break;
                  }
                  v2 = hSCObject;
                  v3 = sub_1000530D(
                         (int)hSCManager,
                         hSCObject,
                         (int)lpServiceName,
                         v10,
                         (const WCHAR *)v12,
                         (const WCHAR *)v13,
                         (const WCHAR *)v14,
                         v11,
                         v16,
                         v15);
                  if ( v3 < 0 )
                  {
                    sub_1000DA66(v3, "Failed to configure service: %ls");
                    break;
                  }
                  v3 = sub_1000EE5C(1000, 0);
                  if ( v3 < 0 )
                  {
                    sub_1000DA66(v3, "failed to send progress message");
                    break;
                  }
                  CloseServiceHandle(v2);
                  v6 = *(_WORD **)SubStr;
                  v2 = 0;
                  hSCObject = 0;
                  v11 = 0;
                  v10 = 0;
                }
              }
              else
              {
                sub_1000DA66(v3, "Failed to read rollback script into CustomAction data.");
              }
            }
            else
            {
              sub_1000DA66(v3, "Failed to open rollback CustomAction script.");
            }
          }
          else
          {
            sub_1000DA66(v5, "Failed to read encoding key from CustomActionData.");
          }
        }
        else
        {
          v3 = -2147418113;
          sub_1000DA66(-2147418113, "Failed due to unexpected CustomActionData passed.");
        }
      }
      else
      {
        sub_1000DA66(v3, "failed to get CustomActionData");
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      else
        v3 = LastError;
      FormatMessageW(0x1300u, 0, LastError, 0x400u, Buffer, 0, 0);
      if ( v3 >= 0 )
      {
        v3 = -2147467261;
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\serviceconfig.cpp", 480, -2147467261);
        sub_1000DA66(-2147467261, "Getting handle to SCM reported success, but no handle was returned.");
      }
      else
      {
        sub_1000DA66(v3, "Failed to get handle to SCM. Error: %ls");
      }
    }
  }
  else
  {
    sub_1000DA66(v3, "Failed to initialize 'RollbackServiceConfig'.");
  }
  if ( *(_DWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  if ( v2 )
    CloseServiceHandle(v2);
  if ( hSCManager )
    CloseServiceHandle(hSCManager);
  sub_1000F6F2(lpMem, 1);
  if ( v16 )
    sub_1000A952(v16);
  if ( v15 )
    sub_1000A952(v15);
  if ( v14 )
    sub_1000A952(v14);
  if ( v13 )
    sub_1000A952(v13);
  if ( v12 )
    sub_1000A952(v12);
  if ( lpServiceName )
    sub_1000A952(lpServiceName);
  if ( v20 )
    sub_1000A952(v20);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10005e60  push    ebp
0x10005e61  mov     ebp, esp
0x10005e63  sub     esp, 3Ch
0x10005e66  push    ebx
0x10005e67  push    esi
0x10005e68  push    edi
0x10005e69  xor     edi, edi
0x10005e6b  push    offset aRollbackservic_0; "RollbackServiceConfig"
0x10005e70  push    [ebp+hInstall]; hInstall
0x10005e73  mov     ebx, edi
0x10005e75  mov     [ebp+pcchValueBuf], edi
0x10005e78  mov     dword ptr [ebp+SubStr], edi
0x10005e7b  mov     [ebp+var_10], edi
0x10005e7e  mov     [ebp+lpMem], edi
0x10005e81  mov     [ebp+lpServiceName], edi
0x10005e84  mov     [ebp+var_30], edi
0x10005e87  mov     [ebp+var_2C], edi
0x10005e8a  mov     [ebp+var_28], edi
0x10005e8d  mov     [ebp+var_24], edi
0x10005e90  mov     [ebp+var_20], edi
0x10005e93  mov     [ebp+var_34], edi
0x10005e96  mov     [ebp+var_38], edi
0x10005e99  mov     dword ptr [ebp+Buffer], edi
0x10005e9c  mov     [ebp+hSCManager], edi
0x10005e9f  mov     [ebp+hSCObject], ebx
0x10005ea2  call    sub_1000D51F
0x10005ea7  mov     esi, eax
0x10005ea9  test    esi, esi
0x10005eab  jns     short loc_10005EB7
0x10005ead  push    offset aFailedToInitia_9; "Failed to initialize 'RollbackServiceCo"...
0x10005eb2  jmp     loc_10006151
0x10005eb7  push    1; dwDesiredAccess
0x10005eb9  push    edi; lpDatabaseName
0x10005eba  push    edi; lpMachineName
0x10005ebb  call    ds:OpenSCManagerW
0x10005ec1  mov     [ebp+hSCManager], eax
0x10005ec4  test    eax, eax
0x10005ec6  jnz     short loc_10005F30
0x10005ec8  call    ds:GetLastError
0x10005ece  test    eax, eax
0x10005ed0  jg      short loc_10005ED6
0x10005ed2  mov     esi, eax
0x10005ed4  jmp     short loc_10005EDF
0x10005ed6  movzx   esi, ax
0x10005ed9  or      esi, 80070000h
0x10005edf  push    edi; Arguments
0x10005ee0  push    edi; nSize
0x10005ee1  lea     ecx, [ebp+Buffer]
0x10005ee4  push    ecx; lpBuffer
0x10005ee5  push    400h; dwLanguageId
0x10005eea  push    eax; dwMessageId
0x10005eeb  push    edi; lpSource
0x10005eec  push    1300h; dwFlags
0x10005ef1  call    ds:FormatMessageW
0x10005ef7  test    esi, esi
0x10005ef9  jns     short loc_10005F11
0x10005efb  push    dword ptr [ebp+Buffer]
0x10005efe  push    offset aFailedToGetHan_0; "Failed to get handle to SCM. Error: %ls"
0x10005f03  push    esi
0x10005f04  call    sub_1000DA66
0x10005f09  add     esp, 0Ch
0x10005f0c  jmp     loc_10006159
0x10005f11  mov     esi, 80004003h
0x10005f16  push    esi
0x10005f17  push    1E0h
0x10005f1c  push    offset aDAWork1SSrcExt_2; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10005f21  call    nullsub_1
0x10005f26  push    offset aGettingHandleT; "Getting handle to SCM reported success,"...
0x10005f2b  jmp     loc_10006151
0x10005f30  lea     eax, [ebp+pcchValueBuf]
0x10005f33  push    eax; pcchValueBuf
0x10005f34  push    offset aCustomactionda; "CustomActionData"
0x10005f39  call    sub_1000E662
0x10005f3e  mov     esi, eax
0x10005f40  test    esi, esi
0x10005f42  jns     short loc_10005F4E
0x10005f44  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10005f49  jmp     loc_10006151
0x10005f4e  push    [ebp+pcchValueBuf]
0x10005f51  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10005f56  push    edi
0x10005f57  call    sub_1000D9AB
0x10005f5c  mov     eax, [ebp+pcchValueBuf]
0x10005f5f  add     esp, 0Ch
0x10005f62  mov     dword ptr [ebp+SubStr], eax
0x10005f65  lea     eax, [ebp+var_10]
0x10005f68  push    eax; int
0x10005f69  lea     eax, [ebp+SubStr]
0x10005f6c  push    eax; SubStr
0x10005f6d  call    sub_1000EFCC
0x10005f72  mov     esi, eax
0x10005f74  cmp     [ebp+var_10], ebx
0x10005f77  jnz     short loc_10005F88
0x10005f79  mov     esi, 8000FFFFh
0x10005f7e  push    offset aFailedDueToUne; "Failed due to unexpected CustomActionDa"...
0x10005f83  jmp     loc_10006151
0x10005f88  test    esi, esi
0x10005f8a  jns     short loc_10005F96
0x10005f8c  push    offset aFailedToReadEn; "Failed to read encoding key from Custom"...
0x10005f91  jmp     loc_10006151
0x10005f96  lea     eax, [ebp+lpMem]
0x10005f99  push    eax
0x10005f9a  push    [ebp+var_10]
0x10005f9d  push    edi
0x10005f9e  push    1
0x10005fa0  push    1
0x10005fa2  call    sub_1000F8CE
0x10005fa7  mov     esi, eax
0x10005fa9  test    esi, esi
0x10005fab  jns     short loc_10005FB7
0x10005fad  push    offset aFailedToOpenRo; "Failed to open rollback CustomAction sc"...
0x10005fb2  jmp     loc_10006151
0x10005fb7  lea     eax, [ebp+pcchValueBuf]
0x10005fba  push    eax
0x10005fbb  push    [ebp+lpMem]
0x10005fbe  call    sub_1000F9CC
0x10005fc3  mov     esi, eax
0x10005fc5  test    esi, esi
0x10005fc7  jns     short loc_10005FD3
0x10005fc9  push    offset aFailedToReadRo; "Failed to read rollback script into Cus"...
0x10005fce  jmp     loc_10006151
0x10005fd3  mov     eax, [ebp+pcchValueBuf]
0x10005fd6  mov     dword ptr [ebp+SubStr], eax
0x10005fd9  jmp     loc_10006118
0x10005fde  cmp     [eax], di
0x10005fe1  jz      loc_10006159
0x10005fe7  lea     eax, [ebp+lpServiceName]
0x10005fea  push    eax; int
0x10005feb  lea     eax, [ebp+SubStr]
0x10005fee  push    eax; SubStr
0x10005fef  call    sub_1000EFCC
0x10005ff4  mov     esi, eax
0x10005ff6  test    esi, esi
0x10005ff8  js      loc_1000614C
0x10005ffe  lea     eax, [ebp+var_30]
0x10006001  push    eax; int
0x10006002  lea     eax, [ebp+SubStr]
0x10006005  push    eax; SubStr
0x10006006  call    sub_1000EFCC
0x1000600b  mov     esi, eax
0x1000600d  test    esi, esi
0x1000600f  js      loc_1000614C
0x10006015  lea     eax, [ebp+var_2C]
0x10006018  push    eax; int
0x10006019  lea     eax, [ebp+SubStr]
0x1000601c  push    eax; SubStr
0x1000601d  call    sub_1000EFCC
0x10006022  mov     esi, eax
0x10006024  test    esi, esi
0x10006026  js      loc_1000614C
0x1000602c  lea     eax, [ebp+var_28]
0x1000602f  push    eax; int
0x10006030  lea     eax, [ebp+SubStr]
0x10006033  push    eax; SubStr
0x10006034  call    sub_1000EFCC
0x10006039  mov     esi, eax
0x1000603b  test    esi, esi
0x1000603d  js      loc_1000614C
0x10006043  lea     eax, [ebp+var_34]
0x10006046  push    eax; int
0x10006047  lea     eax, [ebp+SubStr]
0x1000604a  push    eax; SubStr
0x1000604b  call    sub_1000EF44
0x10006050  mov     esi, eax
0x10006052  test    esi, esi
0x10006054  js      loc_1000614C
0x1000605a  lea     eax, [ebp+var_38]
0x1000605d  push    eax; int
0x1000605e  lea     eax, [ebp+SubStr]
0x10006061  push    eax; SubStr
0x10006062  call    sub_1000EF44
0x10006067  mov     esi, eax
0x10006069  test    esi, esi
0x1000606b  js      loc_1000614C
0x10006071  lea     eax, [ebp+var_24]
0x10006074  push    eax; int
0x10006075  lea     eax, [ebp+SubStr]
0x10006078  push    eax; SubStr
0x10006079  call    sub_1000EFCC
0x1000607e  mov     esi, eax
0x10006080  test    esi, esi
0x10006082  js      loc_1000614C
0x10006088  lea     eax, [ebp+var_20]
0x1000608b  push    eax; int
0x1000608c  lea     eax, [ebp+SubStr]
0x1000608f  push    eax; SubStr
0x10006090  call    sub_1000EFCC
0x10006095  mov     esi, eax
0x10006097  test    esi, esi
0x10006099  js      loc_1000614C
0x1000609f  push    [ebp+lpServiceName]
0x100060a2  push    offset aReconfiguringS; "Reconfiguring Service: %ls"
0x100060a7  push    1
0x100060a9  call    sub_1000D9AB
0x100060ae  add     esp, 0Ch
0x100060b1  lea     eax, [ebp+hSCObject]
0x100060b4  push    eax; int
0x100060b5  push    12h; dwDesiredAccess
0x100060b7  push    [ebp+lpServiceName]; lpServiceName
0x100060ba  push    [ebp+hSCManager]; hSCManager
0x100060bd  call    sub_1000570F
0x100060c2  mov     esi, eax
0x100060c4  test    esi, esi
0x100060c6  js      short loc_10006136
0x100060c8  push    [ebp+var_24]
0x100060cb  mov     ebx, [ebp+hSCObject]
0x100060ce  push    [ebp+var_20]
0x100060d1  push    [ebp+var_34]
0x100060d4  push    [ebp+var_28]
0x100060d7  push    [ebp+var_2C]
0x100060da  push    [ebp+var_30]
0x100060dd  push    [ebp+var_38]
0x100060e0  push    [ebp+lpServiceName]
0x100060e3  push    ebx
0x100060e4  push    [ebp+hSCManager]
0x100060e7  call    sub_1000530D
0x100060ec  mov     esi, eax
0x100060ee  test    esi, esi
0x100060f0  js      short loc_10006129
0x100060f2  push    edi; int
0x100060f3  push    3E8h; iValue
0x100060f8  call    sub_1000EE5C
0x100060fd  mov     esi, eax
0x100060ff  test    esi, esi
0x10006101  js      short loc_10006122
0x10006103  push    ebx; hSCObject
0x10006104  call    ds:CloseServiceHandle
0x1000610a  mov     eax, dword ptr [ebp+SubStr]
0x1000610d  mov     ebx, edi
0x1000610f  mov     [ebp+hSCObject], ebx
0x10006112  mov     [ebp+var_34], edi
0x10006115  mov     [ebp+var_38], edi
0x10006118  test    eax, eax
0x1000611a  jnz     loc_10005FDE
0x10006120  jmp     short loc_10006159
0x10006122  push    offset aFailedToSendPr; "failed to send progress message"
0x10006127  jmp     short loc_10006151
0x10006129  push    [ebp+lpServiceName]
0x1000612c  push    offset aFailedToConfig; "Failed to configure service: %ls"
0x10006131  jmp     loc_10005F03
0x10006136  push    [ebp+lpServiceName]
0x10006139  push    offset aFailedToGetSer_0; "Failed to get service: %ls"
0x1000613e  push    esi
0x1000613f  call    sub_1000DA66
0x10006144  mov     ebx, [ebp+hSCObject]
0x10006147  add     esp, 0Ch
0x1000614a  jmp     short loc_10006159
0x1000614c  push    offset aFailedToProces; "failed to process CustomActionData"
0x10006151  push    esi
0x10006152  call    sub_1000DA66
0x10006157  pop     ecx
0x10006158  pop     ecx
0x10006159  cmp     dword ptr [ebp+Buffer], edi
0x1000615c  jz      short loc_10006167
0x1000615e  push    dword ptr [ebp+Buffer]; hMem
0x10006161  call    ds:LocalFree
0x10006167  test    ebx, ebx
0x10006169  jz      short loc_10006172
0x1000616b  push    ebx; hSCObject
0x1000616c  call    ds:CloseServiceHandle
0x10006172  mov     eax, [ebp+hSCManager]
0x10006175  test    eax, eax
0x10006177  jz      short loc_10006180
0x10006179  push    eax; hSCObject
0x1000617a  call    ds:CloseServiceHandle
0x10006180  push    1; int
0x10006182  push    [ebp+lpMem]; lpMem
0x10006185  call    sub_1000F6F2
0x1000618a  cmp     [ebp+var_20], edi
0x1000618d  jz      short loc_10006197
0x1000618f  push    [ebp+var_20]
0x10006192  call    sub_1000A952
0x10006197  cmp     [ebp+var_24], edi
0x1000619a  jz      short loc_100061A4
0x1000619c  push    [ebp+var_24]
0x1000619f  call    sub_1000A952
0x100061a4  cmp     [ebp+var_28], edi
0x100061a7  jz      short loc_100061B1
0x100061a9  push    [ebp+var_28]
0x100061ac  call    sub_1000A952
0x100061b1  cmp     [ebp+var_2C], edi
0x100061b4  jz      short loc_100061BE
0x100061b6  push    [ebp+var_2C]
0x100061b9  call    sub_1000A952
0x100061be  cmp     [ebp+var_30], edi
0x100061c1  jz      short loc_100061CB
0x100061c3  push    [ebp+var_30]
0x100061c6  call    sub_1000A952
0x100061cb  cmp     [ebp+lpServiceName], edi
0x100061ce  jz      short loc_100061D8
0x100061d0  push    [ebp+lpServiceName]
0x100061d3  call    sub_1000A952
0x100061d8  cmp     [ebp+var_10], edi
0x100061db  jz      short loc_100061E5
0x100061dd  push    [ebp+var_10]
0x100061e0  call    sub_1000A952
0x100061e5  cmp     [ebp+pcchValueBuf], edi
0x100061e8  jz      short loc_100061F2
0x100061ea  push    [ebp+pcchValueBuf]
0x100061ed  call    sub_1000A952
  ... truncated ...
```
