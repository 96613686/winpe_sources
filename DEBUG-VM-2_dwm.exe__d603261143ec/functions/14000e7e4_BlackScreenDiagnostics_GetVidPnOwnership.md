# BlackScreenDiagnostics::GetVidPnOwnership

- ea: `0x14000e7e4`
- end: `0x14000e98e`
- name: `BlackScreenDiagnostics::GetVidPnOwnership`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000e750`

## callees

- `0x140005530`
- `0x14000dc6c`
- `0x14000df24`
- `0x14000df8c`
- `0x14000e7e4`
- `0x14000f16c`
- `0x14000f1b0`

## import_xrefs

- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTCheckVidPnExclusiveOwnership` at `0x14000e910`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTCheckVidPnExclusiveOwnership` at `0x14000e910`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x14000e8e9`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTOpenAdapterFromLuid` at `0x14000e8e9`
- `ntdll!RtlNtStatusToDosError` at `0x14000e952`
- `ntdll!RtlNtStatusToDosError` at `0x14000e952`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x14000e890`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x14000e890`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x14000e821`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x14000e821`

## pseudocode

```c
__int64 __fastcall BlackScreenDiagnostics::GetVidPnOwnership(_DWORD *a1)
{
  int DisplayConfigBufferSizes; // ebx
  DISPLAYCONFIG_PATH_INFO *v3; // rdx
  DISPLAYCONFIG_MODE_INFO *v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rsi
  NTSTATUS v7; // eax
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-29h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+34h] [rbp-25h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h] BYREF
  DISPLAYCONFIG_PATH_INFO *pathArray[3]; // [rsp+40h] [rbp-19h] BYREF
  DISPLAYCONFIG_MODE_INFO *modeInfoArray[3]; // [rsp+58h] [rbp-1h] BYREF
  LUID adapterId; // [rsp+70h] [rbp+17h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+1Fh]

  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, &numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes >= 0 )
  {
    if ( !numPathArrayElements )
    {
      *a1 = 4;
      return (unsigned int)DisplayConfigBufferSizes;
    }
    std::_Compressed_pair<std::allocator<unsigned char>,std::_Vector_val<std::_Simple_types<unsigned char>>,1>::_Compressed_pair<std::allocator<unsigned char>,std::_Vector_val<std::_Simple_types<unsigned char>>,1>(
      pathArray,
      numPathArrayElements);
    std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(pathArray);
    std::_Compressed_pair<std::allocator<unsigned char>,std::_Vector_val<std::_Simple_types<unsigned char>>,1>::_Compressed_pair<std::allocator<unsigned char>,std::_Vector_val<std::_Simple_types<unsigned char>>,1>(
      modeInfoArray,
      numModeInfoArrayElements);
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(modeInfoArray);
    DisplayConfigBufferSizes = QueryDisplayConfig(
                                 2u,
                                 &numPathArrayElements,
                                 pathArray[0],
                                 &numModeInfoArrayElements,
                                 modeInfoArray[0],
                                 0);
    if ( DisplayConfigBufferSizes < 0 )
    {
      *a1 = 5;
      goto LABEL_22;
    }
    v3 = pathArray[0];
    v5 = 0;
    v4 = modeInfoArray[0];
    while ( 1 )
    {
      if ( (unsigned int)v5 >= numPathArrayElements )
        goto LABEL_22;
      v6 = v5;
      if ( !*(_QWORD *)&modeInfoArray[0][(unsigned __int64)pathArray[0][v5].sourceInfo.modeInfoIdx].desktopImageInfo.DesktopImageRegion.top )
        break;
      v5 = (unsigned int)(v5 + 1);
    }
    adapterId = 0;
    v15 = 0;
    adapterId = pathArray[0][v5].sourceInfo.adapterId;
    v7 = D3DKMTOpenAdapterFromLuid(&adapterId, pathArray[0], modeInfoArray[0]);
    if ( v7 >= 0 )
    {
      v11 = v15;
      HIDWORD(v11) = pathArray[0][v6].sourceInfo.id;
      v7 = D3DKMTCheckVidPnExclusiveOwnership(&v11);
      if ( v7 == -1071775738 )
      {
        *a1 = 2;
      }
      else if ( v7 == -1071775732 )
      {
        *a1 = 3;
      }
      else
      {
        if ( v7 )
        {
          *a1 = 7;
LABEL_20:
          DisplayConfigBufferSizes = RtlNtStatusToDosError(v7);
LABEL_22:
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray, v3, v4);
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(pathArray);
          return (unsigned int)DisplayConfigBufferSizes;
        }
        *a1 = 1;
      }
      DisplayConfigBufferSizes = 0;
      goto LABEL_22;
    }
    *a1 = 6;
    goto LABEL_20;
  }
  return (unsigned int)DisplayConfigBufferSizes;
}

