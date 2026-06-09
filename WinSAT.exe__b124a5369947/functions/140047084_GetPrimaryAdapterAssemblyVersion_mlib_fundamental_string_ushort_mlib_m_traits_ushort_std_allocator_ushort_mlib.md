# GetPrimaryAdapterAssemblyVersion(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,_SYSTEMTIME &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140047084`
- end: `0x140047498`
- name: `?GetPrimaryAdapterAssemblyVersion@@YAKAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@00AEAU_SYSTEMTIME@@0@Z`
- size: `1044`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003cac0`
- `0x14004dcec`

## callees

- `0x140003611`
- `0x140005f10`
- `0x140016264`
- `0x140016480`
- `0x140016d04`
- `0x140019bd8`
- `0x14003ec14`
- `0x140046538`
- `0x140047084`
- `0x14007e498`
- `0x14007e970`
- `0x140113220`
- `0x1401132e0`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140047256`
- `KERNEL32!GetLastError` at `0x140047256`
- `KERNEL32!lstrcmpiW` at `0x14004739b`
- `KERNEL32!lstrcmpiW` at `0x14004739b`
- `KERNEL32!FileTimeToSystemTime` at `0x1400473bb`
- `KERNEL32!FileTimeToSystemTime` at `0x1400473bb`
- `KERNEL32!SetLastError` at `0x140047462`
- `KERNEL32!SetLastError` at `0x140047462`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x140047279`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x140047279`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140047456`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140047456`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x140047247`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x140047247`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x140047357`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x140047357`

## string_xrefs

