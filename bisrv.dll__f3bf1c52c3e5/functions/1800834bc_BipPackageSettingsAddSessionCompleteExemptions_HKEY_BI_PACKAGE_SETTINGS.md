# BipPackageSettingsAddSessionCompleteExemptions(HKEY__ *,_BI_PACKAGE_SETTINGS *)

- ea: `0x1800834bc`
- end: `0x1800836e6`
- name: `?BipPackageSettingsAddSessionCompleteExemptions@@YAXPEAUHKEY__@@PEAU_BI_PACKAGE_SETTINGS@@@Z`
- size: `554`
- prototype: `void __fastcall(HKEY, struct _BI_PACKAGE_SETTINGS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800836ec`

## callees

- `0x18002a600`
- `0x180053100`
- `0x1800834bc`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `msvcrt!wcstoul` at `0x18008368e`
- `msvcrt!wcstoul` at `0x18008368e`
- `ntdll!RtlAllocateHeap` at `0x1800835a9`
- `ntdll!RtlAllocateHeap` at `0x1800835a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180083569`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180083569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800836bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800836bc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180083668`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180083668`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008351b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008351b`

## string_xrefs

- `0x1800834f2`: `SessionCompleteBufferExempt`

## pseudocode

```c
void __fastcall BipPackageSettingsAddSessionCompleteExemptions(HKEY a1, struct _BI_PACKAGE_SETTINGS *a2)
{
  LSTATUS v3; // eax
  __int64 v4; // r8
  bool v5; // cc
  _DWORD *Heap; // rax
  _DWORD *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // eax
  DWORD i; // ebx
  unsigned int v13; // eax
  DWORD cValues; // [rsp+60h] [rbp-9h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-5h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-1h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp+3h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+Fh] BYREF
  int v20; // [rsp+80h] [rbp+17h] BYREF
  __int64 *v21; // [rsp+88h] [rbp+1Fh] BYREF
  WCHAR ValueName[8]; // [rsp+90h] [rbp+27h] BYREF

  cValues = 0;
  cchValueName = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(a1, L"SessionCompleteBufferExempt", 0, 0x20019u, &hKey);
  v4 = (unsigned int)v3;
  if ( v3 == 2 )
    goto LABEL_23;
  v5 = v3 <= 0;
  if ( v3
    || (v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0), v4 = (unsigned int)v3, v5 = v3 <= 0, v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0xC0070000;
    if ( (int)v4 < 0 )
      goto LABEL_11;
  }
  else
  {
    if ( !cValues )
      goto LABEL_23;
    Heap = RtlAllocateHeap(BipHeap, 0, 4LL * cValues);
    v7 = Heap;
    if ( !Heap )
    {
      v4 = 3221225495LL;
LABEL_11:
      if ( (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v4) )
      {
        v20 = v9;
        v21 = (__int64 *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v8,
          (__int64)&unk_1800B4DE0,
          v9,
          v10,
          &v21,
          (__int64)&v20);
      }
      goto LABEL_23;
    }
    memset_0(Heap, 0, 4LL * cValues);
    v11 = cValues;
    for ( i = 0; i < cValues; ++i )
    {
      cchValueName = 7;
      cbData = 4;
      if ( !RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData)
        && Type == 4
        && cbData == 4
        && *(_DWORD *)Data == 1 )
      {
        v13 = wcstoul(ValueName, 0, 10);
        if ( v13 )
          v7[i] = v13;
      }
      v11 = cValues;
    }
    *((_DWORD *)a2 + 33) = v11;
    *((_QWORD *)a2 + 17) = v7;
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800834bc  mov     [rsp-8+arg_10], rbx
0x1800834c1  mov     [rsp-8+arg_18], rsi
0x1800834c6  push    rbp
0x1800834c7  push    rdi
0x1800834c8  push    r14
0x1800834ca  lea     rbp, [rsp-47h]
0x1800834cf  sub     rsp, 0B0h
0x1800834d6  mov     rax, cs:__security_cookie
0x1800834dd  xor     rax, rsp
0x1800834e0  mov     [rbp+57h+var_20], rax
0x1800834e4  xor     r14d, r14d
0x1800834e7  lea     rax, [rbp+57h+hKey]
0x1800834eb  mov     rsi, rdx
0x1800834ee  mov     [rbp+57h+cValues], r14d
0x1800834f2  lea     rdx, aSessioncomplet; "SessionCompleteBufferExempt"
0x1800834f9  mov     [rbp+57h+cchValueName], r14d
0x1800834fd  mov     r9d, 20019h; samDesired
0x180083503  mov     [rbp+57h+Type], r14d
0x180083507  xor     r8d, r8d; ulOptions
0x18008350a  mov     dword ptr [rbp+57h+Data], r14d
0x18008350e  mov     [rbp+57h+cbData], r14d
0x180083512  mov     [rbp+57h+hKey], r14
0x180083516  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18008351b  call    cs:__imp_RegOpenKeyExW
0x180083521  mov     r8d, eax
0x180083524  cmp     eax, 2
0x180083527  jz      loc_1800836B3
0x18008352d  test    eax, eax
0x18008352f  jnz     short loc_180083576
0x180083531  mov     rcx, [rbp+57h+hKey]; hKey
0x180083535  lea     rax, [rbp+57h+cValues]
0x180083539  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18008353e  xor     r9d, r9d; lpReserved
0x180083541  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180083546  xor     r8d, r8d; lpcchClass
0x180083549  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18008354e  xor     edx, edx; lpClass
0x180083550  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180083555  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18008355a  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18008355f  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180083564  mov     [rsp+0C0h+phkResult], r14; lpcSubKeys
0x180083569  call    cs:__imp_RegQueryInfoKeyW
0x18008356f  mov     r8d, eax
0x180083572  test    eax, eax
0x180083574  jz      short loc_18008358E
0x180083576  jle     short loc_180083583
0x180083578  movzx   r8d, ax
0x18008357c  or      r8d, 0C0070000h
0x180083583  test    r8d, r8d
0x180083586  jns     loc_1800836B3
0x18008358c  jmp     short loc_1800835BD
0x18008358e  mov     eax, [rbp+57h+cValues]
0x180083591  test    eax, eax
0x180083593  jz      loc_1800836B3
0x180083599  mov     rcx, cs:BipHeap; HeapHandle
0x1800835a0  mov     r8d, eax
0x1800835a3  shl     r8, 2; Size
0x1800835a7  xor     edx, edx; Flags
0x1800835a9  call    cs:__imp_RtlAllocateHeap
0x1800835af  mov     rdi, rax
0x1800835b2  test    rax, rax
0x1800835b5  jnz     short loc_180083610
0x1800835b7  mov     r8d, 0C0000017h
0x1800835bd  mov     eax, cs:dword_1800C3098
0x1800835c3  cmp     eax, 2
0x1800835c6  jbe     loc_1800836B3
0x1800835cc  mov     edx, 3
0x1800835d1  lea     rcx, dword_1800C3098
0x1800835d8  call    _tlgKeywordOn
0x1800835dd  test    al, al
0x1800835df  jz      loc_1800836B3
0x1800835e5  lea     rax, [rbp+57h+var_40]
0x1800835e9  mov     [rbp+57h+var_40], r8d
0x1800835ed  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x1800835f2  lea     rdx, unk_1800B4DE0
0x1800835f9  lea     rax, [rbp+57h+var_38]
0x1800835fd  mov     [rbp+57h+var_38], rsi
0x180083601  mov     [rsp+0C0h+phkResult], rax
0x180083606  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008360b  jmp     loc_1800836B3
0x180083610  mov     r8d, [rbp+57h+cValues]
0x180083614  xor     edx, edx; Val
0x180083616  shl     r8, 2; Size
0x18008361a  mov     rcx, rdi; void *
0x18008361d  call    memset_0
0x180083622  mov     eax, [rbp+57h+cValues]
0x180083625  mov     ebx, r14d
0x180083628  test    eax, eax
0x18008362a  jz      short loc_1800836A6
0x18008362c  mov     rcx, [rbp+57h+hKey]; hKey
0x180083630  lea     rax, [rbp+57h+cbData]
0x180083634  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x180083639  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18008363d  lea     rax, [rbp+57h+Data]
0x180083641  mov     [rbp+57h+cchValueName], 7
0x180083648  mov     [rsp+0C0h+lpcbMaxClassLen], rax; lpData
0x18008364d  lea     r8, [rbp+57h+ValueName]; lpValueName
0x180083651  lea     rax, [rbp+57h+Type]
0x180083655  mov     [rbp+57h+cbData], 4
0x18008365c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x180083661  mov     edx, ebx; dwIndex
0x180083663  mov     [rsp+0C0h+phkResult], r14; lpReserved
0x180083668  call    cs:__imp_RegEnumValueW
0x18008366e  test    eax, eax
0x180083670  jnz     short loc_18008369D
0x180083672  cmp     [rbp+57h+Type], 4
0x180083676  jnz     short loc_18008369D
0x180083678  cmp     [rbp+57h+cbData], 4
0x18008367c  jnz     short loc_18008369D
0x18008367e  cmp     dword ptr [rbp+57h+Data], 1
0x180083682  jnz     short loc_18008369D
0x180083684  xor     edx, edx; EndPtr
0x180083686  lea     r8d, [rax+0Ah]; Radix
0x18008368a  lea     rcx, [rbp+57h+ValueName]; String
0x18008368e  call    cs:__imp_wcstoul
0x180083694  test    eax, eax
0x180083696  jz      short loc_18008369D
0x180083698  mov     ecx, ebx
0x18008369a  mov     [rdi+rcx*4], eax
0x18008369d  mov     eax, [rbp+57h+cValues]
0x1800836a0  inc     ebx
0x1800836a2  cmp     ebx, eax
0x1800836a4  jb      short loc_18008362C
0x1800836a6  mov     [rsi+84h], eax
0x1800836ac  mov     [rsi+88h], rdi
0x1800836b3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800836b7  test    rcx, rcx
0x1800836ba  jz      short loc_1800836C2
0x1800836bc  call    cs:__imp_RegCloseKey
0x1800836c2  mov     rcx, [rbp+57h+var_20]
0x1800836c6  xor     rcx, rsp; StackCookie
0x1800836c9  call    __security_check_cookie
0x1800836ce  lea     r11, [rsp+0C0h+var_10]
0x1800836d6  mov     rbx, [r11+30h]
0x1800836da  mov     rsi, [r11+38h]
0x1800836de  mov     rsp, r11
0x1800836e1  pop     r14
0x1800836e3  pop     rdi
0x1800836e4  pop     rbp
0x1800836e5  retn
```
