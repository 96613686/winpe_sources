# WindowsPerformanceRecorder::CEventProvidersCollection::AddPerfTrackProviders(void)

- ea: `0x180020ba8`
- end: `0x180020de7`
- name: `?AddPerfTrackProviders@CEventProvidersCollection@WindowsPerformanceRecorder@@AEAAJXZ`
- size: `575`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CEventProvidersCollection *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180020b08`

## callees

- `0x180008270`
- `0x180008330`
- `0x180013424`
- `0x180020ba8`
- `0x180026c00`
- `0x1800332c8`
- `0x18004ece0`
- `0x18004f964`
- `0x180067984`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180020ccb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180020ccb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020c14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020c14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c42`
- `ntdll!RtlInitUnicodeString` at `0x180020cf4`
- `ntdll!RtlInitUnicodeString` at `0x180020cf4`
- `ntdll!RtlGUIDFromString` at `0x180020d07`
- `ntdll!RtlGUIDFromString` at `0x180020d07`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CEventProvidersCollection::AddPerfTrackProviders(
        WindowsPerformanceRecorder::CEventProvidersCollection *this)
{
  HKEY v2; // rbx
  LSTATUS v3; // eax
  LSTATUS v4; // edi
  LSTATUS v5; // eax
  __int64 result; // rax
  unsigned int v7; // esi
  wchar_t *v8; // rax
  HKEY v9; // r15
  HKEY i; // rbx
  unsigned int v11; // ebx
  struct _FILETIME *phkResult; // [rsp+20h] [rbp-1C8h]
  HKEY v13; // [rsp+30h] [rbp-1B8h] BYREF
  _QWORD v14[3]; // [rsp+38h] [rbp-1B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-198h] BYREF
  __int64 v16; // [rsp+60h] [rbp-188h]
  ATL::CAtlException *v17; // [rsp+68h] [rbp-180h] BYREF
  char v18[16]; // [rsp+70h] [rbp-178h] BYREF
  GUID Guid; // [rsp+80h] [rbp-168h] BYREF
  _BYTE v20[16]; // [rsp+90h] [rbp-158h] BYREF
  char v21[32]; // [rsp+A0h] [rbp-148h] BYREF
  wchar_t Str[128]; // [rsp+C0h] [rbp-128h] BYREF

  v16 = -2;
  v2 = 0;
  memset(v14, 0, sizeof(v14));
  v13 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\WDI\\Scenarios\\{fd5aa730-b53f-4b39-84e5-cb4303621d74}\\Instrumentation",
         0,
         0x20019u,
         &v13);
  v4 = v3;
  if ( !v3 )
  {
    v5 = ATL::CRegKey::Close((ATL::CRegKey *)v14);
    v4 = v5;
    v2 = v13;
    v14[0] = v13;
  }
  try
  {
    if ( v4 )
    {
      if ( v2 )
        RegCloseKey(v2);
    }
    else
    {
      v7 = 0;
      while ( v4 != 259 )
      {
        Guid = 0;
        memset_0(Str, 0, sizeof(Str));
        LODWORD(v13) = 128;
        v4 = ATL::CRegKey::EnumKey((ATL::CRegKey *)v14, v7, Str, (unsigned int *)&v13, phkResult);
        if ( !v4 && (unsigned int)v13 < 0x80 )
        {
          Str[127] = 0;
          v8 = wcschr(Str, 0x3Bu);
          if ( v8 )
          {
            *v8 = 0;
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, Str);
            if ( RtlGUIDFromString(&DestinationString, &Guid) >= 0 )
            {
              WindowsPerformanceRecorder::CEventProviderInfo::CEventProviderInfo(
                (WindowsPerformanceRecorder::CEventProviderInfo *)v20,
                &Guid,
                &LocaleName);
              v9 = (HKEY)*((_QWORD *)this + 1);
              for ( i = *(HKEY *)this;
                    i != v9 && !(unsigned __int8)WindowsPerformanceRecorder::CEventProviderInfo::operator==(i, v20);
                    i += 10 )
              {
                ;
              }
              if ( i != *((HKEY *)this + 1) )
              {
                v13 = i;
                std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CEventProviderInfo *,std::less<WindowsPerformanceRecorder::CEventProviderInfo *>,std::allocator<WindowsPerformanceRecorder::CEventProviderInfo *>,0>>::insert<0,0>(
                  (char *)this + 24,
                  v18,
                  &v13);
              }
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v21);
            }
          }
        }
        ++v7;
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v14);
    }
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    ATL::CRegKey::Close((ATL::CRegKey *)v14);
    return 2147942414LL;
  }
  catch ( std::length_error )
  {
    v11 = -2147024882;
    goto LABEL_22;
  }
  catch ( ATL::CAtlException *v17 )
  {
    LODWORD(v13) = *(_DWORD *)v17;
    v11 = (unsigned int)v13;
LABEL_22:
    ATL::CRegKey::Close((ATL::CRegKey *)v14);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180020ba8  mov     rax, rsp
0x180020bab  push    rdi
0x180020bac  push    r14
0x180020bae  push    r15
0x180020bb0  sub     rsp, 1D0h
0x180020bb7  mov     [rsp+1E8h+var_188], 0FFFFFFFFFFFFFFFEh
0x180020bc0  mov     [rax+10h], rbx
0x180020bc4  mov     [rax+18h], rsi
0x180020bc8  mov     rax, cs:__security_cookie
0x180020bcf  xor     rax, rsp
0x180020bd2  mov     [rsp+1E8h+var_28], rax
0x180020bda  mov     r14, rcx
0x180020bdd  xor     ebx, ebx
0x180020bdf  mov     [rsp+1E8h+var_1B0], rbx
0x180020be4  mov     [rsp+1E8h+var_1A8], rbx
0x180020be9  mov     [rsp+1E8h+var_1A0], rbx
0x180020bee  mov     [rsp+1E8h+var_1B8], rbx
0x180020bf3  lea     rax, [rsp+1E8h+var_1B8]
0x180020bf8  mov     [rsp+1E8h+phkResult], rax; struct _FILETIME *
0x180020bfd  mov     r9d, 20019h; samDesired
0x180020c03  xor     r8d, r8d; ulOptions
0x180020c06  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\WDI"...
0x180020c0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020c14  call    cs:__imp_RegOpenKeyExW
0x180020c1a  mov     edi, eax
0x180020c1c  test    eax, eax
0x180020c1e  jnz     short loc_180020C36
0x180020c20  lea     rcx, [rsp+1E8h+var_1B0]; this
0x180020c25  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020c2a  mov     edi, eax
0x180020c2c  mov     rbx, [rsp+1E8h+var_1B8]
0x180020c31  mov     [rsp+1E8h+var_1B0], rbx
0x180020c36  test    edi, edi
0x180020c38  jz      short loc_180020C4F
0x180020c3a  test    rbx, rbx
0x180020c3d  jz      short loc_180020C48
0x180020c3f  mov     rcx, rbx; hKey
0x180020c42  call    cs:__imp_RegCloseKey
0x180020c48  xor     eax, eax
0x180020c4a  jmp     loc_180020DBE
0x180020c4f  xor     esi, esi
0x180020c51  cmp     edi, 103h
0x180020c57  jz      loc_180020D87
0x180020c5d  xorps   xmm0, xmm0
0x180020c60  movups  xmmword ptr [rsp+1E8h+Guid.Data1], xmm0
0x180020c68  xor     edx, edx; Val
0x180020c6a  mov     r8d, 100h; Size
0x180020c70  lea     rcx, [rsp+1E8h+Str]; void *
0x180020c78  call    memset_0
0x180020c7d  mov     dword ptr [rsp+1E8h+var_1B8], 80h
0x180020c85  lea     r9, [rsp+1E8h+var_1B8]; unsigned int *
0x180020c8a  lea     r8, [rsp+1E8h+Str]; unsigned __int16 *
0x180020c92  mov     edx, esi; unsigned int
0x180020c94  lea     rcx, [rsp+1E8h+var_1B0]; this
0x180020c99  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x180020c9e  mov     edi, eax
0x180020ca0  test    eax, eax
0x180020ca2  jnz     loc_180020D80
0x180020ca8  cmp     dword ptr [rsp+1E8h+var_1B8], 80h
0x180020cb0  jnb     loc_180020D80
0x180020cb6  xor     ecx, ecx
0x180020cb8  mov     [rsp+1E8h+var_2A], cx
0x180020cc0  lea     edx, [rax+3Bh]; Ch
0x180020cc3  lea     rcx, [rsp+1E8h+Str]; Str
0x180020ccb  call    cs:__imp_wcschr
0x180020cd1  test    rax, rax
0x180020cd4  jz      loc_180020D80
0x180020cda  xor     ecx, ecx
0x180020cdc  mov     [rax], cx
0x180020cdf  xorps   xmm0, xmm0
0x180020ce2  movups  xmmword ptr [rsp+1E8h+DestinationString.Length], xmm0
0x180020ce7  lea     rdx, [rsp+1E8h+Str]; SourceString
0x180020cef  lea     rcx, [rsp+1E8h+DestinationString]; DestinationString
0x180020cf4  call    cs:__imp_RtlInitUnicodeString
0x180020cfa  lea     rdx, [rsp+1E8h+Guid]; Guid
0x180020d02  lea     rcx, [rsp+1E8h+DestinationString]; GuidString
0x180020d07  call    cs:__imp_RtlGUIDFromString
0x180020d0d  test    eax, eax
0x180020d0f  js      short loc_180020D80
0x180020d11  lea     r8, LocaleName; unsigned __int16 *
0x180020d18  lea     rdx, [rsp+1E8h+Guid]; struct _GUID *
0x180020d20  lea     rcx, [rsp+1E8h+var_158]; this
0x180020d28  call    ??0CEventProviderInfo@WindowsPerformanceRecorder@@QEAA@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CEventProviderInfo::CEventProviderInfo(_GUID const &,ushort const *)
0x180020d2d  nop
0x180020d2e  mov     r15, [r14+8]
0x180020d32  mov     rbx, [r14]
0x180020d35  jmp     short loc_180020D4F
0x180020d37  lea     rdx, [rsp+1E8h+var_158]
0x180020d3f  mov     rcx, rbx
0x180020d42  call    ??8CEventProviderInfo@WindowsPerformanceRecorder@@QEBA_NAEBU01@@Z; WindowsPerformanceRecorder::CEventProviderInfo::operator==(WindowsPerformanceRecorder::CEventProviderInfo const &)
0x180020d47  test    al, al
0x180020d49  jnz     short loc_180020D54
0x180020d4b  add     rbx, 28h ; '('
0x180020d4f  cmp     rbx, r15
0x180020d52  jnz     short loc_180020D37
0x180020d54  cmp     rbx, [r14+8]
0x180020d58  jz      short loc_180020D73
0x180020d5a  mov     [rsp+1E8h+var_1B8], rbx
0x180020d5f  lea     rcx, [r14+18h]
0x180020d63  lea     r8, [rsp+1E8h+var_1B8]
0x180020d68  lea     rdx, [rsp+1E8h+var_178]
0x180020d6d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEAUCEventProviderInfo@WindowsPerformanceRecorder@@U?$less@PEAUCEventProviderInfo@WindowsPerformanceRecorder@@@std@@V?$allocator@PEAUCEventProviderInfo@WindowsPerformanceRecorder@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAUCEventProviderInfo@WindowsPerformanceRecorder@@@std@@@std@@@std@@_N@1@$$QEAPEAUCEventProviderInfo@WindowsPerformanceRecorder@@@Z; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CEventProviderInfo *,std::less<WindowsPerformanceRecorder::CEventProviderInfo *>,std::allocator<WindowsPerformanceRecorder::CEventProviderInfo *>,0>>::insert<0,0>(WindowsPerformanceRecorder::CEventProviderInfo * &&)
0x180020d72  nop
0x180020d73  lea     rcx, [rsp+1E8h+var_148]; this
0x180020d7b  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180020d80  inc     esi
0x180020d82  jmp     loc_180020C51
0x180020d87  lea     rcx, [rsp+1E8h+var_1B0]; this
0x180020d8c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020d91  jmp     loc_180020C48
0x180020d96  mov     ebx, dword ptr [rsp+1E8h+var_1B8]
0x180020d9a  jmp     short loc_180020DA1
0x180020d9c  mov     ebx, 8007000Eh
0x180020da1  lea     rcx, [rsp+1E8h+var_1B0]; this
0x180020da6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020dab  mov     eax, ebx
0x180020dad  jmp     short loc_180020DBE
0x180020daf  lea     rcx, [rsp+1E8h+var_1B0]; this
0x180020db4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020db9  mov     eax, 8007000Eh
0x180020dbe  mov     rcx, [rsp+1E8h+var_28]
0x180020dc6  xor     rcx, rsp; StackCookie
0x180020dc9  call    __security_check_cookie
0x180020dce  lea     r11, [rsp+1E8h+var_18]
0x180020dd6  mov     rbx, [r11+28h]
0x180020dda  mov     rsi, [r11+30h]
0x180020dde  mov     rsp, r11
0x180020de1  pop     r15
0x180020de3  pop     r14
0x180020de5  pop     rdi
0x180020de6  retn
```
