# CListenerOperation::Configure(InboundRequestDetails *,Catalog &)

- ea: `0x180084a74`
- end: `0x180085243`
- name: `?Configure@CListenerOperation@@QEAA_NPEAVInboundRequestDetails@@AEAVCatalog@@@Z`
- size: `1999`
- prototype: `char __fastcall(CListenerOperation *this, struct InboundRequestDetails *, struct Catalog *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180083210`
- `0x180144f30`

## callees

- `0x180005d10`
- `0x18000fc50`
- `0x180010030`
- `0x180019950`
- `0x18001d4f0`
- `0x18002b7a0`
- `0x18002dd20`
- `0x180080288`
- `0x1800831c0`
- `0x180084a74`
- `0x180085250`
- `0x1800852a0`
- `0x1800866d0`
- `0x180086820`
- `0x18008f6a0`
- `0x180097248`
- `0x1800976c4`
- `0x1800d4d40`
- `0x180112380`
- `0x1801123e8`
- `0x18011349c`
- `0x18017203c`
- `0x1801ba152`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180084bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008512d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180084bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008512d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084be5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084be5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180084d56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180084d56`

## string_xrefs

- `0x1800851f3`: `onecore\admin\wmi\wmx\service\listeneroperation.cpp`
- `0x180084ab0`: `@Configure`
- `0x180084c54`: `@Configure`
- `0x180084db0`: `http://schemas.microsoft.com/wbem/wsman/1/wmi`

## pseudocode

