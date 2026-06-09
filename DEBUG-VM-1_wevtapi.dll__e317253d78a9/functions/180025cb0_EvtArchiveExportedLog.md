# EvtArchiveExportedLog

- ea: `0x180025cb0`
- end: `0x180025edd`
- name: `EvtArchiveExportedLog`
- size: `557`
- prototype: `BOOL __stdcall(EVT_HANDLE Session, LPCWSTR LogFilePath, LCID Locale, DWORD Flags)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180006aec`
- `0x180007940`
- `0x180007aa0`
- `0x18000a724`
- `0x18000bf5c`
- `0x18000c404`
- `0x180013f6c`
- `0x180023548`
- `0x180025cb0`
- `0x180028900`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025eb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025eb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall EvtArchiveExportedLog(EVT_HANDLE Session, LPCWSTR LogFilePath, LCID Locale, DWORD Flags)
{
  BOOL v7; // ebx
  DWORD v8; // edi
  struct Session *v10; // [rsp+20h] [rbp-C8h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-B0h]
  int v13; // [rsp+40h] [rbp-A8h]
  int v14; // [rsp+44h] [rbp-A4h]
  int v15; // [rsp+48h] [rbp-A0h]
  __int128 v16; // [rsp+50h] [rbp-98h] BYREF
  __int64 v17; // [rsp+60h] [rbp-88h]
  int v18; // [rsp+68h] [rbp-80h]
  int v19; // [rsp+6Ch] [rbp-7Ch]
  int v20; // [rsp+70h] [rbp-78h]
  __int128 v21; // [rsp+78h] [rbp-70h] BYREF
  __int64 v22; // [rsp+88h] [rbp-60h]
  int v23; // [rsp+90h] [rbp-58h]
  int v24; // [rsp+94h] [rbp-54h]
  int v25; // [rsp+98h] [rbp-50h]
  wchar_t *v26[4]; // [rsp+A0h] [rbp-48h] BYREF
  EvtException *v27; // [rsp+C0h] [rbp-28h] BYREF

  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    v7 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 87;
      v14 = -1;
      v15 = 1293;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !LogFilePath )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      v16 = 0;
      v17 = 0;
      v18 = 87;
      v19 = -1;
      v20 = 1298;
      throw (EvtException *)&v16;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v26);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v26) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 14);
      }
      v21 = 0;
      v22 = 0;
      v23 = 14;
      v24 = -1;
      v25 = 1304;
      throw (EvtException *)&v21;
    }
    FullyQualifyFilePath((__int64)v26, LogFilePath);
    GetSession(&v10);
    LogHandle::LocalizeExportLog(v10, Locale, v26[0], 0);
    v8 = 0;
    wmi::AutoRef<Object>::Release(&v10);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v26);
  }
  catch ( EvtException *v27 )
  {
    v7 = 0;
    v8 = *((_DWORD *)v27 + 6);
  }
  SetLastError(v8);
  LOBYTE(v7) = v8 == 0;
  return v7;
}

