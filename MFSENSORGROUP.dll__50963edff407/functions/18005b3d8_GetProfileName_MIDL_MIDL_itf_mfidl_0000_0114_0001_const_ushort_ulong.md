# GetProfileName(__MIDL___MIDL_itf_mfidl_0000_0114_0001 const &,ushort *,ulong)

- ea: `0x18005b3d8`
- end: `0x18005b4f7`
- name: `?GetProfileName@@YAJAEBU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@PEAGK@Z`
- size: `287`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005baa8`

## callees

- `0x180005fa0`
- `0x18000f518`
- `0x18005b3d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b4df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b4df`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18005b467`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18005b467`

## pseudocode

```c
__int64 __fastcall GetProfileName(IID *rclsid, unsigned __int16 *a2)
{
  unsigned __int64 i; // rax
  __int64 v5; // rcx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int Data1; // [rsp+20h] [rbp-18h]
  unsigned int v11; // [rsp+20h] [rbp-18h]
  LPOLESTR lpsz; // [rsp+58h] [rbp+20h] BYREF

  lpsz = 0;
  for ( i = 0; i < 0xC; ++i )
  {
    v5 = *(_QWORD *)&rclsid->Data1 - (_QWORD)*(&g_ProfileNameTable + 3 * i + 1);
    if ( *(struct ProfileNameInfo near **)&rclsid->Data1 == *(&g_ProfileNameTable + 3 * i + 1) )
      v5 = *(_QWORD *)rclsid->Data4 - (_QWORD)*(&g_ProfileNameTable + 3 * i + 2);
    if ( !v5 )
    {
      Data1 = rclsid[1].Data1;
      v6 = StringCchPrintfW(a2, 0x104u, L"%s,%u", *(&g_ProfileNameTable + 3 * i), Data1);
      v7 = v6;
      if ( v6 < 0 && g_wppLevels )
      {
        v8 = 30;
LABEL_16:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v6);
        goto LABEL_17;
      }
      goto LABEL_17;
    }
  }
  v6 = StringFromIID(rclsid, &lpsz);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_17;
    v8 = 31;
    goto LABEL_16;
  }
  v11 = rclsid[1].Data1;
  v6 = StringCchPrintfW(a2, 0x104u, L"%s,%u", lpsz, v11);
  v7 = v6;
  if ( v6 < 0 && g_wppLevels )
  {
    v8 = 32;
    goto LABEL_16;
  }
LABEL_17:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v7;
}

```

## disassembly

```asm
0x18005b3d8  mov     [rsp+arg_0], rbx
0x18005b3dd  mov     [rsp+arg_8], rsi
0x18005b3e2  push    rdi
0x18005b3e3  sub     rsp, 30h
0x18005b3e7  mov     rsi, rdx
0x18005b3ea  mov     [rsp+38h+lpsz], 0
0x18005b3f3  lea     rdx, ?g_ProfileNameTable@@3PAUProfileNameInfo@@A; ProfileNameInfo near * g_ProfileNameTable
0x18005b3fa  mov     rdi, rcx
0x18005b3fd  xor     eax, eax
0x18005b3ff  cmp     rax, 0Ch
0x18005b403  jnb     short loc_18005B45F
0x18005b405  mov     rcx, [rdi]
0x18005b408  lea     r9, [rax+rax*2]
0x18005b40c  sub     rcx, [rdx+r9*8+8]
0x18005b411  jnz     short loc_18005B41C
0x18005b413  mov     rcx, [rdi+8]
0x18005b417  sub     rcx, [rdx+r9*8+10h]
0x18005b41c  test    rcx, rcx
0x18005b41f  jz      short loc_18005B426
0x18005b421  inc     rax
0x18005b424  jmp     short loc_18005B3FF
0x18005b426  mov     r9, [rdx+r9*8]
0x18005b42a  lea     r8, aSU; "%s,%u"
0x18005b431  mov     eax, [rdi+10h]
0x18005b434  mov     edx, 104h; unsigned __int64
0x18005b439  mov     rcx, rsi; unsigned __int16 *
0x18005b43c  mov     [rsp+38h+var_18], eax
0x18005b440  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b445  mov     ebx, eax
0x18005b447  test    eax, eax
0x18005b449  jns     loc_18005B4D5
0x18005b44f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b456  jb      short loc_18005B4D5
0x18005b458  mov     edx, 1Eh
0x18005b45d  jmp     short loc_18005B4B7
0x18005b45f  lea     rdx, [rsp+38h+lpsz]; lplpsz
0x18005b464  mov     rcx, rdi; rclsid
0x18005b467  call    cs:__imp_StringFromIID
0x18005b46d  mov     ebx, eax
0x18005b46f  test    eax, eax
0x18005b471  jns     short loc_18005B483
0x18005b473  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b47a  jb      short loc_18005B4D5
0x18005b47c  mov     edx, 1Fh
0x18005b481  jmp     short loc_18005B4B7
0x18005b483  mov     eax, [rdi+10h]
0x18005b486  lea     r8, aSU; "%s,%u"
0x18005b48d  mov     r9, [rsp+38h+lpsz]
0x18005b492  mov     edx, 104h; unsigned __int64
0x18005b497  mov     rcx, rsi; unsigned __int16 *
0x18005b49a  mov     [rsp+38h+var_18], eax
0x18005b49e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b4a3  mov     ebx, eax
0x18005b4a5  test    eax, eax
0x18005b4a7  jns     short loc_18005B4D5
0x18005b4a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b4b0  jb      short loc_18005B4D5
0x18005b4b2  mov     edx, 20h ; ' '
0x18005b4b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b4be  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x18005b4c5  xor     r9d, r9d
0x18005b4c8  mov     [rsp+38h+var_18], eax
0x18005b4cc  mov     rcx, [rcx+10h]
0x18005b4d0  call    WPP_SF_qD
0x18005b4d5  mov     rcx, [rsp+38h+lpsz]; pv
0x18005b4da  test    rcx, rcx
0x18005b4dd  jz      short loc_18005B4E5
0x18005b4df  call    cs:__imp_CoTaskMemFree
0x18005b4e5  mov     rsi, [rsp+38h+arg_8]
0x18005b4ea  mov     eax, ebx
0x18005b4ec  mov     rbx, [rsp+38h+arg_0]
0x18005b4f1  add     rsp, 30h
0x18005b4f5  pop     rdi
0x18005b4f6  retn
```
