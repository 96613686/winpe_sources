# CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(void *)

- ea: `0x140022c1c`
- end: `0x140022eec`
- name: `?DumpProcessDataSegsRegisteredBlocks@CUserModeHangReport@@AEAAJPEAX@Z`
- size: `720`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140023a6c`

## callees

- `0x140002470`
- `0x140014474`
- `0x140014ddc`
- `0x140022c1c`
- `0x1400274ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022c5f`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140022c55`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140022c55`
- `wer!WerpAuxmdMapFile` at `0x140022e50`
- `wer!WerpAuxmdMapFile` at `0x140022e50`
- `wer!WerpAuxmdHashVaRanges` at `0x140022e16`
- `wer!WerpAuxmdHashVaRanges` at `0x140022e16`
- `wer!WerpAuxmdFreeCopyBuffer` at `0x140022e08`
- `wer!WerpAuxmdFreeCopyBuffer` at `0x140022e08`
- `wer!WerpAuxmdDumpRegisteredBlocks` at `0x140022dfd`
- `wer!WerpAuxmdDumpRegisteredBlocks` at `0x140022dfd`
- `wer!WerpAuxmdDumpProcessImages` at `0x140022dc3`
- `wer!WerpAuxmdDumpProcessImages` at `0x140022dc3`
- `wer!WerpAuxmdInitialize` at `0x140022d84`
- `wer!WerpAuxmdInitialize` at `0x140022d84`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(CUserModeHangReport *this, void *a2)
{
  unsigned int TempPath2W; // eax
  signed int LastError; // eax
  signed int v6; // edi
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  int TempFile; // eax
  char v11; // bp
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  CUserModeHangReport *v15; // r10
  _BYTE v16[528]; // [rsp+40h] [rbp-238h] BYREF

  TempPath2W = GetTempPath2W(260, v16);
  if ( !TempPath2W )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      return (unsigned int)v6;
    }
    v8 = 104;
    goto LABEL_9;
  }
  if ( TempPath2W < 0x104 )
  {
    TempFile = UtilGetTempFile(0, v16, 0, (char *)this + 41640);
    v6 = TempFile;
    if ( TempFile < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
          (unsigned int)TempFile);
      }
      return (unsigned int)v6;
    }
    v6 = WerpAuxmdInitialize((char *)this + 37176, (char *)this + 41640, a2, 0x10000);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        return (unsigned int)v6;
      }
      v8 = 107;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, (unsigned int)v6);
      return (unsigned int)v6;
    }
    v6 = WerpAuxmdDumpProcessImages((char *)this + 37176, 3);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        return (unsigned int)v6;
      }
      v8 = 108;
      goto LABEL_9;
    }
    v11 = WerpAuxmdDumpRegisteredBlocks((char *)this + 37176);
    WerpAuxmdFreeCopyBuffer((char *)this + 37176);
    v6 = WerpAuxmdHashVaRanges((char *)this + 37176, 4);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        return (unsigned int)v6;
      }
      v8 = 109;
      goto LABEL_9;
    }
    v12 = WerpAuxmdMapFile((char *)this + 37176);
    if ( v12 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_37:
        if ( v15 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
          WPP_SF_SDDD(
            *((_QWORD *)v15 + 2),
            v13,
            v14,
            (_DWORD)this + 41640,
            *((_DWORD *)this + 9298) - v11,
            v11,
            *((_DWORD *)this + 9298));
        return 0;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
        (unsigned int)v12);
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, 2147942522LL);
  }
  return 2147942522LL;
}

```

## disassembly

