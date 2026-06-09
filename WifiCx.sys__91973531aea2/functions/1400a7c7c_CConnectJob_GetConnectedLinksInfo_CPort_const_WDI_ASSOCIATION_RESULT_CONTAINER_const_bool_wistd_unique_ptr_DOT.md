# CConnectJob::GetConnectedLinksInfo(CPort const &,_WDI_ASSOCIATION_RESULT_CONTAINER const &,bool *,wistd::unique_ptr<DOT11_CONNECTION_INFO,wistd::default_delete<DOT11_CONNECTION_INFO>> &)

- ea: `0x1400a7c7c`
- end: `0x1400a8207`
- name: `?GetConnectedLinksInfo@CConnectJob@@AEAAHAEBVCPort@@AEBU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEA_NAEAV?$unique_ptr@UDOT11_CONNECTION_INFO@@U?$default_delete@UDOT11_CONNECTION_INFO@@@wistd@@@wistd@@@Z`
- size: `1419`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x1400a8830`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x140016d00`
- `0x14001c540`
- `0x140023ef4`
- `0x14002bcc8`
- `0x140071720`
- `0x140074568`
- `0x14009adbc`
- `0x1400a7c7c`
- `0x1400a9660`
- `0x1400b2ac8`
- `0x1400b6f70`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CConnectJob::GetConnectedLinksInfo(COidJobBase *a1, __int64 a2, __int64 a3, char *a4, _QWORD **a5)
{
  _QWORD **v5; // r12
  int v6; // ebx
  int v8; // esi
  _QWORD *v10; // rcx
  char v11; // r13
  MultiLinkIEHelpers *v12; // rcx
  unsigned __int8 *v13; // r9
  __int64 v14; // r8
  int v15; // edx
  int v16; // esi
  unsigned int v17; // r14d
  char *v18; // rax
  int v19; // edx
  char *v20; // rbx
  unsigned int v21; // r15d
  MultiLinkIEHelpers *v22; // rcx
  int v23; // eax
  int v24; // edx
  unsigned int v25; // edi
  _DWORD *v27; // r14
  __int64 v28; // rdx
  CPropertyCache *PortPropertyCache; // rax
  __int64 v30; // rdi
  __int64 v31; // rcx
  _DWORD *v32; // rax
  _DWORD *v33; // r8
  __int64 v34; // rdx
  unsigned int v35; // edx
  __int64 *v36; // rdx
  _QWORD *v37; // rcx
  struct MultiLinkIEHelpers::MULTILINK_IE_INFO *v38; // [rsp+20h] [rbp-E0h]
  struct MultiLinkIEHelpers::MULTILINK_IE_INFO *v39; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v40; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v41; // [rsp+28h] [rbp-D8h]
  struct DOT11_CONNECTION_INFO *v42; // [rsp+30h] [rbp-D0h]
  struct MultiLinkIEHelpers::MULTILINK_IE_INFO *v43; // [rsp+38h] [rbp-C8h]
  char v44; // [rsp+60h] [rbp-A0h]
  _WDI_OPERATION_MODE v45; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  COidJobBase *v47; // [rsp+70h] [rbp-90h]
  _QWORD **v48; // [rsp+78h] [rbp-88h]
  char *v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h]
  __int64 v52; // [rsp+A0h] [rbp-60h]
  _BYTE v53[168]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+150h] [rbp+50h] BYREF
  __int64 v55; // [rsp+158h] [rbp+58h]
  __int64 v56; // [rsp+160h] [rbp+60h]
  _BYTE v57[168]; // [rsp+168h] [rbp+68h] BYREF

  v5 = a5;
  v6 = 0;
  *a4 = 0;
  v47 = a1;
  v8 = 0;
  v49 = a4;
  v10 = *a5;
  v46 = a2;
  v48 = a5;
  *a5 = 0;
  if ( v10 )
    operator delete(v10);
  v56 = 5;
  v54 = 0;
  v11 = 0;
  v55 = 0;
  v44 = 0;
  memset(v57, 0, 0xA0u);
  `vector constructor iterator'(
    v57,
    0x20u,
    5u,
    (void *(*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::MULTILINK_STA_INFO);
  v52 = 5;
  v50 = 0;
  v51 = 0;
  memset(v53, 0, 0xA0u);
  `vector constructor iterator'(
    v53,
    0x20u,
    5u,
    (void *(*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::MULTILINK_STA_INFO);
  if ( *((_BYTE *)a1 + 1140) )
  {
    if ( (*(_DWORD *)a3 & 0x20) != 0 )
    {
      v13 = (unsigned __int8 *)*(unsigned int *)(a3 + 88);
      v14 = *(_QWORD *)(a3 + 72);
      LOBYTE(v12) = *(_BYTE *)(a3 + 20) != 0;
      v15 = *(_DWORD *)(a3 + 64);
      v39 = *(struct MultiLinkIEHelpers::MULTILINK_IE_INFO **)(a3 + 96);
      LOBYTE(v50) = 1;
      if ( !(unsigned int)MultiLinkIEHelpers::GetMultilinkIEInfoFromAssociationFrames(
                            v12,
                            v15,
                            v14,
                            v13,
                            (unsigned int)v39,
                            (unsigned __int8 *)&v50,
                            (struct MultiLinkIEHelpers::MULTILINK_IE_INFO *)&v54,
                            v43) )
      {
        v6 = HIDWORD(v51);
        v11 = 1;
        v8 = HIDWORD(v55);
        v44 = 1;
      }
    }
  }
  v16 = v6 + v8;
  v17 = 48 * v16 + 164;
  v18 = (char *)operator new(v17);
  v20 = v18;
  if ( v18 )
  {
    memset(v18, 0, (unsigned int)(48 * v16 + 164));
    v21 = 0;
    *(_DWORD *)v20 = v17;
    v22 = (MultiLinkIEHelpers *)(a3 + 4);
    if ( v11 )
    {
      LODWORD(v38) = v16 + 1;
      v23 = MultiLinkIEHelpers::SetConnectionInfoFromMloIEs(
              v22,
              (const unsigned __int8 (*)[6])(a3 + 208),
              (const unsigned __int8 (*)[6])&v50,
              (const struct MultiLinkIEHelpers::MULTILINK_IE_INFO *)&v54,
              v38,
              (unsigned int)v20,
              v42);
      v25 = v23;
      if ( v23 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v41) = v23;
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v24,
            1,
            401,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            v41);
        }
        operator delete(v20);
        `vector destructor iterator'(
          v53,
          0x20u,
          5u,
          (void (*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::~MULTILINK_STA_INFO);
        `vector destructor iterator'(
          v57,
          0x20u,
          5u,
          (void (*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::~MULTILINK_STA_INFO);
        return v25;
      }
      v27 = v20 + 104;
    }
    else
    {
      v28 = v46;
      v27 = v20 + 104;
      *((_DWORD *)v20 + 26) = 1;
      *((_DWORD *)v20 + 27) = 1;
      v20[112] = 0;
      *(_DWORD *)(v20 + 98) = *(_DWORD *)v22;
      *((_WORD *)v20 + 51) = *(_WORD *)(a3 + 8);
      *((_DWORD *)v20 + 23) = *(_DWORD *)(v28 + 184);
      *((_WORD *)v20 + 48) = *(_WORD *)(v28 + 188);
      *(_DWORD *)(v20 + 117) = *((_DWORD *)v20 + 23);
      *(_WORD *)(v20 + 121) = *((_WORD *)v20 + 48);
      v20[116] = 0;
      *((_DWORD *)v20 + 33) = 0;
      *(_DWORD *)(v20 + 123) = *(_DWORD *)v22;
      *(_WORD *)(v20 + 127) = *(_WORD *)(a3 + 8);
      if ( (*(_DWORD *)a3 & 0x20) != 0 )
      {
        *(_DWORD *)(v20 + 117) = *(_DWORD *)(a3 + 208);
        *(_WORD *)(v20 + 121) = *(_WORD *)(a3 + 212);
      }
    }
    v45 = WDI_OPERATION_MODE_STA;
    PortPropertyCache = COidJobBase::GetPortPropertyCache(v47);
    if ( !(unsigned int)CPropertyCache::GetPropertyULong(PortPropertyCache, 0x18u, (unsigned int *)&v45) )
      *((_DWORD *)v20 + 20) = CWabiToDot11Converter::MapOperationMode(v45);
    if ( *v27 )
    {
      while ( 1 )
      {
        v30 = 48LL * v21;
        if ( *(_DWORD *)&v20[v30 + 132] )
          goto LABEL_27;
        v31 = 1736;
        if ( *(_DWORD *)(v46 + 152) != 8 )
          v31 = 1336;
        v32 = (_DWORD *)(**(__int64 (__fastcall ***)(__int64, __int64))(*(_QWORD *)(v46 + 136) + v31))(
                          *(_QWORD *)(v46 + 136) + v31,
                          (__int64)&v20[v30 + 123]);
        if ( v32 )
          break;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v35 = v21 + 1;
          LOBYTE(v35) = 4;
          WPP_RECORDER_SF_dddD_MAC__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v35,
            v30 + (_DWORD)v20 + 123,
            402,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            v21 + 1,
            *v27,
            v20[v30 + 116],
            *(_DWORD *)&v20[v30 + 132],
            (__int64)&v20[v30 + 117],
            (__int64)&v20[v30 + 123]);
LABEL_27:
          v11 = v44;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v36 = &qword_1400FC9C8;
            if ( !v44 )
              v36 = (__int64 *)"non-";
            WPP_RECORDER_SF_ddsdD_MAC__MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v36,
              v21 + 1,
              403,
              (_DWORD)v38,
              v21 + 1,
              *v27,
              (__int64)v36,
              v20[v30 + 116],
              *(_DWORD *)&v20[v30 + 132],
              (__int64)&v20[v30 + 117],
              (__int64)&v20[v30 + 123]);
          }
          goto LABEL_32;
        }
        v11 = v44;
