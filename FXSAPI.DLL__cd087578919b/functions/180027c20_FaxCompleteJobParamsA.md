# FaxCompleteJobParamsA

- ea: `0x180027c20`
- end: `0x180027e1b`
- name: `FaxCompleteJobParamsA`
- size: `507`
- prototype: `BOOL __stdcall(PFAX_JOB_PARAMA *JobParams, PFAX_COVERPAGE_INFOA *CoverpageInfo)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800279f0`
- `0x180027c20`
- `0x180027e30`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027e00`
- `KERNEL32!SetLastError` at `0x180027e00`
- `KERNEL32!GetLastError` at `0x180027dbe`
- `KERNEL32!GetLastError` at `0x180027dbe`

## pseudocode

```c
BOOL __stdcall FaxCompleteJobParamsA(PFAX_JOB_PARAMA *JobParams, PFAX_COVERPAGE_INFOA *CoverpageInfo)
{
  LPCWCH *v4; // rdi
  LPCWCH *v5; // rbx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids);
  }
  if ( JobParams && CoverpageInfo )
  {
    *JobParams = 0;
    *CoverpageInfo = 0;
    if ( FaxCompleteJobParamsW((PFAX_JOB_PARAMW *)JobParams, (PFAX_COVERPAGE_INFOW *)CoverpageInfo) )
    {
      v4 = (LPCWCH *)*JobParams;
      v5 = (LPCWCH *)*CoverpageInfo;
      if ( (unsigned int)ConvertUnicodeStringInPlace((LPCWCH)(*JobParams)->Tsid)
        && (unsigned int)ConvertUnicodeStringInPlace(v4[4])
        && (unsigned int)ConvertUnicodeStringInPlace(v4[5])
        && (unsigned int)ConvertUnicodeStringInPlace(v4[6])
        && (unsigned int)ConvertUnicodeStringInPlace(v4[7])
        && (unsigned int)ConvertUnicodeStringInPlace(v4[11])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[16])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[17])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[18])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[19])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[20])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[21])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[22])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[23])
        && (unsigned int)ConvertUnicodeStringInPlace(v5[24]) )
      {
        return 1;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids, LastError);
      }
      pMemFree(*JobParams);
      pMemFree(*CoverpageInfo);
    }
  }
  else
  {
    SetLastError(0x57u);
  }
  return 0;
}

