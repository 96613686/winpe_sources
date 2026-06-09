# CPreloadManager::InitAndSetPrerenderBrokerStructs(_HIDDENTAB_REQUEST_ACTION,CPreloadManager::PredictivePrerenderPage const * const,_BROKER_BIND_INFO * const,_BROKER_REDIRECT_DETAIL * const,_HIDDENTAB_REQUEST_INFO * const)

- ea: `0x1808ef180`
- end: `0x1808ef393`
- name: `?InitAndSetPrerenderBrokerStructs@CPreloadManager@@AEAAJW4_HIDDENTAB_REQUEST_ACTION@@QEBUPredictivePrerenderPage@1@QEAU_BROKER_BIND_INFO@@QEAU_BROKER_REDIRECT_DETAIL@@QEAU_HIDDENTAB_REQUEST_INFO@@@Z`
- size: `531`
- prototype: `int __high(enum _HIDDENTAB_REQUEST_ACTION, const struct CPreloadManager::PredictivePrerenderPage *const, struct _BROKER_BIND_INFO *const, struct _BROKER_REDIRECT_DETAIL *const, struct _HIDDENTAB_REQUEST_INFO *const)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1806f4938`
- `0x1808eec1c`
- `0x1808ef92c`

## callees

- `0x180135278`
- `0x1804fa5e0`
- `0x1808ef180`
- `0x1810c2cb6`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808ef30b`
- `KERNEL32!GetCurrentProcessId` at `0x1808ef30b`
- `KERNEL32!GetCurrentThreadId` at `0x1808ef348`
- `KERNEL32!GetCurrentThreadId` at `0x1808ef348`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808ef331`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808ef331`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808ef35b`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x1808ef35b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808ef33a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808ef33a`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808ef319`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808ef319`
- `OLEAUT32!__imp_SysAllocString` at `0x1808ef1ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1808ef1ff`
- `OLEAUT32!__imp_VariantInit` at `0x1808ef299`
- `OLEAUT32!__imp_VariantInit` at `0x1808ef2fa`
- `OLEAUT32!__imp_VariantInit` at `0x1808ef299`
- `OLEAUT32!__imp_VariantInit` at `0x1808ef2fa`
- `OLEAUT32!__imp_VariantClear` at `0x1808ef305`
- `OLEAUT32!__imp_VariantClear` at `0x1808ef305`

## pseudocode

```c
__int64 __fastcall CPreloadManager::InitAndSetPrerenderBrokerStructs(
        __int64 a1,
        int a2,
        _DWORD *a3,
        _QWORD *a4,
        char *a5,
        __int64 a6)
{
  int v10; // r14d
  const OLECHAR *Url; // rax
  BSTR v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r10
  __int64 v18; // rcx
  char Integrity; // al
  DWORD CurrentThreadId; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF

  memset_0(a4, 0, 0x90u);
  memset_0(a5, 0, 0x44u);
  *(_OWORD *)a6 = 0;
  *(_DWORD *)(a6 + 16) = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)a3 + 56LL))(*(_QWORD *)a3, a4);
  if ( v10 < 0 )
    return (unsigned int)v10;
  Url = CMarkup::GetUrl(*(const struct CMarkup *const *)(a1 + 96));
  v12 = SysAllocString(Url);
  if ( !v12 )
    return (unsigned int)-2147024882;
  a4[3] = v12;
  if ( a3[6] == 26 )
    goto LABEL_8;
  if ( a3[6] != 27 )
  {
    if ( a3[6] != 99 )
    {
      if ( a3[6] != 100 )
        goto LABEL_10;
      goto LABEL_7;
    }
LABEL_8:
    v13 = 0x2000000000LL;
    goto LABEL_9;
  }
LABEL_7:
  v13 = 0x4000000000LL;
LABEL_9:
  a4[14] |= v13;
