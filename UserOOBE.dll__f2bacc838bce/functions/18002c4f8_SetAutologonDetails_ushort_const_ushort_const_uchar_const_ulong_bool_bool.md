# SetAutologonDetails(ushort const *,ushort const *,uchar const *,ulong,bool,bool)

- ea: `0x18002c4f8`
- end: `0x18002ca4f`
- name: `?SetAutologonDetails@@YAJPEBG0PEBEK_N2@Z`
- size: `1367`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, bool, bool)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029260`
- `0x180029a78`
- `0x18002a480`

## callees

- `0x180007114`
- `0x180007134`
- `0x180015434`
- `0x18002c45c`
- `0x18002c4f8`
- `0x18002cf68`
- `0x18002d18c`
- `0x18002d5fc`
- `0x180047bd0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ca0b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ca0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c681`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c6c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c681`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c6c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c920`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c976`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c920`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c976`
- `CRYPT32!CryptProtectData` at `0x18002c86e`
- `CRYPT32!CryptProtectData` at `0x18002c86e`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18002c5ff`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x18002c5ff`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x18002c798`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x18002c798`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x18002c598`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x18002c736`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x18002c598`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x18002c736`
- `SspiCli!SspiLocalFree` at `0x18002c8a8`
- `SspiCli!SspiLocalFree` at `0x18002c941`
- `SspiCli!SspiLocalFree` at `0x18002c997`
- `SspiCli!SspiLocalFree` at `0x18002c8a8`
- `SspiCli!SspiLocalFree` at `0x18002c941`
- `SspiCli!SspiLocalFree` at `0x18002c997`

## string_xrefs

