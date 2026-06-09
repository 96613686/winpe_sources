# DrvCreatePhysicalMonitorObjects

- ea: `0x14017d2b0`
- end: `0x14017d6fd`
- name: `DrvCreatePhysicalMonitorObjects`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, enum _MODE@<edx>, int, volatile void *, volatile void *Address)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x14017d240`

## callees

- `0x140025afc`
- `0x140031550`
- `0x1400319c0`
- `0x140040394`
- `0x1400411c0`
- `0x1400c4178`
- `0x1400c5250`
- `0x1400c5bdc`
- `0x14014de7c`
- `0x14017d2b0`
- `0x14018ad8c`
- `0x140238bf0`
- `0x1402bd3b4`
- `0x1402bd3fc`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14017d547`
- `ntoskrnl!ProbeForWrite` at `0x14017d563`
- `ntoskrnl!ProbeForWrite` at `0x14017d547`
- `ntoskrnl!ProbeForWrite` at `0x14017d563`
- `watchdog!WdLogSingleEntry4` at `0x14017d2ee`
- `watchdog!WdLogSingleEntry4` at `0x14017d2ee`
- `watchdog!WdLogSingleEntry0` at `0x14017d6c1`
- `watchdog!WdLogSingleEntry0` at `0x14017d6c1`
- `watchdog!WdLogSingleEntry1` at `0x14017d32b`
- `watchdog!WdLogSingleEntry1` at `0x14017d68f`
- `watchdog!WdLogSingleEntry1` at `0x14017d32b`
- `watchdog!WdLogSingleEntry1` at `0x14017d68f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017d444`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017d614`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017d644`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017d444`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017d614`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14017d644`

## pseudocode

```c
__int64 __fastcall DrvCreatePhysicalMonitorObjects(
        struct _UNICODE_STRING *a1,
        enum _MODE a2,
        int a3,
        enum _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS a4,
        unsigned int a5,
        volatile void *a6,
        char *Address)
{
  int DeviceFromNameAndValidateDevice; // eax
  signed int NumberOfPhysicalMonitors; // ebx
  unsigned int v12; // r15d
  void **v13; // rdi
  int v14; // r12d
  unsigned int v15; // r14d
  __int64 v16; // r13
  __int64 (*v17)(void); // rax
  unsigned __int64 v18; // rax
  unsigned int v19; // ecx
  __int64 i; // r14
  __int64 v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 (*v24)(void); // rax
  int v25; // eax
  void *v26; // r12
  void (__fastcall *v27)(void *); // rax
  int v28; // [rsp+30h] [rbp-88h]
  struct tagGRAPHICS_DEVICE *v29; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-78h]
  int v31; // [rsp+44h] [rbp-74h]
  int v32; // [rsp+48h] [rbp-70h]
  struct _LUID v33; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v34[4]; // [rsp+58h] [rbp-60h] BYREF
  int v35; // [rsp+68h] [rbp-50h]
  char v36[8]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-40h]
  __int64 v38; // [rsp+80h] [rbp-38h]
  void **v39; // [rsp+88h] [rbp-30h]

  WdLogSingleEntry4(4, a1, a3, a4, a5);
  WdLogGlobalForLineNumber = 26411;
  v29 = 0;
  DeviceFromNameAndValidateDevice = DrvGetDeviceFromNameAndValidateDevice(a1, a2, &v29);
  NumberOfPhysicalMonitors = DeviceFromNameAndValidateDevice;
  if ( DeviceFromNameAndValidateDevice < 0 )
  {
    WdLogSingleEntry1(5, DeviceFromNameAndValidateDevice);
    WdLogGlobalForLineNumber = 26421;
    return (unsigned int)NumberOfPhysicalMonitors;
  }
  v12 = 0;
  v30 = 0;
  v13 = 0;
  v37 = 0;
  v38 = 0;
  EnsureMonitorDevices::UpdateMonitorDevicesOnGraphicsDevice((EnsureMonitorDevices *)v36, v29);
  LODWORD(v29) = 0;
  NumberOfPhysicalMonitors = DrvGetNumberOfPhysicalMonitors((struct EnsureMonitorDevices *)v36, (unsigned int *)&v29);
  v28 = NumberOfPhysicalMonitors;
  if ( NumberOfPhysicalMonitors < 0 )
    goto LABEL_38;
  v14 = (int)v29;
  if ( a5 < (unsigned int)v29 )
  {
    NumberOfPhysicalMonitors = -1071774234;
LABEL_7:
    v28 = NumberOfPhysicalMonitors;
    goto LABEL_39;
  }
  if ( 8 * (unsigned __int64)(unsigned int)v29 > 0xFFFFFFFF )
  {
    NumberOfPhysicalMonitors = -1073741675;
    v28 = -1073741675;
    goto LABEL_38;
  }
  v13 = (void **)PALLOCMEM(8LL * (unsigned int)v29, 1986291527);
  v39 = v13;
  if ( !v13 )
  {
    NumberOfPhysicalMonitors = -1073741801;
    goto LABEL_7;
  }
  v15 = 0;
  v16 = 0;
  while ( v15 < v37 )
  {
    *(_OWORD *)v34 = 0;
    v35 = 0;
    EnsureMonitorDevices::GetMonitorDevice((EnsureMonitorDevices *)v36, v15, (struct tagVIDEO_MONITOR_DEVICE *)v34);
    v33 = *(struct _LUID *)&v34[2];
    if ( (v34[0] & 1) == 0 )
      goto LABEL_26;
    if ( v12 == v14 )
      goto LABEL_27;
    if ( a3 )
    {
      if ( a3 != 1 )
      {
LABEL_27:
        NumberOfPhysicalMonitors = -1071774233;
        goto LABEL_7;
      }
      v17 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(1) + 24) + 1024LL);
      if ( v17 )
      {
        NumberOfPhysicalMonitors = v17();
        v28 = NumberOfPhysicalMonitors;
      }
      else
      {
        NumberOfPhysicalMonitors = -1073741637;
        v28 = -1073741637;
      }
      if ( NumberOfPhysicalMonitors < 0 )
        goto LABEL_39;
      NumberOfPhysicalMonitors = CreatePhysicalMonitorWrap(&v33, v34[1], &v13[v16]);
      v28 = NumberOfPhysicalMonitors;
      if ( NumberOfPhysicalMonitors < 0 )
        goto LABEL_39;
