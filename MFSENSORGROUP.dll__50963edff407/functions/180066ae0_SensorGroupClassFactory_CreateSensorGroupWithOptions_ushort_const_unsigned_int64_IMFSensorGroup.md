# SensorGroupClassFactory::CreateSensorGroupWithOptions(ushort const *,unsigned __int64,IMFSensorGroup * *)

- ea: `0x180066ae0`
- end: `0x180066f6b`
- name: `?CreateSensorGroupWithOptions@SensorGroupClassFactory@@UEAAJPEBG_KPEAPEAUIMFSensorGroup@@@Z`
- size: `1163`
- prototype: `__int64 __fastcall(SensorGroupClassFactory *this, const unsigned __int16 *, unsigned __int64, struct IMFSensorGroup **)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x180003ac0`
- `0x180003ce4`
- `0x180005b90`
- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x180012284`
- `0x18001b414`
- `0x18001c854`
- `0x18001c96c`
- `0x180028fe0`
- `0x18002c008`
- `0x1800356d8`
- `0x180035c4c`
- `0x18003611c`
- `0x180044f30`
- `0x180045900`
- `0x180051a1c`
- `0x180066ae0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180066c93`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180066c93`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066db6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066db6`

## pseudocode

```c
__int64 __fastcall SensorGroupClassFactory::CreateSensorGroupWithOptions(
        SensorGroupClassFactory *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        struct IMFSensorGroup **a4)
{
  char v4; // di
  int v7; // esi
  const char *v8; // r9
  unsigned int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // r14d
  signed int v13; // r12d
  _ULARGE_INTEGER v14; // rax
  FileTimeTrace *v15; // rax
  const char *String; // rbx
  FileTimeTrace *v17; // rax
  const char *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  FileTimeTrace *v21; // rax
  const char *v22; // rbx
  FileTimeTrace *v23; // rax
  const char *v24; // rax
  struct IMFSensorGroup *v25; // rax
  bool v27; // [rsp+50h] [rbp-B0h] BYREF
  BYTE PropertyBuffer[8]; // [rsp+58h] [rbp-A8h] BYREF
  struct IMFSensorGroup *v29; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+68h] [rbp-98h] BYREF
  _ULARGE_INTEGER v31; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v32; // [rsp+78h] [rbp-88h]
  struct IMFSensorGroup **v33; // [rsp+80h] [rbp-80h]
  void **v34; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v35[24]; // [rsp+90h] [rbp-70h] BYREF
  void **v36; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v37[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszDeviceInterface[264]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = a3;
  v32 = a3;
  v33 = a4;
  v7 = 0;
  v30 = 0;
  memset_0(pszDeviceInterface, 0, 0x208u);
  *(_QWORD *)PropertyBuffer = 0;
  v27 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    LODWORD(v8) = (_DWORD)a2;
    if ( !a2 )
      v8 = L"<nullptr>";
    WPP_SF_Si(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      149,
      (unsigned int)&WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
      (_DWORD)v8,
      v4);
  }
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_41;
    v10 = 150;
    goto LABEL_8;
  }
  v11 = FSGetUniqueSymbolicName(a2, pszDeviceInterface, 0x104u, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
        (char *)this - 8,
        v11);
    goto LABEL_41;
  }
  if ( !FSIsDeviceInterfaceEnabled(pszDeviceInterface) )
  {
    v9 = -1072873822;
    if ( g_wppLevels )
    {
      v10 = 152;
LABEL_8:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
        (char *)this - 8,
        v9);
    }
