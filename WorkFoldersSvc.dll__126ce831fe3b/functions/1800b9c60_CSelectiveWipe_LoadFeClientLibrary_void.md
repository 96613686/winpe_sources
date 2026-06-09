# CSelectiveWipe::LoadFeClientLibrary(void)

- ea: `0x1800b9c60`
- end: `0x1800b9ec9`
- name: `?LoadFeClientLibrary@CSelectiveWipe@@CAJXZ`
- size: `617`
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
- `0x1800b9c60`
- `0x1800bcb0c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800b9dad`
- `KERNEL32!GetProcAddress` at `0x1800b9e15`
- `KERNEL32!GetProcAddress` at `0x1800b9dad`
- `KERNEL32!GetProcAddress` at `0x1800b9e15`
- `KERNEL32!LoadLibraryExW` at `0x1800b9d38`
- `KERNEL32!LoadLibraryExW` at `0x1800b9d38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9ead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9ead`

## string_xrefs

- `0x1800b9d2b`: `feclient.dll`

## pseudocode

```c
__int64 CSelectiveWipe::LoadFeClientLibrary(void)
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
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
  v11 = "CSelectiveWipe::LoadFeClientLibrary";
  v8 = 0;
  v9 = 115;
  v12 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
    &lpCriticalSection,
    &CSelectiveWipe::m_cs);
  if ( CSelectiveWipe::m_hFeClientDll )
  {
    LastFailureAsHRESULT = v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::m_hFeClientDll = LoadLibraryExW(L"feclient.dll", 0, 0x800u);
    v2 = CSelectiveWipe::m_hFeClientDll;
    if ( !CSelectiveWipe::m_hFeClientDll )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 123;
LABEL_16:
      HIWORD(v9) = v4;
      goto LABEL_38;
    }
    v8 = 0;
    LOWORD(v9) = 123;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
      v2 = CSelectiveWipe::m_hFeClientDll;
    }
    CSelectiveWipe::pfncEfsClientQueryProtectors = (int (*)(const unsigned __int16 *, struct _ENCRYPTION_PROTECTOR_LIST **))GetProcAddress(v2, "EfsClientQueryProtectors");
    if ( !CSelectiveWipe::pfncEfsClientQueryProtectors )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 127;
      goto LABEL_16;
    }
    v8 = 0;
    LOWORD(v9) = 127;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    CSelectiveWipe::pfncEfsClientFreeProtectorList = (int (*)(struct _ENCRYPTION_PROTECTOR_LIST *))GetProcAddress(
                                                                                                     CSelectiveWipe::m_hFeClientDll,
                                                                                                     "EfsClientFreeProtectorList");
    if ( !CSelectiveWipe::pfncEfsClientFreeProtectorList )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v8 = LastFailureAsHRESULT;
      v4 = 131;
      goto LABEL_16;
    }
    LastFailureAsHRESULT = 0;
    v8 = 0;
    LOWORD(v9) = 131;
  }
  if ( !CSelectiveWipe::m_spEdpMethods )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_8f615fdb2b0232236e798df82271f47a_Traceguids);
    }
    LastFailureAsHRESULT = CEdpMethods::CreateInstance(&CSelectiveWipe::m_spEdpMethods);
    v8 = LastFailureAsHRESULT;
    v4 = 137;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_16;
    LOWORD(v9) = 137;
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
0x1800b9c60  push    rbp
0x1800b9c62  push    rbx
0x1800b9c63  push    r12
0x1800b9c65  push    r15
0x1800b9c67  mov     rbp, rsp
0x1800b9c6a  sub     rsp, 58h
0x1800b9c6e  mov     rax, cs:WPP_GLOBAL_Control
0x1800b9c75  lea     r15, WPP_GLOBAL_Control
0x1800b9c7c  lea     r12, WPP_8f615fdb2b0232236e798df82271f47a_Traceguids
0x1800b9c83  cmp     rax, r15
0x1800b9c86  jz      short loc_1800B9CAC
0x1800b9c88  test    byte ptr [rax+44h], 20h
0x1800b9c8c  jz      short loc_1800B9CBC
0x1800b9c8e  cmp     byte ptr [rax+41h], 6
0x1800b9c92  jb      short loc_1800B9CAC
0x1800b9c94  mov     rcx, [rax+38h]
0x1800b9c98  mov     edx, 10h
0x1800b9c9d  mov     r8, r12
0x1800b9ca0  call    WPP_SF_
0x1800b9ca5  mov     rax, cs:WPP_GLOBAL_Control
0x1800b9cac  test    byte ptr [rax+44h], 20h
0x1800b9cb0  jz      short loc_1800B9CBC
0x1800b9cb2  cmp     byte ptr [rax+41h], 6
0x1800b9cb6  jb      short loc_1800B9CBC
0x1800b9cb8  mov     cl, 1
0x1800b9cba  jmp     short loc_1800B9CBE
0x1800b9cbc  xor     cl, cl
0x1800b9cbe  mov     [rbp+var_20], cl
0x1800b9cc1  lea     rax, aCselectivewipe_10; "CSelectiveWipe::LoadFeClientLibrary"
0x1800b9cc8  lea     rcx, [rbp+lpCriticalSection]
0x1800b9ccc  mov     [rbp+var_18], rax
0x1800b9cd0  lea     rdx, ?m_cs@CSelectiveWipe@@0VCEcsCriticalSection@@A; CEcsCriticalSection CSelectiveWipe::m_cs
0x1800b9cd7  mov     [rbp+var_28], 0
0x1800b9cde  mov     [rbp+var_24], 73h ; 's'
0x1800b9ce5  mov     [rbp+var_10], 0
0x1800b9ced  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x1800b9cf2  cmp     cs:?m_hFeClientDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CSelectiveWipe::m_hFeClientDll
0x1800b9cfa  jnz     loc_1800B9E4B
0x1800b9d00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9d07  cmp     rcx, r15
0x1800b9d0a  jz      short loc_1800B9D29
0x1800b9d0c  test    byte ptr [rcx+44h], 20h
0x1800b9d10  jz      short loc_1800B9D29
0x1800b9d12  cmp     byte ptr [rcx+41h], 4
0x1800b9d16  jb      short loc_1800B9D29
0x1800b9d18  mov     rcx, [rcx+38h]
0x1800b9d1c  mov     edx, 11h
0x1800b9d21  mov     r8, r12
0x1800b9d24  call    WPP_SF_
0x1800b9d29  xor     edx, edx; hFile
0x1800b9d2b  lea     rcx, aFeclientDll; "feclient.dll"
0x1800b9d32  mov     r8d, 800h; dwFlags
0x1800b9d38  call    cs:__imp_LoadLibraryExW
0x1800b9d3e  mov     cs:?m_hFeClientDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CSelectiveWipe::m_hFeClientDll
0x1800b9d45  mov     r8, rax
0x1800b9d48  test    rax, rax
0x1800b9d4b  jnz     short loc_1800B9D65
0x1800b9d4d  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9d52  mov     ebx, eax
0x1800b9d54  mov     [rbp+var_28], eax
0x1800b9d57  mov     eax, 7Bh ; '{'
0x1800b9d5c  mov     word ptr [rbp+var_24+2], ax
0x1800b9d60  jmp     loc_1800B9EA3
0x1800b9d65  mov     eax, 7Bh ; '{'
0x1800b9d6a  mov     [rbp+var_28], 0
0x1800b9d71  mov     word ptr [rbp+var_24], ax
0x1800b9d75  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9d7c  cmp     rcx, r15
0x1800b9d7f  jz      short loc_1800B9DA3
0x1800b9d81  test    byte ptr [rcx+44h], 20h
0x1800b9d85  jz      short loc_1800B9DA3
0x1800b9d87  cmp     byte ptr [rcx+41h], 4
0x1800b9d8b  jb      short loc_1800B9DA3
0x1800b9d8d  mov     rcx, [rcx+38h]
0x1800b9d91  lea     edx, [rax-69h]
0x1800b9d94  mov     r8, r12
0x1800b9d97  call    WPP_SF_
0x1800b9d9c  mov     r8, cs:?m_hFeClientDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CSelectiveWipe::m_hFeClientDll
0x1800b9da3  lea     rdx, aEfsclientquery; "EfsClientQueryProtectors"
0x1800b9daa  mov     rcx, r8; hModule
0x1800b9dad  call    cs:__imp_GetProcAddress
0x1800b9db3  mov     cs:?pfncEfsClientQueryProtectors@CSelectiveWipe@@0P6AJPEBGPEAPEAU_ENCRYPTION_PROTECTOR_LIST@@@ZEA, rax; long (*CSelectiveWipe::pfncEfsClientQueryProtectors)(ushort const *,_ENCRYPTION_PROTECTOR_LIST * *)
0x1800b9dba  test    rax, rax
0x1800b9dbd  jnz     short loc_1800B9DD0
0x1800b9dbf  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9dc4  mov     ebx, eax
0x1800b9dc6  mov     [rbp+var_28], eax
0x1800b9dc9  mov     eax, 7Fh
0x1800b9dce  jmp     short loc_1800B9D5C
0x1800b9dd0  mov     eax, 7Fh
0x1800b9dd5  mov     [rbp+var_28], 0
0x1800b9ddc  mov     word ptr [rbp+var_24], ax
0x1800b9de0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9de7  cmp     rcx, r15
0x1800b9dea  jz      short loc_1800B9E07
0x1800b9dec  test    byte ptr [rcx+44h], 20h
0x1800b9df0  jz      short loc_1800B9E07
0x1800b9df2  cmp     byte ptr [rcx+41h], 4
0x1800b9df6  jb      short loc_1800B9E07
0x1800b9df8  mov     rcx, [rcx+38h]
0x1800b9dfc  lea     edx, [rax-6Ch]
0x1800b9dff  mov     r8, r12
0x1800b9e02  call    WPP_SF_
0x1800b9e07  mov     rcx, cs:?m_hFeClientDll@CSelectiveWipe@@0PEAUHINSTANCE__@@EA; hModule
0x1800b9e0e  lea     rdx, aEfsclientfreep; "EfsClientFreeProtectorList"
0x1800b9e15  call    cs:__imp_GetProcAddress
0x1800b9e1b  mov     cs:?pfncEfsClientFreeProtectorList@CSelectiveWipe@@0P6AJPEAU_ENCRYPTION_PROTECTOR_LIST@@@ZEA, rax; long (*CSelectiveWipe::pfncEfsClientFreeProtectorList)(_ENCRYPTION_PROTECTOR_LIST *)
0x1800b9e22  test    rax, rax
0x1800b9e25  jnz     short loc_1800B9E3B
0x1800b9e27  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800b9e2c  mov     ebx, eax
0x1800b9e2e  mov     [rbp+var_28], eax
0x1800b9e31  mov     eax, 83h
0x1800b9e36  jmp     loc_1800B9D5C
0x1800b9e3b  xor     ebx, ebx
0x1800b9e3d  mov     eax, 83h
0x1800b9e42  mov     [rbp+var_28], ebx
0x1800b9e45  mov     word ptr [rbp+var_24], ax
0x1800b9e49  jmp     short loc_1800B9E4E
0x1800b9e4b  mov     ebx, [rbp+var_28]
0x1800b9e4e  cmp     cs:?m_spEdpMethods@CSelectiveWipe@@0V?$CComPtr@UIEdpMethods@@@ATL@@A, 0; ATL::CComPtr<IEdpMethods> CSelectiveWipe::m_spEdpMethods
0x1800b9e56  jnz     short loc_1800B9EA3
0x1800b9e58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9e5f  cmp     rcx, r15
0x1800b9e62  jz      short loc_1800B9E81
0x1800b9e64  test    byte ptr [rcx+44h], 20h
0x1800b9e68  jz      short loc_1800B9E81
0x1800b9e6a  cmp     byte ptr [rcx+41h], 4
0x1800b9e6e  jb      short loc_1800B9E81
0x1800b9e70  mov     rcx, [rcx+38h]
0x1800b9e74  mov     edx, 14h
0x1800b9e79  mov     r8, r12
0x1800b9e7c  call    WPP_SF_
0x1800b9e81  lea     rcx, ?m_spEdpMethods@CSelectiveWipe@@0V?$CComPtr@UIEdpMethods@@@ATL@@A; struct IEdpMethods **
0x1800b9e88  call    ?CreateInstance@CEdpMethods@@SAJPEAPEAUIEdpMethods@@@Z; CEdpMethods::CreateInstance(IEdpMethods * *)
0x1800b9e8d  mov     ebx, eax
0x1800b9e8f  mov     [rbp+var_28], eax
0x1800b9e92  test    eax, eax
0x1800b9e94  mov     eax, 89h
0x1800b9e99  js      loc_1800B9D5C
0x1800b9e9f  mov     word ptr [rbp+var_24], ax
0x1800b9ea3  cmp     [rbp+var_30], 0
0x1800b9ea7  jz      short loc_1800B9EB3
0x1800b9ea9  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800b9ead  call    cs:__imp_LeaveCriticalSection
0x1800b9eb3  lea     rcx, [rbp+var_28]; this
0x1800b9eb7  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800b9ebc  mov     eax, ebx
0x1800b9ebe  add     rsp, 58h
0x1800b9ec2  pop     r15
0x1800b9ec4  pop     r12
0x1800b9ec6  pop     rbx
0x1800b9ec7  pop     rbp
0x1800b9ec8  retn
```
