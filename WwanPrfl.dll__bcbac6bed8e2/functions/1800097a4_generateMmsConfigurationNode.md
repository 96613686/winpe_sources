# _generateMmsConfigurationNode

- ea: `0x1800097a4`
- end: `0x180009b29`
- name: `_generateMmsConfigurationNode`
- size: `901`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x1800097a4`
- `0x180011f90`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800098c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800099e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800098c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800099e8`
- `OLEAUT32!__imp_VariantClear` at `0x180009941`
- `OLEAUT32!__imp_VariantClear` at `0x1800099af`
- `OLEAUT32!__imp_VariantClear` at `0x1800099d0`
- `OLEAUT32!__imp_VariantClear` at `0x180009a68`
- `OLEAUT32!__imp_VariantClear` at `0x180009ad4`
- `OLEAUT32!__imp_VariantClear` at `0x180009af2`
- `OLEAUT32!__imp_VariantClear` at `0x180009941`
- `OLEAUT32!__imp_VariantClear` at `0x1800099af`
- `OLEAUT32!__imp_VariantClear` at `0x1800099d0`
- `OLEAUT32!__imp_VariantClear` at `0x180009a68`
- `OLEAUT32!__imp_VariantClear` at `0x180009ad4`
- `OLEAUT32!__imp_VariantClear` at `0x180009af2`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800098ee`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009906`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009926`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009931`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a15`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a2d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a4d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a58`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800098ee`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009906`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009926`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009931`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a15`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a2d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a4d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009a58`

## string_xrefs

