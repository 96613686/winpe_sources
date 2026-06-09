# CSelectiveWipe::LoadEdpUtilLibrary(void)

- ea: `0x1800b9714`
- end: `0x1800b9981`
- name: `?LoadEdpUtilLibrary@CSelectiveWipe@@CAJXZ`
- size: `621`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800b86ec`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180008b60`
- `0x180011314`
- `0x1800b9714`
- `0x1800bcb0c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800b9863`
- `KERNEL32!GetProcAddress` at `0x1800b98cd`
- `KERNEL32!GetProcAddress` at `0x1800b9863`
- `KERNEL32!GetProcAddress` at `0x1800b98cd`
- `KERNEL32!LoadLibraryExW` at `0x1800b97ec`
- `KERNEL32!LoadLibraryExW` at `0x1800b97ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9965`

## string_xrefs

- `0x1800b97df`: `edputil.dll`

## pseudocode

```c
__int64 CSelectiveWipe::LoadEdpUtilLibrary(void)
{
  _BYTE *v0; // rax
  char v1; // cl
  HMODULE v2; // r8
  int LastFailureAsHRESULT; // ebx
  __int16 v4; // ax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]
  int v8; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+34h] [rbp-24h]
  char v10; // [rsp+38h] [rbp-20h]
  const char *v11; // [rsp+40h] [rbp-18h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
  }
  if ( (v0[68] & 0x20) != 0 && v0[65] >= 6u )
  {
    v1 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v1 = 0;
LABEL_9:
  v10 = v1;
  v11 = "CSelectiveWipe::LoadEdpUtilLibrary";
  v8 = 0;
  v9 = 155;
  v12 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
    &lpCriticalSection,
    &CSelectiveWipe::m_cs);
  if ( CSelectiveWipe::m_hEdpUtilDll )
  {
    LastFailureAsHRESULT = v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::m_hEdpUtilDll = LoadLibraryExW(L"edputil.dll", 0, 0x800u);
    v2 = CSelectiveWipe::m_hEdpUtilDll;
    if ( !CSelectiveWipe::m_hEdpUtilDll )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 163;
LABEL_16:
      HIWORD(v9) = v4;
      goto LABEL_38;
    }
    v8 = 0;
    LOWORD(v9) = 163;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
      v2 = CSelectiveWipe::m_hEdpUtilDll;
    }
    CSelectiveWipe::pfncEdpGetIsManaged = (int (*)(void))GetProcAddress(v2, "EdpGetIsManaged");
    if ( !CSelectiveWipe::pfncEdpGetIsManaged )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 167;
      goto LABEL_16;
    }
    v8 = 0;
    LOWORD(v9) = 167;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::pfncEdpConvertProtectorToExternalId = (int (*)(const unsigned __int16 *, unsigned __int16 **))GetProcAddress(CSelectiveWipe::m_hEdpUtilDll, "EdpConvertProtectorToExternalId");
    if ( !CSelectiveWipe::pfncEdpConvertProtectorToExternalId )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 171;
      goto LABEL_16;
    }
    LastFailureAsHRESULT = 0;
    v8 = 0;
    LOWORD(v9) = 171;
  }
  if ( !CSelectiveWipe::m_spEdpMethods )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    LastFailureAsHRESULT = CEdpMethods::CreateInstance(&CSelectiveWipe::m_spEdpMethods);
    v8 = LastFailureAsHRESULT;
    v4 = 177;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_16;
    LOWORD(v9) = 177;
  }
LABEL_38:
  if ( v7 )
    LeaveCriticalSection(lpCriticalSection);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v8);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800b9714  push    rbp
0x1800b9716  push    rbx
0x1800b9717  push    r12
0x1800b9719  push    r15
0x1800b971b  mov     rbp, rsp
0x1800b971e  sub     rsp, 58h
0x1800b9722  mov     rax, cs:WPP_GLOBAL_Control
0x1800b9729  lea     r15, WPP_GLOBAL_Control
0x1800b9730  lea     r12, WPP_8f615fdb2b0232236e798df82271f47a_Traceguids
0x1800b9737  cmp     rax, r15
0x1800b973a  jz      short loc_1800B9760
0x1800b973c  test    byte ptr [rax+44h], 20h
0x1800b9740  jz      short loc_1800B9770
0x1800b9742  cmp     byte ptr [rax+41h], 6
0x1800b9746  jb      short loc_1800B9760
0x1800b9748  mov     rcx, [rax+38h]
0x1800b974c  mov     edx, 15h
0x1800b9751  mov     r8, r12
0x1800b9754  call    WPP_SF_
0x1800b9759  mov     rax, cs:WPP_GLOBAL_Control
0x1800b9760  test    byte ptr [rax+44h], 20h
0x1800b9764  jz      short loc_1800B9770
0x1800b9766  cmp     byte ptr [rax+41h], 6
0x1800b976a  jb      short loc_1800B9770
0x1800b976c  mov     cl, 1
0x1800b976e  jmp     short loc_1800B9772
0x1800b9770  xor     cl, cl
0x1800b9772  mov     [rbp+var_20], cl
0x1800b9775  lea     rax, aCselectivewipe_4; "CSelectiveWipe::LoadEdpUtilLibrary"
0x1800b977c  lea     rcx, [rbp+lpCriticalSection]
0x1800b9780  mov     [rbp+var_18], rax
0x1800b9784  lea     rdx, ?m_cs@CSelectiveWipe@@0VCEcsCriticalSection@@A; CEcsCriticalSection CSelectiveWipe::m_cs
0x1800b978b  mov     [rbp+var_28], 0
0x1800b9792  mov     [rbp+var_24], 9Bh
0x1800b9799  mov     [rbp+var_10], 0
0x1800b97a1  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x1800b97a6  cmp     cs:?m_hEdpUtilDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CSelectiveWipe::m_hEdpUtilDll
0x1800b97ae  jnz     loc_1800B9903
0x1800b97b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b97bb  cmp     rcx, r15
0x1800b97be  jz      short loc_1800B97DD
0x1800b97c0  test    byte ptr [rcx+44h], 20h
0x1800b97c4  jz      short loc_1800B97DD
0x1800b97c6  cmp     byte ptr [rcx+41h], 4
0x1800b97ca  jb      short loc_1800B97DD
0x1800b97cc  mov     rcx, [rcx+38h]
0x1800b97d0  mov     edx, 16h
0x1800b97d5  mov     r8, r12
0x1800b97d8  call    WPP_SF_
0x1800b97dd  xor     edx, edx; hFile
0x1800b97df  lea     rcx, aEdputilDll; "edputil.dll"
0x1800b97e6  mov     r8d, 800h; dwFlags
0x1800b97ec  call    cs:__imp_LoadLibraryExW
0x1800b97f2  mov     cs:?m_hEdpUtilDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CSelectiveWipe::m_hEdpUtilDll
0x1800b97f9  mov     r8, rax
0x1800b97fc  test    rax, rax
0x1800b97ff  jnz     short loc_1800B9819
0x1800b9801  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9806  mov     ebx, eax
0x1800b9808  mov     [rbp+var_28], eax
0x1800b980b  mov     eax, 0A3h
0x1800b9810  mov     word ptr [rbp+var_24+2], ax
0x1800b9814  jmp     loc_1800B995B
0x1800b9819  mov     eax, 0A3h
0x1800b981e  mov     [rbp+var_28], 0
0x1800b9825  mov     word ptr [rbp+var_24], ax
0x1800b9829  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9830  cmp     rcx, r15
0x1800b9833  jz      short loc_1800B9859
0x1800b9835  test    byte ptr [rcx+44h], 20h
0x1800b9839  jz      short loc_1800B9859
0x1800b983b  cmp     byte ptr [rcx+41h], 4
0x1800b983f  jb      short loc_1800B9859
0x1800b9841  mov     rcx, [rcx+38h]
0x1800b9845  mov     edx, 17h
0x1800b984a  mov     r8, r12
0x1800b984d  call    WPP_SF_
0x1800b9852  mov     r8, cs:?m_hEdpUtilDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CSelectiveWipe::m_hEdpUtilDll
0x1800b9859  lea     rdx, aEdpgetismanage; "EdpGetIsManaged"
0x1800b9860  mov     rcx, r8; hModule
0x1800b9863  call    cs:__imp_GetProcAddress
0x1800b9869  mov     cs:?pfncEdpGetIsManaged@CSelectiveWipe@@0P6AHXZEA, rax; int (*CSelectiveWipe::pfncEdpGetIsManaged)(void)
0x1800b9870  test    rax, rax
0x1800b9873  jnz     short loc_1800B9886
0x1800b9875  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b987a  mov     ebx, eax
0x1800b987c  mov     [rbp+var_28], eax
0x1800b987f  mov     eax, 0A7h
0x1800b9884  jmp     short loc_1800B9810
0x1800b9886  mov     eax, 0A7h
0x1800b988b  mov     [rbp+var_28], 0
0x1800b9892  mov     word ptr [rbp+var_24], ax
0x1800b9896  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b989d  cmp     rcx, r15
0x1800b98a0  jz      short loc_1800B98BF
0x1800b98a2  test    byte ptr [rcx+44h], 20h
0x1800b98a6  jz      short loc_1800B98BF
0x1800b98a8  cmp     byte ptr [rcx+41h], 4
0x1800b98ac  jb      short loc_1800B98BF
0x1800b98ae  mov     rcx, [rcx+38h]
0x1800b98b2  mov     edx, 18h
0x1800b98b7  mov     r8, r12
0x1800b98ba  call    WPP_SF_
0x1800b98bf  mov     rcx, cs:?m_hEdpUtilDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; hModule
0x1800b98c6  lea     rdx, aEdpconvertprot; "EdpConvertProtectorToExternalId"
0x1800b98cd  call    cs:__imp_GetProcAddress
0x1800b98d3  mov     cs:?pfncEdpConvertProtectorToExternalId@CSelectiveWipe@@0P6AJPEBGPEAPEAG@ZEA, rax; long (*CSelectiveWipe::pfncEdpConvertProtectorToExternalId)(ushort const *,ushort * *)
0x1800b98da  test    rax, rax
0x1800b98dd  jnz     short loc_1800B98F3
0x1800b98df  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b98e4  mov     ebx, eax
0x1800b98e6  mov     [rbp+var_28], eax
0x1800b98e9  mov     eax, 0ABh
0x1800b98ee  jmp     loc_1800B9810
0x1800b98f3  xor     ebx, ebx
0x1800b98f5  mov     eax, 0ABh
0x1800b98fa  mov     [rbp+var_28], ebx
0x1800b98fd  mov     word ptr [rbp+var_24], ax
0x1800b9901  jmp     short loc_1800B9906
0x1800b9903  mov     ebx, [rbp+var_28]
0x1800b9906  cmp     cs:?m_spEdpMethods@CSelectiveWipe@@0V?$CComPtr@UIEdpMethods@@@ATL@@A, 0; ATL::CComPtr<IEdpMethods> CSelectiveWipe::m_spEdpMethods
0x1800b990e  jnz     short loc_1800B995B
0x1800b9910  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9917  cmp     rcx, r15
0x1800b991a  jz      short loc_1800B9939
0x1800b991c  test    byte ptr [rcx+44h], 20h
0x1800b9920  jz      short loc_1800B9939
0x1800b9922  cmp     byte ptr [rcx+41h], 4
0x1800b9926  jb      short loc_1800B9939
0x1800b9928  mov     rcx, [rcx+38h]
0x1800b992c  mov     edx, 19h
0x1800b9931  mov     r8, r12
0x1800b9934  call    WPP_SF_
0x1800b9939  lea     rcx, ?m_spEdpMethods@CSelectiveWipe@@0V?$CComPtr@UIEdpMethods@@@ATL@@A; struct IEdpMethods **
0x1800b9940  call    ?CreateInstance@CEdpMethods@@SAJPEAPEAUIEdpMethods@@@Z; CEdpMethods::CreateInstance(IEdpMethods * *)
0x1800b9945  mov     ebx, eax
0x1800b9947  mov     [rbp+var_28], eax
0x1800b994a  test    eax, eax
0x1800b994c  mov     eax, 0B1h
0x1800b9951  js      loc_1800B9810
0x1800b9957  mov     word ptr [rbp+var_24], ax
0x1800b995b  cmp     [rbp+var_30], 0
0x1800b995f  jz      short loc_1800B996B
0x1800b9961  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800b9965  call    cs:__imp_LeaveCriticalSection
0x1800b996b  lea     rcx, [rbp+var_28]; this
0x1800b996f  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800b9974  mov     eax, ebx
0x1800b9976  add     rsp, 58h
0x1800b997a  pop     r15
0x1800b997c  pop     r12
0x1800b997e  pop     rbx
0x1800b997f  pop     rbp
0x1800b9980  retn
```
