# CloudDomainHelper::DiscoverLoginUri(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18007c04c`
- end: `0x18007c31a`
- name: `?DiscoverLoginUri@CloudDomainHelper@@SAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z`
- size: `718`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001e558`

## callees

- `0x1800065e8`
- `0x1800067f4`
- `0x18000685c`
- `0x180006908`
- `0x1800069c0`
- `0x180006ac4`
- `0x18000c7ac`
- `0x180071e14`
- `0x18007bc78`
- `0x18007c04c`
- `0x18007c360`
- `0x180094104`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007c0aa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007c0aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c18a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007c18a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c0e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c0e5`

## string_xrefs

- `0x18007c07a`: `CloudDomainHelper::DiscoverLoginUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudDomainHelper::DiscoverLoginUri(unsigned __int16 *a1, _QWORD *a2, __int64 a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  int v8; // ebx
  unsigned int v9; // ebx
  void *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  int *v13; // rsi
  __int64 v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // rcx
  int v18; // [rsp+30h] [rbp-88h]
  _DWORD *v19; // [rsp+50h] [rbp-68h] BYREF
  const char *v20[7]; // [rsp+58h] [rbp-60h] BYREF
  int v21; // [rsp+D8h] [rbp+20h] BYREF

  v21 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v20,
    (int)"clouddomainhelper.cpp",
    (int)"CloudDomainHelper::DiscoverLoginUri",
    (int)&v21);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
  v6 = malloc(0x20u);
  v7 = v6;
  v19 = v6;
  if ( !v6 )
  {
    v9 = -1073741801;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741801, "clouddomainhelper.cpp", 376, "NTSTATUS", &base);
    goto LABEL_18;
  }
  *v6 = 2;
  v6[4] = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 1) = CreateEventW(0, 1, 0, 0);
  v8 = DsrBeginDiscoverEx(a1);
  v21 = v8;
  if ( v8 >= 0 )
  {
    v10 = (void *)*((_QWORD *)v7 + 1);
    if ( !v10 || WaitForSingleObject(v10, 0x1D4C0u) )
    {
      v21 = -2147187533;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -2147187533, "clouddomainhelper.cpp", 383, "HRESULT", &base);
      v9 = -1073445709;
      goto LABEL_16;
    }
    v8 = v7[4];
    v21 = v8;
    if ( v8 >= 0 )
    {
      v11 = *(_QWORD *)DiscoverLoginUriContext::GetAuthority(v7, &v19);
      v12 = (_QWORD *)(v11 - 24);
      v13 = (int *)(*a2 - 24LL);
      if ( (int *)(v11 - 24) != v13 )
      {
        if ( v13[4] >= 0 && *v12 == *(_QWORD *)v13 )
        {
          v14 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12);
          ATL::CStringData::Release((ATL::CStringData *)v13);
          *a2 = v14 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v11, *(unsigned int *)(v11 - 16));
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 6));
      v15 = ATL::CSimpleStringT<unsigned short,0>::StringLength(*(_QWORD *)(*((_QWORD *)v7 + 3) + 176LL));
      ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v16, v15);
      v9 = v7 == 0 ? 0xC0000017 : 0;
      goto LABEL_16;
    }
    v18 = 386;
  }
  else
  {
    v18 = 379;
  }
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v8, "clouddomainhelper.cpp", v18, "HRESULT", &base);
  v9 = v8 & 0xAFFFFFFF | 0x40000000;
LABEL_16:
  DiscoverLoginUriContext::DecRefCount((DiscoverLoginUriContext *)v7);
LABEL_18:
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v20);
  return v9;
}

```

## disassembly

