# AddRemoteAdminSpecificChanges(ICF_AUTHBYPASS_REMOTE_ADMIN_SETTINGS_,ICF_SECURITY_DESCRIPTOR_ *,_tag_FW_RULE *)

- ea: `0x18002a8fc`
- end: `0x18002aaf1`
- name: `?AddRemoteAdminSpecificChanges@@YAJUICF_AUTHBYPASS_REMOTE_ADMIN_SETTINGS_@@PEAUICF_SECURITY_DESCRIPTOR_@@PEAU_tag_FW_RULE@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(__int128 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e4b0`

## callees

- `0x180003b94`
- `0x18001f650`
- `0x1800230c0`
- `0x18002a8fc`
- `0x180031008`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aab5`
- `fwbase!FwArrayCopy` at `0x18002a9cb`
- `fwbase!FwArrayCopy` at `0x18002a9cb`
- `fwbase!FwStringCopy` at `0x18002aa3c`
- `fwbase!FwStringCopy` at `0x18002aa3c`
- `fwbase!FwReportReturnError` at `0x18002a9e0`
- `fwbase!FwReportReturnError` at `0x18002aa29`
- `fwbase!FwReportReturnError` at `0x18002aac4`
- `fwbase!FwReportReturnError` at `0x18002a9e0`
- `fwbase!FwReportReturnError` at `0x18002aa29`
- `fwbase!FwReportReturnError` at `0x18002aac4`

## pseudocode

```c
__int64 __fastcall AddRemoteAdminSpecificChanges(__int128 *a1, _QWORD *a2, __int64 a3)
{
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  int v7; // ecx
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // ebx
  int v13; // ecx
  int v14; // eax
  HLOCAL hMem[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v17; // [rsp+40h] [rbp-40h]
  _OWORD v18[2]; // [rsp+50h] [rbp-30h] BYREF

  v5 = a1[1];
  v17 = *a1;
  v6 = a1[2];
  v18[0] = v5;
  v18[1] = v6;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v7 = *(_DWORD *)(a3 + 176);
  v8 = *(_DWORD *)(a3 + 180);
  hMem[0] = 0;
  if ( DWORD2(v17) == 1 )
  {
    v9 = v8 | 1;
    v10 = v7 | 1;
  }
  else
  {
    v9 = v8 & 0xFFFFFFFE;
    v10 = v7 & 0xFFFFFFFE;
  }
  *(_DWORD *)(a3 + 180) = v9;
  *(_DWORD *)(a3 + 176) = v10;
  v11 = FwArrayCopy(
          8,
          FwCopyIPv4SubNet,
          wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
          v18,
          a3 + 184);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = 3 - ((_DWORD)v17 != 2);
    *(_DWORD *)(a3 + 288) = v13;
    if ( a2 && v13 != 2 )
    {
      v14 = FwMigrateLegacyAuthenticatedBypassSddl(*a2, hMem);
      v12 = v14;
      if ( v14 < 0 || (v14 = FwStringCopy(hMem[0], a3 + 296), v12 = v14, v14 < 0) )
      {
        FwReportReturnError("AddRemoteAdminSpecificChanges", (unsigned int)v14);
        goto LABEL_16;
      }
      LocalFree(hMem[0]);
      *(_WORD *)(a3 + 292) |= 2u;
      hMem[0] = 0;
    }
    *(_WORD *)(a3 + 292) |= 1u;
    *(_WORD *)(a3 + 8) = 256;
    if ( v12 >= 0 )
      return (unsigned int)v12;
    goto LABEL_16;
  }
  FwReportReturnError("AddRemoteAdminSpecificChanges", (unsigned int)v11);
LABEL_16:
  if ( hMem[0] )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        *(_QWORD *)(a3 + 24),
        v12);
    LocalFree(hMem[0]);
  }
  return (unsigned int)FwReportReturnError("AddRemoteAdminSpecificChanges", (unsigned int)v12);
}