- `0x18002c6b6`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18002c673`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18002c5b8`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c623`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c6f9`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c759`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c7b8`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c813`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c87c`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c8f4`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002c9cb`: `shell\oobe\common\lib\autologon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetAutologonDetails(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        bool a5,
        bool a6)
{
  char v10; // bl
  bool v11; // di
  BOOL v12; // r13d
  int v13; // eax
  unsigned int LastError; // edi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  bool v20; // cl
  int v21; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  _BYTE *v24; // rcx
  int v25; // eax
  __int64 cbData; // rdx
  BYTE *pbData; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  BYTE *v30; // rcx
  __int64 v31; // rax
  _BYTE *v32; // rcx
  int v33; // eax
  unsigned int v34; // ebx
  int pdwType; // [rsp+20h] [rbp-60h]
  int pdwTypea; // [rsp+20h] [rbp-60h]
  DWORD pdwTypeb; // [rsp+20h] [rbp-60h]
  PVOID DataBuffer; // [rsp+40h] [rbp-40h] BYREF
  char *v39; // [rsp+48h] [rbp-38h] BYREF
  char v40; // [rsp+50h] [rbp-30h]
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-28h] BYREF
  DATA_BLOB pDataIn; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  char v44; // [rsp+C0h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+C8h] [rbp+48h] BYREF

  v10 = 1;
  v44 = 1;
  v39 = &v44;
  v40 = 1;
  v11 = a1 && *a1 && (a2 || a4 && a3);
  v12 = a2 == 0;
  UnattendLogW(0, L"Setting auto logon with fUseAuthBuffer = %d, fEnableAutologon = %d", a2 == 0, v11);
  if ( v11 )
  {
    v13 = SetPersistedRegistryString(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"AutoAdminLogon",
            L"1");
    LastError = v13;
    if ( v13 > 0 )
      LastError = (unsigned __int16)v13 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)LastError,
        pdwType);
      v40 = 0;
      lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
      return LastError;
    }
    if ( a6 )
    {
      v16 = SetPersistedRegistryBOOL(
              L"Winlogon",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              L"SystemAutoLogon",
              1);
      LastError = v16;
      if ( v16 > 0 )
        LastError = (unsigned __int16)v16 | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)LastError,
          pdwType);
        v40 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
        return LastError;
      }
    }
    else
    {
      LODWORD(DataBuffer) = 0;
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Enabled",
             0x10010u,
             0,
             &DataBuffer,
             &pcbData) )
      {
        pcbData = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"Enabled",
          0x20010010u,
          0,
          &DataBuffer,
          &pcbData);
      }
      if ( (_DWORD)DataBuffer )
      {
        v17 = SHRegSetBOOL(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                L"ForceAutoLogon",
                1);
        LastError = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
            (const char *)(unsigned int)v17,
            pdwType);
          v40 = 0;
          lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
          return LastError;
        }
      }
    }
    v18 = SetPersistedRegistryString(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"DefaultUserName",
            a1);
    LastError = v18;
    if ( v18 > 0 )
      LastError = (unsigned __int16)v18 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)LastError,
        pdwType);
      v40 = 0;
      lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
      return LastError;
    }
    v19 = SetPersistedRegistryDWORD(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"IsConnectedAutoLogon",
            a5);
    LastError = v19;
    if ( v19 > 0 )
      LastError = (unsigned __int16)v19 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)LastError,
        pdwType);
      v40 = 0;
      lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
      return LastError;
    }
    if ( a2 )
    {
      v33 = SetAutologonPassword(a2);
      v34 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v33,
          pdwType);
        v40 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
        return v34;
      }
    }
    else
    {
      DataBuffer = 0;
      pcbData = 0;
      v21 = _EncryptOrDecryptSspiAuthenticationBuffer(v20, a3, a4, (unsigned __int8 **)&DataBuffer, &pcbData);
      LastError = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v21,
          pdwTypea);
        v40 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
        return LastError;
      }
      pDataIn.cbData = pcbData;
      *(&pDataIn.cbData + 1) = 0;
      pDataIn.pbData = (BYTE *)DataBuffer;
      pDataOut = 0;
      if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x65,
                      (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
                      v22);
        v23 = pcbData;
        v24 = DataBuffer;
        if ( pcbData )
        {
          do
          {
            *v24++ = 0;
            --v23;
          }
          while ( v23 );
          v24 = DataBuffer;
        }
LABEL_39:
        SspiLocalFree(v24);
        v40 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
        return LastError;
      }
      pdwTypeb = pDataOut.cbData;
      v25 = SHRegSetBinaryData(
              -2147483646,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              L"ConnectedCredentials",
              pDataOut.pbData);
      LastError = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v25,
          pdwTypeb);
        cbData = pDataOut.cbData;
        pbData = pDataOut.pbData;
        if ( pDataOut.cbData )
        {
          do
          {
            *pbData++ = 0;
            --cbData;
          }
          while ( cbData );
          pbData = pDataOut.pbData;
        }
        LocalFree(pbData);
        v28 = pcbData;
        v24 = DataBuffer;
        if ( pcbData )
        {
          do
          {
            *v24++ = 0;
            --v28;
          }
          while ( v28 );
          v24 = DataBuffer;
        }
        goto LABEL_39;
      }
      v29 = pDataOut.cbData;
      v30 = pDataOut.pbData;
      if ( pDataOut.cbData )
      {
        do
        {
          *v30++ = 0;
          --v29;
        }
        while ( v29 );
        v30 = pDataOut.pbData;
      }
      LocalFree(v30);
      v31 = pcbData;
      v32 = DataBuffer;
      if ( pcbData )
      {
        do
        {
          *v32++ = 0;
          --v31;
        }
        while ( v31 );
        v32 = DataBuffer;
      }
      SspiLocalFree(v32);
    }
    v10 = 0;
    v40 = 0;
    UnattendLogW(0, L"Successfully setting Auto-logon with fUseAuthBuffer = %d", v12);
  }
  else
  {
    v44 = 0;
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoLogonCount");
  UnattendLogW(0, L"Cleaned up the AutoLogon Count value");
  if ( v10 )
  {
    v40 = 0;
    lambda_593abc42667a9590cca80463005afefb_::operator()(&v39);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c4f8  mov     [rsp-38h+arg_10], rbx
0x18002c4fd  push    rbp
0x18002c4fe  push    rsi
0x18002c4ff  push    rdi
0x18002c500  push    r12
0x18002c502  push    r13
0x18002c504  push    r14
0x18002c506  push    r15
0x18002c508  mov     rbp, rsp
0x18002c50b  sub     rsp, 80h
0x18002c512  mov     r15d, r9d
0x18002c515  mov     r12, r8
0x18002c518  mov     rsi, rdx
0x18002c51b  mov     r14, rcx
0x18002c51e  mov     ebx, 1
0x18002c523  mov     [rbp+arg_0], bl
0x18002c526  lea     rax, [rbp+arg_0]
0x18002c52a  mov     [rbp+var_38], rax
0x18002c52e  mov     [rbp+var_30], bl
0x18002c531  xor     eax, eax
0x18002c533  test    rcx, rcx
0x18002c536  jz      short loc_18002C551
0x18002c538  cmp     [rcx], ax
0x18002c53b  jz      short loc_18002C551
0x18002c53d  test    rdx, rdx
0x18002c540  jnz     short loc_18002C54C
0x18002c542  test    r9d, r9d
0x18002c545  jz      short loc_18002C551
0x18002c547  test    r8, r8
0x18002c54a  jz      short loc_18002C551
0x18002c54c  mov     dil, bl
0x18002c54f  jmp     short loc_18002C554
0x18002c551  mov     dil, al
0x18002c554  mov     r13d, eax
0x18002c557  test    rsi, rsi
0x18002c55a  setz    r13b
0x18002c55e  movzx   r9d, dil
0x18002c562  mov     r8d, r13d
0x18002c565  lea     rdx, aSettingAutoLog; "Setting auto logon with fUseAuthBuffer "...
0x18002c56c  xor     ecx, ecx
0x18002c56e  call    UnattendLogW
0x18002c573  test    dil, dil
0x18002c576  jz      loc_18002C9EF
0x18002c57c  lea     r9, a1; "1"
0x18002c583  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x18002c58a  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c591  lea     rcx, aWinlogon; "Winlogon"
0x18002c598  call    cs:__imp_SetPersistedRegistryString
0x18002c59e  mov     edi, eax
0x18002c5a0  test    eax, eax
0x18002c5a2  jle     short loc_18002C5AD
0x18002c5a4  movzx   edi, ax
0x18002c5a7  or      edi, 80070000h
0x18002c5ad  test    edi, edi
0x18002c5af  jns     short loc_18002C5DF
0x18002c5b1  mov     rcx, [rbp+38h]; this
0x18002c5b5  mov     r9d, edi; char *
0x18002c5b8  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c5bf  mov     edx, 48h ; 'H'; void *
0x18002c5c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5c9  nop
0x18002c5ca  mov     [rbp+var_30], 0
0x18002c5ce  lea     rcx, [rbp+var_38]
0x18002c5d2  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c5d7  nop
0x18002c5d8  mov     eax, edi
0x18002c5da  jmp     loc_18002CA34
0x18002c5df  xor     edi, edi
0x18002c5e1  cmp     [rbp+arg_28], dil
0x18002c5e5  jz      short loc_18002C645
0x18002c5e7  mov     r9d, ebx
0x18002c5ea  lea     r8, aSystemautologo; "SystemAutoLogon"
0x18002c5f1  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c5f8  lea     rcx, aWinlogon; "Winlogon"
0x18002c5ff  call    cs:__imp_SetPersistedRegistryBOOL
0x18002c605  mov     edi, eax
0x18002c607  test    eax, eax
0x18002c609  jle     short loc_18002C614
0x18002c60b  movzx   edi, ax
0x18002c60e  or      edi, 80070000h
0x18002c614  test    edi, edi
0x18002c616  jns     loc_18002C71E
0x18002c61c  mov     rcx, [rbp+38h]; this
0x18002c620  mov     r9d, edi; char *
0x18002c623  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c62a  mov     edx, 4Bh ; 'K'; void *
0x18002c62f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c634  nop
0x18002c635  mov     [rbp+var_30], 0
0x18002c639  lea     rcx, [rbp+var_38]
0x18002c63d  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c642  nop
0x18002c643  jmp     short loc_18002C5D8
0x18002c645  mov     dword ptr [rbp+DataBuffer], edi
0x18002c648  mov     [rbp+arg_8], 4
0x18002c64f  lea     rax, [rbp+arg_8]
0x18002c653  mov     [rsp+80h+pcbData], rax; pcbData
0x18002c658  lea     rax, [rbp+DataBuffer]
0x18002c65c  mov     [rsp+80h+pvData], rax; pvData
0x18002c661  mov     [rsp+80h+pdwType], rdi; pdwType
0x18002c666  mov     r9d, 10010h; dwFlags
0x18002c66c  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18002c673  lea     rdx, aOsdataSoftware_0; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18002c67a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002c681  call    cs:__imp_RegGetValueW
0x18002c687  test    eax, eax
0x18002c689  jz      short loc_18002C6CA
0x18002c68b  mov     [rbp+arg_8], 4
0x18002c692  lea     rax, [rbp+arg_8]
0x18002c696  mov     [rsp+80h+pcbData], rax; pcbData
0x18002c69b  lea     rax, [rbp+DataBuffer]
0x18002c69f  mov     [rsp+80h+pvData], rax; pvData
0x18002c6a4  mov     [rsp+80h+pdwType], rdi; int
0x18002c6a9  mov     r9d, 20010010h; dwFlags
0x18002c6af  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18002c6b6  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c6bd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002c6c4  call    cs:__imp_RegGetValueW
0x18002c6ca  cmp     dword ptr [rbp+DataBuffer], edi
0x18002c6cd  jz      short loc_18002C71E
0x18002c6cf  mov     r9d, ebx; int
0x18002c6d2  lea     r8, aForceautologon; "ForceAutoLogon"
0x18002c6d9  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c6e0  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002c6e7  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18002c6ec  mov     edi, eax
0x18002c6ee  test    eax, eax
0x18002c6f0  jns     short loc_18002C71E
0x18002c6f2  mov     rcx, [rbp+38h]; this
0x18002c6f6  mov     r9d, eax; char *
0x18002c6f9  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c700  mov     edx, 4Fh ; 'O'; void *
0x18002c705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c70a  nop
0x18002c70b  mov     [rbp+var_30], 0
0x18002c70f  lea     rcx, [rbp+var_38]
0x18002c713  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c718  nop
0x18002c719  jmp     loc_18002C5D8
0x18002c71e  mov     r9, r14
0x18002c721  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002c728  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c72f  lea     rcx, aWinlogon; "Winlogon"
0x18002c736  call    cs:__imp_SetPersistedRegistryString
0x18002c73c  mov     edi, eax
0x18002c73e  xor     r14d, r14d
0x18002c741  test    eax, eax
0x18002c743  jle     short loc_18002C74E
0x18002c745  movzx   edi, ax
0x18002c748  or      edi, 80070000h
0x18002c74e  test    edi, edi
0x18002c750  jns     short loc_18002C77E
0x18002c752  mov     rcx, [rbp+38h]; this
0x18002c756  mov     r9d, edi; char *
0x18002c759  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c760  mov     edx, 52h ; 'R'; void *
0x18002c765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c76a  nop
0x18002c76b  mov     [rbp+var_30], r14b
0x18002c76f  lea     rcx, [rbp+var_38]
0x18002c773  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c778  nop
0x18002c779  jmp     loc_18002C5D8
0x18002c77e  movzx   r9d, [rbp+arg_20]
0x18002c783  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x18002c78a  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c791  lea     rcx, aWinlogon; "Winlogon"
0x18002c798  call    cs:__imp_SetPersistedRegistryDWORD
0x18002c79e  mov     edi, eax
0x18002c7a0  test    eax, eax
0x18002c7a2  jle     short loc_18002C7AD
0x18002c7a4  movzx   edi, ax
0x18002c7a7  or      edi, 80070000h
0x18002c7ad  test    edi, edi
0x18002c7af  jns     short loc_18002C7DD
0x18002c7b1  mov     rcx, [rbp+38h]; this
0x18002c7b5  mov     r9d, edi; char *
0x18002c7b8  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c7bf  mov     edx, 53h ; 'S'; void *
0x18002c7c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7c9  nop
0x18002c7ca  mov     [rbp+var_30], r14b
0x18002c7ce  lea     rcx, [rbp+var_38]
0x18002c7d2  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c7d7  nop
0x18002c7d8  jmp     loc_18002C5D8
0x18002c7dd  test    rsi, rsi
0x18002c7e0  jnz     loc_18002C9B6
0x18002c7e6  mov     [rbp+DataBuffer], r14
0x18002c7ea  mov     [rbp+arg_8], r14d
0x18002c7ee  lea     rax, [rbp+arg_8]
0x18002c7f2  mov     [rsp+80h+pdwType], rax; int
0x18002c7f7  lea     r9, [rbp+DataBuffer]; unsigned __int8 **
0x18002c7fb  mov     r8d, r15d; unsigned int
0x18002c7fe  mov     rdx, r12; unsigned __int8 *
0x18002c801  call    ?_EncryptOrDecryptSspiAuthenticationBuffer@@YAJ_NPEAEKPEAPEAEPEAK@Z; _EncryptOrDecryptSspiAuthenticationBuffer(bool,uchar *,ulong,uchar * *,ulong *)
0x18002c806  mov     edi, eax
0x18002c808  test    eax, eax
0x18002c80a  jns     short loc_18002C836
0x18002c80c  mov     rcx, [rbp+38h]; this
0x18002c810  mov     r9d, eax; char *
0x18002c813  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c81a  lea     edx, [rsi+5Ch]; void *
0x18002c81d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c822  nop
0x18002c823  mov     [rbp+var_30], r14b
0x18002c827  lea     rcx, [rbp+var_38]
0x18002c82b  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c830  nop
0x18002c831  jmp     loc_18002C5D8
0x18002c836  mov     eax, [rbp+arg_8]
0x18002c839  mov     [rbp+pDataIn.cbData], eax
0x18002c83c  xor     eax, eax
0x18002c83e  mov     dword ptr [rbp+pDataIn+4], eax
0x18002c841  mov     rax, [rbp+DataBuffer]
0x18002c845  mov     [rbp+pDataIn.pbData], rax
0x18002c849  xorps   xmm0, xmm0
0x18002c84c  movups  xmmword ptr [rbp+pDataOut.cbData], xmm0
0x18002c850  lea     rax, [rbp+pDataOut]
0x18002c854  mov     [rsp+80h+pcbData], rax; pDataOut
0x18002c859  mov     dword ptr [rsp+80h+pvData], ebx; dwFlags
0x18002c85d  mov     [rsp+80h+pdwType], r14; pPromptStruct
0x18002c862  xor     r9d, r9d; pvReserved
0x18002c865  xor     r8d, r8d; pOptionalEntropy
0x18002c868  xor     edx, edx; szDataDescr
0x18002c86a  lea     rcx, [rbp+pDataIn]; pDataIn
0x18002c86e  call    cs:__imp_CryptProtectData
0x18002c874  test    eax, eax
0x18002c876  jnz     short loc_18002C8C2
0x18002c878  mov     rcx, [rbp+38h]; this
0x18002c87c  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c883  lea     edx, [rax+65h]; void *
0x18002c886  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c88b  mov     edi, eax
0x18002c88d  mov     edx, [rbp+arg_8]
0x18002c890  mov     rcx, [rbp+DataBuffer]
0x18002c894  test    rdx, rdx
0x18002c897  jz      short loc_18002C8A8
0x18002c899  mov     [rcx], r14b
0x18002c89c  add     rcx, rbx
0x18002c89f  sub     rdx, rbx
0x18002c8a2  jnz     short loc_18002C899
0x18002c8a4  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x18002c8a8  call    cs:__imp_SspiLocalFree
0x18002c8ae  nop
0x18002c8af  mov     [rbp+var_30], r14b
0x18002c8b3  lea     rcx, [rbp+var_38]
0x18002c8b7  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c8bc  nop
0x18002c8bd  jmp     loc_18002C5D8
0x18002c8c2  mov     eax, [rbp+pDataOut.cbData]
0x18002c8c5  mov     dword ptr [rsp+80h+pdwType], eax; int
0x18002c8c9  mov     r9, [rbp+pDataOut.pbData]
0x18002c8cd  lea     r8, aConnectedcrede; "ConnectedCredentials"
0x18002c8d4  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002c8db  mov     rcx, 0FFFFFFFF80000002h
0x18002c8e2  call    SHRegSetBinaryData
0x18002c8e7  mov     edi, eax
0x18002c8e9  test    eax, eax
0x18002c8eb  jns     short loc_18002C95B
0x18002c8ed  mov     rcx, [rbp+38h]; this
0x18002c8f1  mov     r9d, eax; char *
0x18002c8f4  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002c8fb  mov     edx, 6Ch ; 'l'; void *
0x18002c900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c905  mov     edx, [rbp+pDataOut.cbData]
0x18002c908  mov     rcx, [rbp+pDataOut.pbData]
0x18002c90c  test    rdx, rdx
0x18002c90f  jz      short loc_18002C920
0x18002c911  mov     [rcx], r14b
0x18002c914  add     rcx, rbx
0x18002c917  sub     rdx, rbx
0x18002c91a  jnz     short loc_18002C911
0x18002c91c  mov     rcx, [rbp+pDataOut.pbData]; hMem
0x18002c920  call    cs:__imp_LocalFree
0x18002c926  mov     eax, [rbp+arg_8]
0x18002c929  mov     rcx, [rbp+DataBuffer]
0x18002c92d  test    rax, rax
0x18002c930  jz      short loc_18002C941
0x18002c932  mov     [rcx], r14b
0x18002c935  add     rcx, rbx
0x18002c938  sub     rax, rbx
0x18002c93b  jnz     short loc_18002C932
0x18002c93d  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x18002c941  call    cs:__imp_SspiLocalFree
0x18002c947  nop
0x18002c948  mov     [rbp+var_30], r14b
0x18002c94c  lea     rcx, [rbp+var_38]
0x18002c950  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x18002c955  nop
0x18002c956  jmp     loc_18002C5D8
0x18002c95b  mov     eax, [rbp+pDataOut.cbData]
0x18002c95e  mov     rcx, [rbp+pDataOut.pbData]
0x18002c962  test    rax, rax
0x18002c965  jz      short loc_18002C976
0x18002c967  mov     [rcx], r14b
0x18002c96a  add     rcx, rbx
0x18002c96d  sub     rax, rbx
0x18002c970  jnz     short loc_18002C967
0x18002c972  mov     rcx, [rbp+pDataOut.pbData]; hMem
  ... truncated ...
```
