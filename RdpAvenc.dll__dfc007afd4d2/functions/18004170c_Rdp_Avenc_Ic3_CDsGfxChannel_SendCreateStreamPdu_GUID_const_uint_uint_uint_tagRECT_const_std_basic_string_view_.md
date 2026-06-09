# Rdp::Avenc::Ic3::CDsGfxChannel::SendCreateStreamPdu(_GUID const &,uint,uint,uint,tagRECT const &,std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x18004170c`
- end: `0x180041acd`
- name: `?SendCreateStreamPdu@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJAEBU_GUID@@IIIAEBUtagRECT@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z`
- size: `961`
- prototype: `__int64 __fastcall(__int64, __int128 *, unsigned int, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18003f2f0`

## callees

- `0x180003f0c`
- `0x180006580`
- `0x180006f8a`
- `0x180007018`
- `0x1800072b0`
- `0x18000e848`
- `0x180018d88`
- `0x18004170c`
- `0x180082e90`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180041a0e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180041a1c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180041a0e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180041a1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180041752`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180041752`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004177d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004177d`

## string_xrefs

- `0x18004184f`: `SendCreateStreamPdu`
- `0x180041a6e`: `Failed to send RDPDSGFX_PDU_CMDID_STREAMCREATE PDU`
- `0x18004185e`: `Rdp::Avenc::Ic3::CDsGfxChannel::SendCreateStreamPdu`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Rdp::Avenc::Ic3::CDsGfxChannel::SendCreateStreamPdu(
        __int64 a1,
        __int128 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  char v7; // r13
  __int64 v10; // rbx
  int v11; // r8d
  const char *v12; // r9
  __int64 result; // rax
  __int64 v14; // rcx
  unsigned int v15; // edi
  unsigned int *v16; // r14
  unsigned int v17; // r8d
  int v18; // r9d
  unsigned int v19; // ecx
  void *v20; // rcx
  unsigned __int64 v21; // r15
  const char *v22; // rdi
  char *v23; // [rsp+28h] [rbp-D0h]
  char *v24; // [rsp+28h] [rbp-D0h]
  int v27; // [rsp+78h] [rbp-80h] BYREF
  unsigned int v28; // [rsp+7Ch] [rbp-7Ch] BYREF
  unsigned int v29; // [rsp+80h] [rbp-78h] BYREF
  int v30; // [rsp+84h] [rbp-74h] BYREF
  const char *v31; // [rsp+88h] [rbp-70h] BYREF
  __int128 *v32; // [rsp+90h] [rbp-68h] BYREF
  __int64 v33; // [rsp+98h] [rbp-60h] BYREF
  const char *v34; // [rsp+A0h] [rbp-58h] BYREF
  _QWORD v35[2]; // [rsp+A8h] [rbp-50h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v7 = a3;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 120));
  try
  {
    v10 = *(_QWORD *)(a1 + 112);
    v35[1] = v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    ReleaseSRWLockShared((PSRWLOCK)(a1 + 120));
    if ( !v10 )
      return 2147549183LL;
    if ( *(_QWORD *)(a7 + 8) > 0xFFu )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
        (const char *)0x80070057LL,
        (int)"Channel name too long",
        v23);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return 2147942487LL;
    }
    v36 = *a2;
    HIBYTE(v36) = v7;
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v28 = a5;
      v29 = a4;
      v32 = &v36;
      v14 = *(_QWORD *)(a1 + 152);
      v33 = *(_QWORD *)(v14 + 128);
      v30 = *(_DWORD *)(v14 + 136);
      v34 = "SendCreateStreamPdu";
      v35[0] = "Rdp::Avenc::Ic3::CDsGfxChannel::SendCreateStreamPdu";
      v27 = 241;
      v31 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B0209,
        v11,
        (_DWORD)v12,
        (__int64)&v31,
        (__int64)&v27,
        (__int64)v35,
        (__int64)&v34,
        (__int64)&v30,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v29,
        (__int64)&v28);
    }
    v15 = 52;
    if ( *(_BYTE *)(a1 + 144) && *(_QWORD *)(a7 + 8) )
      v15 = *(_DWORD *)(a7 + 8) + 53;
    v16 = (unsigned int *)operator new[](v15);
    memset_0(v16, 0, v15);
    v31 = (const char *)v16;
    *v16 = v15;
    v16[1] = 3;
    *(_OWORD *)(v16 + 2) = v36;
    v16[6] = a3;
    v16[7] = a4;
    v16[8] = a5;
    v17 = a6[1];
    v18 = a6[2] - *a6;
    v19 = a6[3] - v17;
    v16[9] = *a6;
    v16[10] = v17;
    v16[11] = v18;
    v16[12] = v19;
    if ( !*(_BYTE *)(a1 + 144) || !*(_QWORD *)(a7 + 8) )
      goto LABEL_24;
    *((_BYTE *)v16 + 52) = *(_BYTE *)(a7 + 8);
    v20 = (char *)v16 + 53;
    if ( v16 == (unsigned int *)-53LL )
      goto LABEL_22;
    v21 = v15 - 1 - 52LL;
    if ( *(_QWORD *)a7 && v21 >= *(_QWORD *)(a7 + 8) )
    {
      memcpy_0(v20, *(const void **)a7, *(_QWORD *)(a7 + 8));
LABEL_24:
      v22 = (const char *)(*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned int *, __int64, int, unsigned int, int, _QWORD))(*(_QWORD *)v10 + 24LL))(
                            v10,
                            v15,
                            v16,
                            2,
                            1,
                            v15,
                            3,
                            0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
        v22,
        (int)"Failed to send RDPDSGFX_PDU_CMDID_STREAMCREATE PDU",
        v24);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return (unsigned int)v22;
    }
    memset_0(v20, 0, v15 - 1 - 52LL);
    if ( !*(_QWORD *)a7 )
    {
LABEL_22:
      *(_DWORD *)_o__errno() = 22;
    }
    else
    {
      if ( v21 >= *(_QWORD *)(a7 + 8) )
        goto LABEL_24;
      *(_DWORD *)_o__errno() = 34;
    }
    invalid_parameter_noinfo();
    goto LABEL_24;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x117,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsgfxchannel.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18004170c  mov     [rsp+arg_10], rbx
0x180041711  push    rdi
0x180041712  push    r12
0x180041714  push    r13
0x180041716  push    r14
0x180041718  push    r15
0x18004171a  sub     rsp, 0D0h
0x180041721  mov     rax, cs:__security_cookie
0x180041728  xor     rax, rsp
0x18004172b  mov     [rsp+0F8h+var_30], rax
0x180041733  mov     [rsp+0F8h+var_84], r9d
0x180041738  mov     r13d, r8d
0x18004173b  mov     [rsp+0F8h+var_88], r8d
0x180041740  mov     r14, rdx
0x180041743  mov     r15, rcx
0x180041746  mov     r12, [rsp+0F8h+arg_30]
0x18004174e  add     rcx, 78h ; 'x'; SRWLock
0x180041752  call    cs:__imp_AcquireSRWLockShared
0x180041758  mov     rbx, [r15+70h]
0x18004175c  mov     [rsp+0F8h+var_48], rbx
0x180041764  test    rbx, rbx
0x180041767  jz      short loc_180041779
0x180041769  mov     rax, [rbx]
0x18004176c  mov     rcx, rbx
0x18004176f  mov     rax, [rax+8]
0x180041773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041778  nop
0x180041779  lea     rcx, [r15+78h]; SRWLock
0x18004177d  call    cs:__imp_ReleaseSRWLockShared
0x180041783  test    rbx, rbx
0x180041786  jnz     short loc_180041792
0x180041788  mov     eax, 8000FFFFh
0x18004178d  jmp     loc_180041AA3
0x180041792  cmp     qword ptr [r12+8], 0FFh
0x18004179b  jbe     short loc_1800417E2
0x18004179d  mov     rcx, [rsp+0F8h]; this
0x1800417a5  lea     rax, aChannelNameToo; "Channel name too long"
0x1800417ac  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1800417b1  mov     edi, 80070057h
0x1800417b6  mov     r9d, edi; char *
0x1800417b9  lea     r8, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800417c0  mov     edx, 0E3h; void *
0x1800417c5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800417ca  nop
0x1800417cb  mov     rdx, [rbx]
0x1800417ce  mov     rcx, rbx
0x1800417d1  mov     rax, [rdx+10h]
0x1800417d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417da  nop
0x1800417db  mov     eax, edi
0x1800417dd  jmp     loc_180041AA3
0x1800417e2  movups  xmm0, xmmword ptr [r14]
0x1800417e6  movdqu  [rsp+0F8h+var_40], xmm0
0x1800417ef  mov     byte ptr [rsp+0F8h+var_40+0Fh], r13b
0x1800417f7  mov     eax, cs:dword_1800C1058
0x1800417fd  cmp     eax, 4
0x180041800  jbe     loc_180041908
0x180041806  mov     eax, [rsp+0F8h+arg_20]
0x18004180d  mov     [rsp+0F8h+var_7C], eax
0x180041811  mov     eax, [rsp+0F8h+var_84]
0x180041815  mov     [rsp+0F8h+var_78], eax
0x18004181c  lea     rax, [rsp+0F8h+var_40]
0x180041824  mov     [rsp+0F8h+var_68], rax
0x18004182c  mov     rcx, [r15+98h]
0x180041833  mov     rax, [rcx+80h]
0x18004183a  mov     [rsp+0F8h+var_60], rax
0x180041842  mov     eax, [rcx+88h]
0x180041848  mov     [rsp+0F8h+var_74], eax
0x18004184f  lea     rax, aSendcreatestre; "SendCreateStreamPdu"
0x180041856  mov     [rsp+0F8h+var_58], rax
0x18004185e  lea     rax, aRdpAvencIc3Cds_6; "Rdp::Avenc::Ic3::CDsGfxChannel::SendCre"...
0x180041865  mov     [rsp+0F8h+var_50], rax
0x18004186d  mov     [rsp+0F8h+var_80], 0F1h
0x180041875  lea     r13, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004187c  mov     [rsp+0F8h+var_70], r13
0x180041884  lea     rax, [rsp+0F8h+var_7C]
0x180041889  mov     [rsp+0F8h+var_98], rax
0x18004188e  lea     rax, [rsp+0F8h+var_78]
0x180041896  mov     [rsp+0F8h+var_A0], rax
0x18004189b  lea     rax, [rsp+0F8h+var_68]
0x1800418a3  mov     [rsp+0F8h+var_A8], rax
0x1800418a8  lea     rax, [rsp+0F8h+var_60]
0x1800418b0  mov     [rsp+0F8h+var_B0], rax
0x1800418b5  lea     rax, [rsp+0F8h+var_74]
0x1800418bd  mov     [rsp+0F8h+var_B8], rax
0x1800418c2  lea     rax, [rsp+0F8h+var_58]
0x1800418ca  mov     [rsp+0F8h+var_C0], rax
0x1800418cf  lea     rax, [rsp+0F8h+var_50]
0x1800418d7  mov     [rsp+0F8h+var_C8], rax
0x1800418dc  lea     rax, [rsp+0F8h+var_80]
0x1800418e1  mov     [rsp+0F8h+var_D0], rax
0x1800418e6  lea     rax, [rsp+0F8h+var_70]
0x1800418ee  mov     qword ptr [rsp+0F8h+var_D8], rax
0x1800418f3  lea     rdx, byte_1800B0209
0x1800418fa  lea     rcx, dword_1800C1058
0x180041901  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041906  jmp     short loc_18004190F
0x180041908  lea     r13, aOnecoreuapTerm_52; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004190f  mov     edi, 34h ; '4'
0x180041914  cmp     byte ptr [r15+90h], 0
0x18004191c  jz      short loc_18004192E
0x18004191e  cmp     qword ptr [r12+8], 0
0x180041924  jz      short loc_18004192E
0x180041926  mov     edi, [r12+8]
0x18004192b  add     edi, 35h ; '5'
0x18004192e  mov     ecx, edi; unsigned __int64
0x180041930  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180041935  mov     r14, rax
0x180041938  mov     r8d, edi; Size
0x18004193b  xor     edx, edx; Val
0x18004193d  mov     rcx, rax; void *
0x180041940  call    memset_0
0x180041945  mov     [rsp+0F8h+var_70], r14
0x18004194d  mov     [r14], edi
0x180041950  mov     dword ptr [r14+4], 3
0x180041958  movups  xmm0, [rsp+0F8h+var_40]
0x180041960  movdqu  xmmword ptr [r14+8], xmm0
0x180041966  mov     eax, [rsp+0F8h+var_88]
0x18004196a  mov     [r14+18h], eax
0x18004196e  mov     eax, [rsp+0F8h+var_84]
0x180041972  mov     [r14+1Ch], eax
0x180041976  mov     eax, [rsp+0F8h+arg_20]
0x18004197d  mov     [r14+20h], eax
0x180041981  mov     rax, [rsp+0F8h+arg_28]
0x180041989  mov     edx, [rax]
0x18004198b  mov     r8d, [rax+4]
0x18004198f  mov     r9d, [rax+8]
0x180041993  sub     r9d, edx
0x180041996  mov     ecx, [rax+0Ch]
0x180041999  sub     ecx, r8d
0x18004199c  mov     [r14+24h], edx
0x1800419a0  mov     [r14+28h], r8d
0x1800419a4  mov     [r14+2Ch], r9d
0x1800419a8  mov     [r14+30h], ecx
0x1800419ac  cmp     byte ptr [r15+90h], 0
0x1800419b4  jz      short loc_180041A2D
0x1800419b6  cmp     qword ptr [r12+8], 0
0x1800419bc  jz      short loc_180041A2D
0x1800419be  mov     al, [r12+8]
0x1800419c3  mov     [r14+34h], al
0x1800419c7  lea     rcx, [r14+35h]; void *
0x1800419cb  test    rcx, rcx
0x1800419ce  jz      short loc_180041A1C
0x1800419d0  lea     r15d, [rdi-1]
0x1800419d4  add     r15, 0FFFFFFFFFFFFFFCCh
0x1800419d8  cmp     qword ptr [r12], 0
0x1800419dd  jz      short loc_1800419F6
0x1800419df  cmp     r15, [r12+8]
0x1800419e4  jb      short loc_1800419F6
0x1800419e6  mov     r8, [r12+8]; Size
0x1800419eb  mov     rdx, [r12]; Src
0x1800419ef  call    memcpy_0
0x1800419f4  jmp     short loc_180041A2D
0x1800419f6  mov     r8, r15; Size
0x1800419f9  xor     edx, edx; Val
0x1800419fb  call    memset_0
0x180041a00  cmp     qword ptr [r12], 0
0x180041a05  jz      short loc_180041A1C
0x180041a07  cmp     r15, [r12+8]
0x180041a0c  jnb     short loc_180041A2D
0x180041a0e  call    cs:__imp__o__errno
0x180041a14  mov     dword ptr [rax], 22h ; '"'
0x180041a1a  jmp     short loc_180041A28
0x180041a1c  call    cs:__imp__o__errno
0x180041a22  mov     dword ptr [rax], 16h
0x180041a28  call    _invalid_parameter_noinfo
0x180041a2d  mov     rax, [rbx]
0x180041a30  mov     [rsp+0F8h+var_C0], 0
0x180041a39  mov     dword ptr [rsp+0F8h+var_C8], 3
0x180041a41  mov     dword ptr [rsp+0F8h+var_D0], edi; char *
0x180041a45  mov     [rsp+0F8h+var_D8], 1
0x180041a4d  mov     r9d, 2
0x180041a53  mov     r8, r14
0x180041a56  mov     edx, edi
0x180041a58  mov     rcx, rbx
0x180041a5b  mov     rax, [rax+18h]
0x180041a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a64  mov     edi, eax
0x180041a66  mov     rcx, [rsp+0F8h]; this
0x180041a6e  lea     rax, aFailedToSendRd_0; "Failed to send RDPDSGFX_PDU_CMDID_STREA"...
0x180041a75  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180041a7a  mov     r9d, edi; char *
0x180041a7d  mov     r8, r13; unsigned int
0x180041a80  mov     edx, 111h; void *
0x180041a85  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180041a8a  nop
0x180041a8b  mov     rax, [rbx]
0x180041a8e  mov     rcx, rbx
0x180041a91  mov     rax, [rax+10h]
0x180041a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a9a  nop
0x180041a9b  mov     eax, edi
0x180041a9d  jmp     short loc_180041AA3
0x180041a9f  mov     eax, [rsp+0F8h+var_88]
0x180041aa3  mov     rcx, [rsp+0F8h+var_30]
0x180041aab  xor     rcx, rsp; StackCookie
0x180041aae  call    __security_check_cookie
0x180041ab3  mov     rbx, [rsp+0F8h+arg_10]
0x180041abb  add     rsp, 0D0h
0x180041ac2  pop     r15
0x180041ac4  pop     r14
0x180041ac6  pop     r13
0x180041ac8  pop     r12
0x180041aca  pop     rdi
0x180041acb  retn
```
