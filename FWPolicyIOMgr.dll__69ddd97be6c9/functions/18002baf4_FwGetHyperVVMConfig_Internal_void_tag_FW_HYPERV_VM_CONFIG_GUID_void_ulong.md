# FwGetHyperVVMConfig_Internal(void *,_tag_FW_HYPERV_VM_CONFIG,_GUID,void *,ulong *)

- ea: `0x18002baf4`
- end: `0x18002bc2b`
- name: `?FwGetHyperVVMConfig_Internal@@YAJPEAXW4_tag_FW_HYPERV_VM_CONFIG@@U_GUID@@0PEAK@Z`
- size: `311`
- prototype: `__int64 __fastcall(int *, unsigned int, struct _GUID *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002f790`

## callees

- `0x180001cdc`
- `0x1800042c4`
- `0x18001f650`
- `0x18002baf4`
- `0x18002df3c`
- `0x18003b010`

## import_xrefs

- `fwbase!FwRegCloseKey` at `0x18002bc0d`
- `fwbase!FwRegCloseKey` at `0x18002bc0d`

## string_xrefs

- `0x18002bb8b`: `ProcessHyperVVMConfigParams`

## pseudocode

```c
__int64 __fastcall FwGetHyperVVMConfig_Internal(int *a1, unsigned int a2, struct _GUID *a3, __int64 a4, __int64 a5)
{
  struct _GUID v5; // xmm0
  __int64 v7; // r9
  int v8; // eax
  struct _tag_WF_CONFIG_DESCRIPTOR *v9; // rdi
  int v10; // ebx
  struct _tag_WF_CONFIG_DESCRIPTOR *v12; // [rsp+40h] [rbp-58h] BYREF
  HKEY v13; // [rsp+48h] [rbp-50h] BYREF
  struct _GUID v14; // [rsp+50h] [rbp-48h] BYREF

  v5 = *a3;
  v13 = 0;
  v7 = a1[3];
  v14 = v5;
  v12 = 0;
  v8 = ProcessHyperVVMConfigParams(a1, a2, &v14, *((_DWORD *)&FWPolicyAcessRightMap + v7), 0, &v13, &v12);
  v9 = v12;
  v10 = v8;
  if ( v8 >= 0 )
  {
    v10 = (*((__int64 (__fastcall **)(HKEY, _QWORD, __int64, __int64))v12 + 3))(v13, *((_QWORD *)v12 + 2), a4, a5);
    if ( v10 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        (unsigned int)v10);
  }
  else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      158,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      v8,
      (__int64)"ProcessHyperVVMConfigParams");
  }
  if ( v9 && *((_QWORD *)v9 + 1) )
    FwRegCloseKey(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002baf4  mov     r11, rsp
0x18002baf7  push    rbx
0x18002baf8  push    rbp
0x18002baf9  push    rsi
0x18002bafa  push    rdi
0x18002bafb  sub     rsp, 78h
0x18002baff  mov     rax, cs:__security_cookie
0x18002bb06  xor     rax, rsp
0x18002bb09  mov     [rsp+98h+var_38], rax
0x18002bb0e  movups  xmm0, xmmword ptr [r8]
0x18002bb12  mov     rbp, [rsp+98h+arg_20]
0x18002bb1a  lea     rax, [r11-58h]
0x18002bb1e  mov     [r11-68h], rax
0x18002bb22  lea     r8, ?FWPolicyAcessRightMap@@3PAKA; ulong near * FWPolicyAcessRightMap
0x18002bb29  mov     rsi, r9
0x18002bb2c  mov     qword ptr [r11-50h], 0
0x18002bb34  movsxd  r9, dword ptr [rcx+0Ch]
0x18002bb38  lea     rax, [r11-50h]
0x18002bb3c  mov     [r11-70h], rax
0x18002bb40  movdqu  [rsp+98h+var_48], xmm0
0x18002bb46  mov     qword ptr [r11-58h], 0
0x18002bb4e  mov     r9d, [r8+r9*4]; unsigned int
0x18002bb52  lea     r8, [r11-48h]; struct _GUID *
0x18002bb56  mov     [rsp+98h+var_78], 0; int
0x18002bb5e  call    ?ProcessHyperVVMConfigParams@@YAJPEAXKAEBU_GUID@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@@Z; ProcessHyperVVMConfigParams(void *,ulong,_GUID const &,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *)
0x18002bb63  mov     rdi, [rsp+98h+var_58]
0x18002bb68  mov     ebx, eax
0x18002bb6a  test    eax, eax
0x18002bb6c  jns     short loc_18002BBAD
0x18002bb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb75  lea     rax, WPP_GLOBAL_Control
0x18002bb7c  cmp     rcx, rax
0x18002bb7f  jz      short loc_18002BBFC
0x18002bb81  test    byte ptr [rcx+1Ch], 1
0x18002bb85  jz      short loc_18002BBFC
0x18002bb87  mov     rcx, [rcx+10h]
0x18002bb8b  lea     rax, aProcesshypervv; "ProcessHyperVVMConfigParams"
0x18002bb92  mov     edx, 9Eh
0x18002bb97  mov     qword ptr [rsp+98h+var_78], rax
0x18002bb9c  mov     r9d, ebx
0x18002bb9f  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002bba6  call    WPP_SF_ds
0x18002bbab  jmp     short loc_18002BBFC
0x18002bbad  mov     rdx, [rdi+10h]
0x18002bbb1  mov     r9, rbp
0x18002bbb4  mov     rcx, [rsp+98h+var_50]
0x18002bbb9  mov     r8, rsi
0x18002bbbc  mov     rax, [rdi+18h]
0x18002bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbc5  mov     ebx, eax
0x18002bbc7  test    eax, eax
0x18002bbc9  jns     short loc_18002BBFC
0x18002bbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbd2  lea     rax, WPP_GLOBAL_Control
0x18002bbd9  cmp     rcx, rax
0x18002bbdc  jz      short loc_18002BBFC
0x18002bbde  test    byte ptr [rcx+1Ch], 1
0x18002bbe2  jz      short loc_18002BBFC
0x18002bbe4  mov     rcx, [rcx+10h]
0x18002bbe8  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002bbef  mov     edx, 9Fh
0x18002bbf4  mov     r9d, ebx
0x18002bbf7  call    WPP_SF_d
0x18002bbfc  test    rdi, rdi
0x18002bbff  jz      short loc_18002BC13
0x18002bc01  cmp     qword ptr [rdi+8], 0
0x18002bc06  jz      short loc_18002BC13
0x18002bc08  mov     rcx, [rsp+98h+var_50]
0x18002bc0d  call    cs:__imp_FwRegCloseKey
0x18002bc13  mov     eax, ebx
0x18002bc15  mov     rcx, [rsp+98h+var_38]
0x18002bc1a  xor     rcx, rsp; StackCookie
0x18002bc1d  call    __security_check_cookie
0x18002bc22  add     rsp, 78h
0x18002bc26  pop     rdi
0x18002bc27  pop     rsi
0x18002bc28  pop     rbp
0x18002bc29  pop     rbx
0x18002bc2a  retn
```
