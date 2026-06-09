# WsUpdateRegistryToMatchWksta

- ea: `0x18002abe4`
- end: `0x18002aede`
- name: `WsUpdateRegistryToMatchWksta`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18002a810`

## callees

- `0x1800072d8`
- `0x180007400`
- `0x18002abe4`
- `0x18002eb04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002acc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ad14`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002acc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ad14`

## string_xrefs

- `0x18002ad49`: `MaxThreads`
- `0x18002ad7f`: `CacheFileTimeout`
- `0x18002ae38`: `UseLockReadUnlock`
- `0x18002ae20`: `UseRawRead`
- `0x18002ae14`: `UseRawWrite`
- `0x18002ae5c`: `UseWriteRawData`
- `0x18002aead`: `BufFilesDenyWrite`
- `0x18002aea4`: `BufReadOnlyFiles`
- `0x18002ae9b`: `ForceCoreCreateMode`
- `0x18002ae86`: `ReadAheadThroughput`

## pseudocode

```c
LSTATUS __fastcall WsUpdateRegistryToMatchWksta(unsigned int a1, _DWORD *a2, __int64 a3)
{
  LSTATUS result; // eax
  HKEY *v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  const WCHAR *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rsi
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  const wchar_t *v22; // rdx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  HKEY *Data; // [rsp+70h] [rbp+38h] BYREF

  Data = 0;
  result = NetpOpenConfigDataEx(&Data, a2, a3, 0);
  if ( !result )
  {
    v6 = Data;
    if ( a1 > 0x418 )
    {
      result = 1056;
      if ( a1 > 0x420 )
      {
        v29 = a1 - 1057;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( v31 )
            {
              v32 = v31 - 1;
              if ( v32 )
              {
                v33 = v32 - 1;
                if ( v33 )
                {
                  if ( v33 == 1 )
                  {
                    v13 = L"ReadAheadThroughput";
                    goto LABEL_19;
                  }
                  goto LABEL_72;
                }
                v22 = L"Use512ByteMaxTransfer";
              }
              else
              {
                v22 = L"ForceCoreCreateMode";
              }
            }
            else
            {
              v22 = L"BufReadOnlyFiles";
            }
          }
          else
          {
            v22 = L"BufFilesDenyWrite";
          }
        }
        else
        {
          v22 = L"UseEncryption";
        }
      }
      else if ( a1 == 1056 )
      {
        v22 = L"UseWriteRawData";
      }
      else
      {
        v23 = a1 - 1049;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                v27 = v26 - 1;
                if ( v27 )
                {
                  v28 = v27 - 1;
                  if ( v28 )
                  {
                    if ( v28 != 1 )
                      goto LABEL_72;
                    v22 = L"UseRawWrite";
                  }
                  else
                  {
                    v22 = L"UseRawRead";
                  }
                }
                else
                {
                  v22 = L"UtilizeNtCaching";
                }
              }
              else
              {
                v22 = L"UseLockReadUnlock";
              }
            }
            else
            {
              v22 = L"BufNamedPipes";
            }
          }
          else
          {
            v22 = L"UseCloseBehind";
          }
        }
        else
        {
          v22 = L"UseUnlockBehind";
        }
      }
    }
    else
    {
      if ( a1 != 1048 )
      {
        result = 1033;
        if ( a1 <= 0x409 )
        {
          if ( a1 == 1033 )
          {
            v13 = L"MaxThreads";
          }
          else
          {
            v7 = a1 - 502;
            if ( !v7 )
            {
              v14 = qword_18004F010;
              v15 = 0;
              if ( *(_QWORD *)qword_18004F010 )
              {
                do
                {
                  if ( *(_DWORD *)(v14 + 40 * v15 + 28) == 1 )
                  {
                    LODWORD(Data) = **(_DWORD **)(v14 + 40 * v15 + 8);
                    result = RegSetValueExW(*v6, *(LPCWSTR *)(v14 + 40 * v15), 0, 4u, (const BYTE *)&Data, 4u);
                  }
                  else
                  {
                    result = WsSetConfigBool(v6, *(_QWORD *)(v14 + 40 * v15), **(unsigned int **)(v14 + 40 * v15 + 8));
                  }
                  v14 = qword_18004F010;
                  v15 = (unsigned int)(v15 + 1);
                }
                while ( *(_QWORD *)(qword_18004F010 + 40 * v15) );
              }
              goto LABEL_72;
            }
            v8 = v7 - 508;
            if ( v8 )
            {
              v9 = v8 - 1;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( v10 )
                {
                  v11 = v10 - 1;
                  if ( v11 )
                  {
                    v12 = v11 - 5;
                    if ( v12 )
                    {
                      if ( v12 != 5 )
                        goto LABEL_72;
                      v13 = L"SizCharBuf";
                    }
                    else
                    {
                      v13 = L"SessTimeout";
                    }
                  }
                  else
                  {
                    v13 = L"KeepConn";
                  }
                }
                else
                {
                  v13 = L"MaxCollectionCount";
                }
              }
              else
              {
                v13 = L"CollectionTime";
              }
            }
            else
            {
              v13 = L"CharWait";
            }
          }
          goto LABEL_19;
        }
        v16 = a1 - 1041;
        if ( !v16 )
        {
          v13 = L"LockQuota";
          goto LABEL_19;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v13 = L"LockIncrement";
          goto LABEL_19;
        }
        v18 = v17 - 1;
        if ( !v18 )
        {
          v13 = L"LockMaximum";
          goto LABEL_19;
        }
        v19 = v18 - 1;
        if ( !v19 )
        {
          v13 = L"PipeIncrement";
          goto LABEL_19;
        }
        v20 = v19 - 1;
        if ( !v20 )
        {
          v13 = L"PipeMaximum";
          goto LABEL_19;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
          v13 = L"DormantFileLimit";
          goto LABEL_19;
        }
        if ( v21 == 1 )
        {
          v13 = L"CacheFileTimeout";
LABEL_19:
          LODWORD(Data) = *a2;
          result = RegSetValueExW(*v6, v13, 0, 4u, (const BYTE *)&Data, 4u);
        }
LABEL_72:
        if ( v6 )
          return NetpCloseConfigData(v6);
        return result;
      }
      v22 = L"UseOpportunisticLocking";
    }
    result = WsSetConfigBool(Data, v22, (unsigned int)*a2);
    goto LABEL_72;
  }
  return result;
}

```

