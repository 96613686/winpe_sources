# IsRedirectToBrokerNeededInternal(ushort const *,tagRedirectionPolicyFlags const *)

- ea: `0x18010f4f4`
- end: `0x18010f6c9`
- name: `?IsRedirectToBrokerNeededInternal@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct tagRedirectionPolicyFlags *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d3f0`

## callees

- `0x18008a2d4`
- `0x18009acdc`
- `0x1800a856c`
- `0x180108508`
- `0x18010effc`
- `0x18010f4f4`
- `0x18010fc7c`
- `0x18011a410`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f539`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f551`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f5b5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f5e5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f5f4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f620`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f539`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f551`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f5b5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f5e5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f5f4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010f620`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010f50c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010f661`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010f50c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010f661`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18010f68f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18010f68f`
- `OLEAUT32!__imp_SysFreeString` at `0x18010f6b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18010f6b3`

## pseudocode

```c
_BOOL8 __fastcall IsRedirectToBrokerNeededInternal(
        const unsigned __int16 *a1,
        const struct tagRedirectionPolicyFlags *a2)
{
  BOOL v4; // ebx
  int v5; // edx
  int v6; // eax
  OLECHAR *v7; // rdi
  char Bool; // al
  unsigned int v9; // ebx
  bool v10; // zf
  char *CurrentEnterpriseID; // rax
  signed __int64 v12; // r8
  int v13; // edx
  int v14; // ecx
  bool v15; // zf
  BrowserUtilEdp *v16; // rcx
  unsigned int CurrentProcessManager; // ebx
  int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v21; // [rsp+70h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\urlpolicy\\lcieurlpolicy.cpp",
      (const char *)0x80004001LL,
      v19);
  if ( (unsigned __int8)IEConfiguration_GetBool(268435482)
    || (v4 = 1, (unsigned __int8)IEConfiguration_GetBool(268435481)) )
  {
    v5 = *(unsigned __int8 *)a2;
    bstrString = 0;
    v21 = 0;
    v6 = LCIEGetRedirectionPolicyForURLInternal(a1, v5, 1, 0xB000u, &v21, 0, &bstrString);
    v7 = bstrString;
    v4 = v6;
    if ( v6 < 0 )
    {
LABEL_28:
      SysFreeString(v7);
      return v4;
    }
    Bool = IEConfiguration_GetBool(268435526);
    v9 = v21;
    if ( Bool || (((unsigned __int8)v9 ^ (unsigned __int8)IsoGetIntegrity(1)) & 0x7F) == 0 )
    {
      if ( (v9 & 0x300000) == 0
        || (unsigned __int8)IEConfiguration_GetBool(536870913)
        || (unsigned __int8)IEConfiguration_GetBool(536870923)
        || (!IsOs_Wow6432() ? (v10 = (v9 & 0x100000) == 0) : (v10 = (v9 & 0x200000) == 0), v10) )
      {
        if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
        {
LABEL_26:
          CurrentProcessManager = IsoGetCurrentProcessManager();
          InitOnceExecuteOnce(&g_InitOnce, LoadIsoDll, 0, 0);
          v4 = ((__int64 (__fastcall *)(_QWORD, __int64))qword_1801740E0)(CurrentProcessManager, 1) != 0;
          goto LABEL_28;
        }
        CurrentEnterpriseID = (char *)GetCurrentEnterpriseID();
        if ( v7 )
        {
          if ( !CurrentEnterpriseID )
            goto LABEL_27;
          v12 = (char *)v7 - CurrentEnterpriseID;
          do
          {
            v13 = *(unsigned __int16 *)&CurrentEnterpriseID[v12];
            v14 = *(unsigned __int16 *)CurrentEnterpriseID - v13;
            if ( v14 )
              break;
            CurrentEnterpriseID += 2;
          }
          while ( v13 );
          v15 = v14 == 0;
        }
        else
        {
          v15 = CurrentEnterpriseID == 0;
        }
        if ( v15 && (!(unsigned int)IEConfiguration_GetDWORD(536870929) || BrowserUtilEdp::IsEdpEnforcementEnabled(v16)) )
          goto LABEL_26;
      }
    }
LABEL_27:
    v4 = 0;
    goto LABEL_28;
  }
  return v4;
}

