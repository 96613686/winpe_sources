# CAdapter::ValidateAndAddUnicastAuthCipherPairs(_WIFI_STATION_CAPABILITIES const &,_WDI_STATION_ATTRIBUTES_CONTAINER &,DOT11_EXTSTA_ATTRIBUTES *)

- ea: `0x140058f40`
- end: `0x140059270`
- name: `?ValidateAndAddUnicastAuthCipherPairs@CAdapter@@QEAAJAEBU_WIFI_STATION_CAPABILITIES@@AEAU_WDI_STATION_ATTRIBUTES_CONTAINER@@PEAUDOT11_EXTSTA_ATTRIBUTES@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, const struct _WIFI_STATION_CAPABILITIES *, struct _WDI_STATION_ATTRIBUTES_CONTAINER *, struct DOT11_EXTSTA_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140027b68`

## callees

- `0x140001008`
- `0x1400010dc`
- `0x140009420`
- `0x14000c778`
- `0x140054348`
- `0x140058f40`
- `0x14005a3f8`
- `0x140074224`
- `0x1400742b4`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14005925f`
- `ntoskrnl!DbgPrintEx` at `0x14005925f`

## string_xrefs

- `0x14005922f`: `[WIFICX] Driver reported incompatible auth = 0x%x, cipher = 0x%x for IHV Driver version %d.%d.%d.%d - skipping it\n`

## pseudocode

```c
__int64 __fastcall CAdapter::ValidateAndAddUnicastAuthCipherPairs(
        CAdapter *this,
        const struct _WIFI_STATION_CAPABILITIES *a2,
        struct _WDI_STATION_ATTRIBUTES_CONTAINER *a3,
        struct DOT11_EXTSTA_ATTRIBUTES *a4)
{
  __int64 v6; // rdx
  int v7; // edx
  unsigned int Elements; // edi
  struct DOT11_AUTH_CIPHER_PAIR *v10; // rax
  int v11; // edx
  __int64 v12; // r14
  __int64 v13; // r13
  unsigned int v14; // edx
  __int64 v15; // rdi
  __int64 v16; // r8
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r10
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // eax
  int v24; // r9d
  __int64 v25; // r10
  struct _WDI_STATION_ATTRIBUTES_CONTAINER *v26; // rax
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  int v30; // [rsp+28h] [rbp-49h]
  unsigned int *v31; // [rsp+68h] [rbp-9h] BYREF
  __int16 v32; // [rsp+70h] [rbp-1h]
  __int64 v33; // [rsp+78h] [rbp+7h] BYREF
  __int16 v34; // [rsp+80h] [rbp+Fh]
  __int64 v35; // [rsp+88h] [rbp+17h] BYREF
  __int16 v36; // [rsp+90h] [rbp+1Fh]
  CAdapter *v37; // [rsp+D8h] [rbp+67h]
  unsigned int v38; // [rsp+E0h] [rbp+6Fh] BYREF
  struct _WDI_STATION_ATTRIBUTES_CONTAINER *v39; // [rsp+E8h] [rbp+77h]

