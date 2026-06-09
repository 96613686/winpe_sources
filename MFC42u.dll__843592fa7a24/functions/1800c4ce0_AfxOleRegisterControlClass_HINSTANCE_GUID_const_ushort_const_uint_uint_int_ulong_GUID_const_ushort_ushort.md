# AfxOleRegisterControlClass(HINSTANCE__ *,_GUID const &,ushort const *,uint,uint,int,ulong,_GUID const &,ushort,ushort)

- ea: `0x1800c4ce0`
- end: `0x1800c50a0`
- name: `?AfxOleRegisterControlClass@@YAHPEAUHINSTANCE__@@AEBU_GUID@@PEBGIIHK1GG@Z`
- size: `960`
- prototype: `__int64 __fastcall(HINSTANCE, GUID *rguid, LPCWSTR lpSubKey, UINT uID, unsigned int Value, char, unsigned int, GUID *, unsigned __int16, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000b3a0`
- `0x180014640`
- `0x180019290`
- `0x180038490`
- `0x18009ba50`
- `0x1800c4ce0`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!_ltow_s` at `0x1800c4dd5`
- `msvcrt!_ltow_s` at `0x1800c4dd5`
- `msvcrt!_itow_s` at `0x1800c4dbc`
- `msvcrt!_itow_s` at `0x1800c4dbc`
- `msvcrt!swprintf_s` at `0x1800c4dff`
- `msvcrt!swprintf_s` at `0x1800c4e21`
- `msvcrt!swprintf_s` at `0x1800c4dff`
- `msvcrt!swprintf_s` at `0x1800c4e21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4e5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4e97`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4e5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4e97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c502c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c502c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c503f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c504f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c505f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c503f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c504f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c505f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4fe6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4fe6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c4d2c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c4d45`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c4d2c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c4d45`
- `ADVAPI32!RegSetValueW` at `0x1800c4f84`
- `ADVAPI32!RegSetValueW` at `0x1800c4fa9`
- `ADVAPI32!RegSetValueW` at `0x1800c4f84`
- `ADVAPI32!RegSetValueW` at `0x1800c4fa9`

## string_xrefs

- `0x1800c4e13`: `CLSID\%s`
- `0x1800c5020`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AfxOleRegisterControlClass(
        HINSTANCE a1,
        GUID *rguid,
        unsigned __int16 *lpSubKey,
        UINT uID,
        unsigned int Value,
        char a6,
        unsigned int a7,
        GUID *rguida,
        unsigned __int16 a9,
        unsigned __int16 a10)
{
  unsigned int v13; // ebx
  __int64 v14; // rax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v19; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v20; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR v21; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v22[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v23; // [rsp+88h] [rbp-78h]
  __int128 v24; // [rsp+98h] [rbp-68h]
  wchar_t *v25; // [rsp+A8h] [rbp-58h]
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR v27[40]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t SubKey[264]; // [rsp+150h] [rbp+50h] BYREF
  wchar_t Buffer[264]; // [rsp+360h] [rbp+260h] BYREF
  wchar_t v30[264]; // [rsp+570h] [rbp+470h] BYREF
  wchar_t v31[264]; // [rsp+780h] [rbp+680h] BYREF

  if ( StringFromGUID2(rguid, sz, 39) != 39 || StringFromGUID2(rguida, v27, 39) != 39 )
    return 0;
  v13 = 0;
  v21 = _afxPchNil;
  AfxGetModuleShortFileName(a1, (struct CString *)&v21);
  v19 = (unsigned __int16 *)_afxPchNil;
  if ( !(unsigned int)CString::LoadStringW((CString *)&v19, uID) )
    CString::operator=(&v19, sz);
  _itow_s(Value, Buffer, 0x104u, 10);
  _ltow_s(a7, v30, 0x104u, 10);
  dwOptions = a10;
  swprintf_s(v31, 0x104u, L"%d.%d", a9, dwOptions);
  phkResult = 0;
  hKey = 0;
  swprintf_s(SubKey, 0x104u, L"CLSID\\%s", sz);
  if ( !RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)
    && !RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
  {
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v22[0] = v19;
    v22[1] = sz;
    v13 = AfxOleRegisterHelper(
            (const unsigned __int16 *const *)&_afxCtrlProgID,
            (const unsigned __int16 *const *)v22,
            2,
            1,
            hKey);
    if ( v13 )
    {
      v22[1] = lpSubKey;
      *(_QWORD *)&v23 = v21;
      *((_QWORD *)&v23 + 1) = Buffer;
      *(_QWORD *)&v24 = v30;
      *((_QWORD *)&v24 + 1) = v27;
      v25 = v31;
      v13 = AfxOleRegisterHelper(
              (const unsigned __int16 *const *)&_afxCtrlClassID,
              (const unsigned __int16 *const *)v22,
              7,
              1,
              phkResult);
      if ( v13 )
      {
        if ( (a6 & 1) != 0 )
        {
          if ( RegSetValueW(hKey, L"Insertable", 1u, &Data, 0)
            || (v13 = 1, RegSetValueW(phkResult, L"Insertable", 1u, &Data, 0)) )
          {
            v13 = 0;
          }
        }
        if ( (a6 & 2) != 0 )
        {
          v20 = 0;
          if ( RegOpenKeyExW(phkResult, L"InprocServer32", 0, 0x2000000u, &v20) )
          {
            v13 = 0;
          }
          else
          {
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)&aApartment[2 * v14] );
            v13 = RegSetValueExW(v20, L"ThreadingModel", 0, 1u, aApartment, 2 * v14 + 2) == 0;
            RegCloseKey(v20);
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  CString::~CString((CString *)&v19);
  CString::~CString((CString *)&v21);
  return v13;
}

```