LABEL_10:
  v14 = *(_QWORD *)(a1 + 96);
  if ( v14 )
  {
    v15 = *(_QWORD *)(v14 + 320);
    if ( v15 )
    {
      v16 = *(_QWORD *)(v15 + 16);
      if ( v16 )
      {
        if ( *(_QWORD *)(v16 + 64) && *(char *)(v16 + 4868) >= 0 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v17 = 0;
          v18 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 320LL);
          if ( v18 )
            v17 = *(_QWORD *)(v18 + 16);
          if ( (int)CTExec(*(struct IUnknown **)(v17 + 64), &CGID_Explorer, 0x78u, 0, 0, &pvarg) >= 0 )
          {
            if ( pvarg.vt == 8 )
            {
              a4[10] = pvarg.llVal;
              VariantInit(&pvarg);
            }
            VariantClear(&pvarg);
          }
        }
      }
    }
  }
  *((_DWORD *)a5 + 6) = GetCurrentProcessId();
  Integrity = IsoGetIntegrity(1);
  *((_DWORD *)a5 + 8) = 0;
  *((_DWORD *)a5 + 7) = Integrity & 0x7F;
  *((_DWORD *)a5 + 10) = IEConfiguration_GetDWORD(536870929);
  *(_OWORD *)(a5 + 52) = *(_OWORD *)GlobalThreadState();
  CurrentThreadId = GetCurrentThreadId();
  LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, (unsigned int *)a5, 0);
  *((_DWORD *)a5 + 12) = a3[3];
  *(_DWORD *)a6 = a2;
  *(_DWORD *)(a6 + 12) = a3[2];
  *(_DWORD *)(a6 + 8) = 37748736;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1808ef180  push    rbx
