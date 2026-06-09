# FwLuidsToSafearray(_tag_FW_INTERFACE_LUIDS const *,tagVARIANT *)

- ea: `0x1800300c4`
- end: `0x18003031e`
- name: `?FwLuidsToSafearray@@YAJPEBU_tag_FW_INTERFACE_LUIDS@@PEAUtagVARIANT@@@Z`
- size: `602`
- prototype: `int(const struct _tag_FW_INTERFACE_LUIDS *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800210f0`
- `0x180037850`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x18002f8dc`
- `0x18002fec8`
- `0x1800300c4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180030213`
- `OLEAUT32!__imp_SysAllocString` at `0x180030213`
- `OLEAUT32!__imp_SysFreeString` at `0x180030245`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302da`
- `OLEAUT32!__imp_SysFreeString` at `0x180030245`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302da`
- `OLEAUT32!__imp_VariantInit` at `0x180030102`
- `OLEAUT32!__imp_VariantInit` at `0x1800301fd`
- `OLEAUT32!__imp_VariantInit` at `0x180030102`
- `OLEAUT32!__imp_VariantInit` at `0x1800301fd`
- `OLEAUT32!__imp_VariantClear` at `0x18003023c`
- `OLEAUT32!__imp_VariantClear` at `0x18003023c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003012f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003012f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800302f1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800302f1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18003022c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18003022c`
- `fwbase!FwBaseFree` at `0x1800302e4`
- `fwbase!FwBaseFree` at `0x1800302e4`

## pseudocode

```c
__int64 __fastcall FwLuidsToSafearray(ULONG *a1, struct tagVARIANT *a2)
{
  OLECHAR *v3; // rdi
  ULONG v5; // eax
  SAFEARRAY *v6; // r15
  int Adapters; // ebx
  FwPolicy2 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int i; // r14d
  BSTR v12; // rax
  HRESULT v13; // eax
  OLECHAR *psz; // [rsp+20h] [rbp-40h] BYREF
  struct _IP_ADAPTER_ADDRESSES_LH *v16; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-30h] BYREF
  LONG rgIndices; // [rsp+48h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF

  v16 = 0;
  v3 = 0;
  psz = 0;
  VariantInit(a2);
  v5 = *a1;
  if ( !*a1 )
  {
    v6 = 0;
    a2->vt = 0;
    Adapters = 0;
    goto LABEL_27;
  }
  rgsabound.lLbound = 0;
  rgsabound.cElements = v5;
  v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( v6 )
  {
    Adapters = FwGetAdapters(&v16);
    if ( Adapters >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *a1 )
        {
          a2->vt = 8204;
          a2->llVal = (LONGLONG)v6;
          goto LABEL_25;
        }
        if ( (int)FwLuidToInterfaceNameBstr(v16, (const struct _GUID *)(*((_QWORD *)a1 + 1) + 16LL * i), &psz) < 0 )
          break;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v3 = psz;
        pvarg.vt = 8;
        v12 = SysAllocString(psz);
        rgIndices = i;
        pvarg.llVal = (LONGLONG)v12;
        v13 = SafeArrayPutElement(v6, &rgIndices, &pvarg);
        Adapters = v13;
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids,
              (unsigned int)v13);
          goto LABEL_25;
        }
        VariantClear(&pvarg);
        SysFreeString(v3);
        v3 = 0;
        psz = 0;
      }
      Adapters = -2147418113;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, 2147549183LL);
      v3 = psz;
LABEL_25:
      if ( v3 )
        SysFreeString(v3);
    }
    else
    {
      v10 = 2147549183LL;
      Adapters = -2147418113;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 47;
        goto LABEL_7;
      }
    }
  }
  else
  {
    Adapters = -2147024882;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 46;
      v10 = 2147942414LL;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, v10);
    }
  }
LABEL_27:
  FwBaseFree(v16);
  if ( Adapters < 0 )
    SafeArrayDestroy(v6);
  return (unsigned int)Adapters;
}

