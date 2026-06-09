# CalculateDisplayBlankTime

- ea: `0x1801ee154`
- end: `0x1801ee415`
- name: `CalculateDisplayBlankTime`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1802545b4`

## callees

- `0x1800d5b30`
- `0x1801ee154`
- `0x180213c98`
- `0x180226cbc`
- `0x180226dc0`
- `0x180253fa4`
- `0x1802540e0`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1801ee28f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1801ee28f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x1801ee1b3`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x1801ee1b3`

## pseudocode

```c
__int64 __fastcall CalculateDisplayBlankTime(__int64 a1, int a2, double *a3)
{
  unsigned int DisplayConfigBufferSizes; // eax
  unsigned int v7; // r8d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  DISPLAYCONFIG_MODE_INFO *v11; // r8
  UINT32 i; // r9d
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  double v15; // xmm0_8
  UINT64 v16; // rax
  unsigned int v18; // ebx
  unsigned int modeInfoArray; // [rsp+20h] [rbp-50h]
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-40h] BYREF
  DISPLAYCONFIG_MODE_INFO *v21[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h]
  DISPLAYCONFIG_PATH_INFO *pathArray[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  UINT32 numModeInfoArrayElements; // [rsp+A8h] [rbp+38h] BYREF

  v24 = 0;
  *(_OWORD *)pathArray = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  do
  {
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(0x42u, &numPathArrayElements, &numModeInfoArrayElements);
    if ( DisplayConfigBufferSizes )
    {
      v10 = 37;
      goto LABEL_35;
    }
    v8 = 0x8E38E38E38E38E39uLL * (((char *)pathArray[1] - (char *)pathArray[0]) >> 3);
    if ( numPathArrayElements >= v8 )
    {
      if ( numPathArrayElements > v8 )
      {
        if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL
                                   * ((signed __int64)(v24 - (unsigned __int64)pathArray[0]) >> 3) )
          pathArray[1] = (DISPLAYCONFIG_PATH_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                                      pathArray[1],
                                                      numPathArrayElements - v8);
        else
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(pathArray);
      }
    }
    else
    {
      pathArray[1] = &pathArray[0][numPathArrayElements];
    }
    v9 = v21[1] - v21[0];
    if ( numModeInfoArrayElements >= v9 )
    {
      if ( numModeInfoArrayElements > v9 )
      {
        if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v22 - (unsigned __int64)v21[0]) >> 6) )
          v21[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                v21[1],
                                                numModeInfoArrayElements - v9);
        else
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(v21);
      }
    }
    else
    {
      v21[1] = &v21[0][(unsigned __int64)numModeInfoArrayElements];
    }
    DisplayConfigBufferSizes = QueryDisplayConfig(
                                 0x42u,
                                 &numPathArrayElements,
                                 pathArray[0],
                                 &numModeInfoArrayElements,
                                 v21[0],
                                 0);
  }
  while ( DisplayConfigBufferSizes == 122 );
  if ( DisplayConfigBufferSizes )
  {
    v10 = 50;
LABEL_35:
    v18 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v10,
            v7,
            (const char *)DisplayConfigBufferSizes,
            modeInfoArray);
    if ( v21[0] )
    {
      std::_Deallocate<16>(v21[0], (v22 - (unsigned __int64)v21[0]) & 0xFFFFFFFFFFFFFFC0uLL);
      v22 = 0;
      *(_OWORD *)v21 = 0;
    }
    if ( pathArray[0] )
      std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v24 - (unsigned __int64)pathArray[0]) >> 3));
    return v18;
  }
  v11 = v21[0];
  for ( i = 0; ; ++i )
  {
    if ( i >= numModeInfoArrayElements )
    {
      *a3 = 0.001000000047497451;
      goto LABEL_29;
    }
    v13 = (unsigned __int64)i << 6;
    if ( *(DISPLAYCONFIG_MODE_INFO_TYPE *)((char *)&v21[0]->infoType + v13) == DISPLAYCONFIG_MODE_INFO_TYPE_TARGET
      && (*(unsigned int *)((char *)&v21[0]->adapterId.LowPart + v13)
        | (unsigned __int64)((__int64)(int)HIDWORD(*(unsigned __int64 *)((char *)&v21[0]->adapterId + v13)) << 32)) == a1
      && *(UINT32 *)((char *)&v21[0]->id + v13) == a2 )
    {
      break;
    }
  }
  v14 = *(UINT64 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.pixelRate + v13);
  if ( v14 < 0 )
  {
    v16 = *(UINT64 *)((_BYTE *)&v21[0]->targetMode.targetVideoSignalInfo.pixelRate + v13) & 1
        | (*(UINT64 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.pixelRate + v13) >> 1);
    v15 = (double)(int)v16 + (double)(int)v16;
  }
  else
  {
    v15 = (double)(int)v14;
  }
  *a3 = (double)(*(UINT32 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.totalSize.cx + v13)
               * (*(UINT32 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.totalSize.cy + v13)
                - *(UINT32 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.activeSize.cy + v13)))
      / v15;
