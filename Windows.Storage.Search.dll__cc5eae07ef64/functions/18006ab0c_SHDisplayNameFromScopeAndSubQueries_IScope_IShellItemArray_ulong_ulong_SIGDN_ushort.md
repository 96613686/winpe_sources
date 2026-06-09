# SHDisplayNameFromScopeAndSubQueries(IScope *,IShellItemArray *,ulong,ulong,_SIGDN,ushort * *)

- ea: `0x18006ab0c`
- end: `0x18006aebb`
- name: `?SHDisplayNameFromScopeAndSubQueries@@YAJPEAUIScope@@PEAUIShellItemArray@@KKW4_SIGDN@@PEAPEAG@Z`
- size: `943`
- prototype: `__int64 __fastcall(struct IScope *, struct IShellItemArray *, unsigned int, unsigned int, enum _SIGDN, LPWSTR *ppwsz)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e1c0`
- `0x1800bd860`

## callees

- `0x180014ae0`
- `0x18003b150`
- `0x18003b1b0`
- `0x180040020`
- `0x180047ae0`
- `0x18004c300`
- `0x18004d340`
- `0x18005c494`
- `0x18006ab0c`
- `0x180079be4`
- `0x18007ae34`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x18006ae4f`
- `SHCORE!SHStrDupW` at `0x18006ae4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ada9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ada9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ae5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ae5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SHDisplayNameFromScopeAndSubQueries(
        struct IScope *a1,
        struct IShellItemArray *a2,
        unsigned int a3,
        unsigned int a4,
        enum _SIGDN a5,
        LPWSTR *ppwsz)
{
  __int64 v8; // rcx
  struct _DPA *v9; // rbx
  unsigned __int64 v10; // r13
  int appended; // edi
  WCHAR *v12; // r12
  unsigned int v13; // r14d
  struct IUnknown *v14; // rdx
  __int64 v15; // r8
  unsigned int i; // esi
  enum _SIGDN v17; // edx
  int v18; // esi
  int v19; // r14d
  unsigned int v20; // r15d
  const WCHAR *Ptr; // rax
  const unsigned __int16 *v22; // rdx
  HRESULT v23; // eax
  LPVOID pv; // [rsp+48h] [rbp-49h] BYREF
  struct IScopeItem *v26; // [rsp+50h] [rbp-41h] BYREF
  LPCWSTR psz; // [rsp+58h] [rbp-39h] BYREF
  HDPA hdpa[2]; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp-21h] BYREF
  unsigned __int64 v30; // [rsp+78h] [rbp-19h] BYREF
  struct _tagpropertykey v31; // [rsp+88h] [rbp-9h] BYREF
  unsigned int v32; // [rsp+F8h] [rbp+67h] BYREF
  unsigned int v33; // [rsp+100h] [rbp+6Fh]

  v33 = a4;
  v32 = a3;
  v9 = g_pfn_DPA_Create(5);
  hdpa[0] = v9;
  if ( v9 )
  {
    psz = 0;
    v10 = 260;
    appended = _AllocArray<unsigned short,CTLocalAllocPolicy>(v8, 64, 260, &psz);
    if ( appended < 0 )
    {
LABEL_40:
      CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::DestroyCallback(
        hdpa,
        DPA_ILFreeCB<_ITEMIDLIST_ABSOLUTE>);
      v9 = hdpa[0];
      goto LABEL_42;
    }
    v12 = (WCHAR *)psz;
    v29 = (unsigned __int16 *)psz;
    v30 = 260;
    if ( a2 )
    {
      v32 = 0;
      appended = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v32);
      v13 = 0;
      if ( v32 )
      {
        while ( appended >= 0 )
        {
          v26 = 0;
          appended = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IScopeItem **))a2->lpVtbl->GetItemAt)(
                       a2,
                       v13,
                       &v26);
          if ( appended >= 0 )
          {
            pv = 0;
            appended = (*(__int64 (__fastcall **)(struct IScopeItem *, __int64, LPVOID *))(*(_QWORD *)v26 + 40LL))(
                         v26,
                         2147844096LL,
                         &pv);
            if ( appended >= 0 )
            {
              a5 = 4;
              if ( (int)SHMapUrlToZone((const unsigned __int16 *)pv, v14, v15, (unsigned int *)&a5) < 0
                || a5
                || (CoTaskMemFree(pv),
                    appended = (*(__int64 (__fastcall **)(struct IScopeItem *, _QWORD, LPVOID *))(*(_QWORD *)v26 + 40LL))(
                                 v26,
                                 0,
                                 &pv),
                    appended >= 0) )
              {
                appended = CDPA_Base<IScopeItem,CTContainer_PolicyUnOwned<IScopeItem>>::AppendPtr(hdpa, pv);
                if ( appended < 0 )
                  CoTaskMemFree(pv);
              }
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( ++v13 >= v32 )
            goto LABEL_15;
        }
LABEL_29:
        v18 = 0;
        v19 = 0;
        v20 = v33;
        while ( v18 < *(_DWORD *)v9 )
        {
          Ptr = (const WCHAR *)g_pfn_DPA_GetPtr(v9, v18);
          appended = _AppendNext(Ptr, v22, v29, v10, v19, v20, &v29, &v30);
          if ( appended >= 0 )
            v19 = 1;
          ++v18;
          v10 = v30;
        }
        if ( appended == -2147024774 )
        {
          appended = 1;
        }
        else if ( appended < 0 )
        {
LABEL_39:
          LocalFree(v12);
          goto LABEL_40;
        }
        v23 = SHStrDupW(v12, ppwsz);
        if ( v23 < 0 )
          appended = v23;
        goto LABEL_39;
      }
