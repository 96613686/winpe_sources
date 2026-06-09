# FSSourceMediaSource::InternalOnEvent(IMFMediaEvent *,ulong,_GUID const &,long,tagPROPVARIANT const *,IMFAttributes * *)

- ea: `0x18003d190`
- end: `0x18003d569`
- name: `?InternalOnEvent@FSSourceMediaSource@@IEAAJPEAUIMFMediaEvent@@KAEBU_GUID@@JPEBUtagPROPVARIANT@@PEAPEAUIMFAttributes@@@Z`
- size: `985`
- prototype: `__int64 __fastcall(FSSourceMediaSource *__hidden this, struct IMFMediaEvent *, unsigned int, const struct _GUID *, HRESULT hrStatus, PROPVARIANT *pvValue, struct IMFAttributes **ppMFAttributes)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003eee0`
- `0x18003f0c0`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x180009f50`
- `0x18000a91c`
- `0x180017a3c`
- `0x18003d190`
- `0x18003d5cc`
- `0x1800408f8`
- `0x18004d714`
- `0x18004da70`
- `0x1800530bc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d4ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d518`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d4ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d2b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d2b7`
- `MFPlat!MFCreateAttributes` at `0x18003d3c6`
- `MFPlat!MFCreateAttributes` at `0x18003d3c6`
- `MFPlat!MFCreateMediaEvent` at `0x18003d269`
- `MFPlat!MFCreateMediaEvent` at `0x18003d269`

## pseudocode

