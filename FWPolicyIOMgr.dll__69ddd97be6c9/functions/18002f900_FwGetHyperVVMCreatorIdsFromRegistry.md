# FwGetHyperVVMCreatorIdsFromRegistry

- ea: `0x18002f900`
- end: `0x18002fc19`
- name: `FwGetHyperVVMCreatorIdsFromRegistry`
- size: `793`
- prototype: `__int64 __fastcall(struct _tag_WF_POLICY_STORE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x1800179e4`
- `0x180019a70`
- `0x18001ae18`
- `0x18001e670`
- `0x18001f650`
- `0x18002f900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002fac5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002fac5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002fafe`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002fafe`
- `fwbase!FwFree` at `0x18002fc11`
- `fwbase!FwFree` at `0x18002fc11`
- `fwbase!FwAlloc` at `0x18002fa30`
- `fwbase!FwAlloc` at `0x18002fa30`

## pseudocode

```c
__int64 __fastcall FwGetHyperVVMCreatorIdsFromRegistry(HKEY *a1, unsigned int *a2, __int64 *a3)
{
  int *v4; // r15
  bool v5; // zf
  int refreshed; // eax
  int v7; // ebx
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rsi
  unsigned int v12; // r14d
  DWORD i; // r12d
  HKEY v14; // rcx
  LSTATUS v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v21; // [rsp+50h] [rbp-B0h]
  __int64 *v22; // [rsp+58h] [rbp-A8h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName[3]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v22 = a3;
  v21 = a2;
  v4 = &dword_18004C8D0;
  v5 = dword_18004C8D0 == 0;
  *a2 = 0;
  *a3 = 0;
  if ( v5 )
    v4 = 0;
  cSubKeys = 0;
  cchName[0] = 255;
  if ( a1[6] || (refreshed = FwRefreshPolicyStore((struct _tag_WF_POLICY_STORE *)a1), v7 = refreshed, refreshed >= 0) )
  {
    refreshed = FwAdvPolicyRegQueryNumKeys(a1[6], &cSubKeys);
    v7 = refreshed;
    if ( refreshed >= 0 )
    {
      if ( cSubKeys )
      {
        v11 = FwAlloc(16LL * cSubKeys);
        if ( v11 )
        {
          v12 = 0;
          for ( i = 0; i < cSubKeys; ++i )
          {
            v14 = a1[6];
            cchName[0] = 255;
            v15 = RegEnumKeyExW(v14, i, Name, cchName, 0, 0, 0, 0);
            if ( v15 == 259 )
              break;
            if ( v15 > 0 )
              v7 = (unsigned __int16)v15 | 0x80070000;
            else
              v7 = v15;
            if ( v7 < 0 )
            {
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  166,
                  WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
                  (unsigned int)v7);
              FwFree(v11);
              return (unsigned int)v7;
            }
            v7 = CLSIDFromString(Name, (LPCLSID)(v11 + 16LL * v12));
            if ( v7 >= 0 )
            {
              ++v12;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  167,
                  WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
                  Name);
              if ( v4 && (unsigned int)*v4 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
              {
                v19 = 0x2000000;
                v20 = (__int64)Name;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                  (int)v4,
                  (int)word_1800418B2,
                  v16,
                  v17,
                  (__int64 **)&v20,
                  (__int64)&v19);
              }
              v7 = 0;
            }
          }
          *v21 = v12;
          *v22 = v11;
        }
        else
        {
          v7 = -2147024882;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v9 = 165;
            v10 = 2147942414LL;
            goto LABEL_9;
          }
        }
      }
      else
      {
        v7 = 0;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v9 = 164;
          v10 = 0;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = 163;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = 162;
LABEL_8:
      v10 = (unsigned int)refreshed;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v10);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002f900  mov     [rsp-8+arg_18], rbx