LABEL_15:
      if ( appended < 0 )
        goto LABEL_29;
    }
    if ( a1 )
    {
      pv = 0;
      appended = (*(__int64 (__fastcall **)(struct IScope *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)a1 + 64LL))(
                   a1,
                   0,
                   &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                   &pv);
      if ( appended >= 0 )
      {
        v32 = 0;
        appended = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)pv + 24LL))(pv, &v32);
        for ( i = 0; appended >= 0; ++i )
        {
          if ( i >= v32 )
            break;
          v26 = 0;
          appended = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IScopeItem **))(*(_QWORD *)pv + 32LL))(
                       pv,
                       i,
                       &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                       &v26);
          if ( appended >= 0 )
          {
            a5 = SIGDN_NORMALDISPLAY;
            appended = (*(__int64 (__fastcall **)(struct IScopeItem *, enum _SIGDN *))(*(_QWORD *)v26 + 32LL))(v26, &a5);
            if ( appended >= 0 && a5 == 1 )
            {
              psz = 0;
              memset(&v31, 0, sizeof(v31));
              appended = _GetScopeItemName(v26, v17, &v31, (unsigned __int16 **)&psz);
              if ( appended >= 0 )
              {
                appended = CDPA_Base<IScopeItem,CTContainer_PolicyUnOwned<IScopeItem>>::AppendPtr(hdpa, psz);
                if ( appended < 0 )
                  CoTaskMemFree((LPVOID)psz);
              }
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v26 + 16LL))(v26);
          }
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
    }
    goto LABEL_29;
  }
  appended = -2147024882;