LABEL_32:
        if ( ++v21 >= *v27 )
        {
          v5 = v48;
          goto LABEL_34;
        }
      }
      *(_DWORD *)&v20[v30 + 148] = v32[148];
      *(_DWORD *)&v20[48 * v21 + 144] = v32[198];
      *(_DWORD *)&v20[v30 + 136] = CWabiToDot11Converter::MapBandID((unsigned int)v32[171]);
      *(_DWORD *)&v20[v30 + 140] = v33[170];
      *(_DWORD *)&v20[8 * v34] = v33[198];
      if ( v20[v30 + 116] == v20[112] )
        *((_DWORD *)v20 + 22) = v33[149];
      goto LABEL_27;
    }
LABEL_34:
    *v49 = v11;
    v37 = *v5;
    *v5 = v20;
    if ( v37 )
      operator delete(v37);
    `vector destructor iterator'(
      v53,
      0x20u,
      5u,
      (void (*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::~MULTILINK_STA_INFO);
    `vector destructor iterator'(
      v57,
      0x20u,
      5u,
      (void (*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::~MULTILINK_STA_INFO);
    return 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v40) = 48 * v16 + 164;
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        1,
        400,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        v40);
    }
    `vector destructor iterator'(
      v53,
      0x20u,
      5u,
      (void (*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::~MULTILINK_STA_INFO);
    `vector destructor iterator'(
      v57,
      0x20u,
      5u,
      (void (*)(void *))MultiLinkIEHelpers::MULTILINK_STA_INFO::~MULTILINK_STA_INFO);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400a7c7c  push    rbp
