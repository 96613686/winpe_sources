# CContainerMasks::BuildContainerMasks(ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>> *)

- ea: `0x180001b9c`
- end: `0x180001e81`
- name: `?BuildContainerMasks@CContainerMasks@@CAJPEAV?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002d50`

## callees

- `0x180001b9c`
- `0x18000cd5c`
- `0x18000d6cc`
- `0x18000d82c`
- `0x18000f620`
- `0x18000f678`
- `0x180016020`
- `0x1800169b8`
- `0x18002648c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001d7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001da4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001d7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001da4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d19`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180001cc0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180001cc0`

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
  __int128 *k; // r15
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
    for ( i = (CLSID *)&xmmword_180098BC0; i != (CLSID *)&unk_180098C9C; i = (CLSID *)((char *)i + 20) )
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
                for ( k = &xmmword_180098BC0; k != (__int128 *)&unk_180098C9C; k = (__int128 *)((char *)k + 20) )
                {
                  Buf1 = *k;
                  v8 = *((_DWORD *)k + 4);
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
0x180001b9c  mov     [rsp+arg_8], rbx
0x180001ba1  mov     [rsp+arg_10], rsi
0x180001ba6  push    rdi
0x180001ba7  push    r12
0x180001ba9  push    r13
0x180001bab  push    r14
0x180001bad  push    r15
0x180001baf  sub     rsp, 1E0h
0x180001bb6  mov     rax, cs:__security_cookie
0x180001bbd  xor     rax, rsp
0x180001bc0  mov     [rsp+208h+var_38], rax
0x180001bc8  mov     r14, rcx
0x180001bcb  mov     [rsp+208h+var_198], rcx
0x180001bd0  xor     ebx, ebx
0x180001bd2  mov     edi, ebx
0x180001bd4  call    ?RemoveAll@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::RemoveAll(void)
0x180001bd9  mov     r8b, 1
0x180001bdc  lea     edx, [rbx+10h]
0x180001bdf  mov     rcx, r14
0x180001be2  call    ?InitHashTable@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::InitHashTable(uint,bool)
0x180001be7  lea     rsi, xmmword_180098BC0
0x180001bee  lea     r13, unk_180098C9C
0x180001bf5  cmp     rsi, r13
0x180001bf8  jz      short loc_180001C27
0x180001bfa  movups  xmm0, xmmword ptr [rsi]
0x180001bfd  movups  xmmword ptr [rsp+208h+pclsid.Data1], xmm0
0x180001c05  mov     r8d, [rsi+10h]
0x180001c09  mov     [rsp+208h+var_158], r8d
0x180001c11  lea     rdx, [rsp+208h+pclsid]
0x180001c19  mov     rcx, r14
0x180001c1c  call    ?SetAt@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@K@Z; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::SetAt(_GUID const &,ulong)
0x180001c21  add     rsi, 14h
0x180001c25  jmp     short loc_180001BF5
0x180001c27  mov     [rsp+208h+hKey], rbx
0x180001c2c  mov     [rsp+208h+var_1B0], rbx
0x180001c31  mov     [rsp+208h+var_1A8], rbx
0x180001c36  mov     r9d, 20019h; unsigned int
0x180001c3c  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180001c43  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180001c4a  lea     rcx, [rsp+208h+hKey]; this
0x180001c4f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180001c54  mov     esi, eax
0x180001c56  test    eax, eax
0x180001c58  jnz     loc_180001E23
0x180001c5e  xor     edx, edx; Val
0x180001c60  mov     r8d, 80h; Size
0x180001c66  lea     rcx, [rsp+208h+ValueName]; void *
0x180001c6e  call    memset_0
0x180001c73  mov     r12d, ebx
0x180001c76  cmp     esi, 103h
0x180001c7c  jz      loc_180001E23
0x180001c82  cmp     r12d, 0FFFFh
0x180001c89  jnb     loc_180001E23
0x180001c8f  mov     [rsp+208h+cchValueName], 40h ; '@'
0x180001c97  mov     [rsp+208h+lpcbData], rbx; lpcbData
0x180001c9c  mov     [rsp+208h+lpData], rbx; lpData
0x180001ca1  mov     [rsp+208h+lpType], rbx; lpType
0x180001ca6  mov     [rsp+208h+lpReserved], rbx; lpReserved
0x180001cab  lea     r9, [rsp+208h+cchValueName]; lpcchValueName
0x180001cb0  lea     r8, [rsp+208h+ValueName]; lpValueName
0x180001cb8  mov     edx, r12d; dwIndex
0x180001cbb  mov     rcx, [rsp+208h+hKey]; hKey
0x180001cc0  call    cs:__imp_RegEnumValueW
0x180001cc6  mov     esi, eax
0x180001cc8  test    eax, eax
0x180001cca  jnz     short loc_180001D35
0x180001ccc  xor     edx, edx; Val
0x180001cce  mov     r8d, 80h; Size
0x180001cd4  lea     rcx, [rsp+208h+Data]; void *
0x180001cdc  call    memset_0
0x180001ce1  mov     [rsp+208h+Type], ebx
0x180001ce5  mov     [rsp+208h+cbData], 80h
0x180001ced  lea     rax, [rsp+208h+cbData]
0x180001cf2  mov     [rsp+208h+lpType], rax; lpcbData
0x180001cf7  lea     rax, [rsp+208h+Data]
0x180001cff  mov     [rsp+208h+lpReserved], rax; lpData
0x180001d04  lea     r9, [rsp+208h+Type]; lpType
0x180001d09  xor     r8d, r8d; lpReserved
0x180001d0c  lea     rdx, [rsp+208h+ValueName]; lpValueName
0x180001d14  mov     rcx, [rsp+208h+hKey]; hKey
0x180001d19  call    cs:__imp_RegQueryValueExW
0x180001d1f  mov     esi, eax
0x180001d21  test    eax, eax
0x180001d23  jnz     short loc_180001D35
0x180001d25  mov     eax, [rsp+208h+Type]
0x180001d29  dec     eax
0x180001d2b  cmp     eax, 1
0x180001d2e  jbe     short loc_180001D3D
0x180001d30  mov     esi, 0Dh
0x180001d35  inc     r12d
0x180001d38  jmp     loc_180001C76
0x180001d3d  mov     eax, [rsp+208h+cbData]
0x180001d41  test    eax, eax
0x180001d43  jz      short loc_180001D58
0x180001d45  test    al, 1
0x180001d47  jnz     short loc_180001D30
0x180001d49  shr     rax, 1
0x180001d4c  cmp     [rsp+rax*2+208h+var_13A], bx
0x180001d54  jz      short loc_180001D60
0x180001d56  jmp     short loc_180001D30
0x180001d58  mov     word ptr [rsp+208h+Data], bx
0x180001d60  xorps   xmm0, xmm0
0x180001d63  movups  xmmword ptr [rsp+208h+pclsid.Data1], xmm0
0x180001d6b  lea     rdx, [rsp+208h+pclsid]; pclsid
0x180001d73  lea     rcx, [rsp+208h+ValueName]; lpsz
0x180001d7b  call    cs:__imp_CLSIDFromString
0x180001d81  mov     edi, eax
0x180001d83  mov     esi, ebx
0x180001d85  test    eax, eax
0x180001d87  js      short loc_180001D35
0x180001d89  xorps   xmm0, xmm0
0x180001d8c  movups  xmmword ptr [rsp+208h+Buf2.Data1], xmm0
0x180001d94  lea     rdx, [rsp+208h+Buf2]; pclsid
0x180001d9c  lea     rcx, [rsp+208h+Data]; lpsz
0x180001da4  call    cs:__imp_CLSIDFromString
0x180001daa  mov     edi, eax
0x180001dac  test    eax, eax
0x180001dae  js      short loc_180001D35
0x180001db0  lea     r15, xmmword_180098BC0
0x180001db7  cmp     r15, r13
0x180001dba  jz      loc_180001D35
0x180001dc0  movups  xmm0, xmmword ptr [r15]
0x180001dc4  movups  [rsp+208h+Buf1], xmm0
0x180001dcc  mov     r13d, [r15+10h]
0x180001dd0  mov     [rsp+208h+var_178], r13d
0x180001dd8  mov     r8d, 10h; Size
0x180001dde  lea     rdx, [rsp+208h+Buf2]; Buf2
0x180001de6  lea     rcx, [rsp+208h+Buf1]; Buf1
0x180001dee  call    memcmp_0
0x180001df3  test    eax, eax
0x180001df5  jnz     short loc_180001E16
0x180001df7  mov     r8d, r13d
0x180001dfa  lea     rdx, [rsp+208h+pclsid]
0x180001e02  mov     rcx, r14
0x180001e05  call    ?SetAt@?$CAtlMap@U_GUID@@KV?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@K@3@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@K@Z; ATL::CAtlMap<_GUID,ulong,ATL::CElementTraits<_GUID>,ATL::CElementTraits<ulong>>::SetAt(_GUID const &,ulong)
0x180001e0a  lea     r13, unk_180098C9C
0x180001e11  jmp     loc_180001D35
0x180001e16  add     r15, 14h
0x180001e1a  lea     r13, unk_180098C9C
0x180001e21  jmp     short loc_180001DB7
0x180001e23  lea     rcx, [rsp+208h+hKey]; this
0x180001e28  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180001e2d  nop
0x180001e2e  jmp     short loc_180001E39
0x180001e30  mov     edi, [rsp+208h+Type]
0x180001e34  mov     r14, [rsp+208h+var_198]
0x180001e39  test    edi, edi
0x180001e3b  jns     short loc_180001E52
0x180001e3d  cmp     qword ptr [r14+8], 7
0x180001e42  sbb     eax, eax
0x180001e44  and     eax, edi
0x180001e46  mov     edi, eax
0x180001e48  mov     [rsp+208h+Type], eax
0x180001e4c  jmp     short loc_180001E52
0x180001e4e  mov     edi, [rsp+208h+Type]
0x180001e52  mov     eax, edi
0x180001e54  mov     rcx, [rsp+208h+var_38]
0x180001e5c  xor     rcx, rsp; StackCookie
0x180001e5f  call    __security_check_cookie
0x180001e64  lea     r11, [rsp+208h+var_28]
0x180001e6c  mov     rbx, [r11+38h]
0x180001e70  mov     rsi, [r11+40h]
0x180001e74  mov     rsp, r11
0x180001e77  pop     r15
0x180001e79  pop     r14
0x180001e7b  pop     r13
0x180001e7d  pop     r12
0x180001e7f  pop     rdi
0x180001e80  retn
```