```

## disassembly

```asm
0x180025cb0  mov     [rsp+arg_0], rbx
0x180025cb5  mov     [rsp+arg_8], rsi
0x180025cba  push    rdi
0x180025cbb  push    r14
0x180025cbd  push    r15
0x180025cbf  sub     rsp, 0D0h
0x180025cc6  mov     esi, r9d
0x180025cc9  mov     r15d, r8d
0x180025ccc  mov     rdi, rdx
0x180025ccf  mov     r14, rcx
0x180025cd2  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180025cd7  xor     ebx, ebx
0x180025cd9  test    esi, esi
0x180025cdb  jz      short loc_180025D4A
0x180025cdd  lea     rax, WPP_GLOBAL_Control
0x180025ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ceb  cmp     rcx, rax
0x180025cee  jz      short loc_180025D13
0x180025cf0  test    byte ptr [rcx+1Ch], 1
0x180025cf4  jz      short loc_180025D13
0x180025cf6  cmp     byte ptr [rcx+19h], 2
0x180025cfa  jb      short loc_180025D13
0x180025cfc  lea     edx, [rbx+28h]
0x180025cff  lea     r9d, [rbx+57h]
0x180025d03  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025d0a  mov     rcx, [rcx+10h]
0x180025d0e  call    WPP_SF_D
0x180025d13  xorps   xmm0, xmm0
0x180025d16  movdqu  [rsp+0E8h+pExceptionObject], xmm0
0x180025d1c  mov     [rsp+0E8h+var_B0], rbx
0x180025d21  mov     [rsp+0E8h+var_A8], 57h ; 'W'
0x180025d29  mov     [rsp+0E8h+var_A4], 0FFFFFFFFh
0x180025d31  mov     [rsp+0E8h+var_A0], 50Dh
0x180025d39  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180025d40  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180025d45  call    _CxxThrowException_0
0x180025d4a  test    rdi, rdi
0x180025d4d  jnz     short loc_180025DBC
0x180025d4f  lea     rax, WPP_GLOBAL_Control
0x180025d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d5d  cmp     rcx, rax
0x180025d60  jz      short loc_180025D85
0x180025d62  test    byte ptr [rcx+1Ch], 1
0x180025d66  jz      short loc_180025D85
0x180025d68  cmp     byte ptr [rcx+19h], 2
0x180025d6c  jb      short loc_180025D85
0x180025d6e  lea     edx, [rdi+29h]
0x180025d71  lea     r9d, [rdi+57h]
0x180025d75  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025d7c  mov     rcx, [rcx+10h]
0x180025d80  call    WPP_SF_D
0x180025d85  xorps   xmm0, xmm0
0x180025d88  movdqu  [rsp+0E8h+var_98], xmm0
0x180025d8e  mov     [rsp+0E8h+var_88], rbx
0x180025d93  mov     [rsp+0E8h+var_80], 57h ; 'W'
0x180025d9b  mov     [rsp+0E8h+var_7C], 0FFFFFFFFh
0x180025da3  mov     [rsp+0E8h+var_78], 512h
0x180025dab  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180025db2  lea     rcx, [rsp+0E8h+var_98]; pExceptionObject
0x180025db7  call    _CxxThrowException_0
0x180025dbc  lea     rcx, [rsp+0E8h+var_48]
0x180025dc4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180025dc9  nop
0x180025dca  mov     rdx, rdi
0x180025dcd  lea     rcx, [rsp+0E8h+var_48]
0x180025dd5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180025dda  test    al, al
0x180025ddc  jnz     short loc_180025E59
0x180025dde  lea     rax, WPP_GLOBAL_Control
0x180025de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dec  cmp     rcx, rax
0x180025def  jz      short loc_180025E16
0x180025df1  test    byte ptr [rcx+1Ch], 1
0x180025df5  jz      short loc_180025E16
0x180025df7  cmp     byte ptr [rcx+19h], 2
0x180025dfb  jb      short loc_180025E16
0x180025dfd  mov     edx, 2Ah ; '*'
0x180025e02  lea     r9d, [rdx-1Ch]
0x180025e06  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180025e0d  mov     rcx, [rcx+10h]
0x180025e11  call    WPP_SF_D
0x180025e16  xorps   xmm0, xmm0
0x180025e19  movdqu  [rsp+0E8h+var_70], xmm0
0x180025e1f  mov     [rsp+0E8h+var_60], rbx
0x180025e27  mov     [rsp+0E8h+var_58], 0Eh
0x180025e32  mov     [rsp+0E8h+var_54], 0FFFFFFFFh
0x180025e3d  mov     [rsp+0E8h+var_50], 518h
0x180025e48  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180025e4f  lea     rcx, [rsp+0E8h+var_70]; pExceptionObject
0x180025e54  call    _CxxThrowException_0
0x180025e59  mov     rdx, rdi
0x180025e5c  lea     rcx, [rsp+0E8h+var_48]
0x180025e64  call    FullyQualifyFilePath
0x180025e69  mov     rdx, r14
0x180025e6c  lea     rcx, [rsp+0E8h+var_C8]; void *
0x180025e71  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x180025e76  nop
0x180025e77  xor     r9d, r9d; unsigned int
0x180025e7a  mov     r8, [rsp+0E8h+var_48]; wchar_t *
0x180025e82  mov     edx, r15d; unsigned int
0x180025e85  mov     rcx, [rsp+0E8h+var_C8]; this
0x180025e8a  call    ?LocalizeExportLog@LogHandle@@SAXPEAVSession@@KPEB_WK@Z; LogHandle::LocalizeExportLog(Session *,ulong,wchar_t const *,ulong)
0x180025e8f  mov     edi, ebx
0x180025e91  lea     rcx, [rsp+0E8h+var_C8]; void *
0x180025e96  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180025e9b  nop
0x180025e9c  lea     rcx, [rsp+0E8h+var_48]
0x180025ea4  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180025ea9  nop
0x180025eaa  jmp     short loc_180025EB5
0x180025eac  xor     ebx, ebx
0x180025eae  mov     edi, [rsp+0E8h+arg_18]
0x180025eb5  mov     ecx, edi; dwErrCode
0x180025eb7  call    cs:__imp_SetLastError
0x180025ebd  test    edi, edi
0x180025ebf  setz    bl
0x180025ec2  mov     eax, ebx
0x180025ec4  lea     r11, [rsp+0E8h+var_18]
0x180025ecc  mov     rbx, [r11+20h]
0x180025ed0  mov     rsi, [r11+28h]
0x180025ed4  mov     rsp, r11
0x180025ed7  pop     r15
0x180025ed9  pop     r14
0x180025edb  pop     rdi
0x180025edc  retn
```