```

## disassembly

```asm
0x1800300c4  mov     [rsp-28h+arg_10], rbx
0x1800300c9  mov     [rsp-28h+arg_18], rsi
0x1800300ce  push    rbp
0x1800300cf  push    rdi
0x1800300d0  push    r12
0x1800300d2  push    r14
0x1800300d4  push    r15
0x1800300d6  mov     rbp, rsp
0x1800300d9  sub     rsp, 60h
0x1800300dd  mov     rax, cs:__security_cookie
0x1800300e4  xor     rax, rsp
0x1800300e7  mov     [rbp+var_8], rax
0x1800300eb  mov     r12, rcx
0x1800300ee  mov     [rbp+var_38], 0
0x1800300f6  xor     edi, edi
0x1800300f8  mov     rcx, rdx; pvarg
0x1800300fb  mov     [rbp+psz], rdi
0x1800300ff  mov     rsi, rdx
0x180030102  call    cs:__imp_VariantInit
0x180030108  mov     eax, [r12]
0x18003010c  test    eax, eax
0x18003010e  jnz     short loc_18003011D
0x180030110  xor     r15d, r15d
0x180030113  mov     [rsi], ax
0x180030116  xor     ebx, ebx
0x180030118  jmp     loc_1800302E0
0x18003011d  mov     ecx, 0Ch; vt
0x180030122  mov     [rbp+rgsabound.lLbound], edi
0x180030125  lea     r8, [rbp+rgsabound]; rgsabound
0x180030129  mov     [rbp+rgsabound.cElements], eax
0x18003012c  lea     edx, [rcx-0Bh]; cDims
0x18003012f  call    cs:__imp_SafeArrayCreate
0x180030135  mov     r15, rax
0x180030138  test    rax, rax
0x18003013b  jnz     short loc_18003017E
0x18003013d  mov     ebx, 8007000Eh
0x180030142  mov     rcx, cs:WPP_GLOBAL_Control
0x180030149  lea     rdx, WPP_GLOBAL_Control
0x180030150  cmp     rcx, rdx
0x180030153  jz      loc_1800302E0
0x180030159  test    byte ptr [rcx+1Ch], 1
0x18003015d  jz      loc_1800302E0
0x180030163  lea     edx, [rax+2Eh]
0x180030166  mov     r9d, ebx
0x180030169  mov     rcx, [rcx+10h]
0x18003016d  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180030174  call    WPP_SF_d
0x180030179  jmp     loc_1800302E0
0x18003017e  lea     rcx, [rbp+var_38]; struct _IP_ADAPTER_ADDRESSES_LH **
0x180030182  call    ?FwGetAdapters@@YAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; FwGetAdapters(_IP_ADAPTER_ADDRESSES_LH * *)
0x180030187  mov     ebx, eax
0x180030189  test    eax, eax
0x18003018b  jns     short loc_1800301BE
0x18003018d  mov     r9d, 8000FFFFh
0x180030193  mov     ebx, r9d
0x180030196  mov     rcx, cs:WPP_GLOBAL_Control
0x18003019d  lea     rdx, WPP_GLOBAL_Control
0x1800301a4  cmp     rcx, rdx
0x1800301a7  jz      loc_1800302E0
0x1800301ad  test    byte ptr [rcx+1Ch], 1
0x1800301b1  jz      loc_1800302E0
0x1800301b7  mov     edx, 2Fh ; '/'
0x1800301bc  jmp     short loc_180030169
0x1800301be  xor     r14d, r14d
0x1800301c1  cmp     r14d, [r12]
0x1800301c5  jnb     loc_1800302C9
0x1800301cb  mov     rcx, [rbp+var_38]; struct _IP_ADAPTER_ADDRESSES_LH *
0x1800301cf  lea     r8, [rbp+psz]; unsigned __int16 **
0x1800301d3  mov     edx, r14d
0x1800301d6  shl     rdx, 4
0x1800301da  add     rdx, [r12+8]; struct _GUID *
0x1800301df  call    ?FwLuidToInterfaceNameBstr@@YAJPEAU_IP_ADAPTER_ADDRESSES_LH@@PEBU_GUID@@PEAPEAG@Z; FwLuidToInterfaceNameBstr(_IP_ADAPTER_ADDRESSES_LH *,_GUID const *,ushort * *)
0x1800301e4  test    eax, eax
0x1800301e6  js      loc_18003028C
0x1800301ec  xorps   xmm0, xmm0
0x1800301ef  lea     rcx, [rbp+pvarg]; pvarg
0x1800301f3  xor     eax, eax
0x1800301f5  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800301f9  mov     qword ptr [rbp+pvarg+10h], rax
0x1800301fd  call    cs:__imp_VariantInit
0x180030203  mov     rdi, [rbp+psz]
0x180030207  mov     eax, 8
0x18003020c  mov     rcx, rdi; psz
0x18003020f  mov     word ptr [rbp+pvarg], ax
0x180030213  call    cs:__imp_SysAllocString
0x180030219  lea     r8, [rbp+pvarg]; pv
0x18003021d  mov     [rbp+rgIndices], r14d
0x180030221  lea     rdx, [rbp+rgIndices]; rgIndices
0x180030225  mov     qword ptr [rbp+pvarg+8], rax
0x180030229  mov     rcx, r15; psa
0x18003022c  call    cs:__imp_SafeArrayPutElement
0x180030232  mov     ebx, eax
0x180030234  test    eax, eax
0x180030236  js      short loc_180030259
0x180030238  lea     rcx, [rbp+pvarg]; pvarg
0x18003023c  call    cs:__imp_VariantClear
0x180030242  mov     rcx, rdi; bstrString
0x180030245  call    cs:__imp_SysFreeString
0x18003024b  xor     edi, edi
0x18003024d  mov     [rbp+psz], rdi
0x180030251  inc     r14d
0x180030254  jmp     loc_1800301C1
0x180030259  mov     rcx, cs:WPP_GLOBAL_Control
0x180030260  lea     rdx, WPP_GLOBAL_Control
0x180030267  cmp     rcx, rdx
0x18003026a  jz      short loc_1800302D2
0x18003026c  test    byte ptr [rcx+1Ch], 1
0x180030270  jz      short loc_1800302D2
0x180030272  mov     rcx, [rcx+10h]
0x180030276  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18003027d  mov     edx, 31h ; '1'
0x180030282  mov     r9d, eax
0x180030285  call    WPP_SF_d
0x18003028a  jmp     short loc_1800302D2
0x18003028c  mov     r9d, 8000FFFFh
0x180030292  mov     ebx, r9d
0x180030295  mov     rcx, cs:WPP_GLOBAL_Control
0x18003029c  lea     rdx, WPP_GLOBAL_Control
0x1800302a3  cmp     rcx, rdx
0x1800302a6  jz      short loc_1800302C3
0x1800302a8  test    byte ptr [rcx+1Ch], 1
0x1800302ac  jz      short loc_1800302C3
0x1800302ae  mov     rcx, [rcx+10h]
0x1800302b2  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800302b9  mov     edx, 30h ; '0'
0x1800302be  call    WPP_SF_d
0x1800302c3  mov     rdi, [rbp+psz]
0x1800302c7  jmp     short loc_1800302D2
0x1800302c9  mov     word ptr [rsi], 200Ch
0x1800302ce  mov     [rsi+8], r15
0x1800302d2  test    rdi, rdi
0x1800302d5  jz      short loc_1800302E0
0x1800302d7  mov     rcx, rdi; bstrString
0x1800302da  call    cs:__imp_SysFreeString
0x1800302e0  mov     rcx, [rbp+var_38]
0x1800302e4  call    cs:__imp_FwBaseFree
0x1800302ea  test    ebx, ebx
0x1800302ec  jns     short loc_1800302F7
0x1800302ee  mov     rcx, r15; psa
0x1800302f1  call    cs:__imp_SafeArrayDestroy
0x1800302f7  mov     eax, ebx
0x1800302f9  mov     rcx, [rbp+var_8]
0x1800302fd  xor     rcx, rsp; StackCookie
0x180030300  call    __security_check_cookie
0x180030305  lea     r11, [rsp+60h+var_s0]
0x18003030a  mov     rbx, [r11+40h]
0x18003030e  mov     rsi, [r11+48h]
0x180030312  mov     rsp, r11
0x180030315  pop     r15
0x180030317  pop     r14
0x180030319  pop     r12
0x18003031b  pop     rdi
0x18003031c  pop     rbp
0x18003031d  retn
```
