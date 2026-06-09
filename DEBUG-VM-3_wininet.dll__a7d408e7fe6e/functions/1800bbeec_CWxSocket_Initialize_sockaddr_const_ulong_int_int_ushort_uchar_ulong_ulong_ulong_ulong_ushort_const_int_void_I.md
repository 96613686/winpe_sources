# CWxSocket::Initialize(sockaddr const *,ulong,int,int,ushort,uchar,ulong,ulong,ulong *,ulong,ushort const *,int,void *,ICmProxyResult *)

- ea: `0x1800bbeec`
- end: `0x1800bc4de`
- name: `?Initialize@CWxSocket@@AEAAJPEBUsockaddr@@KHHGEKKPEAKKPEBGHPEAXPEAUICmProxyResult@@@Z`
- size: `1522`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, const struct sockaddr *name@<rdx>, unsigned int@<r8d>, int@<r9d>, int, unsigned __int16, char, unsigned int, unsigned int, unsigned int *, unsigned int, const unsigned __int16 *, int, void *, struct ICmProxyResult *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bc5c8`
- `0x18010e444`

## callees

- `0x18002c3b4`
- `0x1800548ec`
- `0x1800701d0`
- `0x1800bbbc4`
- `0x1800bbeec`
- `0x1801119a4`
- `0x180112918`
- `0x1801163b0`
- `0x180135600`
- `0x180140748`
- `0x180148b48`
- `0x18014a7a0`
- `0x1801a40c8`
- `0x1801a4174`
- `0x1801e1790`
- `0x1801e2f30`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800bc48f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800bc48f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800bc03d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800bc03d`
- `ntdll!NtSetInformationObject` at `0x1800bbfeb`
- `ntdll!NtSetInformationObject` at `0x1800bbfeb`
- `srpapi!SrpCloseThreadNetworkContext` at `0x1800bc3a0`
- `srpapi!SrpCloseThreadNetworkContext` at `0x1800bc3a0`
- `srpapi!SrpCreateThreadNetworkContext` at `0x1800bc380`
- `srpapi!SrpCreateThreadNetworkContext` at `0x1800bc380`
- `WS2_32!WSASocketA` at `0x1800bbf8d`
- `WS2_32!WSASocketA` at `0x1800bbf8d`
- `WS2_32!WSAIoctl` at `0x1800bc135`
- `WS2_32!WSAIoctl` at `0x1800bc1bb`
- `WS2_32!WSAIoctl` at `0x1800bc135`
- `WS2_32!WSAIoctl` at `0x1800bc1bb`
- `WS2_32!__imp_bind` at `0x1800bc06f`
- `WS2_32!__imp_bind` at `0x1800bc06f`
- `WS2_32!__imp_closesocket` at `0x1800bc481`
- `WS2_32!__imp_closesocket` at `0x1800bc481`
- `WS2_32!__imp_getsockname` at `0x1800bc096`
- `WS2_32!__imp_getsockname` at `0x1800bc096`
- `WS2_32!__imp_setsockopt` at `0x1800bc0d0`
- `WS2_32!__imp_setsockopt` at `0x1800bc27f`
- `WS2_32!__imp_setsockopt` at `0x1800bc0d0`
- `WS2_32!__imp_setsockopt` at `0x1800bc27f`

## pseudocode