## disassembly

```asm
0x1800c4ce0  push    rbp
0x1800c4ce2  push    rbx
0x1800c4ce3  push    rsi
0x1800c4ce4  push    rdi
0x1800c4ce5  push    r14
0x1800c4ce7  push    r15
0x1800c4ce9  lea     rbp, [rsp-8A8h]
0x1800c4cf1  sub     rsp, 9A8h
0x1800c4cf8  mov     rax, cs:__security_cookie
0x1800c4cff  xor     rax, rsp
0x1800c4d02  mov     [rbp+8D0h+var_40], rax
0x1800c4d09  mov     r14d, r9d
0x1800c4d0c  mov     rdi, r8
0x1800c4d0f  mov     rax, rdx
0x1800c4d12  mov     rsi, rcx
0x1800c4d15  mov     rbx, [rbp+8D0h+rguid]
0x1800c4d1c  mov     r15d, 27h ; '''
0x1800c4d22  mov     r8d, r15d; cchMax
0x1800c4d25  lea     rdx, [rbp+8D0h+sz]; lpsz
0x1800c4d29  mov     rcx, rax; rguid
0x1800c4d2c  call    cs:__imp_StringFromGUID2
0x1800c4d32  cmp     eax, r15d
0x1800c4d35  jnz     loc_1800C507F
0x1800c4d3b  mov     r8d, r15d; cchMax
0x1800c4d3e  lea     rdx, [rbp+8D0h+var_8D0]; lpsz
0x1800c4d42  mov     rcx, rbx; rguid
0x1800c4d45  call    cs:__imp_StringFromGUID2
0x1800c4d4b  cmp     eax, r15d
0x1800c4d4e  jnz     loc_1800C507F
0x1800c4d54  xor     r15d, r15d
0x1800c4d57  mov     ebx, r15d
0x1800c4d5a  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800c4d61  mov     [rsp+9D0h+var_960], rax
0x1800c4d66  lea     rdx, [rsp+9D0h+var_960]; struct CString *
0x1800c4d6b  mov     rcx, rsi; HINSTANCE
0x1800c4d6e  call    ?AfxGetModuleShortFileName@@YAXPEAUHINSTANCE__@@AEAVCString@@@Z; AfxGetModuleShortFileName(HINSTANCE__ *,CString &)
0x1800c4d73  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800c4d7a  mov     [rsp+9D0h+var_970], rax
0x1800c4d7f  mov     edx, r14d; uID
0x1800c4d82  lea     rcx, [rsp+9D0h+var_970]; this
0x1800c4d87  call    ?LoadStringW@CString@@QEAAHI@Z; CString::LoadStringW(uint)
0x1800c4d8c  test    eax, eax
0x1800c4d8e  jnz     short loc_1800C4D9E
0x1800c4d90  lea     rdx, [rbp+8D0h+sz]
0x1800c4d94  lea     rcx, [rsp+9D0h+var_970]
0x1800c4d99  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800c4d9e  mov     esi, 0Ah
0x1800c4da3  mov     r9d, esi; Radix
0x1800c4da6  mov     r14d, 104h
0x1800c4dac  mov     r8d, r14d; BufferCount
0x1800c4daf  lea     rdx, [rbp+8D0h+Buffer]; Buffer
0x1800c4db6  mov     ecx, [rbp+8D0h+Value]; Value
0x1800c4dbc  call    cs:__imp__itow_s
0x1800c4dc2  mov     r9d, esi; Radix
0x1800c4dc5  mov     r8d, r14d; BufferCount
0x1800c4dc8  lea     rdx, [rbp+8D0h+var_460]; Buffer
0x1800c4dcf  mov     ecx, [rbp+8D0h+arg_30]; Value
0x1800c4dd5  call    cs:__imp__ltow_s
0x1800c4ddb  movzx   eax, [rbp+8D0h+arg_48]
0x1800c4de2  movzx   r9d, [rbp+8D0h+arg_40]
0x1800c4dea  mov     [rsp+9D0h+dwOptions], eax
0x1800c4dee  lea     r8, aDD; "%d.%d"
0x1800c4df5  mov     edx, r14d; BufferCount
0x1800c4df8  lea     rcx, [rbp+8D0h+var_250]; Buffer
0x1800c4dff  call    cs:__imp_swprintf_s
0x1800c4e05  mov     [rsp+9D0h+var_980], r15
0x1800c4e0a  mov     [rsp+9D0h+hKey], r15
0x1800c4e0f  lea     r9, [rbp+8D0h+sz]
0x1800c4e13  lea     r8, aClsidS; "CLSID\\%s"
0x1800c4e1a  mov     edx, r14d; BufferCount
0x1800c4e1d  lea     rcx, [rbp+8D0h+SubKey]; Buffer
0x1800c4e21  call    cs:__imp_swprintf_s
0x1800c4e27  mov     [rsp+9D0h+lpdwDisposition], r15; lpdwDisposition
0x1800c4e2c  lea     rax, [rsp+9D0h+var_980]
0x1800c4e31  mov     [rsp+9D0h+phkResult], rax; phkResult
0x1800c4e36  mov     [rsp+9D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800c4e3b  mov     r14d, 2000000h
0x1800c4e41  mov     [rsp+9D0h+samDesired], r14d; samDesired
0x1800c4e46  mov     [rsp+9D0h+dwOptions], r15d; dwOptions
0x1800c4e4b  xor     r9d, r9d; lpClass
0x1800c4e4e  xor     r8d, r8d; Reserved
0x1800c4e51  lea     rdx, [rbp+8D0h+SubKey]; lpSubKey
0x1800c4e55  mov     rsi, 0FFFFFFFF80000000h
0x1800c4e5c  mov     rcx, rsi; hKey
0x1800c4e5f  call    cs:__imp_RegCreateKeyExW
0x1800c4e65  test    eax, eax
0x1800c4e67  jnz     loc_1800C5045
0x1800c4e6d  mov     [rsp+9D0h+lpdwDisposition], r15; lpdwDisposition
0x1800c4e72  lea     rax, [rsp+9D0h+hKey]
0x1800c4e77  mov     [rsp+9D0h+phkResult], rax; phkResult
0x1800c4e7c  mov     [rsp+9D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800c4e81  mov     [rsp+9D0h+samDesired], r14d; samDesired
0x1800c4e86  mov     [rsp+9D0h+dwOptions], r15d; dwOptions
0x1800c4e8b  xor     r9d, r9d; lpClass
0x1800c4e8e  xor     r8d, r8d; Reserved
0x1800c4e91  mov     rdx, rdi; lpSubKey
0x1800c4e94  mov     rcx, rsi; hKey
0x1800c4e97  call    cs:__imp_RegCreateKeyExW
0x1800c4e9d  test    eax, eax
0x1800c4e9f  jnz     loc_1800C5045
0x1800c4ea5  xorps   xmm0, xmm0
0x1800c4ea8  xor     eax, eax
0x1800c4eaa  movups  xmmword ptr [rsp+9D0h+var_958], xmm0
0x1800c4eaf  movups  [rbp+8D0h+var_948], xmm0
0x1800c4eb3  movups  [rbp+8D0h+var_938], xmm0
0x1800c4eb7  mov     [rbp+8D0h+var_928], rax
0x1800c4ebb  mov     rax, [rsp+9D0h+var_970]
0x1800c4ec0  mov     [rsp+9D0h+var_958], rax
0x1800c4ec5  lea     rax, [rbp+8D0h+sz]
0x1800c4ec9  mov     [rbp+8D0h+var_958+8], rax
0x1800c4ecd  mov     rax, [rsp+9D0h+hKey]
0x1800c4ed2  mov     qword ptr [rsp+9D0h+dwOptions], rax; HKEY
0x1800c4ed7  mov     esi, 1
0x1800c4edc  mov     r9d, esi; int
0x1800c4edf  lea     r8d, [rsi+1]; int
0x1800c4ee3  lea     rdx, [rsp+9D0h+var_958]; unsigned __int16 **
0x1800c4ee8  lea     rcx, ?_afxCtrlProgID@@3QBQEBGB; unsigned __int16 **
0x1800c4eef  call    ?AfxOleRegisterHelper@@YAHPEBQEBG0HHPEAUHKEY__@@@Z; AfxOleRegisterHelper(ushort const * const *,ushort const * const *,int,int,HKEY__ *)
0x1800c4ef4  mov     ebx, eax
0x1800c4ef6  test    eax, eax
0x1800c4ef8  jz      loc_1800C5045
0x1800c4efe  mov     [rbp+8D0h+var_958+8], rdi
0x1800c4f02  mov     rax, [rsp+9D0h+var_960]
0x1800c4f07  mov     qword ptr [rbp+8D0h+var_948], rax
0x1800c4f0b  lea     rax, [rbp+8D0h+Buffer]
0x1800c4f12  mov     qword ptr [rbp+8D0h+var_948+8], rax
0x1800c4f16  lea     rax, [rbp+8D0h+var_460]
0x1800c4f1d  mov     qword ptr [rbp+8D0h+var_938], rax
0x1800c4f21  lea     rax, [rbp+8D0h+var_8D0]
0x1800c4f25  mov     qword ptr [rbp+8D0h+var_938+8], rax
0x1800c4f29  lea     rax, [rbp+8D0h+var_250]
0x1800c4f30  mov     [rbp+8D0h+var_928], rax
0x1800c4f34  mov     rax, [rsp+9D0h+var_980]
0x1800c4f39  mov     qword ptr [rsp+9D0h+dwOptions], rax; HKEY
0x1800c4f3e  mov     r9d, esi; int
0x1800c4f41  lea     r8d, [rsi+6]; int
0x1800c4f45  lea     rdx, [rsp+9D0h+var_958]; unsigned __int16 **
0x1800c4f4a  lea     rcx, ?_afxCtrlClassID@@3QBQEBGB; unsigned __int16 **
0x1800c4f51  call    ?AfxOleRegisterHelper@@YAHPEBQEBG0HHPEAUHKEY__@@@Z; AfxOleRegisterHelper(ushort const * const *,ushort const * const *,int,int,HKEY__ *)
0x1800c4f56  mov     ebx, eax
0x1800c4f58  test    eax, eax
0x1800c4f5a  jz      loc_1800C5045
0x1800c4f60  test    [rbp+8D0h+arg_28], sil
0x1800c4f67  jz      short loc_1800C4FB8
0x1800c4f69  mov     [rsp+9D0h+dwOptions], r15d; cbData
0x1800c4f6e  lea     r9, Data; lpData
0x1800c4f75  mov     r8d, esi; dwType
0x1800c4f78  lea     rdx, aInsertable; "Insertable"
0x1800c4f7f  mov     rcx, [rsp+9D0h+hKey]; hKey
0x1800c4f84  call    cs:__imp_RegSetValueW
0x1800c4f8a  test    eax, eax
0x1800c4f8c  jnz     short loc_1800C4FB5
0x1800c4f8e  mov     [rsp+9D0h+dwOptions], r15d; cbData
0x1800c4f93  lea     r9, Data; lpData
0x1800c4f9a  mov     r8d, esi; dwType
0x1800c4f9d  lea     rdx, aInsertable; "Insertable"
0x1800c4fa4  mov     rcx, [rsp+9D0h+var_980]; hKey
0x1800c4fa9  call    cs:__imp_RegSetValueW
0x1800c4faf  test    eax, eax
0x1800c4fb1  mov     ebx, esi
0x1800c4fb3  jz      short loc_1800C4FB8
0x1800c4fb5  mov     ebx, r15d
0x1800c4fb8  test    [rbp+8D0h+arg_28], 2
0x1800c4fbf  jz      loc_1800C5045
0x1800c4fc5  mov     [rsp+9D0h+var_968], r15
0x1800c4fca  lea     rax, [rsp+9D0h+var_968]
0x1800c4fcf  mov     qword ptr [rsp+9D0h+dwOptions], rax; phkResult
0x1800c4fd4  mov     r9d, r14d; samDesired
0x1800c4fd7  xor     r8d, r8d; ulOptions
0x1800c4fda  lea     rdx, aInprocserver32; "InprocServer32"
0x1800c4fe1  mov     rcx, [rsp+9D0h+var_980]; hKey
0x1800c4fe6  call    cs:__imp_RegOpenKeyExW
0x1800c4fec  test    eax, eax
0x1800c4fee  jz      short loc_1800C4FF5
0x1800c4ff0  mov     ebx, r15d
0x1800c4ff3  jmp     short loc_1800C5045
0x1800c4ff5  lea     rcx, aApartment; "Apartment"
0x1800c4ffc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c5000  inc     rax
0x1800c5003  cmp     [rcx+rax*2], r15w
0x1800c5008  jnz     short loc_1800C5000
0x1800c500a  lea     eax, ds:2[rax*2]
0x1800c5011  mov     [rsp+9D0h+samDesired], eax; cbData
0x1800c5015  mov     qword ptr [rsp+9D0h+dwOptions], rcx; lpData
0x1800c501a  mov     r9d, esi; dwType
0x1800c501d  xor     r8d, r8d; Reserved
0x1800c5020  lea     rdx, ValueName; "ThreadingModel"
0x1800c5027  mov     rcx, [rsp+9D0h+var_968]; hKey
0x1800c502c  call    cs:__imp_RegSetValueExW
0x1800c5032  mov     ebx, r15d
0x1800c5035  test    eax, eax
0x1800c5037  setz    bl
0x1800c503a  mov     rcx, [rsp+9D0h+var_968]; hKey
0x1800c503f  call    cs:__imp_RegCloseKey
0x1800c5045  mov     rcx, [rsp+9D0h+hKey]; hKey
0x1800c504a  test    rcx, rcx
0x1800c504d  jz      short loc_1800C5055
0x1800c504f  call    cs:__imp_RegCloseKey
0x1800c5055  mov     rcx, [rsp+9D0h+var_980]; hKey
0x1800c505a  test    rcx, rcx
0x1800c505d  jz      short loc_1800C5066
0x1800c505f  call    cs:__imp_RegCloseKey
0x1800c5065  nop
0x1800c5066  lea     rcx, [rsp+9D0h+var_970]; this
0x1800c506b  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800c5070  nop
0x1800c5071  lea     rcx, [rsp+9D0h+var_960]; this
0x1800c5076  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800c507b  mov     eax, ebx
0x1800c507d  jmp     short loc_1800C5081
0x1800c507f  xor     eax, eax
0x1800c5081  mov     rcx, [rbp+8D0h+var_40]
0x1800c5088  xor     rcx, rsp; StackCookie
0x1800c508b  call    __security_check_cookie
0x1800c5090  add     rsp, 9A8h
0x1800c5097  pop     r15
0x1800c5099  pop     r14
0x1800c509b  pop     rdi
0x1800c509c  pop     rsi
0x1800c509d  pop     rbx
0x1800c509e  pop     rbp
0x1800c509f  retn
```
