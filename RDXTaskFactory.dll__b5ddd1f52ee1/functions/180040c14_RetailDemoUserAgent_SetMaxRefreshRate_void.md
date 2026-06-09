# RetailDemoUserAgent::SetMaxRefreshRate(void)

- ea: `0x180040c14`
- end: `0x1800410fc`
- name: `?SetMaxRefreshRate@RetailDemoUserAgent@@AEAAJXZ`
- size: `1256`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003eebc`

## callees

- `0x18000aa7c`
- `0x18001ff9c`
- `0x180035d34`
- `0x180035dc0`
- `0x180036cb4`
- `0x18003ebe8`
- `0x180040694`
- `0x180040c14`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180040d8a`
- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180040d8a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180040c73`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180040c73`
- `USER32!SetDisplayConfig` at `0x180040fe0`
- `USER32!SetDisplayConfig` at `0x180041062`
- `USER32!SetDisplayConfig` at `0x180040fe0`
- `USER32!SetDisplayConfig` at `0x180041062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040df5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040df5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410d4`

## string_xrefs

- `0x180040c4d`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18004109d`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180040ca9`: `GetDisplayConfigBufferSizes failed (attempt %d/%d)`

## pseudocode

```c
__int64 __fastcall RetailDemoUserAgent::SetMaxRefreshRate(RetailDemoUserAgent *this)
{
  DISPLAYCONFIG_PATH_INFO *v1; // rsi
  DISPLAYCONFIG_MODE_INFO *v2; // rdi
  unsigned int v3; // ebx
  int i; // r14d
  LONG DisplayConfigBufferSizes; // eax
  __int64 v6; // r8
  const char *v7; // r9
  unsigned __int64 v8; // r9
  _QWORD *unique_cotaskmem; // rax
  __int64 v10; // r8
  const char *v11; // r9
  void *v12; // rcx
  _QWORD *v13; // rax
  void *v14; // rcx
  unsigned int v16; // ebx
  unsigned int v17; // r15d
  char v18; // dl
  UINT32 v19; // r12d
  __int64 modeInfoIdx; // rax
  UINT32 v21; // eax
  unsigned __int64 v22; // r14
  int v23; // ecx
  double v24; // xmm6_8
  unsigned int v25; // edx
  DISPLAYCONFIG_PATH_INFO *v26; // rbx
  __int64 v27; // r13
  GUID *v28; // rax
  int Data1; // ecx
  double v30; // xmm1_8
  double v31; // xmm0_8
  double v32; // xmm0_8
  unsigned __int64 v33; // rcx
  LONG v34; // eax
  int v35; // ebx
  unsigned __int64 v36; // r9
  unsigned int modeInfoArray; // [rsp+20h] [rbp-88h]
  int modeInfoArraya; // [rsp+20h] [rbp-88h]
  DISPLAYCONFIG_TOPOLOGY_ID *currentTopologyId; // [rsp+28h] [rbp-80h]
  __int64 v40; // [rsp+30h] [rbp-78h]
  LPVOID v41; // [rsp+40h] [rbp-68h] BYREF
  DISPLAYCONFIG_PATH_INFO *pathArray; // [rsp+48h] [rbp-60h] BYREF
  __int64 v43; // [rsp+50h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  DISPLAYCONFIG_MODE_INFO *v45; // [rsp+B0h] [rbp+8h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+B8h] [rbp+10h] BYREF
  UINT32 numPathArrayElements; // [rsp+C0h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp+20h] BYREF

  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  v1 = 0;
  pathArray = 0;
  v2 = 0;
  v45 = 0;
  v3 = 0;
  for ( i = 0; i < 3; ++i )
  {
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, &numModeInfoArrayElements);
    v3 = DisplayConfigBufferSizes;
    if ( DisplayConfigBufferSizes )
    {
      if ( DisplayConfigBufferSizes > 0 )
        v8 = (unsigned __int16)DisplayConfigBufferSizes | 0x80070000;
      else
        v8 = (unsigned int)DisplayConfigBufferSizes;
      LODWORD(v40) = 3;
      LODWORD(currentTopologyId) = i + 1;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x9DF,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)v8,
        (int)"GetDisplayConfigBufferSizes failed (attempt %d/%d)",
        (const char *)currentTopologyId,
        v40);
    }
    else
    {
      if ( !numPathArrayElements || !numModeInfoArrayElements )
      {
        if ( v2 )
          CoTaskMemFree(v2);
        if ( v1 )
          CoTaskMemFree(v1);
        return 0;
      }
      unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_PATH_INFO [0]>(
                           &pv,
                           numPathArrayElements,
                           v6,
                           v7);
      wistd::unique_ptr<DISPLAYCONFIG_MODE_INFO [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        &pathArray,
        unique_cotaskmem);
      v12 = pv;
      pv = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      v13 = wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_MODE_INFO [0]>(&v41, numModeInfoArrayElements, v10, v11);
      wistd::unique_ptr<DISPLAYCONFIG_MODE_INFO [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
        &v45,
        v13);
      v14 = v41;
      v41 = 0;
      if ( v14 )
        CoTaskMemFree(v14);
      v1 = pathArray;
      v2 = v45;
      if ( !pathArray || !v45 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9EB,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)0x8007000ELL,
          modeInfoArray);
        if ( v2 )
          CoTaskMemFree(v2);
        if ( v1 )
          CoTaskMemFree(v1);
        return 2147942414LL;
      }
      v3 = QueryDisplayConfig(2u, &numPathArrayElements, pathArray, &numModeInfoArrayElements, v45, 0);
      if ( v3 != 122 )
        break;
    }
  }
  if ( v3 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x9F4,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
            (const char *)v3,
            modeInfoArray);
    if ( v2 )
      CoTaskMemFree(v2);
    if ( v1 )
      CoTaskMemFree(v1);
    return v16;
  }
  else
  {
    v17 = 0;
    v18 = 0;
    LOBYTE(v45) = 0;
    v19 = 0;
    if ( numPathArrayElements )
    {
      do
      {
        modeInfoIdx = v1[v19].sourceInfo.modeInfoIdx;
        if ( (_DWORD)modeInfoIdx != -1
          && (unsigned int)modeInfoIdx < numModeInfoArrayElements
          && v2[modeInfoIdx].infoType == DISPLAYCONFIG_MODE_INFO_TYPE_SOURCE )
        {
          v21 = v1[v19].targetInfo.modeInfoIdx;
          if ( v21 != -1 && v21 < numModeInfoArrayElements )
          {
            v22 = (unsigned __int64)v21 << 6;
            if ( *(DISPLAYCONFIG_MODE_INFO_TYPE *)((char *)&v2->infoType + v22) == DISPLAYCONFIG_MODE_INFO_TYPE_TARGET )
            {
              v23 = *(LONG *)((char *)&v2->desktopImageInfo.DesktopImageRegion.bottom + v22);
              v24 = 0.0;
              if ( v23 )
                v24 = (double)*(int *)((char *)&v2->sourceMode.position.y + v22) / (double)v23;
              v25 = (int)(v24 + 0.5);
              v41 = (LPVOID)v25;
              v43 = *(_QWORD *)((char *)&v2->desktopImageInfo.DesktopImageRegion.right + v22);
              v26 = *(DISPLAYCONFIG_PATH_INFO **)((char *)&v2->desktopImageInfo.DesktopImageRegion.left + v22);
              pathArray = v26;
              v27 = *(UINT64 *)((char *)&v2->targetMode.targetVideoSignalInfo.pixelRate + v22);
              v28 = (GUID *)qword_18005DBD0;
              pv = qword_18005DBD0;
              while ( 1 )
              {
                Data1 = v28->Data1;
                if ( v28->Data1 <= v25 )
                {
LABEL_53:
                  *(_QWORD *)((char *)&v2->desktopImageInfo.DesktopImageRegion.right + v22) = v43;
                  *(_QWORD *)((char *)&v2->desktopImageInfo.DesktopImageRegion.left + v22) = v26;
                  *(UINT64 *)((char *)&v2->targetMode.targetVideoSignalInfo.pixelRate + v22) = v27;
                  v18 = (char)v45;
                  goto LABEL_54;
                }
                v30 = (double)Data1 / v24;
                *(UINT32 *)((char *)&v2->targetMode.targetVideoSignalInfo.vSyncFreq.Numerator + v22) = Data1;
                *(UINT32 *)((char *)&v2->targetMode.targetVideoSignalInfo.vSyncFreq.Denominator + v22) = 1;
                *(UINT32 *)((char *)&v2->targetMode.targetVideoSignalInfo.hSyncFreq.Numerator + v22) = (int)((double)(int)v26 * v30);
                *(UINT32 *)((char *)&v2->targetMode.targetVideoSignalInfo.hSyncFreq.Denominator + v22) = HIDWORD(pathArray);
                if ( v27 < 0 )
                  v31 = (double)(int)(v27 & 1 | ((unsigned __int64)v27 >> 1))
                      + (double)(int)(v27 & 1 | ((unsigned __int64)v27 >> 1));
                else
                  v31 = (double)(int)v27;
                v32 = v31 * v30;
                v33 = 0;
                if ( v32 >= 9.223372036854776e18 )
                {
                  v32 = v32 - 9.223372036854776e18;
                  if ( v32 < 9.223372036854776e18 )
                    v33 = 0x8000000000000000uLL;
                }
                *(UINT64 *)((char *)&v2->targetMode.targetVideoSignalInfo.pixelRate + v22) = v33
                                                                                           + (unsigned int)(int)v32;
                if ( !SetDisplayConfig(numPathArrayElements, v1, numModeInfoArrayElements, v2, 0x60u) )
                  break;
                v28 = (GUID *)((char *)pv + 4);
                pv = v28;
                v25 = (unsigned int)v41;
                if ( v28 == &GUID_9324da94_50ec_4a14_a770_e90ca03e7c8f )
                  goto LABEL_53;
              }
              v18 = 1;
              LOBYTE(v45) = 1;
            }
          }
        }
LABEL_54:
        ++v19;
      }
      while ( v19 < numPathArrayElements );
      if ( v18 )
      {
        v34 = SetDisplayConfig(numPathArrayElements, v1, numModeInfoArrayElements, v2, 0x6A0u);
        v35 = v34;
        if ( v34 )
        {
          if ( v34 > 0 )
            v36 = (unsigned __int16)v34 | 0x80070000;
          else
            v36 = (unsigned int)v34;
          if ( (v36 & 0x80000000) != 0LL )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xA49,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
              (const char *)v36,
              modeInfoArraya);
          if ( v35 > 0 )
            v17 = (unsigned __int16)v35 | 0x80070000;
          else
            v17 = v35;
        }
      }
    }
    if ( v2 )
      CoTaskMemFree(v2);
    if ( v1 )
      CoTaskMemFree(v1);
    return v17;
  }
}

```

