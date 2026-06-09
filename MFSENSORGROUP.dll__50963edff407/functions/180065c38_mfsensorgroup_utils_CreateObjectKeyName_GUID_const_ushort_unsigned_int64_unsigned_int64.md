# mfsensorgroup_utils::CreateObjectKeyName(_GUID const &,ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x180065c38`
- end: `0x180065d6e`
- name: `?CreateObjectKeyName@mfsensorgroup_utils@@YAJAEBU_GUID@@PEAG_KPEA_K@Z`
- size: `310`
- prototype: `__int64 __fastcall(mfsensorgroup_utils *this, wchar_t *, unsigned __int16 *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180065f98`
- `0x1800661d4`

## callees

- `0x180005fa0`
- `0x1800199f4`
- `0x180049c9c`
- `0x180065c38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065d59`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180065cdc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180065cdc`

## string_xrefs

- `0x180065d10`: `Software\Classes\CLSID\%ls`

## pseudocode

```c
__int64 __fastcall mfsensorgroup_utils::CreateObjectKeyName(
        mfsensorgroup_utils *this,
        wchar_t *a2,
        unsigned __int16 *a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp+18h] BYREF

  lpsz = 0;
  v11 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      *a4 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpsz,
        0);
      v8 = StringFromCLSID(&CLSID_MFSensorGroupClassFactory, &lpsz);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v8 = StringCchPrintfExW(a2, 0x104u, 0, &v11, 0x1000u, L"Software\\Classes\\CLSID\\%ls", lpsz);
        v6 = v8;
        if ( v8 >= 0 )
        {
          *a4 = 260 - v11;
          goto LABEL_17;
        }
        if ( !g_wppLevels )
          goto LABEL_17;
        v9 = 15;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_17;
        v9 = 14;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v8);
      goto LABEL_17;
    }
    v6 = -2147467261;
    if ( !g_wppLevels )
      return v6;
    v7 = 13;
  }
  else
  {
    v6 = -2147024809;
    if ( !g_wppLevels )
      return v6;
    v7 = 11;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids, 0, v6);
LABEL_17:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v6;
}

```

## disassembly

```asm
0x180065c38  mov     rax, rsp
0x180065c3b  mov     [rax+10h], rbx
0x180065c3f  mov     [rax+18h], r8
0x180065c43  mov     [rax+8], rcx
0x180065c47  push    rbp
0x180065c48  push    rsi
0x180065c49  push    rdi
0x180065c4a  sub     rsp, 40h
0x180065c4e  mov     qword ptr [rax+18h], 0
0x180065c56  mov     rsi, r9
0x180065c59  mov     qword ptr [rax+8], 0
0x180065c61  mov     rbp, rdx
0x180065c64  test    rdx, rdx
0x180065c67  jnz     short loc_180065CA1
0x180065c69  mov     ebx, 80070057h
0x180065c6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065c75  jb      loc_180065D5F
0x180065c7b  lea     edx, [rbp+0Bh]
0x180065c7e  mov     [rsp+58h+var_38], ebx
0x180065c82  mov     rcx, cs:WPP_GLOBAL_Control
0x180065c89  lea     r8, WPP_bf69d25898313d4026ed1607ec5cb6bf_Traceguids
0x180065c90  xor     r9d, r9d
0x180065c93  mov     rcx, [rcx+10h]
0x180065c97  call    WPP_SF_qD
0x180065c9c  jmp     loc_180065D4F
0x180065ca1  test    rsi, rsi
0x180065ca4  jnz     short loc_180065CBD
0x180065ca6  mov     ebx, 80004003h
0x180065cab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065cb2  jb      loc_180065D5F
0x180065cb8  lea     edx, [rsi+0Dh]
0x180065cbb  jmp     short loc_180065C7E
0x180065cbd  xor     edx, edx
0x180065cbf  mov     qword ptr [r9], 0
0x180065cc6  lea     rcx, [rsp+58h+lpsz]
0x180065ccb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180065cd0  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x180065cd5  lea     rcx, CLSID_MFSensorGroupClassFactory; rclsid
0x180065cdc  call    cs:__imp_StringFromCLSID
0x180065ce2  mov     ebx, eax
0x180065ce4  test    eax, eax
0x180065ce6  jns     short loc_180065CFC
0x180065ce8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065cef  jb      short loc_180065D4F
0x180065cf1  mov     edx, 0Eh
0x180065cf6  mov     [rsp+58h+var_38], eax
0x180065cfa  jmp     short loc_180065C82
0x180065cfc  mov     rax, [rsp+58h+lpsz]
0x180065d01  lea     r9, [rsp+58h+arg_0]; unsigned __int64 *
0x180065d06  mov     [rsp+58h+var_28], rax
0x180065d0b  mov     edi, 104h
0x180065d10  lea     rax, aSoftwareClasse; "Software\\Classes\\CLSID\\%ls"
0x180065d17  xor     r8d, r8d; unsigned __int16 **
0x180065d1a  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x180065d1f  mov     edx, edi; unsigned __int64
0x180065d21  mov     rcx, rbp; Buffer
0x180065d24  mov     [rsp+58h+var_38], 1000h; unsigned int
0x180065d2c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180065d31  mov     ebx, eax
0x180065d33  test    eax, eax
0x180065d35  jns     short loc_180065D47
0x180065d37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065d3e  jb      short loc_180065D4F
0x180065d40  mov     edx, 0Fh
0x180065d45  jmp     short loc_180065CF6
0x180065d47  sub     rdi, [rsp+58h+arg_0]
0x180065d4c  mov     [rsi], rdi
0x180065d4f  mov     rcx, [rsp+58h+lpsz]; pv
0x180065d54  test    rcx, rcx
0x180065d57  jz      short loc_180065D5F
0x180065d59  call    cs:__imp_CoTaskMemFree
0x180065d5f  mov     eax, ebx
0x180065d61  mov     rbx, [rsp+58h+arg_8]
0x180065d66  add     rsp, 40h
0x180065d6a  pop     rdi
0x180065d6b  pop     rsi
0x180065d6c  pop     rbp
0x180065d6d  retn
```
