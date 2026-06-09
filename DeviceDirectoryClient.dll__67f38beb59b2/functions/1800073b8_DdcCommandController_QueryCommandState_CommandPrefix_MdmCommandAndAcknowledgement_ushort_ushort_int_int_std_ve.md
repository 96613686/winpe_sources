# DdcCommandController::QueryCommandState(CommandPrefix *,MdmCommandAndAcknowledgement *,ushort * *,ushort * *,int *,int *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x1800073b8`
- end: `0x180007831`
- name: `?QueryCommandState@DdcCommandController@@CAJPEAUCommandPrefix@@PEAUMdmCommandAndAcknowledgement@@PEAPEAG2PEAH3PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1145`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005f5c`
- `0x180007838`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180002fc0`
- `0x1800035b0`
- `0x1800050b8`
- `0x180005a64`
- `0x180005a9c`
- `0x1800073b8`
- `0x180028ad0`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x1800074ea`
- `ntdll!NtQueryWnfStateData` at `0x1800074ea`
- `MdmCommon!MdmParseLocateCommand` at `0x18000778e`
- `MdmCommon!MdmParseLocateCommand` at `0x18000778e`
- `MdmCommon!MdmParseLockCommand` at `0x1800076b4`
- `MdmCommon!MdmParseLockCommand` at `0x1800076b4`
- `MdmCommon!MdmParseCommandData` at `0x180007562`
- `MdmCommon!MdmParseCommandData` at `0x180007562`

## string_xrefs

- `0x180007484`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x18000753e`: `CBR(cbBuffer >= sizeof(CommandPrefix) + 1)`
- `0x18000757b`: `CHR(MdmParseCommandData(bCommand, cbCommand, &cmdType))`
- `0x1800076cf`: `CHR(MdmParseLockCommand(bCommand, cbCommand, &pwszPin, &pwszCpn, &fRingAfterLock, vCids))`
- `0x1800077a3`: `CHR(MdmParseLocateCommand(bCommand, cbCommand, &fEnableLocation))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcCommandController::QueryCommandState(
        __int64 a1,
        _DWORD *a2,
        void **a3,
        void **a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7)
{
  int v10; // edx
  __int64 v11; // rcx
  int v12; // r8d
  int v13; // ebx
  int v14; // ebx
  unsigned int v15; // esi
  char v16; // al
  void **v17; // r15
  _DWORD *v18; // r13
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  char v22; // [rsp+20h] [rbp-E0h]
  const char *v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+3Ch] [rbp-C4h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+68h] [rbp-98h] BYREF
  void **v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+90h] [rbp-70h]
  unsigned __int8 v38[4076]; // [rsp+94h] [rbp-6Ch] BYREF

  v34 = a4;
  v35 = a5;
  v33 = 0;
  memset_0(&v36, 0, 0x1000u);
  v25 = 4096;
  v24 = 0;
  Block = 0;
  v29 = 0;
  v26 = 0;
  v27 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v30);
  if ( !a1 )
  {
    v12 = -2147024809;
    v13 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_46;
    v23 = "CPR(pPrefix)";
    v22 = 52;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v13 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        53,
        "CPR(pCmdType)");
    goto LABEL_46;
  }
  v14 = NtQueryWnfStateData(&stru_180049258, 0, 0, &v33, &v36, &v25);
  if ( v14 )
  {
    v13 = v14 | 0x10000000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_46;
    v23 = "CBR(ntStatus == ((NTSTATUS)0x00000000L))";
    v22 = 63;
LABEL_12:
    v12 = v13;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v11,
      v10,
      v12,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      v22,
      v23);
    goto LABEL_46;
  }
  if ( v25 < 0x15 )
  {
    v13 = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_46;
    v23 = "CBR(cbBuffer >= sizeof(CommandPrefix) + 1)";
    v22 = 66;
    goto LABEL_12;
  }
  v15 = v25 - 20;
  v13 = MdmParseCommandData(v38, v25 - 20, (struct MdmCommandAndAcknowledgement *)&v24);
  if ( v13 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_46;
    v23 = "CHR(MdmParseCommandData(bCommand, cbCommand, &cmdType))";
    v22 = 73;
    goto LABEL_12;
  }
  v16 = v24;
  *a2 = v24;
  *(_OWORD *)a1 = v36;
  *(_DWORD *)(a1 + 16) = v37;
  LODWORD(v11) = v16 & 0x3F;
  if ( (_BYTE)v11 == 3 )
  {
    if ( !a3 )
    {
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          82,
          "CPR(ppwszPin)");
      goto LABEL_46;
    }
    v17 = v34;
    if ( !v34 )
    {
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          83,
          "CPR(ppwszCpn)");
      goto LABEL_46;
    }
    v18 = (_DWORD *)v35;
    if ( !v35 )
    {
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          84,
          "CPR(pfRingAfterLock)");
      goto LABEL_46;
    }
    if ( !a7 )
    {
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          85,
          "CPR(pvCids)");
      goto LABEL_46;
    }
    v13 = MdmParseLockCommand(v38, v15, &Block, &v29, &v26, &v30);
    v10 = 0;
    if ( v13 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_46;
      v23 = "CHR(MdmParseLockCommand(bCommand, cbCommand, &pwszPin, &pwszCpn, &fRingAfterLock, vCids))";
      v22 = 87;
      goto LABEL_12;
    }
    *a3 = Block;
    Block = 0;
    *v17 = v29;
    v29 = 0;
    *v18 = v26;
    if ( (_QWORD **)a7 != &v30 )
    {
      v19 = *(_QWORD **)a7;
      *(_QWORD *)a7 = v30;
      v30 = v19;
      v20 = *(_QWORD *)(a7 + 8);
      *(_QWORD *)(a7 + 8) = v31;
      v31 = v20;
      v11 = *(_QWORD *)(a7 + 16);
      *(_QWORD *)(a7 + 16) = v32;
      v32 = v11;
    }
    v16 = v24;
  }
  if ( (v16 & 0x3F) != 2 )
    goto LABEL_46;
  if ( a6 )
  {
    v13 = MdmParseLocateCommand(v38, v15, &v27);
    if ( v13 >= 0 )
    {
      *a6 = v27;
      goto LABEL_46;
    }
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_46;
    v23 = "CHR(MdmParseLocateCommand(bCommand, cbCommand, &fEnableLocation))";
    v22 = 103;
    goto LABEL_12;
  }
  v13 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v11,
      v10,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      102,
      "CPR(pfEnableLocation)");
LABEL_46:
  if ( Block )
    operator delete(Block);
  if ( v29 )
    operator delete(v29);
  if ( v30 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v30, v31);
    std::_Deallocate<16>(v30, (v32 - (_QWORD)v30) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800073b8  push    rbp
0x1800073ba  push    rbx
0x1800073bb  push    rsi
0x1800073bc  push    rdi
0x1800073bd  push    r12
0x1800073bf  push    r13
0x1800073c1  push    r14
0x1800073c3  push    r15
0x1800073c5  lea     rbp, [rsp-0F98h]
0x1800073cd  mov     eax, 1098h
0x1800073d2  call    _alloca_probe
0x1800073d7  sub     rsp, rax
0x1800073da  mov     rax, cs:__security_cookie
0x1800073e1  xor     rax, rsp
0x1800073e4  mov     [rbp+0FD0h+var_50], rax
0x1800073eb  mov     [rsp+10D0h+var_1060], r9
0x1800073f0  mov     r12, r8
0x1800073f3  mov     r15, rdx
0x1800073f6  mov     r13, rcx
0x1800073f9  mov     rax, [rbp+0FD0h+arg_20]
0x180007400  mov     [rsp+10D0h+var_1058], rax
0x180007405  mov     r14, [rbp+0FD0h+arg_28]
0x18000740c  mov     rdi, [rbp+0FD0h+arg_30]
0x180007413  mov     [rsp+10D0h+var_1068], 0
0x18000741b  mov     ebx, 1000h
0x180007420  mov     r8d, ebx; Size
0x180007423  xor     edx, edx; Val
0x180007425  lea     rcx, [rbp+0FD0h+var_1050]; void *
0x180007429  call    memset_0
0x18000742e  mov     [rsp+10D0h+var_109C], ebx
0x180007432  xor     edx, edx
0x180007434  mov     [rsp+10D0h+var_10A0], edx
0x180007438  mov     [rsp+10D0h+Block], rdx
0x18000743d  mov     [rsp+10D0h+var_1088], rdx
0x180007442  mov     [rsp+10D0h+var_1098], edx
0x180007446  mov     [rsp+10D0h+var_1094], edx
0x18000744a  lea     rcx, [rsp+10D0h+var_1080]
0x18000744f  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x180007454  nop
0x180007455  test    r13, r13
0x180007458  jnz     short loc_180007495
0x18000745a  mov     r8d, 80070057h
0x180007460  mov     ebx, r8d
0x180007463  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000746a  jz      loc_1800077C3
0x180007470  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x180007477  mov     [rsp+10D0h+var_10A8], rax
0x18000747c  mov     dword ptr [rsp+10D0h+var_10B0], 134h
0x180007484  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000748b  call    McTemplateU0dsqs_EventWriteTransfer
0x180007490  jmp     loc_1800077C3
0x180007495  test    r15, r15
0x180007498  jnz     short loc_1800074C6
0x18000749a  mov     r8d, 80070057h
0x1800074a0  mov     ebx, r8d
0x1800074a3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800074aa  jz      loc_1800077C3
0x1800074b0  lea     rax, aCprPcmdtype; "CPR(pCmdType)"
0x1800074b7  mov     [rsp+10D0h+var_10A8], rax
0x1800074bc  mov     dword ptr [rsp+10D0h+var_10B0], 135h
0x1800074c4  jmp     short loc_180007484
0x1800074c6  lea     rax, [rsp+10D0h+var_109C]
0x1800074cb  mov     [rsp+10D0h+var_10A8], rax
0x1800074d0  lea     rax, [rbp+0FD0h+var_1050]
0x1800074d4  mov     [rsp+10D0h+var_10B0], rax
0x1800074d9  lea     r9, [rsp+10D0h+var_1068]
0x1800074de  xor     r8d, r8d
0x1800074e1  xor     edx, edx
0x1800074e3  lea     rcx, stru_180049258
0x1800074ea  call    cs:__imp_NtQueryWnfStateData
0x1800074f0  mov     ebx, eax
0x1800074f2  test    eax, eax
0x1800074f4  jz      short loc_180007523
0x1800074f6  bts     ebx, 1Ch
0x1800074fa  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180007501  jz      loc_1800077C3
0x180007507  lea     rax, aCbrNtstatusNts; "CBR(ntStatus == ((NTSTATUS)0x00000000L)"...
0x18000750e  mov     [rsp+10D0h+var_10A8], rax
0x180007513  mov     dword ptr [rsp+10D0h+var_10B0], 13Fh
0x18000751b  mov     r8d, ebx
0x18000751e  jmp     loc_180007484
0x180007523  mov     eax, [rsp+10D0h+var_109C]
0x180007527  cmp     eax, 15h
0x18000752a  jnb     short loc_180007554
0x18000752c  mov     ebx, 8000FFFFh
0x180007531  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180007538  jz      loc_1800077C3
0x18000753e  lea     rax, aCbrCbbufferSiz; "CBR(cbBuffer >= sizeof(CommandPrefix) +"...
0x180007545  mov     [rsp+10D0h+var_10A8], rax
0x18000754a  mov     dword ptr [rsp+10D0h+var_10B0], 142h
0x180007552  jmp     short loc_18000751B
0x180007554  lea     esi, [rax-14h]
0x180007557  lea     r8, [rsp+10D0h+var_10A0]
0x18000755c  mov     edx, esi
0x18000755e  lea     rcx, [rbp+0FD0h+var_103C]
0x180007562  call    cs:__imp_?MdmParseCommandData@@YAJPEAEKPEAUMdmCommandAndAcknowledgement@@@Z; MdmParseCommandData(uchar *,ulong,MdmCommandAndAcknowledgement *)
0x180007568  mov     ebx, eax
0x18000756a  test    eax, eax
0x18000756c  jns     short loc_180007591
0x18000756e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180007575  jz      loc_1800077C3
0x18000757b  lea     rax, aChrMdmparsecom; "CHR(MdmParseCommandData(bCommand, cbCom"...
0x180007582  mov     [rsp+10D0h+var_10A8], rax
0x180007587  mov     dword ptr [rsp+10D0h+var_10B0], 149h
0x18000758f  jmp     short loc_18000751B
0x180007591  mov     eax, [rsp+10D0h+var_10A0]
0x180007595  mov     [r15], eax
0x180007598  movaps  xmm0, [rbp+0FD0h+var_1050]
0x18000759c  movups  xmmword ptr [r13+0], xmm0
0x1800075a1  mov     ecx, [rbp+0FD0h+var_1040]
0x1800075a4  mov     [r13+10h], ecx
0x1800075a8  mov     ecx, eax
0x1800075aa  and     ecx, 3Fh
0x1800075ad  cmp     cl, 3
0x1800075b0  jnz     loc_18000774D
0x1800075b6  test    r12, r12
0x1800075b9  jnz     short loc_1800075EA
0x1800075bb  mov     r8d, 80070057h
0x1800075c1  mov     ebx, r8d
0x1800075c4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800075cb  jz      loc_1800077C3
0x1800075d1  lea     rax, aCprPpwszpin; "CPR(ppwszPin)"
0x1800075d8  mov     [rsp+10D0h+var_10A8], rax
0x1800075dd  mov     dword ptr [rsp+10D0h+var_10B0], 152h
0x1800075e5  jmp     loc_180007484
0x1800075ea  mov     r15, [rsp+10D0h+var_1060]
0x1800075ef  test    r15, r15
0x1800075f2  jnz     short loc_180007623
0x1800075f4  mov     r8d, 80070057h
0x1800075fa  mov     ebx, r8d
0x1800075fd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180007604  jz      loc_1800077C3
0x18000760a  lea     rax, aCprPpwszcpn; "CPR(ppwszCpn)"
0x180007611  mov     [rsp+10D0h+var_10A8], rax
0x180007616  mov     dword ptr [rsp+10D0h+var_10B0], 153h
0x18000761e  jmp     loc_180007484
0x180007623  mov     r13, [rsp+10D0h+var_1058]
0x180007628  test    r13, r13
0x18000762b  jnz     short loc_18000765C
0x18000762d  mov     r8d, 80070057h
0x180007633  mov     ebx, r8d
0x180007636  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000763d  jz      loc_1800077C3
0x180007643  lea     rax, aCprPfringafter; "CPR(pfRingAfterLock)"
0x18000764a  mov     [rsp+10D0h+var_10A8], rax
0x18000764f  mov     dword ptr [rsp+10D0h+var_10B0], 154h
0x180007657  jmp     loc_180007484
0x18000765c  test    rdi, rdi
0x18000765f  jnz     short loc_180007690
0x180007661  mov     r8d, 80070057h
0x180007667  mov     ebx, r8d
0x18000766a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180007671  jz      loc_1800077C3
0x180007677  lea     rax, aCprPvcids; "CPR(pvCids)"
0x18000767e  mov     [rsp+10D0h+var_10A8], rax
0x180007683  mov     dword ptr [rsp+10D0h+var_10B0], 155h
0x18000768b  jmp     loc_180007484
0x180007690  lea     rax, [rsp+10D0h+var_1080]
0x180007695  mov     [rsp+10D0h+var_10A8], rax
0x18000769a  lea     rax, [rsp+10D0h+var_1098]
0x18000769f  mov     [rsp+10D0h+var_10B0], rax
0x1800076a4  lea     r9, [rsp+10D0h+var_1088]
0x1800076a9  lea     r8, [rsp+10D0h+Block]
0x1800076ae  mov     edx, esi
0x1800076b0  lea     rcx, [rbp+0FD0h+var_103C]
0x1800076b4  call    cs:__imp_?MdmParseLockCommand@@YAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::wstring> &)
0x1800076ba  mov     ebx, eax
0x1800076bc  xor     edx, edx
0x1800076be  test    eax, eax
0x1800076c0  jns     short loc_1800076E8
0x1800076c2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800076c9  jz      loc_1800077C3
0x1800076cf  lea     rax, aChrMdmparseloc_0; "CHR(MdmParseLockCommand(bCommand, cbCom"...
0x1800076d6  mov     [rsp+10D0h+var_10A8], rax
0x1800076db  mov     dword ptr [rsp+10D0h+var_10B0], 157h
0x1800076e3  jmp     loc_18000751B
0x1800076e8  mov     rax, [rsp+10D0h+Block]
0x1800076ed  mov     [r12], rax
0x1800076f1  mov     [rsp+10D0h+Block], rdx
0x1800076f6  mov     rax, [rsp+10D0h+var_1088]
0x1800076fb  mov     [r15], rax
0x1800076fe  mov     [rsp+10D0h+var_1088], rdx
0x180007703  mov     eax, [rsp+10D0h+var_1098]
0x180007707  mov     [r13+0], eax
0x18000770b  lea     rax, [rsp+10D0h+var_1080]
0x180007710  cmp     rdi, rax
0x180007713  jz      short loc_180007749
0x180007715  mov     rcx, [rdi]
0x180007718  mov     rax, [rsp+10D0h+var_1080]
0x18000771d  mov     [rdi], rax
0x180007720  mov     [rsp+10D0h+var_1080], rcx
0x180007725  mov     rcx, [rdi+8]
0x180007729  mov     rax, [rsp+10D0h+var_1078]
0x18000772e  mov     [rdi+8], rax
0x180007732  mov     [rsp+10D0h+var_1078], rcx
0x180007737  mov     rcx, [rdi+10h]
0x18000773b  mov     rax, [rsp+10D0h+var_1070]
0x180007740  mov     [rdi+10h], rax
0x180007744  mov     [rsp+10D0h+var_1070], rcx
0x180007749  mov     eax, [rsp+10D0h+var_10A0]
0x18000774d  and     al, 3Fh
0x18000774f  cmp     al, 2
0x180007751  jnz     short loc_1800077C3
0x180007753  test    r14, r14
0x180007756  jnz     short loc_180007783
0x180007758  mov     r8d, 80070057h
0x18000775e  mov     ebx, r8d
0x180007761  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180007768  jz      short loc_1800077C3
0x18000776a  lea     rax, aCprPfenableloc; "CPR(pfEnableLocation)"
0x180007771  mov     [rsp+10D0h+var_10A8], rax
0x180007776  mov     dword ptr [rsp+10D0h+var_10B0], 166h
0x18000777e  jmp     loc_180007484
0x180007783  lea     r8, [rsp+10D0h+var_1094]
0x180007788  mov     edx, esi
0x18000778a  lea     rcx, [rbp+0FD0h+var_103C]
0x18000778e  call    cs:__imp_?MdmParseLocateCommand@@YAJPEAEKPEAH@Z; MdmParseLocateCommand(uchar *,ulong,int *)
0x180007794  mov     ebx, eax
0x180007796  test    eax, eax
0x180007798  jns     short loc_1800077BC
0x18000779a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800077a1  jz      short loc_1800077C3
0x1800077a3  lea     rax, aChrMdmparseloc; "CHR(MdmParseLocateCommand(bCommand, cbC"...
0x1800077aa  mov     [rsp+10D0h+var_10A8], rax
0x1800077af  mov     dword ptr [rsp+10D0h+var_10B0], 167h
0x1800077b7  jmp     loc_18000751B
0x1800077bc  mov     eax, [rsp+10D0h+var_1094]
0x1800077c0  mov     [r14], eax
0x1800077c3  mov     rcx, [rsp+10D0h+Block]; Block
0x1800077c8  test    rcx, rcx
0x1800077cb  jz      short loc_1800077D2
0x1800077cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800077d2  mov     rcx, [rsp+10D0h+var_1088]; Block
0x1800077d7  test    rcx, rcx
0x1800077da  jz      short loc_1800077E2
0x1800077dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800077e1  nop
0x1800077e2  mov     rcx, [rsp+10D0h+var_1080]
0x1800077e7  test    rcx, rcx
0x1800077ea  jz      short loc_18000780C
0x1800077ec  mov     rdx, [rsp+10D0h+var_1078]
0x1800077f1  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800077f6  mov     rcx, [rsp+10D0h+var_1080]
0x1800077fb  mov     rdx, [rsp+10D0h+var_1070]
0x180007800  sub     rdx, rcx
0x180007803  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180007807  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000780c  mov     eax, ebx
0x18000780e  mov     rcx, [rbp+0FD0h+var_50]
0x180007815  xor     rcx, rsp; StackCookie
0x180007818  call    __security_check_cookie
0x18000781d  add     rsp, 1098h
0x180007824  pop     r15
0x180007826  pop     r14
0x180007828  pop     r13
0x18000782a  pop     r12
0x18000782c  pop     rdi
0x18000782d  pop     rsi
0x18000782e  pop     rbx
0x18000782f  pop     rbp
0x180007830  retn
```
