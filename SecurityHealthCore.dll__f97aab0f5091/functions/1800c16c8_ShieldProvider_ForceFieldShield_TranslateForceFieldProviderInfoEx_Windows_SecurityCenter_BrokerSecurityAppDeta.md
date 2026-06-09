# ShieldProvider::ForceFieldShield::TranslateForceFieldProviderInfoEx(Windows::SecurityCenter::BrokerSecurityAppDetails *,Shield_ForceFieldProviderInfo * *)

- ea: `0x1800c16c8`
- end: `0x1800c18c3`
- name: `?TranslateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUBrokerSecurityAppDetails@SecurityCenter@Windows@@PEAPEAUShield_ForceFieldProviderInfo@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(struct Windows::SecurityCenter::BrokerSecurityAppDetails *, struct Shield_ForceFieldProviderInfo **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bfab8`
- `0x1800c07bc`

## callees

- `0x18000d7fc`
- `0x1800be3f8`
- `0x1800c16c8`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c1730`
- `ole32!CoTaskMemFree` at `0x1800c173a`
- `ole32!CoTaskMemFree` at `0x1800c1744`
- `ole32!CoTaskMemFree` at `0x1800c174d`
- `ole32!CoTaskMemFree` at `0x1800c188d`
- `ole32!CoTaskMemFree` at `0x1800c1897`
- `ole32!CoTaskMemFree` at `0x1800c18a1`
- `ole32!CoTaskMemFree` at `0x1800c18aa`
- `ole32!CoTaskMemFree` at `0x1800c1730`
- `ole32!CoTaskMemFree` at `0x1800c173a`
- `ole32!CoTaskMemFree` at `0x1800c1744`
- `ole32!CoTaskMemFree` at `0x1800c174d`
- `ole32!CoTaskMemFree` at `0x1800c188d`
- `ole32!CoTaskMemFree` at `0x1800c1897`
- `ole32!CoTaskMemFree` at `0x1800c18a1`
- `ole32!CoTaskMemFree` at `0x1800c18aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c178f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c17f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c183b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c178f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c17f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c183b`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::TranslateForceFieldProviderInfoEx(
        struct Windows::SecurityCenter::BrokerSecurityAppDetails *a1,
        struct Shield_ForceFieldProviderInfo **a2)
{
  int v4; // eax
  int v5; // esi
  char *v6; // rbx
  HSTRING v8; // rcx
  unsigned __int16 **StringRawBuffer; // rax
  unsigned __int16 *v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  HSTRING v13; // rcx
  unsigned __int16 **v14; // rax
  unsigned __int16 *v15; // r8
  HSTRING v16; // rcx
  unsigned __int16 **v17; // rax
  unsigned __int16 *v18; // r8
  int v19; // eax
  unsigned int v20; // edi
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  v4 = CommonUtil::UtilCoTaskMemAllocObject<Shield_ForceFieldProviderInfo>(&pv);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
        (unsigned int)v4);
    v6 = (char *)pv;
    goto LABEL_6;
  }
  v6 = (char *)pv;
  *(_OWORD *)pv = *(_OWORD *)a1;
  *((_DWORD *)v6 + 14) = *((_DWORD *)a1 + 16);
  *((_DWORD *)v6 + 10) = *((_DWORD *)a1 + 10);
  *((_DWORD *)v6 + 11) = *((_DWORD *)a1 + 13);
  *((_DWORD *)v6 + 12) = *((_DWORD *)a1 + 11);
  *((_DWORD *)v6 + 13) = *((_DWORD *)a1 + 12);
  v8 = (HSTRING)*((_QWORD *)a1 + 2);
  if ( v8 )
  {
    StringRawBuffer = (unsigned __int16 **)WindowsGetStringRawBuffer(v8, 0);
    v5 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 16), StringRawBuffer, v10);
    if ( v5 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 72;
LABEL_14:
        WPP_SF_d(v11[2], v12, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, (unsigned int)v5);
        goto LABEL_6;
      }
      goto LABEL_6;
    }
  }
  v13 = (HSTRING)*((_QWORD *)a1 + 3);
  if ( v13 )
  {
    v14 = (unsigned __int16 **)WindowsGetStringRawBuffer(v13, 0);
    v5 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 24), v14, v15);
    if ( v5 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 73;
        goto LABEL_14;
      }
LABEL_6:
      if ( v6 )
      {
        CoTaskMemFree(*((LPVOID *)v6 + 2));
        CoTaskMemFree(*((LPVOID *)v6 + 3));
        CoTaskMemFree(*((LPVOID *)v6 + 4));
        CoTaskMemFree(v6);
      }
      return (unsigned int)v5;
    }
  }
  v16 = (HSTRING)*((_QWORD *)a1 + 4);
  if ( v16
    && (v17 = (unsigned __int16 **)WindowsGetStringRawBuffer(v16, 0),
        v19 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 32), v17, v18),
        v20 = v19,
        v19 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
        (unsigned int)v19);
    if ( v6 )
    {
      CoTaskMemFree(*((LPVOID *)v6 + 2));
      CoTaskMemFree(*((LPVOID *)v6 + 3));
      CoTaskMemFree(*((LPVOID *)v6 + 4));
      CoTaskMemFree(v6);
    }
    return v20;
  }
  else
  {
    *a2 = (struct Shield_ForceFieldProviderInfo *)v6;
    return 0;
  }
}

```

