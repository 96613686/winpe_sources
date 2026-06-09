# FwGetHyperVProfileConfig_Internal(void *,_tag_FW_PROFILE_TYPE,_tag_FW_HYPERV_PROFILE_CONFIG,_GUID,void *,ulong *)

- ea: `0x18002b56c`
- end: `0x18002b6ac`
- name: `?FwGetHyperVProfileConfig_Internal@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@W4_tag_FW_HYPERV_PROFILE_CONFIG@@U_GUID@@0PEAK@Z`
- size: `320`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int128 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002f610`

## callees

- `0x180001cdc`
- `0x1800042c4`
- `0x18001f650`
- `0x18002b56c`
- `0x18002dcb0`
- `0x18003b010`

## import_xrefs

- `fwbase!FwRegCloseKey` at `0x18002b68e`
- `fwbase!FwRegCloseKey` at `0x18002b68e`

## string_xrefs

- `0x18002b60c`: `ProcessHyperVProfileConfigParams`

## pseudocode

```c
__int64 __fastcall FwGetHyperVProfileConfig_Internal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // eax
  __int64 v7; // rdi
  int v8; // ebx
  int v10; // [rsp+20h] [rbp-78h]
  __int64 v11; // [rsp+40h] [rbp-58h] BYREF
  __int64 v12; // [rsp+48h] [rbp-50h] BYREF
  __int128 v13; // [rsp+50h] [rbp-48h] BYREF

  v10 = *((_DWORD *)&FWPolicyAcessRightMap + *(int *)(a1 + 12));
  v13 = *a4;
  v12 = 0;
  v11 = 0;
  v6 = ProcessHyperVProfileConfigParams(a1, a2, a3, &v13, v10, 0, &v12, &v11);
  v7 = v11;
  v8 = v6;
  if ( v6 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(v11 + 24))(v12, *(_QWORD *)(v11 + 16), a5, a6);
    if ( v8 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        161,
        WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        (unsigned int)v8);
  }
  else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      160,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      v6,
      (__int64)"ProcessHyperVProfileConfigParams");
  }
  if ( v7 && *(_QWORD *)(v7 + 8) )
    FwRegCloseKey(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b56c  mov     r11, rsp
0x18002b56f  push    rbx
0x18002b570  push    rbp
0x18002b571  push    rsi
0x18002b572  push    rdi
0x18002b573  sub     rsp, 78h
0x18002b577  mov     rax, cs:__security_cookie
0x18002b57e  xor     rax, rsp
0x18002b581  mov     [rsp+98h+var_38], rax
0x18002b586  movups  xmm0, xmmword ptr [r9]
0x18002b58a  movsxd  rax, dword ptr [rcx+0Ch]
0x18002b58e  lea     r9, [r11-58h]
0x18002b592  mov     rsi, [rsp+98h+arg_20]
0x18002b59a  lea     r10, ?FWPolicyAcessRightMap@@3PAKA; ulong near * FWPolicyAcessRightMap
0x18002b5a1  mov     rbp, [rsp+98h+arg_28]
0x18002b5a9  mov     [r11-60h], r9
0x18002b5ad  lea     r9, [r11-50h]
0x18002b5b1  mov     eax, [r10+rax*4]
0x18002b5b5  mov     [r11-68h], r9
0x18002b5b9  lea     r9, [r11-48h]
0x18002b5bd  mov     [rsp+98h+var_70], 0
0x18002b5c5  mov     dword ptr [rsp+98h+var_78], eax
0x18002b5c9  movdqu  [rsp+98h+var_48], xmm0
0x18002b5cf  mov     qword ptr [r11-50h], 0
0x18002b5d7  mov     qword ptr [r11-58h], 0
0x18002b5df  call    ?ProcessHyperVProfileConfigParams@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@KAEBU_GUID@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@@Z; ProcessHyperVProfileConfigParams(void *,_tag_FW_PROFILE_TYPE,ulong,_GUID const &,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *)
0x18002b5e4  mov     rdi, [rsp+98h+var_58]
0x18002b5e9  mov     ebx, eax
0x18002b5eb  test    eax, eax
0x18002b5ed  jns     short loc_18002B62E
0x18002b5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5f6  lea     rax, WPP_GLOBAL_Control
0x18002b5fd  cmp     rcx, rax
0x18002b600  jz      short loc_18002B67D
0x18002b602  test    byte ptr [rcx+1Ch], 1
0x18002b606  jz      short loc_18002B67D
0x18002b608  mov     rcx, [rcx+10h]
0x18002b60c  lea     rax, aProcesshypervp; "ProcessHyperVProfileConfigParams"
0x18002b613  mov     edx, 0A0h
0x18002b618  mov     [rsp+98h+var_78], rax
0x18002b61d  mov     r9d, ebx
0x18002b620  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b627  call    WPP_SF_ds
0x18002b62c  jmp     short loc_18002B67D
0x18002b62e  mov     rdx, [rdi+10h]
0x18002b632  mov     r9, rbp
0x18002b635  mov     rcx, [rsp+98h+var_50]
0x18002b63a  mov     r8, rsi
0x18002b63d  mov     rax, [rdi+18h]
0x18002b641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b646  mov     ebx, eax
0x18002b648  test    eax, eax
0x18002b64a  jns     short loc_18002B67D
0x18002b64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b653  lea     rax, WPP_GLOBAL_Control
0x18002b65a  cmp     rcx, rax
0x18002b65d  jz      short loc_18002B67D
0x18002b65f  test    byte ptr [rcx+1Ch], 1
0x18002b663  jz      short loc_18002B67D
0x18002b665  mov     rcx, [rcx+10h]
0x18002b669  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b670  mov     edx, 0A1h
0x18002b675  mov     r9d, ebx
0x18002b678  call    WPP_SF_d
0x18002b67d  test    rdi, rdi
0x18002b680  jz      short loc_18002B694
0x18002b682  cmp     qword ptr [rdi+8], 0
0x18002b687  jz      short loc_18002B694
0x18002b689  mov     rcx, [rsp+98h+var_50]
0x18002b68e  call    cs:__imp_FwRegCloseKey
0x18002b694  mov     eax, ebx
0x18002b696  mov     rcx, [rsp+98h+var_38]
0x18002b69b  xor     rcx, rsp; StackCookie
0x18002b69e  call    __security_check_cookie
0x18002b6a3  add     rsp, 78h
0x18002b6a7  pop     rdi
0x18002b6a8  pop     rsi
0x18002b6a9  pop     rbp
0x18002b6aa  pop     rbx
0x18002b6ab  retn
```