LABEL_25:
      v16 = (unsigned int)(v16 + 1);
      v30 = ++v12;
      goto LABEL_26;
    }
    LODWORD(v29) = 0;
    NumberOfPhysicalMonitors = OPMCreateProtectedOutput(a4, &v33, v34[1], &v13[v16], (int *)&v29);
    v28 = NumberOfPhysicalMonitors;
    if ( NumberOfPhysicalMonitors < 0 )
      goto LABEL_38;
    if ( !(_DWORD)v29 )
      goto LABEL_25;
LABEL_26:
    ++v15;
  }
  v18 = 8LL * a5;
  v19 = 8 * a5;
  if ( v18 > 0xFFFFFFFF )
    v19 = -1;
  NumberOfPhysicalMonitors = v18 > 0xFFFFFFFF ? 0xC0000095 : 0;
  v28 = NumberOfPhysicalMonitors;
  if ( v18 <= 0xFFFFFFFF )
  {
    ProbeForWrite(Address, v19, 8u);
    ProbeForWrite(a6, 4u, 4u);
    if ( v12 > a5 )
    {
      NumberOfPhysicalMonitors = -1071774234;
      v28 = -1071774234;
      v32 = -1071774234;
    }
    else
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v31 = i;
        if ( (unsigned int)i >= v12 )
          break;
        RtlWriteULong64ToUser(&Address[8 * i], v13[i]);
      }
      RtlWriteULongToUser(a6, v12);
    }
  }
LABEL_38:
  if ( NumberOfPhysicalMonitors >= 0 )
  {
    GreDeleteFastMutex(v13);
    WdLogSingleEntry0(5);
    WdLogGlobalForLineNumber = 26596;
    EnsureMonitorDevices::~EnsureMonitorDevices((EnsureMonitorDevices *)v36);
    return 0;
  }
  else
  {
LABEL_39:
    if ( v13 )
    {
      if ( v12 )
      {
        v21 = 0;
        do
        {
          OPMDestroyProtectedOutput(v13[v21]);
          if ( a3 )
          {
            if ( a3 == 1 )
            {
              v23 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v22) + 24);
              v24 = *(__int64 (**)(void))(v23 + 1040);
              if ( v24 )
                v25 = v24();
              else
                v25 = -1073741637;
              if ( v25 >= 0 )
              {
                v26 = v13[v21];
                v27 = *(void (__fastcall **)(void *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v23) + 24) + 1048LL);
                if ( v27 )
                  v27(v26);
              }
            }
          }
          else
          {
            OPMDestroyProtectedOutput(v13[v21]);
          }
          v21 = (unsigned int)(v21 + 1);
        }
        while ( (unsigned int)v21 < v12 );
        NumberOfPhysicalMonitors = v28;
      }
      GreDeleteFastMutex(v13);
    }
    WdLogSingleEntry1(5, NumberOfPhysicalMonitors);
    WdLogGlobalForLineNumber = 26590;
    EnsureMonitorDevices::~EnsureMonitorDevices((EnsureMonitorDevices *)v36);
    return (unsigned int)NumberOfPhysicalMonitors;
  }
}