```

## disassembly

```asm
0x14000e7e4  push    rbp
0x14000e7e6  push    rbx
0x14000e7e7  push    rsi
0x14000e7e8  push    rdi
0x14000e7e9  lea     rbp, [rsp-3Fh]
0x14000e7ee  sub     rsp, 98h
0x14000e7f5  mov     rax, cs:__security_cookie
0x14000e7fc  xor     rax, rsp
0x14000e7ff  mov     [rbp+57h+var_30], rax
0x14000e803  mov     rdi, rcx
0x14000e806  mov     [rbp+57h+numPathArrayElements], 0
0x14000e80d  mov     ecx, 2; flags
0x14000e812  mov     [rbp+57h+numModeInfoArrayElements], 0
0x14000e819  lea     r8, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x14000e81d  lea     rdx, [rbp+57h+numPathArrayElements]; numPathArrayElements
0x14000e821  call    cs:__imp_GetDisplayConfigBufferSizes
0x14000e827  mov     ebx, eax
0x14000e829  test    eax, eax
0x14000e82b  js      loc_14000E974
0x14000e831  mov     eax, [rbp+57h+numPathArrayElements]
0x14000e834  test    eax, eax
0x14000e836  jnz     short loc_14000E843
0x14000e838  mov     dword ptr [rdi], 4
0x14000e83e  jmp     loc_14000E974
0x14000e843  lea     rcx, [rbp+57h+pathArray]
0x14000e847  mov     rdx, rax
0x14000e84a  call    ??$?0AEBV?$allocator@E@std@@$$V@?$_Compressed_pair@V?$allocator@E@std@@V?$_Vector_val@U?$_Simple_types@E@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBV?$allocator@E@1@@Z; std::_Compressed_pair<std::allocator<uchar>,std::_Vector_val<std::_Simple_types<uchar>>,1>::_Compressed_pair<std::allocator<uchar>,std::_Vector_val<std::_Simple_types<uchar>>,1>(std::_One_then_variadic_args_t,std::allocator<uchar> const &)
0x14000e84f  lea     rcx, [rbp+57h+pathArray]
0x14000e853  call    ??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(unsigned __int64)
0x14000e858  mov     edx, [rbp+57h+numModeInfoArrayElements]
0x14000e85b  lea     rcx, [rbp+57h+var_58]
0x14000e85f  call    ??$?0AEBV?$allocator@E@std@@$$V@?$_Compressed_pair@V?$allocator@E@std@@V?$_Vector_val@U?$_Simple_types@E@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBV?$allocator@E@1@@Z; std::_Compressed_pair<std::allocator<uchar>,std::_Vector_val<std::_Simple_types<uchar>>,1>::_Compressed_pair<std::allocator<uchar>,std::_Vector_val<std::_Simple_types<uchar>>,1>(std::_One_then_variadic_args_t,std::allocator<uchar> const &)
0x14000e864  lea     rcx, [rbp+57h+var_58]
0x14000e868  call    ??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(unsigned __int64)
0x14000e86d  mov     rax, [rbp+57h+var_58]
0x14000e871  lea     r9, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x14000e875  mov     r8, [rbp+57h+pathArray]; pathArray
0x14000e879  lea     rdx, [rbp+57h+numPathArrayElements]; numPathArrayElements
0x14000e87d  mov     [rsp+0B0h+currentTopologyId], 0; currentTopologyId
0x14000e886  mov     ecx, 2; flags
0x14000e88b  mov     [rsp+0B0h+modeInfoArray], rax; modeInfoArray
0x14000e890  call    cs:__imp_QueryDisplayConfig
0x14000e896  mov     ebx, eax
0x14000e898  test    eax, eax
0x14000e89a  js      loc_14000E95C
0x14000e8a0  mov     rdx, [rbp+57h+pathArray]
0x14000e8a4  xor     ecx, ecx
0x14000e8a6  mov     r8, [rbp+57h+var_58]
0x14000e8aa  cmp     ecx, [rbp+57h+numPathArrayElements]
0x14000e8ad  jnb     loc_14000E962
0x14000e8b3  lea     rsi, [rcx+rcx*8]
0x14000e8b7  mov     eax, [rdx+rsi*8+0Ch]
0x14000e8bb  shl     rax, 6
0x14000e8bf  mov     rax, [rax+r8+1Ch]
0x14000e8c4  test    eax, eax
0x14000e8c6  jnz     short loc_14000E8D0
0x14000e8c8  shr     rax, 20h
0x14000e8cc  test    eax, eax
0x14000e8ce  jz      short loc_14000E8D4
0x14000e8d0  inc     ecx
0x14000e8d2  jmp     short loc_14000E8AA
0x14000e8d4  xor     eax, eax
0x14000e8d6  lea     rcx, [rbp+57h+var_40]
0x14000e8da  mov     [rbp+57h+var_40], rax
0x14000e8de  mov     [rbp+57h+var_38], eax
0x14000e8e1  mov     rax, [rdx+rsi*8]
0x14000e8e5  mov     [rbp+57h+var_40], rax
0x14000e8e9  call    cs:__imp_D3DKMTOpenAdapterFromLuid
0x14000e8ef  test    eax, eax
0x14000e8f1  js      short loc_14000E94A
0x14000e8f3  mov     eax, [rbp+57h+var_38]
0x14000e8f6  mov     [rbp+57h+var_78], 0
0x14000e8fe  mov     dword ptr [rbp+57h+var_78], eax
0x14000e901  mov     rax, [rbp+57h+pathArray]
0x14000e905  mov     ecx, [rax+rsi*8+8]
0x14000e909  mov     dword ptr [rbp+57h+var_78+4], ecx
0x14000e90c  lea     rcx, [rbp+57h+var_78]
0x14000e910  call    cs:__imp_D3DKMTCheckVidPnExclusiveOwnership
0x14000e916  cmp     eax, 0C01E0006h
0x14000e91b  jz      short loc_14000E942
0x14000e91d  cmp     eax, 0C01E000Ch
0x14000e922  jz      short loc_14000E938
0x14000e924  test    eax, eax
0x14000e926  jz      short loc_14000E930
0x14000e928  mov     dword ptr [rdi], 7
0x14000e92e  jmp     short loc_14000E950
0x14000e930  mov     dword ptr [rdi], 1
0x14000e936  jmp     short loc_14000E93E
0x14000e938  mov     dword ptr [rdi], 3
0x14000e93e  xor     ebx, ebx
0x14000e940  jmp     short loc_14000E962
0x14000e942  mov     dword ptr [rdi], 2
0x14000e948  jmp     short loc_14000E93E
0x14000e94a  mov     dword ptr [rdi], 6
0x14000e950  mov     ecx, eax; Status
0x14000e952  call    cs:__imp_RtlNtStatusToDosError
0x14000e958  mov     ebx, eax
0x14000e95a  jmp     short loc_14000E962
0x14000e95c  mov     dword ptr [rdi], 5
0x14000e962  lea     rcx, [rbp+57h+var_58]
0x14000e966  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x14000e96b  lea     rcx, [rbp+57h+pathArray]
0x14000e96f  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x14000e974  mov     eax, ebx
0x14000e976  mov     rcx, [rbp+57h+var_30]
0x14000e97a  xor     rcx, rsp; StackCookie
0x14000e97d  call    __security_check_cookie
0x14000e982  add     rsp, 98h
0x14000e989  pop     rdi
0x14000e98a  pop     rsi
0x14000e98b  pop     rbx
0x14000e98c  pop     rbp
0x14000e98d  retn
```