- `0x1800097e6`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x1800097f7`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000985a`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009970`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009a92`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800097df`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009864`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000997a`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009a9c`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009817`: `MmsConfiguration`

## pseudocode

```c
__int64 __fastcall generateMmsConfigurationNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 result; // rax
  OLECHAR *v8; // r15
  OLECHAR *v9; // r9
  unsigned int v10; // edi
  struct IXMLDOMNode *v11; // rbx
  OLECHAR *v12; // r9
  OLECHAR *v13; // r9
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMNode *v15; // [rsp+90h] [rbp+40h] BYREF

  result = 0;
  if ( *(_WORD *)a3 || *(_DWORD *)(a3 + 516) )
  {
    v15 = 0;
    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    if ( a4 < 3 )
    {
      v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    v10 = XcAddChildElement(a1, a2, (OLECHAR *)L"MmsConfiguration", v9, 0, &v15);
    if ( v10 )
    {
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    }
    else
    {
      v11 = v15;
      if ( !*(_WORD *)a3 )
        goto LABEL_60;
      if ( a4 < 3 )
      {
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      v10 = XcAddChildElement(a1, v15, (OLECHAR *)L"MmscUrl", v12, (OLECHAR *)a3, 0);
      if ( !v10 )
      {
LABEL_60:
        if ( *(_DWORD *)(a3 + 512) )
        {
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = *(_DWORD *)(a3 + 512);
          if ( VariantChangeType(&pvarg, &pvarg, 0, 8u) < 0 )
          {
            v10 = (VariantChangeType(&pvarg, &pvarg, 0, 8u) & 0x1FFF0000) == 0x70000
                ? (unsigned __int16)VariantChangeType(&pvarg, &pvarg, 0, 8u)
                : VariantChangeType(&pvarg, &pvarg, 0, 8u);
            if ( v10 )
            {
              VariantClear(&pvarg);
              if ( v11 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
              return v10;
            }
          }
          if ( a4 < 3 )
          {
            v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          else
          {
            v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
          }
          v10 = XcAddChildElement(a1, v11, (OLECHAR *)L"MmscPort", v13, pvarg.bstrVal, 0);
          if ( v10 )
          {
            VariantClear(&pvarg);
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
            return v10;
          }
          VariantClear(&pvarg);
        }
        if ( *(_DWORD *)(a3 + 516) )
        {
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = *(_DWORD *)(a3 + 516);
          if ( VariantChangeType(&pvarg, &pvarg, 0, 8u) < 0 )
          {
            v10 = (VariantChangeType(&pvarg, &pvarg, 0, 8u) & 0x1FFF0000) == 0x70000
                ? (unsigned __int16)VariantChangeType(&pvarg, &pvarg, 0, 8u)
                : VariantChangeType(&pvarg, &pvarg, 0, 8u);
            if ( v10 )
            {
              VariantClear(&pvarg);
              if ( v11 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
              return v10;
            }
          }
          if ( a4 < 3 )
          {
            v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          v10 = XcAddChildElement(a1, v11, (OLECHAR *)L"MmsMaximumMessageSize", v8, pvarg.bstrVal, 0);
          if ( v10 )
          {
            VariantClear(&pvarg);
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
            return v10;
          }
          VariantClear(&pvarg);
        }
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        return v10;
      }
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800097a4  mov     [rsp-28h+arg_0], rbx
0x1800097a9  mov     [rsp-28h+arg_8], rsi
0x1800097ae  push    rbp
0x1800097af  push    rdi
0x1800097b0  push    r12
0x1800097b2  push    r14
0x1800097b4  push    r15
0x1800097b6  mov     rbp, rsp
0x1800097b9  sub     rsp, 50h
0x1800097bd  mov     esi, r9d
0x1800097c0  mov     r14, r8
0x1800097c3  mov     r12, rcx
0x1800097c6  xor     eax, eax
0x1800097c8  cmp     ax, [r8]
0x1800097cc  jnz     short loc_1800097DB
0x1800097ce  cmp     [r8+204h], eax
0x1800097d5  jz      loc_180009B10
0x1800097db  mov     [rbp+arg_10], rax
0x1800097df  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800097e6  lea     r15, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x1800097ed  cmp     esi, 3
0x1800097f0  jb      short loc_1800097F7
0x1800097f2  mov     r9, r15
0x1800097f5  jmp     short loc_180009805
0x1800097f7  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800097fe  cmp     esi, 2
0x180009801  cmovnz  r9, rax; OLECHAR *
0x180009805  lea     rax, [rbp+arg_10]
0x180009809  mov     [rsp+50h+var_28], rax; struct IXMLDOMNode **
0x18000980e  mov     [rsp+50h+var_30], 0; OLECHAR *
0x180009817  lea     r8, aMmsconfigurati; "MmsConfiguration"
0x18000981e  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009823  mov     edi, eax
0x180009825  test    eax, eax
0x180009827  jz      short loc_180009844
0x180009829  mov     rcx, [rbp+arg_10]
0x18000982d  test    rcx, rcx
0x180009830  jz      short loc_18000983F
0x180009832  mov     rdx, [rcx]
0x180009835  mov     rax, [rdx+10h]
0x180009839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983e  nop
0x18000983f  jmp     loc_180009B0E
0x180009844  xor     eax, eax
0x180009846  mov     rbx, [rbp+arg_10]
0x18000984a  cmp     ax, [r14]
0x18000984e  jz      short loc_1800098AF
0x180009850  cmp     esi, 3
0x180009853  jb      short loc_18000985A
0x180009855  mov     r9, r15
0x180009858  jmp     short loc_18000986F
0x18000985a  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009861  cmp     esi, 2
0x180009864  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000986b  cmovnz  r9, rax; OLECHAR *
0x18000986f  mov     [rsp+50h+var_28], 0; struct IXMLDOMNode **
0x180009878  mov     [rsp+50h+var_30], r14; OLECHAR *
0x18000987d  lea     r8, aMmscurl; "MmscUrl"
0x180009884  mov     rdx, rbx; struct IXMLDOMNode *
0x180009887  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18000988a  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000988f  mov     edi, eax
0x180009891  test    eax, eax
0x180009893  jz      short loc_1800098AF
0x180009895  test    rbx, rbx
0x180009898  jz      short loc_1800098AA
0x18000989a  mov     rax, [rbx]
0x18000989d  mov     rcx, rbx
0x1800098a0  mov     rax, [rax+10h]
0x1800098a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a9  nop
0x1800098aa  jmp     loc_180009B0E
0x1800098af  cmp     dword ptr [r14+200h], 0
0x1800098b7  jz      loc_1800099D6
0x1800098bd  lea     rcx, [rbp+pvarg]; pvarg
0x1800098c1  call    cs:__imp_VariantInit
0x1800098c7  nop
0x1800098c8  mov     eax, 3
0x1800098cd  mov     word ptr [rbp+pvarg], ax
0x1800098d1  mov     eax, [r14+200h]
0x1800098d8  mov     dword ptr [rbp+pvarg+8], eax
0x1800098db  mov     edi, 8
0x1800098e0  mov     r9d, edi; vt
0x1800098e3  xor     r8d, r8d; wFlags
0x1800098e6  lea     rdx, [rbp+pvarg]; pvarSrc
0x1800098ea  lea     rcx, [rbp+pvarg]; pvargDest
0x1800098ee  call    cs:__imp_VariantChangeType
0x1800098f4  test    eax, eax
0x1800098f6  jns     short loc_180009962
0x1800098f8  mov     r9d, edi; vt
0x1800098fb  xor     r8d, r8d; wFlags
0x1800098fe  lea     rdx, [rbp+pvarg]; pvarSrc
0x180009902  lea     rcx, [rbp+pvarg]; pvargDest
0x180009906  call    cs:__imp_VariantChangeType
0x18000990c  and     eax, 1FFF0000h
0x180009911  mov     r9d, edi; vt
0x180009914  xor     r8d, r8d; wFlags
0x180009917  lea     rdx, [rbp+pvarg]; pvarSrc
0x18000991b  lea     rcx, [rbp+pvarg]; pvargDest
0x18000991f  cmp     eax, 70000h
0x180009924  jnz     short loc_180009931
0x180009926  call    cs:__imp_VariantChangeType
0x18000992c  movzx   edi, ax
0x18000992f  jmp     short loc_180009939
0x180009931  call    cs:__imp_VariantChangeType
0x180009937  mov     edi, eax
0x180009939  test    edi, edi
0x18000993b  jz      short loc_180009962
0x18000993d  lea     rcx, [rbp+pvarg]; pvarg
0x180009941  call    cs:__imp_VariantClear
0x180009947  nop
0x180009948  test    rbx, rbx
0x18000994b  jz      short loc_18000995D
0x18000994d  mov     rax, [rbx]
0x180009950  mov     rcx, rbx
0x180009953  mov     rax, [rax+10h]
0x180009957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995c  nop
0x18000995d  jmp     loc_180009B0E
0x180009962  mov     rax, qword ptr [rbp+pvarg+8]
0x180009966  cmp     esi, 3
0x180009969  jb      short loc_180009970
0x18000996b  mov     r9, r15
0x18000996e  jmp     short loc_180009985
0x180009970  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009977  cmp     esi, 2
0x18000997a  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009981  cmovnz  r9, rcx; OLECHAR *
0x180009985  mov     [rsp+50h+var_28], 0; struct IXMLDOMNode **
0x18000998e  mov     [rsp+50h+var_30], rax; OLECHAR *
0x180009993  lea     r8, aMmscport; "MmscPort"
0x18000999a  mov     rdx, rbx; struct IXMLDOMNode *
0x18000999d  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800099a0  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800099a5  mov     edi, eax
0x1800099a7  lea     rcx, [rbp+pvarg]; pvarg
0x1800099ab  test    eax, eax
0x1800099ad  jz      short loc_1800099D0
0x1800099af  call    cs:__imp_VariantClear
0x1800099b5  nop
0x1800099b6  test    rbx, rbx
0x1800099b9  jz      short loc_1800099CB
0x1800099bb  mov     rax, [rbx]
0x1800099be  mov     rcx, rbx
0x1800099c1  mov     rax, [rax+10h]
0x1800099c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ca  nop
0x1800099cb  jmp     loc_180009B0E
0x1800099d0  call    cs:__imp_VariantClear
0x1800099d6  cmp     dword ptr [r14+204h], 0
0x1800099de  jz      loc_180009AF9
0x1800099e4  lea     rcx, [rbp+pvarg]; pvarg
0x1800099e8  call    cs:__imp_VariantInit
0x1800099ee  nop
0x1800099ef  mov     eax, 3
0x1800099f4  mov     word ptr [rbp+pvarg], ax
0x1800099f8  mov     eax, [r14+204h]
0x1800099ff  mov     dword ptr [rbp+pvarg+8], eax
0x180009a02  mov     edi, 8
0x180009a07  mov     r9d, edi; vt
0x180009a0a  xor     r8d, r8d; wFlags
0x180009a0d  lea     rdx, [rbp+pvarg]; pvarSrc
0x180009a11  lea     rcx, [rbp+pvarg]; pvargDest
0x180009a15  call    cs:__imp_VariantChangeType
0x180009a1b  test    eax, eax
0x180009a1d  jns     short loc_180009A89
0x180009a1f  mov     r9d, edi; vt
0x180009a22  xor     r8d, r8d; wFlags
0x180009a25  lea     rdx, [rbp+pvarg]; pvarSrc
0x180009a29  lea     rcx, [rbp+pvarg]; pvargDest
0x180009a2d  call    cs:__imp_VariantChangeType
0x180009a33  and     eax, 1FFF0000h
0x180009a38  mov     r9d, edi; vt
0x180009a3b  xor     r8d, r8d; wFlags
0x180009a3e  lea     rdx, [rbp+pvarg]; pvarSrc
0x180009a42  lea     rcx, [rbp+pvarg]; pvargDest
0x180009a46  cmp     eax, 70000h
0x180009a4b  jnz     short loc_180009A58
0x180009a4d  call    cs:__imp_VariantChangeType
0x180009a53  movzx   edi, ax
0x180009a56  jmp     short loc_180009A60
0x180009a58  call    cs:__imp_VariantChangeType
0x180009a5e  mov     edi, eax
0x180009a60  test    edi, edi
0x180009a62  jz      short loc_180009A89
0x180009a64  lea     rcx, [rbp+pvarg]; pvarg
0x180009a68  call    cs:__imp_VariantClear
0x180009a6e  nop
0x180009a6f  test    rbx, rbx
0x180009a72  jz      short loc_180009A84
0x180009a74  mov     rax, [rbx]
0x180009a77  mov     rcx, rbx
0x180009a7a  mov     rax, [rax+10h]
0x180009a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a83  nop
0x180009a84  jmp     loc_180009B0E
0x180009a89  mov     rax, qword ptr [rbp+pvarg+8]
0x180009a8d  cmp     esi, 3
0x180009a90  jnb     short loc_180009AA7
0x180009a92  lea     r15, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009a99  cmp     esi, 2
0x180009a9c  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009aa3  cmovnz  r15, rcx
0x180009aa7  mov     [rsp+50h+var_28], 0; struct IXMLDOMNode **
0x180009ab0  mov     [rsp+50h+var_30], rax; OLECHAR *
0x180009ab5  mov     r9, r15; OLECHAR *
0x180009ab8  lea     r8, aMmsmaximummess; "MmsMaximumMessageSize"
0x180009abf  mov     rdx, rbx; struct IXMLDOMNode *
0x180009ac2  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180009ac5  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009aca  mov     edi, eax
0x180009acc  lea     rcx, [rbp+pvarg]; pvarg
0x180009ad0  test    eax, eax
0x180009ad2  jz      short loc_180009AF2
0x180009ad4  call    cs:__imp_VariantClear
0x180009ada  nop
0x180009adb  test    rbx, rbx
0x180009ade  jz      short loc_180009AF0
0x180009ae0  mov     rax, [rbx]
0x180009ae3  mov     rcx, rbx
0x180009ae6  mov     rax, [rax+10h]
0x180009aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aef  nop
0x180009af0  jmp     short loc_180009B0E
0x180009af2  call    cs:__imp_VariantClear
0x180009af8  nop
0x180009af9  test    rbx, rbx
0x180009afc  jz      short loc_180009B0E
0x180009afe  mov     rax, [rbx]
0x180009b01  mov     rcx, rbx
0x180009b04  mov     rax, [rax+10h]
0x180009b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0d  nop
0x180009b0e  mov     eax, edi
0x180009b10  lea     r11, [rsp+50h+var_s0]
0x180009b15  mov     rbx, [r11+30h]
0x180009b19  mov     rsi, [r11+38h]
0x180009b1d  mov     rsp, r11
0x180009b20  pop     r15
0x180009b22  pop     r14
0x180009b24  pop     r12
0x180009b26  pop     rdi
0x180009b27  pop     rbp
0x180009b28  retn
```
