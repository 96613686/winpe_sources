# CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(void *)

- ea: `0x14002430c`
- end: `0x14002460d`
- name: `?DumpProcessDataSegsRegisteredBlocks@CUserModeHangReport@@AEAAJPEAX@Z`
- size: `769`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400251c0`

## callees

- `0x140002490`
- `0x140014f14`
- `0x1400158e8`
- `0x14002430c`
- `0x140028ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024355`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140024345`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140024345`
- `wer!WerpAuxmdMapFile` at `0x14002456a`
- `wer!WerpAuxmdMapFile` at `0x14002456a`
- `wer!WerpAuxmdHashVaRanges` at `0x14002452a`
- `wer!WerpAuxmdHashVaRanges` at `0x14002452a`
- `wer!WerpAuxmdFreeCopyBuffer` at `0x140024516`
- `wer!WerpAuxmdFreeCopyBuffer` at `0x140024516`
- `wer!WerpAuxmdDumpRegisteredBlocks` at `0x140024505`
- `wer!WerpAuxmdDumpRegisteredBlocks` at `0x140024505`
- `wer!WerpAuxmdDumpProcessImages` at `0x1400244c5`
- `wer!WerpAuxmdDumpProcessImages` at `0x1400244c5`
- `wer!WerpAuxmdInitialize` at `0x140024480`
- `wer!WerpAuxmdInitialize` at `0x140024480`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::DumpProcessDataSegsRegisteredBlocks(wchar_t *this, void *a2)
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
  __int64 v16; // [rsp+20h] [rbp-258h]
  WCHAR v17[264]; // [rsp+40h] [rbp-238h] BYREF

  TempPath2W = GetTempPath2W(260, v17);
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
    TempFile = UtilGetTempFile(0, v17, 0, this + 20820, v16, 0, 0, 0);
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
    v6 = WerpAuxmdInitialize(this + 18588, this + 20820, a2, 0x10000);
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
    v6 = WerpAuxmdDumpProcessImages(this + 18588, 3);
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
    v11 = WerpAuxmdDumpRegisteredBlocks(this + 18588);
    WerpAuxmdFreeCopyBuffer(this + 18588);
    v6 = WerpAuxmdHashVaRanges(this + 18588, 4);
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
    v12 = WerpAuxmdMapFile(this + 18588);
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
0x14002430c  mov     [rsp+arg_10], rbx
0x140024311  mov     [rsp+arg_18], rbp
0x140024316  push    rsi
0x140024317  push    rdi
0x140024318  push    r14
0x14002431a  sub     rsp, 260h
0x140024321  mov     rax, cs:__security_cookie
0x140024328  xor     rax, rsp
0x14002432b  mov     [rsp+278h+var_28], rax
0x140024333  mov     rbp, rdx
0x140024336  mov     r14, rcx
0x140024339  mov     ebx, 104h
0x14002433e  lea     rdx, [rsp+278h+var_238]
0x140024343  mov     ecx, ebx
0x140024345  call    cs:__imp_GetTempPath2W
0x14002434c  nop     dword ptr [rax+rax+00h]
0x140024351  test    eax, eax
0x140024353  jnz     short loc_1400243B2
0x140024355  call    cs:__imp_GetLastError
0x14002435c  nop     dword ptr [rax+rax+00h]
0x140024361  mov     edi, eax
0x140024363  test    eax, eax
0x140024365  jle     short loc_140024370
0x140024367  movzx   edi, ax
0x14002436a  or      edi, 80070000h
0x140024370  test    edi, edi
0x140024372  mov     eax, 80004005h
0x140024377  cmovns  edi, eax
0x14002437a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024381  lea     rbx, WPP_GLOBAL_Control
0x140024388  cmp     rcx, rbx
0x14002438b  jz      short loc_1400243AB
0x14002438d  test    byte ptr [rcx+1Ch], 2
0x140024391  jz      short loc_1400243AB
0x140024393  mov     edx, 68h ; 'h'
0x140024398  mov     rcx, [rcx+10h]
0x14002439c  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400243a3  mov     r9d, edi
0x1400243a6  call    WPP_SF_d
0x1400243ab  mov     eax, edi
0x1400243ad  jmp     loc_1400245E4
0x1400243b2  cmp     eax, ebx
0x1400243b4  jb      short loc_1400243F4
0x1400243b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400243bd  lea     rbx, WPP_GLOBAL_Control
0x1400243c4  cmp     rcx, rbx
0x1400243c7  jz      short loc_1400243EA
0x1400243c9  test    byte ptr [rcx+1Ch], 2
0x1400243cd  jz      short loc_1400243EA
0x1400243cf  mov     rcx, [rcx+10h]
0x1400243d3  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400243da  mov     edx, 69h ; 'i'
0x1400243df  mov     r9d, 8007007Ah
0x1400243e5  call    WPP_SF_d
0x1400243ea  mov     eax, 8007007Ah
0x1400243ef  jmp     loc_1400245E4
0x1400243f4  mov     [rsp+278h+var_240], 0
0x1400243fc  lea     rsi, [r14+0A2A8h]
0x140024403  mov     r9, rsi
0x140024406  mov     [rsp+278h+var_248], 0
0x14002440e  xor     r8d, r8d
0x140024411  mov     [rsp+278h+var_250], 0
0x14002441a  lea     rdx, [rsp+278h+var_238]
0x14002441f  xor     ecx, ecx
0x140024421  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140024426  mov     edi, eax
0x140024428  test    eax, eax
0x14002442a  jns     short loc_14002446A
0x14002442c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024433  lea     rbx, WPP_GLOBAL_Control
0x14002443a  cmp     rcx, rbx
0x14002443d  jz      loc_1400243AB
0x140024443  test    byte ptr [rcx+1Ch], 2
0x140024447  jz      loc_1400243AB
0x14002444d  mov     rcx, [rcx+10h]
0x140024451  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140024458  mov     edx, 6Ah ; 'j'
0x14002445d  mov     r9d, eax
0x140024460  call    WPP_SF_d
0x140024465  jmp     loc_1400243AB
0x14002446a  lea     rbx, [r14+9138h]
0x140024471  mov     r9d, 10000h
0x140024477  mov     rcx, rbx
0x14002447a  mov     r8, rbp
0x14002447d  mov     rdx, rsi
0x140024480  call    cs:__imp_WerpAuxmdInitialize
0x140024487  nop     dword ptr [rax+rax+00h]
0x14002448c  mov     edi, eax
0x14002448e  test    eax, eax
0x140024490  jns     short loc_1400244BD
0x140024492  mov     rcx, cs:WPP_GLOBAL_Control
0x140024499  lea     rbx, WPP_GLOBAL_Control
0x1400244a0  cmp     rcx, rbx
0x1400244a3  jz      loc_1400243AB
0x1400244a9  test    byte ptr [rcx+1Ch], 2
0x1400244ad  jz      loc_1400243AB
0x1400244b3  mov     edx, 6Bh ; 'k'
0x1400244b8  jmp     loc_140024398
0x1400244bd  mov     edx, 3
0x1400244c2  mov     rcx, rbx
0x1400244c5  call    cs:__imp_WerpAuxmdDumpProcessImages
0x1400244cc  nop     dword ptr [rax+rax+00h]
0x1400244d1  mov     edi, eax
0x1400244d3  test    eax, eax
0x1400244d5  jns     short loc_140024502
0x1400244d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400244de  lea     rbx, WPP_GLOBAL_Control
0x1400244e5  cmp     rcx, rbx
0x1400244e8  jz      loc_1400243AB
0x1400244ee  test    byte ptr [rcx+1Ch], 2
0x1400244f2  jz      loc_1400243AB
0x1400244f8  mov     edx, 6Ch ; 'l'
0x1400244fd  jmp     loc_140024398
0x140024502  mov     rcx, rbx
0x140024505  call    cs:__imp_WerpAuxmdDumpRegisteredBlocks
0x14002450c  nop     dword ptr [rax+rax+00h]
0x140024511  mov     rcx, rbx
0x140024514  mov     ebp, eax
0x140024516  call    cs:__imp_WerpAuxmdFreeCopyBuffer
0x14002451d  nop     dword ptr [rax+rax+00h]
0x140024522  mov     edx, 4
0x140024527  mov     rcx, rbx
0x14002452a  call    cs:__imp_WerpAuxmdHashVaRanges
0x140024531  nop     dword ptr [rax+rax+00h]
0x140024536  mov     edi, eax
0x140024538  test    eax, eax
0x14002453a  jns     short loc_140024567
0x14002453c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024543  lea     rbx, WPP_GLOBAL_Control
0x14002454a  cmp     rcx, rbx
0x14002454d  jz      loc_1400243AB
0x140024553  test    byte ptr [rcx+1Ch], 2
0x140024557  jz      loc_1400243AB
0x14002455d  mov     edx, 6Dh ; 'm'
0x140024562  jmp     loc_140024398
0x140024567  mov     rcx, rbx
0x14002456a  call    cs:__imp_WerpAuxmdMapFile
0x140024571  nop     dword ptr [rax+rax+00h]
0x140024576  lea     rbx, WPP_GLOBAL_Control
0x14002457d  test    eax, eax
0x14002457f  jns     short loc_1400245AC
0x140024581  mov     r10, cs:WPP_GLOBAL_Control
0x140024588  cmp     r10, rbx
0x14002458b  jz      short loc_1400245E2
0x14002458d  test    byte ptr [r10+1Ch], 2
0x140024592  jz      short loc_1400245B3
0x140024594  mov     rcx, [r10+10h]
0x140024598  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x14002459f  mov     edx, 6Eh ; 'n'
0x1400245a4  mov     r9d, eax
0x1400245a7  call    WPP_SF_d
0x1400245ac  mov     r10, cs:WPP_GLOBAL_Control
0x1400245b3  cmp     r10, rbx
0x1400245b6  jz      short loc_1400245E2
0x1400245b8  test    byte ptr [r10+1Ch], 8
0x1400245bd  jz      short loc_1400245E2
0x1400245bf  mov     eax, [r14+9148h]
0x1400245c6  mov     r9, rsi
0x1400245c9  mov     ecx, eax
0x1400245cb  mov     [rsp+278h+var_248], eax
0x1400245cf  sub     ecx, ebp
0x1400245d1  mov     dword ptr [rsp+278h+var_250], ebp
0x1400245d5  mov     dword ptr [rsp+278h+var_258], ecx
0x1400245d9  mov     rcx, [r10+10h]
0x1400245dd  call    WPP_SF_SDDD
0x1400245e2  xor     eax, eax
0x1400245e4  mov     rcx, [rsp+278h+var_28]
0x1400245ec  xor     rcx, rsp; StackCookie
0x1400245ef  call    __security_check_cookie
0x1400245f4  lea     r11, [rsp+278h+var_18]
0x1400245fc  mov     rbx, [r11+30h]
0x140024600  mov     rbp, [r11+38h]
0x140024604  mov     rsp, r11
0x140024607  pop     r14
0x140024609  pop     rdi
0x14002460a  pop     rsi
0x14002460b  retn
```