  v39 = a3;
  v37 = this;
  *((_DWORD *)a3 + 16) = 0;
  a4->uInfraNumSupportedUcastAlgoPairs = 0;
  a4->pInfraSupportedUcastAlgoPairs = 0;
  v6 = *((unsigned int *)a2 + 14);
  if ( (_DWORD)v6 )
  {
    Elements = ArrayOfElements<_WDI_ALGO_PAIRS>::AllocateElements((char *)a3 + 64, v6, 0);
    if ( Elements )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          1,
          189,
          (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
          *((_DWORD *)a2 + 14));
      }
      return Elements;
    }
    v10 = (struct DOT11_AUTH_CIPHER_PAIR *)operator new(saturated_mul(*((unsigned int *)a2 + 14), 8u));
    a4->pInfraSupportedUcastAlgoPairs = v10;
    if ( !v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          190,
          (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
          *((_DWORD *)a2 + 14));
      }
      return 3221225626LL;
    }
    this = v37;
  }
  v12 = 0;
  if ( *((_DWORD *)a2 + 14) )
  {
    v13 = 0;
    do
    {
      v14 = *((_DWORD *)this + 1348);
      v15 = 8 * v13;
      if ( v14 >= 0x2000C )
      {
LABEL_18:
        v18 = CDot11ToWabiConverter::MapCipherAlgorithm(*(unsigned int *)(*((_QWORD *)a2 + 8) + v15 + 4));
        *(_DWORD *)(*(_QWORD *)(v19 + 72) + 8 * v12 + 4) = v18;
        v23 = CDot11ToWabiConverter::MapAuthAlgorithm(*(unsigned int *)(*((_QWORD *)a2 + 8) + 8 * v13), v20, v21, v22);
        *(_DWORD *)(*(_QWORD *)(v25 + 72) + 8 * v12) = v23;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_ddDDDD(
            WPP_GLOBAL_Control->DeviceExtension,
            *((_QWORD *)a2 + 8),
            v13 + 1,
            v24,
            v30,
            v13 + 1,
            *((_DWORD *)a2 + 14),
            *(_DWORD *)(*((_QWORD *)a2 + 8) + 8 * v13),
            *(_DWORD *)(*((_QWORD *)a2 + 8) + 8 * v13 + 4),
            *(_DWORD *)(*(_QWORD *)(v25 + 72) + 8 * v12),
            *(_DWORD *)(*(_QWORD *)(v25 + 72) + 8 * v12 + 4));
        a4->pInfraSupportedUcastAlgoPairs[v12] = *(struct DOT11_AUTH_CIPHER_PAIR *)(v15 + *((_QWORD *)a2 + 8));
        v12 = (unsigned int)(v12 + 1);
      }
      else
      {
        v16 = *((_QWORD *)a2 + 8);
        v17 = 0;
        while ( *(_DWORD *)(v15 + v16) != LODWORD((&g_WiFi7Networks)[v17])
             || *(_DWORD *)(v15 + v16 + 4) != HIDWORD((&g_WiFi7Networks)[v17]) )
        {
          v17 = (unsigned int)(v17 + 1);
          if ( (unsigned int)v17 >= 3 )
            goto LABEL_18;
        }
        v38 = v14;
        if ( (unsigned int)dword_14010EC48 > 3 && (unsigned __int8)tlgKeywordOn(&dword_14010EC48, 5) )
        {
          v29 = *((_QWORD *)a2 + 8);
          v31 = &v38;
          v32 = 4;
          v34 = 4;
          v35 = v15 + v29;
          v36 = 4;
          v33 = v15 + v29 + 4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
            v15 + v29,
            (unsigned int)&unk_140104258,
            v27,
            v28,
            (__int64)&v35,
            (__int64)&v33,
            (__int64)&v31);
        }
        DbgPrintEx(
          0x65u,
          0,
          "[WIFICX] Driver reported incompatible auth = 0x%x, cipher = 0x%x for IHV Driver version %d.%d.%d.%d - skipping it\n",
          *(_DWORD *)(*((_QWORD *)a2 + 8) + 8 * v13),
          *(_DWORD *)(*((_QWORD *)a2 + 8) + 8 * v13 + 4),
          HIBYTE(v38),
          BYTE2(v38),
          BYTE1(v38),
          (unsigned __int8)v38);
      }
      this = v37;
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < *((_DWORD *)a2 + 14) );
  }
  v26 = v39;
  a4->uInfraNumSupportedUcastAlgoPairs = v12;
  *((_DWORD *)v26 + 16) = v12;
  return 0;
}