LABEL_42:
  if ( v9 )
  {
    g_pfn_DPA_DestroyCallback(v9, CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::_StandardDestroyCB, 0);
    DPA_Destroy(0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18006ab0c  mov     rax, rsp
0x18006ab0f  mov     [rax+8], rbx
0x18006ab13  mov     [rax+20h], r9d
0x18006ab17  mov     [rax+18h], r8d
0x18006ab1b  push    rbp
0x18006ab1c  push    rsi
0x18006ab1d  push    rdi
0x18006ab1e  push    r12
0x18006ab20  push    r13
0x18006ab22  push    r14
0x18006ab24  push    r15
0x18006ab26  lea     rbp, [rax-4Fh]
0x18006ab2a  sub     rsp, 0A0h
0x18006ab31  mov     rsi, rdx
0x18006ab34  mov     r15, rcx
0x18006ab37  mov     ecx, 5; cItemGrow
0x18006ab3c  call    cs:g_pfn_DPA_Create
0x18006ab42  mov     rbx, rax
0x18006ab45  mov     [rbp+47h+hdpa], rax
0x18006ab49  test    rax, rax
0x18006ab4c  jz      loc_18006AE79
0x18006ab52  mov     [rbp+47h+psz], 0
0x18006ab5a  lea     r9, [rbp+47h+psz]
0x18006ab5e  mov     r13d, 104h
0x18006ab64  mov     r8d, r13d
0x18006ab67  mov     edx, 40h ; '@'
0x18006ab6c  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18006ab71  mov     edi, eax
0x18006ab73  test    eax, eax
0x18006ab75  js      loc_18006AE63
0x18006ab7b  mov     r12, [rbp+47h+psz]
0x18006ab7f  mov     [rbp+47h+var_68], r12
0x18006ab83  mov     [rbp+47h+var_60], r13
0x18006ab87  mov     r14d, 1
0x18006ab8d  test    rsi, rsi
0x18006ab90  jz      loc_18006ACA2
0x18006ab96  mov     [rbp+47h+arg_10], 0
0x18006ab9d  mov     rax, [rsi]
0x18006aba0  lea     rdx, [rbp+47h+arg_10]
0x18006aba4  mov     rcx, rsi
0x18006aba7  mov     rax, [rax+38h]
0x18006abab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abb0  mov     edi, eax
0x18006abb2  xor     r14d, r14d
0x18006abb5  cmp     [rbp+47h+arg_10], r14d
0x18006abb9  jbe     loc_18006AC94
0x18006abbf  test    edi, edi
0x18006abc1  js      loc_18006ADDA
0x18006abc7  mov     [rbp+47h+var_88], 0
0x18006abcf  mov     rax, [rsi]
0x18006abd2  lea     r8, [rbp+47h+var_88]
0x18006abd6  mov     edx, r14d
0x18006abd9  mov     rcx, rsi
0x18006abdc  mov     rax, [rax+40h]
0x18006abe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abe5  mov     edi, eax
0x18006abe7  test    eax, eax
0x18006abe9  js      loc_18006AC87
0x18006abef  mov     [rbp+47h+pv], 0
0x18006abf7  mov     rcx, [rbp+47h+var_88]
0x18006abfb  mov     rax, [rcx]
0x18006abfe  lea     r8, [rbp+47h+pv]
0x18006ac02  mov     edx, 80058000h
0x18006ac07  mov     rax, [rax+28h]
0x18006ac0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac10  mov     edi, eax
0x18006ac12  test    eax, eax
0x18006ac14  js      short loc_18006AC77
0x18006ac16  mov     [rbp+47h+arg_20], 4
0x18006ac1d  lea     r9, [rbp+47h+arg_20]; unsigned int *
0x18006ac21  mov     rcx, [rbp+47h+pv]; unsigned __int16 *
0x18006ac25  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x18006ac2a  test    eax, eax
0x18006ac2c  js      short loc_18006AC5A
0x18006ac2e  cmp     [rbp+47h+arg_20], 0
0x18006ac32  jnz     short loc_18006AC5A
0x18006ac34  mov     rcx, [rbp+47h+pv]; pv
0x18006ac38  call    cs:__imp_CoTaskMemFree
0x18006ac3e  mov     rcx, [rbp+47h+var_88]
0x18006ac42  mov     rax, [rcx]
0x18006ac45  lea     r8, [rbp+47h+pv]
0x18006ac49  xor     edx, edx
0x18006ac4b  mov     rax, [rax+28h]
0x18006ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac54  mov     edi, eax
0x18006ac56  test    eax, eax
0x18006ac58  js      short loc_18006AC77
0x18006ac5a  mov     rdx, [rbp+47h+pv]
0x18006ac5e  lea     rcx, [rbp+47h+hdpa]
0x18006ac62  call    ?AppendPtr@?$CDPA_Base@UIScopeItem@@V?$CTContainer_PolicyUnOwned@UIScopeItem@@@@@@QEAAJPEAUIScopeItem@@PEAH@Z; CDPA_Base<IScopeItem,CTContainer_PolicyUnOwned<IScopeItem>>::AppendPtr(IScopeItem *,int *)
0x18006ac67  mov     edi, eax
0x18006ac69  test    eax, eax
0x18006ac6b  jns     short loc_18006AC77
0x18006ac6d  mov     rcx, [rbp+47h+pv]; pv
0x18006ac71  call    cs:__imp_CoTaskMemFree
0x18006ac77  mov     rcx, [rbp+47h+var_88]
0x18006ac7b  mov     rax, [rcx]
0x18006ac7e  mov     rax, [rax+10h]
0x18006ac82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac87  inc     r14d
0x18006ac8a  cmp     r14d, [rbp+47h+arg_10]
0x18006ac8e  jb      loc_18006ABBF
0x18006ac94  test    edi, edi
0x18006ac96  js      loc_18006ADDA
0x18006ac9c  mov     r14d, 1
0x18006aca2  test    r15, r15
0x18006aca5  jz      loc_18006ADDA
0x18006acab  mov     [rbp+47h+pv], 0
0x18006acb3  mov     rax, [r15]
0x18006acb6  lea     r9, [rbp+47h+pv]
0x18006acba  lea     r8, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x18006acc1  xor     edx, edx
0x18006acc3  mov     rcx, r15
0x18006acc6  mov     rax, [rax+40h]
0x18006acca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006accf  mov     edi, eax
0x18006acd1  test    eax, eax
0x18006acd3  js      loc_18006ADDA
0x18006acd9  mov     [rbp+47h+arg_10], 0
0x18006ace0  mov     rcx, [rbp+47h+pv]
0x18006ace4  mov     rax, [rcx]
0x18006ace7  lea     rdx, [rbp+47h+arg_10]
0x18006aceb  mov     rax, [rax+18h]
0x18006acef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acf4  mov     edi, eax
0x18006acf6  xor     esi, esi
0x18006acf8  test    eax, eax
0x18006acfa  js      loc_18006ADCA
0x18006ad00  cmp     esi, [rbp+47h+arg_10]
0x18006ad03  jnb     loc_18006ADCA
0x18006ad09  mov     [rbp+47h+var_88], 0
0x18006ad11  mov     rcx, [rbp+47h+pv]
0x18006ad15  mov     rax, [rcx]
0x18006ad18  lea     r9, [rbp+47h+var_88]
0x18006ad1c  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18006ad23  mov     edx, esi
0x18006ad25  mov     rax, [rax+20h]
0x18006ad29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad2e  mov     edi, eax
0x18006ad30  test    eax, eax
0x18006ad32  js      loc_18006ADBF
0x18006ad38  mov     [rbp+47h+arg_20], 0
0x18006ad3f  mov     rcx, [rbp+47h+var_88]
0x18006ad43  mov     rax, [rcx]
0x18006ad46  lea     rdx, [rbp+47h+arg_20]
0x18006ad4a  mov     rax, [rax+20h]
0x18006ad4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad53  mov     edi, eax
0x18006ad55  test    eax, eax
0x18006ad57  js      short loc_18006ADAF
0x18006ad59  cmp     [rbp+47h+arg_20], r14d
0x18006ad5d  jnz     short loc_18006ADAF
0x18006ad5f  mov     [rbp+47h+psz], 0
0x18006ad67  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18006ad6e  movaps  xmmword ptr [rbp+47h+var_50.fmtid.Data1], xmm0
0x18006ad72  mov     eax, cs:PKEY_Null.pid
0x18006ad78  mov     [rbp+47h+var_50.pid], eax
0x18006ad7b  lea     r9, [rbp+47h+psz]; unsigned __int16 **
0x18006ad7f  lea     r8, [rbp+47h+var_50]; struct _tagpropertykey
0x18006ad83  mov     rcx, [rbp+47h+var_88]; struct IScopeItem *
0x18006ad87  call    ?_GetScopeItemName@@YAJPEAUIScopeItem@@W4_SIGDN@@U_tagpropertykey@@PEAPEAG@Z; _GetScopeItemName(IScopeItem *,_SIGDN,_tagpropertykey,ushort * *)
0x18006ad8c  mov     edi, eax
0x18006ad8e  test    eax, eax
0x18006ad90  js      short loc_18006ADAF
0x18006ad92  mov     rdx, [rbp+47h+psz]
0x18006ad96  lea     rcx, [rbp+47h+hdpa]
0x18006ad9a  call    ?AppendPtr@?$CDPA_Base@UIScopeItem@@V?$CTContainer_PolicyUnOwned@UIScopeItem@@@@@@QEAAJPEAUIScopeItem@@PEAH@Z; CDPA_Base<IScopeItem,CTContainer_PolicyUnOwned<IScopeItem>>::AppendPtr(IScopeItem *,int *)
0x18006ad9f  mov     edi, eax
0x18006ada1  test    eax, eax
0x18006ada3  jns     short loc_18006ADAF
0x18006ada5  mov     rcx, [rbp+47h+psz]; pv
0x18006ada9  call    cs:__imp_CoTaskMemFree
0x18006adaf  mov     rcx, [rbp+47h+var_88]
0x18006adb3  mov     rax, [rcx]
0x18006adb6  mov     rax, [rax+10h]
0x18006adba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adbf  add     esi, r14d
0x18006adc2  test    edi, edi
0x18006adc4  jns     loc_18006AD00
0x18006adca  mov     rcx, [rbp+47h+pv]
0x18006adce  mov     rax, [rcx]
0x18006add1  mov     rax, [rax+10h]
0x18006add5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adda  xor     esi, esi
0x18006addc  mov     r14d, esi
0x18006addf  mov     r15d, [rbp+47h+arg_18]
0x18006ade3  lea     ecx, [rsi+1]
0x18006ade6  mov     eax, edi
0x18006ade8  cmp     esi, [rbx]
0x18006adea  jge     short loc_18006AE38
0x18006adec  movsxd  rdx, esi; i
0x18006adef  mov     rcx, rbx; hdpa
0x18006adf2  call    cs:g_pfn_DPA_GetPtr
0x18006adf8  lea     rcx, [rbp+47h+var_60]
0x18006adfc  mov     [rsp+38h], rcx; unsigned __int64 *
0x18006ae01  lea     rcx, [rbp+47h+var_68]
0x18006ae05  mov     [rsp+0D0h+var_A0], rcx; unsigned __int16 **
0x18006ae0a  mov     [rsp+0D0h+var_A8], r15d; unsigned int
0x18006ae0f  mov     [rsp+0D0h+var_B0], r14d; int
0x18006ae14  mov     r9, r13; unsigned __int64
0x18006ae17  mov     r8, [rbp+47h+var_68]; unsigned __int16 *
0x18006ae1b  mov     rcx, rax; pszSrc
0x18006ae1e  call    ?_AppendNext@@YAJPEBG0PEAG_KHKPEAPEAGPEA_K@Z; _AppendNext(ushort const *,ushort const *,ushort *,unsigned __int64,int,ulong,ushort * *,unsigned __int64 *)
0x18006ae23  mov     edi, eax
0x18006ae25  test    eax, eax
0x18006ae27  mov     ecx, 1
0x18006ae2c  cmovns  r14d, ecx
0x18006ae30  add     esi, ecx
0x18006ae32  mov     r13, [rbp+47h+var_60]
0x18006ae36  jmp     short loc_18006ADE6
0x18006ae38  cmp     edi, 8007007Ah
0x18006ae3e  jnz     short loc_18006AE44
0x18006ae40  mov     edi, ecx
0x18006ae42  jmp     short loc_18006AE48
0x18006ae44  test    eax, eax
0x18006ae46  js      short loc_18006AE5A
0x18006ae48  mov     rdx, [rbp+47h+ppwsz]; ppwsz
0x18006ae4c  mov     rcx, r12; psz
0x18006ae4f  call    cs:__imp_SHStrDupW
0x18006ae55  test    eax, eax
0x18006ae57  cmovs   edi, eax
0x18006ae5a  mov     rcx, r12; hMem
0x18006ae5d  call    cs:__imp_LocalFree
0x18006ae63  lea     rdx, ??$DPA_ILFreeCB@U_ITEMIDLIST_ABSOLUTE@@@@YAHPEAU_ITEMIDLIST_ABSOLUTE@@PEAX@Z; DPA_ILFreeCB<_ITEMIDLIST_ABSOLUTE>(_ITEMIDLIST_ABSOLUTE *,void *)
0x18006ae6a  lea     rcx, [rbp+47h+hdpa]
0x18006ae6e  call    ?DestroyCallback@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAXP6AHPEAGPEAX@Z1@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::DestroyCallback(int (*)(ushort *,void *),void *)
0x18006ae73  mov     rbx, [rbp+47h+hdpa]
0x18006ae77  jmp     short loc_18006AE7E
0x18006ae79  mov     edi, 8007000Eh
0x18006ae7e  test    rbx, rbx
0x18006ae81  jz      short loc_18006AE9E
0x18006ae83  xor     r8d, r8d; pData
0x18006ae86  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@VCIDLNode@@V?$CTContainer_PolicyUnOwned@VCIDLNode@@@@@@CAHPEAVCIDLNode@@PEAX@Z; pfnCB
0x18006ae8d  mov     rcx, rbx; hdpa
0x18006ae90  call    cs:g_pfn_DPA_DestroyCallback
0x18006ae96  xor     ecx, ecx; hdpa
0x18006ae98  call    cs:__imp_DPA_Destroy
0x18006ae9e  mov     eax, edi
0x18006aea0  mov     rbx, [rsp+0D0h+arg_0]
0x18006aea8  add     rsp, 0A0h
0x18006aeaf  pop     r15
0x18006aeb1  pop     r14
0x18006aeb3  pop     r13
0x18006aeb5  pop     r12
0x18006aeb7  pop     rdi
0x18006aeb8  pop     rsi
0x18006aeb9  pop     rbp
0x18006aeba  retn
```