```

## disassembly

```asm
0x18002a8fc  mov     [rsp-28h+arg_18], rbx
0x18002a901  push    rbp
0x18002a902  push    rsi
0x18002a903  push    rdi
0x18002a904  push    r13
0x18002a906  push    r15
0x18002a908  mov     rbp, rsp
0x18002a90b  sub     rsp, 80h
0x18002a912  mov     rax, cs:__security_cookie
0x18002a919  xor     rax, rsp
0x18002a91c  mov     [rbp+var_10], rax
0x18002a920  movups  xmm0, xmmword ptr [rcx]
0x18002a923  mov     rdi, r8
0x18002a926  mov     rsi, rdx
0x18002a929  movups  xmm1, xmmword ptr [rcx+10h]
0x18002a92d  movaps  [rbp+var_40], xmm0
0x18002a931  movups  xmm0, xmmword ptr [rcx+20h]
0x18002a935  movaps  [rbp+var_30], xmm1
0x18002a939  movaps  [rbp+var_20], xmm0
0x18002a93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a944  lea     r15, WPP_GLOBAL_Control
0x18002a94b  cmp     rcx, r15
0x18002a94e  jz      short loc_18002A96B
0x18002a950  test    byte ptr [rcx+1Ch], 8
0x18002a954  jz      short loc_18002A96B
0x18002a956  mov     rcx, [rcx+10h]
0x18002a95a  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002a961  mov     edx, 30h ; '0'
0x18002a966  call    WPP_SF_
0x18002a96b  mov     ecx, [rdi+0B0h]
0x18002a971  mov     r13d, 1
0x18002a977  mov     eax, [rdi+0B4h]
0x18002a97d  mov     [rbp+hMem], 0
0x18002a985  cmp     dword ptr [rbp+var_40+8], r13d
0x18002a989  jnz     short loc_18002A993
0x18002a98b  or      eax, r13d
0x18002a98e  or      ecx, r13d
0x18002a991  jmp     short loc_18002A99C
0x18002a993  mov     edx, 0FFFFFFFEh
0x18002a998  and     eax, edx
0x18002a99a  and     ecx, edx
0x18002a99c  mov     [rdi+0B4h], eax
0x18002a9a2  lea     r9, [rbp+var_30]
0x18002a9a6  lea     rax, [rdi+0B8h]
0x18002a9ad  mov     [rdi+0B0h], ecx
0x18002a9b3  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18002a9ba  mov     [rsp+80h+var_60], rax
0x18002a9bf  lea     rdx, FwCopyIPv4SubNet
0x18002a9c6  mov     ecx, 8
0x18002a9cb  call    cs:__imp_FwArrayCopy
0x18002a9d1  mov     ebx, eax
0x18002a9d3  test    eax, eax
0x18002a9d5  jns     short loc_18002A9EB
0x18002a9d7  mov     edx, eax
0x18002a9d9  lea     rcx, aAddremoteadmin; "AddRemoteAdminSpecificChanges"
0x18002a9e0  call    cs:__imp_FwReportReturnError
0x18002a9e6  jmp     loc_18002AA7B
0x18002a9eb  mov     r15d, 2
0x18002a9f1  mov     eax, r15d
0x18002a9f4  sub     eax, dword ptr [rbp+var_40]
0x18002a9f7  neg     eax
0x18002a9f9  sbb     ecx, ecx
0x18002a9fb  add     ecx, 3
0x18002a9fe  mov     [rdi+120h], ecx
0x18002aa04  test    rsi, rsi
0x18002aa07  jz      short loc_18002AA62
0x18002aa09  cmp     ecx, r15d
0x18002aa0c  jz      short loc_18002AA62
0x18002aa0e  mov     rcx, [rsi]
0x18002aa11  lea     rdx, [rbp+hMem]
0x18002aa15  call    FwMigrateLegacyAuthenticatedBypassSddl
0x18002aa1a  mov     ebx, eax
0x18002aa1c  test    eax, eax
0x18002aa1e  jns     short loc_18002AA31
0x18002aa20  mov     edx, eax
0x18002aa22  lea     rcx, aAddremoteadmin; "AddRemoteAdminSpecificChanges"
0x18002aa29  call    cs:__imp_FwReportReturnError
0x18002aa2f  jmp     short loc_18002AA74
0x18002aa31  mov     rcx, [rbp+hMem]
0x18002aa35  lea     rdx, [rdi+128h]
0x18002aa3c  call    cs:__imp_FwStringCopy
0x18002aa42  mov     ebx, eax
0x18002aa44  test    eax, eax
0x18002aa46  js      short loc_18002AA20
0x18002aa48  mov     rcx, [rbp+hMem]; hMem
0x18002aa4c  call    cs:__imp_LocalFree
0x18002aa52  or      [rdi+124h], r15w
0x18002aa5a  mov     [rbp+hMem], 0
0x18002aa62  or      [rdi+124h], r13w
0x18002aa6a  mov     word ptr [rdi+8], 100h
0x18002aa70  test    ebx, ebx
0x18002aa72  jns     short loc_18002AACC
0x18002aa74  lea     r15, WPP_GLOBAL_Control
0x18002aa7b  cmp     [rbp+hMem], 0
0x18002aa80  jz      short loc_18002AABB
0x18002aa82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa89  cmp     rcx, r15
0x18002aa8c  jz      short loc_18002AAB1
0x18002aa8e  test    [rcx+1Ch], r13b
0x18002aa92  jz      short loc_18002AAB1
0x18002aa94  mov     r9, [rdi+18h]
0x18002aa98  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002aa9f  mov     rcx, [rcx+10h]
0x18002aaa3  mov     edx, 31h ; '1'
0x18002aaa8  mov     dword ptr [rsp+80h+var_60], ebx
0x18002aaac  call    WPP_SF_Sd
0x18002aab1  mov     rcx, [rbp+hMem]; hMem
0x18002aab5  call    cs:__imp_LocalFree
0x18002aabb  mov     edx, ebx
0x18002aabd  lea     rcx, aAddremoteadmin; "AddRemoteAdminSpecificChanges"
0x18002aac4  call    cs:__imp_FwReportReturnError
0x18002aaca  mov     ebx, eax
0x18002aacc  mov     eax, ebx
0x18002aace  mov     rcx, [rbp+var_10]
0x18002aad2  xor     rcx, rsp; StackCookie
0x18002aad5  call    __security_check_cookie
0x18002aada  mov     rbx, [rsp+80h+arg_18]
0x18002aae2  add     rsp, 80h
0x18002aae9  pop     r15
0x18002aaeb  pop     r13
0x18002aaed  pop     rdi
0x18002aaee  pop     rsi
0x18002aaef  pop     rbp
0x18002aaf0  retn
```