```c
__int64 __fastcall FSSourceMediaSource::InternalOnEvent(
        FSSourceMediaSource *this,
        struct IMFMediaEvent *a2,
        unsigned int a3,
        const struct _GUID *a4,
        HRESULT hrStatus,
        PROPVARIANT *pvValue,
        struct IMFAttributes **ppMFAttributes)
{
  char v7; // di
  char v10; // bl
  int v12; // r15d
  GuidTrace *v13; // rax
  const char *v14; // rax
  __int64 v15; // r8
  bool v16; // zf
  struct IMFAttributes **v17; // r13
  HRESULT v18; // eax
  int v19; // edi
  __int64 v20; // rdx
  unsigned int v21; // r14d
  unsigned __int64 v22; // rdx
  unsigned int v23; // r15d
  const struct std::nothrow_t *unique; // rax
  _QWORD *v25; // r14
  HRESULT v26; // eax
  __int64 v27; // rdx
  unsigned int i; // r8d
  __int64 v29; // r10
  __int64 v30; // rdx
  __int64 v31; // rdx
  IMFMediaEvent *ppEvent; // [rsp+40h] [rbp-38h] BYREF
  __int64 v34; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v35[40]; // [rsp+50h] [rbp-28h] BYREF
  _QWORD *v36; // [rsp+C8h] [rbp+50h] BYREF

  v7 = 0;
  LODWORD(v36) = 0;
  ppEvent = a2;
  v10 = (char)a2;
  if ( a2 )
    ((void (__fastcall *)(struct IMFMediaEvent *))a2->lpVtbl->AddRef)(a2);
  v12 = hrStatus;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v13 = GuidTrace::GuidTrace((GuidTrace *)v35, a4);
    GuidTrace::GetString(v13);
    v14 = MFTRACE_STRING_FROM_MET(a3);
    WPP_SF_qqssD(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, (__int64)v14, v15, v12);
    v7 = 1;
  }
  if ( (v7 & 1) != 0 )
    FSString::~FSString((FSString *)v35, (const struct std::nothrow_t *)a2);
  v16 = ppEvent == 0;
  v17 = ppMFAttributes;
  *ppMFAttributes = 0;
  if ( v16 )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
    v18 = MFCreateMediaEvent(a3, a4, v12, pvValue, &ppEvent);
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, this, v18);
LABEL_41:
      if ( byte_18010EC4D )
      {
        v31 = 225;
LABEL_45:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v31,
          &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
          this,
          v19);
        goto LABEL_46;
      }
      goto LABEL_46;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_BYTE *)this + 104) )
  {
    v19 = *((_DWORD *)this + 27);
    if ( v19 < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 219;
LABEL_39:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, this, v19);
        goto LABEL_40;
      }
      goto LABEL_40;
    }
  }
  if ( !*((_QWORD *)this + 16) )
  {
    v19 = -1072873851;
    if ( g_wppLevels )
    {
      v20 = 220;
      goto LABEL_39;
    }
LABEL_40:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    goto LABEL_41;
  }
  v21 = a3 - 1;
  if ( !v21 || v21 - 799 <= 1 )
  {
    *((_DWORD *)this + 27) = v12;
    if ( v12 >= 0 )
      *((_DWORD *)this + 27) = -1072875810;
    v22 = (unsigned int)(16 * *((_DWORD *)this + 46));
    v36 = 0;
    v23 = v22;
    ppMFAttributes = 0;
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v34, v22);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=((void **)&v36, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v34);
    v25 = v36;
    if ( !v36 )
    {
      v19 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          221,
          &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
          this,
          -2147024882);
      goto LABEL_25;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v26 = MFCreateAttributes((IMFAttributes **)&ppMFAttributes, 1u);
    v19 = v26;
    if ( v26 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_25:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v36);
        goto LABEL_40;
      }
      v27 = 222;
LABEL_29:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, this, v26);
      goto LABEL_25;
    }
    for ( i = 0; i < *((_DWORD *)this + 46); v25[v29 + 1] = *(_QWORD *)(*(_QWORD *)(v30 + *((_QWORD *)this + 22)) + 144LL) )
    {
      v29 = i++;
      v30 = 8 * v29;
      v29 *= 2;
      LODWORD(v25[v29]) = *(_DWORD *)(*(_QWORD *)(v30 + *((_QWORD *)this + 22)) + 140LL);
      HIDWORD(v25[v29]) = *(_DWORD *)(*(_QWORD *)(v30 + *((_QWORD *)this + 22)) + 136LL);
    }
    v26 = ((__int64 (__fastcall *)(struct IMFAttributes **, __int64 *, _QWORD *, _QWORD))(*ppMFAttributes)[26].lpVtbl)(
            ppMFAttributes,
            FS_EVENTCALLBACK_STREAMS_TO_DISCONNECT,
            v25,
            v23);
    v19 = v26;
    if ( v26 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_25;
      v27 = 223;
      goto LABEL_29;
    }
    FSSourceMediaSource::InternalShutdown(this, 0);
    *v17 = (struct IMFAttributes *)ppMFAttributes;
    ppMFAttributes = 0;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v36);
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaEvent *))(**((_QWORD **)this + 16) + 48LL))(
          *((_QWORD *)this + 16),
          ppEvent);
  if ( v19 < 0 )
  {
    if ( g_wppLevels )
    {
      v20 = 224;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v31 = 226;
    goto LABEL_45;
  }
LABEL_46:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppEvent);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18003d190  push    rbp
0x18003d192  push    rbx
0x18003d193  push    rsi
0x18003d194  push    rdi
0x18003d195  push    r12
0x18003d197  push    r13
0x18003d199  push    r14
0x18003d19b  push    r15
0x18003d19d  mov     rbp, rsp
0x18003d1a0  sub     rsp, 78h
0x18003d1a4  xor     edi, edi
0x18003d1a6  mov     r12, r9
0x18003d1a9  mov     dword ptr [rbp+arg_8], edi
0x18003d1ac  mov     r14d, r8d
0x18003d1af  mov     [rbp+var_38], rdx
0x18003d1b3  mov     rbx, rdx
0x18003d1b6  mov     rsi, rcx
0x18003d1b9  test    rdx, rdx
0x18003d1bc  jz      short loc_18003D1CD
0x18003d1be  mov     rax, [rdx]
0x18003d1c1  mov     rcx, rdx
0x18003d1c4  mov     rax, [rax+8]
0x18003d1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1cd  cmp     cs:byte_18010EC4D, 8
0x18003d1d4  mov     r15d, [rbp+hrStatus]
0x18003d1d8  jb      short loc_18003D228
0x18003d1da  mov     rdx, r12; struct _GUID *
0x18003d1dd  lea     rcx, [rbp+var_28]; this
0x18003d1e1  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18003d1e6  mov     rcx, rax; this
0x18003d1e9  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18003d1ee  mov     ecx, r14d; unsigned int
0x18003d1f1  mov     r8, rax
0x18003d1f4  call    ?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z; MFTRACE_STRING_FROM_MET(ulong)
0x18003d1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d200  mov     r9, rsi
0x18003d203  mov     dword ptr [rsp+78h+var_40], r15d; char
0x18003d208  mov     [rsp+78h+var_48], r8; __int64
0x18003d20d  mov     [rsp+78h+var_50], rax; __int64
0x18003d212  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003d219  mov     [rsp+78h+ppEvent], rbx; char
0x18003d21e  call    WPP_SF_qqssD
0x18003d223  mov     edi, 1
0x18003d228  test    dil, 1
0x18003d22c  jz      short loc_18003D237
0x18003d22e  lea     rcx, [rbp+var_28]; this
0x18003d232  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18003d237  cmp     [rbp+var_38], 0
0x18003d23c  mov     r13, [rbp+ppMFAttributes]
0x18003d240  mov     qword ptr [r13+0], 0
0x18003d248  jnz     short loc_18003D2AD
0x18003d24a  lea     rcx, [rbp+var_38]
0x18003d24e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003d253  mov     r9, [rbp+pvValue]; pvValue
0x18003d257  lea     rax, [rbp+var_38]
0x18003d25b  mov     r8d, r15d; hrStatus
0x18003d25e  mov     [rsp+78h+ppEvent], rax; ppEvent
0x18003d263  mov     rdx, r12; guidExtendedType
0x18003d266  mov     ecx, r14d; met
0x18003d269  call    cs:__imp_MFCreateMediaEvent
0x18003d26f  xor     r12d, r12d
0x18003d272  mov     edi, eax
0x18003d274  test    eax, eax
0x18003d276  jns     short loc_18003D2B0
0x18003d278  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d27f  jb      loc_18003D505
0x18003d285  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d28c  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003d293  mov     edx, 0DAh
0x18003d298  mov     dword ptr [rsp+78h+ppEvent], eax
0x18003d29c  mov     r9, rsi
0x18003d29f  mov     rcx, [rcx+10h]
0x18003d2a3  call    WPP_SF_qD
0x18003d2a8  jmp     loc_18003D505
0x18003d2ad  xor     r12d, r12d
0x18003d2b0  lea     rbx, [rsi+40h]
0x18003d2b4  mov     rcx, rbx; lpCriticalSection
0x18003d2b7  call    cs:__imp_EnterCriticalSection
0x18003d2bd  cmp     [rsi+68h], r12b
0x18003d2c1  jz      short loc_18003D2E1
0x18003d2c3  mov     edi, [rsi+6Ch]
0x18003d2c6  test    edi, edi
0x18003d2c8  jns     short loc_18003D2E1
0x18003d2ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d2d1  jb      loc_18003D4FC
0x18003d2d7  mov     edx, 0DBh
0x18003d2dc  jmp     loc_18003D4DE
0x18003d2e1  cmp     [rsi+80h], r12
0x18003d2e8  jnz     short loc_18003D306
0x18003d2ea  mov     edi, 0C00D3E85h
0x18003d2ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d2f6  jb      loc_18003D4FC
0x18003d2fc  mov     edx, 0DCh
0x18003d301  jmp     loc_18003D4DE
0x18003d306  sub     r14d, 1
0x18003d30a  jz      short loc_18003D31F
0x18003d30c  sub     r14d, 31Fh
0x18003d313  jz      short loc_18003D31F
0x18003d315  cmp     r14d, 1
0x18003d319  jnz     loc_18003D4B3
0x18003d31f  mov     [rsi+6Ch], r15d
0x18003d323  test    r15d, r15d
0x18003d326  js      short loc_18003D32F
0x18003d328  mov     dword ptr [rsi+6Ch], 0C00D36DEh
0x18003d32f  mov     eax, [rsi+0B8h]
0x18003d335  lea     rcx, [rbp+var_30]
0x18003d339  shl     eax, 4
0x18003d33c  mov     edx, eax
0x18003d33e  mov     [rbp+arg_8], r12
0x18003d342  mov     r15d, eax
0x18003d345  mov     [rbp+ppMFAttributes], r12
0x18003d349  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003d34e  mov     rdx, rax
0x18003d351  lea     rcx, [rbp+arg_8]
0x18003d355  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18003d35a  lea     rcx, [rbp+var_30]
0x18003d35e  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18003d363  mov     r14, [rbp+arg_8]
0x18003d367  test    r14, r14
0x18003d36a  jnz     short loc_18003D3B4
0x18003d36c  mov     edi, 8007000Eh
0x18003d371  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d378  jb      short loc_18003D39D
0x18003d37a  mov     edx, 0DDh
0x18003d37f  mov     dword ptr [rsp+78h+ppEvent], edi
0x18003d383  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d38a  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003d391  mov     r9, rsi
0x18003d394  mov     rcx, [rcx+10h]
0x18003d398  call    WPP_SF_qD
0x18003d39d  lea     rcx, [rbp+ppMFAttributes]; void *
0x18003d3a1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003d3a6  lea     rcx, [rbp+arg_8]
0x18003d3aa  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18003d3af  jmp     loc_18003D4FC
0x18003d3b4  lea     rcx, [rbp+ppMFAttributes]
0x18003d3b8  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003d3bd  mov     edx, 1; cInitialSize
0x18003d3c2  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18003d3c6  call    cs:__imp_MFCreateAttributes
0x18003d3cc  mov     edi, eax
0x18003d3ce  test    eax, eax
0x18003d3d0  jns     short loc_18003D3E6
0x18003d3d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d3d9  jb      short loc_18003D39D
0x18003d3db  mov     edx, 0DEh
0x18003d3e0  mov     dword ptr [rsp+78h+ppEvent], eax
0x18003d3e4  jmp     short loc_18003D383
0x18003d3e6  mov     r8d, r12d
0x18003d3e9  cmp     [rsi+0B8h], r12d
0x18003d3f0  jbe     short loc_18003D44E
0x18003d3f2  mov     rax, [rsi+0B0h]
0x18003d3f9  mov     r10d, r8d
0x18003d3fc  inc     r8d
0x18003d3ff  lea     rdx, ds:0[r10*8]
0x18003d407  add     r10, r10
0x18003d40a  mov     rcx, [rdx+rax]
0x18003d40e  mov     eax, [rcx+8Ch]
0x18003d414  mov     [r14+r10*8], eax
0x18003d418  mov     rax, [rsi+0B0h]
0x18003d41f  mov     rcx, [rdx+rax]
0x18003d423  mov     eax, [rcx+88h]
0x18003d429  mov     [r14+r10*8+4], eax
0x18003d42e  mov     rax, [rsi+0B0h]
0x18003d435  mov     rcx, [rdx+rax]
0x18003d439  mov     rax, [rcx+90h]
0x18003d440  mov     [r14+r10*8+8], rax
0x18003d445  cmp     r8d, [rsi+0B8h]
0x18003d44c  jb      short loc_18003D3F2
0x18003d44e  mov     rcx, [rbp+ppMFAttributes]
0x18003d452  lea     rdx, FS_EVENTCALLBACK_STREAMS_TO_DISCONNECT
0x18003d459  mov     r9d, r15d
0x18003d45c  mov     r8, r14
0x18003d45f  mov     rax, [rcx]
0x18003d462  mov     rax, [rax+0D0h]
0x18003d469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d46e  mov     edi, eax
0x18003d470  test    eax, eax
0x18003d472  jns     short loc_18003D48B
0x18003d474  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d47b  jb      loc_18003D39D
0x18003d481  mov     edx, 0DFh
0x18003d486  jmp     loc_18003D3E0
0x18003d48b  xor     edx, edx; bool
0x18003d48d  mov     rcx, rsi; this
0x18003d490  call    ?InternalShutdown@FSSourceMediaSource@@IEAAX_N@Z; FSSourceMediaSource::InternalShutdown(bool)
0x18003d495  mov     rax, [rbp+ppMFAttributes]
0x18003d499  lea     rcx, [rbp+ppMFAttributes]; void *
0x18003d49d  mov     [r13+0], rax
0x18003d4a1  mov     [rbp+ppMFAttributes], r12
0x18003d4a5  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003d4aa  lea     rcx, [rbp+arg_8]
0x18003d4ae  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18003d4b3  mov     rcx, [rsi+80h]
0x18003d4ba  mov     rdx, [rbp+var_38]
0x18003d4be  mov     rax, [rcx]
0x18003d4c1  mov     rax, [rax+30h]
0x18003d4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4ca  mov     edi, eax
0x18003d4cc  test    eax, eax
0x18003d4ce  jns     short loc_18003D515
0x18003d4d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d4d7  jb      short loc_18003D4FC
0x18003d4d9  mov     edx, 0E0h
0x18003d4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4e5  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003d4ec  mov     r9, rsi
0x18003d4ef  mov     dword ptr [rsp+78h+ppEvent], edi
0x18003d4f3  mov     rcx, [rcx+10h]
0x18003d4f7  call    WPP_SF_qD
0x18003d4fc  mov     rcx, rbx; lpCriticalSection
0x18003d4ff  call    cs:__imp_LeaveCriticalSection
0x18003d505  cmp     cs:byte_18010EC4D, 1
0x18003d50c  jb      short loc_18003D54D
0x18003d50e  mov     edx, 0E1h
0x18003d513  jmp     short loc_18003D52C
0x18003d515  mov     rcx, rbx; lpCriticalSection
0x18003d518  call    cs:__imp_LeaveCriticalSection
0x18003d51e  cmp     cs:byte_18010EC4D, 8
0x18003d525  jb      short loc_18003D54D
0x18003d527  mov     edx, 0E2h
0x18003d52c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d533  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003d53a  mov     r9, rsi
0x18003d53d  mov     dword ptr [rsp+78h+ppEvent], edi
0x18003d541  mov     rcx, [rcx+0D8h]
0x18003d548  call    WPP_SF_qD
0x18003d54d  lea     rcx, [rbp+var_38]; void *
0x18003d551  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003d556  mov     eax, edi
0x18003d558  add     rsp, 78h
0x18003d55c  pop     r15
0x18003d55e  pop     r14
0x18003d560  pop     r13
0x18003d562  pop     r12
0x18003d564  pop     rdi
0x18003d565  pop     rsi
0x18003d566  pop     rbx
0x18003d567  pop     rbp
0x18003d568  retn
```
