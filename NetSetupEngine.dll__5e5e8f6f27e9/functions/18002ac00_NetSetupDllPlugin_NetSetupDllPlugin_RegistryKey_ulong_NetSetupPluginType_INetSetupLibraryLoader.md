# NetSetupDllPlugin::NetSetupDllPlugin(RegistryKey &,ulong,NetSetupPluginType,INetSetupLibraryLoader *)

- ea: `0x18002ac00`
- end: `0x18002b24b`
- name: `??0NetSetupDllPlugin@@QEAA@AEAVRegistryKey@@KW4NetSetupPluginType@@PEAUINetSetupLibraryLoader@@@Z`
- size: `1611`
- prototype: `__int64 __fastcall(__int64, HKEY *, unsigned int, int, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18002aac0`

## callees

- `0x180007250`
- `0x18001dee8`
- `0x18002ac00`
- `0x18002b260`
- `0x18002b4cc`
- `0x18002b5d8`
- `0x18005097c`
- `0x180052620`
- `0x180052698`
- `0x180055b8c`
- `0x18005b034`
- `0x180064704`
- `0x1800647e0`
- `0x180065035`
- `0x180065056`
- `0x180065062`
- `0x180073f8c`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0bb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002ae1f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002ae1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aee5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aee5`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002af2c`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002af2c`
- `RPCRT4!MesHandleFree` at `0x18002af55`
- `RPCRT4!MesHandleFree` at `0x18002af55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NetSetupDllPlugin::NetSetupDllPlugin(__int64 a1, HKEY *a2, unsigned int a3, int a4, __int64 a5)
{
  __int64 v7; // r14
  unsigned __int64 *v8; // rdi
  size_t *v9; // r13
  void **v10; // rbx
  void **ValueString; // rsi
  _QWORD *v12; // rsi
  const WCHAR *v13; // r8
  size_t v14; // rbx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  void *v17; // rcx
  LSTATUS Value; // eax
  int v19; // ebx
  char *v20; // rbx
  unsigned int v21; // edi
  handle_t v22; // rdi
  handle_t v23; // rax
  __int64 v24; // rdx
  int v25; // edi
  __int64 v26; // r8
  unsigned __int64 *v28; // rcx
  signed int LastError; // eax
  LPCWCH *v30; // r9
  char *Buffer; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  _BYTE pExceptionObject[208]; // [rsp+78h] [rbp-88h] BYREF
  handle_t pHandle; // [rsp+148h] [rbp+48h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+150h] [rbp+50h] BYREF
  int v40; // [rsp+160h] [rbp+60h]
  unsigned __int64 v41; // [rsp+168h] [rbp+68h]
  CHAR MultiByteStr[256]; // [rsp+170h] [rbp+70h] BYREF

  v35 = -2;
  v36 = a1;
  *(_QWORD *)a1 = &NetSetupDllPlugin::`vftable';
  *(_DWORD *)(a1 + 8) = a4;
  *(_QWORD *)(a1 + 48) = 0;
  v7 = a1 + 56;
  *(_QWORD *)(a1 + 80) = 7;
  *(_QWORD *)(a1 + 72) = 0;
  *(_WORD *)(a1 + 56) = 0;
  v8 = (unsigned __int64 *)(a1 + 88);
  v9 = (size_t *)(a1 + 104);
  *(_QWORD *)(a1 + 112) = 15;
  *(_QWORD *)(a1 + 104) = 0;
  *(_BYTE *)(a1 + 88) = 0;
  v10 = (void **)(a1 + 120);
  *(_QWORD *)(a1 + 144) = 7;
  *(_QWORD *)(a1 + 136) = 0;
  *(_WORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 200) = a5;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 24) = a3;
  ValueString = (void **)RegistryKey::GetValueString(a2, &Buffer, L"Name");
  if ( v10 != ValueString )
  {
    if ( (unsigned __int64)v10[3] >= 8 )
      operator delete(*v10);
    v10[3] = (void *)7;
    v10[2] = 0;
    *(_WORD *)v10 = 0;
    if ( (unsigned __int64)ValueString[3] < 8 )
    {
      if ( ValueString[2] != (void *)-1LL )
        memmove_0(v10, ValueString, 2LL * ((_QWORD)ValueString[2] + 1));
    }
    else
    {
      *v10 = *ValueString;
      *ValueString = 0;
    }
    v10[2] = ValueString[2];
    v10[3] = ValueString[3];
    ValueString[3] = (void *)7;
    ValueString[2] = 0;
    *(_WORD *)ValueString = 0;
  }
  if ( v34 >= 8 )
    operator delete(Buffer);
  v12 = (_QWORD *)RegistryKey::GetValueString(a2, &Buffer, L"Module");
  if ( (_QWORD *)v7 != v12 )
  {
    if ( *(_QWORD *)(v7 + 24) >= 8u )
      operator delete(*(void **)v7);
    *(_QWORD *)(v7 + 24) = 7;
    *(_QWORD *)(v7 + 16) = 0;
    *(_WORD *)v7 = 0;
    if ( v12[3] < 8u )
    {
      if ( v12[2] != -1 )
        memmove_0((void *)v7, v12, 2 * (v12[2] + 1LL));
    }
    else
    {
      *(_QWORD *)v7 = *v12;
      *v12 = 0;
    }
    *(_QWORD *)(v7 + 16) = v12[2];
    *(_QWORD *)(v7 + 24) = v12[3];
    v12[3] = 7;
    v12[2] = 0;
    *(_WORD *)v12 = 0;
  }
  if ( v34 >= 8 )
    operator delete(Buffer);
  if ( (unsigned __int64)v10[3] >= 8 )
    v10 = (void **)*v10;
  *(_QWORD *)(a1 + 16) = v10;
  RegistryKey::GetValueString(a2, lpWideCharStr, L"Export");
  if ( v41 < 8 )
    v13 = (const WCHAR *)lpWideCharStr;
  else
    v13 = lpWideCharStr[0];
  if ( !WideCharToMultiByte(0xFDE9u, 0x80u, v13, v40 + 1, MultiByteStr, 256, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = lpWideCharStr;
      if ( v41 >= 8 )
        v30 = (LPCWCH *)lpWideCharStr[0];
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_7c690f37a9643bb7f037de91b585edb0_Traceguids, v30);
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  MultiByteStr[255] = 0;
  if ( MultiByteStr[0] )
  {
    v14 = -1;
    do
      ++v14;
    while ( MultiByteStr[v14] );
  }
  else
  {
    v14 = 0;
  }
  v15 = v8[3];
  if ( v15 < 0x10 )
    v16 = (unsigned __int64)v8;
  else
    v16 = *v8;
  if ( (unsigned __int64)MultiByteStr >= v16 )
  {
    v28 = v15 < 0x10 ? v8 : (unsigned __int64 *)*v8;
    if ( (char *)v28 + *v9 > MultiByteStr )
    {
      std::string::assign(v8);
      goto LABEL_36;
    }
  }
  if ( v14 == -1 )
    std::_Xlength_error("string too long");
  if ( v15 < v14 )
  {
    std::string::_Copy(v8, v14, *v9);
    if ( !v14 )
      goto LABEL_36;
    goto LABEL_31;
  }
  if ( v14 )
  {
LABEL_31:
    if ( v8[3] < 0x10 )
      v17 = v8;
    else
      v17 = (void *)*v8;
    memcpy_0(v17, MultiByteStr, v14);
    if ( v8[3] >= 0x10 )
      v8 = (unsigned __int64 *)*v8;
    *v9 = v14;
    *((_BYTE *)v8 + v14) = 0;
    goto LABEL_36;
  }
  if ( v15 >= 0x10 )
    v8 = (unsigned __int64 *)*v8;
  *v9 = 0;
  *(_BYTE *)v8 = 0;
LABEL_36:
  Value = RegQueryValueExW(*a2, L"Filter", 0, 0, 0, 0);
  v19 = Value;
  if ( Value != 2 )
  {
    if ( Value )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (unsigned int)L"Filter",
          Value);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v19);
      throw (Win32Exception *)pExceptionObject;
    }
    RegistryKey::GetValueBlob(a2, &Buffer, L"Filter", 0);
    pHandle = 0;
    v20 = Buffer;
    v21 = MesDecodeBufferHandleCreate(Buffer, v33 - (_DWORD)Buffer, &pHandle);
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_7c690f37a9643bb7f037de91b585edb0_Traceguids, v21);
      HResultException::HResultException((HResultException *)pExceptionObject, v21 | 0x80010000);
      throw (HResultException *)pExceptionObject;
    }
    v22 = pHandle;
    v23 = *(handle_t *)(a1 + 48);
    if ( pHandle == v23 )
    {
      v22 = *(handle_t *)(a1 + 48);
    }
    else
    {
      if ( v23 )
        MesHandleFree(*(handle_t *)(a1 + 48));
      *(_QWORD *)(a1 + 48) = v22;
    }
    v25 = DecodePluginFilterBlob(v22, a1 + 32);
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v26, a3, v25);
      HResultException::HResultException((HResultException *)pExceptionObject, v25);
      throw (HResultException *)pExceptionObject;
    }
    if ( v20 )
      operator delete(v20);
  }
  if ( v41 >= 8 )
    operator delete((void *)lpWideCharStr[0]);
  return a1;
}

```

## disassembly

```asm
0x18002ac00  push    rbp
0x18002ac02  push    rsi
0x18002ac03  push    rdi
0x18002ac04  push    r12
0x18002ac06  push    r13
0x18002ac08  push    r14
0x18002ac0a  push    r15
0x18002ac0c  lea     rbp, [rsp-180h]
0x18002ac14  sub     rsp, 280h
0x18002ac1b  mov     [rsp+2B0h+var_248], 0FFFFFFFFFFFFFFFEh
0x18002ac24  mov     [rsp+2B0h+arg_18], rbx
0x18002ac2c  mov     rax, cs:__security_cookie
0x18002ac33  xor     rax, rsp
0x18002ac36  mov     [rbp+1B0h+var_40], rax
0x18002ac3d  mov     [rsp+2B0h+var_270], r8d
0x18002ac42  mov     r12, rdx
0x18002ac45  mov     r15, rcx
0x18002ac48  mov     [rsp+2B0h+var_240], rcx
0x18002ac4d  xor     ecx, ecx
0x18002ac4f  lea     rax, ??_7NetSetupDllPlugin@@6B@; const NetSetupDllPlugin::`vftable'
0x18002ac56  mov     [r15], rax
0x18002ac59  mov     [r15+8], r9d
0x18002ac5d  mov     [r15+30h], rcx
0x18002ac61  lea     r14, [r15+38h]
0x18002ac65  mov     qword ptr [r14+18h], 7
0x18002ac6d  mov     [r14+10h], rcx
0x18002ac71  mov     [r14], cx
0x18002ac75  lea     rdi, [r15+58h]
0x18002ac79  lea     r13, [rdi+10h]
0x18002ac7d  mov     qword ptr [rdi+18h], 0Fh
0x18002ac85  mov     [r13+0], rcx
0x18002ac89  mov     [rdi], cl
0x18002ac8b  lea     rbx, [r15+78h]
0x18002ac8f  mov     qword ptr [rbx+18h], 7
0x18002ac97  mov     [rbx+10h], rcx
0x18002ac9b  mov     [rbx], cx
0x18002ac9e  mov     [r15+98h], rcx
0x18002aca5  mov     [r15+0A0h], rcx
0x18002acac  mov     rax, [rbp+1B0h+arg_20]
0x18002acb3  mov     [r15+0C8h], rax
0x18002acba  xorps   xmm0, xmm0
0x18002acbd  movups  xmmword ptr [r15+10h], xmm0
0x18002acc2  movups  xmmword ptr [r15+20h], xmm0
0x18002acc7  mov     [r15+18h], r8d
0x18002accb  lea     r8, aName; "Name"
0x18002acd2  lea     rdx, [rsp+2B0h+Buffer]
0x18002acd7  mov     rcx, r12
0x18002acda  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18002acdf  mov     rsi, rax
0x18002ace2  cmp     rbx, rax
0x18002ace5  jz      short loc_18002AD36
0x18002ace7  cmp     qword ptr [rbx+18h], 8
0x18002acec  jnb     loc_18002AFB7
0x18002acf2  mov     qword ptr [rbx+18h], 7
0x18002acfa  xor     ecx, ecx
0x18002acfc  mov     [rbx+10h], rcx
0x18002ad00  mov     [rbx], cx
0x18002ad03  cmp     qword ptr [rsi+18h], 8
0x18002ad08  jb      loc_18002AFFA
0x18002ad0e  mov     rax, [rsi]
0x18002ad11  mov     [rbx], rax
0x18002ad14  mov     [rsi], rcx
0x18002ad17  mov     rax, [rsi+10h]
0x18002ad1b  mov     [rbx+10h], rax
0x18002ad1f  mov     rax, [rsi+18h]
0x18002ad23  mov     [rbx+18h], rax
0x18002ad27  mov     qword ptr [rsi+18h], 7
0x18002ad2f  mov     [rsi+10h], rcx
0x18002ad33  mov     [rsi], cx
0x18002ad36  cmp     [rsp+2B0h+var_250], 8
0x18002ad3c  jnb     loc_18002AFC4
0x18002ad42  lea     r8, aModule; "Module"
0x18002ad49  lea     rdx, [rsp+2B0h+Buffer]
0x18002ad4e  mov     rcx, r12
0x18002ad51  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18002ad56  mov     rsi, rax
0x18002ad59  cmp     r14, rax
0x18002ad5c  jz      loc_18002B0E3
0x18002ad62  cmp     qword ptr [r14+18h], 8
0x18002ad67  jnb     loc_18002AFD3
0x18002ad6d  mov     qword ptr [r14+18h], 7
0x18002ad75  xor     ecx, ecx
0x18002ad77  mov     [r14+10h], rcx
0x18002ad7b  mov     [r14], cx
0x18002ad7f  cmp     qword ptr [rsi+18h], 8
0x18002ad84  jb      loc_18002B01D
0x18002ad8a  mov     rax, [rsi]
0x18002ad8d  mov     [r14], rax
0x18002ad90  mov     [rsi], rcx
0x18002ad93  mov     rax, [rsi+10h]
0x18002ad97  mov     [r14+10h], rax
0x18002ad9b  mov     rax, [rsi+18h]
0x18002ad9f  mov     [r14+18h], rax
0x18002ada3  mov     qword ptr [rsi+18h], 7
0x18002adab  xor     r14d, r14d
0x18002adae  mov     [rsi+10h], r14
0x18002adb2  mov     [rsi], r14w
0x18002adb6  cmp     [rsp+2B0h+var_250], 8
0x18002adbc  jnb     loc_18002AFE0
0x18002adc2  cmp     qword ptr [rbx+18h], 8
0x18002adc7  jb      short loc_18002ADCC
0x18002adc9  mov     rbx, [rbx]
0x18002adcc  mov     [r15+10h], rbx
0x18002add0  lea     r8, aExport; "Export"
0x18002add7  lea     rdx, [rbp+1B0h+lpWideCharStr]
0x18002addb  mov     rcx, r12
0x18002adde  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18002ade3  nop
0x18002ade4  mov     r9d, [rbp+1B0h+var_150]
0x18002ade8  cmp     [rbp+1B0h+var_148], 8
0x18002aded  jb      loc_18002B04E
0x18002adf3  mov     r8, [rbp+1B0h+lpWideCharStr]; lpWideCharStr
0x18002adf7  inc     r9d; cchWideChar
0x18002adfa  mov     [rsp+2B0h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18002adff  mov     [rsp+2B0h+lpDefaultChar], r14; lpDefaultChar
0x18002ae04  mov     [rsp+2B0h+cbMultiByte], 100h; cbMultiByte
0x18002ae0c  lea     rax, [rbp+1B0h+MultiByteStr]
0x18002ae10  mov     [rsp+2B0h+lpMultiByteStr], rax; lpMultiByteStr
0x18002ae15  mov     edx, 80h; dwFlags
0x18002ae1a  mov     ecx, 0FDE9h; CodePage
0x18002ae1f  call    cs:__imp_WideCharToMultiByte
0x18002ae25  test    eax, eax
0x18002ae27  jz      loc_18002B0EB
0x18002ae2d  mov     [rbp+1B0h+var_41], 0
0x18002ae34  cmp     [rbp+1B0h+MultiByteStr], 0
0x18002ae38  jz      loc_18002B133
0x18002ae3e  lea     rax, [rbp+1B0h+MultiByteStr]
0x18002ae42  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002ae49  nop     dword ptr [rax+00000000h]
0x18002ae50  inc     rbx
0x18002ae53  cmp     byte ptr [rax+rbx], 0
0x18002ae57  jnz     short loc_18002AE50
0x18002ae59  mov     rdx, [rdi+18h]
0x18002ae5d  cmp     rdx, 10h
0x18002ae61  jb      loc_18002B03E
0x18002ae67  mov     rax, [rdi]
0x18002ae6a  lea     rcx, [rbp+1B0h+MultiByteStr]
0x18002ae6e  cmp     rcx, rax
0x18002ae71  jnb     loc_18002B057
0x18002ae77  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x18002ae7b  ja      loc_18002B13B
0x18002ae81  cmp     rdx, rbx
0x18002ae84  jnb     loc_18002B148
0x18002ae8a  mov     r8, [r13+0]
0x18002ae8e  mov     rdx, rbx
0x18002ae91  mov     rcx, rdi
0x18002ae94  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18002ae99  test    rbx, rbx
0x18002ae9c  jz      short loc_18002AECA
0x18002ae9e  cmp     qword ptr [rdi+18h], 10h
0x18002aea3  jb      loc_18002B046
0x18002aea9  mov     rcx, [rdi]; void *
0x18002aeac  mov     r8, rbx; Size
0x18002aeaf  lea     rdx, [rbp+1B0h+MultiByteStr]; Src
0x18002aeb3  call    memcpy_0
0x18002aeb8  cmp     qword ptr [rdi+18h], 10h
0x18002aebd  jb      short loc_18002AEC2
0x18002aebf  mov     rdi, [rdi]
0x18002aec2  mov     [r13+0], rbx
0x18002aec6  mov     byte ptr [rbx+rdi], 0
0x18002aeca  mov     qword ptr [rsp+2B0h+cbMultiByte], r14; lpcbData
0x18002aecf  mov     [rsp+2B0h+lpMultiByteStr], r14; lpData
0x18002aed4  xor     r9d, r9d; lpType
0x18002aed7  xor     r8d, r8d; lpReserved
0x18002aeda  lea     rdx, aFilter; "Filter"
0x18002aee1  mov     rcx, [r12]; hKey
0x18002aee5  call    cs:__imp_RegQueryValueExW
0x18002aeeb  mov     ebx, eax
0x18002aeed  cmp     eax, 2
0x18002aef0  jz      loc_18002AF83
0x18002aef6  test    eax, eax
0x18002aef8  jnz     loc_18002B156
0x18002aefe  xor     r9d, r9d
0x18002af01  lea     r8, aFilter; "Filter"
0x18002af08  lea     rdx, [rsp+2B0h+Buffer]
0x18002af0d  mov     rcx, r12
0x18002af10  call    ?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)
0x18002af15  nop
0x18002af16  mov     [rbp+1B0h+pHandle], r14
0x18002af1a  mov     edx, [rsp+2B0h+var_260]
0x18002af1e  mov     rbx, [rsp+2B0h+Buffer]
0x18002af23  sub     edx, ebx; BufferSize
0x18002af25  lea     r8, [rbp+1B0h+pHandle]; pHandle
0x18002af29  mov     rcx, rbx; Buffer
0x18002af2c  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002af32  mov     edi, eax
0x18002af34  test    eax, eax
0x18002af36  jnz     loc_18002B1AD
0x18002af3c  mov     rdi, [rbp+1B0h+pHandle]
0x18002af40  mov     rax, [r15+30h]
0x18002af44  cmp     rdi, rax
0x18002af47  jz      loc_18002B09E
0x18002af4d  test    rax, rax
0x18002af50  jz      short loc_18002AF5B
0x18002af52  mov     rcx, rax; Handle
0x18002af55  call    cs:__imp_MesHandleFree
0x18002af5b  mov     [r15+30h], rdi
0x18002af5f  lea     rdx, [r15+20h]
0x18002af63  mov     rcx, rdi
0x18002af66  call    DecodePluginFilterBlob
0x18002af6b  mov     edi, eax
0x18002af6d  test    eax, eax
0x18002af6f  js      loc_18002B202
0x18002af75  test    rbx, rbx
0x18002af78  jz      short loc_18002AF83
0x18002af7a  mov     rcx, rbx; Block
0x18002af7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002af82  nop
0x18002af83  cmp     [rbp+1B0h+var_148], 8
0x18002af88  jnb     short loc_18002AFEF
0x18002af8a  mov     rax, r15
0x18002af8d  mov     rcx, [rbp+1B0h+var_40]
0x18002af94  xor     rcx, rsp; StackCookie
0x18002af97  call    __security_check_cookie
0x18002af9c  mov     rbx, [rsp+2B0h+arg_18]
0x18002afa4  add     rsp, 280h
0x18002afab  pop     r15
0x18002afad  pop     r14
0x18002afaf  pop     r13
0x18002afb1  pop     r12
0x18002afb3  pop     rdi
0x18002afb4  pop     rsi
0x18002afb5  pop     rbp
0x18002afb6  retn
0x18002afb7  mov     rcx, [rbx]; Block
0x18002afba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002afbf  jmp     loc_18002ACF2
0x18002afc4  mov     rcx, [rsp+2B0h+Buffer]; Block
0x18002afc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002afce  jmp     loc_18002AD42
0x18002afd3  mov     rcx, [r14]; Block
0x18002afd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002afdb  jmp     loc_18002AD6D
0x18002afe0  mov     rcx, [rsp+2B0h+Buffer]; Block
0x18002afe5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002afea  jmp     loc_18002ADC2
0x18002afef  mov     rcx, [rbp+1B0h+lpWideCharStr]; Block
0x18002aff3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aff8  jmp     short loc_18002AF8A
0x18002affa  mov     r8, [rsi+10h]
0x18002affe  add     r8, 1
0x18002b002  jz      loc_18002AD17
0x18002b008  add     r8, r8; Size
0x18002b00b  mov     rdx, rsi; Src
0x18002b00e  mov     rcx, rbx; void *
0x18002b011  call    memmove_0
0x18002b016  xor     ecx, ecx
0x18002b018  jmp     loc_18002AD17
0x18002b01d  mov     r8, [rsi+10h]
0x18002b021  add     r8, 1
0x18002b025  jz      loc_18002AD93
0x18002b02b  add     r8, r8; Size
0x18002b02e  mov     rdx, rsi; Src
0x18002b031  mov     rcx, r14; void *
0x18002b034  call    memmove_0
0x18002b039  jmp     loc_18002AD93
0x18002b03e  mov     rax, rdi
0x18002b041  jmp     loc_18002AE6A
0x18002b046  mov     rcx, rdi
0x18002b049  jmp     loc_18002AEAC
0x18002b04e  lea     r8, [rbp+1B0h+lpWideCharStr]
0x18002b052  jmp     loc_18002ADF7
0x18002b057  cmp     rdx, 10h
0x18002b05b  jb      short loc_18002B094
0x18002b05d  mov     rcx, [rdi]
0x18002b060  add     rcx, [r13+0]
0x18002b064  lea     rax, [rbp+1B0h+MultiByteStr]
0x18002b068  cmp     rcx, rax
0x18002b06b  jbe     loc_18002AE77
0x18002b071  cmp     rdx, 10h
0x18002b075  jb      short loc_18002B099
0x18002b077  mov     rax, [rdi]
0x18002b07a  lea     r8, [rbp+1B0h+MultiByteStr]
0x18002b07e  sub     r8, rax
0x18002b081  mov     r9, rbx
0x18002b084  mov     rdx, rdi
0x18002b087  mov     rcx, rdi; void *
0x18002b08a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18002b08f  jmp     loc_18002AECA
0x18002b094  mov     rcx, rdi
0x18002b097  jmp     short loc_18002B060
0x18002b099  mov     rax, rdi
0x18002b09c  jmp     short loc_18002B07A
0x18002b09e  mov     rdi, rax
0x18002b0a1  jmp     loc_18002AF5F
0x18002b0a6  cmp     rdx, 10h
0x18002b0aa  jb      short loc_18002B0AF
0x18002b0ac  mov     rdi, [rdi]
0x18002b0af  mov     [r13+0], r14
0x18002b0b3  mov     byte ptr [rdi], 0
0x18002b0b6  jmp     loc_18002AECA
0x18002b0bb  call    cs:__imp_GetLastError
0x18002b0c1  test    eax, eax
0x18002b0c3  jg      short loc_18002B129
0x18002b0c5  mov     edx, eax; int
0x18002b0c7  lea     rcx, [rsp+2B0h+pExceptionObject]; this
0x18002b0cc  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002b0d1  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002b0d8  lea     rcx, [rsp+2B0h+pExceptionObject]; pExceptionObject
0x18002b0dd  call    _CxxThrowException_0
  ... truncated ...
```
