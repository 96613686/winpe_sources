# FwSetHyperVProfileConfigInRegistry

- ea: `0x180030390`
- end: `0x180030671`
- name: `FwSetHyperVProfileConfigInRegistry`
- size: `737`
- prototype: `__int64 __usercall@<rax>(struct _tag_WF_POLICY_STORE *@<rcx>, __int64, int)`
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
- `0x18002dcb0`
- `0x180030390`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003054a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003054a`
- `fwbase!FwRegCloseKey` at `0x1800305c1`
- `fwbase!FwRegCloseKey` at `0x18003064c`
- `fwbase!FwRegCloseKey` at `0x1800305c1`
- `fwbase!FwRegCloseKey` at `0x18003064c`
- `fwbase!FwRegDeleteKey` at `0x1800305dd`
- `fwbase!FwRegDeleteKey` at `0x1800305dd`
- `fwbase!FwRegQueryNumValues` at `0x180030589`
- `fwbase!FwRegQueryNumValues` at `0x180030589`

## string_xrefs

- `0x1800304a7`: `ProcessHyperVProfileConfigParams`

## pseudocode

```c
__int64 __fastcall FwSetHyperVProfileConfigInRegistry(
        struct _tag_WF_POLICY_STORE *a1,
        unsigned int a2,
        unsigned int a3,
        const GUID *a4,
        __int64 a5,
        unsigned int a6)
{
  LPCOLESTR v10; // rcx
  int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v15; // [rsp+40h] [rbp-59h] BYREF
  __int64 v16; // [rsp+48h] [rbp-51h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-49h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  v15 = 0;
  v16 = 0;
  if ( !a1 || a3 - 1 > 3 || !a5 && a6 )
  {
    v11 = -2147024809;
    if ( v10 == (LPCOLESTR)&WPP_GLOBAL_Control || (v10[14] & 1) == 0 )
      return (unsigned int)v11;
    v12 = 184;
    goto LABEL_39;
  }
  if ( *((_DWORD *)a1 + 3) != 2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v11 = ProcessHyperVProfileConfigParams(
          (__int64)a1,
          a2,
          a3,
          a4,
          *((_DWORD *)&FWPolicyAcessRightMap + *((int *)a1 + 3)),
          1,
          &v15,
          (__int64)&v16);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        185,
        (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        v11,
        (__int64)"ProcessHyperVProfileConfigParams");
    goto LABEL_40;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v16 + 32))(v15, *(_QWORD *)(v16 + 16), a5, a6);
  if ( v11 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 186;
LABEL_39:
      WPP_SF_d(*((_QWORD *)v10 + 2), v12, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v11);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( a5 || a6 )
  {
LABEL_35:
    UpdatePolicyVersion(a1);
    goto LABEL_40;
  }
  LODWORD(v16) = 0;
  memset_0(sz, 0, 0x4Eu);
  v11 = StringFromGUID2(a4, sz, 39);
  if ( v11 >= 0 )
  {
    v11 = FwRegQueryNumValues(v15, &v16);
    if ( v11 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 188;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    FwRegCloseKey(v15);
    v15 = 0;
    if ( !(_DWORD)v16 )
    {
      v13 = FwRegDeleteKey(*((_QWORD *)a1 + 6), sz);
      v11 = 0;
      if ( v13 != -2147024894 )
        v11 = v13;
      if ( v11 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 189;
          goto LABEL_39;
        }
        goto LABEL_40;
      }
    }
    goto LABEL_35;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = 187;
    goto LABEL_39;
  }
LABEL_40:
  if ( v15 )
    FwRegCloseKey(v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030390  push    rbp
0x180030392  push    rbx
0x180030393  push    rdi
0x180030394  push    r12
0x180030396  push    r14
0x180030398  push    r15
0x18003039a  lea     rbp, [rsp-1Fh]
0x18003039f  sub     rsp, 0B8h
0x1800303a6  mov     rax, cs:__security_cookie
0x1800303ad  xor     rax, rsp
0x1800303b0  mov     [rbp+47h+var_40], rax
0x1800303b4  mov     r14, [rbp+47h+arg_20]
0x1800303b8  mov     r15, r9
0x1800303bb  mov     ebx, r8d
0x1800303be  mov     r12d, edx
0x1800303c1  mov     rdi, rcx
0x1800303c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303cb  lea     rdx, WPP_GLOBAL_Control
0x1800303d2  cmp     rcx, rdx
0x1800303d5  jz      short loc_180030400
0x1800303d7  test    byte ptr [rcx+1Ch], 8
0x1800303db  jz      short loc_180030400
0x1800303dd  mov     rcx, [rcx+10h]
0x1800303e1  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800303e8  mov     edx, 0B7h
0x1800303ed  call    WPP_SF_
0x1800303f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303f9  lea     rdx, WPP_GLOBAL_Control
0x180030400  mov     [rbp+47h+var_A0], 0
0x180030408  mov     [rbp+47h+var_98], 0
0x180030410  test    rdi, rdi
0x180030413  jz      loc_18003061B
0x180030419  lea     eax, [rbx-1]
0x18003041c  cmp     eax, 3
0x18003041f  ja      loc_18003061B
0x180030425  test    r14, r14
0x180030428  jnz     short loc_180030434
0x18003042a  cmp     [rbp+47h+arg_28], r14d
0x18003042e  jnz     loc_18003061B
0x180030434  cmp     dword ptr [rdi+0Ch], 2
0x180030438  jz      short loc_18003043F
0x18003043a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003043f  movsxd  rax, dword ptr [rdi+0Ch]
0x180030443  lea     rdx, ?FWPolicyAcessRightMap@@3PAKA; ulong near * FWPolicyAcessRightMap
0x18003044a  lea     rcx, [rbp+47h+var_98]
0x18003044e  mov     r9, r15
0x180030451  mov     [rsp+0E0h+var_A8], rcx
0x180030456  mov     r8d, ebx
0x180030459  lea     rcx, [rbp+47h+var_A0]
0x18003045d  mov     eax, [rdx+rax*4]
0x180030460  mov     edx, r12d
0x180030463  mov     [rsp+0E0h+var_B0], rcx
0x180030468  mov     rcx, rdi
0x18003046b  mov     [rsp+0E0h+var_B8], 1
0x180030473  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180030477  call    ?ProcessHyperVProfileConfigParams@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@KAEBU_GUID@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@@Z; ProcessHyperVProfileConfigParams(void *,_tag_FW_PROFILE_TYPE,ulong,_GUID const &,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *)
0x18003047c  mov     ebx, eax
0x18003047e  test    eax, eax
0x180030480  jns     short loc_1800304CC
0x180030482  mov     rcx, cs:WPP_GLOBAL_Control
0x180030489  lea     rax, WPP_GLOBAL_Control
0x180030490  cmp     rcx, rax
0x180030493  jz      loc_180030643
0x180030499  test    byte ptr [rcx+1Ch], 1
0x18003049d  jz      loc_180030643
0x1800304a3  mov     rcx, [rcx+10h]
0x1800304a7  lea     rax, aProcesshypervp; "ProcessHyperVProfileConfigParams"
0x1800304ae  mov     edx, 0B9h
0x1800304b3  mov     [rsp+0E0h+var_C0], rax
0x1800304b8  mov     r9d, ebx
0x1800304bb  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800304c2  call    WPP_SF_ds
0x1800304c7  jmp     loc_180030643
0x1800304cc  mov     rdx, [rbp+47h+var_98]
0x1800304d0  mov     r8, r14
0x1800304d3  mov     r9d, [rbp+47h+arg_28]
0x1800304d7  mov     rcx, [rbp+47h+var_A0]
0x1800304db  mov     rax, [rdx+20h]
0x1800304df  mov     rdx, [rdx+10h]
0x1800304e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304e8  mov     ebx, eax
0x1800304ea  test    eax, eax
0x1800304ec  jns     short loc_180030519
0x1800304ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304f5  lea     rax, WPP_GLOBAL_Control
0x1800304fc  cmp     rcx, rax
0x1800304ff  jz      loc_180030643
0x180030505  test    byte ptr [rcx+1Ch], 1
0x180030509  jz      loc_180030643
0x18003050f  mov     edx, 0BAh
0x180030514  jmp     loc_180030630
0x180030519  test    r14, r14
0x18003051c  jnz     loc_180030611
0x180030522  cmp     [rbp+47h+arg_28], r14d
0x180030526  jnz     loc_180030611
0x18003052c  xor     edx, edx; Val
0x18003052e  mov     dword ptr [rbp+47h+var_98], r14d
0x180030532  lea     r8d, [r14+4Eh]; Size
0x180030536  lea     rcx, [rbp+47h+sz]; void *
0x18003053a  call    memset_0
0x18003053f  lea     r8d, [r14+27h]; cchMax
0x180030543  mov     rcx, r15; rguid
0x180030546  lea     rdx, [rbp+47h+sz]; lpsz
0x18003054a  call    cs:__imp_StringFromGUID2
0x180030550  mov     ebx, eax
0x180030552  test    eax, eax
0x180030554  jns     short loc_180030581
0x180030556  mov     rcx, cs:WPP_GLOBAL_Control
0x18003055d  lea     rax, WPP_GLOBAL_Control
0x180030564  cmp     rcx, rax
0x180030567  jz      loc_180030643
0x18003056d  test    byte ptr [rcx+1Ch], 1
0x180030571  jz      loc_180030643
0x180030577  mov     edx, 0BBh
0x18003057c  jmp     loc_180030630
0x180030581  mov     rcx, [rbp+47h+var_A0]
0x180030585  lea     rdx, [rbp+47h+var_98]
0x180030589  call    cs:__imp_FwRegQueryNumValues
0x18003058f  mov     ebx, eax
0x180030591  test    eax, eax
0x180030593  jns     short loc_1800305BD
0x180030595  mov     rcx, cs:WPP_GLOBAL_Control
0x18003059c  lea     rax, WPP_GLOBAL_Control
0x1800305a3  cmp     rcx, rax
0x1800305a6  jz      loc_180030643
0x1800305ac  test    byte ptr [rcx+1Ch], 1
0x1800305b0  jz      loc_180030643
0x1800305b6  mov     edx, 0BCh
0x1800305bb  jmp     short loc_180030630
0x1800305bd  mov     rcx, [rbp+47h+var_A0]
0x1800305c1  call    cs:__imp_FwRegCloseKey
0x1800305c7  cmp     dword ptr [rbp+47h+var_98], 0
0x1800305cb  mov     [rbp+47h+var_A0], 0
0x1800305d3  jnz     short loc_180030611
0x1800305d5  mov     rcx, [rdi+30h]
0x1800305d9  lea     rdx, [rbp+47h+sz]
0x1800305dd  call    cs:__imp_FwRegDeleteKey
0x1800305e3  xor     ebx, ebx
0x1800305e5  cmp     eax, 80070002h
0x1800305ea  cmovnz  ebx, eax
0x1800305ed  test    ebx, ebx
0x1800305ef  jns     short loc_180030611
0x1800305f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305f8  lea     rax, WPP_GLOBAL_Control
0x1800305ff  cmp     rcx, rax
0x180030602  jz      short loc_180030643
0x180030604  test    byte ptr [rcx+1Ch], 1
0x180030608  jz      short loc_180030643
0x18003060a  mov     edx, 0BDh
0x18003060f  jmp     short loc_180030630
0x180030611  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x180030614  call    ?UpdatePolicyVersion@@YAJPEAU_tag_WF_POLICY_STORE@@@Z; UpdatePolicyVersion(_tag_WF_POLICY_STORE *)
0x180030619  jmp     short loc_180030643
0x18003061b  mov     ebx, 80070057h
0x180030620  cmp     rcx, rdx
0x180030623  jz      short loc_180030652
0x180030625  test    byte ptr [rcx+1Ch], 1
0x180030629  jz      short loc_180030652
0x18003062b  mov     edx, 0B8h
0x180030630  mov     rcx, [rcx+10h]
0x180030634  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18003063b  mov     r9d, ebx
0x18003063e  call    WPP_SF_d
0x180030643  mov     rcx, [rbp+47h+var_A0]
0x180030647  test    rcx, rcx
0x18003064a  jz      short loc_180030652
0x18003064c  call    cs:__imp_FwRegCloseKey
0x180030652  mov     eax, ebx
0x180030654  mov     rcx, [rbp+47h+var_40]
0x180030658  xor     rcx, rsp; StackCookie
0x18003065b  call    __security_check_cookie
0x180030660  add     rsp, 0B8h
0x180030667  pop     r15
0x180030669  pop     r14
0x18003066b  pop     r12
0x18003066d  pop     rdi
0x18003066e  pop     rbx
0x18003066f  pop     rbp
0x180030670  retn
```
