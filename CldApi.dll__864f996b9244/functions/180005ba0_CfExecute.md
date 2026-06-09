# CfExecute

- ea: `0x180005ba0`
- end: `0x180005f13`
- name: `CfExecute`
- size: `883`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callees

- `0x1800022ee`
- `0x180005ba0`
- `0x180009f88`
- `0x18000a0d0`
- `0x18000a234`
- `0x18000a4c8`
- `0x18000a608`
- `0x18000a794`
- `0x18000a8f4`
- `0x18000aa48`
- `0x18000b218`
- `0x18000b6c8`
- `0x180018404`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005be0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005be0`

## string_xrefs

- `0x180005e9f`: `ParamSize Invalid for TransferData`
- `0x180005e5f`: `ParamSize Invalid for RetrieveData`
- `0x180005e2e`: `ParamSize Invalid for AckData`
- `0x180005df6`: `ParamSize Invalid for RestartHydration`
- `0x180005dbb`: `ParamSize Invalid for TransferPlaceholders`
- `0x180005d80`: `ParamSize Invalid for AckDehydrate`
- `0x180005d5c`: `CfpExecuteAckDelete Failed`
- `0x180005d45`: `ParamSize Invalid for AckDelete`
- `0x180005d18`: `CfpExecuteAckRename Failed`
- `0x180005cff`: `ParamSize Invalid for AckRename`

## pseudocode

```c
__int64 __fastcall CfExecute(__int64 a1, _DWORD *a2)
{
  signed int v4; // ebx
  __int64 v5; // rbp
  const wchar_t *v6; // rdx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  int Data; // eax
  char v17[8]; // [rsp+30h] [rbp-88h] BYREF
  const wchar_t *v18; // [rsp+38h] [rbp-80h]
  unsigned __int64 UnbiasedTime; // [rsp+C0h] [rbp+8h] BYREF

  UnbiasedTime = 0;
  memset_0(v17, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v4 = *(_DWORD *)a1 < 0x18u ? 0x57 : 0;
  if ( *(_DWORD *)a1 < 0x18u )
    v4 = (*(_DWORD *)a1 < 0x18u ? 0x57 : 0) | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = 0;
LABEL_73:
    v6 = 0;
    goto LABEL_74;
  }
  v5 = CfpReferenceSyncRoot(*(_QWORD *)(a1 + 8));
  v4 = v5 == 0 ? 0x57 : 0;
  if ( !v5 )
    v4 |= 0x80070000;
  if ( v4 <= -1 )
  {
    v6 = L"syncRoot not found with ConnectionKey";
    goto LABEL_74;
  }
  v4 = *(_QWORD *)(a1 + 16) == 0 ? 0x57 : 0;
  if ( !*(_QWORD *)(a1 + 16) )
    v4 = (*(_QWORD *)(a1 + 16) == 0 ? 0x57 : 0) | 0x80070000;
  if ( v4 <= -1 )
  {
    v6 = L"Invalid TransferKey";
    goto LABEL_74;
  }
  v7 = *(_DWORD *)(a1 + 4);
  v4 = 0;
  if ( v7 >= 8 )
    v4 = -2147024809;
  if ( v4 <= -1 )
  {
    v6 = L" Invalid Operation Type";
    goto LABEL_74;
  }
  if ( !v7 )
  {
    v4 = *a2 < 0x28u ? 0x57 : 0;
    if ( *a2 < 0x28u )
      v4 = (*a2 < 0x28u ? 0x57 : 0) | 0x80070000;
    if ( v4 <= -1 )
    {
      v6 = L"ParamSize Invalid for TransferData";
      goto LABEL_74;
    }
    v4 = CfpExecuteTransferData(a1, a2);
    if ( v4 <= -1 )
    {
      v6 = L"CfpExecuteTransferData Failed";
      goto LABEL_74;
    }
    goto LABEL_73;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v4 = *a2 < 0x30u ? 0x57 : 0;
    if ( *a2 < 0x30u )
      v4 = (*a2 < 0x30u ? 0x57 : 0) | 0x80070000;
    if ( v4 <= -1 )
    {
      v6 = L"ParamSize Invalid for RetrieveData";
      goto LABEL_74;
    }
    Data = CfpExecuteRetrieveData(a1, a2);
    goto LABEL_62;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v4 = *a2 < 0x20u ? 0x57 : 0;
    if ( *a2 < 0x20u )
      v4 = (*a2 < 0x20u ? 0x57 : 0) | 0x80070000;
    if ( v4 <= -1 )
    {
      v6 = L"ParamSize Invalid for AckData";
      goto LABEL_74;
    }
    Data = CfpExecuteAckData(a1, a2);
LABEL_62:
    v6 = L"CfpExecuteRetrieveData Failed";
    goto LABEL_63;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          if ( v13 == 1 )
          {
            v4 = *a2 < 0x10u ? 0x57 : 0;
            if ( *a2 < 0x10u )
              v4 = (*a2 < 0x10u ? 0x57 : 0) | 0x80070000;
            if ( v4 > -1 )
            {
              v14 = CfpExecuteAckRename(a1, a2);
              v6 = L"CfpExecuteAckRename Failed";
              v4 = v14;
              if ( v14 > -1 )
                v6 = 0;
            }
            else
            {
              v6 = L"ParamSize Invalid for AckRename";
            }
          }
          else
          {
            v4 = -2147024809;
            v6 = L"Invalid Operation Type";
          }
          goto LABEL_74;
        }
        v4 = *a2 < 0x10u ? 0x57 : 0;
        if ( *a2 < 0x10u )
          v4 = (*a2 < 0x10u ? 0x57 : 0) | 0x80070000;
        if ( v4 <= -1 )
        {
          v6 = L"ParamSize Invalid for AckDelete";
          goto LABEL_74;
        }
        Data = CfpExecuteAckDelete(a1, a2);
        v6 = L"CfpExecuteAckDelete Failed";
      }
      else
      {
        v4 = *a2 < 0x20u ? 0x57 : 0;
        if ( *a2 < 0x20u )
          v4 = (*a2 < 0x20u ? 0x57 : 0) | 0x80070000;
        if ( v4 <= -1 )
        {
          v6 = L"ParamSize Invalid for AckDehydrate";
          goto LABEL_74;
        }
        Data = CfpExecuteAckDehydrate(a1);
        v6 = L"CfpExecuteAckDehydrate Failed";
      }
    }
    else
    {
      v4 = *a2 < 0x28u ? 0x57 : 0;
      if ( *a2 < 0x28u )
        v4 = (*a2 < 0x28u ? 0x57 : 0) | 0x80070000;
      if ( v4 <= -1 )
      {
        v6 = L"ParamSize Invalid for TransferPlaceholders";
        goto LABEL_74;
      }
      Data = CfpExecuteTransferPlaceholders(a1, a2);
      v6 = L"CfpExecuteTransferPlaceholders Failed";
    }
  }
  else
  {
    v4 = *a2 < 0x28u ? 0x57 : 0;
    if ( *a2 < 0x28u )
      v4 = (*a2 < 0x28u ? 0x57 : 0) | 0x80070000;
    if ( v4 <= -1 )
    {
      v6 = L"ParamSize Invalid for RestartHydration";
      goto LABEL_74;
    }
    Data = CfpExecuteRestartHydration(a1);
    v6 = L"CfpExecuteRestartHydration Failed";
  }
