# WinSAT::StorageDevice::OpenTempFile(ulong,unsigned __int64,unsigned __int64,unsigned __int64 &,unsigned __int64 &,ulong,bool,bool,void *)

- ea: `0x140061600`
- end: `0x140061aab`
- name: `?OpenTempFile@StorageDevice@WinSAT@@QEAA_NK_K0AEA_K1K_N2PEAX@Z`
- size: `1195`
- prototype: `char __fastcall(WinSAT::StorageDevice *this, unsigned int, LARGE_INTEGER, unsigned __int64, unsigned __int64 *, LARGE_INTEGER *, bool, bool, bool, void *)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14006bb04`
- `0x14006c494`
- `0x14006c890`

## callees

- `0x140004348`
- `0x140005f4c`
- `0x140016480`
- `0x140016d04`
- `0x140017af0`
- `0x1400478c0`
- `0x14004fce4`
- `0x140060688`
- `0x140060888`
- `0x14006099c`
- `0x140061238`
- `0x140061270`
- `0x140061600`
- `0x140061f60`
- `0x14006220c`
- `0x14006237c`
- `0x140062a38`

## import_xrefs

- `ADVAPI32!ImpersonateSelf` at `0x140061761`
- `ADVAPI32!ImpersonateSelf` at `0x140061761`
- `KERNEL32!GetTickCount` at `0x140061983`
- `KERNEL32!GetTickCount` at `0x140061983`
- `KERNEL32!DeviceIoControl` at `0x1400617f8`
- `KERNEL32!DeviceIoControl` at `0x1400617f8`
- `KERNEL32!SetEndOfFile` at `0x14006182f`
- `KERNEL32!SetEndOfFile` at `0x14006182f`
- `KERNEL32!CloseHandle` at `0x1400618f0`
- `KERNEL32!CloseHandle` at `0x140061a14`
- `KERNEL32!CloseHandle` at `0x1400618f0`
- `KERNEL32!CloseHandle` at `0x140061a14`
- `KERNEL32!SetFileValidData` at `0x1400618ba`
- `KERNEL32!SetFileValidData` at `0x1400618ba`
- `KERNEL32!SetFilePointerEx` at `0x14006181d`
- `KERNEL32!SetFilePointerEx` at `0x140061952`
- `KERNEL32!SetFilePointerEx` at `0x14006181d`
- `KERNEL32!SetFilePointerEx` at `0x140061952`
- `KERNEL32!VirtualAlloc` at `0x140061971`
- `KERNEL32!VirtualAlloc` at `0x140061971`
- `KERNEL32!VirtualFree` at `0x1400619f4`
- `KERNEL32!VirtualFree` at `0x140061a0a`
- `KERNEL32!VirtualFree` at `0x1400619f4`
- `KERNEL32!VirtualFree` at `0x140061a0a`
- `KERNEL32!WriteFile` at `0x1400619d7`
- `KERNEL32!WriteFile` at `0x1400619d7`
- `KERNEL32!SetLastError` at `0x140061659`
- `KERNEL32!SetLastError` at `0x140061659`
- `ntdll!RtlRandom` at `0x140061993`
- `ntdll!RtlRandom` at `0x140061993`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WinSAT::StorageDevice::OpenTempFile(
        WinSAT::StorageDevice *this,
        unsigned int a2,
        LARGE_INTEGER a3,
        unsigned __int64 a4,
        unsigned __int64 *a5,
        LARGE_INTEGER *a6,
        bool a7,
        bool a8,
        bool a9,
        void *a10)
{
  DWORD v14; // ecx
  __int64 v16; // rbx
  const unsigned __int16 *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  unsigned int v20; // edx
  WinSAT::ManagePrivilege *v21; // rcx
  int v22; // r8d
  char v23; // al
  WinSAT::StorageDevice *v24; // rcx
  unsigned __int64 *p_QuadPart; // rax
  bool v26; // r9
  unsigned __int64 *v27; // r8
  unsigned __int64 v28; // rdx
  unsigned __int64 *v29; // rsi
  __int64 v30; // rax
  WinSAT::StorageDevice *v31; // rcx
  char v32; // al
  _DWORD *v33; // r14
  __int64 i; // rsi
  unsigned __int64 j; // rsi
  DWORD v36; // r15d
  char v37; // al
  _WORD v38[2]; // [rsp+40h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v40; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v41[2]; // [rsp+50h] [rbp-10h] BYREF
  ULONG InBuffer; // [rsp+90h] [rbp+30h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v40,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v41,
    8);
  a7 = 0;
  v38[0] = 0;
  if ( !*((_QWORD *)this + 10) )
  {
    v14 = 6;
LABEL_3:
    SetLastError(v14);
    goto LABEL_4;
  }
  if ( *((_QWORD *)this + 9) != -1 )
    WinSAT::StorageDevice::Close(this);
  if ( **((_BYTE **)this + 12) )
  {
    v16 = *((_QWORD *)this + 3);
    v17 = mlib::MUISpf_((mlib *)"base\\winsat\\storage\\storedev.cpp", (const char *)0x26C, 428, a3.LowPart, a4);
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16 + 240, v17);
    std::endl(v18);
  }
  if ( !(unsigned __int8)WinSAT::StorageDevice::FindDriveContainingOffset(this, v41, &a7, a2, a4, 1) )
    goto LABEL_4;
  if ( !a7 )
  {
    v14 = 33619972;
    goto LABEL_3;
  }
  if ( (unsigned int)GetTemporaryFile(L"Disk", L"tmp", *(_QWORD *)(v41[0] + 24LL), &v40) )
    goto LABEL_4;
  v19 = v40;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    (char *)this + 32,
    v40);
  *((_BYTE *)this + 112) = 1;
  if ( !ImpersonateSelf(SecurityImpersonation) )
    goto LABEL_4;
  LOBYTE(v38[0]) = 1;
  if ( WinSAT::ManagePrivilege::AdjustProcessPrivilege(v21, v20, v22) )
    goto LABEL_4;
  HIBYTE(v38[0]) = 1;
  *((_BYTE *)this + 112) = 0;
  v23 = WinSAT::StorageDevice::pOpen(this, &v40, 3221225472LL, 0);
  *((_BYTE *)this + 112) = 1;
  if ( !v23 )
    goto LABEL_4;
  a7 = 0;
  if ( !WinSAT::StorageDevice::IsFileCompressed(this, &a7) )
    goto LABEL_4;
  if ( a7 )
  {
    LOWORD(InBuffer) = 0;
    BytesReturned = 0;
    if ( !DeviceIoControl(*((HANDLE *)this + 9), 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      v14 = 33619973;
      goto LABEL_3;
    }
  }
  *((LARGE_INTEGER *)this + 5) = a3;
  if ( !SetFilePointerEx(*((HANDLE *)this + 9), a3, 0, 0) )
    goto LABEL_4;
  if ( !SetEndOfFile(*((HANDLE *)this + 9)) )
  {
    v14 = 33619978;
    goto LABEL_3;
  }
  v24 = this;
  if ( a8 )
  {
    p_QuadPart = (unsigned __int64 *)&a6->QuadPart;
    v26 = 0;
    v27 = a5;
    v28 = a4;
  }
  else
  {
    LOBYTE(InBuffer) = 0;
    v29 = a5;
    if ( !WinSAT::StorageDevice::IsFileInOnePiece(this, (bool *)&InBuffer, a5) )
      goto LABEL_4;
    p_QuadPart = (unsigned __int64 *)&a6->QuadPart;
    if ( (_BYTE)InBuffer )
    {
      *a6 = a3;
      goto LABEL_31;
    }
    v26 = 1;
    v27 = v29;
    v28 = *v29;
    v24 = this;
  }
  if ( !WinSAT::StorageDevice::SetFileLocation(v24, v28, v27, v26, a10, p_QuadPart) )
  {
    v14 = 33619970;
    goto LABEL_3;
  }
LABEL_31:
  if ( !SetFileValidData(*((HANDLE *)this + 9), *((_QWORD *)this + 5)) && **((_BYTE **)this + 12) )
  {
    v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            *((_QWORD *)this + 3) + 240LL,
            L"Warning:  Could not pre grow file for assessment, may take performance hit.");
    std::endl(v30);
  }
  CloseHandle(*((HANDLE *)this + 9));
  *((_QWORD *)this + 9) = -1;
  *((_BYTE *)this + 93) = 0;
  WinSAT::ManagePrivilege::Release((WinSAT::ManagePrivilege *)v38);
  if ( a9 )
  {
    BytesReturned = 0;
    InBuffer = 0;
    *((_BYTE *)this + 112) = 0;
    v32 = WinSAT::StorageDevice::pOpen(this, &v40, 3221225472LL, 0x20000000);
    *((_BYTE *)this + 112) = 1;
    if ( !v32 )
      goto LABEL_4;
    if ( !SetFilePointerEx(*((HANDLE *)this + 9), 0, 0, 0) )
      goto LABEL_4;
    v33 = VirtualAlloc(0, 0x100000u, 0x1000u, 4u);
    if ( !v33 )
      goto LABEL_4;
    InBuffer = GetTickCount();
    for ( i = 0; i != 0x40000; ++i )
      v33[i] = RtlRandom(&InBuffer);
    for ( j = *((_QWORD *)this + 5); j; j -= v36 )
    {
      v36 = j;
      if ( j >= 0x100000 )
        v36 = 0x100000;
      if ( !WriteFile(*((HANDLE *)this + 9), v33, v36, &BytesReturned, 0) )
      {
        VirtualFree(v33, 0, 0x8000u);
        goto LABEL_4;
      }
    }
    VirtualFree(v33, 0, 0x8000u);
    CloseHandle(*((HANDLE *)this + 9));
    *((_QWORD *)this + 9) = -1;
    *((_BYTE *)this + 93) = 0;
  }
  if ( WinSAT::StorageDevice::PreCopyOnWriteFile(v31, *(const unsigned __int16 **)(v19 + 24))
    || (*((_BYTE *)this + 112) = 0,
        v37 = WinSAT::StorageDevice::pOpen(this, &v40, 3221225472LL, 1610612736),
        *((_BYTE *)this + 112) = 1,
        !v37)
    || !WinSAT::StorageDevice::IsFileCompressed(this, &a7) )
  {
LABEL_4:
    WinSAT::ManagePrivilege::Release((WinSAT::ManagePrivilege *)v38);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v41);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v40);
    return 0;
  }
  if ( a7 )
  {
    v14 = 33619974;
    goto LABEL_3;
  }
  *((_BYTE *)this + 93) = 1;
  WinSAT::ManagePrivilege::Release((WinSAT::ManagePrivilege *)v38);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v41);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v40);
  return 1;
}

