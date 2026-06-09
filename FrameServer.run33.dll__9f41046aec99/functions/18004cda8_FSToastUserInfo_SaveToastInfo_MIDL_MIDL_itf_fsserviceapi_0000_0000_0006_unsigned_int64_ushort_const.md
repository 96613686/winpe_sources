# FSToastUserInfo::SaveToastInfo(__MIDL___MIDL_itf_fsserviceapi_0000_0000_0006,unsigned __int64,ushort const *)

- ea: `0x18004cda8`
- end: `0x18004cf7c`
- name: `?SaveToastInfo@FSToastUserInfo@@QEAAJW4__MIDL___MIDL_itf_fsserviceapi_0000_0000_0006@@_KPEBG@Z`
- size: `468`
- prototype: `int __high(enum __MIDL___MIDL_itf_fsserviceapi_0000_0000_0006, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18004ac44`
- `0x18004c470`

## callees

- `0x180009608`
- `0x180009f50`
- `0x18000a91c`
- `0x180017014`
- `0x180017a3c`
- `0x18004cda8`
- `0x18004d0e0`
- `0x1800e924c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ceac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004cf06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ceac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004cf06`

## pseudocode

```c
__int64 __fastcall FSToastUserInfo::SaveToastInfo(__int64 a1, int a2, __int64 a3, const WCHAR *a4)
{
  int v8; // eax
  signed int v9; // ebx
  unsigned __int64 v10; // r14
  DWORD cbData; // ebp
  __int64 unique; // rax
  __int64 v13; // rdx
  BYTE *lpData; // rbx
  LSTATUS v15; // eax
  int v16; // edx
  int v17; // r8d
  HKEY v18; // rcx
  LSTATUS v19; // eax
  unsigned __int64 v21[2]; // [rsp+30h] [rbp-38h] BYREF
  BYTE *v22; // [rsp+70h] [rbp+8h] BYREF

  v21[0] = 0;
  v22 = 0;
  v8 = StringCchLengthW(*(const unsigned __int16 **)(a1 + 80), 0x7FFFFFFFu, v21);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids, a1, v8);
    goto LABEL_23;
  }
  v10 = v21[0] + 1;
  cbData = 2 * (LODWORD(v21[0]) + 1) + 8;
  unique = wil::make_unique_nothrow<unsigned char [0]>(v21, cbData);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v22, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v21);
  if ( !cbData )
  {
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_23;
    v13 = 35;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids, a1, v9);
    goto LABEL_23;
  }
  lpData = v22;
  *(_QWORD *)v22 = a3;
  memcpy_0(lpData + 8, *(const void **)(a1 + 80), 2 * v10);
  v15 = RegSetValueExW(*(HKEY *)(a1 + 64), a4, 0, 3u, lpData, cbData);
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_23;
    v13 = 36;
    goto LABEL_8;
  }
  if ( a2 == 2 )
  {
    v18 = *(HKEY *)(a1 + 64);
    ++*(_DWORD *)(a1 + 108);
    *(_QWORD *)(a1 + 96) = a3;
    v19 = RegSetValueExW(v18, L"EffectsDiscoveredToast", 0, 4u, (const BYTE *)(a1 + 108), 4u);
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_23;
      v13 = 37;
      goto LABEL_8;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 88) = a3;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_SI(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, v17, *(_QWORD *)(a1 + 80), a3);
LABEL_23:
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004cda8  mov     rax, rsp
0x18004cdab  mov     [rax+10h], rbx
0x18004cdaf  mov     [rax+18h], rbp
0x18004cdb3  push    rsi
0x18004cdb4  push    rdi
0x18004cdb5  push    r12
0x18004cdb7  push    r14
0x18004cdb9  push    r15
0x18004cdbb  sub     rsp, 40h
0x18004cdbf  mov     r15d, edx
0x18004cdc2  mov     qword ptr [rax-38h], 0
0x18004cdca  mov     rdi, rcx
0x18004cdcd  mov     qword ptr [rax+8], 0
0x18004cdd5  mov     rcx, [rcx+50h]; unsigned __int16 *
0x18004cdd9  mov     rsi, r8
0x18004cddc  lea     r8, [rax-38h]; unsigned __int64 *
0x18004cde0  mov     edx, 7FFFFFFFh; unsigned __int64
0x18004cde5  mov     r12, r9
0x18004cde8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004cded  mov     ebx, eax
0x18004cdef  test    eax, eax
0x18004cdf1  jns     short loc_18004CE28
0x18004cdf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cdfa  jb      loc_18004CF57
0x18004ce00  mov     edx, 22h ; '"'
0x18004ce05  mov     dword ptr [rsp+68h+lpData], eax
0x18004ce09  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce10  lea     r8, WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids
0x18004ce17  mov     r9, rdi
0x18004ce1a  mov     rcx, [rcx+10h]
0x18004ce1e  call    WPP_SF_qD
0x18004ce23  jmp     loc_18004CF57
0x18004ce28  mov     r14, [rsp+68h+var_38]
0x18004ce2d  lea     rcx, [rsp+68h+var_38]
0x18004ce32  inc     r14
0x18004ce35  lea     ebp, ds:8[r14*2]
0x18004ce3d  mov     edx, ebp
0x18004ce3f  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18004ce44  mov     rdx, rax
0x18004ce47  lea     rcx, [rsp+68h+arg_0]
0x18004ce4c  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x18004ce51  lea     rcx, [rsp+68h+var_38]
0x18004ce56  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004ce5b  test    ebp, ebp
0x18004ce5d  jnz     short loc_18004CE7A
0x18004ce5f  mov     ebx, 8007000Eh
0x18004ce64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ce6b  jb      loc_18004CF57
0x18004ce71  lea     edx, [rbp+23h]
0x18004ce74  mov     dword ptr [rsp+68h+lpData], ebx
0x18004ce78  jmp     short loc_18004CE09
0x18004ce7a  mov     rbx, [rsp+68h+arg_0]
0x18004ce7f  lea     r8, [r14+r14]; Size
0x18004ce83  mov     [rbx], rsi
0x18004ce86  lea     rcx, [rbx+8]; void *
0x18004ce8a  mov     rdx, [rdi+50h]; Src
0x18004ce8e  call    memcpy_0
0x18004ce93  mov     rcx, [rdi+40h]; hKey
0x18004ce97  mov     r9d, 3; dwType
0x18004ce9d  xor     r8d, r8d; Reserved
0x18004cea0  mov     [rsp+68h+cbData], ebp; cbData
0x18004cea4  mov     rdx, r12; lpValueName
0x18004cea7  mov     [rsp+68h+lpData], rbx; lpData
0x18004ceac  call    cs:__imp_RegSetValueExW
0x18004ceb2  mov     ebx, eax
0x18004ceb4  mov     ebp, 80070000h
0x18004ceb9  test    eax, eax
0x18004cebb  jle     short loc_18004CEC2
0x18004cebd  movzx   ebx, ax
0x18004cec0  or      ebx, ebp
0x18004cec2  test    ebx, ebx
0x18004cec4  jns     short loc_18004CEDA
0x18004cec6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cecd  jb      loc_18004CF57
0x18004ced3  mov     edx, 24h ; '$'
0x18004ced8  jmp     short loc_18004CE74
0x18004ceda  cmp     r15d, 2
0x18004cede  jnz     short loc_18004CF2E
0x18004cee0  mov     rcx, [rdi+40h]; hKey
0x18004cee4  lea     rax, [rdi+6Ch]
0x18004cee8  inc     dword ptr [rax]
0x18004ceea  lea     r9d, [r15+2]; dwType
0x18004ceee  mov     [rsp+68h+cbData], r9d; cbData
0x18004cef3  lea     rdx, ValueName; "EffectsDiscoveredToast"
0x18004cefa  xor     r8d, r8d; Reserved
0x18004cefd  mov     [rsp+68h+lpData], rax; lpData
0x18004cf02  mov     [rdi+60h], rsi
0x18004cf06  call    cs:__imp_RegSetValueExW
0x18004cf0c  mov     ebx, eax
0x18004cf0e  test    eax, eax
0x18004cf10  jle     short loc_18004CF17
0x18004cf12  movzx   ebx, ax
0x18004cf15  or      ebx, ebp
0x18004cf17  test    ebx, ebx
0x18004cf19  jns     short loc_18004CF32
0x18004cf1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cf22  jb      short loc_18004CF57
0x18004cf24  mov     edx, 25h ; '%'
0x18004cf29  jmp     loc_18004CE74
0x18004cf2e  mov     [rdi+58h], rsi
0x18004cf32  cmp     cs:byte_18010EC4D, 8
0x18004cf39  jb      short loc_18004CF57
0x18004cf3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf42  mov     r9, [rdi+50h]
0x18004cf46  mov     [rsp+68h+lpData], rsi
0x18004cf4b  mov     rcx, [rcx+0D8h]
0x18004cf52  call    WPP_SF_SI
0x18004cf57  lea     rcx, [rsp+68h+arg_0]
0x18004cf5c  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004cf61  lea     r11, [rsp+68h+var_28]
0x18004cf66  mov     eax, ebx
0x18004cf68  mov     rbx, [r11+38h]
0x18004cf6c  mov     rbp, [r11+40h]
0x18004cf70  mov     rsp, r11
0x18004cf73  pop     r15
0x18004cf75  pop     r14
0x18004cf77  pop     r12
0x18004cf79  pop     rdi
0x18004cf7a  pop     rsi
0x18004cf7b  retn
```