LABEL_41:
    if ( byte_18008D62D )
    {
      v20 = 158;
LABEL_51:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v20, &WPP_09150840c5f230171d137cf28cc6c946_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v12 = 5000;
  v13 = 0;
  if ( (int)FSIsNetworkCamera(pszDeviceInterface, &v27) >= 0 && v27 )
    v12 = 30000;
  while ( 1 )
  {
    v29 = 0;
    v31.QuadPart = 0;
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v29);
    v9 = LoadSensorGroupBySymbolicLink(pszDeviceInterface, v32, &v29);
    if ( (v9 & 0x80000000) == 0 )
      break;
    GetSystemTimePreciseAsFileTime(&v31);
    v14 = *(_ULARGE_INTEGER *)PropertyBuffer;
    if ( !*(_QWORD *)PropertyBuffer )
    {
      v30 = 0;
      if ( (int)FSGetDeviceNodeProperty(
                  pszDeviceInterface,
                  (DEVPROPKEY *)&DEVPKEY_Device_LastArrivalDate,
                  PropertyBuffer,
                  8u,
                  &v30) < 0
        || (v14 = *(_ULARGE_INTEGER *)PropertyBuffer, !*(_QWORD *)PropertyBuffer) )
      {
        if ( byte_18008D62D )
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            154,
            (unsigned int)&WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
            v9,
            (__int64)pszDeviceInterface);
        if ( g_wppLevels >= 8u )
        {
          v19 = 155;
          goto LABEL_39;
        }
LABEL_40:
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v29);
        goto LABEL_41;
      }
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v15 = FileTimeTrace::FileTimeTrace((FileTimeTrace *)&v36, (const union _ULARGE_INTEGER *)PropertyBuffer);
      String = FSString::GetString((FileTimeTrace *)((char *)v15 + 8));
      v7 |= 0xCu;
      v17 = FileTimeTrace::FileTimeTrace((FileTimeTrace *)&v34, &v31);
      v18 = FSString::GetString((FileTimeTrace *)((char *)v17 + 8));
      WPP_SF_DddssS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v13,
        v12 / 0x1F4,
        (__int64)v18,
        (__int64)String,
        (__int64)pszDeviceInterface);
      v14 = *(_ULARGE_INTEGER *)PropertyBuffer;
    }
    if ( (v7 & 8) != 0 )
    {
      v7 &= ~8u;
      v34 = &BlobTrace::`vftable';
      FSString::~FSString((FSString *)v35);
      v14 = *(_ULARGE_INTEGER *)PropertyBuffer;
    }
    if ( (v7 & 4) != 0 )
    {
      v7 &= ~4u;
      v36 = &BlobTrace::`vftable';
      FSString::~FSString((FSString *)v37);
      v14 = *(_ULARGE_INTEGER *)PropertyBuffer;
    }
    if ( !v14.QuadPart || v14.QuadPart >= v31.QuadPart || v14.QuadPart + 10000 * v12 <= v31.QuadPart )
    {
      if ( g_wppLevels >= 8u )
      {
        v19 = 157;
LABEL_39:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
          (char *)this - 8,
          v9);
      }
      goto LABEL_40;
    }
    Sleep(0x1F4u);
    ++v13;
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v29);
    if ( v13 >= (int)(v12 / 0x1F4) )
      goto LABEL_41;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v21 = FileTimeTrace::FileTimeTrace((FileTimeTrace *)&v34, (const union _ULARGE_INTEGER *)PropertyBuffer);
    v22 = FSString::GetString((FileTimeTrace *)((char *)v21 + 8));
    LOBYTE(v7) = v7 | 3;
    v23 = FileTimeTrace::FileTimeTrace((FileTimeTrace *)&v36, &v31);
    v24 = FSString::GetString((FileTimeTrace *)((char *)v23 + 8));
    WPP_SF_dssS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v24, (__int64)v22, (__int64)pszDeviceInterface);
  }
  if ( (v7 & 2) != 0 )
  {
    LOBYTE(v7) = v7 & 0xFD;
    v36 = &BlobTrace::`vftable';
    FSString::~FSString((FSString *)v37);
  }
  if ( (v7 & 1) != 0 )
  {
    v34 = &BlobTrace::`vftable';
    FSString::~FSString((FSString *)v35);
  }
  v25 = v29;
  v29 = 0;
  *v33 = v25;
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v29);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v20 = 159;
    goto LABEL_51;
  }
  return v9;
}