0x1808ef182  push    rbp
0x1808ef183  push    rsi
0x1808ef184  push    rdi
0x1808ef185  push    r12
0x1808ef187  push    r14
0x1808ef189  push    r15
0x1808ef18b  sub     rsp, 50h
0x1808ef18f  mov     rsi, r8
0x1808ef192  mov     r12d, edx
0x1808ef195  mov     rdi, rcx
0x1808ef198  xor     edx, edx; Val
0x1808ef19a  mov     r8d, 90h; Size
0x1808ef1a0  mov     rcx, r9; void *
0x1808ef1a3  mov     rbx, r9
0x1808ef1a6  call    memset_0
0x1808ef1ab  mov     rbp, [rsp+88h+arg_20]
0x1808ef1b3  xor     edx, edx; Val
0x1808ef1b5  mov     rcx, rbp; void *
0x1808ef1b8  lea     r8d, [rdx+44h]; Size
0x1808ef1bc  call    memset_0
0x1808ef1c1  mov     r15, [rsp+88h+arg_28]
0x1808ef1c9  xor     eax, eax
0x1808ef1cb  xorps   xmm0, xmm0
0x1808ef1ce  mov     rdx, rbx
0x1808ef1d1  movups  xmmword ptr [r15], xmm0
0x1808ef1d5  mov     [r15+10h], eax
0x1808ef1d9  mov     rcx, [rsi]
0x1808ef1dc  mov     rax, [rcx]
0x1808ef1df  mov     rax, [rax+38h]
0x1808ef1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808ef1e8  mov     r14d, eax
0x1808ef1eb  test    eax, eax
0x1808ef1ed  js      loc_1808EF381
0x1808ef1f3  mov     rcx, [rdi+60h]; struct CMarkup *
0x1808ef1f7  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x1808ef1fc  mov     rcx, rax; psz
0x1808ef1ff  call    cs:__imp_SysAllocString
0x1808ef205  test    rax, rax
0x1808ef208  jz      loc_1808EF37B
0x1808ef20e  mov     [rbx+18h], rax
0x1808ef212  mov     ecx, [rsi+18h]
0x1808ef215  sub     ecx, 1Ah
0x1808ef218  jz      short loc_1808EF235
0x1808ef21a  sub     ecx, 1
0x1808ef21d  jz      short loc_1808EF229
0x1808ef21f  sub     ecx, 48h ; 'H'
0x1808ef222  jz      short loc_1808EF235
0x1808ef224  cmp     ecx, 1
0x1808ef227  jnz     short loc_1808EF243
0x1808ef229  mov     rax, 4000000000h
0x1808ef233  jmp     short loc_1808EF23F
0x1808ef235  mov     rax, 2000000000h
0x1808ef23f  or      [rbx+70h], rax
0x1808ef243  mov     rax, [rdi+60h]
0x1808ef247  test    rax, rax
0x1808ef24a  jz      loc_1808EF30B
0x1808ef250  mov     rax, [rax+140h]
0x1808ef257  test    rax, rax
0x1808ef25a  jz      loc_1808EF30B
0x1808ef260  mov     rax, [rax+10h]
0x1808ef264  test    rax, rax
0x1808ef267  jz      loc_1808EF30B
0x1808ef26d  cmp     qword ptr [rax+40h], 0
0x1808ef272  jz      loc_1808EF30B
0x1808ef278  test    byte ptr [rax+1304h], 80h
0x1808ef27f  jnz     loc_1808EF30B
0x1808ef285  xorps   xmm0, xmm0
0x1808ef288  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1808ef28d  xor     eax, eax
0x1808ef28f  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1808ef294  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1808ef299  call    cs:__imp_VariantInit
0x1808ef29f  mov     rax, [rdi+60h]
0x1808ef2a3  xor     r10d, r10d
0x1808ef2a6  mov     rcx, [rax+140h]
0x1808ef2ad  test    rcx, rcx
0x1808ef2b0  jz      short loc_1808EF2B6
0x1808ef2b2  mov     r10, [rcx+10h]
0x1808ef2b6  mov     rcx, [r10+40h]; struct IUnknown *
0x1808ef2ba  lea     rax, [rsp+88h+pvarg]
0x1808ef2bf  xor     r9d, r9d; unsigned int
0x1808ef2c2  mov     [rsp+88h+var_60], rax; struct tagVARIANT *
0x1808ef2c7  lea     rdx, CGID_Explorer; struct _GUID *
0x1808ef2ce  mov     [rsp+88h+var_68], 0; struct tagVARIANT *
0x1808ef2d7  lea     r8d, [r9+78h]; unsigned int
0x1808ef2db  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x1808ef2e0  test    eax, eax
0x1808ef2e2  js      short loc_1808EF30B
0x1808ef2e4  cmp     word ptr [rsp+88h+pvarg], 8
0x1808ef2ea  jnz     short loc_1808EF300
0x1808ef2ec  mov     rax, qword ptr [rsp+88h+pvarg+8]
0x1808ef2f1  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1808ef2f6  mov     [rbx+50h], rax
0x1808ef2fa  call    cs:__imp_VariantInit
0x1808ef300  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1808ef305  call    cs:__imp_VariantClear
0x1808ef30b  call    cs:__imp_GetCurrentProcessId
0x1808ef311  mov     ecx, 1
0x1808ef316  mov     [rbp+18h], eax
0x1808ef319  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1808ef31f  mov     ecx, 20000011h
0x1808ef324  mov     dword ptr [rbp+20h], 0
0x1808ef32b  and     eax, 7Fh
0x1808ef32e  mov     [rbp+1Ch], eax
0x1808ef331  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1808ef337  mov     [rbp+28h], eax
0x1808ef33a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808ef340  movups  xmm0, xmmword ptr [rax]
0x1808ef343  movdqu  xmmword ptr [rbp+34h], xmm0
0x1808ef348  call    cs:__imp_GetCurrentThreadId
0x1808ef34e  xor     r9d, r9d
0x1808ef351  mov     r8, rbp
0x1808ef354  mov     edx, eax
0x1808ef356  mov     ecx, 203h
0x1808ef35b  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1808ef361  mov     eax, [rsi+0Ch]
0x1808ef364  mov     [rbp+30h], eax
0x1808ef367  mov     [r15], r12d
0x1808ef36a  mov     eax, [rsi+8]
0x1808ef36d  mov     [r15+0Ch], eax
0x1808ef371  mov     dword ptr [r15+8], 2400000h
0x1808ef379  jmp     short loc_1808EF381
0x1808ef37b  mov     r14d, 8007000Eh
0x1808ef381  mov     eax, r14d
0x1808ef384  add     rsp, 50h
0x1808ef388  pop     r15
0x1808ef38a  pop     r14
0x1808ef38c  pop     r12
0x1808ef38e  pop     rdi
0x1808ef38f  pop     rsi
0x1808ef390  pop     rbp
0x1808ef391  pop     rbx
0x1808ef392  retn
```