```

## disassembly

```asm
0x140061600  mov     [rsp-28h+arg_8], rbx
0x140061605  mov     [rsp-28h+arg_10], rsi
0x14006160a  push    rbp
0x14006160b  push    rdi
0x14006160c  push    r12
0x14006160e  push    r14
0x140061610  push    r15
0x140061612  mov     rbp, rsp
0x140061615  sub     rsp, 60h
0x140061619  mov     r15, r9
0x14006161c  mov     r14, r8
0x14006161f  mov     esi, edx
0x140061621  mov     rdi, rcx
0x140061624  mov     edx, 104h
0x140061629  lea     rcx, [rbp+var_18]
0x14006162d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140061632  nop
0x140061633  mov     edx, 8
0x140061638  lea     rcx, [rbp+var_10]
0x14006163c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140061641  nop
0x140061642  xor     r12d, r12d
0x140061645  mov     [rbp+arg_30], r12b
0x140061649  mov     [rbp+var_20], r12w
0x14006164e  cmp     [rdi+50h], r12
0x140061652  jnz     short loc_140061698
0x140061654  lea     ecx, [r12+6]; dwErrCode
0x140061659  call    cs:__imp_SetLastError
0x14006165f  nop
0x140061660  lea     rcx, [rbp+var_20]; this
0x140061664  call    ?Release@ManagePrivilege@WinSAT@@QEAA_NXZ; WinSAT::ManagePrivilege::Release(void)
0x140061669  nop
0x14006166a  lea     rcx, [rbp+var_10]
0x14006166e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140061673  nop
0x140061674  lea     rcx, [rbp+var_18]
0x140061678  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14006167d  xor     al, al
0x14006167f  lea     r11, [rsp+60h+var_s0]
0x140061684  mov     rbx, [r11+38h]
0x140061688  mov     rsi, [r11+40h]
0x14006168c  mov     rsp, r11
0x14006168f  pop     r15
0x140061691  pop     r14
0x140061693  pop     r12
0x140061695  pop     rdi
0x140061696  pop     rbp
0x140061697  retn
0x140061698  cmp     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x14006169d  jz      short loc_1400616A7
0x14006169f  mov     rcx, rdi; this
0x1400616a2  call    ?Close@StorageDevice@WinSAT@@QEAAXXZ; WinSAT::StorageDevice::Close(void)
0x1400616a7  mov     rax, [rdi+60h]
0x1400616ab  cmp     [rax], r12b
0x1400616ae  jz      short loc_1400616EA
0x1400616b0  mov     rbx, [rdi+18h]
0x1400616b4  mov     r8d, 1ACh; int
0x1400616ba  mov     [rsp+60h+lpOutBuffer], r15
0x1400616bf  mov     r9, r14; unsigned __int16
0x1400616c2  mov     edx, 26Ch; char *
0x1400616c7  lea     rcx, aBaseWinsatStor_1; "base\\winsat\\storage\\storedev.cpp"
0x1400616ce  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x1400616d3  mov     rdx, rax
0x1400616d6  lea     rcx, [rbx+0F0h]
0x1400616dd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400616e2  mov     rcx, rax
0x1400616e5  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x1400616ea  mov     byte ptr [rsp+60h+nOutBufferSize], 1
0x1400616ef  mov     [rsp+60h+lpOutBuffer], r15
0x1400616f4  mov     r9d, esi
0x1400616f7  lea     r8, [rbp+arg_30]
0x1400616fb  lea     rdx, [rbp+var_10]
0x1400616ff  mov     rcx, rdi
0x140061702  call    ?FindDriveContainingOffset@StorageDevice@WinSAT@@AEBA_NAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEA_NK_K_N@Z; WinSAT::StorageDevice::FindDriveContainingOffset(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,bool &,ulong,unsigned __int64,bool)
0x140061707  test    al, al
0x140061709  jz      loc_140061660
0x14006170f  cmp     [rbp+arg_30], r12b
0x140061713  jnz     short loc_14006171F
0x140061715  mov     ecx, 2010004h
0x14006171a  jmp     loc_140061659
0x14006171f  lea     r9, [rbp+var_18]
0x140061723  mov     r8, [rbp+var_10]
0x140061727  mov     r8, [r8+18h]
0x14006172b  lea     rdx, aTmp_0; "tmp"
0x140061732  lea     rcx, aDisk; "Disk"
0x140061739  call    ?GetTemporaryFile@@YAKPEBG00AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetTemporaryFile(ushort const *,ushort const *,ushort const *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x14006173e  test    eax, eax
0x140061740  jnz     loc_140061660
0x140061746  lea     rcx, [rdi+20h]
0x14006174a  mov     rbx, [rbp+var_18]
0x14006174e  mov     rdx, rbx
0x140061751  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140061756  mov     byte ptr [rdi+70h], 1
0x14006175a  mov     esi, 2
0x14006175f  mov     ecx, esi; ImpersonationLevel
0x140061761  call    cs:__imp_ImpersonateSelf
0x140061767  test    eax, eax
0x140061769  jz      loc_140061660
0x14006176f  mov     byte ptr [rbp+var_20], 1
0x140061773  call    ?AdjustProcessPrivilege@ManagePrivilege@WinSAT@@AEAAKKH@Z; WinSAT::ManagePrivilege::AdjustProcessPrivilege(ulong,int)
0x140061778  test    eax, eax
0x14006177a  jnz     loc_140061660
0x140061780  mov     byte ptr [rbp+var_20+1], 1
0x140061784  mov     [rdi+70h], r12b
0x140061788  xor     r9d, r9d
0x14006178b  mov     r8d, 0C0000000h
0x140061791  lea     rdx, [rbp+var_18]
0x140061795  mov     rcx, rdi
0x140061798  call    ?pOpen@StorageDevice@WinSAT@@AEAA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@KK@Z; WinSAT::StorageDevice::pOpen(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong)
0x14006179d  mov     byte ptr [rdi+70h], 1
0x1400617a1  test    al, al
0x1400617a3  jz      loc_140061660
0x1400617a9  mov     [rbp+arg_30], r12b
0x1400617ad  lea     rdx, [rbp+arg_30]; bool *
0x1400617b1  mov     rcx, rdi; this
0x1400617b4  call    ?IsFileCompressed@StorageDevice@WinSAT@@AEBA_NAEA_N@Z; WinSAT::StorageDevice::IsFileCompressed(bool &)
0x1400617b9  test    al, al
0x1400617bb  jz      loc_140061660
0x1400617c1  cmp     [rbp+arg_30], r12b
0x1400617c5  jz      short loc_14006180C
0x1400617c7  mov     word ptr [rbp+InBuffer], r12w
0x1400617cc  mov     [rbp+BytesReturned], r12d
0x1400617d0  mov     [rsp+60h+lpOverlapped], r12; lpOverlapped
0x1400617d5  lea     rax, [rbp+BytesReturned]
0x1400617d9  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x1400617de  mov     [rsp+60h+nOutBufferSize], r12d; nOutBufferSize
0x1400617e3  mov     [rsp+60h+lpOutBuffer], r12; lpOutBuffer
0x1400617e8  mov     r9d, esi; nInBufferSize
0x1400617eb  lea     r8, [rbp+InBuffer]; lpInBuffer
0x1400617ef  mov     edx, 9C040h; dwIoControlCode
0x1400617f4  mov     rcx, [rdi+48h]; hDevice
0x1400617f8  call    cs:__imp_DeviceIoControl
0x1400617fe  test    eax, eax
0x140061800  jnz     short loc_14006180C
0x140061802  mov     ecx, 2010005h
0x140061807  jmp     loc_140061659
0x14006180c  mov     [rdi+28h], r14
0x140061810  xor     r9d, r9d; dwMoveMethod
0x140061813  xor     r8d, r8d; lpNewFilePointer
0x140061816  mov     rdx, r14; liDistanceToMove
0x140061819  mov     rcx, [rdi+48h]; hFile
0x14006181d  call    cs:__imp_SetFilePointerEx
0x140061823  test    eax, eax
0x140061825  jz      loc_140061660
0x14006182b  mov     rcx, [rdi+48h]; hFile
0x14006182f  call    cs:__imp_SetEndOfFile
0x140061835  test    eax, eax
0x140061837  jnz     short loc_140061843
0x140061839  mov     ecx, 201000Ah
0x14006183e  jmp     loc_140061659
0x140061843  mov     rcx, rdi; this
0x140061846  cmp     [rbp+arg_38], r12b
0x14006184a  jz      short loc_14006187B
0x14006184c  mov     rax, [rbp+arg_28]
0x140061850  xor     r9d, r9d; bool
0x140061853  mov     r8, [rbp+arg_20]; unsigned __int64 *
0x140061857  mov     rdx, r15; unsigned __int64
0x14006185a  mov     qword ptr [rsp+60h+nOutBufferSize], rax; unsigned __int64 *
0x14006185f  mov     rax, [rbp+arg_48]
0x140061863  mov     [rsp+60h+lpOutBuffer], rax; void *
0x140061868  call    ?SetFileLocation@StorageDevice@WinSAT@@AEBA_N_KAEA_K_NPEAX1@Z; WinSAT::StorageDevice::SetFileLocation(unsigned __int64,unsigned __int64 &,bool,void *,unsigned __int64 &)
0x14006186d  test    al, al
0x14006186f  jnz     short loc_1400618B2
0x140061871  mov     ecx, 2010002h
0x140061876  jmp     loc_140061659
0x14006187b  mov     byte ptr [rbp+InBuffer], r12b
0x14006187f  mov     rsi, [rbp+arg_20]
0x140061883  mov     r8, rsi; unsigned __int64 *
0x140061886  lea     rdx, [rbp+InBuffer]; bool *
0x14006188a  call    ?IsFileInOnePiece@StorageDevice@WinSAT@@AEAA_NAEA_NAEA_K@Z; WinSAT::StorageDevice::IsFileInOnePiece(bool &,unsigned __int64 &)
0x14006188f  test    al, al
0x140061891  jz      loc_140061660
0x140061897  mov     rax, [rbp+arg_28]
0x14006189b  cmp     byte ptr [rbp+InBuffer], r12b
0x14006189f  jnz     short loc_1400618AF
0x1400618a1  mov     r9b, 1
0x1400618a4  mov     r8, rsi
0x1400618a7  mov     rdx, [rsi]
0x1400618aa  mov     rcx, rdi
0x1400618ad  jmp     short loc_14006185A
0x1400618af  mov     [rax], r14
0x1400618b2  mov     rdx, [rdi+28h]; ValidDataLength
0x1400618b6  mov     rcx, [rdi+48h]; hFile
0x1400618ba  call    cs:__imp_SetFileValidData
0x1400618c0  test    eax, eax
0x1400618c2  jnz     short loc_1400618EC
0x1400618c4  mov     rax, [rdi+60h]
0x1400618c8  cmp     [rax], r12b
0x1400618cb  jz      short loc_1400618EC
0x1400618cd  mov     rcx, [rdi+18h]
0x1400618d1  add     rcx, 0F0h
0x1400618d8  lea     rdx, aWarningCouldNo; "Warning:  Could not pre grow file for a"...
0x1400618df  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400618e4  mov     rcx, rax
0x1400618e7  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x1400618ec  mov     rcx, [rdi+48h]; hObject
0x1400618f0  call    cs:__imp_CloseHandle
0x1400618f6  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x1400618fe  mov     [rdi+5Dh], r12b
0x140061902  lea     rcx, [rbp+var_20]; this
0x140061906  call    ?Release@ManagePrivilege@WinSAT@@QEAA_NXZ; WinSAT::ManagePrivilege::Release(void)
0x14006190b  cmp     [rbp+arg_40], r12b
0x14006190f  jz      loc_140061A26
0x140061915  mov     [rbp+BytesReturned], r12d
0x140061919  mov     [rbp+InBuffer], r12d
0x14006191d  mov     [rdi+70h], r12b
0x140061921  mov     r9d, 20000000h
0x140061927  mov     r8d, 0C0000000h
0x14006192d  lea     rdx, [rbp+var_18]
0x140061931  mov     rcx, rdi
0x140061934  call    ?pOpen@StorageDevice@WinSAT@@AEAA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@KK@Z; WinSAT::StorageDevice::pOpen(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong)
0x140061939  mov     byte ptr [rdi+70h], 1
0x14006193d  test    al, al
0x14006193f  jz      loc_140061660
0x140061945  mov     rdx, r12; liDistanceToMove
0x140061948  xor     r9d, r9d; dwMoveMethod
0x14006194b  xor     r8d, r8d; lpNewFilePointer
0x14006194e  mov     rcx, [rdi+48h]; hFile
0x140061952  call    cs:__imp_SetFilePointerEx
0x140061958  test    eax, eax
0x14006195a  jz      loc_140061660
0x140061960  mov     edx, 100000h; dwSize
0x140061965  xor     ecx, ecx; lpAddress
0x140061967  lea     r9d, [rcx+4]; flProtect
0x14006196b  mov     r8d, 1000h; flAllocationType
0x140061971  call    cs:__imp_VirtualAlloc
0x140061977  mov     r14, rax
0x14006197a  test    rax, rax
0x14006197d  jz      loc_140061660
0x140061983  call    cs:__imp_GetTickCount
0x140061989  mov     [rbp+InBuffer], eax
0x14006198c  mov     rsi, r12
0x14006198f  lea     rcx, [rbp+InBuffer]; Seed
0x140061993  call    cs:__imp_RtlRandom
0x140061999  mov     [r14+rsi*4], eax
0x14006199d  inc     rsi
0x1400619a0  cmp     rsi, 40000h
0x1400619a7  jnz     short loc_14006198F
0x1400619a9  mov     rsi, [rdi+28h]
0x1400619ad  test    rsi, rsi
0x1400619b0  jz      short loc_1400619FF
0x1400619b2  cmp     rsi, 100000h
0x1400619b9  mov     r15d, esi
0x1400619bc  jb      short loc_1400619C4
0x1400619be  mov     r15d, 100000h
0x1400619c4  mov     [rsp+60h+lpOutBuffer], r12; lpOverlapped
0x1400619c9  lea     r9, [rbp+BytesReturned]; lpNumberOfBytesWritten
0x1400619cd  mov     r8d, r15d; nNumberOfBytesToWrite
0x1400619d0  mov     rdx, r14; lpBuffer
0x1400619d3  mov     rcx, [rdi+48h]; hFile
0x1400619d7  call    cs:__imp_WriteFile
0x1400619dd  test    eax, eax
0x1400619df  jz      short loc_1400619E9
0x1400619e1  mov     eax, r15d
0x1400619e4  sub     rsi, rax
0x1400619e7  jmp     short loc_1400619AD
0x1400619e9  xor     edx, edx; dwSize
0x1400619eb  mov     r8d, 8000h; dwFreeType
0x1400619f1  mov     rcx, r14; lpAddress
0x1400619f4  call    cs:__imp_VirtualFree
0x1400619fa  jmp     loc_140061660
0x1400619ff  xor     edx, edx; dwSize
0x140061a01  mov     r8d, 8000h; dwFreeType
0x140061a07  mov     rcx, r14; lpAddress
0x140061a0a  call    cs:__imp_VirtualFree
0x140061a10  mov     rcx, [rdi+48h]; hObject
0x140061a14  call    cs:__imp_CloseHandle
0x140061a1a  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x140061a22  mov     [rdi+5Dh], r12b
0x140061a26  mov     rdx, [rbx+18h]; unsigned __int16 *
0x140061a2a  call    ?PreCopyOnWriteFile@StorageDevice@WinSAT@@AEAAKPEBG@Z; WinSAT::StorageDevice::PreCopyOnWriteFile(ushort const *)
0x140061a2f  test    eax, eax
0x140061a31  jnz     loc_140061660
0x140061a37  mov     [rdi+70h], r12b
0x140061a3b  mov     r9d, 60000000h
0x140061a41  mov     r8d, 0C0000000h
0x140061a47  lea     rdx, [rbp+var_18]
0x140061a4b  mov     rcx, rdi
0x140061a4e  call    ?pOpen@StorageDevice@WinSAT@@AEAA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@KK@Z; WinSAT::StorageDevice::pOpen(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong)
0x140061a53  mov     byte ptr [rdi+70h], 1
0x140061a57  test    al, al
0x140061a59  jz      loc_140061660
0x140061a5f  lea     rdx, [rbp+arg_30]; bool *
0x140061a63  mov     rcx, rdi; this
0x140061a66  call    ?IsFileCompressed@StorageDevice@WinSAT@@AEBA_NAEA_N@Z; WinSAT::StorageDevice::IsFileCompressed(bool &)
0x140061a6b  test    al, al
0x140061a6d  jz      loc_140061660
0x140061a73  cmp     [rbp+arg_30], r12b
0x140061a77  jz      short loc_140061A83
0x140061a79  mov     ecx, 2010006h
0x140061a7e  jmp     loc_140061659
0x140061a83  mov     byte ptr [rdi+5Dh], 1
0x140061a87  lea     rcx, [rbp+var_20]; this
0x140061a8b  call    ?Release@ManagePrivilege@WinSAT@@QEAA_NXZ; WinSAT::ManagePrivilege::Release(void)
0x140061a90  nop
0x140061a91  lea     rcx, [rbp+var_10]
0x140061a95  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140061a9a  nop
0x140061a9b  lea     rcx, [rbp+var_18]
0x140061a9f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
  ... truncated ...
```