- `0x14004720e`: `base\winsat\common\winsatutilities.cpp`
- `0x140047384`: `base\winsat\common\winsatutilities.cpp`
- `0x14004742e`: `base\winsat\common\winsatutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetPrimaryAdapterAssemblyVersion(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _SYSTEMTIME *a4,
        __int64 a5)
{
  D3DCommon *v8; // rcx
  D3DCommon *v9; // rcx
  int LastError; // ebx
  __int64 ClassDevs; // rdi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // r14
  DWORD i; // ebx
  unsigned int j; // esi
  int v17; // esi
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+48h] [rbp-B8h] BYREF
  FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME *v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  DEVPROPKEY *PropertyKey; // [rsp+70h] [rbp-90h]
  PBYTE PropertyBuffer; // [rsp+78h] [rbp-88h]
  DWORD PropertyBufferSize[2]; // [rsp+80h] [rbp-80h]
  const DEVPROPKEY *v28; // [rsp+88h] [rbp-78h]
  _BYTE *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  const DEVPROPKEY *v31; // [rsp+A0h] [rbp-60h]
  _BYTE *v32; // [rsp+A8h] [rbp-58h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  const DEVPROPKEY *v34; // [rsp+B8h] [rbp-48h]
  FILETIME *p_FileTime; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  const DEVPROPKEY *v37; // [rsp+D0h] [rbp-30h]
  WCHAR *v38; // [rsp+D8h] [rbp-28h]
  __int64 v39; // [rsp+E0h] [rbp-20h]
  _BYTE v40[1064]; // [rsp+F0h] [rbp-10h] BYREF
  int v41; // [rsp+518h] [rbp+418h]
  int v42; // [rsp+51Ch] [rbp+41Ch]
  int v43; // [rsp+520h] [rbp+420h]
  int v44; // [rsp+524h] [rbp+424h]
  struct _SYSTEMTIME SystemTime; // [rsp+540h] [rbp+440h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v47[512]; // [rsp+570h] [rbp+470h] BYREF
  _BYTE v48[512]; // [rsp+770h] [rbp+670h] BYREF
  _BYTE v49[512]; // [rsp+970h] [rbp+870h] BYREF
  WCHAR String1[2048]; // [rsp+B70h] [rbp+A70h] BYREF

  v23 = a4;
  v24 = a5;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v19);
  memset_0(v47, 0, sizeof(v47));
  memset_0(v48, 0, sizeof(v48));
  memset_0(v49, 0, sizeof(v49));
  FileTime = 0;
  SystemTime = 0;
  memset_0(String1, 0, sizeof(String1));
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  LastError = D3DCommon::DX9Init(v8);
  if ( LastError >= 0 )
  {
    ClassDevs = -1;
    v12 = qword_1401CBA60;
    if ( qword_1401CBA60 )
    {
      memset_0(v40, 0, 0x450u);
      LastError = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v12 + 40LL))(v12, 0, 0, v40);
      if ( LastError >= 0 )
      {
        v13 = (_QWORD *)FormatPNPString((unsigned int)v22, v41, v42, v43, v44);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
          &v19,
          *v13);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(&v19);
        v14 = v19;
        Log_Text_F(
          (__int64)"base\\winsat\\common\\winsatutilities.cpp",
          1101,
          "PNPID from DX9 call = %S",
          *(const wchar_t **)(v19 + 24));
        ClassDevs = (__int64)SetupDiGetClassDevsExW(&ClassGuid, 0, 0, 0x12u, 0, 0, 0);
        if ( ClassDevs == -1 )
        {
LABEL_6:
          LastError = GetLastError();
        }
        else
        {
          PropertyType = 0;
          for ( i = 0; SetupDiEnumDeviceInfo((HDEVINFO)ClassDevs, i, &DeviceInfoData); ++i )
          {
            PropertyKey = (DEVPROPKEY *)&DEVPKEY_Device_Manufacturer;
            PropertyBuffer = v47;
            *(_QWORD *)PropertyBufferSize = 512;
            v28 = &DEVPKEY_Device_DriverProvider;
            v29 = v48;
            v30 = 512;
            v31 = &DEVPKEY_Device_DriverVersion;
            v32 = v49;
            v33 = 512;
            v34 = &DEVPKEY_Device_DriverDate;
            p_FileTime = &FileTime;
            v36 = 8;
            v37 = &DEVPKEY_Device_HardwareIds;
            v38 = String1;
            v39 = 4096;
            for ( j = 0; j < 5; ++j )
            {
              if ( !SetupDiGetDevicePropertyW(
                      (HDEVINFO)ClassDevs,
                      &DeviceInfoData,
                      *(&PropertyKey + 3 * (int)j),
                      &PropertyType,
                      *(PBYTE *)&PropertyBufferSize[6 * j - 2],
                      PropertyBufferSize[6 * j],
                      0,
                      0) )
                goto LABEL_6;
            }
            Log_Text_F((__int64)"base\\winsat\\common\\winsatutilities.cpp", 1167, "Index [%d]: PNPID = %S", i, String1);
            v17 = lstrcmpiW(String1, *(LPCWSTR *)(v14 + 24));
            if ( !v17 || !i )
            {
              if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
                goto LABEL_6;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
                a1,
                v47);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
                a2,
                v48);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
                a3,
                v49);
              *v23 = SystemTime;
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
                v24,
                String1);
              if ( !v17 )
                Log_Text_F(
                  (__int64)"base\\winsat\\common\\winsatutilities.cpp",
                  1191,
                  "Matching device PnPID is %S",
                  String1);
            }
          }
          LastError = 0;
        }
      }
    }
    else
    {
      LastError = 31;
    }
    D3DCommon::DX9Shutdown(v9);
    if ( ClassDevs != -1 )
      SetupDiDestroyDeviceInfoList((HDEVINFO)ClassDevs);
  }
  if ( LastError )
    SetLastError(LastError);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140047084  push    rbp
0x140047086  push    rbx
0x140047087  push    rsi
0x140047088  push    rdi
0x140047089  push    r12
0x14004708b  push    r13
0x14004708d  push    r14
0x14004708f  push    r15
0x140047091  lea     rbp, [rsp-1A88h]
0x140047099  mov     eax, 1B88h
0x14004709e  call    _alloca_probe
0x1400470a3  sub     rsp, rax
0x1400470a6  mov     rax, cs:__security_cookie
0x1400470ad  xor     rax, rsp
0x1400470b0  mov     [rbp+1AC0h+var_50], rax
0x1400470b7  mov     [rsp+1BC0h+var_1B60], r9
0x1400470bc  mov     r13, r8
0x1400470bf  mov     r12, rdx
0x1400470c2  mov     r15, rcx
0x1400470c5  mov     rax, [rbp+1AC0h+arg_20]
0x1400470cc  mov     [rsp+1BC0h+var_1B58], rax
0x1400470d1  lea     rcx, [rsp+1BC0h+var_1B80]
0x1400470d6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1400470db  nop
0x1400470dc  mov     esi, 200h
0x1400470e1  mov     r8d, esi; Size
0x1400470e4  xor     edx, edx; Val
0x1400470e6  lea     rcx, [rbp+1AC0h+var_1650]; void *
0x1400470ed  call    memset_0
0x1400470f2  mov     r8d, esi; Size
0x1400470f5  xor     edx, edx; Val
0x1400470f7  lea     rcx, [rbp+1AC0h+var_1450]; void *
0x1400470fe  call    memset_0
0x140047103  mov     r8d, esi; Size
0x140047106  xor     edx, edx; Val
0x140047108  lea     rcx, [rbp+1AC0h+var_1250]; void *
0x14004710f  call    memset_0
0x140047114  mov     qword ptr [rsp+1BC0h+FileTime.dwLowDateTime], 0
0x14004711d  xorps   xmm0, xmm0
0x140047120  movups  xmmword ptr [rbp+1AC0h+SystemTime.wYear], xmm0
0x140047127  xor     edx, edx; Val
0x140047129  mov     r8d, 1000h; Size
0x14004712f  lea     rcx, [rbp+1AC0h+String1]; void *
0x140047136  call    memset_0
0x14004713b  xorps   xmm0, xmm0
0x14004713e  movups  xmmword ptr [rbp+1AC0h+DeviceInfoData.cbSize], xmm0
0x140047145  movups  xmmword ptr [rbp+1AC0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x14004714c  mov     [rbp+1AC0h+DeviceInfoData.cbSize], 20h ; ' '
0x140047156  call    ?DX9Init@D3DCommon@@YAJXZ; D3DCommon::DX9Init(void)
0x14004715b  mov     ebx, eax
0x14004715d  test    eax, eax
0x14004715f  js      loc_14004745C
0x140047165  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140047169  mov     rbx, cs:qword_1401CBA60
0x140047170  test    rbx, rbx
0x140047173  jnz     short loc_14004717D
0x140047175  lea     ebx, [rdi+20h]
0x140047178  jmp     loc_140047448
0x14004717d  xor     edx, edx; Val
0x14004717f  mov     r8d, 450h; Size
0x140047185  lea     rcx, [rbp+1AC0h+var_1AD0]; void *
0x140047189  call    memset_0
0x14004718e  mov     rax, [rbx]
0x140047191  lea     r9, [rbp+1AC0h+var_1AD0]
0x140047195  xor     r8d, r8d
0x140047198  xor     edx, edx
0x14004719a  mov     rcx, rbx
0x14004719d  mov     rax, [rax+28h]
0x1400471a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400471a6  mov     ebx, eax
0x1400471a8  test    eax, eax
0x1400471aa  js      loc_140047448
0x1400471b0  mov     eax, [rbp+1AC0h+var_169C]
0x1400471b6  mov     dword ptr [rsp+1BC0h+DeviceInfoSet], eax
0x1400471ba  mov     r9d, [rbp+1AC0h+var_16A0]
0x1400471c1  mov     r8d, [rbp+1AC0h+var_16A4]
0x1400471c8  mov     edx, [rbp+1AC0h+var_16A8]
0x1400471ce  lea     rcx, [rsp+1BC0h+var_1B68]
0x1400471d3  call    ?FormatPNPString@@YA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@KKKK@Z; FormatPNPString(ulong,ulong,ulong,ulong)
0x1400471d8  mov     rdx, [rax]
0x1400471db  lea     rcx, [rsp+1BC0h+var_1B80]
0x1400471e0  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1400471e5  lea     rcx, [rsp+1BC0h+var_1B68]
0x1400471ea  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400471ef  lea     rcx, [rsp+1BC0h+var_1B80]
0x1400471f4  call    ?strip_lt_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_lt_ws(void)
0x1400471f9  mov     r14, [rsp+1BC0h+var_1B80]
0x1400471fe  mov     r9, [r14+18h]
0x140047202  lea     r8, aPnpidFromDx9Ca; "PNPID from DX9 call = %S"
0x140047209  mov     edx, 44Dh
0x14004720e  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x140047215  call    Log_Text_F
0x14004721a  mov     [rsp+1BC0h+Reserved], 0; Reserved
0x140047223  mov     [rsp+1BC0h+MachineName], 0; MachineName
0x14004722c  mov     [rsp+1BC0h+DeviceInfoSet], 0; DeviceInfoSet
0x140047235  mov     r9d, 12h; Flags
0x14004723b  xor     r8d, r8d; hwndParent
0x14004723e  xor     edx, edx; Enumerator
0x140047240  lea     rcx, ClassGuid; ClassGuid
0x140047247  call    cs:__imp_SetupDiGetClassDevsExW
0x14004724d  mov     rdi, rax
0x140047250  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140047254  jnz     short loc_140047263
0x140047256  call    cs:__imp_GetLastError
0x14004725c  mov     ebx, eax
0x14004725e  jmp     loc_140047448
0x140047263  mov     [rsp+1BC0h+PropertyType], 0
0x14004726b  xor     ebx, ebx
0x14004726d  lea     r8, [rbp+1AC0h+DeviceInfoData]; DeviceInfoData
0x140047274  mov     edx, ebx; MemberIndex
0x140047276  mov     rcx, rdi; DeviceInfoSet
0x140047279  call    cs:__imp_SetupDiEnumDeviceInfo
0x14004727f  test    eax, eax
0x140047281  jz      loc_140047446
0x140047287  lea     rax, DEVPKEY_Device_Manufacturer
0x14004728e  mov     [rsp+1BC0h+PropertyKey], rax
0x140047293  lea     rax, [rbp+1AC0h+var_1650]
0x14004729a  mov     [rsp+1BC0h+PropertyBuffer], rax
0x14004729f  mov     qword ptr [rbp+1AC0h+PropertyBufferSize], rsi
0x1400472a3  lea     rax, DEVPKEY_Device_DriverProvider
0x1400472aa  mov     [rbp+1AC0h+var_1B38], rax
0x1400472ae  lea     rax, [rbp+1AC0h+var_1450]
0x1400472b5  mov     [rbp+1AC0h+var_1B30], rax
0x1400472b9  mov     [rbp+1AC0h+var_1B28], rsi
0x1400472bd  lea     rax, DEVPKEY_Device_DriverVersion
0x1400472c4  mov     [rbp+1AC0h+var_1B20], rax
0x1400472c8  lea     rax, [rbp+1AC0h+var_1250]
0x1400472cf  mov     [rbp+1AC0h+var_1B18], rax
0x1400472d3  mov     [rbp+1AC0h+var_1B10], rsi
0x1400472d7  lea     rax, DEVPKEY_Device_DriverDate
0x1400472de  mov     [rbp+1AC0h+var_1B08], rax
0x1400472e2  lea     rax, [rsp+1BC0h+FileTime]
0x1400472e7  mov     [rbp+1AC0h+var_1B00], rax
0x1400472eb  mov     [rbp+1AC0h+var_1AF8], 8
0x1400472f3  lea     rax, DEVPKEY_Device_HardwareIds
0x1400472fa  mov     [rbp+1AC0h+var_1AF0], rax
0x1400472fe  lea     rax, [rbp+1AC0h+String1]
0x140047305  mov     [rbp+1AC0h+var_1AE8], rax
0x140047309  mov     [rbp+1AC0h+var_1AE0], 1000h
0x140047311  xor     esi, esi
0x140047313  cmp     esi, 5
0x140047316  jnb     short loc_140047369
0x140047318  movsxd  rax, esi
0x14004731b  lea     r8, [rax+rax*2]
0x14004731f  mov     [rsp+1BC0h+Flags], 0; Flags
0x140047327  mov     [rsp+1BC0h+Reserved], 0; RequiredSize
0x140047330  mov     eax, [rbp+r8*8+1AC0h+PropertyBufferSize]
0x140047335  mov     dword ptr [rsp+1BC0h+MachineName], eax; PropertyBufferSize
0x140047339  mov     rax, [rsp+r8*8+1BC0h+PropertyBuffer]
0x14004733e  mov     [rsp+1BC0h+DeviceInfoSet], rax; PropertyBuffer
0x140047343  lea     r9, [rsp+1BC0h+PropertyType]; PropertyType
0x140047348  mov     r8, [rsp+r8*8+1BC0h+PropertyKey]; PropertyKey
0x14004734d  lea     rdx, [rbp+1AC0h+DeviceInfoData]; DeviceInfoData
0x140047354  mov     rcx, rdi; DeviceInfoSet
0x140047357  call    cs:__imp_SetupDiGetDevicePropertyW
0x14004735d  test    eax, eax
0x14004735f  jz      loc_140047256
0x140047365  inc     esi
0x140047367  jmp     short loc_140047313
0x140047369  lea     rax, [rbp+1AC0h+String1]
0x140047370  mov     [rsp+1BC0h+DeviceInfoSet], rax
0x140047375  mov     r9d, ebx
0x140047378  lea     r8, aIndexDPnpidS; "Index [%d]: PNPID = %S"
0x14004737f  mov     edx, 48Fh
0x140047384  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x14004738b  call    Log_Text_F
0x140047390  mov     rdx, [r14+18h]; lpString2
0x140047394  lea     rcx, [rbp+1AC0h+String1]; lpString1
0x14004739b  call    cs:__imp_lstrcmpiW
0x1400473a1  mov     esi, eax
0x1400473a3  test    eax, eax
0x1400473a5  jz      short loc_1400473AF
0x1400473a7  test    ebx, ebx
0x1400473a9  jnz     loc_14004743A
0x1400473af  lea     rdx, [rbp+1AC0h+SystemTime]; lpSystemTime
0x1400473b6  lea     rcx, [rsp+1BC0h+FileTime]; lpFileTime
0x1400473bb  call    cs:__imp_FileTimeToSystemTime
0x1400473c1  test    eax, eax
0x1400473c3  jz      loc_140047256
0x1400473c9  lea     rdx, [rbp+1AC0h+var_1650]
0x1400473d0  mov     rcx, r15
0x1400473d3  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x1400473d8  lea     rdx, [rbp+1AC0h+var_1450]
0x1400473df  mov     rcx, r12
0x1400473e2  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x1400473e7  lea     rdx, [rbp+1AC0h+var_1250]
0x1400473ee  mov     rcx, r13
0x1400473f1  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x1400473f6  movups  xmm0, xmmword ptr [rbp+1AC0h+SystemTime.wYear]
0x1400473fd  mov     rax, [rsp+1BC0h+var_1B60]
0x140047402  movdqu  xmmword ptr [rax], xmm0
0x140047406  lea     rdx, [rbp+1AC0h+String1]
0x14004740d  mov     rcx, [rsp+1BC0h+var_1B58]
0x140047412  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x140047417  test    esi, esi
0x140047419  jnz     short loc_14004743A
0x14004741b  lea     r9, [rbp+1AC0h+String1]
0x140047422  lea     r8, aMatchingDevice; "Matching device PnPID is %S"
0x140047429  mov     edx, 4A7h
0x14004742e  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x140047435  call    Log_Text_F
0x14004743a  inc     ebx
0x14004743c  mov     esi, 200h
0x140047441  jmp     loc_14004726D
0x140047446  xor     ebx, ebx
0x140047448  call    ?DX9Shutdown@D3DCommon@@YAXXZ; D3DCommon::DX9Shutdown(void)
0x14004744d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140047451  jz      short loc_14004745C
0x140047453  mov     rcx, rdi; DeviceInfoSet
0x140047456  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x14004745c  test    ebx, ebx
0x14004745e  jz      short loc_140047469
0x140047460  mov     ecx, ebx; dwErrCode
0x140047462  call    cs:__imp_SetLastError
0x140047468  nop
0x140047469  lea     rcx, [rsp+1BC0h+var_1B80]
0x14004746e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140047473  mov     eax, ebx
0x140047475  mov     rcx, [rbp+1AC0h+var_50]
0x14004747c  xor     rcx, rsp; StackCookie
0x14004747f  call    __security_check_cookie
0x140047484  add     rsp, 1B88h
0x14004748b  pop     r15
0x14004748d  pop     r14
0x14004748f  pop     r13
0x140047491  pop     r12
0x140047493  pop     rdi
0x140047494  pop     rsi
0x140047495  pop     rbx
0x140047496  pop     rbp
0x140047497  retn
```