```

## disassembly

```asm
0x140058f40  mov     rax, rsp
0x140058f43  mov     [rax+20h], rbx
0x140058f47  mov     [rax+18h], r8
0x140058f4b  mov     [rax+8], rcx
0x140058f4f  push    rbp
0x140058f50  push    rsi
0x140058f51  push    rdi
0x140058f52  push    r12
0x140058f54  push    r13
0x140058f56  push    r14
0x140058f58  push    r15
0x140058f5a  lea     rbp, [rax-5Fh]
0x140058f5e  sub     rsp, 90h
0x140058f65  mov     dword ptr [r8+40h], 0
0x140058f6d  mov     rbx, rdx
0x140058f70  mov     dword ptr [r9+40h], 0
0x140058f78  mov     r15, r9
0x140058f7b  mov     qword ptr [r9+48h], 0
0x140058f83  mov     r10, r8
0x140058f86  mov     edx, [rdx+38h]
0x140058f89  test    edx, edx
0x140058f8b  jz      loc_140059065
0x140058f91  xor     r8d, r8d
0x140058f94  lea     rcx, [r10+40h]
0x140058f98  call    ?AllocateElements@?$ArrayOfElements@U_WDI_ALGO_PAIRS@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_ALGO_PAIRS>::AllocateElements(uint,unsigned __int64)
0x140058f9d  mov     edi, eax
0x140058f9f  test    eax, eax
0x140058fa1  jz      short loc_140058FEB
0x140058fa3  lea     rsi, WPP_RECORDER_INITIALIZED
0x140058faa  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140058fb1  jz      short loc_140058FE4
0x140058fb3  mov     ecx, [rbx+38h]
0x140058fb6  mov     r9d, 0BDh
0x140058fbc  mov     dword ptr [rsp+0C0h+var_98], ecx
0x140058fc0  mov     r8d, 1
0x140058fc6  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140058fcd  mov     dl, 2
0x140058fcf  mov     [rsp+0C0h+var_A0], rcx
0x140058fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140058fdb  mov     rcx, [rcx+40h]
0x140058fdf  call    WPP_RECORDER_SF_d
0x140058fe4  mov     eax, edi
0x140058fe6  jmp     loc_140059182
0x140058feb  mov     ecx, [rbx+38h]
0x140058fee  mov     eax, 8
0x140058ff3  mul     rcx
0x140058ff6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140058ffd  cmovb   rax, rcx
0x140059001  mov     rcx, rax; unsigned __int64
0x140059004  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140059009  mov     [r15+48h], rax
0x14005900d  test    rax, rax
0x140059010  jnz     short loc_14005905D
0x140059012  lea     rsi, WPP_RECORDER_INITIALIZED
0x140059019  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140059020  jz      short loc_140059053
0x140059022  mov     eax, [rbx+38h]
0x140059025  lea     rcx, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14005902c  mov     dword ptr [rsp+0C0h+var_98], eax
0x140059030  mov     r9d, 0BEh
0x140059036  mov     [rsp+0C0h+var_A0], rcx
0x14005903b  mov     r8d, 1
0x140059041  mov     rcx, cs:WPP_GLOBAL_Control
0x140059048  mov     dl, 2
0x14005904a  mov     rcx, [rcx+40h]
0x14005904e  call    WPP_RECORDER_SF_d
0x140059053  mov     eax, 0C000009Ah
0x140059058  jmp     loc_140059182
0x14005905d  mov     r10, [rbp+57h+arg_10]
0x140059061  mov     rcx, [rbp+57h+arg_0]
0x140059065  xor     r14d, r14d
0x140059068  cmp     [rbx+38h], r14d
0x14005906c  jbe     loc_140059174
0x140059072  xor     r13d, r13d
0x140059075  lea     rsi, WPP_RECORDER_INITIALIZED
0x14005907c  lea     r11, ?g_WiFi7Networks@@3PAUDOT11_AUTH_CIPHER_PAIR@@A; DOT11_AUTH_CIPHER_PAIR near * g_WiFi7Networks
0x140059083  lea     r12d, [r14+4]
0x140059087  mov     edx, [rcx+1510h]
0x14005908d  lea     rdi, ds:0[r13*8]
0x140059095  cmp     edx, 2000Ch
0x14005909b  jnb     short loc_1400590C4
0x14005909d  mov     r8, [rbx+40h]
0x1400590a1  xor     ecx, ecx
0x1400590a3  mov     r9d, [rdi+r8]
0x1400590a7  cmp     r9d, [r11+rcx*8]
0x1400590ab  jnz     short loc_1400590BD
0x1400590ad  mov     eax, [r11+rcx*8+4]
0x1400590b2  cmp     [rdi+r8+4], eax
0x1400590b7  jz      loc_14005919E
0x1400590bd  inc     ecx
0x1400590bf  cmp     ecx, 3
0x1400590c2  jb      short loc_1400590A7
0x1400590c4  mov     rcx, [rbx+40h]
0x1400590c8  mov     ecx, [rcx+rdi+4]
0x1400590cc  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x1400590d1  mov     rcx, [r10+48h]
0x1400590d5  mov     [rcx+r14*8+4], eax
0x1400590da  mov     rcx, [rbx+40h]
0x1400590de  mov     ecx, [rcx+rdi]
0x1400590e1  call    ?MapAuthAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z; CDot11ToWabiConverter::MapAuthAlgorithm(_DOT11_AUTH_ALGORITHM)
0x1400590e6  mov     rcx, [r10+48h]
0x1400590ea  mov     [rcx+r14*8], eax
0x1400590ee  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400590f5  jz      short loc_14005913F
0x1400590f7  mov     rcx, [r10+48h]
0x1400590fb  lea     r8d, [r13+1]
0x1400590ff  mov     rdx, [rbx+40h]
0x140059103  mov     eax, [rcx+r14*8+4]
0x140059108  mov     [rsp+50h], eax
0x14005910c  mov     eax, [rcx+r14*8]
0x140059110  mov     rcx, cs:WPP_GLOBAL_Control
0x140059117  mov     [rsp+0C0h+var_78], eax
0x14005911b  mov     eax, [rdx+rdi+4]
0x14005911f  mov     [rsp+0C0h+var_80], eax
0x140059123  mov     eax, [rdx+rdi]
0x140059126  mov     rcx, [rcx+40h]
0x14005912a  mov     [rsp+0C0h+var_88], eax
0x14005912e  mov     eax, [rbx+38h]
0x140059131  mov     [rsp+0C0h+var_90], eax
0x140059135  mov     dword ptr [rsp+0C0h+var_98], r8d
0x14005913a  call    WPP_RECORDER_SF_ddDDDD
0x14005913f  mov     rax, [rbx+40h]
0x140059143  mov     r12d, 4
0x140059149  mov     rcx, [r15+48h]
0x14005914d  mov     rax, [rdi+rax]
0x140059151  mov     [rcx+r14*8], rax
0x140059155  inc     r14d
0x140059158  mov     r10, [rbp+57h+arg_10]
0x14005915c  lea     r11, ?g_WiFi7Networks@@3PAUDOT11_AUTH_CIPHER_PAIR@@A; DOT11_AUTH_CIPHER_PAIR near * g_WiFi7Networks
0x140059163  mov     rcx, [rbp+57h+arg_0]
0x140059167  inc     r13d
0x14005916a  cmp     r13d, [rbx+38h]
0x14005916e  jb      loc_140059087
0x140059174  mov     rax, [rbp+57h+arg_10]
0x140059178  mov     [r15+40h], r14d
0x14005917c  mov     [rax+40h], r14d
0x140059180  xor     eax, eax
0x140059182  mov     rbx, [rsp+0C0h+arg_18]
0x14005918a  add     rsp, 90h
0x140059191  pop     r15
0x140059193  pop     r14
0x140059195  pop     r13
0x140059197  pop     r12
0x140059199  pop     rdi
0x14005919a  pop     rsi
0x14005919b  pop     rbp
0x14005919c  retn
0x14005919e  mov     eax, cs:dword_14010EC48
0x1400591a4  mov     [rbp+57h+arg_8], edx
0x1400591a7  cmp     eax, 3
0x1400591aa  jbe     short loc_140059212
0x1400591ac  mov     edx, 5
0x1400591b1  lea     rcx, dword_14010EC48
0x1400591b8  call    _tlgKeywordOn
0x1400591bd  test    al, al
0x1400591bf  jz      short loc_140059212
0x1400591c1  mov     rcx, [rbx+40h]
0x1400591c5  lea     rax, [rbp+57h+arg_8]
0x1400591c9  mov     [rbp+57h+var_60], rax
0x1400591cd  lea     rdx, unk_140104258
0x1400591d4  add     rcx, rdi
0x1400591d7  mov     [rbp+57h+var_58], r12w
0x1400591dc  mov     [rbp+57h+var_48], r12w
0x1400591e1  mov     [rbp+57h+var_40], rcx
0x1400591e5  mov     [rbp+57h+var_38], r12w
0x1400591ea  lea     rax, [rcx+4]
0x1400591ee  mov     [rbp+57h+var_50], rax
0x1400591f2  lea     rax, [rbp+57h+var_60]
0x1400591f6  mov     qword ptr [rsp+0C0h+var_90], rax
0x1400591fb  lea     rax, [rbp+57h+var_50]
0x1400591ff  mov     [rsp+0C0h+var_98], rax
0x140059204  lea     rax, [rbp+57h+var_40]
0x140059208  mov     [rsp+0C0h+var_A0], rax
0x14005920d  call    ??$Write@U?$_tlgWrapperArray@$00@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x140059212  mov     r9d, [rbp+57h+arg_8]
0x140059216  mov     eax, r9d
0x140059219  mov     r10, [rbx+40h]
0x14005921d  shr     eax, 8
0x140059220  movzx   edx, al
0x140059223  mov     eax, r9d
0x140059226  movzx   r8d, r9b
0x14005922a  mov     [rsp+0C0h+var_80], r8d
0x14005922f  lea     r8, aWificxDriverRe; "[WIFICX] Driver reported incompatible a"...
0x140059236  mov     [rsp+0C0h+var_88], edx
0x14005923a  xor     edx, edx; Level
0x14005923c  shr     eax, 10h
0x14005923f  movzx   ecx, al
0x140059242  mov     eax, [r10+rdi+4]
0x140059247  mov     [rsp+0C0h+var_90], ecx
0x14005924b  lea     ecx, [rdx+65h]; ComponentId
0x14005924e  shr     r9d, 18h
0x140059252  mov     dword ptr [rsp+0C0h+var_98], r9d
0x140059257  mov     r9d, [r10+rdi]
0x14005925b  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14005925f  call    cs:__imp_DbgPrintEx
0x140059266  nop     dword ptr [rax+rax+00h]
0x14005926b  jmp     loc_140059158
```