```asm
0x18007c04c  mov     rax, rsp
0x18007c04f  mov     [rax+8], rbx
0x18007c053  mov     [rax+10h], rbp
0x18007c057  push    rsi
0x18007c058  push    rdi
0x18007c059  push    r13
0x18007c05b  push    r14
0x18007c05d  push    r15
0x18007c05f  sub     rsp, 90h
0x18007c066  mov     r15, r8
0x18007c069  mov     r14, rdx
0x18007c06c  mov     rsi, rcx
0x18007c06f  mov     dword ptr [rax+20h], 0
0x18007c076  lea     r9, [rax+20h]
0x18007c07a  lea     r8, aClouddomainhel_0; "CloudDomainHelper::DiscoverLoginUri"
0x18007c081  lea     rbp, aOnecoreuapDsEx_13+20h; "clouddomainhelper.cpp"
0x18007c088  mov     rdx, rbp
0x18007c08b  lea     rcx, [rax-60h]
0x18007c08f  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18007c094  nop
0x18007c095  mov     rcx, r14
0x18007c098  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18007c09d  mov     rcx, r15
0x18007c0a0  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18007c0a5  mov     ecx, 20h ; ' '; Size
0x18007c0aa  call    cs:__imp_malloc
0x18007c0b0  mov     rdi, rax
0x18007c0b3  mov     [rsp+0B8h+var_68], rax
0x18007c0b8  mov     r13d, 2
0x18007c0be  test    rax, rax
0x18007c0c1  jz      loc_18007C2AF
0x18007c0c7  mov     [rax], r13d
0x18007c0ca  mov     dword ptr [rax+10h], 0
0x18007c0d1  mov     qword ptr [rax+18h], 0
0x18007c0d9  xor     r9d, r9d; lpName
0x18007c0dc  xor     r8d, r8d; bInitialState
0x18007c0df  lea     edx, [r13-1]; bManualReset
0x18007c0e3  xor     ecx, ecx; lpEventAttributes
0x18007c0e5  call    cs:__imp_CreateEventW
0x18007c0eb  mov     [rdi+8], rax
0x18007c0ef  test    rdi, rdi
0x18007c0f2  jz      loc_18007C2AF
0x18007c0f8  mov     rax, rdi
0x18007c0fb  neg     rax
0x18007c0fe  sbb     ebp, ebp
0x18007c100  not     ebp
0x18007c102  and     ebp, 0C0000017h
0x18007c108  mov     r9, rdi
0x18007c10b  lea     r8, ?DiscoverLoginUriCallBack@@YAXPEAU_DISCOVERY_METADATA@@Ustruct_dsreg_server_response@@_KJ@Z; DiscoverLoginUriCallBack(_DISCOVERY_METADATA *,struct_dsreg_server_response,unsigned __int64,long)
0x18007c112  mov     rcx, rsi; unsigned __int16 *
0x18007c115  call    DsrBeginDiscoverEx
0x18007c11a  mov     ebx, eax
0x18007c11c  mov     [rsp+0B8h+arg_18], eax
0x18007c123  test    eax, eax
0x18007c125  jns     short loc_18007C178
0x18007c127  lea     rax, base
0x18007c12e  mov     [rsp+0B8h+var_78], rax
0x18007c133  lea     rax, aHresult; "HRESULT"
0x18007c13a  mov     [rsp+0B8h+var_80], rax
0x18007c13f  mov     [rsp+0B8h+var_88], 17Bh
0x18007c147  lea     rax, aOnecoreuapDsEx_13+20h; "clouddomainhelper.cpp"
0x18007c14e  mov     [rsp+0B8h+var_90], rax
0x18007c153  mov     [rsp+0B8h+var_98], ebx
0x18007c157  mov     r9d, r13d
0x18007c15a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007c161  xor     edx, edx
0x18007c163  mov     ecx, r13d
0x18007c166  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007c16b  btr     ebx, 1Ch
0x18007c16f  bts     ebx, 1Eh
0x18007c173  jmp     loc_18007C2A5
0x18007c178  mov     rcx, [rdi+8]; hHandle
0x18007c17c  test    rcx, rcx
0x18007c17f  jz      loc_18007C250
0x18007c185  mov     edx, 1D4C0h; dwMilliseconds
0x18007c18a  call    cs:__imp_WaitForSingleObject
0x18007c190  test    eax, eax
0x18007c192  jnz     loc_18007C250
0x18007c198  mov     ebx, [rdi+10h]
0x18007c19b  mov     [rsp+0B8h+arg_18], ebx
0x18007c1a2  test    ebx, ebx
0x18007c1a4  jns     short loc_18007C1CB
0x18007c1a6  lea     rax, base
0x18007c1ad  mov     [rsp+0B8h+var_78], rax
0x18007c1b2  lea     rax, aHresult; "HRESULT"
0x18007c1b9  mov     [rsp+0B8h+var_80], rax
0x18007c1be  mov     [rsp+0B8h+var_88], 182h
0x18007c1c6  jmp     loc_18007C147
0x18007c1cb  lea     rdx, [rsp+0B8h+var_68]
0x18007c1d0  mov     rcx, rdi
0x18007c1d3  call    ?GetAuthority@DiscoverLoginUriContext@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; DiscoverLoginUriContext::GetAuthority(void)
0x18007c1d8  nop
0x18007c1d9  mov     rdx, [rax]
0x18007c1dc  lea     rcx, [rdx-18h]
0x18007c1e0  mov     rsi, [r14]
0x18007c1e3  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18007c1e7  cmp     rcx, rsi
0x18007c1ea  jz      short loc_18007C220
0x18007c1ec  cmp     dword ptr [rsi+10h], 0
0x18007c1f0  jl      short loc_18007C213
0x18007c1f2  mov     rax, [rsi]
0x18007c1f5  cmp     [rcx], rax
0x18007c1f8  jnz     short loc_18007C213
0x18007c1fa  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18007c1ff  mov     rbx, rax
0x18007c202  mov     rcx, rsi; this
0x18007c205  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18007c20a  lea     rax, [rbx+18h]
0x18007c20e  mov     [r14], rax
0x18007c211  jmp     short loc_18007C220
0x18007c213  mov     r8d, [rdx-10h]
0x18007c217  mov     rcx, r14
0x18007c21a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18007c21f  nop
0x18007c220  mov     rcx, [rsp+0B8h+var_68]
0x18007c225  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18007c229  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18007c22e  mov     rax, [rdi+18h]
0x18007c232  mov     rcx, [rax+0B0h]
0x18007c239  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x18007c23e  mov     r8d, eax
0x18007c241  mov     rdx, rcx
0x18007c244  mov     rcx, r15
0x18007c247  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18007c24c  mov     ebx, ebp
0x18007c24e  jmp     short loc_18007C2A5
0x18007c250  mov     ecx, 800484B3h
0x18007c255  mov     [rsp+0B8h+arg_18], ecx
0x18007c25c  lea     rax, base
0x18007c263  mov     [rsp+0B8h+var_78], rax
0x18007c268  lea     rax, aHresult; "HRESULT"
0x18007c26f  mov     [rsp+0B8h+var_80], rax
0x18007c274  mov     [rsp+0B8h+var_88], 17Fh
0x18007c27c  lea     rax, aOnecoreuapDsEx_13+20h; "clouddomainhelper.cpp"
0x18007c283  mov     [rsp+0B8h+var_90], rax
0x18007c288  mov     [rsp+0B8h+var_98], ecx
0x18007c28c  mov     r9d, r13d
0x18007c28f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007c296  xor     edx, edx
0x18007c298  mov     ecx, r13d
0x18007c29b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007c2a0  mov     ebx, 0C00484B3h
0x18007c2a5  mov     rcx, rdi; this
0x18007c2a8  call    ?DecRefCount@DiscoverLoginUriContext@@QEAAXXZ; DiscoverLoginUriContext::DecRefCount(void)
0x18007c2ad  jmp     short loc_18007C2F2
0x18007c2af  mov     ebx, 0C0000017h
0x18007c2b4  lea     rax, base
0x18007c2bb  mov     [rsp+0B8h+var_78], rax
0x18007c2c0  lea     rax, aNtstatus; "NTSTATUS"
0x18007c2c7  mov     [rsp+0B8h+var_80], rax
0x18007c2cc  mov     [rsp+0B8h+var_88], 178h
0x18007c2d4  mov     [rsp+0B8h+var_90], rbp
0x18007c2d9  mov     [rsp+0B8h+var_98], ebx
0x18007c2dd  mov     r9d, r13d
0x18007c2e0  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007c2e7  xor     edx, edx
0x18007c2e9  mov     ecx, r13d
0x18007c2ec  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007c2f1  nop
0x18007c2f2  lea     rcx, [rsp+0B8h+var_60]
0x18007c2f7  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18007c2fc  mov     eax, ebx
0x18007c2fe  lea     r11, [rsp+0B8h+var_28]
0x18007c306  mov     rbx, [r11+30h]
0x18007c30a  mov     rbp, [r11+38h]
0x18007c30e  mov     rsp, r11
0x18007c311  pop     r15
0x18007c313  pop     r14
0x18007c315  pop     r13
0x18007c317  pop     rdi
0x18007c318  pop     rsi
0x18007c319  retn
```