## disassembly

```asm
0x18002abe4  mov     [rsp-20h+Data], r8
0x18002abe9  push    rbp
0x18002abea  push    rbx
0x18002abeb  push    rsi
0x18002abec  push    rdi
0x18002abed  mov     rbp, rsp
0x18002abf0  sub     rsp, 38h
0x18002abf4  mov     ebx, ecx
0x18002abf6  mov     [rbp+Data], 0
0x18002abfe  lea     rcx, [rbp+Data]
0x18002ac02  xor     r9d, r9d
0x18002ac05  mov     rsi, rdx
0x18002ac08  call    NetpOpenConfigDataEx
0x18002ac0d  test    eax, eax
0x18002ac0f  jnz     loc_18002AED5
0x18002ac15  mov     rdi, [rbp+Data]
0x18002ac19  mov     eax, 418h
0x18002ac1e  cmp     ebx, eax
0x18002ac20  ja      loc_18002ADDF
0x18002ac26  jz      loc_18002ADD3
0x18002ac2c  mov     eax, 409h
0x18002ac31  cmp     ebx, eax
0x18002ac33  ja      loc_18002AD55
0x18002ac39  jz      loc_18002AD49
0x18002ac3f  sub     ebx, 1F6h
0x18002ac45  jz      loc_18002ACCF
0x18002ac4b  sub     ebx, 1FCh
0x18002ac51  jz      short loc_18002AC9D
0x18002ac53  sub     ebx, 1
0x18002ac56  jz      short loc_18002AC94
0x18002ac58  sub     ebx, 1
0x18002ac5b  jz      short loc_18002AC8B
0x18002ac5d  sub     ebx, 1
0x18002ac60  jz      short loc_18002AC82
0x18002ac62  sub     ebx, 5
0x18002ac65  jz      short loc_18002AC79
0x18002ac67  cmp     ebx, 5
0x18002ac6a  jnz     loc_18002AEC8
0x18002ac70  lea     rdx, aSizcharbuf; "SizCharBuf"
0x18002ac77  jmp     short loc_18002ACA4
0x18002ac79  lea     rdx, aSesstimeout; "SessTimeout"
0x18002ac80  jmp     short loc_18002ACA4
0x18002ac82  lea     rdx, aKeepconn; "KeepConn"
0x18002ac89  jmp     short loc_18002ACA4
0x18002ac8b  lea     rdx, aMaxcollectionc; "MaxCollectionCount"
0x18002ac92  jmp     short loc_18002ACA4
0x18002ac94  lea     rdx, aCollectiontime; "CollectionTime"
0x18002ac9b  jmp     short loc_18002ACA4
0x18002ac9d  lea     rdx, aCharwait; "CharWait"
0x18002aca4  mov     eax, [rsi]
0x18002aca6  mov     ebx, 4
0x18002acab  mov     dword ptr [rbp+Data], eax
0x18002acae  mov     r9d, ebx; dwType
0x18002acb1  mov     rcx, [rdi]; hKey
0x18002acb4  lea     rax, [rbp+Data]
0x18002acb8  mov     [rsp+38h+cbData], ebx; cbData
0x18002acbc  xor     r8d, r8d; Reserved
0x18002acbf  mov     [rsp+38h+lpData], rax; lpData
0x18002acc4  call    cs:__imp_RegSetValueExW
0x18002acca  jmp     loc_18002AEC8
0x18002accf  mov     rdx, cs:qword_18004F010
0x18002acd6  xor     esi, esi
0x18002acd8  cmp     [rdx], rsi
0x18002acdb  jz      loc_18002AEC8
0x18002ace1  lea     ebx, [rsi+4]
0x18002ace4  lea     r10, [rsi+rsi*4]
0x18002ace8  cmp     dword ptr [rdx+r10*8+1Ch], 1
0x18002acee  jnz     short loc_18002AD1C
0x18002acf0  mov     rax, [rdx+r10*8+8]
0x18002acf5  mov     r9d, ebx; dwType
0x18002acf8  mov     [rsp+38h+cbData], ebx; cbData
0x18002acfc  xor     r8d, r8d; Reserved
0x18002acff  mov     ecx, [rax]
0x18002ad01  lea     rax, [rbp+Data]
0x18002ad05  mov     dword ptr [rbp+Data], ecx
0x18002ad08  mov     rdx, [rdx+r10*8]; lpValueName
0x18002ad0c  mov     rcx, [rdi]; hKey
0x18002ad0f  mov     [rsp+38h+lpData], rax; lpData
0x18002ad14  call    cs:__imp_RegSetValueExW
0x18002ad1a  jmp     short loc_18002AD30
0x18002ad1c  mov     r8, [rdx+r10*8+8]
0x18002ad21  mov     rcx, rdi
0x18002ad24  mov     rdx, [rdx+r10*8]
0x18002ad28  mov     r8d, [r8]
0x18002ad2b  call    WsSetConfigBool
0x18002ad30  mov     rdx, cs:qword_18004F010
0x18002ad37  inc     esi
0x18002ad39  lea     rcx, [rsi+rsi*4]
0x18002ad3d  cmp     qword ptr [rdx+rcx*8], 0
0x18002ad42  jnz     short loc_18002ACE4
0x18002ad44  jmp     loc_18002AEC8
0x18002ad49  lea     rdx, aMaxthreads; "MaxThreads"
0x18002ad50  jmp     loc_18002ACA4
0x18002ad55  sub     ebx, 411h
0x18002ad5b  jz      short loc_18002ADC7
0x18002ad5d  sub     ebx, 1
0x18002ad60  jz      short loc_18002ADBB
0x18002ad62  sub     ebx, 1
0x18002ad65  jz      short loc_18002ADAF
0x18002ad67  sub     ebx, 1
0x18002ad6a  jz      short loc_18002ADA3
0x18002ad6c  sub     ebx, 1
0x18002ad6f  jz      short loc_18002AD97
0x18002ad71  sub     ebx, 1
0x18002ad74  jz      short loc_18002AD8B
0x18002ad76  cmp     ebx, 1
0x18002ad79  jnz     loc_18002AEC8
0x18002ad7f  lea     rdx, aCachefiletimeo; "CacheFileTimeout"
0x18002ad86  jmp     loc_18002ACA4
0x18002ad8b  lea     rdx, aDormantfilelim; "DormantFileLimit"
0x18002ad92  jmp     loc_18002ACA4
0x18002ad97  lea     rdx, aPipemaximum; "PipeMaximum"
0x18002ad9e  jmp     loc_18002ACA4
0x18002ada3  lea     rdx, aPipeincrement; "PipeIncrement"
0x18002adaa  jmp     loc_18002ACA4
0x18002adaf  lea     rdx, aLockmaximum; "LockMaximum"
0x18002adb6  jmp     loc_18002ACA4
0x18002adbb  lea     rdx, aLockincrement; "LockIncrement"
0x18002adc2  jmp     loc_18002ACA4
0x18002adc7  lea     rdx, aLockquota; "LockQuota"
0x18002adce  jmp     loc_18002ACA4
0x18002add3  lea     rdx, aUseopportunist; "UseOpportunisticLocking"
0x18002adda  jmp     loc_18002AEBD
0x18002addf  mov     eax, 420h
0x18002ade4  cmp     ebx, eax
0x18002ade6  ja      short loc_18002AE65
0x18002ade8  jz      short loc_18002AE5C
0x18002adea  sub     ebx, 419h
0x18002adf0  jz      short loc_18002AE53
0x18002adf2  sub     ebx, 1
0x18002adf5  jz      short loc_18002AE4A
0x18002adf7  sub     ebx, 1
0x18002adfa  jz      short loc_18002AE41
0x18002adfc  sub     ebx, 1
0x18002adff  jz      short loc_18002AE38
0x18002ae01  sub     ebx, 1
0x18002ae04  jz      short loc_18002AE2C
0x18002ae06  sub     ebx, 1
0x18002ae09  jz      short loc_18002AE20
0x18002ae0b  cmp     ebx, 1
0x18002ae0e  jnz     loc_18002AEC8
0x18002ae14  lea     rdx, aUserawwrite; "UseRawWrite"
0x18002ae1b  jmp     loc_18002AEBD
0x18002ae20  lea     rdx, aUserawread; "UseRawRead"
0x18002ae27  jmp     loc_18002AEBD
0x18002ae2c  lea     rdx, aUtilizentcachi; "UtilizeNtCaching"
0x18002ae33  jmp     loc_18002AEBD
0x18002ae38  lea     rdx, aUselockreadunl; "UseLockReadUnlock"
0x18002ae3f  jmp     short loc_18002AEBD
0x18002ae41  lea     rdx, aBufnamedpipes; "BufNamedPipes"
0x18002ae48  jmp     short loc_18002AEBD
0x18002ae4a  lea     rdx, aUseclosebehind; "UseCloseBehind"
0x18002ae51  jmp     short loc_18002AEBD
0x18002ae53  lea     rdx, aUseunlockbehin; "UseUnlockBehind"
0x18002ae5a  jmp     short loc_18002AEBD
0x18002ae5c  lea     rdx, aUsewriterawdat; "UseWriteRawData"
0x18002ae63  jmp     short loc_18002AEBD
0x18002ae65  sub     ebx, 421h
0x18002ae6b  jz      short loc_18002AEB6
0x18002ae6d  sub     ebx, 1
0x18002ae70  jz      short loc_18002AEAD
0x18002ae72  sub     ebx, 1
0x18002ae75  jz      short loc_18002AEA4
0x18002ae77  sub     ebx, 1
0x18002ae7a  jz      short loc_18002AE9B
0x18002ae7c  sub     ebx, 1
0x18002ae7f  jz      short loc_18002AE92
0x18002ae81  cmp     ebx, 1
0x18002ae84  jnz     short loc_18002AEC8
0x18002ae86  lea     rdx, aReadaheadthrou; "ReadAheadThroughput"
0x18002ae8d  jmp     loc_18002ACA4
0x18002ae92  lea     rdx, aUse512bytemaxt; "Use512ByteMaxTransfer"
0x18002ae99  jmp     short loc_18002AEBD
0x18002ae9b  lea     rdx, aForcecorecreat; "ForceCoreCreateMode"
0x18002aea2  jmp     short loc_18002AEBD
0x18002aea4  lea     rdx, aBufreadonlyfil; "BufReadOnlyFiles"
0x18002aeab  jmp     short loc_18002AEBD
0x18002aead  lea     rdx, aBuffilesdenywr; "BufFilesDenyWrite"
0x18002aeb4  jmp     short loc_18002AEBD
0x18002aeb6  lea     rdx, aUseencryption; "UseEncryption"
0x18002aebd  mov     r8d, [rsi]
0x18002aec0  mov     rcx, rdi
0x18002aec3  call    WsSetConfigBool
0x18002aec8  test    rdi, rdi
0x18002aecb  jz      short loc_18002AED5
0x18002aecd  mov     rcx, rdi
0x18002aed0  call    NetpCloseConfigData
0x18002aed5  add     rsp, 38h
0x18002aed9  pop     rdi
0x18002aeda  pop     rsi
0x18002aedb  pop     rbx
0x18002aedc  pop     rbp
0x18002aedd  retn
```
