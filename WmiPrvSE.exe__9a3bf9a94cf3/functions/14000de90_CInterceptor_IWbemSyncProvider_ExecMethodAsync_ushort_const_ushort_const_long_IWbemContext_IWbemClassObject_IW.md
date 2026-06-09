# CInterceptor_IWbemSyncProvider::ExecMethodAsync(ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x14000de90`
- end: `0x14000e2e8`
- name: `?ExecMethodAsync@CInterceptor_IWbemSyncProvider@@UEAAJQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `1112`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, unsigned __int16 *const, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400053dc`
- `0x1400054a0`
- `0x140005544`
- `0x1400058dc`
- `0x140006c64`
- `0x14000d090`
- `0x14000de90`
- `0x14000e2f0`
- `0x14001ca74`
- `0x1400234b8`
- `0x1400292f8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000e066`
- `wbemcomn!GetMemLogObject` at `0x14000e202`
- `wbemcomn!GetMemLogObject` at `0x14000e246`
- `wbemcomn!GetMemLogObject` at `0x14000e066`
- `wbemcomn!GetMemLogObject` at `0x14000e202`
- `wbemcomn!GetMemLogObject` at `0x14000e246`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e20d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e251`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e20d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000e251`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000e033`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x14000e033`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000e025`
- `wbemcomn!?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z` at `0x14000e025`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000e1be`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000e1be`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000dfc6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000dfc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::ExecMethodAsync(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int16 *const a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject *a6,
        struct IWbemObjectSink *a7)
{
  int v7; // r15d
  _QWORD *v9; // rcx
  int v10; // edi
  struct IUnknown *v11; // r13
  __int64 v12; // rdx
  int v13; // r12d
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  HRESULT v19; // ebx
  int v20; // r14d
  struct IWbemContext *v21; // rdi
  int v22; // ebx
  struct IUnknown *v23; // rbx
  struct IServerSecurity *v24; // r14
  struct IUnknown *v25; // r15
  CMemoryLog *v27; // rax
  int v28; // eax
  unsigned int CurrentImpersonationLevel; // eax
  unsigned int v30; // edx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v32; // rax
  int v33; // [rsp+58h] [rbp-31h] BYREF
  struct IUnknown *v34; // [rsp+60h] [rbp-29h] BYREF
  struct IServerSecurity *v35; // [rsp+68h] [rbp-21h] BYREF
  struct IUnknown *ppInterface; // [rsp+70h] [rbp-19h] BYREF
  void *v37; // [rsp+78h] [rbp-11h] BYREF
  int v38; // [rsp+D8h] [rbp+4Fh] BYREF
  unsigned __int16 *v39; // [rsp+E0h] [rbp+57h]
  unsigned __int16 *v40; // [rsp+E8h] [rbp+5Fh]
  int v41; // [rsp+F0h] [rbp+67h]

  v41 = a4;
  v40 = a3;
  v39 = a2;
  v7 = a4;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSdqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      126,
      (unsigned int)WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      (char)a6,
      (char)a5,
      (char)a7);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = -2147217372;
  v11 = (struct IUnknown *)*((_QWORD *)this + 41);
  if ( !v11 )
    goto LABEL_30;
  v12 = *((_QWORD *)this + 75);
  if ( !*(_DWORD *)(v12 + 2092) )
    goto LABEL_30;
  v37 = 0;
  v13 = 0;
  v38 = 0;
  v34 = 0;
  v33 = 0;
  ppInterface = 0;
  v35 = 0;
  v14 = *(_DWORD *)(v12 + 1680) - 1;
  if ( v14 )
  {
    v15 = v14 - 4;
    if ( v15 )
    {
      v16 = v15 - 2;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 3;
          if ( v18 )
          {
            if ( (unsigned int)(v18 - 1) >= 2 )
            {
              v20 = 0;
              v11 = 0;
              v19 = ProviderSubSystem_Common_Globals::BeginImpersonation(&ppInterface, &v35, &v33, 0);
              v10 = -2147217406;
              if ( v19 >= 0 )
              {
                v28 = ProviderSubSystem_Common_Globals::SetProxyState(
                        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                        0,
                        &IID_IWbemServices,
                        *((struct IUnknown **)this + 41),
                        &v34,
                        &v38);
                v19 = v28;
                v13 = v38;
                if ( v28 == -2147217406 )
                {
                  v11 = (struct IUnknown *)*((_QWORD *)this + 41);
                  v19 = 0;
LABEL_37:
                  v9 = WPP_GLOBAL_Control;
                  v7 = v41;
                  goto LABEL_11;
                }
                if ( v28 < 0 )
                  goto LABEL_49;
                v11 = v34;
                CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
                v19 = ProviderSubSystem_Common_Globals::SetCloaking(v11, v30, CurrentImpersonationLevel);
                v20 = 1;
                if ( v19 < 0 )
                  goto LABEL_48;
                v19 = CoImpersonateClient();
                if ( v19 < 0 )
                {
                  v19 = -2147217405;
LABEL_48:
                  ProviderSubSystem_Common_Globals::RevertProxyState(
                    (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
                    0,
                    v34,
                    v13);
                  if ( v19 != -2147217406 )
                  {
LABEL_49:
                    ProviderSubSystem_Common_Globals::EndImpersonation(ppInterface, v35, v33);
LABEL_35:
                    if ( v19 < 0 )
                    {
                      MemLogObject = GetMemLogObject();
                      CMemoryLog::Write(MemLogObject, v19);
                    }
                    goto LABEL_37;
                  }
LABEL_22:
                  v9 = WPP_GLOBAL_Control;
                  goto LABEL_23;
                }
              }
              if ( v19 != -2147217406 )
                goto LABEL_35;
              goto LABEL_22;
            }
          }
        }
      }
    }
  }
  v19 = 0;
  v20 = 0;
LABEL_11:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
  {
    WPP_SF_d(v9[2], 71, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, (unsigned int)v19);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v19 >= 0 )
  {
    v21 = a5;
    v22 = CMUIPreferredLanguages::Set((CMUIPreferredLanguages *)&v37, a5);
    if ( v22 < 0 )
    {
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, v22);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v22);
      }
    }
    v10 = CInterceptor_IWbemSyncProvider::Helper_ExecMethodAsync(
            this,
            v20,
            v39,
            v40,
            v7,
            v21,
            a6,
            a7,
            (struct IWbemServices *)v11);
    v23 = v34;
    v24 = v35;
    v25 = ppInterface;
    CoRevertToSelf();
    if ( v23 )
      ProviderSubSystem_Common_Globals::RevertProxyState(
        (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
        0,
        v23,
        v13);
    if ( *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 1
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 5
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 7
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 8
      && *(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) != 11
      && (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 75) + 1680LL) - 12) >= 2 )
    {
      ProviderSubSystem_Common_Globals::EndImpersonation(v25, v24, v33);
    }
    goto LABEL_22;
  }
  v10 = v19;
LABEL_23:
  if ( v37 )
  {
    v38 = 0;
    if ( (int)CMUILocale::SetPreferredLanguages(8u, (const unsigned __int16 *)v37, (unsigned int *)&v38) >= 0 )
      CMUILocale::_Free(v37);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v10 < 0 )
  {
LABEL_30:
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, v10);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    WPP_SF_d(v9[2], 128, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000de90  mov     rax, rsp
0x14000de93  mov     [rax+20h], r9d
0x14000de97  mov     [rax+18h], r8
0x14000de9b  mov     [rax+10h], rdx
0x14000de9f  push    rbp
0x14000dea0  push    rbx
0x14000dea1  push    rsi
0x14000dea2  push    rdi
0x14000dea3  push    r12
0x14000dea5  push    r13
0x14000dea7  push    r14
0x14000dea9  push    r15
0x14000deab  lea     rbp, [rax-47h]
0x14000deaf  sub     rsp, 88h
0x14000deb6  mov     r15d, r9d
0x14000deb9  mov     r9, rdx
0x14000debc  mov     rsi, rcx
0x14000debf  lea     rax, WPP_GLOBAL_Control
0x14000dec6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000decd  cmp     rcx, rax
0x14000ded0  jz      short loc_14000DEDC
0x14000ded2  test    byte ptr [rcx+1Ch], 4
0x14000ded6  jnz     loc_14000E0C6
0x14000dedc  mov     edi, 80041024h
0x14000dee1  mov     r13, [rsi+148h]
0x14000dee8  xor     r8d, r8d
0x14000deeb  test    r13, r13
0x14000deee  jz      loc_14000E066
0x14000def4  mov     rdx, [rsi+258h]
0x14000defb  cmp     [rdx+82Ch], r8d
0x14000df02  jz      loc_14000E066
0x14000df08  mov     [rbp+3Fh+var_50], r8
0x14000df0c  mov     r12d, r8d
0x14000df0f  mov     [rbp+3Fh+arg_0], r8d
0x14000df13  mov     [rbp+3Fh+var_68], r8
0x14000df17  mov     [rbp+3Fh+var_70], r8d
0x14000df1b  mov     [rbp+3Fh+ppInterface], r8
0x14000df1f  mov     [rbp+3Fh+var_60], r8
0x14000df23  mov     edx, [rdx+690h]
0x14000df29  sub     edx, 1
0x14000df2c  jz      short loc_14000DF46
0x14000df2e  sub     edx, 4
0x14000df31  jz      short loc_14000DF46
0x14000df33  sub     edx, 2
0x14000df36  jz      short loc_14000DF46
0x14000df38  sub     edx, 1
0x14000df3b  jz      short loc_14000DF46
0x14000df3d  sub     edx, 3
0x14000df40  jnz     loc_14000E116
0x14000df46  mov     ebx, r8d
0x14000df49  mov     r14d, r8d
0x14000df4c  lea     rax, WPP_GLOBAL_Control
0x14000df53  cmp     rcx, rax
0x14000df56  jz      short loc_14000DF62
0x14000df58  test    byte ptr [rcx+1Ch], 4
0x14000df5c  jnz     loc_14000E218
0x14000df62  test    ebx, ebx
0x14000df64  js      loc_14000E2E0
0x14000df6a  mov     rdi, [rbp+3Fh+arg_20]
0x14000df6e  mov     rdx, rdi; struct IWbemContext *
0x14000df71  lea     rcx, [rbp+3Fh+var_50]; this
0x14000df75  call    ?Set@CMUIPreferredLanguages@@QEAAJPEAUIWbemContext@@@Z; CMUIPreferredLanguages::Set(IWbemContext *)
0x14000df7a  mov     ebx, eax
0x14000df7c  test    eax, eax
0x14000df7e  js      loc_14000E246
0x14000df84  mov     [rsp+40h], r13; struct IWbemServices *
0x14000df89  mov     rax, [rbp+3Fh+arg_30]
0x14000df8d  mov     [rsp+0C0h+var_88], rax; struct IWbemObjectSink *
0x14000df92  mov     rax, [rbp+3Fh+arg_28]
0x14000df96  mov     [rsp+0C0h+var_90], rax; struct IWbemClassObject *
0x14000df9b  mov     [rsp+0C0h+var_98], rdi; struct IWbemContext *
0x14000dfa0  mov     dword ptr [rsp+0C0h+var_A0], r15d; int
0x14000dfa5  mov     r9, [rbp+3Fh+arg_10]; unsigned __int16 *
0x14000dfa9  mov     r8, [rbp+3Fh+arg_8]; unsigned __int16 *
0x14000dfad  mov     edx, r14d; int
0x14000dfb0  mov     rcx, rsi; this
0x14000dfb3  call    ?Helper_ExecMethodAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z; CInterceptor_IWbemSyncProvider::Helper_ExecMethodAsync(int,ushort * const,ushort * const,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *,IWbemServices *)
0x14000dfb8  mov     edi, eax
0x14000dfba  mov     rbx, [rbp+3Fh+var_68]
0x14000dfbe  mov     r14, [rbp+3Fh+var_60]
0x14000dfc2  mov     r15, [rbp+3Fh+ppInterface]
0x14000dfc6  call    cs:__imp_CoRevertToSelf
0x14000dfcc  test    rbx, rbx
0x14000dfcf  jnz     loc_14000E29F
0x14000dfd5  mov     rcx, [rsi+258h]
0x14000dfdc  mov     r9d, [rcx+690h]
0x14000dfe3  sub     r9d, 1
0x14000dfe7  jz      short loc_14000E005
0x14000dfe9  sub     r9d, 4
0x14000dfed  jz      short loc_14000E005
0x14000dfef  sub     r9d, 2
0x14000dff3  jz      short loc_14000E005
0x14000dff5  sub     r9d, 1
0x14000dff9  jz      short loc_14000E005
0x14000dffb  sub     r9d, 3
0x14000dfff  jnz     loc_14000E2B8
0x14000e005  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e00c  mov     rdx, [rbp+3Fh+var_50]
0x14000e010  test    rdx, rdx
0x14000e013  jz      short loc_14000E040
0x14000e015  mov     [rbp+3Fh+arg_0], 0
0x14000e01c  lea     r8, [rbp+3Fh+arg_0]
0x14000e020  mov     ecx, 8
0x14000e025  call    cs:__imp_?SetPreferredLanguages@CMUILocale@@SAJKPEBGPEAK@Z; CMUILocale::SetPreferredLanguages(ulong,ushort const *,ulong *)
0x14000e02b  test    eax, eax
0x14000e02d  js      short loc_14000E039
0x14000e02f  mov     rcx, [rbp+3Fh+var_50]
0x14000e033  call    cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x14000e039  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e040  test    edi, edi
0x14000e042  js      short loc_14000E066
0x14000e044  lea     rax, WPP_GLOBAL_Control
0x14000e04b  cmp     rcx, rax
0x14000e04e  jnz     short loc_14000E080
0x14000e050  mov     eax, edi
0x14000e052  add     rsp, 88h
0x14000e059  pop     r15
0x14000e05b  pop     r14
0x14000e05d  pop     r13
0x14000e05f  pop     r12
0x14000e061  pop     rdi
0x14000e062  pop     rsi
0x14000e063  pop     rbx
0x14000e064  pop     rbp
0x14000e065  retn
0x14000e066  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000e06c  mov     edx, edi
0x14000e06e  mov     rcx, rax
0x14000e071  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000e077  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e07e  jmp     short loc_14000E044
0x14000e080  test    byte ptr [rcx+1Ch], 4
0x14000e084  jz      short loc_14000E050
0x14000e086  cmp     byte ptr [rcx+19h], 2
0x14000e08a  jb      short loc_14000E050
0x14000e08c  mov     edx, 80h
0x14000e091  mov     r9d, edi
0x14000e094  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000e09b  mov     rcx, [rcx+10h]
0x14000e09f  call    WPP_SF_d
0x14000e0a4  jmp     short loc_14000E050
0x14000e0a6  cmp     ebx, edi
0x14000e0a8  jz      loc_14000E005
0x14000e0ae  test    ebx, ebx
0x14000e0b0  js      loc_14000E202
0x14000e0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e0bd  mov     r15d, [rbp+3Fh+arg_18]
0x14000e0c1  jmp     loc_14000DF4C
0x14000e0c6  cmp     byte ptr [rcx+19h], 5
0x14000e0ca  jb      loc_14000DEDC
0x14000e0d0  mov     edx, 7Eh ; '~'
0x14000e0d5  mov     rax, [rbp+3Fh+arg_30]
0x14000e0d9  mov     [rsp+40h], rax
0x14000e0de  mov     rax, [rbp+3Fh+arg_20]
0x14000e0e2  mov     [rsp+0C0h+var_88], rax
0x14000e0e7  mov     rax, [rbp+3Fh+arg_28]
0x14000e0eb  mov     [rsp+0C0h+var_90], rax
0x14000e0f0  mov     dword ptr [rsp+0C0h+var_98], r15d
0x14000e0f5  mov     [rsp+0C0h+var_A0], r8
0x14000e0fa  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000e101  mov     rcx, [rcx+10h]
0x14000e105  call    WPP_SF_SSdqqq
0x14000e10a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e111  jmp     loc_14000DEDC
0x14000e116  sub     edx, 1
0x14000e119  jz      loc_14000DF46
0x14000e11f  cmp     edx, 1
0x14000e122  jz      loc_14000DF46
0x14000e128  mov     r14d, r8d
0x14000e12b  mov     r13, r8
0x14000e12e  xor     r9d, r9d; unsigned int *
0x14000e131  lea     r8, [rbp+3Fh+var_70]; int *
0x14000e135  lea     rdx, [rbp+3Fh+var_60]; struct IServerSecurity **
0x14000e139  lea     rcx, [rbp+3Fh+ppInterface]; ppInterface
0x14000e13d  call    ?BeginImpersonation@ProviderSubSystem_Common_Globals@@SAJAEAPEAUIUnknown@@AEAPEAUIServerSecurity@@AEAHPEAK@Z; ProviderSubSystem_Common_Globals::BeginImpersonation(IUnknown * &,IServerSecurity * &,int &,ulong *)
0x14000e142  mov     ebx, eax
0x14000e144  mov     edi, 80041002h
0x14000e149  test    eax, eax
0x14000e14b  js      loc_14000E0A6
0x14000e151  lea     r15, [rsi+1B8h]
0x14000e158  lea     rax, [rbp+3Fh+arg_0]
0x14000e15c  mov     [rsp+0C0h+var_98], rax; int *
0x14000e161  lea     rax, [rbp+3Fh+var_68]
0x14000e165  mov     [rsp+0C0h+var_A0], rax; struct IUnknown **
0x14000e16a  mov     r9, [rsi+148h]; struct IUnknown *
0x14000e171  lea     r8, IID_IWbemServices; struct _GUID *
0x14000e178  xor     edx, edx; unsigned int
0x14000e17a  mov     rcx, r15; struct ProxyContainer *
0x14000e17d  call    ?SetProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KAEBU_GUID@@PEAUIUnknown@@AEAPEAU4@AEAH@Z; ProviderSubSystem_Common_Globals::SetProxyState(ProxyContainer &,ulong,_GUID const &,IUnknown *,IUnknown * &,int &)
0x14000e182  mov     ebx, eax
0x14000e184  mov     r12d, [rbp+3Fh+arg_0]
0x14000e188  cmp     eax, edi
0x14000e18a  jnz     short loc_14000E19A
0x14000e18c  mov     r13, [rsi+148h]
0x14000e193  xor     ebx, ebx
0x14000e195  jmp     loc_14000E0B6
0x14000e19a  test    eax, eax
0x14000e19c  js      short loc_14000E1EC
0x14000e19e  mov     r13, [rbp+3Fh+var_68]
0x14000e1a2  call    ?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ; ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
0x14000e1a7  mov     r8d, eax; unsigned int
0x14000e1aa  mov     rcx, r13; struct IUnknown *
0x14000e1ad  call    ?SetCloaking@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@KK@Z; ProviderSubSystem_Common_Globals::SetCloaking(IUnknown *,ulong,ulong)
0x14000e1b2  mov     ebx, eax
0x14000e1b4  mov     r14d, 1
0x14000e1ba  test    eax, eax
0x14000e1bc  js      short loc_14000E1D3
0x14000e1be  call    cs:__imp_CoImpersonateClient
0x14000e1c4  mov     ebx, eax
0x14000e1c6  test    eax, eax
0x14000e1c8  jns     loc_14000E0A6
0x14000e1ce  mov     ebx, 80041003h
0x14000e1d3  mov     r9d, r12d; int
0x14000e1d6  mov     r8, [rbp+3Fh+var_68]; struct IUnknown *
0x14000e1da  xor     edx, edx; unsigned int
0x14000e1dc  mov     rcx, r15; struct ProxyContainer *
0x14000e1df  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000e1e4  cmp     ebx, edi
0x14000e1e6  jz      loc_14000E005
0x14000e1ec  mov     r8d, [rbp+3Fh+var_70]; int
0x14000e1f0  mov     rdx, [rbp+3Fh+var_60]; struct IServerSecurity *
0x14000e1f4  mov     rcx, [rbp+3Fh+ppInterface]; struct IUnknown *
0x14000e1f8  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000e1fd  jmp     loc_14000E0AE
0x14000e202  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000e208  mov     edx, ebx
0x14000e20a  mov     rcx, rax
0x14000e20d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000e213  jmp     loc_14000E0B6
0x14000e218  cmp     byte ptr [rcx+19h], 2
0x14000e21c  jb      loc_14000DF62
0x14000e222  mov     edx, 47h ; 'G'
0x14000e227  mov     r9d, ebx
0x14000e22a  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000e231  mov     rcx, [rcx+10h]
0x14000e235  call    WPP_SF_d
0x14000e23a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e241  jmp     loc_14000DF62
0x14000e246  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000e24c  mov     edx, ebx
0x14000e24e  mov     rcx, rax
0x14000e251  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000e257  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e25e  lea     rax, WPP_GLOBAL_Control
0x14000e265  cmp     rcx, rax
0x14000e268  jz      loc_14000DF84
0x14000e26e  test    byte ptr [rcx+1Ch], 4
0x14000e272  jz      loc_14000DF84
0x14000e278  cmp     byte ptr [rcx+19h], 2
0x14000e27c  jb      loc_14000DF84
0x14000e282  mov     edx, 7Fh
0x14000e287  mov     r9d, ebx
0x14000e28a  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000e291  mov     rcx, [rcx+10h]
0x14000e295  call    WPP_SF_d
0x14000e29a  jmp     loc_14000DF84
0x14000e29f  lea     rcx, [rsi+1B8h]; struct ProxyContainer *
0x14000e2a6  mov     r9d, r12d; int
0x14000e2a9  mov     r8, rbx; struct IUnknown *
0x14000e2ac  xor     edx, edx; unsigned int
0x14000e2ae  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14000e2b3  jmp     loc_14000DFD5
0x14000e2b8  sub     r9d, 1
0x14000e2bc  jz      loc_14000E005
0x14000e2c2  cmp     r9d, 1
0x14000e2c6  jz      loc_14000E005
0x14000e2cc  mov     r8d, [rbp+3Fh+var_70]; int
0x14000e2d0  mov     rdx, r14; struct IServerSecurity *
0x14000e2d3  mov     rcx, r15; struct IUnknown *
0x14000e2d6  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14000e2db  jmp     loc_14000E005
0x14000e2e0  mov     edi, ebx
0x14000e2e2  jmp     loc_14000E00C
```
