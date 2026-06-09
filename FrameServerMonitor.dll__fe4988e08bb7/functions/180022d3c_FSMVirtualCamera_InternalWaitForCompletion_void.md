# FSMVirtualCamera::InternalWaitForCompletion(void *)

- ea: `0x180022d3c`
- end: `0x180022ed5`
- name: `?InternalWaitForCompletion@FSMVirtualCamera@@IEAAJPEAX@Z`
- size: `409`
- prototype: `int(FSMVirtualCamera *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024850`
- `0x180024b00`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d4f8`
- `0x180022d3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022dc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e01`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalWaitForCompletion(FSMVirtualCamera *this, void *a2)
{
  __int64 v4; // rcx
  signed int v5; // ebx
  __int64 v6; // rdx
  unsigned __int8 Level; // al
  DWORD v8; // eax
  signed int LastError; // eax
  __int64 v10; // rdx

  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 254, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, v4);
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_7:
      Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_32:
      if ( !Level )
        return (unsigned int)v5;
      v10 = 261;
      goto LABEL_22;
    }
    v6 = 255;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v5);
    goto LABEL_7;
  }
  v8 = WaitForSingleObject(a2, 0xFFFFFFFF);
  if ( v8 )
  {
    if ( v8 == 128 )
    {
      v5 = -2147024768;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_7;
      v6 = 257;
      goto LABEL_6;
    }
    if ( v8 == 258 )
    {
      v5 = -2147024638;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_7;
      goto LABEL_6;
    }
    if ( v8 != -1 )
    {
      v5 = -1072875845;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_7;
      v6 = 260;
      goto LABEL_6;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_7;
      v6 = 259;
      goto LABEL_6;
    }
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  }
  else
  {
    v5 = *((_DWORD *)this + 156);
    if ( v5 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v6 = 256;
      goto LABEL_6;
    }
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
    if ( v5 < 0 )
      goto LABEL_32;
  }
  if ( Level >= 8u )
  {
    v10 = 262;
LABEL_22:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022d3c  mov     [rsp+arg_0], rbx
0x180022d41  mov     [rsp+arg_8], rsi
0x180022d46  push    rdi
0x180022d47  sub     rsp, 30h
0x180022d4b  mov     rbx, rdx
0x180022d4e  mov     rdi, rcx
0x180022d51  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022d56  lea     rsi, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180022d5d  cmp     al, 8
0x180022d5f  jb      short loc_180022D7F
0x180022d61  mov     r9, rcx
0x180022d64  mov     edx, 0FEh
0x180022d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d70  mov     r8, rsi
0x180022d73  mov     rcx, [rcx+0D8h]
0x180022d7a  call    WPP_SF_q
0x180022d7f  test    rbx, rbx
0x180022d82  jnz     short loc_180022DBB
0x180022d84  mov     ebx, 80070057h
0x180022d89  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022d8e  cmp     al, 1
0x180022d90  jb      short loc_180022DB1
0x180022d92  mov     edx, 0FFh
0x180022d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d9e  mov     r9, rdi
0x180022da1  mov     r8, rsi
0x180022da4  mov     [rsp+38h+var_18], ebx
0x180022da8  mov     rcx, [rcx+10h]
0x180022dac  call    WPP_SF_qD
0x180022db1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022db6  jmp     loc_180022EC7
0x180022dbb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022dbe  mov     rcx, rbx; hHandle
0x180022dc1  call    cs:__imp_WaitForSingleObject
0x180022dc7  test    eax, eax
0x180022dc9  jz      loc_180022E9D
0x180022dcf  cmp     eax, 80h
0x180022dd4  jz      loc_180022E81
0x180022dda  mov     edx, 102h
0x180022ddf  cmp     eax, edx
0x180022de1  jz      loc_180022E6A
0x180022de7  cmp     eax, 0FFFFFFFFh
0x180022dea  jz      short loc_180022E01
0x180022dec  mov     ebx, 0C00D36BBh
0x180022df1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022df6  cmp     al, 1
0x180022df8  jb      short loc_180022DB1
0x180022dfa  mov     edx, 104h
0x180022dff  jmp     short loc_180022D97
0x180022e01  call    cs:__imp_GetLastError
0x180022e07  mov     ebx, eax
0x180022e09  test    eax, eax
0x180022e0b  jle     short loc_180022E16
0x180022e0d  movzx   ebx, ax
0x180022e10  or      ebx, 80070000h
0x180022e16  test    ebx, ebx
0x180022e18  jns     short loc_180022E2D
0x180022e1a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022e1f  cmp     al, 1
0x180022e21  jb      short loc_180022DB1
0x180022e23  mov     edx, 103h
0x180022e28  jmp     loc_180022D97
0x180022e2d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022e32  cmp     al, 8
0x180022e34  jb      short loc_180022E58
0x180022e36  mov     edx, 106h
0x180022e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e42  mov     r9, rdi
0x180022e45  mov     r8, rsi
0x180022e48  mov     [rsp+38h+var_18], ebx
0x180022e4c  mov     rcx, [rcx+0D8h]
0x180022e53  call    WPP_SF_qD
0x180022e58  mov     rsi, [rsp+38h+arg_8]
0x180022e5d  mov     eax, ebx
0x180022e5f  mov     rbx, [rsp+38h+arg_0]
0x180022e64  add     rsp, 30h
0x180022e68  pop     rdi
0x180022e69  retn
0x180022e6a  mov     ebx, 80070102h
0x180022e6f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022e74  cmp     al, 1
0x180022e76  jb      loc_180022DB1
0x180022e7c  jmp     loc_180022D97
0x180022e81  mov     ebx, 80070080h
0x180022e86  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022e8b  cmp     al, 1
0x180022e8d  jb      loc_180022DB1
0x180022e93  mov     edx, 101h
0x180022e98  jmp     loc_180022D97
0x180022e9d  mov     ebx, [rdi+270h]
0x180022ea3  test    ebx, ebx
0x180022ea5  jns     short loc_180022EBA
0x180022ea7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022eac  cmp     al, 1
0x180022eae  jb      short loc_180022EBA
0x180022eb0  mov     edx, 100h
0x180022eb5  jmp     loc_180022D97
0x180022eba  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180022ebf  test    ebx, ebx
0x180022ec1  jns     loc_180022E32
0x180022ec7  cmp     al, 1
0x180022ec9  jb      short loc_180022E58
0x180022ecb  mov     edx, 105h
0x180022ed0  jmp     loc_180022E3B
```