```

## disassembly

```asm
0x180027c20  push    rbx
0x180027c22  push    rsi
0x180027c23  push    rdi
0x180027c24  push    r14
0x180027c26  push    r15
0x180027c28  sub     rsp, 20h
0x180027c2c  mov     rsi, rdx
0x180027c2f  mov     r14, rcx
0x180027c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c39  lea     r15, WPP_GLOBAL_Control
0x180027c40  cmp     rcx, r15
0x180027c43  jz      short loc_180027C69
0x180027c45  test    dword ptr [rcx+1Ch], 1000h
0x180027c4c  jz      short loc_180027C69
0x180027c4e  cmp     byte ptr [rcx+19h], 5
0x180027c52  jb      short loc_180027C69
0x180027c54  mov     rcx, [rcx+10h]
0x180027c58  lea     r8, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids
0x180027c5f  mov     edx, 0Ch
0x180027c64  call    WPP_SF_
0x180027c69  test    r14, r14
0x180027c6c  jz      loc_180027DFB
0x180027c72  test    rsi, rsi
0x180027c75  jz      loc_180027DFB
0x180027c7b  mov     qword ptr [r14], 0
0x180027c82  mov     rdx, rsi; CoverpageInfo
0x180027c85  mov     rcx, r14; JobParams
0x180027c88  mov     qword ptr [rsi], 0
0x180027c8f  call    FaxCompleteJobParamsW
0x180027c94  test    eax, eax
0x180027c96  jz      loc_180027E0C
0x180027c9c  mov     rdi, [r14]
0x180027c9f  mov     rbx, [rsi]
0x180027ca2  mov     rcx, [rdi+18h]; lpWideCharStr
0x180027ca6  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027cab  test    eax, eax
0x180027cad  jz      loc_180027DA3
0x180027cb3  mov     rcx, [rdi+20h]; lpWideCharStr
0x180027cb7  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027cbc  test    eax, eax
0x180027cbe  jz      loc_180027DA3
0x180027cc4  mov     rcx, [rdi+28h]; lpWideCharStr
0x180027cc8  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027ccd  test    eax, eax
0x180027ccf  jz      loc_180027DA3
0x180027cd5  mov     rcx, [rdi+30h]; lpWideCharStr
0x180027cd9  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027cde  test    eax, eax
0x180027ce0  jz      loc_180027DA3
0x180027ce6  mov     rcx, [rdi+38h]; lpWideCharStr
0x180027cea  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027cef  test    eax, eax
0x180027cf1  jz      loc_180027DA3
0x180027cf7  mov     rcx, [rdi+58h]; lpWideCharStr
0x180027cfb  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d00  test    eax, eax
0x180027d02  jz      loc_180027DA3
0x180027d08  mov     rcx, [rbx+80h]; lpWideCharStr
0x180027d0f  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d14  test    eax, eax
0x180027d16  jz      loc_180027DA3
0x180027d1c  mov     rcx, [rbx+88h]; lpWideCharStr
0x180027d23  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d28  test    eax, eax
0x180027d2a  jz      short loc_180027DA3
0x180027d2c  mov     rcx, [rbx+90h]; lpWideCharStr
0x180027d33  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d38  test    eax, eax
0x180027d3a  jz      short loc_180027DA3
0x180027d3c  mov     rcx, [rbx+98h]; lpWideCharStr
0x180027d43  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d48  test    eax, eax
0x180027d4a  jz      short loc_180027DA3
0x180027d4c  mov     rcx, [rbx+0A0h]; lpWideCharStr
0x180027d53  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d58  test    eax, eax
0x180027d5a  jz      short loc_180027DA3
0x180027d5c  mov     rcx, [rbx+0A8h]; lpWideCharStr
0x180027d63  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d68  test    eax, eax
0x180027d6a  jz      short loc_180027DA3
0x180027d6c  mov     rcx, [rbx+0B0h]; lpWideCharStr
0x180027d73  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d78  test    eax, eax
0x180027d7a  jz      short loc_180027DA3
0x180027d7c  mov     rcx, [rbx+0B8h]; lpWideCharStr
0x180027d83  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d88  test    eax, eax
0x180027d8a  jz      short loc_180027DA3
0x180027d8c  mov     rcx, [rbx+0C0h]; lpWideCharStr
0x180027d93  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x180027d98  test    eax, eax
0x180027d9a  jz      short loc_180027DA3
0x180027d9c  mov     eax, 1
0x180027da1  jmp     short loc_180027E0E
0x180027da3  mov     rax, cs:WPP_GLOBAL_Control
0x180027daa  cmp     rax, r15
0x180027dad  jz      short loc_180027DE9
0x180027daf  test    dword ptr [rax+1Ch], 1000h
0x180027db6  jz      short loc_180027DE9
0x180027db8  cmp     byte ptr [rax+19h], 2
0x180027dbc  jb      short loc_180027DE9
0x180027dbe  call    cs:__imp_GetLastError
0x180027dc5  nop     dword ptr [rax+rax+00h]
0x180027dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180027dd1  lea     r8, WPP_a4158162aa603b3b4cac811f54679e94_Traceguids
0x180027dd8  mov     edx, 0Dh
0x180027ddd  mov     r9d, eax
0x180027de0  mov     rcx, [rcx+10h]
0x180027de4  call    WPP_SF_d
0x180027de9  mov     rcx, [r14]; lpMem
0x180027dec  call    pMemFree
0x180027df1  mov     rcx, [rsi]; lpMem
0x180027df4  call    pMemFree
0x180027df9  jmp     short loc_180027E0C
0x180027dfb  mov     ecx, 57h ; 'W'; dwErrCode
0x180027e00  call    cs:__imp_SetLastError
0x180027e07  nop     dword ptr [rax+rax+00h]
0x180027e0c  xor     eax, eax
0x180027e0e  add     rsp, 20h
0x180027e12  pop     r15
0x180027e14  pop     r14
0x180027e16  pop     rdi
0x180027e17  pop     rsi
0x180027e18  pop     rbx
0x180027e19  retn
```