```c
char __fastcall CListenerOperation::Configure(
        CListenerOperation *this,
        struct InboundRequestDetails *a2,
        struct Catalog *a3)
{
  struct Catalog *v3; // rbx
  int v6; // ebx
  bool IsInitialized; // al
  const wchar_t *v8; // rcx
  signed __int32 v9; // eax
  char v10; // bp
  char *v11; // rsi
  DWORD *v12; // rbx
  DWORD v13; // ecx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  struct _FWXML_ELEMENT *v16; // rbx
  struct _FWXML_ELEMENT *v17; // rax
  _DWORD *v18; // rcx
  HANDLE EventW; // r13
  const unsigned __int16 *Value; // r14
  __int64 v21; // rbx
  __int64 v22; // rax
  struct _WSMAN_KEY *Keys; // rax
  __int64 v24; // rcx
  _DWORD *v25; // rcx
  _DWORD *v26; // rcx
  int v27; // ebx
  int v28; // r12d
  const struct Catalog::Resource *Resource; // rax
  const struct Catalog::Resource *v30; // r13
  __int64 v31; // r8
  struct IRequestContext *v32; // r14
  __int64 v33; // rcx
  int v34; // edx
  int v35; // edx
  char v36; // al
  char v38; // al
  int v39; // [rsp+90h] [rbp+8h]
  __int64 v42; // [rsp+A8h] [rbp+20h]

  v3 = a3;
  *((_QWORD *)this + 263) = *((_QWORD *)a2 + 9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v6 = *((_DWORD *)this + 2) & 0x7FFFFFFF;
    IsInitialized = IOperation::IsInitialized(this);
    v8 = L"true";
    if ( !IsInitialized )
      v8 = L"false";
    WPP_SF_qsSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"@Configure", (__int64)v8, v6);
    v3 = a3;
  }
  do
  {
    v9 = *((_DWORD *)this + 2);
    if ( v9 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids,
          this,
          *((_QWORD *)this + 3));
      v10 = 0;
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 263) + 72LL))(*((_QWORD *)this + 263), 1115);
      v11 = (char *)this + 2112;
      goto LABEL_85;
    }
  }
  while ( v9 != _InterlockedCompareExchange((volatile signed __int32 *)this + 2, v9 + 1, v9) );
  v10 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids,
      this,
      *((_QWORD *)this + 3));
  v11 = (char *)this + 2112;
  *((_QWORD *)this + 134) = v3;
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr((char *)this + 2112);
  *((_QWORD *)this + 264) = a2;
  (**(void (__fastcall ***)(struct InboundRequestDetails *))a2)(a2);
  *((_QWORD *)a2 + 12) = this;
  v12 = (DWORD *)((char *)this + 168);
  *((_QWORD *)this + 32) = *(_QWORD *)(*((_QWORD *)this + 264) + 264LL);
  v13 = *((_DWORD *)this + 42);
  if ( v13 || (v13 = *((_DWORD *)this + 284)) != 0 )
  {
    SetLastError(v13);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids);
    goto LABEL_41;
  }
  CWSManCriticalSection::Acquire((CListenerOperation *)((char *)this + 168));
  *((_BYTE *)this + 224) = 1;
  if ( *v12 )
    SetLastError(*v12);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_PROCESS_CLIENT_REQUEST) )
    WSMan::LogEvent<unsigned short *>(&LOG_WSMAN_AN_PROCESS_CLIENT_REQUEST, *((_QWORD *)this + 262));
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 144LL))(*((_QWORD *)this + 263)) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v15 = 16;
      goto LABEL_22;
    }
    goto LABEL_85;
  }
  if ( *(_DWORD *)(*(_QWORD *)v11 + 464LL) == 1
    || (unsigned int)PacketParser::ValidateHeaders(
                       *((PacketParser **)this + 32),
                       *((struct IRequestContext **)this + 263),
                       *((_DWORD *)this + 66)) )
  {
    if ( (*((_BYTE *)this + 264) & 0x40) != 0 )
    {
      v16 = *(_DWORD *)(*((_QWORD *)this + 32) + 3672LL)
          ? (struct _FWXML_ELEMENT *)PacketParser::PacketElement<_FWXML_ELEMENT *>::GetValue()
          : 0LL;
      v17 = *(_DWORD *)(*((_QWORD *)this + 32) + 3696LL)
          ? (struct _FWXML_ELEMENT *)PacketParser::PacketElement<_FWXML_ELEMENT *>::GetValue()
          : 0LL;
      if ( !(unsigned int)CWSManResourceNoResourceUri::ParseHeaders(
                            (CListenerOperation *)((char *)this + 1216),
                            *((struct IRequestContext **)this + 263),
                            v17,
                            v16,
                            0) )
        goto LABEL_85;
    }
    *(_QWORD *)(*(_QWORD *)v11 + 56LL) = &Class;
    v18 = (_DWORD *)(*((_QWORD *)this + 32) + 3048LL);
    if ( *v18 )
      *(_QWORD *)(*(_QWORD *)v11 + 56LL) = PacketParser::PacketElement<unsigned short const *>::GetValue(v18);
    if ( *((_QWORD *)this + 136) )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( !EventW )
      {
LABEL_41:
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 24LL))(*((_QWORD *)this + 263));
        goto LABEL_85;
      }
      if ( *((_DWORD *)a2 + 116) == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids);
        Value = L"http://schemas.microsoft.com/wbem/wsman/1/wmi";
      }
      else
      {
        Value = (const unsigned __int16 *)PacketParser::PacketElement<unsigned short const *>::GetValue(*((_QWORD *)this + 32) + 3024LL);
      }
      v39 = (int)Value;
      v21 = ((unsigned __int64)this + 112) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
      *(_OWORD *)v21 = 0;
      *(_OWORD *)(v21 + 16) = 0;
      *(_OWORD *)(v21 + 32) = 0;
      *(_QWORD *)(v21 + 48) = 0;
      *(_QWORD *)v21 = (*(_QWORD *)v11 + 16LL) & -(__int64)(*(_QWORD *)v11 != 0);
      *(_QWORD *)(v21 + 8) = Locale::GetString((Locale *)(*((_QWORD *)this + 32) + 3944LL));
      *(_QWORD *)(v21 + 0x30) = Locale::GetString((Locale *)(*((_QWORD *)this + 32) + 4120LL));
      *(_QWORD *)(v21 + 0x10) = Value;
      *(_DWORD *)(v21 + 0x20) = 0;
      *(_QWORD *)(v21 + 0x28) = EventW;
      memset_0((char *)this + 288, 0, 0x68u);
      *(_QWORD *)(v21 + 0x18) = (char *)this + 288;
      v22 = *((_QWORD *)this + 32);
      if ( *(_DWORD *)(v22 + 3720) )
      {
        *((_QWORD *)this + 37) = *(_QWORD *)(v22 + 3744);
        *((_QWORD *)this + 36) = PacketParser::PacketElement<unsigned short const *>::GetValue(v22 + 3720);
      }
      *((_DWORD *)this + 84) = *((_DWORD *)this + 519);
      *((_QWORD *)this + 43) = *((_QWORD *)this + 257);
      *((_DWORD *)this + 88) = *((_DWORD *)this + 520);
      *((_QWORD *)this + 45) = *((_QWORD *)this + 258);
      Keys = CWSManResourceNoResourceUri::GetKeys((CListenerOperation *)((char *)this + 1216));
      v24 = *((_QWORD *)this + 32);
      *((_QWORD *)this + 41) = Keys;
      v25 = (_DWORD *)(v24 + 3600);
      *((_DWORD *)this + 80) = *((_DWORD *)this + 504);
      *((_DWORD *)this + 92) = -1430532899;
      if ( *v25 )
        *((_QWORD *)this + 47) = PacketParser::PacketElement<unsigned short const *>::GetValue(v25);
      v26 = (_DWORD *)(*((_QWORD *)this + 32) + 3624LL);
      if ( *v26 )
        *((_QWORD *)this + 48) = PacketParser::PacketElement<unsigned short const *>::GetValue(v26);
      v27 = *(_DWORD *)(*((_QWORD *)this + 32) + 3720LL) != 0 ? 2 : 0;
      if ( !*((_DWORD *)this + 519) || (v28 = 8, !*((_DWORD *)this + 520)) )
        v28 = 0;
      Resource = Catalog::GetResource(a3, Value, *((struct IRequestContext **)this + 263));
      *((_QWORD *)this + 151) = Resource;
      v30 = Resource;
      if ( Resource )
      {
        v31 = *((_QWORD *)this + 136);
        v32 = (struct IRequestContext *)*((_QWORD *)this + 263);
        v42 = v31;
        v33 = *(int *)(v31 + 20);
        v34 = *(_DWORD *)((char *)Resource + v33) | 8;
        if ( !*((_BYTE *)Resource + 32) )
          v34 = *(_DWORD *)((char *)Resource + v33);
        v35 = ~v34;
        if ( (v35 & 1) != 0 || (v35 & v27) != 0 )
        {
          (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)v32 + 64LL))(
            v32,
            2150858801LL,
            1077134173,
            *(_QWORD *)v31);
        }
        else if ( (v35 & v28) != 0 )
        {
          (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64))(*(_QWORD *)v32 + 64LL))(
            v32,
            2150858918LL,
            1077134351);
        }
        else if ( Catalog::Provider::Load(*((Catalog::Provider **)Resource + 2), v32) )
        {
          if ( *(_QWORD *)(*(int *)(v42 + 32) + *((_QWORD *)v30 + 2)) )
            return 1;
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\catalog\\catalog.cpp", 1899, L"1899", 0x54Fu, v32);
        }
        LODWORD(Value) = v39;
      }
      if ( *((_DWORD *)a2 + 116) != 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v38 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 152LL))(*((_QWORD *)this + 263));
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids,
            (_DWORD)Value,
            v38);
        }
        goto LABEL_85;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v36 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 152LL))(*((_QWORD *)this + 263));
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids,
          (_DWORD)Value,
          v36);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 263) + 200LL))(*((_QWORD *)this + 263), 1);
    }
    return 1;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v15 = 17;
LABEL_22:
    WPP_SF_(v14[2], v15, &WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids);
  }
LABEL_85:
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 144LL))(*((_QWORD *)this + 263)) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\listeneroperation.cpp", 306, L"306", 0x54Fu, 0);
  AutoRelease<CServiceConfigCache>::operator=(v11, 0);
  IOperation::Release(this, "@Response");
  if ( v10 )
  {
    IOperation::Shutdown(this);
    IOperation::Release(this, "@Configure");
  }
  return 0;
}

```