LABEL_29:
  if ( v11 )
  {
    std::_Deallocate<16>(v11, (v22 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFC0uLL);
    v22 = 0;
    *(_OWORD *)v21 = 0;
  }
  if ( pathArray[0] )
    std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v24 - (unsigned __int64)pathArray[0]) >> 3));
  return 0;
}

```

## disassembly

```asm
0x1801ee154  mov     [rsp-18h+arg_0], rbx
0x1801ee159  mov     [rsp-18h+arg_8], rsi
0x1801ee15e  push    rbp
0x1801ee15f  push    rdi
0x1801ee160  push    r15
0x1801ee162  mov     rbp, rsp
0x1801ee165  sub     rsp, 70h
0x1801ee169  xorps   xmm0, xmm0
0x1801ee16c  mov     [rbp+var_10], 0
0x1801ee174  movdqu  xmmword ptr [rbp+pathArray], xmm0
0x1801ee179  mov     rbx, r8
0x1801ee17c  mov     edi, edx
0x1801ee17e  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801ee183  mov     rsi, rcx
0x1801ee186  mov     [rbp+var_28], 0
0x1801ee18e  mov     [rbp+numPathArrayElements], 0
0x1801ee195  mov     r15, 8E38E38E38E38E39h
0x1801ee19f  mov     [rbp+numModeInfoArrayElements], 0
0x1801ee1a6  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x1801ee1aa  mov     ecx, 42h ; 'B'; flags
0x1801ee1af  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x1801ee1b3  call    cs:__imp_GetDisplayConfigBufferSizes
0x1801ee1b9  test    eax, eax
0x1801ee1bb  jnz     loc_1801EE39D
0x1801ee1c1  mov     r8, [rbp+pathArray]
0x1801ee1c5  mov     rcx, [rbp+pathArray+8]
0x1801ee1c9  mov     edx, [rbp+numPathArrayElements]
0x1801ee1cc  sub     rcx, r8
0x1801ee1cf  sar     rcx, 3
0x1801ee1d3  imul    rcx, r15
0x1801ee1d7  cmp     rdx, rcx
0x1801ee1da  jnb     short loc_1801EE1EA
0x1801ee1dc  lea     rax, [rdx+rdx*8]
0x1801ee1e0  lea     rcx, [r8+rax*8]
0x1801ee1e4  mov     [rbp+pathArray+8], rcx
0x1801ee1e8  jmp     short loc_1801EE21B
0x1801ee1ea  jbe     short loc_1801EE21B
0x1801ee1ec  mov     rax, [rbp+var_10]
0x1801ee1f0  sub     rax, r8
0x1801ee1f3  sar     rax, 3
0x1801ee1f7  imul    rax, r15
0x1801ee1fb  cmp     rdx, rax
0x1801ee1fe  jbe     short loc_1801EE20B
0x1801ee200  lea     rcx, [rbp+pathArray]
0x1801ee204  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801ee209  jmp     short loc_1801EE21B
0x1801ee20b  sub     rdx, rcx
0x1801ee20e  mov     rcx, [rbp+pathArray+8]
0x1801ee212  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x1801ee217  mov     [rbp+pathArray+8], rax
0x1801ee21b  mov     r8, [rbp+var_38]
0x1801ee21f  mov     rcx, [rbp+var_38+8]
0x1801ee223  mov     edx, [rbp+numModeInfoArrayElements]
0x1801ee226  sub     rcx, r8
0x1801ee229  sar     rcx, 6
0x1801ee22d  cmp     rdx, rcx
0x1801ee230  jnb     short loc_1801EE23F
0x1801ee232  shl     rdx, 6
0x1801ee236  add     rdx, r8
0x1801ee239  mov     [rbp+var_38+8], rdx
0x1801ee23d  jmp     short loc_1801EE26C
0x1801ee23f  jbe     short loc_1801EE26C
0x1801ee241  mov     rax, [rbp+var_28]
0x1801ee245  sub     rax, r8
0x1801ee248  sar     rax, 6
0x1801ee24c  cmp     rdx, rax
0x1801ee24f  jbe     short loc_1801EE25C
0x1801ee251  lea     rcx, [rbp+var_38]
0x1801ee255  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801ee25a  jmp     short loc_1801EE26C
0x1801ee25c  sub     rdx, rcx
0x1801ee25f  mov     rcx, [rbp+var_38+8]
0x1801ee263  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x1801ee268  mov     [rbp+var_38+8], rax
0x1801ee26c  mov     rax, [rbp+var_38]
0x1801ee270  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x1801ee274  mov     r8, [rbp+pathArray]; pathArray
0x1801ee278  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x1801ee27c  mov     [rsp+70h+currentTopologyId], 0; currentTopologyId
0x1801ee285  mov     ecx, 42h ; 'B'; flags
0x1801ee28a  mov     [rsp+70h+modeInfoArray], rax; modeInfoArray
0x1801ee28f  call    cs:__imp_QueryDisplayConfig
0x1801ee295  cmp     eax, 7Ah ; 'z'
0x1801ee298  jz      loc_1801EE1A6
0x1801ee29e  test    eax, eax
0x1801ee2a0  jz      short loc_1801EE2AC
0x1801ee2a2  mov     edx, 32h ; '2'
0x1801ee2a7  jmp     loc_1801EE3A2
0x1801ee2ac  mov     r8, [rbp+var_38]
0x1801ee2b0  xor     r9d, r9d
0x1801ee2b3  cmp     r9d, [rbp+numModeInfoArrayElements]
0x1801ee2b7  jnb     loc_1801EE33F
0x1801ee2bd  mov     edx, r9d
0x1801ee2c0  shl     rdx, 6
0x1801ee2c4  cmp     dword ptr [rdx+r8], 2
0x1801ee2c9  jnz     short loc_1801EE2EF
0x1801ee2cb  mov     rax, [rdx+r8+8]
0x1801ee2d0  shr     rax, 20h
0x1801ee2d4  movsxd  rcx, eax
0x1801ee2d7  mov     eax, [rdx+r8+8]
0x1801ee2dc  shl     rcx, 20h
0x1801ee2e0  or      rcx, rax
0x1801ee2e3  cmp     rcx, rsi
0x1801ee2e6  jnz     short loc_1801EE2EF
0x1801ee2e8  cmp     [rdx+r8+4], edi
0x1801ee2ed  jz      short loc_1801EE2F4
0x1801ee2ef  inc     r9d
0x1801ee2f2  jmp     short loc_1801EE2B3
0x1801ee2f4  mov     eax, [rdx+r8+34h]
0x1801ee2f9  xorps   xmm1, xmm1
0x1801ee2fc  sub     eax, [rdx+r8+2Ch]
0x1801ee301  xorps   xmm0, xmm0
0x1801ee304  imul    eax, [rdx+r8+30h]
0x1801ee30a  mov     rcx, [rdx+r8+10h]
0x1801ee30f  cvtsi2sd xmm1, rax
0x1801ee314  test    rcx, rcx
0x1801ee317  js      short loc_1801EE320
0x1801ee319  cvtsi2sd xmm0, rcx
0x1801ee31e  jmp     short loc_1801EE335
0x1801ee320  mov     rax, rcx
0x1801ee323  and     ecx, 1
0x1801ee326  shr     rax, 1
0x1801ee329  or      rax, rcx
0x1801ee32c  cvtsi2sd xmm0, rax
0x1801ee331  addsd   xmm0, xmm0
0x1801ee335  divsd   xmm1, xmm0
0x1801ee339  movsd   qword ptr [rbx], xmm1
0x1801ee33d  jmp     short loc_1801EE34C
0x1801ee33f  mov     rax, 3F50624DE0000000h
0x1801ee349  mov     [rbx], rax
0x1801ee34c  test    r8, r8
0x1801ee34f  jz      short loc_1801EE374
0x1801ee351  mov     rdx, [rbp+var_28]
0x1801ee355  mov     rcx, r8
0x1801ee358  sub     rdx, r8
0x1801ee35b  and     rdx, 0FFFFFFFFFFFFFFC0h
0x1801ee35f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ee364  xorps   xmm0, xmm0
0x1801ee367  mov     [rbp+var_28], 0
0x1801ee36f  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801ee374  mov     rcx, [rbp+pathArray]
0x1801ee378  test    rcx, rcx
0x1801ee37b  jz      short loc_1801EE399
0x1801ee37d  mov     rax, [rbp+var_10]
0x1801ee381  sub     rax, rcx
0x1801ee384  sar     rax, 3
0x1801ee388  imul    rax, r15
0x1801ee38c  lea     rdx, [rax+rax*8]
0x1801ee390  shl     rdx, 3
0x1801ee394  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ee399  xor     eax, eax
0x1801ee39b  jmp     short loc_1801EE400
0x1801ee39d  mov     edx, 25h ; '%'; void *
0x1801ee3a2  mov     rcx, [rbp+18h]; this
0x1801ee3a6  mov     r9d, eax; char *
0x1801ee3a9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801ee3ae  mov     rcx, [rbp+var_38]
0x1801ee3b2  mov     ebx, eax
0x1801ee3b4  test    rcx, rcx
0x1801ee3b7  jz      short loc_1801EE3D9
0x1801ee3b9  mov     rdx, [rbp+var_28]
0x1801ee3bd  sub     rdx, rcx
0x1801ee3c0  and     rdx, 0FFFFFFFFFFFFFFC0h
0x1801ee3c4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ee3c9  xorps   xmm0, xmm0
0x1801ee3cc  mov     [rbp+var_28], 0
0x1801ee3d4  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801ee3d9  mov     rcx, [rbp+pathArray]
0x1801ee3dd  test    rcx, rcx
0x1801ee3e0  jz      short loc_1801EE3FE
0x1801ee3e2  mov     rax, [rbp+var_10]
0x1801ee3e6  sub     rax, rcx
0x1801ee3e9  sar     rax, 3
0x1801ee3ed  imul    rax, r15
0x1801ee3f1  lea     rdx, [rax+rax*8]
0x1801ee3f5  shl     rdx, 3
0x1801ee3f9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ee3fe  mov     eax, ebx
0x1801ee400  lea     r11, [rsp+70h+var_s0]
0x1801ee405  mov     rbx, [r11+20h]
0x1801ee409  mov     rsi, [r11+28h]
0x1801ee40d  mov     rsp, r11
0x1801ee410  pop     r15
0x1801ee412  pop     rdi
0x1801ee413  pop     rbp
0x1801ee414  retn
```
