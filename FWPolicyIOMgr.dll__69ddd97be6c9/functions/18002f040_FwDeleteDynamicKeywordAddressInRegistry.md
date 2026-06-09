# FwDeleteDynamicKeywordAddressInRegistry

- ea: `0x18002f040`
- end: `0x18002f1b5`
- name: `FwDeleteDynamicKeywordAddressInRegistry`
- size: `373`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002b3d0`
- `0x18002f040`
- `0x18003993c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f08e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f08e`
- `fwbase!FwRegCloseKey` at `0x18002f195`
- `fwbase!FwRegCloseKey` at `0x18002f195`
- `fwbase!FwRegDeleteValue` at `0x18002f161`
- `fwbase!FwRegDeleteValue` at `0x18002f161`

## pseudocode

```c
__int64 __fastcall FwDeleteDynamicKeywordAddressInRegistry(GUID *rguid, int a2)
{
  HKEY v2; // rdi
  int DynamicKeywordRegKeyById; // ebx
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v10; // [rsp+20h] [rbp-39h] BYREF
  int v11; // [rsp+24h] [rbp-35h] BYREF
  HKEY v12; // [rsp+28h] [rbp-31h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-29h] BYREF

  v2 = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  memset_0(sz, 0, 0x4Eu);
  if ( StringFromGUID2(rguid, sz, 39) )
  {
    DynamicKeywordRegKeyById = FwGetDynamicKeywordRegKeyById(sz, &v10, &v12, (enum _tag_FW_STORE_TYPE *)&v11);
    if ( DynamicKeywordRegKeyById >= 0 )
    {
      v2 = v12;
      if ( !v10 )
        goto LABEL_22;
      if ( v10 != 1 || !v12 )
        MicrosoftTelemetryAssertTriggeredArgs(v8, (unsigned int)v10);
      if ( DynamicKeywordRegKeyById == 2 )
      {
LABEL_22:
        DynamicKeywordRegKeyById = 0;
        goto LABEL_23;
      }
      if ( a2 != v11 )
      {
        DynamicKeywordRegKeyById = -2147024891;
        goto LABEL_23;
      }
      DynamicKeywordRegKeyById = FwRegDeleteValue(v2, 0, sz);
      if ( DynamicKeywordRegKeyById < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v7 = 398;
          goto LABEL_5;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          397,
          WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
          (unsigned int)DynamicKeywordRegKeyById);
      v2 = v12;
    }
  }
  else
  {
    DynamicKeywordRegKeyById = -2147418113;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 396;
LABEL_5:
      WPP_SF_d(
        *((_QWORD *)v6 + 2),
        v7,
        WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        (unsigned int)DynamicKeywordRegKeyById);
    }
  }
LABEL_23:
  FwRegCloseKey(v2);
  return (unsigned int)DynamicKeywordRegKeyById;
}