## disassembly

```asm
0x180084a74  mov     [rsp+arg_10], r8
0x180084a79  mov     [rsp+arg_8], rdx
0x180084a7e  push    rbx
0x180084a7f  push    rbp
0x180084a80  push    rsi
0x180084a81  push    rdi
0x180084a82  push    r12
0x180084a84  push    r13
0x180084a86  push    r14
0x180084a88  push    r15
0x180084a8a  sub     rsp, 48h
0x180084a8e  mov     rax, [rdx+48h]
0x180084a92  mov     rbx, r8
0x180084a95  mov     [rcx+838h], rax
0x180084a9c  mov     r12, rdx
0x180084a9f  mov     rdi, rcx
0x180084aa2  mov     rax, cs:WPP_GLOBAL_Control
0x180084aa9  lea     r13, WPP_GLOBAL_Control
0x180084ab0  lea     r14, aConfigure; "@Configure"
0x180084ab7  mov     esi, 0Eh
0x180084abc  cmp     rax, r13
0x180084abf  jz      short loc_180084B1C
0x180084ac1  test    dword ptr [rax+1Ch], 1000h
0x180084ac8  jz      short loc_180084B1C
0x180084aca  mov     ebx, [rcx+8]
0x180084acd  btr     ebx, 1Fh
0x180084ad1  call    ?IsInitialized@IOperation@@QEBA_NXZ; IOperation::IsInitialized(void)
0x180084ad6  lea     rdx, aFalse; "false"
0x180084add  mov     dword ptr [rsp+88h+var_58], ebx; char
0x180084ae1  test    al, al
0x180084ae3  lea     rcx, aTrue; "true"
0x180084aea  mov     r9, rdi
0x180084aed  lea     r8, WPP_e4968f4695e73c65848dbd42e49ea3da_Traceguids
0x180084af4  cmovz   rcx, rdx
0x180084af8  mov     edx, esi
0x180084afa  mov     [rsp+88h+var_60], rcx; __int64
0x180084aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180084b06  mov     [rsp+88h+var_68], r14; __int64
0x180084b0b  mov     rcx, [rcx+10h]; LoggerHandle
0x180084b0f  call    WPP_SF_qsSd
0x180084b14  mov     rbx, [rsp+88h+arg_10]
0x180084b1c  mov     eax, [rdi+8]
0x180084b1f  test    eax, eax
0x180084b21  jns     loc_180085166
0x180084b27  lea     ecx, [rax+1]
0x180084b2a  lock cmpxchg [rdi+8], ecx
0x180084b2f  jnz     short loc_180084B1C
0x180084b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180084b38  lea     r15, WPP_75752af15f5d369c87e52fdd3e6b012d_Traceguids
0x180084b3f  mov     ebp, 1
0x180084b44  mov     r14d, 400h
0x180084b4a  cmp     rcx, r13
0x180084b4d  jz      short loc_180084B6F
0x180084b4f  test    [rcx+1Ch], r14d
0x180084b53  jz      short loc_180084B6F
0x180084b55  mov     rax, [rdi+18h]
0x180084b59  mov     edx, esi
0x180084b5b  mov     rcx, [rcx+10h]
0x180084b5f  mov     r9, rdi
0x180084b62  mov     r8, r15
0x180084b65  mov     [rsp+88h+var_68], rax
0x180084b6a  call    WPP_SF_qq
0x180084b6f  lea     rsi, [rdi+840h]
0x180084b76  mov     [rdi+430h], rbx
0x180084b7d  mov     rcx, rsi
0x180084b80  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180084b85  mov     [rsi], r12
0x180084b88  mov     rcx, r12
0x180084b8b  mov     rax, [r12]
0x180084b8f  mov     rax, [rax]
0x180084b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b97  mov     [r12+60h], rdi
0x180084b9c  lea     rbx, [rdi+0A8h]
0x180084ba3  mov     rax, [rsi]
0x180084ba6  mov     rcx, [rax+108h]
0x180084bad  mov     [rdi+100h], rcx
0x180084bb4  mov     ecx, [rbx]; dwErrCode
0x180084bb6  test    ecx, ecx
0x180084bb8  jnz     loc_18008512D
0x180084bbe  mov     ecx, [rdi+470h]
0x180084bc4  test    ecx, ecx
0x180084bc6  jnz     loc_18008512D
0x180084bcc  mov     rcx, rbx; this
0x180084bcf  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x180084bd4  mov     [rdi+0E0h], bpl
0x180084bdb  mov     ecx, [rbx]; dwErrCode
0x180084bdd  test    ecx, ecx
0x180084bdf  jnz     short loc_180084BED
0x180084be1  lea     rcx, [rbx+8]; lpCriticalSection
0x180084be5  call    cs:__imp_LeaveCriticalSection
0x180084beb  jmp     short loc_180084BF3
0x180084bed  call    cs:__imp_SetLastError
0x180084bf3  lea     rcx, LOG_WSMAN_AN_PROCESS_CLIENT_REQUEST; struct _EVENT_DESCRIPTOR *
0x180084bfa  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x180084bff  test    al, al
0x180084c01  jz      short loc_180084C16
0x180084c03  mov     rdx, [rdi+830h]
0x180084c0a  lea     rcx, LOG_WSMAN_AN_PROCESS_CLIENT_REQUEST
0x180084c11  call    ??$LogEvent@PEAG@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@PEAG@Z; WSMan::LogEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180084c16  mov     rcx, [rdi+838h]
0x180084c1d  mov     rax, [rcx]
0x180084c20  mov     rax, [rax+90h]
0x180084c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c2c  test    eax, eax
0x180084c2e  jnz     short loc_180084C60
0x180084c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c37  cmp     rcx, r13
0x180084c3a  jz      short loc_180084C54
0x180084c3c  test    dword ptr [rcx+1Ch], 200h
0x180084c43  jz      short loc_180084C54
0x180084c45  lea     edx, [rax+10h]
0x180084c48  mov     rcx, [rcx+10h]
0x180084c4c  mov     r8, r15
0x180084c4f  call    WPP_SF_
0x180084c54  lea     r14, aConfigure; "@Configure"
0x180084c5b  jmp     loc_1800851BE
0x180084c60  mov     rax, [rsi]
0x180084c63  cmp     [rax+1D0h], ebp
0x180084c69  jz      short loc_180084CA3
0x180084c6b  mov     r8d, [rdi+108h]; unsigned int
0x180084c72  mov     rdx, [rdi+838h]; struct IRequestContext *
0x180084c79  mov     rcx, [rdi+100h]; this
0x180084c80  call    ?ValidateHeaders@PacketParser@@QEAAHPEAVIRequestContext@@K@Z; PacketParser::ValidateHeaders(IRequestContext *,ulong)
0x180084c85  test    eax, eax
0x180084c87  jnz     short loc_180084CA3
0x180084c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c90  cmp     rcx, r13
0x180084c93  jz      short loc_180084C54
0x180084c95  test    dword ptr [rcx+1Ch], 200h
0x180084c9c  jz      short loc_180084C54
0x180084c9e  lea     edx, [rax+11h]
0x180084ca1  jmp     short loc_180084C48
0x180084ca3  test    byte ptr [rdi+108h], 40h
0x180084caa  jz      short loc_180084D11
0x180084cac  mov     rcx, [rdi+100h]
0x180084cb3  add     rcx, 0E58h
0x180084cba  cmp     dword ptr [rcx], 0
0x180084cbd  jz      short loc_180084CC9
0x180084cbf  call    ?GetValue@?$PacketElement@PEAU_FWXML_ELEMENT@@@PacketParser@@QEBAPEAU_FWXML_ELEMENT@@XZ; PacketParser::PacketElement<_FWXML_ELEMENT *>::GetValue(void)
0x180084cc4  mov     rbx, rax
0x180084cc7  jmp     short loc_180084CCB
0x180084cc9  xor     ebx, ebx
0x180084ccb  mov     rcx, [rdi+100h]
0x180084cd2  add     rcx, 0E70h
0x180084cd9  cmp     dword ptr [rcx], 0
0x180084cdc  jz      short loc_180084CE5
0x180084cde  call    ?GetValue@?$PacketElement@PEAU_FWXML_ELEMENT@@@PacketParser@@QEBAPEAU_FWXML_ELEMENT@@XZ; PacketParser::PacketElement<_FWXML_ELEMENT *>::GetValue(void)
0x180084ce3  jmp     short loc_180084CE7
0x180084ce5  xor     eax, eax
0x180084ce7  mov     rdx, [rdi+838h]; struct IRequestContext *
0x180084cee  lea     rcx, [rdi+4C0h]; this
0x180084cf5  mov     r9, rbx; struct _FWXML_ELEMENT *
0x180084cf8  mov     [rsp+88h+var_68], 0; struct _FWXML_ELEMENT *
0x180084d01  mov     r8, rax; struct _FWXML_ELEMENT *
0x180084d04  call    ?ParseHeaders@CWSManResourceNoResourceUri@@QEAAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@11@Z; CWSManResourceNoResourceUri::ParseHeaders(IRequestContext *,_FWXML_ELEMENT *,_FWXML_ELEMENT *,_FWXML_ELEMENT *)
0x180084d09  test    eax, eax
0x180084d0b  jz      loc_180084C54
0x180084d11  mov     rax, [rsi]
0x180084d14  lea     rcx, Class
0x180084d1b  mov     [rax+38h], rcx
0x180084d1f  mov     rcx, [rdi+100h]
0x180084d26  add     rcx, 0BE8h
0x180084d2d  cmp     dword ptr [rcx], 0
0x180084d30  jz      short loc_180084D3E
0x180084d32  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180084d37  mov     rcx, [rsi]
0x180084d3a  mov     [rcx+38h], rax
0x180084d3e  cmp     qword ptr [rdi+440h], 0
0x180084d46  jz      loc_1800850C7
0x180084d4c  xor     r9d, r9d; lpName
0x180084d4f  xor     r8d, r8d; bInitialState
0x180084d52  mov     edx, ebp; bManualReset
0x180084d54  xor     ecx, ecx; lpEventAttributes
0x180084d56  call    cs:__imp_CreateEventW
0x180084d5c  mov     r13, rax
0x180084d5f  test    rax, rax
0x180084d62  jnz     short loc_180084D7C
0x180084d64  mov     rcx, [rdi+838h]
0x180084d6b  mov     rax, [rcx]
0x180084d6e  mov     rax, [rax+18h]
0x180084d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d77  jmp     loc_180084C54
0x180084d7c  cmp     [r12+1D0h], ebp
0x180084d84  jnz     short loc_180084DB9
0x180084d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180084d8d  lea     rax, WPP_GLOBAL_Control
0x180084d94  cmp     rcx, rax
0x180084d97  jz      short loc_180084DB0
0x180084d99  test    [rcx+1Ch], r14d
0x180084d9d  jz      short loc_180084DB0
0x180084d9f  mov     rcx, [rcx+10h]
0x180084da3  mov     edx, 12h
0x180084da8  mov     r8, r15
0x180084dab  call    WPP_SF_
0x180084db0  lea     r14, aHttpSchemasMic_56; "http://schemas.microsoft.com/wbem/wsman"...
0x180084db7  jmp     short loc_180084DCF
0x180084db9  mov     rcx, [rdi+100h]
0x180084dc0  add     rcx, 0BD0h
0x180084dc7  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180084dcc  mov     r14, rax
0x180084dcf  xorps   xmm0, xmm0
0x180084dd2  mov     [rsp+88h+arg_0], r14
0x180084dda  lea     rdx, [rdi+70h]
0x180084dde  mov     rcx, rdi
0x180084de1  neg     rcx
0x180084de4  sbb     rbx, rbx
0x180084de7  xor     eax, eax
0x180084de9  and     rbx, rdx
0x180084dec  movups  xmmword ptr [rbx], xmm0
0x180084def  movups  xmmword ptr [rbx+10h], xmm0
0x180084df3  movups  xmmword ptr [rbx+20h], xmm0
0x180084df7  mov     [rbx+30h], rax
0x180084dfb  mov     rax, [rsi]
0x180084dfe  lea     rcx, [rax+10h]
0x180084e02  neg     rax
0x180084e05  sbb     rax, rax
0x180084e08  and     rax, rcx
0x180084e0b  mov     [rbx], rax
0x180084e0e  mov     rcx, [rdi+100h]
0x180084e15  add     rcx, 0F68h; this
0x180084e1c  call    ?GetString@Locale@@QEAAPEBGXZ; Locale::GetString(void)
0x180084e21  mov     [rbx+8], rax
0x180084e25  mov     rcx, [rdi+100h]
0x180084e2c  add     rcx, 1018h; this
0x180084e33  call    ?GetString@Locale@@QEAAPEBGXZ; Locale::GetString(void)
0x180084e38  xor     edx, edx; Val
0x180084e3a  mov     [rbx+30h], rax
0x180084e3e  mov     [rbx+10h], r14
0x180084e42  lea     r12, [rdi+120h]
0x180084e49  mov     rcx, r12; void *
0x180084e4c  mov     dword ptr [rbx+20h], 0
0x180084e53  mov     [rbx+28h], r13
0x180084e57  lea     r8d, [rdx+68h]; Size
0x180084e5b  call    memset_0
0x180084e60  mov     [rbx+18h], r12
0x180084e64  xor     r13d, r13d
0x180084e67  mov     rax, [rdi+100h]
0x180084e6e  lea     rcx, [rax+0E88h]
0x180084e75  cmp     [rcx], r13d
0x180084e78  jz      short loc_180084E91
0x180084e7a  mov     rax, [rax+0EA0h]
0x180084e81  mov     [rdi+128h], rax
0x180084e88  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180084e8d  mov     [r12], rax
0x180084e91  lea     rcx, [rdi+4C0h]; this
0x180084e98  mov     eax, [rcx+35Ch]
0x180084e9e  mov     [rdi+150h], eax
0x180084ea4  mov     rax, [rdi+808h]
0x180084eab  mov     [rdi+158h], rax
0x180084eb2  mov     eax, [rdi+820h]
0x180084eb8  mov     [rdi+160h], eax
0x180084ebe  mov     rax, [rdi+810h]
0x180084ec5  mov     [rdi+168h], rax
0x180084ecc  call    ?GetKeys@CWSManResourceNoResourceUri@@QEAAPEAU_WSMAN_KEY@@XZ; CWSManResourceNoResourceUri::GetKeys(void)
0x180084ed1  mov     rcx, [rdi+100h]
0x180084ed8  mov     [rdi+148h], rax
0x180084edf  add     rcx, 0E10h
0x180084ee6  mov     eax, [rdi+7E0h]
0x180084eec  mov     [rdi+140h], eax
0x180084ef2  mov     dword ptr [rdi+170h], 0AABBCCDDh
0x180084efc  cmp     [rcx], r13d
0x180084eff  jz      short loc_180084F0D
0x180084f01  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180084f06  mov     [rdi+178h], rax
0x180084f0d  mov     rcx, [rdi+100h]
0x180084f14  add     rcx, 0E28h
0x180084f1b  cmp     [rcx], r13d
0x180084f1e  jz      short loc_180084F2C
0x180084f20  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180084f25  mov     [rdi+180h], rax
0x180084f2c  mov     rax, [rdi+100h]
0x180084f33  mov     ecx, [rax+0E88h]
0x180084f39  neg     ecx
0x180084f3b  sbb     ebx, ebx
0x180084f3d  and     ebx, 2
0x180084f40  cmp     [rdi+81Ch], r13d
0x180084f47  jbe     short loc_180084F58
0x180084f49  mov     r12d, 8
0x180084f4f  cmp     [rdi+820h], r13d
0x180084f56  jnz     short loc_180084F5B
0x180084f58  mov     r12d, r13d
0x180084f5b  mov     r8, [rdi+838h]; struct IRequestContext *
0x180084f62  mov     rdx, r14; unsigned __int16 *
0x180084f65  mov     rcx, [rsp+88h+arg_10]; this
0x180084f6d  call    ?GetResource@Catalog@@QEBAPEBVResource@1@PEBGAEAVIRequestContext@@@Z; Catalog::GetResource(ushort const *,IRequestContext &)
0x180084f72  mov     [rdi+4B8h], rax
0x180084f79  mov     r13, rax
0x180084f7c  test    rax, rax
0x180084f7f  jz      loc_18008504E
0x180084f85  mov     r8, [rdi+440h]
0x180084f8c  mov     r14, [rdi+838h]
0x180084f93  mov     [rsp+88h+arg_18], r8
0x180084f9b  movsxd  rcx, dword ptr [r8+14h]
0x180084f9f  mov     edx, [rcx+rax]
0x180084fa2  or      edx, 8
0x180084fa5  cmp     byte ptr [rax+20h], 0
0x180084fa9  cmovz   edx, [rcx+rax]
0x180084fad  not     edx
0x180084faf  test    bpl, dl
0x180084fb2  jz      short loc_180084FD3
  ... truncated ...
```