```c
__int64 __fastcall CWxSocket::Initialize(
        struct sockaddr *pv,
        const struct sockaddr *name,
        int a3,
        int a4,
        int a5,
        unsigned __int16 a6,
        unsigned __int8 a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int *a10,
        unsigned int a11,
        const unsigned __int16 *a12,
        int a13,
        void *a14,
        struct ICmProxyResult *a15)
{
  int sa_family; // ebx
  struct _TP_IO *ThreadpoolIo; // r15
  int v19; // r12d
  void *v20; // rbx
  signed int Error; // edi
  bool v22; // sf
  NTSTATUS v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  int v26; // edx
  int v27; // eax
  int v28; // edx
  unsigned __int16 v29; // r8
  unsigned __int8 v30; // cl
  struct ICmProxyResult *v32; // rsi
  int LastError; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // [rsp+50h] [rbp-59h] BYREF
  int v38; // [rsp+54h] [rbp-55h]
  unsigned int *v39; // [rsp+58h] [rbp-51h]
  int v40; // [rsp+64h] [rbp-45h]
  struct ICmProxyResult *v41; // [rsp+68h] [rbp-41h]
  void *v42; // [rsp+70h] [rbp-39h]
  int namelen; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int16 ObjectInformation; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int8 v45; // [rsp+82h] [rbp-27h]
  char v46; // [rsp+83h] [rbp-26h]
  _DWORD vInBuffer[2]; // [rsp+88h] [rbp-21h] BYREF
  __int128 v48; // [rsp+90h] [rbp-19h] BYREF

  sa_family = name->sa_family;
  v39 = a10;
  v42 = a14;
  vInBuffer[0] = a4;
  namelen = a3;
  v41 = a15;
  v38 = 0;
  v37 = 1;
  v48 = 0;
  if ( a12 )
  {
    Error = SrpCreateThreadNetworkContext(a12, &v48);
    if ( Error < 0 )
    {
      v38 = 1100;
      return (unsigned int)Error;
    }
  }
  ThreadpoolIo = 0;
  v19 = sa_family;
  v20 = (void *)WSASocketA(sa_family, 1, 6, 0, 0, 0x81u);
  if ( v20 == (void *)-1LL )
    Error = WxWSAGetLastError();
  else
    Error = 0;
  if ( a12 )
  {
    v36 = SrpCloseThreadNetworkContext(&v48);
    WxFatalHResult(v36);
  }
  v22 = Error < 0;
  if ( Error > 0 )
  {
    Error = (unsigned __int16)Error | 0x80070000;
    v22 = Error < 0;
  }
  if ( v22 )
  {
    v38 = 1125;
    goto LABEL_43;
  }
  v40 = 0;
  ObjectInformation = 0;
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_qD(1027, 12, &WPP_c409c363c67d3d5c7a2e7a93c81b5aa4_Traceguids, v20, 1);
  HIBYTE(ObjectInformation) = 1;
  v23 = NtSetInformationObject(v20, ObjectHandleFlagInformation, &ObjectInformation, 2u);
  v24 = HRESULT_FROM_NTSTATUS(v23);
  Error = v24;
  if ( v24 < 0 )
    v40 = 505;
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_d(1027, 13, &WPP_c409c363c67d3d5c7a2e7a93c81b5aa4_Traceguids, (unsigned int)v24);
  if ( Error < 0 )
  {
    v38 = 1132;
    goto LABEL_43;
  }
  Error = _SetSocketInlineCompletion(v20, &v37);
  if ( Error < 0 )
  {
    v38 = 1138;
    goto LABEL_43;
  }
  ThreadpoolIo = CreateThreadpoolIo(v20, CWxSocket::IoCompletionCallback, pv, 0);
  if ( !ThreadpoolIo )
  {
    LastError = WxGetLastError(v25);
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    v38 = 1145;
    if ( Error >= 0 )
      Error = -2147418113;
    goto LABEL_43;
  }
  Error = 0;
  if ( vInBuffer[0] )
  {
    v40 = 0;
    if ( a11 )
    {
      Error = _SetSocketInterface((SOCKET)v20, v19, *v39);
      if ( Error < 0 )
      {
        v40 = 433;
        v38 = 1158;
        goto LABEL_43;
      }
    }
    if ( bind((SOCKET)v20, name, namelen) == -1 )
    {
      v34 = WxWSAGetLastError();
      Error = v34;
      if ( v34 > 0 )
        Error = (unsigned __int16)v34 | 0x80070000;
      v38 = 1160;
      goto LABEL_43;
    }
    HIDWORD(v39) = 0;
    namelen = 128;
    if ( getsockname((SOCKET)v20, pv + 20, &namelen) == -1 )
    {
      v35 = WxWSAGetLastError();
      Error = v35;
      if ( v35 > 0 )
        Error = (unsigned __int16)v35 | 0x80070000;
      HIDWORD(v39) = 76;
    }
    else
    {
      Error = 0;
    }
    if ( Error < 0 )
    {
      v38 = 1166;
      goto LABEL_43;
    }
  }
  HIDWORD(v39) = 0;
  namelen = 1;
  if ( setsockopt((SOCKET)v20, 6, 1, (const char *)&namelen, 4) == -1 )
  {
    WxWSAGetLastError();
    HIDWORD(v39) = 139;
  }
  _SetSocketAckFrequency((unsigned __int64)v20, v26);
  v27 = 100794368;
  if ( a5 )
    v27 = 100663296;
  HIDWORD(v39) = 0;
  vInBuffer[1] = v27;
  namelen = 0;
  vInBuffer[0] = 2;
  if ( WSAIoctl((SOCKET)v20, 0x9800012C, vInBuffer, 8u, 0, 0, (LPDWORD)&namelen, 0, 0) == -1 )
  {
    WxWSAGetLastError();
    HIDWORD(v39) = 286;
  }
  v28 = a7;
  v29 = 0;
  HIDWORD(v39) = 0;
  ObjectInformation = 0;
  v45 = 0;
  v46 = 0;
  namelen = 0;
  if ( a6 != 0xFFFF || a7 != 0xFF )
  {
    v30 = 0;
    if ( a7 != 0xFF )
      v30 = a7;
    v45 = v30;
    if ( a6 != 0xFFFF )
      v29 = a6;
    ObjectInformation = v29;
    if ( WSAIoctl((SOCKET)v20, 0x98000011, &ObjectInformation, 4u, 0, 0, (LPDWORD)&namelen, 0, 0) == -1 )
    {
      WxWSAGetLastError();
      HIDWORD(v39) = 327;
    }
  }
  if ( a8 != -1 )
    _SetSocketBufferLength(v20, 2);
  if ( a9 != -1 )
  {
    namelen = a9;
    HIDWORD(v39) = 0;
    if ( setsockopt((SOCKET)v20, 0xFFFF, 4098, (const char *)&namelen, 4) == -1 )
    {
      WxWSAGetLastError();
      HIDWORD(v39) = 358;
    }
  }
  if ( a13 )
  {
    Error = _SetSocketFastOpen((unsigned __int64)v20, v28);
    if ( Error < 0 )
    {
      v38 = 1211;
LABEL_43:
      if ( v20 != (void *)-1LL )
      {
        _SetSocketProtect(v20, 0);
        closesocket((SOCKET)v20);
      }
      if ( ThreadpoolIo )
        CloseThreadpoolIo(ThreadpoolIo);
      return (unsigned int)Error;
    }
  }
  v32 = v41;
  if ( (xmmword_180266B60 & 0x20) != 0 )
    WPP_SF_qq(1029, 21, (unsigned int)&WPP_c409c363c67d3d5c7a2e7a93c81b5aa4_Traceguids, (_DWORD)v42, (__int64)v41);
  if ( v42 )
    _SetSocketNameResolutionPolicy((SOCKET)v20, v42);
  if ( v32 )
    _SetSocketProxyDetectionPolicy((SOCKET)v20, v32);
  *(_DWORD *)&pv[19].sa_data[2] = v37;
  *(_QWORD *)&pv[1].sa_family = v20;
  *(_QWORD *)&pv[1].sa_data[6] = ThreadpoolIo;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800bbeec  mov     [rsp-8+arg_18], rbx
0x1800bbef1  push    rbp
0x1800bbef2  push    rsi
0x1800bbef3  push    rdi
0x1800bbef4  push    r12
0x1800bbef6  push    r13
0x1800bbef8  push    r14
0x1800bbefa  push    r15
0x1800bbefc  lea     rbp, [rsp-7]
0x1800bbf01  sub     rsp, 0B0h
0x1800bbf08  mov     rax, cs:__security_cookie
0x1800bbf0f  xor     rax, rsp
0x1800bbf12  mov     [rbp+37h+var_40], rax
0x1800bbf16  mov     rax, [rbp+37h+arg_48]
0x1800bbf1d  xorps   xmm0, xmm0
0x1800bbf20  mov     rsi, [rbp+37h+arg_58]
0x1800bbf27  mov     r13, rdx
0x1800bbf2a  movzx   ebx, word ptr [rdx]
0x1800bbf2d  mov     r14, rcx
0x1800bbf30  mov     [rbp+37h+var_88], rax
0x1800bbf34  mov     rax, [rbp+37h+arg_68]
0x1800bbf3b  mov     [rbp+37h+var_70], rax
0x1800bbf3f  mov     rax, [rbp+37h+arg_70]
0x1800bbf46  mov     [rbp+37h+vInBuffer], r9d
0x1800bbf4a  mov     [rbp+37h+namelen], r8d
0x1800bbf4e  mov     [rbp+37h+var_78], rax
0x1800bbf52  mov     [rbp+37h+var_8C], 0
0x1800bbf59  mov     [rbp+37h+var_90], 1
0x1800bbf60  movups  [rbp+37h+var_50], xmm0
0x1800bbf64  test    rsi, rsi
0x1800bbf67  jnz     loc_1800BC379
0x1800bbf6d  xor     r15d, r15d
0x1800bbf70  mov     [rsp+0E0h+dwFlags], 81h; dwFlags
0x1800bbf78  xor     r9d, r9d; lpProtocolInfo
0x1800bbf7b  mov     [rsp+0E0h+g], r15d; g
0x1800bbf80  mov     ecx, ebx; af
0x1800bbf82  mov     r12d, ebx
0x1800bbf85  lea     edx, [r15+1]; type
0x1800bbf89  lea     r8d, [r15+6]; protocol
0x1800bbf8d  call    cs:__imp_WSASocketA
0x1800bbf93  mov     rbx, rax
0x1800bbf96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bbf9a  jz      loc_1800BC247
0x1800bbfa0  xor     edi, edi
0x1800bbfa2  test    rsi, rsi
0x1800bbfa5  jnz     loc_1800BC39C
0x1800bbfab  xor     esi, esi
0x1800bbfad  test    edi, edi
0x1800bbfaf  jle     short loc_1800BBFBC
0x1800bbfb1  movzx   edi, di
0x1800bbfb4  or      edi, 80070000h
0x1800bbfba  test    edi, edi
0x1800bbfbc  js      loc_1800BC2DD
0x1800bbfc2  mov     [rbp+37h+var_7C], esi
0x1800bbfc5  mov     [rbp+37h+ObjectInformation], si
0x1800bbfc9  test    byte ptr cs:xmmword_180266B60, 8
0x1800bbfd0  jnz     loc_1800BC313
0x1800bbfd6  mov     r9d, 2; Length
0x1800bbfdc  mov     byte ptr [rbp+37h+ObjectInformation+1], 1
0x1800bbfe0  lea     r8, [rbp+37h+ObjectInformation]; ObjectInformation
0x1800bbfe4  mov     rcx, rbx; ObjectHandle
0x1800bbfe7  lea     edx, [r9+2]; ObjectInformationClass
0x1800bbfeb  call    cs:__imp_NtSetInformationObject
0x1800bbff1  mov     ecx, eax; int
0x1800bbff3  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800bbff8  mov     edi, eax
0x1800bbffa  test    eax, eax
0x1800bbffc  js      loc_1800BC3B2
0x1800bc002  test    byte ptr cs:xmmword_180266B60, 8
0x1800bc009  jnz     loc_1800BC3BE
0x1800bc00f  test    edi, edi
0x1800bc011  js      loc_1800BC3DC
0x1800bc017  lea     rdx, [rbp+37h+var_90]; int *
0x1800bc01b  mov     rcx, rbx; FileHandle
0x1800bc01e  call    ?_SetSocketInlineCompletion@@YAJ_KPEAH@Z; _SetSocketInlineCompletion(unsigned __int64,int *)
0x1800bc023  mov     edi, eax
0x1800bc025  test    eax, eax
0x1800bc027  js      loc_1800BC3E8
0x1800bc02d  xor     r9d, r9d; pcbe
0x1800bc030  lea     rdx, ?IoCompletionCallback@CWxSocket@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1800bc037  mov     r8, r14; pv
0x1800bc03a  mov     rcx, rbx; fl
0x1800bc03d  call    cs:__imp_CreateThreadpoolIo
0x1800bc043  mov     r15, rax
0x1800bc046  test    rax, rax
0x1800bc049  jz      loc_1800BC2E9
0x1800bc04f  mov     edi, esi
0x1800bc051  cmp     [rbp+37h+vInBuffer], esi
0x1800bc054  jz      short loc_1800BC0AF
0x1800bc056  mov     [rbp+37h+var_7C], esi
0x1800bc059  cmp     [rbp+37h+arg_50], esi
0x1800bc05f  jnz     loc_1800BC3F4
0x1800bc065  mov     r8d, [rbp+37h+namelen]; namelen
0x1800bc069  mov     rdx, r13; name
0x1800bc06c  mov     rcx, rbx; s
0x1800bc06f  call    cs:__imp_bind
0x1800bc075  cmp     eax, 0FFFFFFFFh
0x1800bc078  jz      loc_1800BC339
0x1800bc07e  lea     rdx, [r14+140h]; name
0x1800bc085  mov     dword ptr [rbp+37h+var_88+4], esi
0x1800bc088  lea     r8, [rbp+37h+namelen]; namelen
0x1800bc08c  mov     [rbp+37h+namelen], 80h
0x1800bc093  mov     rcx, rbx; s
0x1800bc096  call    cs:__imp_getsockname
0x1800bc09c  cmp     eax, 0FFFFFFFFh
0x1800bc09f  jz      loc_1800BC359
0x1800bc0a5  mov     edi, esi
0x1800bc0a7  test    edi, edi
0x1800bc0a9  js      loc_1800BC423
0x1800bc0af  mov     eax, 1
0x1800bc0b4  mov     dword ptr [rbp+37h+var_88+4], esi
0x1800bc0b7  lea     r9, [rbp+37h+namelen]; optval
0x1800bc0bb  mov     [rbp+37h+namelen], eax
0x1800bc0be  mov     r8d, eax; optname
0x1800bc0c1  mov     rcx, rbx; s
0x1800bc0c4  lea     r12d, [rax+3]
0x1800bc0c8  lea     edx, [rax+5]; level
0x1800bc0cb  mov     [rsp+0E0h+g], r12d; optlen
0x1800bc0d0  call    cs:__imp_setsockopt
0x1800bc0d6  cmp     eax, 0FFFFFFFFh
0x1800bc0d9  jz      loc_1800BC42F
0x1800bc0df  mov     rcx, rbx; unsigned __int64
0x1800bc0e2  call    ?_SetSocketAckFrequency@@YAJ_KH@Z; _SetSocketAckFrequency(unsigned __int64,int)
0x1800bc0e7  cmp     [rbp+37h+arg_20], esi
0x1800bc0ea  lea     r8, [rbp+37h+vInBuffer]; lpvInBuffer
0x1800bc0ee  mov     [rsp+0E0h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x1800bc0f3  mov     eax, 6020000h
0x1800bc0f8  mov     [rsp+0E0h+lpOverlapped], rsi; lpOverlapped
0x1800bc0fd  mov     ecx, 6000000h
0x1800bc102  cmovnz  eax, ecx
0x1800bc105  mov     dword ptr [rbp+37h+var_88+4], esi
0x1800bc108  mov     [rbp+37h+var_54], eax
0x1800bc10b  mov     r9d, 8; cbInBuffer
0x1800bc111  lea     rax, [rbp+37h+namelen]
0x1800bc115  mov     [rbp+37h+namelen], esi
0x1800bc118  mov     [rsp+0E0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800bc11d  mov     edx, 9800012Ch; dwIoControlCode
0x1800bc122  mov     [rsp+0E0h+dwFlags], esi; cbOutBuffer
0x1800bc126  mov     rcx, rbx; s
0x1800bc129  mov     qword ptr [rsp+0E0h+g], rsi; lpvOutBuffer
0x1800bc12e  mov     [rbp+37h+vInBuffer], 2
0x1800bc135  call    cs:__imp_WSAIoctl
0x1800bc13b  cmp     eax, 0FFFFFFFFh
0x1800bc13e  jz      loc_1800BC440
0x1800bc144  movzx   r9d, [rbp+37h+arg_28]
0x1800bc149  xor     ecx, ecx
0x1800bc14b  movzx   edx, [rbp+37h+arg_30]
0x1800bc14f  mov     r13d, 0FFFFh
0x1800bc155  movzx   eax, sil
0x1800bc159  mov     r8d, esi
0x1800bc15c  mov     dword ptr [rbp+37h+var_88+4], esi
0x1800bc15f  mov     [rbp+37h+ObjectInformation], r8w
0x1800bc164  mov     [rbp+37h+var_5E], al
0x1800bc167  mov     [rbp+37h+var_5D], cl
0x1800bc16a  mov     [rbp+37h+namelen], esi
0x1800bc16d  cmp     r9w, r13w
0x1800bc171  jz      loc_1800BC253
0x1800bc177  cmp     dl, 0FFh
0x1800bc17a  mov     [rsp+0E0h+lpCompletionRoutine], rsi; lpCompletionRoutine
0x1800bc17f  mov     ecx, eax
0x1800bc181  mov     [rsp+0E0h+lpOverlapped], rsi; lpOverlapped
0x1800bc186  cmovnz  ecx, edx
0x1800bc189  lea     rax, [rbp+37h+namelen]
0x1800bc18d  cmp     r9w, r13w
0x1800bc191  mov     [rsp+0E0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800bc196  mov     [rbp+37h+var_5E], cl
0x1800bc199  mov     edx, 98000011h; dwIoControlCode
0x1800bc19e  cmovnz  r8w, r9w
0x1800bc1a3  mov     [rsp+0E0h+dwFlags], esi; cbOutBuffer
0x1800bc1a7  mov     [rbp+37h+ObjectInformation], r8w
0x1800bc1ac  mov     r9d, r12d; cbInBuffer
0x1800bc1af  lea     r8, [rbp+37h+ObjectInformation]; lpvInBuffer
0x1800bc1b3  mov     qword ptr [rsp+0E0h+g], rsi; lpvOutBuffer
0x1800bc1b8  mov     rcx, rbx; s
0x1800bc1bb  call    cs:__imp_WSAIoctl
0x1800bc1c1  cmp     eax, 0FFFFFFFFh
0x1800bc1c4  jz      loc_1800BC451
0x1800bc1ca  mov     r8d, [rbp+37h+arg_38]
0x1800bc1ce  or      r12d, 0FFFFFFFFh
0x1800bc1d2  cmp     r8d, r12d
0x1800bc1d5  jnz     loc_1800BC462
0x1800bc1db  mov     eax, [rbp+37h+arg_40]
0x1800bc1e1  cmp     eax, r12d
0x1800bc1e4  jnz     short loc_1800BC261
0x1800bc1e6  cmp     [rbp+37h+arg_60], esi
0x1800bc1ec  jz      loc_1800BC29F
0x1800bc1f2  mov     rcx, rbx; unsigned __int64
0x1800bc1f5  call    ?_SetSocketFastOpen@@YAJ_KH@Z; _SetSocketFastOpen(unsigned __int64,int)
0x1800bc1fa  mov     edi, eax
0x1800bc1fc  test    eax, eax
0x1800bc1fe  jns     loc_1800BC29F
0x1800bc204  mov     [rbp+37h+var_8C], 4BBh
0x1800bc20b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bc20f  jnz     loc_1800BC474
0x1800bc215  test    r15, r15
0x1800bc218  jnz     loc_1800BC48C
0x1800bc21e  mov     eax, edi
0x1800bc220  mov     rcx, [rbp+37h+var_40]
0x1800bc224  xor     rcx, rsp; StackCookie
0x1800bc227  call    __security_check_cookie
0x1800bc22c  mov     rbx, [rsp+0E0h+arg_18]
0x1800bc234  add     rsp, 0B0h
0x1800bc23b  pop     r15
0x1800bc23d  pop     r14
0x1800bc23f  pop     r13
0x1800bc241  pop     r12
0x1800bc243  pop     rdi
0x1800bc244  pop     rsi
0x1800bc245  pop     rbp
0x1800bc246  retn
0x1800bc247  call    WxWSAGetLastError
0x1800bc24c  mov     edi, eax
0x1800bc24e  jmp     loc_1800BBFA2
0x1800bc253  cmp     dl, 0FFh
0x1800bc256  jz      loc_1800BC1CA
0x1800bc25c  jmp     loc_1800BC177
0x1800bc261  mov     [rbp+37h+namelen], eax
0x1800bc264  lea     r9, [rbp+37h+namelen]; optval
0x1800bc268  mov     r8d, 1002h; optname
0x1800bc26e  mov     dword ptr [rbp+37h+var_88+4], esi
0x1800bc271  mov     edx, r13d; level
0x1800bc274  mov     [rsp+0E0h+g], 4; optlen
0x1800bc27c  mov     rcx, rbx; s
0x1800bc27f  call    cs:__imp_setsockopt
0x1800bc285  cmp     eax, 0FFFFFFFFh
0x1800bc288  jnz     loc_1800BC1E6
0x1800bc28e  call    WxWSAGetLastError
0x1800bc293  mov     dword ptr [rbp+37h+var_88+4], 166h
0x1800bc29a  jmp     loc_1800BC1E6
0x1800bc29f  test    byte ptr cs:xmmword_180266B60, 20h
0x1800bc2a6  mov     rsi, [rbp+37h+var_78]
0x1800bc2aa  jnz     loc_1800BC49A
0x1800bc2b0  mov     rax, [rbp+37h+var_70]
0x1800bc2b4  test    rax, rax
0x1800bc2b7  jnz     loc_1800BC4BE
0x1800bc2bd  test    rsi, rsi
0x1800bc2c0  jnz     loc_1800BC4CE
0x1800bc2c6  mov     ecx, [rbp+37h+var_90]
0x1800bc2c9  mov     [r14+134h], ecx
0x1800bc2d0  mov     [r14+10h], rbx
0x1800bc2d4  mov     [r14+18h], r15
0x1800bc2d8  jmp     loc_1800BC21E
0x1800bc2dd  mov     [rbp+37h+var_8C], 465h
0x1800bc2e4  jmp     loc_1800BC20B
0x1800bc2e9  call    WxGetLastError
0x1800bc2ee  mov     edi, eax
0x1800bc2f0  test    eax, eax
0x1800bc2f2  jle     short loc_1800BC2FD
0x1800bc2f4  movzx   edi, ax
0x1800bc2f7  or      edi, 80070000h
0x1800bc2fd  test    edi, edi
0x1800bc2ff  mov     [rbp+37h+var_8C], 479h
0x1800bc306  mov     eax, 8000FFFFh
0x1800bc30b  cmovns  edi, eax
0x1800bc30e  jmp     loc_1800BC20B
0x1800bc313  mov     edx, 0Ch
0x1800bc318  mov     [rsp+0E0h+g], 1
0x1800bc320  mov     ecx, 403h
0x1800bc325  lea     r8, WPP_c409c363c67d3d5c7a2e7a93c81b5aa4_Traceguids
0x1800bc32c  mov     r9, rbx
0x1800bc32f  call    WPP_SF_qD
0x1800bc334  jmp     loc_1800BBFD6
0x1800bc339  call    WxWSAGetLastError
0x1800bc33e  mov     edi, eax
0x1800bc340  test    eax, eax
0x1800bc342  jle     short loc_1800BC34D
0x1800bc344  movzx   edi, ax
0x1800bc347  or      edi, 80070000h
0x1800bc34d  mov     [rbp+37h+var_8C], 488h
0x1800bc354  jmp     loc_1800BC20B
0x1800bc359  call    WxWSAGetLastError
0x1800bc35e  mov     edi, eax
0x1800bc360  test    eax, eax
0x1800bc362  jle     short loc_1800BC36D
0x1800bc364  movzx   edi, ax
0x1800bc367  or      edi, 80070000h
0x1800bc36d  mov     dword ptr [rbp+37h+var_88+4], 4Ch ; 'L'
0x1800bc374  jmp     loc_1800BC0A7
0x1800bc379  lea     rdx, [rbp+37h+var_50]
0x1800bc37d  mov     rcx, rsi
0x1800bc380  call    cs:__imp_SrpCreateThreadNetworkContext
0x1800bc386  mov     edi, eax
0x1800bc388  test    eax, eax
0x1800bc38a  jns     loc_1800BBF6D
0x1800bc390  mov     [rbp+37h+var_8C], 44Ch
0x1800bc397  jmp     loc_1800BC21E
0x1800bc39c  lea     rcx, [rbp+37h+var_50]
0x1800bc3a0  call    cs:__imp_SrpCloseThreadNetworkContext
0x1800bc3a6  mov     ecx, eax; int
0x1800bc3a8  call    ?WxFatalHResult@@YAXJ@Z; WxFatalHResult(long)
0x1800bc3ad  jmp     loc_1800BBFAB
0x1800bc3b2  mov     [rbp+37h+var_7C], 1F9h
0x1800bc3b9  jmp     loc_1800BC002
0x1800bc3be  mov     edx, 0Dh
0x1800bc3c3  lea     r8, WPP_c409c363c67d3d5c7a2e7a93c81b5aa4_Traceguids
0x1800bc3ca  mov     ecx, 403h
0x1800bc3cf  mov     r9d, edi
0x1800bc3d2  call    WPP_SF_d
0x1800bc3d7  jmp     loc_1800BC00F
0x1800bc3dc  mov     [rbp+37h+var_8C], 46Ch
  ... truncated ...
```