## disassembly

```asm
0x180040c14  mov     rax, rsp
0x180040c17  mov     [rax+8], rcx
0x180040c1b  push    rbx
0x180040c1c  push    rsi
0x180040c1d  push    rdi
0x180040c1e  push    r12
0x180040c20  push    r13
0x180040c22  push    r14
0x180040c24  push    r15
0x180040c26  sub     rsp, 70h
0x180040c2a  movaps  xmmword ptr [rax-48h], xmm6
0x180040c2e  xor     r13d, r13d
0x180040c31  mov     [rax+18h], r13d
0x180040c35  mov     [rax+10h], r13d
0x180040c39  mov     esi, r13d
0x180040c3c  mov     [rax-60h], r13
0x180040c40  mov     edi, r13d
0x180040c43  mov     [rax+8], r13
0x180040c47  mov     ebx, r13d
0x180040c4a  mov     r14d, r13d
0x180040c4d  lea     r15, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180040c54  cmp     r14d, 3
0x180040c58  jge     loc_180040E02
0x180040c5e  lea     r8, [rsp+0A8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180040c66  lea     rdx, [rsp+0A8h+numPathArrayElements]; numPathArrayElements
0x180040c6e  mov     ecx, 2; flags
0x180040c73  call    cs:__imp_GetDisplayConfigBufferSizes
0x180040c79  mov     ebx, eax
0x180040c7b  test    eax, eax
0x180040c7d  jz      short loc_180040CC7
0x180040c7f  jg      short loc_180040C86
0x180040c81  mov     r9d, eax
0x180040c84  jmp     short loc_180040C91
0x180040c86  movzx   r9d, ax
0x180040c8a  or      r9d, 80070000h; char *
0x180040c91  lea     eax, [r14+1]
0x180040c95  mov     rcx, [rsp+0A8h]; this
0x180040c9d  mov     [rsp+0A8h+var_78], 3
0x180040ca5  mov     dword ptr [rsp+0A8h+currentTopologyId], eax; char *
0x180040ca9  lea     rax, aGetdisplayconf; "GetDisplayConfigBufferSizes failed (att"...
0x180040cb0  mov     [rsp+0A8h+modeInfoArray], rax; int
0x180040cb5  mov     r8, r15; unsigned int
0x180040cb8  mov     edx, 9DFh; void *
0x180040cbd  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180040cc2  jmp     loc_180040D97
0x180040cc7  mov     eax, [rsp+0A8h+numPathArrayElements]
0x180040cce  test    eax, eax
0x180040cd0  jz      loc_180040DDF
0x180040cd6  cmp     [rsp+0A8h+numModeInfoArrayElements], r13d
0x180040cde  jz      loc_180040DDF
0x180040ce4  mov     edx, eax
0x180040ce6  lea     rcx, [rsp+0A8h+pv]
0x180040cee  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@UDISPLAYCONFIG_PATH_INFO@@@wil@@YA?AV?$unique_ptr@$$BY0A@UDISPLAYCONFIG_PATH_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_PATH_INFO [0]>(unsigned __int64)
0x180040cf3  mov     rdx, rax
0x180040cf6  lea     rcx, [rsp+0A8h+pathArray]
0x180040cfb  call    ??4?$unique_ptr@$$BY0A@UDISPLAYCONFIG_MODE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<DISPLAYCONFIG_MODE_INFO [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<DISPLAYCONFIG_MODE_INFO [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180040d00  mov     rcx, [rsp+0A8h+pv]; pv
0x180040d08  mov     [rsp+0A8h+pv], r13
0x180040d10  test    rcx, rcx
0x180040d13  jz      short loc_180040D1B
0x180040d15  call    cs:__imp_CoTaskMemFree
0x180040d1b  mov     edx, [rsp+0A8h+numModeInfoArrayElements]
0x180040d22  lea     rcx, [rsp+0A8h+var_68]
0x180040d27  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@UDISPLAYCONFIG_MODE_INFO@@@wil@@YA?AV?$unique_ptr@$$BY0A@UDISPLAYCONFIG_MODE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_MODE_INFO [0]>(unsigned __int64)
0x180040d2c  mov     rdx, rax
0x180040d2f  lea     rcx, [rsp+0A8h+arg_0]
0x180040d37  call    ??4?$unique_ptr@$$BY0A@UDISPLAYCONFIG_MODE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<DISPLAYCONFIG_MODE_INFO [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<DISPLAYCONFIG_MODE_INFO [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180040d3c  mov     rcx, [rsp+0A8h+var_68]; pv
0x180040d41  mov     [rsp+0A8h+var_68], r13
0x180040d46  test    rcx, rcx
0x180040d49  jz      short loc_180040D51
0x180040d4b  call    cs:__imp_CoTaskMemFree
0x180040d51  mov     rsi, [rsp+0A8h+pathArray]
0x180040d56  mov     rdi, [rsp+0A8h+arg_0]
0x180040d5e  test    rsi, rsi
0x180040d61  jz      short loc_180040D9F
0x180040d63  test    rdi, rdi
0x180040d66  jz      short loc_180040D9F
0x180040d68  mov     [rsp+0A8h+currentTopologyId], r13; currentTopologyId
0x180040d6d  mov     [rsp+0A8h+modeInfoArray], rdi; modeInfoArray
0x180040d72  lea     r9, [rsp+0A8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180040d7a  mov     r8, rsi; pathArray
0x180040d7d  lea     rdx, [rsp+0A8h+numPathArrayElements]; numPathArrayElements
0x180040d85  mov     ecx, 2; flags
0x180040d8a  call    cs:__imp_QueryDisplayConfig
0x180040d90  mov     ebx, eax
0x180040d92  cmp     eax, 7Ah ; 'z'
0x180040d95  jnz     short loc_180040E02
0x180040d97  inc     r14d
0x180040d9a  jmp     loc_180040C54
0x180040d9f  mov     rcx, [rsp+0A8h]; this
0x180040da7  mov     ebx, 8007000Eh
0x180040dac  mov     r9d, ebx; char *
0x180040daf  mov     r8, r15; unsigned int
0x180040db2  mov     edx, 9EBh; void *
0x180040db7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040dbc  test    rdi, rdi
0x180040dbf  jz      short loc_180040DCA
0x180040dc1  mov     rcx, rdi; pv
0x180040dc4  call    cs:__imp_CoTaskMemFree
0x180040dca  test    rsi, rsi
0x180040dcd  jz      short loc_180040DD8
0x180040dcf  mov     rcx, rsi; pv
0x180040dd2  call    cs:__imp_CoTaskMemFree
0x180040dd8  mov     eax, ebx
0x180040dda  jmp     loc_1800410E6
0x180040ddf  test    rdi, rdi
0x180040de2  jz      short loc_180040DED
0x180040de4  mov     rcx, rdi; pv
0x180040de7  call    cs:__imp_CoTaskMemFree
0x180040ded  test    rsi, rsi
0x180040df0  jz      short loc_180040DFB
0x180040df2  mov     rcx, rsi; pv
0x180040df5  call    cs:__imp_CoTaskMemFree
0x180040dfb  xor     eax, eax
0x180040dfd  jmp     loc_1800410E6
0x180040e02  test    ebx, ebx
0x180040e04  jz      short loc_180040E43
0x180040e06  mov     rcx, [rsp+0A8h]; this
0x180040e0e  mov     r9d, ebx; char *
0x180040e11  mov     r8, r15; unsigned int
0x180040e14  mov     edx, 9F4h; void *
0x180040e19  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040e1e  mov     ebx, eax
0x180040e20  test    rdi, rdi
0x180040e23  jz      short loc_180040E2E
0x180040e25  mov     rcx, rdi; pv
0x180040e28  call    cs:__imp_CoTaskMemFree
0x180040e2e  test    rsi, rsi
0x180040e31  jz      short loc_180040E3C
0x180040e33  mov     rcx, rsi; pv
0x180040e36  call    cs:__imp_CoTaskMemFree
0x180040e3c  mov     eax, ebx
0x180040e3e  jmp     loc_1800410E6
0x180040e43  mov     r15d, r13d
0x180040e46  mov     dl, r13b
0x180040e49  mov     byte ptr [rsp+0A8h+arg_0], dl
0x180040e50  mov     r12d, r13d
0x180040e53  cmp     [rsp+0A8h+numPathArrayElements], r13d
0x180040e5b  jbe     loc_1800410BE
0x180040e61  mov     eax, r12d
0x180040e64  lea     rcx, [rax+rax*8]
0x180040e68  mov     eax, [rsi+rcx*8+0Ch]
0x180040e6c  cmp     eax, 0FFFFFFFFh
0x180040e6f  jz      loc_180041035
0x180040e75  cmp     eax, [rsp+0A8h+numModeInfoArrayElements]
0x180040e7c  jnb     loc_180041035
0x180040e82  shl     rax, 6
0x180040e86  cmp     dword ptr [rax+rdi], 1
0x180040e8a  jnz     loc_180041035
0x180040e90  mov     eax, [rsi+rcx*8+20h]
0x180040e94  cmp     eax, 0FFFFFFFFh
0x180040e97  jz      loc_180041035
0x180040e9d  cmp     eax, [rsp+0A8h+numModeInfoArrayElements]
0x180040ea4  jnb     loc_180041035
0x180040eaa  mov     r14d, eax
0x180040ead  shl     r14, 6
0x180040eb1  cmp     dword ptr [r14+rdi], 2
0x180040eb6  jnz     loc_180041035
0x180040ebc  mov     ecx, [r14+rdi+24h]
0x180040ec1  xorps   xmm6, xmm6
0x180040ec4  test    ecx, ecx
0x180040ec6  jz      short loc_180040EDE
0x180040ec8  mov     eax, [r14+rdi+20h]
0x180040ecd  cvtsi2sd xmm6, rax
0x180040ed2  xorps   xmm0, xmm0
0x180040ed5  cvtsi2sd xmm0, rcx
0x180040eda  divsd   xmm6, xmm0
0x180040ede  movaps  xmm0, xmm6
0x180040ee1  addsd   xmm0, cs:__real@3fe0000000000000
0x180040ee9  cvttsd2si rdx, xmm0
0x180040eee  mov     [rsp+0A8h+var_68], rdx
0x180040ef3  mov     rax, [r14+rdi+20h]
0x180040ef8  mov     [rsp+0A8h+var_58], rax
0x180040efd  mov     rbx, [r14+rdi+18h]
0x180040f02  mov     [rsp+0A8h+pathArray], rbx
0x180040f07  mov     r13, [r14+rdi+10h]
0x180040f0c  lea     rax, qword_18005DBD0
0x180040f13  mov     [rsp+0A8h+pv], rax
0x180040f1b  mov     ecx, [rax]
0x180040f1d  cmp     ecx, edx
0x180040f1f  jbe     loc_180041017
0x180040f25  xorps   xmm1, xmm1
0x180040f28  cvtsi2sd xmm1, rcx
0x180040f2d  divsd   xmm1, xmm6
0x180040f31  mov     [r14+rdi+20h], ecx
0x180040f36  mov     dword ptr [r14+rdi+24h], 1
0x180040f3f  mov     eax, ebx
0x180040f41  xorps   xmm0, xmm0
0x180040f44  cvtsi2sd xmm0, rax
0x180040f49  mulsd   xmm0, xmm1
0x180040f4d  cvttsd2si rax, xmm0
0x180040f52  mov     [r14+rdi+18h], eax
0x180040f57  mov     eax, dword ptr [rsp+0A8h+pathArray+4]
0x180040f5b  mov     [r14+rdi+1Ch], eax
0x180040f60  xorps   xmm0, xmm0
0x180040f63  test    r13, r13
0x180040f66  js      short loc_180040F6F
0x180040f68  cvtsi2sd xmm0, r13
0x180040f6d  jmp     short loc_180040F87
0x180040f6f  mov     rcx, r13
0x180040f72  shr     rcx, 1
0x180040f75  mov     rax, r13
0x180040f78  and     eax, 1
0x180040f7b  or      rcx, rax
0x180040f7e  cvtsi2sd xmm0, rcx
0x180040f83  addsd   xmm0, xmm0
0x180040f87  mulsd   xmm0, xmm1
0x180040f8b  xor     ecx, ecx
0x180040f8d  comisd  xmm0, cs:__real@43e0000000000000
0x180040f95  jb      short loc_180040FB6
0x180040f97  subsd   xmm0, cs:__real@43e0000000000000
0x180040f9f  comisd  xmm0, cs:__real@43e0000000000000
0x180040fa7  jnb     short loc_180040FB6
0x180040fa9  mov     rax, 8000000000000000h
0x180040fb3  mov     rcx, rax
0x180040fb6  cvttsd2si rax, xmm0
0x180040fbb  add     rax, rcx
0x180040fbe  mov     [r14+rdi+10h], rax
0x180040fc3  mov     dword ptr [rsp+0A8h+modeInfoArray], 60h ; '`'; flags
0x180040fcb  mov     r9, rdi; modeInfoArray
0x180040fce  mov     r8d, [rsp+0A8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180040fd6  mov     rdx, rsi; pathArray
0x180040fd9  mov     ecx, [rsp+0A8h+numPathArrayElements]; numPathArrayElements
0x180040fe0  call    cs:__imp_SetDisplayConfig
0x180040fe6  test    eax, eax
0x180040fe8  jz      loc_18004107B
0x180040fee  mov     rax, [rsp+0A8h+pv]
0x180040ff6  add     rax, 4
0x180040ffa  mov     [rsp+0A8h+pv], rax
0x180041002  lea     rcx, _GUID_9324da94_50ec_4a14_a770_e90ca03e7c8f
0x180041009  cmp     rax, rcx
0x18004100c  mov     rdx, [rsp+0A8h+var_68]
0x180041011  jnz     loc_180040F1B
0x180041017  mov     rax, [rsp+0A8h+var_58]
0x18004101c  mov     [r14+rdi+20h], rax
0x180041021  mov     [r14+rdi+18h], rbx
0x180041026  mov     [r14+rdi+10h], r13
0x18004102b  mov     dl, byte ptr [rsp+0A8h+arg_0]
0x180041032  xor     r13d, r13d
0x180041035  inc     r12d
0x180041038  mov     ecx, [rsp+0A8h+numPathArrayElements]; numPathArrayElements
0x18004103f  cmp     r12d, ecx
0x180041042  jb      loc_180040E61
0x180041048  test    dl, dl
0x18004104a  jz      short loc_1800410BE
0x18004104c  mov     dword ptr [rsp+0A8h+modeInfoArray], 6A0h; int
0x180041054  mov     r9, rdi; modeInfoArray
0x180041057  mov     r8d, [rsp+0A8h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18004105f  mov     rdx, rsi; pathArray
0x180041062  call    cs:__imp_SetDisplayConfig
0x180041068  mov     ebx, eax
0x18004106a  test    eax, eax
0x18004106c  jz      short loc_1800410BE
0x18004106e  movzx   r15d, bx
0x180041072  test    eax, eax
0x180041074  jg      short loc_180041086
0x180041076  mov     r9d, eax
0x180041079  jmp     short loc_180041090
0x18004107b  mov     dl, 1
0x18004107d  mov     byte ptr [rsp+0A8h+arg_0], dl
0x180041084  jmp     short loc_180041032
0x180041086  mov     r9d, r15d
0x180041089  or      r9d, 80070000h; char *
0x180041090  mov     rcx, [rsp+0A8h]; this
0x180041098  test    r9d, r9d
0x18004109b  jns     short loc_1800410AE
0x18004109d  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800410a4  mov     edx, 0A49h; void *
0x1800410a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800410ae  test    ebx, ebx
0x1800410b0  jg      short loc_1800410B7
0x1800410b2  mov     r15d, ebx
0x1800410b5  jmp     short loc_1800410BE
0x1800410b7  or      r15d, 80070000h
0x1800410be  test    rdi, rdi
0x1800410c1  jz      short loc_1800410CC
0x1800410c3  mov     rcx, rdi; pv
0x1800410c6  call    cs:__imp_CoTaskMemFree
0x1800410cc  test    rsi, rsi
0x1800410cf  jz      short loc_1800410DA
0x1800410d1  mov     rcx, rsi; pv
0x1800410d4  call    cs:__imp_CoTaskMemFree
0x1800410da  mov     eax, r15d
0x1800410dd  jmp     short loc_1800410E6
0x1800410df  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x1800410e6  movaps  xmm6, [rsp+0A8h+var_48]
0x1800410eb  add     rsp, 70h
0x1800410ef  pop     r15
0x1800410f1  pop     r14
0x1800410f3  pop     r13
0x1800410f5  pop     r12
0x1800410f7  pop     rdi
0x1800410f8  pop     rsi
0x1800410f9  pop     rbx
0x1800410fa  retn
```