## disassembly

```asm
0x1800c16c8  push    rbx
0x1800c16ca  push    rsi
0x1800c16cb  push    rdi
0x1800c16cc  push    r14
0x1800c16ce  sub     rsp, 28h
0x1800c16d2  mov     rdi, rcx
0x1800c16d5  mov     [rsp+48h+pv], 0
0x1800c16de  lea     rcx, [rsp+48h+pv]
0x1800c16e3  mov     r14, rdx
0x1800c16e6  call    ??$UtilCoTaskMemAllocObject@UShield_ForceFieldProviderInfo@@@CommonUtil@@YAJPEAPEAUShield_ForceFieldProviderInfo@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<Shield_ForceFieldProviderInfo>(Shield_ForceFieldProviderInfo * *,unsigned __int64,bool)
0x1800c16eb  mov     esi, eax
0x1800c16ed  test    eax, eax
0x1800c16ef  jns     short loc_1800C175A
0x1800c16f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c16f8  lea     rdx, WPP_GLOBAL_Control
0x1800c16ff  cmp     rcx, rdx
0x1800c1702  jz      short loc_1800C1722
0x1800c1704  test    byte ptr [rcx+1Ch], 1
0x1800c1708  jz      short loc_1800C1722
0x1800c170a  mov     rcx, [rcx+10h]
0x1800c170e  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c1715  mov     edx, 47h ; 'G'
0x1800c171a  mov     r9d, eax
0x1800c171d  call    WPP_SF_d
0x1800c1722  mov     rbx, [rsp+48h+pv]
0x1800c1727  test    rbx, rbx
0x1800c172a  jz      short loc_1800C1753
0x1800c172c  mov     rcx, [rbx+10h]; pv
0x1800c1730  call    cs:__imp_CoTaskMemFree
0x1800c1736  mov     rcx, [rbx+18h]; pv
0x1800c173a  call    cs:__imp_CoTaskMemFree
0x1800c1740  mov     rcx, [rbx+20h]; pv
0x1800c1744  call    cs:__imp_CoTaskMemFree
0x1800c174a  mov     rcx, rbx; pv
0x1800c174d  call    cs:__imp_CoTaskMemFree
0x1800c1753  mov     eax, esi
0x1800c1755  jmp     loc_1800C18B9
0x1800c175a  mov     rbx, [rsp+48h+pv]
0x1800c175f  movups  xmm0, xmmword ptr [rdi]
0x1800c1762  movdqu  xmmword ptr [rbx], xmm0
0x1800c1766  mov     eax, [rdi+40h]
0x1800c1769  mov     [rbx+38h], eax
0x1800c176c  mov     eax, [rdi+28h]
0x1800c176f  mov     [rbx+28h], eax
0x1800c1772  mov     eax, [rdi+34h]
0x1800c1775  mov     [rbx+2Ch], eax
0x1800c1778  mov     eax, [rdi+2Ch]
0x1800c177b  mov     [rbx+30h], eax
0x1800c177e  mov     eax, [rdi+30h]
0x1800c1781  mov     [rbx+34h], eax
0x1800c1784  mov     rcx, [rdi+10h]; string
0x1800c1788  test    rcx, rcx
0x1800c178b  jz      short loc_1800C17E5
0x1800c178d  xor     edx, edx; length
0x1800c178f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1795  mov     rdx, rax; unsigned __int16 **
0x1800c1798  lea     rcx, [rbx+10h]; this
0x1800c179c  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800c17a1  mov     esi, eax
0x1800c17a3  test    eax, eax
0x1800c17a5  jns     short loc_1800C17E5
0x1800c17a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c17ae  lea     rdx, WPP_GLOBAL_Control
0x1800c17b5  cmp     rcx, rdx
0x1800c17b8  jz      loc_1800C1727
0x1800c17be  test    byte ptr [rcx+1Ch], 1
0x1800c17c2  jz      loc_1800C1727
0x1800c17c8  mov     edx, 48h ; 'H'
0x1800c17cd  mov     rcx, [rcx+10h]
0x1800c17d1  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c17d8  mov     r9d, esi
0x1800c17db  call    WPP_SF_d
0x1800c17e0  jmp     loc_1800C1727
0x1800c17e5  mov     rcx, [rdi+18h]; string
0x1800c17e9  test    rcx, rcx
0x1800c17ec  jz      short loc_1800C1830
0x1800c17ee  xor     edx, edx; length
0x1800c17f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c17f6  mov     rdx, rax; unsigned __int16 **
0x1800c17f9  lea     rcx, [rbx+18h]; this
0x1800c17fd  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800c1802  mov     esi, eax
0x1800c1804  test    eax, eax
0x1800c1806  jns     short loc_1800C1830
0x1800c1808  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c180f  lea     rdx, WPP_GLOBAL_Control
0x1800c1816  cmp     rcx, rdx
0x1800c1819  jz      loc_1800C1727
0x1800c181f  test    byte ptr [rcx+1Ch], 1
0x1800c1823  jz      loc_1800C1727
0x1800c1829  mov     edx, 49h ; 'I'
0x1800c182e  jmp     short loc_1800C17CD
0x1800c1830  mov     rcx, [rdi+20h]; string
0x1800c1834  test    rcx, rcx
0x1800c1837  jz      short loc_1800C18B4
0x1800c1839  xor     edx, edx; length
0x1800c183b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1841  mov     rdx, rax; unsigned __int16 **
0x1800c1844  lea     rcx, [rbx+20h]; this
0x1800c1848  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800c184d  mov     edi, eax
0x1800c184f  test    eax, eax
0x1800c1851  jns     short loc_1800C18B4
0x1800c1853  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c185a  lea     rdx, WPP_GLOBAL_Control
0x1800c1861  cmp     rcx, rdx
0x1800c1864  jz      short loc_1800C1884
0x1800c1866  test    byte ptr [rcx+1Ch], 1
0x1800c186a  jz      short loc_1800C1884
0x1800c186c  mov     rcx, [rcx+10h]
0x1800c1870  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c1877  mov     edx, 4Ah ; 'J'
0x1800c187c  mov     r9d, eax
0x1800c187f  call    WPP_SF_d
0x1800c1884  test    rbx, rbx
0x1800c1887  jz      short loc_1800C18B0
0x1800c1889  mov     rcx, [rbx+10h]; pv
0x1800c188d  call    cs:__imp_CoTaskMemFree
0x1800c1893  mov     rcx, [rbx+18h]; pv
0x1800c1897  call    cs:__imp_CoTaskMemFree
0x1800c189d  mov     rcx, [rbx+20h]; pv
0x1800c18a1  call    cs:__imp_CoTaskMemFree
0x1800c18a7  mov     rcx, rbx; pv
0x1800c18aa  call    cs:__imp_CoTaskMemFree
0x1800c18b0  mov     eax, edi
0x1800c18b2  jmp     short loc_1800C18B9
0x1800c18b4  mov     [r14], rbx
0x1800c18b7  xor     eax, eax
0x1800c18b9  add     rsp, 28h
0x1800c18bd  pop     r14
0x1800c18bf  pop     rdi
0x1800c18c0  pop     rsi
0x1800c18c1  pop     rbx
0x1800c18c2  retn
```