LABEL_63:
  v4 = Data;
  if ( Data > -1 )
    v6 = 0;
LABEL_74:
  v18 = v6;
  TlmLogSyncProcessOperation(a1, (_DWORD)a2, UnbiasedTime, (unsigned int)v17, v4);
  if ( v5 )
    CfpReleaseSyncRoot(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005ba0  mov     rax, rsp
0x180005ba3  mov     [rax+10h], rbx
0x180005ba7  mov     [rax+18h], rbp
0x180005bab  push    rsi
0x180005bac  push    rdi
0x180005bad  push    r12
0x180005baf  push    r14
0x180005bb1  push    r15
0x180005bb3  sub     rsp, 90h
0x180005bba  mov     rdi, rdx
0x180005bbd  mov     qword ptr [rax+8], 0
0x180005bc5  xor     edx, edx; Val
0x180005bc7  mov     rsi, rcx
0x180005bca  lea     rcx, [rsp+0B8h+var_88]; void *
0x180005bcf  lea     r8d, [rdx+58h]; Size
0x180005bd3  call    memset_0
0x180005bd8  lea     rcx, [rsp+0B8h+UnbiasedTime]; UnbiasedTime
0x180005be0  call    cs:__imp_QueryUnbiasedInterruptTime
0x180005be6  cmp     dword ptr [rsi], 18h
0x180005be9  mov     r12d, 57h ; 'W'
0x180005bef  mov     r15d, 80070000h
0x180005bf5  sbb     ebx, ebx
0x180005bf7  and     ebx, r12d
0x180005bfa  mov     eax, ebx
0x180005bfc  or      eax, r15d
0x180005bff  cmp     dword ptr [rsi], 18h
0x180005c02  cmovb   ebx, eax
0x180005c05  test    ebx, ebx
0x180005c07  js      loc_180005EC3
0x180005c0d  mov     rcx, [rsi+8]
0x180005c11  call    CfpReferenceSyncRoot
0x180005c16  mov     rbp, rax
0x180005c19  neg     rax
0x180005c1c  sbb     ebx, ebx
0x180005c1e  not     ebx
0x180005c20  and     ebx, r12d
0x180005c23  mov     eax, ebx
0x180005c25  or      eax, r15d
0x180005c28  test    rbp, rbp
0x180005c2b  cmovz   ebx, eax
0x180005c2e  or      r14d, 0FFFFFFFFh
0x180005c32  cmp     ebx, r14d
0x180005c35  jg      short loc_180005C43
0x180005c37  lea     rdx, aSyncrootNotFou; "syncRoot not found with ConnectionKey"
0x180005c3e  jmp     loc_180005EC7
0x180005c43  mov     rax, [rsi+10h]
0x180005c47  neg     rax
0x180005c4a  sbb     ebx, ebx
0x180005c4c  not     ebx
0x180005c4e  and     ebx, r12d
0x180005c51  mov     eax, ebx
0x180005c53  or      eax, r15d
0x180005c56  cmp     qword ptr [rsi+10h], 0
0x180005c5b  cmovz   ebx, eax
0x180005c5e  cmp     ebx, r14d
0x180005c61  jg      short loc_180005C6F
0x180005c63  lea     rdx, aInvalidTransfe; "Invalid TransferKey"
0x180005c6a  jmp     loc_180005EC7
0x180005c6f  mov     ecx, [rsi+4]
0x180005c72  xor     ebx, ebx
0x180005c74  cmp     ecx, 8
0x180005c77  cmovge  ebx, r12d
0x180005c7b  mov     eax, ebx
0x180005c7d  or      eax, r15d
0x180005c80  cmp     ecx, 8
0x180005c83  cmovge  ebx, eax
0x180005c86  cmp     ebx, r14d
0x180005c89  jg      short loc_180005C97
0x180005c8b  lea     rdx, aInvalidOperati; " Invalid Operation Type"
0x180005c92  jmp     loc_180005EC7
0x180005c97  test    ecx, ecx
0x180005c99  jz      loc_180005E87
0x180005c9f  sub     ecx, 1
0x180005ca2  jz      loc_180005E47
0x180005ca8  sub     ecx, 1
0x180005cab  jz      loc_180005E16
0x180005cb1  sub     ecx, 1
0x180005cb4  jz      loc_180005DDE
0x180005cba  sub     ecx, 1
0x180005cbd  jz      loc_180005DA3
0x180005cc3  sub     ecx, 1
0x180005cc6  jz      loc_180005D68
0x180005ccc  sub     ecx, 1
0x180005ccf  jz      short loc_180005D2D
0x180005cd1  cmp     ecx, 1
0x180005cd4  jz      short loc_180005CE7
0x180005cd6  mov     ebx, 80070057h
0x180005cdb  lea     rdx, aInvalidOperati_0; "Invalid Operation Type"
0x180005ce2  jmp     loc_180005EC7
0x180005ce7  cmp     dword ptr [rdi], 10h
0x180005cea  sbb     ebx, ebx
0x180005cec  and     ebx, r12d
0x180005cef  mov     eax, ebx
0x180005cf1  or      eax, r15d
0x180005cf4  cmp     dword ptr [rdi], 10h
0x180005cf7  cmovb   ebx, eax
0x180005cfa  cmp     ebx, r14d
0x180005cfd  jg      short loc_180005D0B
0x180005cff  lea     rdx, aParamsizeInval_6; "ParamSize Invalid for AckRename"
0x180005d06  jmp     loc_180005EC7
0x180005d0b  mov     rdx, rdi
0x180005d0e  mov     rcx, rsi
0x180005d11  call    CfpExecuteAckRename
0x180005d16  xor     ecx, ecx
0x180005d18  lea     rdx, aCfpexecuteackr_0; "CfpExecuteAckRename Failed"
0x180005d1f  cmp     eax, r14d
0x180005d22  mov     ebx, eax
0x180005d24  cmovg   rdx, rcx
0x180005d28  jmp     loc_180005EC7
0x180005d2d  cmp     dword ptr [rdi], 10h
0x180005d30  sbb     ebx, ebx
0x180005d32  and     ebx, r12d
0x180005d35  mov     eax, ebx
0x180005d37  or      eax, r15d
0x180005d3a  cmp     dword ptr [rdi], 10h
0x180005d3d  cmovb   ebx, eax
0x180005d40  cmp     ebx, r14d
0x180005d43  jg      short loc_180005D51
0x180005d45  lea     rdx, aParamsizeInval_0; "ParamSize Invalid for AckDelete"
0x180005d4c  jmp     loc_180005EC7
0x180005d51  mov     rdx, rdi
0x180005d54  mov     rcx, rsi
0x180005d57  call    CfpExecuteAckDelete
0x180005d5c  lea     rdx, aCfpexecuteackd_2; "CfpExecuteAckDelete Failed"
0x180005d63  jmp     loc_180005E7A
0x180005d68  cmp     dword ptr [rdi], 20h ; ' '
0x180005d6b  sbb     ebx, ebx
0x180005d6d  and     ebx, r12d
0x180005d70  mov     eax, ebx
0x180005d72  or      eax, r15d
0x180005d75  cmp     dword ptr [rdi], 20h ; ' '
0x180005d78  cmovb   ebx, eax
0x180005d7b  cmp     ebx, r14d
0x180005d7e  jg      short loc_180005D8C
0x180005d80  lea     rdx, aParamsizeInval_1; "ParamSize Invalid for AckDehydrate"
0x180005d87  jmp     loc_180005EC7
0x180005d8c  mov     rdx, rdi
0x180005d8f  mov     rcx, rsi; int
0x180005d92  call    CfpExecuteAckDehydrate
0x180005d97  lea     rdx, aCfpexecuteackd_0; "CfpExecuteAckDehydrate Failed"
0x180005d9e  jmp     loc_180005E7A
0x180005da3  cmp     dword ptr [rdi], 28h ; '('
0x180005da6  sbb     ebx, ebx
0x180005da8  and     ebx, r12d
0x180005dab  mov     eax, ebx
0x180005dad  or      eax, r15d
0x180005db0  cmp     dword ptr [rdi], 28h ; '('
0x180005db3  cmovb   ebx, eax
0x180005db6  cmp     ebx, r14d
0x180005db9  jg      short loc_180005DC7
0x180005dbb  lea     rdx, aParamsizeInval_2; "ParamSize Invalid for TransferPlacehold"...
0x180005dc2  jmp     loc_180005EC7
0x180005dc7  mov     rdx, rdi
0x180005dca  mov     rcx, rsi
0x180005dcd  call    CfpExecuteTransferPlaceholders
0x180005dd2  lea     rdx, aCfpexecutetran_2; "CfpExecuteTransferPlaceholders Failed"
0x180005dd9  jmp     loc_180005E7A
0x180005dde  cmp     dword ptr [rdi], 28h ; '('
0x180005de1  sbb     ebx, ebx
0x180005de3  and     ebx, r12d
0x180005de6  mov     eax, ebx
0x180005de8  or      eax, r15d
0x180005deb  cmp     dword ptr [rdi], 28h ; '('
0x180005dee  cmovb   ebx, eax
0x180005df1  cmp     ebx, r14d
0x180005df4  jg      short loc_180005E02
0x180005df6  lea     rdx, aParamsizeInval_4; "ParamSize Invalid for RestartHydration"
0x180005dfd  jmp     loc_180005EC7
0x180005e02  mov     rdx, rdi
0x180005e05  mov     rcx, rsi; int
0x180005e08  call    CfpExecuteRestartHydration
0x180005e0d  lea     rdx, aCfpexecuterest_0; "CfpExecuteRestartHydration Failed"
0x180005e14  jmp     short loc_180005E7A
0x180005e16  cmp     dword ptr [rdi], 20h ; ' '
0x180005e19  sbb     ebx, ebx
0x180005e1b  and     ebx, r12d
0x180005e1e  mov     eax, ebx
0x180005e20  or      eax, r15d
0x180005e23  cmp     dword ptr [rdi], 20h ; ' '
0x180005e26  cmovb   ebx, eax
0x180005e29  cmp     ebx, r14d
0x180005e2c  jg      short loc_180005E3A
0x180005e2e  lea     rdx, aParamsizeInval; "ParamSize Invalid for AckData"
0x180005e35  jmp     loc_180005EC7
0x180005e3a  mov     rdx, rdi
0x180005e3d  mov     rcx, rsi
0x180005e40  call    CfpExecuteAckData
0x180005e45  jmp     short loc_180005E73
0x180005e47  cmp     dword ptr [rdi], 30h ; '0'
0x180005e4a  sbb     ebx, ebx
0x180005e4c  and     ebx, r12d
0x180005e4f  mov     eax, ebx
0x180005e51  or      eax, r15d
0x180005e54  cmp     dword ptr [rdi], 30h ; '0'
0x180005e57  cmovb   ebx, eax
0x180005e5a  cmp     ebx, r14d
0x180005e5d  jg      short loc_180005E68
0x180005e5f  lea     rdx, aParamsizeInval_3; "ParamSize Invalid for RetrieveData"
0x180005e66  jmp     short loc_180005EC7
0x180005e68  mov     rdx, rdi
0x180005e6b  mov     rcx, rsi
0x180005e6e  call    CfpExecuteRetrieveData
0x180005e73  lea     rdx, aCfpexecuteretr; "CfpExecuteRetrieveData Failed"
0x180005e7a  mov     ebx, eax
0x180005e7c  xor     eax, eax
0x180005e7e  cmp     ebx, r14d
0x180005e81  cmovg   rdx, rax
0x180005e85  jmp     short loc_180005EC7
0x180005e87  cmp     dword ptr [rdi], 28h ; '('
0x180005e8a  sbb     ebx, ebx
0x180005e8c  and     ebx, r12d
0x180005e8f  mov     eax, ebx
0x180005e91  or      eax, r15d
0x180005e94  cmp     dword ptr [rdi], 28h ; '('
0x180005e97  cmovb   ebx, eax
0x180005e9a  cmp     ebx, r14d
0x180005e9d  jg      short loc_180005EA8
0x180005e9f  lea     rdx, aParamsizeInval_5; "ParamSize Invalid for TransferData"
0x180005ea6  jmp     short loc_180005EC7
0x180005ea8  mov     rdx, rdi
0x180005eab  mov     rcx, rsi
0x180005eae  call    CfpExecuteTransferData
0x180005eb3  mov     ebx, eax
0x180005eb5  cmp     eax, r14d
0x180005eb8  jg      short loc_180005EC5
0x180005eba  lea     rdx, aCfpexecutetran; "CfpExecuteTransferData Failed"
0x180005ec1  jmp     short loc_180005EC7
0x180005ec3  xor     ebp, ebp
0x180005ec5  xor     edx, edx
0x180005ec7  mov     r8, [rsp+0B8h+UnbiasedTime]
0x180005ecf  lea     r9, [rsp+0B8h+var_88]
0x180005ed4  mov     [rsp+0B8h+var_80], rdx
0x180005ed9  mov     rcx, rsi
0x180005edc  mov     rdx, rdi
0x180005edf  mov     [rsp+0B8h+var_98], ebx
0x180005ee3  call    TlmLogSyncProcessOperation
0x180005ee8  test    rbp, rbp
0x180005eeb  jz      short loc_180005EF5
0x180005eed  mov     rcx, rbp
0x180005ef0  call    CfpReleaseSyncRoot
0x180005ef5  lea     r11, [rsp+0B8h+var_28]
0x180005efd  mov     eax, ebx
0x180005eff  mov     rbx, [r11+38h]
0x180005f03  mov     rbp, [r11+40h]
0x180005f07  mov     rsp, r11
0x180005f0a  pop     r15
0x180005f0c  pop     r14
0x180005f0e  pop     r12
0x180005f10  pop     rdi
0x180005f11  pop     rsi
0x180005f12  retn
```
