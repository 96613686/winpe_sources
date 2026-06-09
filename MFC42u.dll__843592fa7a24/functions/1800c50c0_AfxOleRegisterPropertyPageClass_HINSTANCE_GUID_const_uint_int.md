# AfxOleRegisterPropertyPageClass(HINSTANCE__ *,_GUID const &,uint,int)

- ea: `0x1800c50c0`
- end: `0x1800c52df`
- name: `?AfxOleRegisterPropertyPageClass@@YAHPEAUHINSTANCE__@@AEBU_GUID@@IH@Z`
- size: `543`
- prototype: `__int64 __fastcall(HINSTANCE, GUID *rguid, UINT uID, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c50b0`
- `0x1800cade0`
- `0x1800cd180`
- `0x1800ce110`

## callees

- `0x18000b3a0`
- `0x180014640`
- `0x180019290`
- `0x180038490`
- `0x18009ba50`
- `0x1800c50c0`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800c517a`
- `msvcrt!swprintf_s` at `0x1800c517a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c51b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c51b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c5278`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c5278`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c528b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c529b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c528b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c529b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5232`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5232`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c5105`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c5105`

## string_xrefs

- `0x1800c516a`: `CLSID\%s`
- `0x1800c526c`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AfxOleRegisterPropertyPageClass(HINSTANCE a1, GUID *rguid, UINT uID, char a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v11; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v12; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v13[3]; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF

  if ( StringFromGUID2(rguid, sz, 39) != 39 )
    return 0;
  v8 = 0;
  v12 = (HKEY)_afxPchNil;
  AfxGetModuleShortFileName(a1, (struct CString *)&v12);
  v11 = (HKEY)_afxPchNil;
  if ( !(unsigned int)CString::LoadStringW((CString *)&v11, uID) )
    CString::operator=(&v11, sz);
  hKey = 0;
  swprintf_s(Buffer, 0x104u, L"CLSID\\%s", sz);
  if ( !RegCreateKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
  {
    v13[0] = v11;
    v13[1] = v12;
    v8 = AfxOleRegisterHelper(
           (const unsigned __int16 *const *)&_afxPropPageClass,
           (const unsigned __int16 *const *)v13,
           2,
           1,
           hKey);
    if ( v8 )
    {
      if ( (a4 & 2) != 0 )
      {
        v13[0] = 0;
        if ( RegOpenKeyExW(hKey, L"InprocServer32", 0, 0x2000000u, v13) )
        {
          v8 = 0;
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&aApartment_0[2 * v9] );
          v8 = RegSetValueExW(v13[0], L"ThreadingModel", 0, 1u, aApartment_0, 2 * v9 + 2) == 0;
          RegCloseKey(v13[0]);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  CString::~CString((CString *)&v11);
  CString::~CString((CString *)&v12);
  return v8;
}

```

## disassembly

```asm
0x1800c50c0  mov     [rsp-8+arg_18], rbx
0x1800c50c5  push    rbp
0x1800c50c6  push    rsi
0x1800c50c7  push    rdi
0x1800c50c8  push    r14
0x1800c50ca  push    r15
0x1800c50cc  lea     rbp, [rsp-1F0h]
0x1800c50d4  sub     rsp, 2F0h
0x1800c50db  mov     rax, cs:__security_cookie
0x1800c50e2  xor     rax, rsp
0x1800c50e5  mov     [rbp+210h+var_30], rax
0x1800c50ec  mov     edi, r9d
0x1800c50ef  mov     r14d, r8d
0x1800c50f2  mov     rax, rdx
0x1800c50f5  mov     rsi, rcx
0x1800c50f8  mov     r8d, 27h ; '''; cchMax
0x1800c50fe  lea     rdx, [rbp+210h+sz]; lpsz
0x1800c5102  mov     rcx, rax; rguid
0x1800c5105  call    cs:__imp_StringFromGUID2
0x1800c510b  cmp     eax, 27h ; '''
0x1800c510e  jz      short loc_1800C5117
0x1800c5110  xor     eax, eax
0x1800c5112  jmp     loc_1800C52B9
0x1800c5117  xor     r15d, r15d
0x1800c511a  mov     ebx, r15d
0x1800c511d  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800c5124  mov     [rsp+310h+var_2B0], rax
0x1800c5129  lea     rdx, [rsp+310h+var_2B0]; struct CString *
0x1800c512e  mov     rcx, rsi; HINSTANCE
0x1800c5131  call    ?AfxGetModuleShortFileName@@YAXPEAUHINSTANCE__@@AEAVCString@@@Z; AfxGetModuleShortFileName(HINSTANCE__ *,CString &)
0x1800c5136  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800c513d  mov     [rsp+310h+var_2B8], rax
0x1800c5142  mov     edx, r14d; uID
0x1800c5145  lea     rcx, [rsp+310h+var_2B8]; this
0x1800c514a  call    ?LoadStringW@CString@@QEAAHI@Z; CString::LoadStringW(uint)
0x1800c514f  test    eax, eax
0x1800c5151  jnz     short loc_1800C5161
0x1800c5153  lea     rdx, [rbp+210h+sz]
0x1800c5157  lea     rcx, [rsp+310h+var_2B8]
0x1800c515c  call    ??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x1800c5161  mov     [rsp+310h+hKey], r15
0x1800c5166  lea     r9, [rbp+210h+sz]
0x1800c516a  lea     r8, aClsidS; "CLSID\\%s"
0x1800c5171  mov     edx, 104h; BufferCount
0x1800c5176  lea     rcx, [rbp+210h+Buffer]; Buffer
0x1800c517a  call    cs:__imp_swprintf_s
0x1800c5180  mov     [rsp+310h+lpdwDisposition], r15; lpdwDisposition
0x1800c5185  lea     rax, [rsp+310h+hKey]
0x1800c518a  mov     [rsp+310h+phkResult], rax; phkResult
0x1800c518f  mov     [rsp+310h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800c5194  mov     esi, 2000000h
0x1800c5199  mov     [rsp+310h+samDesired], esi; samDesired
0x1800c519d  mov     [rsp+310h+dwOptions], r15d; dwOptions
0x1800c51a2  xor     r9d, r9d; lpClass
0x1800c51a5  xor     r8d, r8d; Reserved
0x1800c51a8  lea     rdx, [rbp+210h+Buffer]; lpSubKey
0x1800c51ac  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800c51b3  call    cs:__imp_RegCreateKeyExW
0x1800c51b9  test    eax, eax
0x1800c51bb  jnz     loc_1800C5291
0x1800c51c1  mov     rax, [rsp+310h+var_2B8]
0x1800c51c6  mov     [rsp+310h+var_2A8], rax
0x1800c51cb  mov     rax, [rsp+310h+var_2B0]
0x1800c51d0  mov     [rsp+310h+var_2A0], rax
0x1800c51d5  mov     rax, [rsp+310h+hKey]
0x1800c51da  mov     qword ptr [rsp+310h+dwOptions], rax; HKEY
0x1800c51df  mov     r14d, 1
0x1800c51e5  mov     r9d, r14d; int
0x1800c51e8  lea     r8d, [r14+1]; int
0x1800c51ec  lea     rdx, [rsp+310h+var_2A8]; unsigned __int16 **
0x1800c51f1  lea     rcx, ?_afxPropPageClass@@3QBQEBGB; unsigned __int16 **
0x1800c51f8  call    ?AfxOleRegisterHelper@@YAHPEBQEBG0HHPEAUHKEY__@@@Z; AfxOleRegisterHelper(ushort const * const *,ushort const * const *,int,int,HKEY__ *)
0x1800c51fd  mov     ebx, eax
0x1800c51ff  test    eax, eax
0x1800c5201  jz      loc_1800C5291
0x1800c5207  test    dil, 2
0x1800c520b  jz      loc_1800C5291
0x1800c5211  mov     [rsp+310h+var_2A8], r15
0x1800c5216  lea     rax, [rsp+310h+var_2A8]
0x1800c521b  mov     qword ptr [rsp+310h+dwOptions], rax; phkResult
0x1800c5220  mov     r9d, esi; samDesired
0x1800c5223  xor     r8d, r8d; ulOptions
0x1800c5226  lea     rdx, aInprocserver32; "InprocServer32"
0x1800c522d  mov     rcx, [rsp+310h+hKey]; hKey
0x1800c5232  call    cs:__imp_RegOpenKeyExW
0x1800c5238  test    eax, eax
0x1800c523a  jz      short loc_1800C5241
0x1800c523c  mov     ebx, r15d
0x1800c523f  jmp     short loc_1800C5291
0x1800c5241  lea     rcx, aApartment_0; "Apartment"
0x1800c5248  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c524c  inc     rax
0x1800c524f  cmp     [rcx+rax*2], r15w
0x1800c5254  jnz     short loc_1800C524C
0x1800c5256  lea     eax, ds:2[rax*2]
0x1800c525d  mov     [rsp+310h+samDesired], eax; cbData
0x1800c5261  mov     qword ptr [rsp+310h+dwOptions], rcx; lpData
0x1800c5266  mov     r9d, r14d; dwType
0x1800c5269  xor     r8d, r8d; Reserved
0x1800c526c  lea     rdx, ValueName; "ThreadingModel"
0x1800c5273  mov     rcx, [rsp+310h+var_2A8]; hKey
0x1800c5278  call    cs:__imp_RegSetValueExW
0x1800c527e  mov     ebx, r15d
0x1800c5281  test    eax, eax
0x1800c5283  setz    bl
0x1800c5286  mov     rcx, [rsp+310h+var_2A8]; hKey
0x1800c528b  call    cs:__imp_RegCloseKey
0x1800c5291  mov     rcx, [rsp+310h+hKey]; hKey
0x1800c5296  test    rcx, rcx
0x1800c5299  jz      short loc_1800C52A2
0x1800c529b  call    cs:__imp_RegCloseKey
0x1800c52a1  nop
0x1800c52a2  lea     rcx, [rsp+310h+var_2B8]; this
0x1800c52a7  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800c52ac  nop
0x1800c52ad  lea     rcx, [rsp+310h+var_2B0]; this
0x1800c52b2  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800c52b7  mov     eax, ebx
0x1800c52b9  mov     rcx, [rbp+210h+var_30]
0x1800c52c0  xor     rcx, rsp; StackCookie
0x1800c52c3  call    __security_check_cookie
0x1800c52c8  mov     rbx, [rsp+310h+arg_18]
0x1800c52d0  add     rsp, 2F0h
0x1800c52d7  pop     r15
0x1800c52d9  pop     r14
0x1800c52db  pop     rdi
0x1800c52dc  pop     rsi
0x1800c52dd  pop     rbp
0x1800c52de  retn
```