```

## disassembly

```asm
0x18010f4f4  mov     [rsp+arg_0], rbx
0x18010f4f9  push    rsi
0x18010f4fa  push    rdi
0x18010f4fb  push    r14
0x18010f4fd  sub     rsp, 40h
0x18010f501  mov     rsi, rcx
0x18010f504  mov     rdi, rdx
0x18010f507  mov     ecx, 1000002Dh
0x18010f50c  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18010f512  cmp     eax, 2
0x18010f515  jnz     short loc_18010F534
0x18010f517  mov     rcx, [rsp+58h]; this
0x18010f51c  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\urlmon\\urlpolicy"...
0x18010f523  mov     r9d, 80004001h; char *
0x18010f529  mov     edx, 85h; void *
0x18010f52e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18010f534  mov     ecx, 1000001Ah
0x18010f539  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010f53f  mov     r14d, 1
0x18010f545  test    al, al
0x18010f547  jnz     short loc_18010F55F
0x18010f549  mov     ecx, 10000019h
0x18010f54e  mov     ebx, r14d
0x18010f551  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010f557  test    al, al
0x18010f559  jz      loc_18010F6B9
0x18010f55f  movzx   edx, byte ptr [rdi]; int
0x18010f562  lea     rax, [rsp+58h+bstrString]
0x18010f567  mov     [rsp+58h+var_28], rax; unsigned __int16 **
0x18010f56c  mov     r9d, 0B000h; unsigned int
0x18010f572  lea     rax, [rsp+58h+arg_10]
0x18010f577  mov     [rsp+58h+var_30], 0; int *
0x18010f580  mov     r8d, r14d; int
0x18010f583  mov     [rsp+58h+var_38], rax; unsigned int *
0x18010f588  mov     rcx, rsi; pwzURI
0x18010f58b  mov     [rsp+58h+bstrString], 0
0x18010f594  mov     [rsp+58h+arg_10], 0
0x18010f59c  call    ?LCIEGetRedirectionPolicyForURLInternal@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURLInternal(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x18010f5a1  mov     rdi, [rsp+58h+bstrString]
0x18010f5a6  mov     ebx, eax
0x18010f5a8  test    eax, eax
0x18010f5aa  js      loc_18010F6B0
0x18010f5b0  mov     ecx, 10000046h
0x18010f5b5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010f5bb  mov     ebx, [rsp+58h+arg_10]
0x18010f5bf  test    al, al
0x18010f5c1  jnz     short loc_18010F5D5
0x18010f5c3  mov     ecx, r14d
0x18010f5c6  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18010f5cb  xor     eax, ebx
0x18010f5cd  test    al, 7Fh
0x18010f5cf  jnz     loc_18010F6AE
0x18010f5d5  mov     esi, r14d
0x18010f5d8  test    ebx, 300000h
0x18010f5de  jz      short loc_18010F61B
0x18010f5e0  mov     ecx, 20000001h
0x18010f5e5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010f5eb  test    al, al
0x18010f5ed  jnz     short loc_18010F61B
0x18010f5ef  mov     ecx, 2000000Bh
0x18010f5f4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010f5fa  test    al, al
0x18010f5fc  jnz     short loc_18010F61B
0x18010f5fe  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x18010f603  test    al, al
0x18010f605  jz      short loc_18010F60F
0x18010f607  test    ebx, 200000h
0x18010f60d  jmp     short loc_18010F615
0x18010f60f  test    ebx, 100000h
0x18010f615  jnz     loc_18010F6AE
0x18010f61b  mov     ecx, 20000001h
0x18010f620  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010f626  test    al, al
0x18010f628  jnz     short loc_18010F674
0x18010f62a  call    GetCurrentEnterpriseID
0x18010f62f  test    rdi, rdi
0x18010f632  jz      short loc_18010F657
0x18010f634  test    rax, rax
0x18010f637  jz      short loc_18010F6AE
0x18010f639  mov     r8, rdi
0x18010f63c  sub     r8, rax
0x18010f63f  movzx   ecx, word ptr [rax]
0x18010f642  movzx   edx, word ptr [rax+r8]
0x18010f647  sub     ecx, edx
0x18010f649  jnz     short loc_18010F653
0x18010f64b  add     rax, 2
0x18010f64f  test    edx, edx
0x18010f651  jnz     short loc_18010F63F
0x18010f653  test    ecx, ecx
0x18010f655  jmp     short loc_18010F65A
0x18010f657  test    rax, rax
0x18010f65a  jnz     short loc_18010F6AE
0x18010f65c  mov     ecx, 20000011h
0x18010f661  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18010f667  test    eax, eax
0x18010f669  jz      short loc_18010F674
0x18010f66b  call    ?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpEnforcementEnabled(void)
0x18010f670  test    al, al
0x18010f672  jz      short loc_18010F6AE
0x18010f674  call    ?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x18010f679  xor     r9d, r9d; Context
0x18010f67c  lea     rdx, ?LoadIsoDll@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18010f683  xor     r8d, r8d; Parameter
0x18010f686  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18010f68d  mov     ebx, eax
0x18010f68f  call    cs:__imp_InitOnceExecuteOnce
0x18010f695  mov     rax, cs:qword_1801740E0
0x18010f69c  mov     edx, r14d
0x18010f69f  mov     ecx, ebx
0x18010f6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f6a6  neg     eax
0x18010f6a8  sbb     ebx, ebx
0x18010f6aa  and     ebx, esi
0x18010f6ac  jmp     short loc_18010F6B0
0x18010f6ae  xor     ebx, ebx
0x18010f6b0  mov     rcx, rdi; bstrString
0x18010f6b3  call    cs:__imp_SysFreeString
0x18010f6b9  mov     eax, ebx
0x18010f6bb  mov     rbx, [rsp+58h+arg_0]
0x18010f6c0  add     rsp, 40h
0x18010f6c4  pop     r14
0x18010f6c6  pop     rdi
0x18010f6c7  pop     rsi
0x18010f6c8  retn
```