```

## disassembly

```asm
0x18002f040  push    rbp
0x18002f042  push    rbx
0x18002f043  push    rsi
0x18002f044  push    rdi
0x18002f045  lea     rbp, [rsp-3Fh]
0x18002f04a  sub     rsp, 98h
0x18002f051  mov     rax, cs:__security_cookie
0x18002f058  xor     rax, rsp
0x18002f05b  mov     [rbp+57h+var_30], rax
0x18002f05f  xor     edi, edi
0x18002f061  mov     [rbp+57h+var_90], 0
0x18002f068  mov     esi, edx
0x18002f06a  mov     [rbp+57h+var_88], rdi
0x18002f06e  mov     rbx, rcx
0x18002f071  mov     [rbp+57h+var_8C], edi
0x18002f074  xor     edx, edx; Val
0x18002f076  lea     rcx, [rbp+57h+sz]; void *
0x18002f07a  lea     r8d, [rdi+4Eh]; Size
0x18002f07e  call    memset_0
0x18002f083  lea     r8d, [rdi+27h]; cchMax
0x18002f087  mov     rcx, rbx; rguid
0x18002f08a  lea     rdx, [rbp+57h+sz]; lpsz
0x18002f08e  call    cs:__imp_StringFromGUID2
0x18002f094  test    eax, eax
0x18002f096  jnz     short loc_18002F0DB
0x18002f098  mov     ebx, 8000FFFFh
0x18002f09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0a4  lea     rax, WPP_GLOBAL_Control
0x18002f0ab  cmp     rcx, rax
0x18002f0ae  jz      loc_18002F192
0x18002f0b4  test    byte ptr [rcx+1Ch], 1
0x18002f0b8  jz      loc_18002F192
0x18002f0be  mov     edx, 18Ch
0x18002f0c3  mov     rcx, [rcx+10h]
0x18002f0c7  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002f0ce  mov     r9d, ebx
0x18002f0d1  call    WPP_SF_d
0x18002f0d6  jmp     loc_18002F192
0x18002f0db  lea     r9, [rbp+57h+var_8C]; enum _tag_FW_STORE_TYPE *
0x18002f0df  lea     r8, [rbp+57h+var_88]; HKEY *
0x18002f0e3  lea     rdx, [rbp+57h+var_90]; int *
0x18002f0e7  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x18002f0eb  call    ?FwGetDynamicKeywordRegKeyById@@YAJPEBGPEAHPEAPEAUHKEY__@@PEAW4_tag_FW_STORE_TYPE@@@Z; FwGetDynamicKeywordRegKeyById(ushort const *,int *,HKEY__ * *,_tag_FW_STORE_TYPE *)
0x18002f0f0  mov     ebx, eax
0x18002f0f2  test    eax, eax
0x18002f0f4  jns     short loc_18002F12D
0x18002f0f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0fd  lea     rax, WPP_GLOBAL_Control
0x18002f104  cmp     rcx, rax
0x18002f107  jz      short loc_18002F127
0x18002f109  test    byte ptr [rcx+1Ch], 1
0x18002f10d  jz      short loc_18002F127
0x18002f10f  mov     rcx, [rcx+10h]
0x18002f113  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002f11a  mov     edx, 18Dh
0x18002f11f  mov     r9d, ebx
0x18002f122  call    WPP_SF_d
0x18002f127  mov     rdi, [rbp+57h+var_88]
0x18002f12b  jmp     short loc_18002F192
0x18002f12d  mov     edx, [rbp+57h+var_90]
0x18002f130  mov     rdi, [rbp+57h+var_88]
0x18002f134  test    edx, edx
0x18002f136  jz      short loc_18002F190
0x18002f138  cmp     edx, 1
0x18002f13b  jnz     short loc_18002F142
0x18002f13d  test    rdi, rdi
0x18002f140  jnz     short loc_18002F147
0x18002f142  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002f147  cmp     ebx, 2
0x18002f14a  jz      short loc_18002F190
0x18002f14c  cmp     esi, [rbp+57h+var_8C]
0x18002f14f  jz      short loc_18002F158
0x18002f151  mov     ebx, 80070005h
0x18002f156  jmp     short loc_18002F192
0x18002f158  lea     r8, [rbp+57h+sz]
0x18002f15c  xor     edx, edx
0x18002f15e  mov     rcx, rdi
0x18002f161  call    cs:__imp_FwRegDeleteValue
0x18002f167  mov     ebx, eax
0x18002f169  test    eax, eax
0x18002f16b  jns     short loc_18002F192
0x18002f16d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f174  lea     rax, WPP_GLOBAL_Control
0x18002f17b  cmp     rcx, rax
0x18002f17e  jz      short loc_18002F192
0x18002f180  test    byte ptr [rcx+1Ch], 1
0x18002f184  jz      short loc_18002F192
0x18002f186  mov     edx, 18Eh
0x18002f18b  jmp     loc_18002F0C3
0x18002f190  xor     ebx, ebx
0x18002f192  mov     rcx, rdi
0x18002f195  call    cs:__imp_FwRegCloseKey
0x18002f19b  mov     eax, ebx
0x18002f19d  mov     rcx, [rbp+57h+var_30]
0x18002f1a1  xor     rcx, rsp; StackCookie
0x18002f1a4  call    __security_check_cookie
0x18002f1a9  add     rsp, 98h
0x18002f1b0  pop     rdi
0x18002f1b1  pop     rsi
0x18002f1b2  pop     rbx
0x18002f1b3  pop     rbp
0x18002f1b4  retn
```
