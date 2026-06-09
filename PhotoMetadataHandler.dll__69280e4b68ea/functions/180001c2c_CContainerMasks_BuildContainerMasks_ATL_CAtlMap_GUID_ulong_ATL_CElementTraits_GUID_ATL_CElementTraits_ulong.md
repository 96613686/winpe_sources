# CContainerMasks::BuildContainerMasks(ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>> *)

- ea: `0x180001c2c`
- end: `0x180001f2e`
- name: `?BuildContainerMasks@CContainerMasks@@CAJPEAV?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@@Z`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002eb0`

## callees

- `0x180001c2c`
- `0x18000d69c`
- `0x18000dfc4`
- `0x18000e138`
- `0x18000fd88`
- `0x18000fde8`
- `0x180016a40`
- `0x180017408`
- `0x18002773c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001e17`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001e46`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001e17`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001e46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001daf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001daf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180001d50`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180001d50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContainerMasks::BuildContainerMasks(__int64 a1)
{
  __int64 v1; // r14
  int v2; // edi
  __int64 v3; // r8
  CLSID *i; // rsi
  LSTATUS v5; // esi
  DWORD j; // r12d
  int *k; // r15
  unsigned int v8; // r13d
  DWORD Type; // [rsp+40h] [rbp-1C8h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-1C4h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-1C0h] BYREF
  HKEY hKey[4]; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v14; // [rsp+70h] [rbp-198h]
  __int128 Buf1; // [rsp+80h] [rbp-188h] BYREF
  unsigned int v16; // [rsp+90h] [rbp-178h]
  DWORD *v17; // [rsp+98h] [rbp-170h] BYREF
  CLSID pclsid; // [rsp+A0h] [rbp-168h] BYREF
  unsigned int Data1; // [rsp+B0h] [rbp-158h]
  CLSID Buf2; // [rsp+B8h] [rbp-150h] BYREF
  BYTE Data[2]; // [rsp+D0h] [rbp-138h] BYREF
  WCHAR ValueName[64]; // [rsp+150h] [rbp-B8h] BYREF

  v1 = a1;
  v14 = a1;
  v2 = 0;
  ATL::CAtlMap<_GUID,unsigned long,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned long>>::RemoveAll();
  try
  {
    LOBYTE(v3) = 1;
    ATL::CAtlMap<_GUID,unsigned long,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned long>>::InitHashTable(
      v1,
      16,
      v3);
    for ( i = (CLSID *)&xmmword_180099CC0; i != (CLSID *)&dword_180099D9C; i = (CLSID *)((char *)i + 20) )
    {
      pclsid = *i;
      Data1 = i[1].Data1;
      ATL::CAtlMap<_GUID,unsigned long,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned long>>::SetAt(
        v1,
        &pclsid,
        Data1);
    }
    memset(hKey, 0, 24);
    v5 = ATL::CRegKey::Open(
           (ATL::CRegKey *)hKey,
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PhotoPropertyHandler\\ContainerAssociations",
           0x20019u);
    if ( !v5 )
    {
      memset_0(ValueName, 0, sizeof(ValueName));
      for ( j = 0; v5 != 259 && j < 0xFFFF; ++j )
      {
        cchValueName = 64;
        v5 = RegEnumValueW(hKey[0], j, ValueName, &cchValueName, 0, 0, 0, 0);
        if ( !v5 )
        {
          memset_0(Data, 0, 0x80u);
          Type = 0;
          cbData = 128;
          v5 = RegQueryValueExW(hKey[0], ValueName, 0, &Type, Data, &cbData);
          if ( !v5 )
          {
            if ( Type - 1 > 1 )
              goto LABEL_11;
            if ( cbData )
            {
              if ( (cbData & 1) != 0 || *(_WORD *)&Data[2 * ((unsigned __int64)cbData >> 1) - 2] )
              {
LABEL_11:
                v5 = 13;
                continue;
              }
            }
            else
            {
              *(_WORD *)Data = 0;
            }
            pclsid = 0;
            v2 = CLSIDFromString(ValueName, &pclsid);
            v5 = 0;
            if ( v2 >= 0 )
            {
              Buf2 = 0;
              v2 = CLSIDFromString((LPCOLESTR)Data, &Buf2);
              if ( v2 >= 0 )
              {
                for ( k = (int *)&xmmword_180099CC0; k != &dword_180099D9C; k += 5 )
                {
                  Buf1 = *(_OWORD *)k;
                  v8 = k[4];
                  v16 = v8;
                  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
                  {
                    ATL::CAtlMap<_GUID,unsigned long,ATL::CElementTraits<_GUID>,ATL::CElementTraits<unsigned long>>::SetAt(
                      v1,
                      &pclsid,
                      v8);
                    break;
                  }
                }
              }
            }
          }
        }
      }
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  catch ( const ATL::CAtlException *v17 )
  {
    Type = *v17;
    v2 = Type;
    v1 = v14;
  }
  if ( v2 < 0 )
  {
    v2 &= -(*(_QWORD *)(v1 + 8) < 7u);
    Type = v2;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001c2c  mov     [rsp+arg_8], rbx
0x180001c31  mov     [rsp+arg_10], rsi
0x180001c36  push    rdi
0x180001c37  push    r12
0x180001c39  push    r13
0x180001c3b  push    r14
0x180001c3d  push    r15
0x180001c3f  sub     rsp, 1E0h
0x180001c46  mov     rax, cs:__security_cookie
0x180001c4d  xor     rax, rsp
0x180001c50  mov     [rsp+208h+var_38], rax
0x180001c58  mov     r14, rcx
0x180001c5b  mov     [rsp+208h+var_198], rcx
0x180001c60  xor     ebx, ebx
0x180001c62  mov     edi, ebx
0x180001c64  call    ?RemoveAll@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::RemoveAll(void)
0x180001c69  mov     r8b, 1
0x180001c6c  lea     edx, [rbx+10h]
0x180001c6f  mov     rcx, r14
0x180001c72  call    ?InitHashTable@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::InitHashTable(uint,bool)
0x180001c77  lea     rsi, xmmword_180099CC0
0x180001c7e  lea     r13, dword_180099D9C
0x180001c85  cmp     rsi, r13
0x180001c88  jz      short loc_180001CB7
0x180001c8a  movups  xmm0, xmmword ptr [rsi]
0x180001c8d  movups  xmmword ptr [rsp+208h+pclsid.Data1], xmm0
0x180001c95  mov     r8d, [rsi+10h]
0x180001c99  mov     [rsp+208h+var_158], r8d
0x180001ca1  lea     rdx, [rsp+208h+pclsid]
0x180001ca9  mov     rcx, r14
0x180001cac  call    ?SetAt@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@K@Z; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::SetAt(_GUID const &,ulong)
0x180001cb1  add     rsi, 14h
0x180001cb5  jmp     short loc_180001C85
0x180001cb7  mov     [rsp+208h+hKey], rbx
0x180001cbc  mov     [rsp+208h+var_1B0], rbx
0x180001cc1  mov     [rsp+208h+var_1A8], rbx
0x180001cc6  mov     r9d, 20019h; unsigned int
0x180001ccc  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180001cd3  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180001cda  lea     rcx, [rsp+208h+hKey]; this
0x180001cdf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180001ce4  mov     esi, eax
0x180001ce6  test    eax, eax
0x180001ce8  jnz     loc_180001ECF
0x180001cee  xor     edx, edx; Val
0x180001cf0  mov     r8d, 80h; Size
0x180001cf6  lea     rcx, [rsp+208h+ValueName]; void *
0x180001cfe  call    memset_0
0x180001d03  mov     r12d, ebx
0x180001d06  cmp     esi, 103h
0x180001d0c  jz      loc_180001ECF
0x180001d12  cmp     r12d, 0FFFFh
0x180001d19  jnb     loc_180001ECF
0x180001d1f  mov     [rsp+208h+cchValueName], 40h ; '@'
0x180001d27  mov     [rsp+208h+lpcbData], rbx; lpcbData
0x180001d2c  mov     [rsp+208h+lpData], rbx; lpData
0x180001d31  mov     [rsp+208h+lpType], rbx; lpType
0x180001d36  mov     [rsp+208h+lpReserved], rbx; lpReserved
0x180001d3b  lea     r9, [rsp+208h+cchValueName]; lpcchValueName
0x180001d40  lea     r8, [rsp+208h+ValueName]; lpValueName
0x180001d48  mov     edx, r12d; dwIndex
0x180001d4b  mov     rcx, [rsp+208h+hKey]; hKey
0x180001d50  call    cs:__imp_RegEnumValueW
0x180001d57  nop     dword ptr [rax+rax+00h]
0x180001d5c  mov     esi, eax
0x180001d5e  test    eax, eax
0x180001d60  jnz     short loc_180001DD1
0x180001d62  xor     edx, edx; Val
0x180001d64  mov     r8d, 80h; Size
0x180001d6a  lea     rcx, [rsp+208h+Data]; void *
0x180001d72  call    memset_0
0x180001d77  mov     [rsp+208h+Type], ebx
0x180001d7b  mov     [rsp+208h+cbData], 80h
0x180001d83  lea     rax, [rsp+208h+cbData]
0x180001d88  mov     [rsp+208h+lpType], rax; lpcbData
0x180001d8d  lea     rax, [rsp+208h+Data]
0x180001d95  mov     [rsp+208h+lpReserved], rax; lpData
0x180001d9a  lea     r9, [rsp+208h+Type]; lpType
0x180001d9f  xor     r8d, r8d; lpReserved
0x180001da2  lea     rdx, [rsp+208h+ValueName]; lpValueName
0x180001daa  mov     rcx, [rsp+208h+hKey]; hKey
0x180001daf  call    cs:__imp_RegQueryValueExW
0x180001db6  nop     dword ptr [rax+rax+00h]
0x180001dbb  mov     esi, eax
0x180001dbd  test    eax, eax
0x180001dbf  jnz     short loc_180001DD1
0x180001dc1  mov     eax, [rsp+208h+Type]
0x180001dc5  dec     eax
0x180001dc7  cmp     eax, 1
0x180001dca  jbe     short loc_180001DD9
0x180001dcc  mov     esi, 0Dh
0x180001dd1  inc     r12d
0x180001dd4  jmp     loc_180001D06
0x180001dd9  mov     eax, [rsp+208h+cbData]
0x180001ddd  test    eax, eax
0x180001ddf  jz      short loc_180001DF4
0x180001de1  test    al, 1
0x180001de3  jnz     short loc_180001DCC
0x180001de5  shr     rax, 1
0x180001de8  cmp     [rsp+rax*2+208h+var_13A], bx
0x180001df0  jz      short loc_180001DFC
0x180001df2  jmp     short loc_180001DCC
0x180001df4  mov     word ptr [rsp+208h+Data], bx
0x180001dfc  xorps   xmm0, xmm0
0x180001dff  movups  xmmword ptr [rsp+208h+pclsid.Data1], xmm0
0x180001e07  lea     rdx, [rsp+208h+pclsid]; pclsid
0x180001e0f  lea     rcx, [rsp+208h+ValueName]; lpsz
0x180001e17  call    cs:__imp_CLSIDFromString
0x180001e1e  nop     dword ptr [rax+rax+00h]
0x180001e23  mov     edi, eax
0x180001e25  mov     esi, ebx
0x180001e27  test    eax, eax
0x180001e29  js      short loc_180001DD1
0x180001e2b  xorps   xmm0, xmm0
0x180001e2e  movups  xmmword ptr [rsp+208h+Buf2.Data1], xmm0
0x180001e36  lea     rdx, [rsp+208h+Buf2]; pclsid
0x180001e3e  lea     rcx, [rsp+208h+Data]; lpsz
0x180001e46  call    cs:__imp_CLSIDFromString
0x180001e4d  nop     dword ptr [rax+rax+00h]
0x180001e52  mov     edi, eax
0x180001e54  test    eax, eax
0x180001e56  js      loc_180001DD1
0x180001e5c  lea     r15, xmmword_180099CC0
0x180001e63  cmp     r15, r13
0x180001e66  jz      loc_180001DD1
0x180001e6c  movups  xmm0, xmmword ptr [r15]
0x180001e70  movups  [rsp+208h+Buf1], xmm0
0x180001e78  mov     r13d, [r15+10h]
0x180001e7c  mov     [rsp+208h+var_178], r13d
0x180001e84  mov     r8d, 10h; Size
0x180001e8a  lea     rdx, [rsp+208h+Buf2]; Buf2
0x180001e92  lea     rcx, [rsp+208h+Buf1]; Buf1
0x180001e9a  call    memcmp_0
0x180001e9f  test    eax, eax
0x180001ea1  jnz     short loc_180001EC2
0x180001ea3  mov     r8d, r13d
0x180001ea6  lea     rdx, [rsp+208h+pclsid]
0x180001eae  mov     rcx, r14
0x180001eb1  call    ?SetAt@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@K@Z; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::SetAt(_GUID const &,ulong)
0x180001eb6  lea     r13, dword_180099D9C
0x180001ebd  jmp     loc_180001DD1
0x180001ec2  add     r15, 14h
0x180001ec6  lea     r13, dword_180099D9C
0x180001ecd  jmp     short loc_180001E63
0x180001ecf  lea     rcx, [rsp+208h+hKey]; this
0x180001ed4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180001ed9  nop
0x180001eda  jmp     short loc_180001EE5
0x180001edc  mov     edi, [rsp+208h+Type]
0x180001ee0  mov     r14, [rsp+208h+var_198]
0x180001ee5  test    edi, edi
0x180001ee7  jns     short loc_180001EFE
0x180001ee9  cmp     qword ptr [r14+8], 7
0x180001eee  sbb     eax, eax
0x180001ef0  and     eax, edi
0x180001ef2  mov     edi, eax
0x180001ef4  mov     [rsp+208h+Type], eax
0x180001ef8  jmp     short loc_180001EFE
0x180001efa  mov     edi, [rsp+208h+Type]
0x180001efe  mov     eax, edi
0x180001f00  mov     rcx, [rsp+208h+var_38]
0x180001f08  xor     rcx, rsp; StackCookie
0x180001f0b  call    __security_check_cookie
0x180001f10  lea     r11, [rsp+208h+var_28]
0x180001f18  mov     rbx, [r11+38h]
0x180001f1c  mov     rsi, [r11+40h]
0x180001f20  mov     rsp, r11
0x180001f23  pop     r15
0x180001f25  pop     r14
0x180001f27  pop     r13
0x180001f29  pop     r12
0x180001f2b  pop     rdi
0x180001f2c  retn
```