0x1400a7c7e  push    rbx
0x1400a7c7f  push    rsi
0x1400a7c80  push    rdi
0x1400a7c81  push    r12
0x1400a7c83  push    r13
0x1400a7c85  push    r14
0x1400a7c87  push    r15
0x1400a7c89  lea     rbp, [rsp-128h]
0x1400a7c91  sub     rsp, 228h
0x1400a7c98  mov     rax, cs:__security_cookie
0x1400a7c9f  xor     rax, rsp
0x1400a7ca2  mov     [rbp+160h+var_50], rax
0x1400a7ca9  mov     r12, [rbp+160h+arg_20]
0x1400a7cb0  xor     ebx, ebx
0x1400a7cb2  mov     [r9], bl
0x1400a7cb5  mov     r14, rcx
0x1400a7cb8  mov     [rsp+260h+var_1F0], rcx
0x1400a7cbd  xor     esi, esi
0x1400a7cbf  mov     [rbp+160h+var_1E0], r9
0x1400a7cc3  mov     rdi, r8
0x1400a7cc6  mov     rcx, [r12]; void *
0x1400a7cca  mov     [rsp+260h+var_1F8], rdx
0x1400a7ccf  mov     [rsp+260h+var_1E8], r12
0x1400a7cd4  mov     [r12], rbx
0x1400a7cd8  test    rcx, rcx
0x1400a7cdb  jz      short loc_1400A7CE2
0x1400a7cdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400a7ce2  xor     eax, eax
0x1400a7ce4  mov     [rbp+160h+var_100], 5
0x1400a7cec  mov     r15d, 0A0h
0x1400a7cf2  mov     [rbp+160h+var_110], rax
0x1400a7cf6  xor     r13b, r13b
0x1400a7cf9  mov     [rbp+160h+var_108], rax
0x1400a7cfd  mov     r8d, r15d; Size
0x1400a7d00  mov     [rsp+260h+var_200], r13b
0x1400a7d05  xor     edx, edx; Val
0x1400a7d07  lea     rcx, [rbp+160h+var_F8]; void *
0x1400a7d0b  call    memset
0x1400a7d10  lea     edx, [r15-80h]; unsigned __int64
0x1400a7d14  lea     r9, ??0MULTILINK_STA_INFO@MultiLinkIEHelpers@@QEAA@XZ; void *(*)(void *)
0x1400a7d1b  lea     rcx, [rbp+160h+var_F8]; void *
0x1400a7d1f  lea     r8d, [rdx-1Bh]; unsigned __int64
0x1400a7d23  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400a7d28  xor     eax, eax
0x1400a7d2a  mov     [rbp+160h+var_1C0], 5
0x1400a7d32  mov     r8d, r15d; Size
0x1400a7d35  mov     [rbp+160h+var_1D0], rax
0x1400a7d39  xor     edx, edx; Val
0x1400a7d3b  mov     [rbp+160h+var_1C8], rax
0x1400a7d3f  lea     rcx, [rbp+160h+var_1B8]; void *
0x1400a7d43  call    memset
0x1400a7d48  lea     edx, [r15-80h]; unsigned __int64
0x1400a7d4c  lea     r9, ??0MULTILINK_STA_INFO@MultiLinkIEHelpers@@QEAA@XZ; void *(*)(void *)
0x1400a7d53  lea     rcx, [rbp+160h+var_1B8]; void *
0x1400a7d57  lea     r8d, [rdx-1Bh]; unsigned __int64
0x1400a7d5b  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400a7d60  cmp     [r14+474h], bl
0x1400a7d67  jz      short loc_1400A7DB6
0x1400a7d69  mov     eax, [rdi]
0x1400a7d6b  test    al, 20h
0x1400a7d6d  jz      short loc_1400A7DB6
0x1400a7d6f  cmp     [rdi+14h], bl
0x1400a7d72  lea     rax, [rbp+160h+var_110]
0x1400a7d76  mov     r9d, [rdi+58h]; unsigned __int8 *
0x1400a7d7a  mov     r8, [rdi+48h]; unsigned int
0x1400a7d7e  setnz   cl; this
0x1400a7d81  mov     edx, [rdi+40h]; bool
0x1400a7d84  mov     [rsp+260h+var_230], rax; struct DOT11_CONNECTION_INFO *
0x1400a7d89  lea     rax, [rbp+160h+var_1D0]
0x1400a7d8d  mov     [rsp+260h+var_238], rax; unsigned __int8 *
0x1400a7d92  mov     rax, [rdi+60h]
0x1400a7d96  mov     [rsp+260h+var_240], rax; unsigned int
0x1400a7d9b  mov     byte ptr [rbp+160h+var_1D0], 1
0x1400a7d9f  call    ?GetMultilinkIEInfoFromAssociationFrames@MultiLinkIEHelpers@@YAH_NKPEAEK1PEAUMULTILINK_IE_INFO@1@2@Z; MultiLinkIEHelpers::GetMultilinkIEInfoFromAssociationFrames(bool,ulong,uchar *,ulong,uchar *,MultiLinkIEHelpers::MULTILINK_IE_INFO *,MultiLinkIEHelpers::MULTILINK_IE_INFO *)
0x1400a7da4  test    eax, eax
0x1400a7da6  jnz     short loc_1400A7DB6
0x1400a7da8  mov     ebx, dword ptr [rbp+160h+var_1C8+4]
0x1400a7dab  mov     r13b, 1
0x1400a7dae  mov     esi, dword ptr [rbp+160h+var_108+4]
0x1400a7db1  mov     [rsp+260h+var_200], r13b
0x1400a7db6  add     esi, ebx
0x1400a7db8  lea     r14d, [rsi+rsi*2]
0x1400a7dbc  shl     r14d, 4
0x1400a7dc0  add     r14d, 0A4h
0x1400a7dc7  mov     ecx, r14d; unsigned __int64
0x1400a7dca  mov     r15d, r14d
0x1400a7dcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a7dd2  mov     rbx, rax
0x1400a7dd5  test    rax, rax
0x1400a7dd8  jz      loc_1400A816D
0x1400a7dde  mov     r8d, r15d; Size
0x1400a7de1  xor     edx, edx; Val
0x1400a7de3  mov     rcx, rax; void *
0x1400a7de6  call    memset
0x1400a7deb  xor     r15d, r15d
0x1400a7dee  mov     [rbx], r14d
0x1400a7df1  lea     rcx, [rdi+4]; this
0x1400a7df5  test    r13b, r13b
0x1400a7df8  jz      loc_1400A7EA7
0x1400a7dfe  lea     eax, [rsi+1]
0x1400a7e01  mov     [rsp+260h+var_238], rbx; unsigned int
0x1400a7e06  lea     rdx, [rdi+0D0h]; unsigned __int8 (*)[6]
0x1400a7e0d  mov     dword ptr [rsp+260h+var_240], eax; struct MultiLinkIEHelpers::MULTILINK_IE_INFO *
0x1400a7e11  lea     r9, [rbp+160h+var_110]; struct MultiLinkIEHelpers::MULTILINK_IE_INFO *
0x1400a7e15  lea     r8, [rbp+160h+var_1D0]; unsigned __int8 (*)[6]
0x1400a7e19  call    ?SetConnectionInfoFromMloIEs@MultiLinkIEHelpers@@YAHAEAY05$$CBE0AEBUMULTILINK_IE_INFO@1@1KPEAUDOT11_CONNECTION_INFO@@@Z; MultiLinkIEHelpers::SetConnectionInfoFromMloIEs(uchar const (&)[6],uchar const (&)[6],MultiLinkIEHelpers::MULTILINK_IE_INFO const &,MultiLinkIEHelpers::MULTILINK_IE_INFO const &,ulong,DOT11_CONNECTION_INFO *)
0x1400a7e1e  mov     edi, eax
0x1400a7e20  test    eax, eax
0x1400a7e22  jz      short loc_1400A7EA1
0x1400a7e24  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400a7e2b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a7e32  jz      short loc_1400A7E60
0x1400a7e34  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7e3b  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a7e42  mov     dword ptr [rsp+260h+var_238], eax
0x1400a7e46  lea     r8d, [r15+1]
0x1400a7e4a  mov     r9d, 191h
0x1400a7e50  mov     [rsp+260h+var_240], r12
0x1400a7e55  mov     dl, 2
0x1400a7e57  mov     rcx, [rcx+40h]
0x1400a7e5b  call    WPP_RECORDER_SF_d
0x1400a7e60  mov     rcx, rbx; void *
0x1400a7e63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400a7e68  mov     esi, 5
0x1400a7e6d  lea     r9, ??1MULTILINK_STA_INFO@MultiLinkIEHelpers@@QEAA@XZ; void (*)(void *)
0x1400a7e74  mov     r8d, esi; unsigned __int64
0x1400a7e77  lea     rcx, [rbp+160h+var_1B8]; void *
0x1400a7e7b  lea     ebx, [rsi+1Bh]
0x1400a7e7e  mov     edx, ebx; unsigned __int64
0x1400a7e80  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400a7e85  lea     r9, ??1MULTILINK_STA_INFO@MultiLinkIEHelpers@@QEAA@XZ; void (*)(void *)
0x1400a7e8c  mov     r8d, esi; unsigned __int64
0x1400a7e8f  mov     edx, ebx; unsigned __int64
0x1400a7e91  lea     rcx, [rbp+160h+var_F8]; void *
0x1400a7e95  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400a7e9a  mov     eax, edi
0x1400a7e9c  jmp     loc_1400A81E3
0x1400a7ea1  lea     r14, [rbx+68h]
0x1400a7ea5  jmp     short loc_1400A7F20
0x1400a7ea7  mov     rdx, [rsp+260h+var_1F8]
0x1400a7eac  lea     r14, [rbx+68h]
0x1400a7eb0  mov     eax, 1
0x1400a7eb5  mov     [r14], eax
0x1400a7eb8  mov     [rbx+6Ch], eax
0x1400a7ebb  mov     [rbx+70h], r15b
0x1400a7ebf  mov     eax, [rcx]
0x1400a7ec1  mov     [rbx+62h], eax
0x1400a7ec4  movzx   eax, word ptr [rcx+4]
0x1400a7ec8  mov     [rbx+66h], ax
0x1400a7ecc  mov     eax, [rdx+0B8h]
0x1400a7ed2  mov     [rbx+5Ch], eax
0x1400a7ed5  movzx   eax, word ptr [rdx+0BCh]
0x1400a7edc  mov     [rbx+60h], ax
0x1400a7ee0  mov     eax, [rbx+5Ch]
0x1400a7ee3  mov     [rbx+75h], eax
0x1400a7ee6  movzx   eax, word ptr [rbx+60h]
0x1400a7eea  mov     [rbx+79h], ax
0x1400a7eee  mov     [rbx+74h], r15b
0x1400a7ef2  mov     [rbx+84h], r15d
0x1400a7ef9  mov     eax, [rcx]
0x1400a7efb  mov     [rbx+7Bh], eax
0x1400a7efe  movzx   eax, word ptr [rcx+4]
0x1400a7f02  mov     [rbx+7Fh], ax
0x1400a7f06  mov     eax, [rdi]
0x1400a7f08  test    al, 20h
0x1400a7f0a  jz      short loc_1400A7F20
0x1400a7f0c  mov     eax, [rdi+0D0h]
0x1400a7f12  mov     [rbx+75h], eax
0x1400a7f15  movzx   eax, word ptr [rdi+0D4h]
0x1400a7f1c  mov     [rbx+79h], ax
0x1400a7f20  mov     rcx, [rsp+260h+var_1F0]; this
0x1400a7f25  mov     [rsp+260h+var_1FC], 1
0x1400a7f2d  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a7f32  lea     r8, [rsp+260h+var_1FC]; unsigned int *
0x1400a7f37  mov     edx, 18h; unsigned int
0x1400a7f3c  mov     rcx, rax; this
0x1400a7f3f  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400a7f44  test    eax, eax
0x1400a7f46  jnz     short loc_1400A7F54
0x1400a7f48  mov     ecx, [rsp+260h+var_1FC]; enum _WDI_OPERATION_MODE
0x1400a7f4c  call    ?MapOperationMode@CWabiToDot11Converter@@SAKW4_WDI_OPERATION_MODE@@@Z; CWabiToDot11Converter::MapOperationMode(_WDI_OPERATION_MODE)
0x1400a7f51  mov     [rbx+50h], eax
0x1400a7f54  cmp     [r14], r15d
0x1400a7f57  jbe     loc_1400A811E
0x1400a7f5d  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400a7f64  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a7f6b  mov     r13d, r15d
0x1400a7f6e  lea     rdi, ds:0[r13*2]
0x1400a7f76  add     rdi, r13
0x1400a7f79  shl     rdi, 4
0x1400a7f7d  cmp     dword ptr [rdi+rbx+84h], 0
0x1400a7f85  jnz     loc_1400A808A
0x1400a7f8b  mov     rax, [rsp+260h+var_1F8]
0x1400a7f90  mov     edx, 538h
0x1400a7f95  mov     ecx, 6C8h
0x1400a7f9a  cmp     dword ptr [rax+98h], 8
0x1400a7fa1  cmovnz  ecx, edx
0x1400a7fa4  lea     rdx, [rbx+7Bh]
0x1400a7fa8  add     rcx, [rax+88h]
0x1400a7faf  add     rdx, rdi
0x1400a7fb2  mov     rax, [rcx]
0x1400a7fb5  mov     rax, [rax]
0x1400a7fb8  call    _guard_dispatch_icall
0x1400a7fbd  mov     r8, rax
0x1400a7fc0  test    rax, rax
0x1400a7fc3  jz      short loc_1400A8025
0x1400a7fc5  mov     ecx, [rax+250h]
0x1400a7fcb  lea     rdx, [r13+3]
0x1400a7fcf  mov     [rdi+rbx+94h], ecx
0x1400a7fd6  lea     rdx, [rdx+rdx*2]
0x1400a7fda  mov     ecx, [rax+318h]
0x1400a7fe0  add     rdx, rdx
0x1400a7fe3  mov     [rbx+rdx*8], ecx
0x1400a7fe6  mov     ecx, [rax+2ACh]
0x1400a7fec  call    ?MapBandID@CWabiToDot11Converter@@SA?AW4_DOT11_BAND_ID@@W4_WDI_BAND_ID@@@Z; CWabiToDot11Converter::MapBandID(_WDI_BAND_ID)
0x1400a7ff1  mov     [rdi+rbx+88h], eax
0x1400a7ff8  mov     eax, [r8+2A8h]
0x1400a7fff  mov     [rdi+rbx+8Ch], eax
0x1400a8006  mov     eax, [r8+318h]
0x1400a800d  mov     [rbx+rdx*8], eax
0x1400a8010  mov     al, [rbx+70h]
0x1400a8013  cmp     [rdi+rbx+74h], al
0x1400a8017  jnz     short loc_1400A808A
0x1400a8019  mov     eax, [r8+254h]
0x1400a8020  mov     [rbx+58h], eax
0x1400a8023  jmp     short loc_1400A808A
0x1400a8025  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a802c  jz      loc_1400A8108
0x1400a8032  movzx   ecx, byte ptr [rdi+rbx+74h]
0x1400a8037  lea     edx, [r15+1]
0x1400a803b  lea     r8, [rbx+7Bh]
0x1400a803f  mov     r9d, 192h
0x1400a8045  add     r8, rdi
0x1400a8048  lea     rax, [rbx+75h]
0x1400a804c  mov     [rsp+260h+var_210], r8
0x1400a8051  add     rax, rdi
0x1400a8054  mov     [rsp+260h+var_218], rax
0x1400a8059  mov     eax, [rdi+rbx+84h]
0x1400a8060  mov     [rsp+260h+var_220], eax
0x1400a8064  mov     eax, [r14]
0x1400a8067  mov     dword ptr [rsp+260h+var_228], ecx
0x1400a806b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8072  mov     dword ptr [rsp+260h+var_230], eax
0x1400a8076  mov     dword ptr [rsp+260h+var_238], edx
0x1400a807a  mov     dl, 4
0x1400a807c  mov     [rsp+260h+var_240], r12
0x1400a8081  mov     rcx, [rcx+40h]
0x1400a8085  call    WPP_RECORDER_SF_dddD_MAC__MAC_
0x1400a808a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a8091  mov     r13b, [rsp+260h+var_200]
0x1400a8096  jz      short loc_1400A810D
0x1400a8098  movzx   r10d, byte ptr [rdi+rbx+74h]
0x1400a809e  lea     r8, aNon; "non-"
0x1400a80a5  lea     rax, [rbx+7Bh]
0x1400a80a9  mov     r9d, 193h
0x1400a80af  add     rax, rdi
0x1400a80b2  lea     rcx, [rbx+75h]
0x1400a80b6  mov     [rsp+260h+var_208], rax
0x1400a80bb  lea     rdx, qword_1400FC9C8
0x1400a80c2  mov     eax, [rdi+rbx+84h]
0x1400a80c9  add     rcx, rdi
0x1400a80cc  mov     [rsp+260h+var_210], rcx
0x1400a80d1  test    r13b, r13b
0x1400a80d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a80db  mov     dword ptr [rsp+260h+var_218], eax
0x1400a80df  cmovz   rdx, r8
0x1400a80e3  mov     eax, [r14]
0x1400a80e6  lea     r8d, [r15+1]
0x1400a80ea  mov     [rsp+260h+var_220], r10d
0x1400a80ef  mov     rcx, [rcx+40h]
0x1400a80f3  mov     [rsp+260h+var_228], rdx
0x1400a80f8  mov     dword ptr [rsp+260h+var_230], eax
0x1400a80fc  mov     dword ptr [rsp+260h+var_238], r8d
0x1400a8101  call    WPP_RECORDER_SF_ddsdD_MAC__MAC_
0x1400a8106  jmp     short loc_1400A810D
0x1400a8108  mov     r13b, [rsp+260h+var_200]
0x1400a810d  inc     r15d
0x1400a8110  cmp     r15d, [r14]
0x1400a8113  jb      loc_1400A7F6B
0x1400a8119  mov     r12, [rsp+260h+var_1E8]
0x1400a811e  mov     rax, [rbp+160h+var_1E0]
0x1400a8122  mov     [rax], r13b
0x1400a8125  mov     rcx, [r12]; void *
0x1400a8129  mov     [r12], rbx
0x1400a812d  test    rcx, rcx
0x1400a8130  jz      short loc_1400A8137
0x1400a8132  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400a8137  mov     edi, 5
0x1400a813c  lea     r9, ??1MULTILINK_STA_INFO@MultiLinkIEHelpers@@QEAA@XZ; void (*)(void *)
0x1400a8143  mov     r8d, edi; unsigned __int64
0x1400a8146  lea     rcx, [rbp+160h+var_1B8]; void *
0x1400a814a  lea     ebx, [rdi+1Bh]
0x1400a814d  mov     edx, ebx; unsigned __int64
0x1400a814f  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400a8154  lea     r9, ??1MULTILINK_STA_INFO@MultiLinkIEHelpers@@QEAA@XZ; void (*)(void *)
0x1400a815b  mov     r8d, edi; unsigned __int64
0x1400a815e  mov     edx, ebx; unsigned __int64
0x1400a8160  lea     rcx, [rbp+160h+var_F8]; void *
0x1400a8164  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
  ... truncated ...
```