```asm
0x140022c1c  mov     [rsp+arg_10], rbx
0x140022c21  mov     [rsp+arg_18], rbp
0x140022c26  push    rsi
0x140022c27  push    rdi
0x140022c28  push    r14
0x140022c2a  sub     rsp, 260h
0x140022c31  mov     rax, cs:__security_cookie
0x140022c38  xor     rax, rsp
0x140022c3b  mov     [rsp+278h+var_28], rax
0x140022c43  mov     rbp, rdx
0x140022c46  mov     r14, rcx
0x140022c49  mov     ebx, 104h
0x140022c4e  lea     rdx, [rsp+278h+var_238]
0x140022c53  mov     ecx, ebx
0x140022c55  call    cs:__imp_GetTempPath2W
0x140022c5b  test    eax, eax
0x140022c5d  jnz     short loc_140022CB6
0x140022c5f  call    cs:__imp_GetLastError
0x140022c65  mov     edi, eax
0x140022c67  test    eax, eax
0x140022c69  jle     short loc_140022C74
0x140022c6b  movzx   edi, ax
0x140022c6e  or      edi, 80070000h
0x140022c74  test    edi, edi
0x140022c76  mov     eax, 80004005h
0x140022c7b  cmovns  edi, eax
0x140022c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022c85  lea     rbx, WPP_GLOBAL_Control
0x140022c8c  cmp     rcx, rbx
0x140022c8f  jz      short loc_140022CAF
0x140022c91  test    byte ptr [rcx+1Ch], 2
0x140022c95  jz      short loc_140022CAF
0x140022c97  mov     edx, 68h ; 'h'
0x140022c9c  mov     rcx, [rcx+10h]
0x140022ca0  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140022ca7  mov     r9d, edi
0x140022caa  call    WPP_SF_d
0x140022caf  mov     eax, edi
0x140022cb1  jmp     loc_140022EC4
0x140022cb6  cmp     eax, ebx
0x140022cb8  jb      short loc_140022CF8
0x140022cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140022cc1  lea     rbx, WPP_GLOBAL_Control
0x140022cc8  cmp     rcx, rbx
0x140022ccb  jz      short loc_140022CEE
0x140022ccd  test    byte ptr [rcx+1Ch], 2
0x140022cd1  jz      short loc_140022CEE
0x140022cd3  mov     rcx, [rcx+10h]
0x140022cd7  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140022cde  mov     edx, 69h ; 'i'
0x140022ce3  mov     r9d, 8007007Ah
0x140022ce9  call    WPP_SF_d
0x140022cee  mov     eax, 8007007Ah
0x140022cf3  jmp     loc_140022EC4
0x140022cf8  mov     [rsp+278h+var_240], 0
0x140022d00  lea     rsi, [r14+0A2A8h]
0x140022d07  mov     r9, rsi
0x140022d0a  mov     [rsp+278h+var_248], 0
0x140022d12  xor     r8d, r8d
0x140022d15  mov     [rsp+278h+var_250], 0
0x140022d1e  lea     rdx, [rsp+278h+var_238]
0x140022d23  xor     ecx, ecx
0x140022d25  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140022d2a  mov     edi, eax
0x140022d2c  test    eax, eax
0x140022d2e  jns     short loc_140022D6E
0x140022d30  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d37  lea     rbx, WPP_GLOBAL_Control
0x140022d3e  cmp     rcx, rbx
0x140022d41  jz      loc_140022CAF
0x140022d47  test    byte ptr [rcx+1Ch], 2
0x140022d4b  jz      loc_140022CAF
0x140022d51  mov     rcx, [rcx+10h]
0x140022d55  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140022d5c  mov     edx, 6Ah ; 'j'
0x140022d61  mov     r9d, eax
0x140022d64  call    WPP_SF_d
0x140022d69  jmp     loc_140022CAF
0x140022d6e  lea     rbx, [r14+9138h]
0x140022d75  mov     r9d, 10000h
0x140022d7b  mov     rcx, rbx
0x140022d7e  mov     r8, rbp
0x140022d81  mov     rdx, rsi
0x140022d84  call    cs:__imp_WerpAuxmdInitialize
0x140022d8a  mov     edi, eax
0x140022d8c  test    eax, eax
0x140022d8e  jns     short loc_140022DBB
0x140022d90  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d97  lea     rbx, WPP_GLOBAL_Control
0x140022d9e  cmp     rcx, rbx
0x140022da1  jz      loc_140022CAF
0x140022da7  test    byte ptr [rcx+1Ch], 2
0x140022dab  jz      loc_140022CAF
0x140022db1  mov     edx, 6Bh ; 'k'
0x140022db6  jmp     loc_140022C9C
0x140022dbb  mov     edx, 3
0x140022dc0  mov     rcx, rbx
0x140022dc3  call    cs:__imp_WerpAuxmdDumpProcessImages
0x140022dc9  mov     edi, eax
0x140022dcb  test    eax, eax
0x140022dcd  jns     short loc_140022DFA
0x140022dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140022dd6  lea     rbx, WPP_GLOBAL_Control
0x140022ddd  cmp     rcx, rbx
0x140022de0  jz      loc_140022CAF
0x140022de6  test    byte ptr [rcx+1Ch], 2
0x140022dea  jz      loc_140022CAF
0x140022df0  mov     edx, 6Ch ; 'l'
0x140022df5  jmp     loc_140022C9C
0x140022dfa  mov     rcx, rbx
0x140022dfd  call    cs:__imp_WerpAuxmdDumpRegisteredBlocks
0x140022e03  mov     rcx, rbx
0x140022e06  mov     ebp, eax
0x140022e08  call    cs:__imp_WerpAuxmdFreeCopyBuffer
0x140022e0e  mov     edx, 4
0x140022e13  mov     rcx, rbx
0x140022e16  call    cs:__imp_WerpAuxmdHashVaRanges
0x140022e1c  mov     edi, eax
0x140022e1e  test    eax, eax
0x140022e20  jns     short loc_140022E4D
0x140022e22  mov     rcx, cs:WPP_GLOBAL_Control
0x140022e29  lea     rbx, WPP_GLOBAL_Control
0x140022e30  cmp     rcx, rbx
0x140022e33  jz      loc_140022CAF
0x140022e39  test    byte ptr [rcx+1Ch], 2
0x140022e3d  jz      loc_140022CAF
0x140022e43  mov     edx, 6Dh ; 'm'
0x140022e48  jmp     loc_140022C9C
0x140022e4d  mov     rcx, rbx
0x140022e50  call    cs:__imp_WerpAuxmdMapFile
0x140022e56  lea     rbx, WPP_GLOBAL_Control
0x140022e5d  test    eax, eax
0x140022e5f  jns     short loc_140022E8C
0x140022e61  mov     r10, cs:WPP_GLOBAL_Control
0x140022e68  cmp     r10, rbx
0x140022e6b  jz      short loc_140022EC2
0x140022e6d  test    byte ptr [r10+1Ch], 2
0x140022e72  jz      short loc_140022E93
0x140022e74  mov     rcx, [r10+10h]
0x140022e78  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140022e7f  mov     edx, 6Eh ; 'n'
0x140022e84  mov     r9d, eax
0x140022e87  call    WPP_SF_d
0x140022e8c  mov     r10, cs:WPP_GLOBAL_Control
0x140022e93  cmp     r10, rbx
0x140022e96  jz      short loc_140022EC2
0x140022e98  test    byte ptr [r10+1Ch], 8
0x140022e9d  jz      short loc_140022EC2
0x140022e9f  mov     eax, [r14+9148h]
0x140022ea6  mov     r9, rsi
0x140022ea9  mov     ecx, eax
0x140022eab  mov     [rsp+278h+var_248], eax
0x140022eaf  sub     ecx, ebp
0x140022eb1  mov     dword ptr [rsp+278h+var_250], ebp
0x140022eb5  mov     [rsp+278h+var_258], ecx
0x140022eb9  mov     rcx, [r10+10h]
0x140022ebd  call    WPP_SF_SDDD
0x140022ec2  xor     eax, eax
0x140022ec4  mov     rcx, [rsp+278h+var_28]
0x140022ecc  xor     rcx, rsp; StackCookie
0x140022ecf  call    __security_check_cookie
0x140022ed4  lea     r11, [rsp+278h+var_18]
0x140022edc  mov     rbx, [r11+30h]
0x140022ee0  mov     rbp, [r11+38h]
0x140022ee4  mov     rsp, r11
0x140022ee7  pop     r14
0x140022ee9  pop     rdi
0x140022eea  pop     rsi
0x140022eeb  retn
```