```

## disassembly

```asm
0x180066ae0  push    rbp
0x180066ae2  push    rbx
0x180066ae3  push    rsi
0x180066ae4  push    rdi
0x180066ae5  push    r12
0x180066ae7  push    r13
0x180066ae9  push    r14
0x180066aeb  push    r15
0x180066aed  lea     rbp, [rsp-1F8h]
0x180066af5  sub     rsp, 2F8h
0x180066afc  mov     rax, cs:__security_cookie
0x180066b03  xor     rax, rsp
0x180066b06  mov     [rbp+230h+var_50], rax
0x180066b0d  mov     rdi, r8
0x180066b10  mov     [rsp+330h+var_2B8], r8
0x180066b15  mov     rbx, rdx
0x180066b18  mov     [rbp+230h+var_2B0], r9
0x180066b1c  mov     r15, rcx
0x180066b1f  xor     esi, esi
0x180066b21  xor     edx, edx; Val
0x180066b23  mov     [rsp+330h+var_2C8], esi
0x180066b27  mov     r8d, 208h; Size
0x180066b2d  lea     rcx, [rbp+230h+pszDeviceInterface]; void *
0x180066b31  call    memset_0
0x180066b36  mov     qword ptr [rsp+330h+PropertyBuffer], rsi
0x180066b3b  mov     [rsp+330h+var_2E0], sil
0x180066b40  cmp     cs:byte_18008D62D, 8
0x180066b47  lea     r14, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180066b4e  jb      short loc_180066B81
0x180066b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b57  lea     rax, aNullptr; "<nullptr>"
0x180066b5e  test    rbx, rbx
0x180066b61  mov     [rsp+330h+var_310], rdi
0x180066b66  mov     r9, rbx
0x180066b69  mov     edx, 95h
0x180066b6e  cmovz   r9, rax
0x180066b72  mov     r8, r14
0x180066b75  mov     rcx, [rcx+0D8h]
0x180066b7c  call    WPP_SF_Si
0x180066b81  test    rbx, rbx
0x180066b84  jnz     short loc_180066BBD
0x180066b86  mov     edi, 80070057h
0x180066b8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066b92  jb      loc_180066E4F
0x180066b98  mov     edx, 96h
0x180066b9d  mov     dword ptr [rsp+330h+var_310], edi
0x180066ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180066ba8  lea     r9, [r15-8]
0x180066bac  mov     r8, r14
0x180066baf  mov     rcx, [rcx+10h]
0x180066bb3  call    WPP_SF_qD
0x180066bb8  jmp     loc_180066E4F
0x180066bbd  xor     r9d, r9d; unsigned int *
0x180066bc0  lea     rdx, [rbp+230h+pszDeviceInterface]; unsigned __int16 *
0x180066bc4  mov     r8d, 104h; unsigned int
0x180066bca  mov     rcx, rbx; pszDeviceInterface
0x180066bcd  call    ?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z; FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)
0x180066bd2  mov     edi, eax
0x180066bd4  test    eax, eax
0x180066bd6  jns     short loc_180066BF0
0x180066bd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066bdf  jb      loc_180066E4F
0x180066be5  mov     edx, 97h
0x180066bea  mov     dword ptr [rsp+330h+var_310], eax
0x180066bee  jmp     short loc_180066BA1
0x180066bf0  lea     rcx, [rbp+230h+pszDeviceInterface]; unsigned __int16 *
0x180066bf4  call    ?FSIsDeviceInterfaceEnabled@@YA_NPEBG@Z; FSIsDeviceInterfaceEnabled(ushort const *)
0x180066bf9  test    al, al
0x180066bfb  jnz     short loc_180066C16
0x180066bfd  mov     edi, 0C00D3EA2h
0x180066c02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066c09  jb      loc_180066E4F
0x180066c0f  mov     edx, 98h
0x180066c14  jmp     short loc_180066B9D
0x180066c16  lea     rdx, [rsp+330h+var_2E0]; bool *
0x180066c1b  mov     r14d, 1388h
0x180066c21  lea     rcx, [rbp+230h+pszDeviceInterface]; pszDeviceInterface
0x180066c25  xor     r12d, r12d
0x180066c28  call    ?FSIsNetworkCamera@@YAJPEBGPEA_N@Z; FSIsNetworkCamera(ushort const *,bool *)
0x180066c2d  test    eax, eax
0x180066c2f  js      short loc_180066C3F
0x180066c31  cmp     [rsp+330h+var_2E0], sil
0x180066c36  mov     eax, 7530h
0x180066c3b  cmovnz  r14d, eax
0x180066c3f  mov     eax, 10624DD3h
0x180066c44  lea     rbx, ??_7BlobTrace@@6B@; const BlobTrace::`vftable'
0x180066c4b  mul     r14d
0x180066c4e  mov     r13d, edx
0x180066c51  shr     r13d, 5
0x180066c55  lea     rcx, [rsp+330h+var_2D0]
0x180066c5a  mov     [rsp+330h+var_2D0], 0
0x180066c63  mov     qword ptr [rsp+330h+var_2C0], 0
0x180066c6c  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180066c71  mov     rdx, [rsp+330h+var_2B8]; unsigned __int64
0x180066c76  lea     r8, [rsp+330h+var_2D0]; struct IMFSensorGroup **
0x180066c7b  lea     rcx, [rbp+230h+pszDeviceInterface]; pszDeviceInterface
0x180066c7f  call    ?LoadSensorGroupBySymbolicLink@@YAJPEBG_KPEAPEAUIMFSensorGroup@@@Z; LoadSensorGroupBySymbolicLink(ushort const *,unsigned __int64,IMFSensorGroup * *)
0x180066c84  mov     edi, eax
0x180066c86  test    eax, eax
0x180066c88  jns     loc_180066E66
0x180066c8e  lea     rcx, [rsp+330h+var_2C0]
0x180066c93  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180066c99  mov     rax, qword ptr [rsp+330h+PropertyBuffer]
0x180066c9e  test    rax, rax
0x180066ca1  jnz     short loc_180066CE2
0x180066ca3  mov     [rsp+330h+var_2C8], eax
0x180066ca7  lea     r8, [rsp+330h+PropertyBuffer]; PropertyBuffer
0x180066cac  lea     rax, [rsp+330h+var_2C8]
0x180066cb1  mov     r9d, 8; unsigned int
0x180066cb7  lea     rdx, DEVPKEY_Device_LastArrivalDate; PropertyKey
0x180066cbe  mov     [rsp+330h+var_310], rax; unsigned int *
0x180066cc3  lea     rcx, [rbp+230h+pszDeviceInterface]; pszDeviceInterface
0x180066cc7  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180066ccc  test    eax, eax
0x180066cce  js      loc_180066DD4
0x180066cd4  mov     rax, qword ptr [rsp+330h+PropertyBuffer]
0x180066cd9  test    rax, rax
0x180066cdc  jz      loc_180066DD4
0x180066ce2  cmp     cs:byte_18008D62D, 8
0x180066ce9  jb      short loc_180066D5E
0x180066ceb  lea     rdx, [rsp+330h+PropertyBuffer]; union _ULARGE_INTEGER *
0x180066cf0  lea     rcx, [rbp+230h+var_288]; this
0x180066cf4  call    ??0FileTimeTrace@@QEAA@PEBT_ULARGE_INTEGER@@@Z; FileTimeTrace::FileTimeTrace(_ULARGE_INTEGER const *)
0x180066cf9  lea     rcx, [rax+8]; this
0x180066cfd  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180066d02  lea     rcx, [rbp+230h+var_2A8]; this
0x180066d06  mov     rbx, rax
0x180066d09  lea     rdx, [rsp+330h+var_2C0]; union _ULARGE_INTEGER *
0x180066d0e  or      esi, 0Ch
0x180066d11  call    ??0FileTimeTrace@@QEAA@PEBT_ULARGE_INTEGER@@@Z; FileTimeTrace::FileTimeTrace(_ULARGE_INTEGER const *)
0x180066d16  lea     rcx, [rax+8]; this
0x180066d1a  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180066d1f  lea     rcx, [rbp+230h+pszDeviceInterface]
0x180066d23  mov     r9d, edi
0x180066d26  mov     [rsp+330h+var_2F0], rcx; __int64
0x180066d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d32  mov     [rsp+330h+var_2F8], rbx; __int64
0x180066d37  mov     [rsp+330h+var_300], rax; __int64
0x180066d3c  mov     dword ptr [rsp+330h+var_308], r13d; char
0x180066d41  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180066d48  mov     dword ptr [rsp+330h+var_310], r12d; char
0x180066d4d  call    WPP_SF_DddssS
0x180066d52  mov     rax, qword ptr [rsp+330h+PropertyBuffer]
0x180066d57  lea     rbx, ??_7BlobTrace@@6B@; const BlobTrace::`vftable'
0x180066d5e  test    sil, 8
0x180066d62  jz      short loc_180066D79
0x180066d64  and     esi, 0FFFFFFF7h
0x180066d67  mov     [rbp+230h+var_2A8], rbx
0x180066d6b  lea     rcx, [rbp+230h+var_2A0]; this
0x180066d6f  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180066d74  mov     rax, qword ptr [rsp+330h+PropertyBuffer]
0x180066d79  test    sil, 4
0x180066d7d  jz      short loc_180066D94
0x180066d7f  and     esi, 0FFFFFFFBh
0x180066d82  mov     [rbp+230h+var_288], rbx
0x180066d86  lea     rcx, [rbp+230h+var_280]; this
0x180066d8a  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180066d8f  mov     rax, qword ptr [rsp+330h+PropertyBuffer]
0x180066d94  test    rax, rax
0x180066d97  jz      short loc_180066E18
0x180066d99  cmp     rax, qword ptr [rsp+330h+var_2C0]
0x180066d9e  jnb     short loc_180066E18
0x180066da0  imul    edx, r14d, 2710h
0x180066da7  add     rdx, rax
0x180066daa  cmp     rdx, qword ptr [rsp+330h+var_2C0]
0x180066daf  jbe     short loc_180066E18
0x180066db1  mov     ecx, 1F4h; dwMilliseconds
0x180066db6  call    cs:__imp_Sleep
0x180066dbc  lea     rcx, [rsp+330h+var_2D0]
0x180066dc1  inc     r12d
0x180066dc4  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180066dc9  cmp     r12d, r13d
0x180066dcc  jl      loc_180066C55
0x180066dd2  jmp     short loc_180066E4F
0x180066dd4  cmp     cs:byte_18008D62D, 1
0x180066ddb  jb      short loc_180066E08
0x180066ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180066de4  lea     rax, [rbp+230h+pszDeviceInterface]
0x180066de8  mov     edx, 9Ah
0x180066ded  mov     [rsp+330h+var_310], rax
0x180066df2  mov     r9d, edi
0x180066df5  lea     r8, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180066dfc  mov     rcx, [rcx+0D8h]
0x180066e03  call    WPP_SF_dS
0x180066e08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180066e0f  jb      short loc_180066E45
0x180066e11  mov     edx, 9Bh
0x180066e16  jmp     short loc_180066E26
0x180066e18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180066e1f  jb      short loc_180066E45
0x180066e21  mov     edx, 9Dh
0x180066e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e2d  lea     r9, [r15-8]
0x180066e31  lea     r8, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180066e38  mov     dword ptr [rsp+330h+var_310], edi
0x180066e3c  mov     rcx, [rcx+10h]
0x180066e40  call    WPP_SF_qD
0x180066e45  lea     rcx, [rsp+330h+var_2D0]
0x180066e4a  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180066e4f  cmp     cs:byte_18008D62D, 1
0x180066e56  jb      loc_180066F46
0x180066e5c  mov     edx, 9Eh
0x180066e61  jmp     loc_180066F29
0x180066e66  cmp     cs:byte_18008D62D, 8
0x180066e6d  jb      short loc_180066ED3
0x180066e6f  lea     rdx, [rsp+330h+PropertyBuffer]; union _ULARGE_INTEGER *
0x180066e74  lea     rcx, [rbp+230h+var_2A8]; this
0x180066e78  call    ??0FileTimeTrace@@QEAA@PEBT_ULARGE_INTEGER@@@Z; FileTimeTrace::FileTimeTrace(_ULARGE_INTEGER const *)
0x180066e7d  lea     rcx, [rax+8]; this
0x180066e81  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180066e86  lea     rcx, [rbp+230h+var_288]; this
0x180066e8a  mov     rbx, rax
0x180066e8d  lea     rdx, [rsp+330h+var_2C0]; union _ULARGE_INTEGER *
0x180066e92  or      esi, 3
0x180066e95  call    ??0FileTimeTrace@@QEAA@PEBT_ULARGE_INTEGER@@@Z; FileTimeTrace::FileTimeTrace(_ULARGE_INTEGER const *)
0x180066e9a  lea     rcx, [rax+8]; this
0x180066e9e  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180066ea3  lea     rcx, [rbp+230h+pszDeviceInterface]
0x180066ea7  mov     r9d, r12d
0x180066eaa  mov     [rsp+330h+var_300], rcx; __int64
0x180066eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180066eb6  mov     qword ptr [rsp+330h+var_308], rbx; __int64
0x180066ebb  mov     [rsp+330h+var_310], rax; __int64
0x180066ec0  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180066ec7  call    WPP_SF_dssS
0x180066ecc  lea     rbx, ??_7BlobTrace@@6B@; const BlobTrace::`vftable'
0x180066ed3  test    sil, 2
0x180066ed7  jz      short loc_180066EE9
0x180066ed9  and     esi, 0FFFFFFFDh
0x180066edc  mov     [rbp+230h+var_288], rbx
0x180066ee0  lea     rcx, [rbp+230h+var_280]; this
0x180066ee4  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180066ee9  test    sil, 1
0x180066eed  jz      short loc_180066EFC
0x180066eef  lea     rcx, [rbp+230h+var_2A0]; this
0x180066ef3  mov     [rbp+230h+var_2A8], rbx
0x180066ef7  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180066efc  mov     rax, [rsp+330h+var_2D0]
0x180066f01  mov     rcx, [rbp+230h+var_2B0]
0x180066f05  mov     [rsp+330h+var_2D0], 0
0x180066f0e  mov     [rcx], rax
0x180066f11  lea     rcx, [rsp+330h+var_2D0]
0x180066f16  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180066f1b  cmp     cs:byte_18008D62D, 8
0x180066f22  jb      short loc_180066F46
0x180066f24  mov     edx, 9Fh
0x180066f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f30  lea     r8, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180066f37  mov     r9d, edi
0x180066f3a  mov     rcx, [rcx+0D8h]
0x180066f41  call    WPP_SF_d
0x180066f46  mov     eax, edi
0x180066f48  mov     rcx, [rbp+230h+var_50]
0x180066f4f  xor     rcx, rsp; StackCookie
0x180066f52  call    __security_check_cookie
0x180066f57  add     rsp, 2F8h
0x180066f5e  pop     r15
0x180066f60  pop     r14
0x180066f62  pop     r13
0x180066f64  pop     r12
0x180066f66  pop     rdi
0x180066f67  pop     rsi
0x180066f68  pop     rbx
0x180066f69  pop     rbp
0x180066f6a  retn
```
