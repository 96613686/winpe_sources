# FwSetHyperVVMConfigInRegistry

- ea: `0x180030680`
- end: `0x18003092e`
- name: `FwSetHyperVVMConfigInRegistry`
- size: `686`
- prototype: `__int64 __usercall@<rax>(struct _tag_WF_POLICY_STORE *@<rcx>, unsigned int@<edx>, struct _GUID *@<r8>, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030dd0`

## callees

- `0x180001cdc`
- `0x180003b94`
- `0x1800042c4`
- `0x180004f9c`
- `0x18001e9ac`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002df3c`
- `0x180030680`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003081c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003081c`
- `fwbase!FwRegCloseKey` at `0x180030885`
- `fwbase!FwRegCloseKey` at `0x180030909`
- `fwbase!FwRegCloseKey` at `0x180030885`
- `fwbase!FwRegCloseKey` at `0x180030909`
- `fwbase!FwRegDeleteKey` at `0x1800308a1`
- `fwbase!FwRegDeleteKey` at `0x1800308a1`
- `fwbase!FwRegQueryNumValues` at `0x180030851`
- `fwbase!FwRegQueryNumValues` at `0x180030851`

## string_xrefs

- `0x18003077d`: `ProcessHyperVVMConfigParams`

## pseudocode

```c
__int64 __fastcall FwSetHyperVVMConfigInRegistry(
        struct _tag_WF_POLICY_STORE *a1,
        unsigned int a2,
        struct _GUID *a3,
        __int64 a4,
        unsigned int a5)
{
  LPCOLESTR v9; // rcx
  int v10; // ebx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  HKEY v16; // [rsp+40h] [rbp-51h] BYREF
  struct _tag_WF_CONFIG_DESCRIPTOR *v17; // [rsp+48h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-41h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v16 = 0;
  v17 = 0;
  if ( !a1 || a2 - 1 > 4 || !a4 && a5 )
  {
    v10 = -2147024809;
    if ( v9 == (LPCOLESTR)&WPP_GLOBAL_Control || (v9[14] & 1) == 0 )
      return (unsigned int)v10;
    v12 = 173;
    goto LABEL_40;
  }
  if ( *((_DWORD *)a1 + 3) != 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = ProcessHyperVVMConfigParams(
          (int *)a1,
          a2,
          a3,
          *((_DWORD *)&FWPolicyAcessRightMap + *((int *)a1 + 3)),
          1,
          &v16,
          &v17);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        174,
        (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        v10,
        (__int64)"ProcessHyperVVMConfigParams");
    goto LABEL_42;
  }
  v11 = (*((__int64 (__fastcall **)(HKEY, _QWORD, __int64, _QWORD))v17 + 4))(v16, *((_QWORD *)v17 + 2), a4, a5);
  v10 = v11;
  if ( v11 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 175;
LABEL_18:
      v13 = (unsigned int)v11;
LABEL_41:
      WPP_SF_d(*((_QWORD *)v9 + 2), v12, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v13);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  if ( a4 || a5 )
  {
LABEL_36:
    UpdatePolicyVersion(a1);
    goto LABEL_42;
  }
  LODWORD(v17) = 0;
  memset_0(sz, 0, 0x4Eu);
  v11 = StringFromGUID2(a3, sz, 39);
  v10 = v11;
  if ( v11 >= 0 )
  {
    v11 = FwRegQueryNumValues(v16, &v17);
    v10 = v11;
    if ( v11 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 177;
        goto LABEL_18;
      }
      goto LABEL_42;
    }
    FwRegCloseKey(v16);
    v16 = 0;
    if ( !(_DWORD)v17 )
    {
      v14 = FwRegDeleteKey(*((_QWORD *)a1 + 6), sz);
      v10 = 0;
      if ( v14 != -2147024894 )
        v10 = v14;
      if ( v10 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_42;
        v12 = 178;
LABEL_40:
        v13 = (unsigned int)v10;
        goto LABEL_41;
      }
    }
    goto LABEL_36;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = 176;
    goto LABEL_18;
  }
LABEL_42:
  if ( v16 )
    FwRegCloseKey(v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180030680  push    rbp
0x180030682  push    rbx
0x180030683  push    rdi
0x180030684  push    r13
0x180030686  push    r14
0x180030688  push    r15
0x18003068a  lea     rbp, [rsp-27h]
0x18003068f  sub     rsp, 0B8h
0x180030696  mov     rax, cs:__security_cookie
0x18003069d  xor     rax, rsp
0x1800306a0  mov     [rbp+4Fh+var_40], rax
0x1800306a4  mov     r14, r9
0x1800306a7  mov     r15, r8
0x1800306aa  mov     ebx, edx
0x1800306ac  mov     rdi, rcx
0x1800306af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306b6  lea     r13, WPP_GLOBAL_Control
0x1800306bd  cmp     rcx, r13
0x1800306c0  jz      short loc_1800306E4
0x1800306c2  test    byte ptr [rcx+1Ch], 8
0x1800306c6  jz      short loc_1800306E4
0x1800306c8  mov     rcx, [rcx+10h]
0x1800306cc  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800306d3  mov     edx, 0ACh
0x1800306d8  call    WPP_SF_
0x1800306dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306e4  mov     [rbp+4Fh+var_A0], 0
0x1800306ec  mov     [rbp+4Fh+var_98], 0
0x1800306f4  test    rdi, rdi
0x1800306f7  jz      loc_1800308D8
0x1800306fd  lea     eax, [rbx-1]
0x180030700  cmp     eax, 4
0x180030703  ja      loc_1800308D8
0x180030709  test    r14, r14
0x18003070c  jnz     short loc_180030718
0x18003070e  cmp     [rbp+4Fh+arg_20], r14d
0x180030712  jnz     loc_1800308D8
0x180030718  cmp     dword ptr [rdi+0Ch], 2
0x18003071c  jz      short loc_180030723
0x18003071e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030723  movsxd  r9, dword ptr [rdi+0Ch]
0x180030727  lea     rax, [rbp+4Fh+var_98]
0x18003072b  mov     [rsp+0E0h+var_B0], rax; struct _tag_WF_CONFIG_DESCRIPTOR **
0x180030730  lea     rcx, ?FWPolicyAcessRightMap@@3PAKA; ulong near * FWPolicyAcessRightMap
0x180030737  lea     rax, [rbp+4Fh+var_A0]
0x18003073b  mov     r8, r15; struct _GUID *
0x18003073e  mov     [rsp+0E0h+var_B8], rax; HKEY *
0x180030743  mov     edx, ebx; unsigned int
0x180030745  mov     r9d, [rcx+r9*4]; unsigned int
0x180030749  mov     rcx, rdi; void *
0x18003074c  mov     [rsp+0E0h+var_C0], 1; int
0x180030754  call    ?ProcessHyperVVMConfigParams@@YAJPEAXKAEBU_GUID@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@@Z; ProcessHyperVVMConfigParams(void *,ulong,_GUID const &,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *)
0x180030759  mov     ebx, eax
0x18003075b  test    eax, eax
0x18003075d  jns     short loc_1800307A2
0x18003075f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030766  cmp     rcx, r13
0x180030769  jz      loc_180030900
0x18003076f  test    byte ptr [rcx+1Ch], 1
0x180030773  jz      loc_180030900
0x180030779  mov     rcx, [rcx+10h]
0x18003077d  lea     rax, aProcesshypervv; "ProcessHyperVVMConfigParams"
0x180030784  mov     edx, 0AEh
0x180030789  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18003078e  mov     r9d, ebx
0x180030791  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180030798  call    WPP_SF_ds
0x18003079d  jmp     loc_180030900
0x1800307a2  mov     rdx, [rbp+4Fh+var_98]
0x1800307a6  mov     r8, r14
0x1800307a9  mov     r9d, [rbp+4Fh+arg_20]
0x1800307ad  mov     rcx, [rbp+4Fh+var_A0]
0x1800307b1  mov     rax, [rdx+20h]
0x1800307b5  mov     rdx, [rdx+10h]
0x1800307b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307be  mov     ebx, eax
0x1800307c0  test    eax, eax
0x1800307c2  jns     short loc_1800307EB
0x1800307c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307cb  cmp     rcx, r13
0x1800307ce  jz      loc_180030900
0x1800307d4  test    byte ptr [rcx+1Ch], 1
0x1800307d8  jz      loc_180030900
0x1800307de  mov     edx, 0AFh
0x1800307e3  mov     r9d, eax
0x1800307e6  jmp     loc_1800308F0
0x1800307eb  test    r14, r14
0x1800307ee  jnz     loc_1800308CE
0x1800307f4  cmp     [rbp+4Fh+arg_20], r14d
0x1800307f8  jnz     loc_1800308CE
0x1800307fe  xor     edx, edx; Val
0x180030800  mov     dword ptr [rbp+4Fh+var_98], r14d
0x180030804  lea     r8d, [r14+4Eh]; Size
0x180030808  lea     rcx, [rbp+4Fh+sz]; void *
0x18003080c  call    memset_0
0x180030811  lea     r8d, [r14+27h]; cchMax
0x180030815  mov     rcx, r15; rguid
0x180030818  lea     rdx, [rbp+4Fh+sz]; lpsz
0x18003081c  call    cs:__imp_StringFromGUID2
0x180030822  mov     ebx, eax
0x180030824  test    eax, eax
0x180030826  jns     short loc_180030849
0x180030828  mov     rcx, cs:WPP_GLOBAL_Control
0x18003082f  cmp     rcx, r13
0x180030832  jz      loc_180030900
0x180030838  test    byte ptr [rcx+1Ch], 1
0x18003083c  jz      loc_180030900
0x180030842  mov     edx, 0B0h
0x180030847  jmp     short loc_1800307E3
0x180030849  mov     rcx, [rbp+4Fh+var_A0]
0x18003084d  lea     rdx, [rbp+4Fh+var_98]
0x180030851  call    cs:__imp_FwRegQueryNumValues
0x180030857  mov     ebx, eax
0x180030859  test    eax, eax
0x18003085b  jns     short loc_180030881
0x18003085d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030864  cmp     rcx, r13
0x180030867  jz      loc_180030900
0x18003086d  test    byte ptr [rcx+1Ch], 1
0x180030871  jz      loc_180030900
0x180030877  mov     edx, 0B1h
0x18003087c  jmp     loc_1800307E3
0x180030881  mov     rcx, [rbp+4Fh+var_A0]
0x180030885  call    cs:__imp_FwRegCloseKey
0x18003088b  cmp     dword ptr [rbp+4Fh+var_98], 0
0x18003088f  mov     [rbp+4Fh+var_A0], 0
0x180030897  jnz     short loc_1800308CE
0x180030899  mov     rcx, [rdi+30h]
0x18003089d  lea     rdx, [rbp+4Fh+sz]
0x1800308a1  call    cs:__imp_FwRegDeleteKey
0x1800308a7  xor     ebx, ebx
0x1800308a9  cmp     eax, 80070002h
0x1800308ae  cmovnz  ebx, eax
0x1800308b1  test    ebx, ebx
0x1800308b3  jns     short loc_1800308CE
0x1800308b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308bc  cmp     rcx, r13
0x1800308bf  jz      short loc_180030900
0x1800308c1  test    byte ptr [rcx+1Ch], 1
0x1800308c5  jz      short loc_180030900
0x1800308c7  mov     edx, 0B2h
0x1800308cc  jmp     short loc_1800308ED
0x1800308ce  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x1800308d1  call    ?UpdatePolicyVersion@@YAJPEAU_tag_WF_POLICY_STORE@@@Z; UpdatePolicyVersion(_tag_WF_POLICY_STORE *)
0x1800308d6  jmp     short loc_180030900
0x1800308d8  mov     ebx, 80070057h
0x1800308dd  cmp     rcx, r13
0x1800308e0  jz      short loc_18003090F
0x1800308e2  test    byte ptr [rcx+1Ch], 1
0x1800308e6  jz      short loc_18003090F
0x1800308e8  mov     edx, 0ADh
0x1800308ed  mov     r9d, ebx
0x1800308f0  mov     rcx, [rcx+10h]
0x1800308f4  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800308fb  call    WPP_SF_d
0x180030900  mov     rcx, [rbp+4Fh+var_A0]
0x180030904  test    rcx, rcx
0x180030907  jz      short loc_18003090F
0x180030909  call    cs:__imp_FwRegCloseKey
0x18003090f  mov     eax, ebx
0x180030911  mov     rcx, [rbp+4Fh+var_40]
0x180030915  xor     rcx, rsp; StackCookie
0x180030918  call    __security_check_cookie
0x18003091d  add     rsp, 0B8h
0x180030924  pop     r15
0x180030926  pop     r14
0x180030928  pop     r13
0x18003092a  pop     rdi
0x18003092b  pop     rbx
0x18003092c  pop     rbp
0x18003092d  retn
```