0x18002f905  push    rbp
0x18002f906  push    rsi
0x18002f907  push    rdi
0x18002f908  push    r12
0x18002f90a  push    r13
0x18002f90c  push    r14
0x18002f90e  push    r15
0x18002f910  lea     rbp, [rsp-180h]
0x18002f918  sub     rsp, 280h
0x18002f91f  mov     rax, cs:__security_cookie
0x18002f926  xor     rax, rsp
0x18002f929  mov     [rbp+1B0h+var_40], rax
0x18002f930  xor     edi, edi
0x18002f932  mov     [rsp+2B0h+var_258], r8
0x18002f937  mov     r13, rcx
0x18002f93a  mov     [rsp+2B0h+var_260], rdx
0x18002f93f  mov     ecx, cs:dword_18004C8D0
0x18002f945  lea     r15, dword_18004C8D0
0x18002f94c  test    ecx, ecx
0x18002f94e  mov     [rdx], edi
0x18002f950  mov     [r8], rdi
0x18002f953  cmovz   r15, rdi
0x18002f957  mov     [rsp+2B0h+cSubKeys], edi
0x18002f95b  mov     [rsp+2B0h+cchName], 0FFh
0x18002f963  cmp     [r13+30h], rdi
0x18002f967  jnz     short loc_18002F9B5
0x18002f969  mov     rcx, r13; struct _tag_WF_POLICY_STORE *
0x18002f96c  call    ?FwRefreshPolicyStore@@YAJPEAU_tag_WF_POLICY_STORE@@@Z; FwRefreshPolicyStore(_tag_WF_POLICY_STORE *)
0x18002f971  mov     ebx, eax
0x18002f973  test    eax, eax
0x18002f975  jns     short loc_18002F9B5
0x18002f977  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f97e  lea     rdi, WPP_GLOBAL_Control
0x18002f985  cmp     rcx, rdi
0x18002f988  jz      loc_18002FBB8
0x18002f98e  test    byte ptr [rcx+1Ch], 1
0x18002f992  jz      loc_18002FBB8
0x18002f998  mov     edx, 0A2h
0x18002f99d  mov     r9d, eax
0x18002f9a0  mov     rcx, [rcx+10h]
0x18002f9a4  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002f9ab  call    WPP_SF_d
0x18002f9b0  jmp     loc_18002FBB8
0x18002f9b5  mov     rcx, [r13+30h]; hKey
0x18002f9b9  lea     rdx, [rsp+2B0h+cSubKeys]; lpcSubKeys
0x18002f9be  call    FwAdvPolicyRegQueryNumKeys
0x18002f9c3  mov     ebx, eax
0x18002f9c5  test    eax, eax
0x18002f9c7  jns     short loc_18002F9F1
0x18002f9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9d0  lea     rdi, WPP_GLOBAL_Control
0x18002f9d7  cmp     rcx, rdi
0x18002f9da  jz      loc_18002FBB8
0x18002f9e0  test    byte ptr [rcx+1Ch], 1
0x18002f9e4  jz      loc_18002FBB8
0x18002f9ea  mov     edx, 0A3h
0x18002f9ef  jmp     short loc_18002F99D
0x18002f9f1  mov     eax, [rsp+2B0h+cSubKeys]
0x18002f9f5  test    eax, eax
0x18002f9f7  jnz     short loc_18002FA29
0x18002f9f9  mov     ebx, edi
0x18002f9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa02  lea     rdi, WPP_GLOBAL_Control
0x18002fa09  cmp     rcx, rdi
0x18002fa0c  jz      loc_18002FBB8
0x18002fa12  test    byte ptr [rcx+1Ch], 1
0x18002fa16  jz      loc_18002FBB8
0x18002fa1c  mov     edx, 0A4h
0x18002fa21  xor     r9d, r9d
0x18002fa24  jmp     loc_18002F9A0
0x18002fa29  mov     rcx, rax
0x18002fa2c  shl     rcx, 4
0x18002fa30  call    cs:__imp_FwAlloc
0x18002fa36  mov     rsi, rax
0x18002fa39  test    rax, rax
0x18002fa3c  jnz     short loc_18002FA71
0x18002fa3e  mov     ebx, 8007000Eh
0x18002fa43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa4a  lea     rdi, WPP_GLOBAL_Control
0x18002fa51  cmp     rcx, rdi
0x18002fa54  jz      loc_18002FBB8
0x18002fa5a  test    byte ptr [rcx+1Ch], 1
0x18002fa5e  jz      loc_18002FBB8
0x18002fa64  mov     edx, 0A5h
0x18002fa69  mov     r9d, ebx
0x18002fa6c  jmp     loc_18002F9A0
0x18002fa71  mov     r14d, edi
0x18002fa74  mov     r12d, edi
0x18002fa77  cmp     [rsp+2B0h+cSubKeys], edi
0x18002fa7b  jbe     loc_18002FBA8
0x18002fa81  lea     rdi, WPP_GLOBAL_Control
0x18002fa88  mov     rcx, [r13+30h]; hKey
0x18002fa8c  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18002fa91  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002fa9a  lea     r8, [rsp+2B0h+Name]; lpName
0x18002fa9f  mov     [rsp+2B0h+lpcchClass], 0; lpcchClass
0x18002faa8  mov     edx, r12d; dwIndex
0x18002faab  mov     [rsp+2B0h+lpClass], 0; lpClass
0x18002fab4  mov     [rsp+2B0h+lpReserved], 0; lpReserved
0x18002fabd  mov     [rsp+2B0h+cchName], 0FFh
0x18002fac5  call    cs:__imp_RegEnumKeyExW
0x18002facb  cmp     eax, 103h
0x18002fad0  jz      loc_18002FBA8
0x18002fad6  test    eax, eax
0x18002fad8  jg      short loc_18002FADE
0x18002fada  mov     ebx, eax
0x18002fadc  jmp     short loc_18002FAE7
0x18002fade  movzx   ebx, ax
0x18002fae1  or      ebx, 80070000h
0x18002fae7  test    ebx, ebx
0x18002fae9  js      loc_18002FBE4
0x18002faef  mov     edx, r14d
0x18002faf2  lea     rcx, [rsp+2B0h+Name]; lpsz
0x18002faf7  shl     rdx, 4
0x18002fafb  add     rdx, rsi; pclsid
0x18002fafe  call    cs:__imp_CLSIDFromString
0x18002fb04  mov     ebx, eax
0x18002fb06  test    eax, eax
0x18002fb08  jns     loc_18002FB97
0x18002fb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb15  cmp     rcx, rdi
0x18002fb18  jz      short loc_18002FB3A
0x18002fb1a  test    byte ptr [rcx+1Ch], 1
0x18002fb1e  jz      short loc_18002FB3A
0x18002fb20  mov     rcx, [rcx+10h]
0x18002fb24  lea     r9, [rsp+2B0h+Name]
0x18002fb29  mov     edx, 0A7h
0x18002fb2e  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002fb35  call    WPP_SF_S
0x18002fb3a  test    r15, r15
0x18002fb3d  jz      short loc_18002FB93
0x18002fb3f  mov     eax, [r15]
0x18002fb42  cmp     eax, 5
0x18002fb45  jbe     short loc_18002FB93
0x18002fb47  mov     rdx, 400000000000h
0x18002fb51  mov     rcx, r15
0x18002fb54  call    _tlgKeywordOn
0x18002fb59  test    al, al
0x18002fb5b  jz      short loc_18002FB93
0x18002fb5d  lea     rax, [rsp+2B0h+Name]
0x18002fb62  mov     [rsp+2B0h+var_270], 2000000h
0x18002fb6b  mov     [rsp+2B0h+var_268], rax
0x18002fb70  lea     rdx, word_1800418B2
0x18002fb77  lea     rax, [rsp+2B0h+var_270]
0x18002fb7c  mov     rcx, r15; int
0x18002fb7f  mov     [rsp+2B0h+lpClass], rax; __int64
0x18002fb84  lea     rax, [rsp+2B0h+var_268]
0x18002fb89  mov     [rsp+2B0h+lpReserved], rax; __int64
0x18002fb8e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18002fb93  xor     ebx, ebx
0x18002fb95  jmp     short loc_18002FB9A
0x18002fb97  inc     r14d
0x18002fb9a  inc     r12d
0x18002fb9d  cmp     r12d, [rsp+2B0h+cSubKeys]
0x18002fba2  jb      loc_18002FA88
0x18002fba8  mov     rax, [rsp+2B0h+var_260]
0x18002fbad  mov     [rax], r14d
0x18002fbb0  mov     rax, [rsp+2B0h+var_258]
0x18002fbb5  mov     [rax], rsi
0x18002fbb8  mov     eax, ebx
0x18002fbba  mov     rcx, [rbp+1B0h+var_40]
0x18002fbc1  xor     rcx, rsp; StackCookie
0x18002fbc4  call    __security_check_cookie
0x18002fbc9  mov     rbx, [rsp+2B0h+arg_18]
0x18002fbd1  add     rsp, 280h
0x18002fbd8  pop     r15
0x18002fbda  pop     r14
0x18002fbdc  pop     r13
0x18002fbde  pop     r12
0x18002fbe0  pop     rdi
0x18002fbe1  pop     rsi
0x18002fbe2  pop     rbp
0x18002fbe3  retn
0x18002fbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbeb  cmp     rcx, rdi
0x18002fbee  jz      short loc_18002FC0E
0x18002fbf0  test    byte ptr [rcx+1Ch], 1
0x18002fbf4  jz      short loc_18002FC0E
0x18002fbf6  mov     rcx, [rcx+10h]
0x18002fbfa  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002fc01  mov     edx, 0A6h
0x18002fc06  mov     r9d, ebx
0x18002fc09  call    WPP_SF_d
0x18002fc0e  mov     rcx, rsi
0x18002fc11  call    cs:__imp_FwFree
0x18002fc17  jmp     short loc_18002FBB8
```