```

## disassembly

```asm
0x14017d2b0  mov     [rsp+arg_0], rbx
0x14017d2b5  mov     [rsp+arg_18], r9d
0x14017d2ba  mov     [rsp+arg_10], r8d
0x14017d2bf  push    rdi
0x14017d2c0  push    r12
0x14017d2c2  push    r13
0x14017d2c4  push    r14
0x14017d2c6  push    r15
0x14017d2c8  sub     rsp, 90h
0x14017d2cf  movsxd  r8, r8d
0x14017d2d2  mov     ebx, edx
0x14017d2d4  mov     rdi, rcx
0x14017d2d7  mov     ecx, [rsp+0B8h+arg_20]
0x14017d2de  movsxd  r9, r9d
0x14017d2e1  mov     [rsp+0B8h+var_98], rcx
0x14017d2e6  mov     rdx, rdi
0x14017d2e9  mov     ecx, 4
0x14017d2ee  call    cs:__imp_WdLogSingleEntry4
0x14017d2f5  nop     dword ptr [rax+rax+00h]
0x14017d2fa  mov     cs:WdLogGlobalForLineNumber, 672Bh
0x14017d304  mov     [rsp+0B8h+var_80], 0
0x14017d30d  lea     r8, [rsp+0B8h+var_80]; struct tagGRAPHICS_DEVICE **
0x14017d312  mov     edx, ebx; enum _MODE
0x14017d314  mov     rcx, rdi; struct _UNICODE_STRING *
0x14017d317  call    ?DrvGetDeviceFromNameAndValidateDevice@@YAJPEAU_UNICODE_STRING@@W4_MODE@@PEAPEAUtagGRAPHICS_DEVICE@@@Z; DrvGetDeviceFromNameAndValidateDevice(_UNICODE_STRING *,_MODE,tagGRAPHICS_DEVICE * *)
0x14017d31c  movsxd  rbx, eax
0x14017d31f  test    eax, eax
0x14017d321  jns     short loc_14017D348
0x14017d323  mov     rdx, rbx
0x14017d326  mov     ecx, 5
0x14017d32b  call    cs:__imp_WdLogSingleEntry1
0x14017d332  nop     dword ptr [rax+rax+00h]
0x14017d337  mov     cs:WdLogGlobalForLineNumber, 6735h
0x14017d341  mov     eax, ebx
0x14017d343  jmp     loc_14017D6E3
0x14017d348  xor     r15d, r15d
0x14017d34b  mov     [rsp+0B8h+var_78], r15d
0x14017d350  xor     edi, edi
0x14017d352  mov     [rsp+0B8h+var_40], edi
0x14017d356  mov     [rsp+0B8h+var_38], rdi
0x14017d35e  mov     rdx, [rsp+0B8h+var_80]; struct tagGRAPHICS_DEVICE *
0x14017d363  lea     rcx, [rsp+0B8h+var_48]; this
0x14017d368  call    ?UpdateMonitorDevicesOnGraphicsDevice@EnsureMonitorDevices@@AEAAXPEAUtagGRAPHICS_DEVICE@@@Z; EnsureMonitorDevices::UpdateMonitorDevicesOnGraphicsDevice(tagGRAPHICS_DEVICE *)
0x14017d36d  mov     dword ptr [rsp+0B8h+var_80], edi
0x14017d371  lea     rdx, [rsp+0B8h+var_80]; unsigned int *
0x14017d376  lea     rcx, [rsp+0B8h+var_48]; this
0x14017d37b  call    ?DrvGetNumberOfPhysicalMonitors@@YAJAEAVEnsureMonitorDevices@@PEAK@Z; DrvGetNumberOfPhysicalMonitors(EnsureMonitorDevices &,ulong *)
0x14017d380  mov     ebx, eax
0x14017d382  mov     [rsp+0B8h+var_88], eax
0x14017d386  test    eax, eax
0x14017d388  js      loc_14017D5DE
0x14017d38e  mov     r12d, dword ptr [rsp+0B8h+var_80]
0x14017d393  cmp     [rsp+0B8h+arg_20], r12d
0x14017d39b  jnb     short loc_14017D3AB
0x14017d39d  mov     ebx, 0C01E05E6h
0x14017d3a2  mov     [rsp+0B8h+var_88], ebx
0x14017d3a6  jmp     loc_14017D5E6
0x14017d3ab  mov     rcx, r12
0x14017d3ae  shl     rcx, 3
0x14017d3b2  mov     ebx, 0FFFFFFFFh
0x14017d3b7  cmp     rcx, rbx
0x14017d3ba  ja      loc_14017D5D5
0x14017d3c0  mov     edx, 76646747h
0x14017d3c5  call    PALLOCMEM
0x14017d3ca  mov     rdi, rax
0x14017d3cd  mov     [rsp+0B8h+var_30], rax
0x14017d3d5  test    rax, rax
0x14017d3d8  jnz     short loc_14017D3E1
0x14017d3da  mov     ebx, 0C0000017h
0x14017d3df  jmp     short loc_14017D3A2
0x14017d3e1  xor     r14d, r14d
0x14017d3e4  xor     r13d, r13d
0x14017d3e7  cmp     r14d, [rsp+0B8h+var_40]
0x14017d3ec  jnb     loc_14017D4FD
0x14017d3f2  xorps   xmm0, xmm0
0x14017d3f5  xor     eax, eax
0x14017d3f7  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x14017d3fc  mov     [rsp+0B8h+var_50], eax
0x14017d400  lea     r8, [rsp+0B8h+var_60]; struct tagVIDEO_MONITOR_DEVICE *
0x14017d405  mov     edx, r14d; unsigned int
0x14017d408  lea     rcx, [rsp+0B8h+var_48]; this
0x14017d40d  call    ?GetMonitorDevice@EnsureMonitorDevices@@QEBAXKAEAUtagVIDEO_MONITOR_DEVICE@@@Z; EnsureMonitorDevices::GetMonitorDevice(ulong,tagVIDEO_MONITOR_DEVICE &)
0x14017d412  mov     r8, qword ptr [rsp+0B8h+var_60+8]
0x14017d417  mov     qword ptr [rsp+0B8h+var_68.LowPart], r8
0x14017d41c  test    byte ptr [rsp+0B8h+var_60], 1
0x14017d421  jz      loc_14017D4EB
0x14017d427  cmp     r15d, r12d
0x14017d42a  jz      loc_14017D4F3
0x14017d430  mov     ecx, [rsp+0B8h+arg_10]
0x14017d437  test    ecx, ecx
0x14017d439  jz      short loc_14017D49F
0x14017d43b  cmp     ecx, 1
0x14017d43e  jnz     loc_14017D4F3
0x14017d444  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017d44b  nop     dword ptr [rax+rax+00h]
0x14017d450  mov     rcx, [rax+18h]
0x14017d454  mov     rax, [rcx+400h]
0x14017d45b  test    rax, rax
0x14017d45e  jz      short loc_14017D46D
0x14017d460  call    _guard_dispatch_icall
0x14017d465  mov     ebx, eax
0x14017d467  mov     [rsp+0B8h+var_88], eax
0x14017d46b  jmp     short loc_14017D476
0x14017d46d  mov     ebx, 0C00000BBh
0x14017d472  mov     [rsp+0B8h+var_88], ebx
0x14017d476  test    ebx, ebx
0x14017d478  js      loc_14017D5E6
0x14017d47e  lea     r8, [rdi+r13*8]
0x14017d482  mov     edx, [rsp+0B8h+var_60+4]
0x14017d486  lea     rcx, [rsp+0B8h+var_68]
0x14017d48b  call    CreatePhysicalMonitorWrap
0x14017d490  mov     ebx, eax
0x14017d492  mov     [rsp+0B8h+var_88], eax
0x14017d496  test    eax, eax
0x14017d498  jns     short loc_14017D4E0
0x14017d49a  jmp     loc_14017D5E6
0x14017d49f  mov     dword ptr [rsp+0B8h+var_80], 0
0x14017d4a7  lea     r9, [rdi+r13*8]; void **
0x14017d4ab  lea     rax, [rsp+0B8h+var_80]
0x14017d4b0  mov     [rsp+0B8h+var_98], rax; int *
0x14017d4b5  mov     r8d, [rsp+0B8h+var_60+4]; unsigned int
0x14017d4ba  lea     rdx, [rsp+0B8h+var_68]; struct _LUID *
0x14017d4bf  mov     ecx, [rsp+0B8h+arg_18]; enum _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
0x14017d4c6  call    ?OPMCreateProtectedOutput@@YAJW4_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS@@AEAU_LUID@@KPEAPEAXPEAH@Z; OPMCreateProtectedOutput(_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS,_LUID &,ulong,void * *,int *)
0x14017d4cb  mov     ebx, eax
0x14017d4cd  mov     [rsp+0B8h+var_88], eax
0x14017d4d1  test    eax, eax
0x14017d4d3  js      loc_14017D5DE
0x14017d4d9  cmp     dword ptr [rsp+0B8h+var_80], 0
0x14017d4de  jnz     short loc_14017D4EB
0x14017d4e0  inc     r13d
0x14017d4e3  inc     r15d
0x14017d4e6  mov     [rsp+0B8h+var_78], r15d
0x14017d4eb  inc     r14d
0x14017d4ee  jmp     loc_14017D3E7
0x14017d4f3  mov     ebx, 0C01E05E7h
0x14017d4f8  jmp     loc_14017D3A2
0x14017d4fd  mov     eax, [rsp+0B8h+arg_20]
0x14017d504  shl     rax, 3
0x14017d508  mov     ebx, 0FFFFFFFFh
0x14017d50d  cmp     rax, rbx
0x14017d510  mov     ecx, eax
0x14017d512  jbe     short loc_14017D516
0x14017d514  mov     ecx, ebx
0x14017d516  cmp     rbx, rax
0x14017d519  sbb     ebx, ebx
0x14017d51b  and     ebx, 0C0000095h
0x14017d521  mov     [rsp+0B8h+var_88], ebx
0x14017d525  mov     r8d, 0FFFFFFFFh
0x14017d52b  cmp     rax, r8
0x14017d52e  ja      loc_14017D5DE
0x14017d534  mov     edx, ecx; Length
0x14017d536  mov     r8d, 8; Alignment
0x14017d53c  mov     r12, [rsp+0B8h+Address]
0x14017d544  mov     rcx, r12; Address
0x14017d547  call    cs:__imp_ProbeForWrite
0x14017d54e  nop     dword ptr [rax+rax+00h]
0x14017d553  mov     edx, 4; Length
0x14017d558  mov     r8d, edx; Alignment
0x14017d55b  mov     rcx, [rsp+0B8h+arg_28]; Address
0x14017d563  call    cs:__imp_ProbeForWrite
0x14017d56a  nop     dword ptr [rax+rax+00h]
0x14017d56f  cmp     r15d, [rsp+0B8h+arg_20]
0x14017d577  ja      short loc_14017D5AA
0x14017d579  xor     r14d, r14d
0x14017d57c  mov     [rsp+0B8h+var_74], r14d
0x14017d581  cmp     r14d, r15d
0x14017d584  jnb     short loc_14017D598
0x14017d586  lea     rcx, [r12+r14*8]
0x14017d58a  mov     rdx, [rdi+r14*8]
0x14017d58e  call    RtlWriteULong64ToUser
0x14017d593  inc     r14d
0x14017d596  jmp     short loc_14017D57C
0x14017d598  mov     edx, r15d
0x14017d59b  mov     rcx, [rsp+0B8h+arg_28]
0x14017d5a3  call    RtlWriteULongToUser
0x14017d5a8  jmp     short loc_14017D5DE
0x14017d5aa  mov     ebx, 0C01E05E6h
0x14017d5af  mov     [rsp+0B8h+var_88], ebx
0x14017d5b3  mov     [rsp+0B8h+var_70], ebx
0x14017d5b7  jmp     short loc_14017D5DE
0x14017d5b9  mov     ebx, 0C01E05E4h
0x14017d5be  mov     [rsp+0B8h+var_88], ebx
0x14017d5c2  mov     [rsp+0B8h+var_70], ebx
0x14017d5c6  mov     r15d, [rsp+0B8h+var_78]
0x14017d5cb  mov     rdi, [rsp+0B8h+var_30]
0x14017d5d3  jmp     short loc_14017D5DE
0x14017d5d5  mov     ebx, 0C0000095h
0x14017d5da  mov     [rsp+0B8h+var_88], ebx
0x14017d5de  test    ebx, ebx
0x14017d5e0  jns     loc_14017D6B4
0x14017d5e6  test    rdi, rdi
0x14017d5e9  jz      loc_14017D687
0x14017d5ef  test    r15d, r15d
0x14017d5f2  jz      loc_14017D67F
0x14017d5f8  xor     r14d, r14d
0x14017d5fb  mov     ebx, [rsp+0B8h+arg_10]
0x14017d602  mov     rcx, [rdi+r14*8]; void *
0x14017d606  call    ?OPMDestroyProtectedOutput@@YAJPEAX@Z; OPMDestroyProtectedOutput(void *)
0x14017d60b  test    ebx, ebx
0x14017d60d  jz      short loc_14017D66A
0x14017d60f  cmp     ebx, 1
0x14017d612  jnz     short loc_14017D673
0x14017d614  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017d61b  nop     dword ptr [rax+rax+00h]
0x14017d620  mov     rcx, [rax+18h]
0x14017d624  mov     rax, [rcx+410h]
0x14017d62b  test    rax, rax
0x14017d62e  jz      short loc_14017D637
0x14017d630  call    _guard_dispatch_icall
0x14017d635  jmp     short loc_14017D63C
0x14017d637  mov     eax, 0C00000BBh
0x14017d63c  test    eax, eax
0x14017d63e  js      short loc_14017D673
0x14017d640  mov     r12, [rdi+r14*8]
0x14017d644  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14017d64b  nop     dword ptr [rax+rax+00h]
0x14017d650  mov     rdx, [rax+18h]
0x14017d654  mov     rax, [rdx+418h]
0x14017d65b  test    rax, rax
0x14017d65e  jz      short loc_14017D673
0x14017d660  mov     rcx, r12
0x14017d663  call    _guard_dispatch_icall
0x14017d668  jmp     short loc_14017D673
0x14017d66a  mov     rcx, [rdi+r14*8]; void *
0x14017d66e  call    ?OPMDestroyProtectedOutput@@YAJPEAX@Z; OPMDestroyProtectedOutput(void *)
0x14017d673  inc     r14d
0x14017d676  cmp     r14d, r15d
0x14017d679  jb      short loc_14017D602
0x14017d67b  mov     ebx, [rsp+0B8h+var_88]
0x14017d67f  mov     rcx, rdi; Buffer
0x14017d682  call    GreDeleteFastMutex
0x14017d687  movsxd  rdx, ebx
0x14017d68a  mov     ecx, 5
0x14017d68f  call    cs:__imp_WdLogSingleEntry1
0x14017d696  nop     dword ptr [rax+rax+00h]
0x14017d69b  mov     cs:WdLogGlobalForLineNumber, 67DEh
0x14017d6a5  lea     rcx, [rsp+0B8h+var_48]; this
0x14017d6aa  call    ??1EnsureMonitorDevices@@QEAA@XZ; EnsureMonitorDevices::~EnsureMonitorDevices(void)
0x14017d6af  jmp     loc_14017D341
0x14017d6b4  mov     rcx, rdi; Buffer
0x14017d6b7  call    GreDeleteFastMutex
0x14017d6bc  mov     ecx, 5
0x14017d6c1  call    cs:__imp_WdLogSingleEntry0
0x14017d6c8  nop     dword ptr [rax+rax+00h]
0x14017d6cd  mov     cs:WdLogGlobalForLineNumber, 67E4h
0x14017d6d7  lea     rcx, [rsp+0B8h+var_48]; this
0x14017d6dc  call    ??1EnsureMonitorDevices@@QEAA@XZ; EnsureMonitorDevices::~EnsureMonitorDevices(void)
0x14017d6e1  xor     eax, eax
0x14017d6e3  mov     rbx, [rsp+0B8h+arg_0]
0x14017d6eb  add     rsp, 90h
0x14017d6f2  pop     r15
0x14017d6f4  pop     r14
0x14017d6f6  pop     r13
0x14017d6f8  pop     r12
0x14017d6fa  pop     rdi
0x14017d6fb  retn
```
