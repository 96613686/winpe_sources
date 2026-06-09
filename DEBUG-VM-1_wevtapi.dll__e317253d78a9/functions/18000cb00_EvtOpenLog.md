# EvtOpenLog

- ea: `0x18000cb00`
- end: `0x18000ce25`
- name: `EvtOpenLog`
- size: `805`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, LPCWSTR Path, DWORD Flags)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x18000a100`
- `0x18000bf84`
- `0x18000c404`
- `0x18000cb00`
- `0x180013f6c`
- `0x180021850`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
EVT_HANDLE __stdcall EvtOpenLog(EVT_HANDLE Session, LPCWSTR Path, DWORD Flags)
{
  __int64 v5; // r14
  __int64 v6; // r8
  int v7; // ecx
  __int64 v8; // rcx
  DWORD v9; // esi
  void *v10; // rsi
  wmi::RefBase *v12; // [rsp+30h] [rbp-E8h] BYREF
  void *v13; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-D8h] BYREF
  void *v15[2]; // [rsp+48h] [rbp-D0h] BYREF
  char v16; // [rsp+58h] [rbp-C0h] BYREF
  __int128 pExceptionObject; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+78h] [rbp-A0h]
  int v19; // [rsp+80h] [rbp-98h]
  int v20; // [rsp+84h] [rbp-94h]
  int v21; // [rsp+88h] [rbp-90h]
  __int128 v22; // [rsp+90h] [rbp-88h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-78h]
  int v24; // [rsp+A8h] [rbp-70h]
  int v25; // [rsp+ACh] [rbp-6Ch]
  int v26; // [rsp+B0h] [rbp-68h]
  __int128 v27; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-50h]
  int v29; // [rsp+D0h] [rbp-48h]
  int v30; // [rsp+D4h] [rbp-44h]
  int v31; // [rsp+D8h] [rbp-40h]
  DWORD v32; // [rsp+130h] [rbp+18h] BYREF
  __int64 v33; // [rsp+138h] [rbp+20h] BYREF

  v32 = Flags;
  v5 = 0;
  v33 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  if ( Flags - 1 > 1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v18 = 0;
    v19 = 87;
    v20 = -1;
    v21 = 1057;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !Path )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    v22 = 0;
    v23 = 0;
    v24 = 87;
    v25 = -1;
    v26 = 1062;
    throw (EvtException *)&v22;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v15);
  v6 = -1;
  do
    ++v6;
  while ( Path[v6] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v15,
                           Path,
                           v6) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 14);
    }
    v27 = 0;
    v28 = 0;
    v29 = 14;
    v30 = -1;
    v31 = 1068;
    throw (EvtException *)&v27;
  }
  if ( (Flags & 2) != 0 )
    FullyQualifyFilePath((__int64)v15, Path);
  GetSession(&v12);
  v13 = v15[0];
  v14 = 0;
  v8 = HandleTable::Emplace<LogHandle,wmi::AutoRef<Session> &,wchar_t const *,unsigned long &>(
         v7,
         (unsigned int)&v14,
         (unsigned int)&v12,
         (unsigned int)&v13,
         (__int64)&v32);
  if ( v8 )
  {
    *(_QWORD *)(v8 + 16) = v14;
    _InterlockedAdd((volatile signed __int32 *)(v8 + 8), 1u);
    _InterlockedAdd((volatile signed __int32 *)(v8 + 24), 1u);
    v5 = v8;
    v33 = v8;
    v13 = 0;
    EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v13);
    v9 = 0;
  }
  else
  {
    v9 = 14;
  }
  if ( v12 )
    wmi::RefBase::Release(v12);
  v12 = 0;
  if ( v15[0] != &v16 )
    operator delete(v15[0]);
  SetLastError(v9);
  if ( v5 )
  {
    v10 = *(void **)(v5 + 16);
    v33 = 0;
    *(_BYTE *)(v5 + 29) = 1;
  }
  else
  {
    v10 = 0;
  }
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v33);
  return v10;
}

```

## disassembly

```asm
0x18000cb00  mov     rax, rsp
0x18000cb03  mov     [rax+8], rbx
0x18000cb07  mov     [rax+18h], r8d
0x18000cb0b  push    rsi
0x18000cb0c  push    rdi
0x18000cb0d  push    r12
0x18000cb0f  push    r14
0x18000cb11  push    r15
0x18000cb13  sub     rsp, 0F0h
0x18000cb1a  mov     esi, r8d
0x18000cb1d  mov     r15, rdx
0x18000cb20  mov     r12, rcx
0x18000cb23  xor     ebx, ebx
0x18000cb25  mov     r14d, ebx
0x18000cb28  mov     [rax+20h], rbx
0x18000cb2c  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18000cb31  lea     eax, [rsi-1]
0x18000cb34  lea     edi, [rbx+1]
0x18000cb37  cmp     eax, edi
0x18000cb39  ja      loc_18000CC3F
0x18000cb3f  test    r15, r15
0x18000cb42  jz      loc_18000CCB7
0x18000cb48  lea     rcx, [rsp+118h+var_D0]
0x18000cb4d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000cb52  nop
0x18000cb53  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cb57  inc     r8
0x18000cb5a  cmp     [r15+r8*2], bx
0x18000cb5f  jnz     short loc_18000CB57
0x18000cb61  mov     rdx, r15
0x18000cb64  lea     rcx, [rsp+118h+var_D0]
0x18000cb69  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000cb6e  test    al, al
0x18000cb70  jz      loc_18000CD39
0x18000cb76  test    sil, 2
0x18000cb7a  jnz     loc_18000CDBF
0x18000cb80  mov     rdx, r12
0x18000cb83  lea     rcx, [rsp+118h+var_E8]; void *
0x18000cb88  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18000cb8d  nop
0x18000cb8e  mov     rax, [rsp+118h+var_D0]
0x18000cb93  mov     [rsp+118h+var_E0], rax
0x18000cb98  mov     [rsp+118h+var_D8], rbx
0x18000cb9d  lea     rax, [rsp+118h+arg_10]
0x18000cba5  mov     [rsp+118h+var_F8], rax
0x18000cbaa  lea     r9, [rsp+118h+var_E0]
0x18000cbaf  lea     r8, [rsp+118h+var_E8]
0x18000cbb4  lea     rdx, [rsp+118h+var_D8]
0x18000cbb9  call    ??$Emplace@VLogHandle@@AEAV?$AutoRef@VSession@@@wmi@@PEB_WAEAK@HandleTable@@QEAAPEAVLogHandle@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@$$QEAPEB_WAEAK@Z; HandleTable::Emplace<LogHandle,wmi::AutoRef<Session> &,wchar_t const *,ulong &>(void * &,wmi::AutoRef<Session> &,wchar_t const * &&,ulong &)
0x18000cbbe  mov     rcx, rax
0x18000cbc1  test    rax, rax
0x18000cbc4  jnz     loc_18000CDD1
0x18000cbca  lea     esi, [rax+0Eh]
0x18000cbcd  mov     rcx, [rsp+118h+var_E8]; this
0x18000cbd2  test    rcx, rcx
0x18000cbd5  jz      short loc_18000CBDC
0x18000cbd7  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000cbdc  mov     [rsp+118h+var_E8], rbx
0x18000cbe1  lea     rax, [rsp+118h+var_C0]
0x18000cbe6  mov     rcx, [rsp+118h+var_D0]; void *
0x18000cbeb  cmp     rcx, rax
0x18000cbee  jz      short loc_18000CBF6
0x18000cbf0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cbf5  nop
0x18000cbf6  mov     ecx, esi; dwErrCode
0x18000cbf8  call    cs:__imp_SetLastError
0x18000cbfe  test    r14, r14
0x18000cc01  jz      loc_18000CE1C
0x18000cc07  mov     rsi, [r14+10h]
0x18000cc0b  mov     [rsp+118h+arg_18], rbx
0x18000cc13  xchg    dil, [r14+1Dh]
0x18000cc17  lea     rcx, [rsp+118h+arg_18]; this
0x18000cc1f  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18000cc24  mov     rax, rsi
0x18000cc27  mov     rbx, [rsp+118h+arg_0]
0x18000cc2f  add     rsp, 0F0h
0x18000cc36  pop     r15
0x18000cc38  pop     r14
0x18000cc3a  pop     r12
0x18000cc3c  pop     rdi
0x18000cc3d  pop     rsi
0x18000cc3e  retn
0x18000cc3f  lea     rax, WPP_GLOBAL_Control
0x18000cc46  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc4d  cmp     rcx, rax
0x18000cc50  jz      short loc_18000CC77
0x18000cc52  test    [rcx+1Ch], dil
0x18000cc56  jz      short loc_18000CC77
0x18000cc58  cmp     byte ptr [rcx+19h], 2
0x18000cc5c  jb      short loc_18000CC77
0x18000cc5e  mov     edx, 1Fh
0x18000cc63  lea     r9d, [rdx+38h]
0x18000cc67  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000cc6e  mov     rcx, [rcx+10h]
0x18000cc72  call    WPP_SF_D
0x18000cc77  xorps   xmm0, xmm0
0x18000cc7a  movdqu  [rsp+118h+pExceptionObject], xmm0
0x18000cc80  mov     [rsp+118h+var_A0], rbx
0x18000cc85  mov     [rsp+118h+var_98], 57h ; 'W'
0x18000cc90  mov     [rsp+118h+var_94], 0FFFFFFFFh
0x18000cc9b  mov     [rsp+118h+var_90], 421h
0x18000cca6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000ccad  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18000ccb2  call    _CxxThrowException_0
0x18000ccb7  lea     rax, WPP_GLOBAL_Control
0x18000ccbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc5  cmp     rcx, rax
0x18000ccc8  jz      short loc_18000CCEF
0x18000ccca  test    [rcx+1Ch], dil
0x18000ccce  jz      short loc_18000CCEF
0x18000ccd0  cmp     byte ptr [rcx+19h], 2
0x18000ccd4  jb      short loc_18000CCEF
0x18000ccd6  mov     edx, 20h ; ' '
0x18000ccdb  lea     r9d, [rdx+37h]
0x18000ccdf  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000cce6  mov     rcx, [rcx+10h]
0x18000ccea  call    WPP_SF_D
0x18000ccef  xorps   xmm0, xmm0
0x18000ccf2  movdqu  [rsp+118h+var_88], xmm0
0x18000ccfb  mov     [rsp+118h+var_78], rbx
0x18000cd03  mov     [rsp+118h+var_70], 57h ; 'W'
0x18000cd0e  mov     [rsp+118h+var_6C], 0FFFFFFFFh
0x18000cd19  mov     [rsp+118h+var_68], 426h
0x18000cd24  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000cd2b  lea     rcx, [rsp+118h+var_88]; pExceptionObject
0x18000cd33  call    _CxxThrowException_0
0x18000cd39  lea     rax, WPP_GLOBAL_Control
0x18000cd40  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd47  cmp     rcx, rax
0x18000cd4a  jz      short loc_18000CD75
0x18000cd4c  test    [rcx+1Ch], dil
0x18000cd50  jz      short loc_18000CD75
0x18000cd52  cmp     byte ptr [rcx+19h], 2
0x18000cd56  jb      short loc_18000CD75
0x18000cd58  mov     edx, 21h ; '!'
0x18000cd5d  lea     esi, [rdx-13h]
0x18000cd60  mov     r9d, esi
0x18000cd63  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18000cd6a  mov     rcx, [rcx+10h]
0x18000cd6e  call    WPP_SF_D
0x18000cd73  jmp     short loc_18000CD7A
0x18000cd75  mov     esi, 0Eh
0x18000cd7a  xorps   xmm0, xmm0
0x18000cd7d  movdqu  [rsp+118h+var_60], xmm0
0x18000cd86  mov     [rsp+118h+var_50], rbx
0x18000cd8e  mov     [rsp+118h+var_48], esi
0x18000cd95  mov     [rsp+118h+var_44], 0FFFFFFFFh
0x18000cda0  mov     [rsp+118h+var_40], 42Ch
0x18000cdab  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000cdb2  lea     rcx, [rsp+118h+var_60]; pExceptionObject
0x18000cdba  call    _CxxThrowException_0
0x18000cdbf  mov     rdx, r15
0x18000cdc2  lea     rcx, [rsp+118h+var_D0]
0x18000cdc7  call    FullyQualifyFilePath
0x18000cdcc  jmp     loc_18000CB80
0x18000cdd1  mov     rax, [rsp+118h+var_D8]
0x18000cdd6  mov     [rcx+10h], rax
0x18000cdda  lock add [rcx+8], edi
0x18000cdde  lock add [rcx+18h], edi
0x18000cde2  mov     r14, rcx
0x18000cde5  mov     [rsp+118h+arg_18], rcx
0x18000cded  mov     [rsp+118h+var_E0], rbx
0x18000cdf2  lea     rcx, [rsp+118h+var_E0]; this
0x18000cdf7  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18000cdfc  mov     esi, ebx
0x18000cdfe  jmp     loc_18000CBCD
0x18000ce03  xor     ebx, ebx
0x18000ce05  lea     edi, [rbx+1]
0x18000ce08  mov     esi, [rsp+118h+arg_10]
0x18000ce0f  mov     r14, [rsp+118h+arg_18]
0x18000ce17  jmp     loc_18000CBF6
0x18000ce1c  mov     rsi, rbx
0x18000ce1f  jmp     loc_18000CC17
```
