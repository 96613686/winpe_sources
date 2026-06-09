# CQPrivate::QMCreatePrivateQueue(wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,int)

- ea: `0x18001bba0`
- end: `0x18001c018`
- name: `?QMCreatePrivateQueue@CQPrivate@@QEAAJPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@H@Z`
- size: `1144`
- prototype: `__int64 __fastcall(CQPrivate *this, wchar_t *, void *, unsigned int, unsigned int *const, struct tagPROPVARIANT *const, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180036d10`

## callees

- `0x18000f35c`
- `0x180011578`
- `0x1800195a8`
- `0x18001b388`
- `0x18001b3f0`
- `0x18001ba30`
- `0x18001bba0`
- `0x18001d438`
- `0x18001d534`
- `0x18001d5e0`
- `0x1800205c8`
- `0x180029394`
- `0x18002c61c`
- `0x1800457e4`
- `0x18004599c`
- `0x18004d280`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18001be26`
- `msvcrt!free` at `0x18001be2f`
- `msvcrt!free` at `0x18001be93`
- `msvcrt!free` at `0x18001be9f`
- `msvcrt!free` at `0x18001beda`
- `msvcrt!free` at `0x18001bee6`
- `msvcrt!free` at `0x18001bf3b`
- `msvcrt!free` at `0x18001bf45`
- `msvcrt!free` at `0x18001bf7e`
- `msvcrt!free` at `0x18001bf88`
- `msvcrt!free` at `0x18001bfd1`
- `msvcrt!free` at `0x18001bfdb`
- `msvcrt!free` at `0x18001be26`
- `msvcrt!free` at `0x18001be2f`
- `msvcrt!free` at `0x18001be93`
- `msvcrt!free` at `0x18001be9f`
- `msvcrt!free` at `0x18001beda`
- `msvcrt!free` at `0x18001bee6`
- `msvcrt!free` at `0x18001bf3b`
- `msvcrt!free` at `0x18001bf45`
- `msvcrt!free` at `0x18001bf7e`
- `msvcrt!free` at `0x18001bf88`
- `msvcrt!free` at `0x18001bfd1`
- `msvcrt!free` at `0x18001bfdb`
- `mqsec!MQSec_GetDefaultPrivateQueueSecurityDescriptor` at `0x18001bdcc`
- `mqsec!MQSec_GetDefaultPrivateQueueSecurityDescriptor` at `0x18001bdcc`
- `mqsec!MQSec_GetLocalMachineSid` at `0x18001bdad`
- `mqsec!MQSec_GetLocalMachineSid` at `0x18001bdad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQPrivate::QMCreatePrivateQueue(
        CQPrivate *this,
        wchar_t *a2,
        void *a3,
        unsigned int a4,
        unsigned int *const a5,
        struct tagPROPVARIANT *const a6,
        int a7)
{
  CQPrivate *v10; // rcx
  unsigned __int64 v11; // r8
  unsigned __int16 v12; // r8
  int v13; // ebx
  int v14; // eax
  wchar_t *v15; // r8
  int DefaultPrivateQueueSecurityDescriptor; // eax
  CQPrivate *v17; // rcx
  int v18; // eax
  CQPrivate *v19; // rcx
  int NextPrivateQueueId; // eax
  CQPrivate *v21; // rcx
  __int64 v22; // r9
  struct tagPROPVARIANT *v23; // rsi
  int v24; // eax
  wchar_t *v25; // r8
  int v26; // eax
  CQueueMgr *v27; // rcx
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v31; // [rsp+60h] [rbp-A0h] BYREF
  struct tagPROPVARIANT *v32; // [rsp+68h] [rbp-98h] BYREF
  void *v33; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v34; // [rsp+78h] [rbp-88h] BYREF
  __int16 v35; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+82h] [rbp-7Eh]
  __int16 v37; // [rsp+86h] [rbp-7Ah]
  GUID v38; // [rsp+88h] [rbp-78h]
  unsigned int v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+9Ch] [rbp-64h]
  _BYTE v41[64]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v42[144]; // [rsp+E0h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  v29 = 0;
  if ( !IsPathnameForLocalMachine(a2, (int *)&v29) )
  {
    v12 = 50;
    v13 = -1072824300;
LABEL_6:
    LogMsgHR(v13, (wchar_t *)L"cqpriv", v12);
    return (unsigned int)v13;
  }
  if ( v29 )
  {
    v13 = ReplaceDNSNameWithNetBiosName(a2, v42, v11);
    if ( v13 < 0 )
    {
      v12 = 1107;
      goto LABEL_6;
    }
    a2 = v42;
  }
  if ( a7 )
  {
    CQMDSSecureableObject::CQMDSSecureableObject(v41, 1, &CQueueMgr::m_guidQmQueue);
    v14 = CSecureableObject::AccessCheck((CSecureableObject *)v41, 4u);
    v13 = v14;
    if ( v14 < 0 )
      LogMsgHR(v14, (wchar_t *)L"qmsecutl", 0x50u);
    CQMDSSecureableObject::~CQMDSSecureableObject((CQMDSSecureableObject *)v41);
    if ( v13 < 0 )
    {
      v12 = 60;
      goto LABEL_6;
    }
  }
  if ( CQPrivate::IsPrivateSysQueue(v10, a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v12 = 1108;
    v13 = -1072824315;
    goto LABEL_6;
  }
  v33 = 0;
  if ( (int)LQSOpen(a2, &v33, v15) < 0 )
  {
    v29 = 0;
    v34 = 0;
    v32 = 0;
    Block = 0;
    MQSec_GetLocalMachineSid(0, 0);
    DefaultPrivateQueueSecurityDescriptor = MQSec_GetDefaultPrivateQueueSecurityDescriptor(&Block, 1, a3);
    if ( DefaultPrivateQueueSecurityDescriptor >= 0 )
    {
      v18 = CQPrivate::SetQueueProperties(v17, a2, Block, a4, a5, a6, &v29, &v34, &v32);
      v13 = v18;
      if ( v18 >= 0 )
      {
        v31 = 0;
        NextPrivateQueueId = CQPrivate::GetNextPrivateQueueId(v19, &v31);
        v13 = NextPrivateQueueId;
        if ( NextPrivateQueueId >= 0 )
        {
          v23 = v32;
          v24 = CQPrivate::RegisterPrivateQueueProperties(v21, a2, v31, v22, v29, v34, v32);
          v13 = v24;
          if ( v24 >= 0 )
          {
            v26 = LQSOpen(a2, &v33, v25);
            v13 = v26;
            if ( v26 >= 0 )
            {
              v36 = 0;
              v37 = 0;
              v40 = 0;
              v35 = 2;
              v38 = CQueueMgr::m_guidQmQueue;
              v39 = v31;
              CQueueMgr::UpdateQueueProperties(v27, (const struct QUEUE_FORMAT *)&v35, a4, a5, a6);
            }
            else
            {
              LogMsgHR(v26, (wchar_t *)L"cqpriv", 0x6Fu);
            }
            free(Block);
            free(v23);
          }
          else
          {
            LogMsgHR(v24, (wchar_t *)L"cqpriv", 0x6Eu);
            free(Block);
            free(v23);
          }
        }
        else
        {
          LogMsgHR(NextPrivateQueueId, (wchar_t *)L"cqpriv", 0x64u);
          free(Block);
          free(v32);
        }
      }
      else
      {
        LogMsgHR(v18, (wchar_t *)L"cqpriv", 0x5Au);
        free(Block);
        free(v32);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids,
          (unsigned int)DefaultPrivateQueueSecurityDescriptor);
      v13 = -1072824281;
      LogMsgHR(-1072824281, (wchar_t *)L"cqpriv", 0x456u);
      free(Block);
      free(0);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = -1072824315;
    LogMsgHR(-1072824315, (wchar_t *)L"cqpriv", 0x455u);
  }
  CHLQS::~CHLQS((CHLQS *)&v33);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001bba0  mov     [rsp-8+arg_0], rbx
0x18001bba5  push    rbp
0x18001bba6  push    rsi
0x18001bba7  push    rdi
0x18001bba8  push    r12
0x18001bbaa  push    r13
0x18001bbac  push    r14
0x18001bbae  push    r15
0x18001bbb0  lea     rbp, [rsp-110h]
0x18001bbb8  sub     rsp, 210h
0x18001bbbf  mov     rax, cs:__security_cookie
0x18001bbc6  xor     rax, rsp
0x18001bbc9  mov     [rbp+140h+var_40], rax
0x18001bbd0  mov     r14d, r9d
0x18001bbd3  mov     rsi, r8
0x18001bbd6  mov     rdi, rdx
0x18001bbd9  mov     r15, [rbp+140h+arg_20]
0x18001bbe0  mov     r12, [rbp+140h+arg_28]
0x18001bbe7  lea     rax, WPP_GLOBAL_Control
0x18001bbee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbf5  cmp     rcx, rax
0x18001bbf8  jz      short loc_18001BC18
0x18001bbfa  test    byte ptr [rcx+1Ch], 4
0x18001bbfe  jz      short loc_18001BC18
0x18001bc00  mov     edx, 0Dh
0x18001bc05  mov     r9, rdi
0x18001bc08  lea     r8, WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids
0x18001bc0f  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bc13  call    WPP_SF_S
0x18001bc18  xor     r13d, r13d
0x18001bc1b  mov     [rsp+240h+var_1F0], r13d
0x18001bc20  lea     rdx, [rsp+240h+var_1F0]; int *
0x18001bc25  mov     rcx, rdi; wchar_t *
0x18001bc28  call    ?IsPathnameForLocalMachine@@YAHPEB_WPEAH@Z; IsPathnameForLocalMachine(wchar_t const *,int *)
0x18001bc2d  test    eax, eax
0x18001bc2f  jnz     short loc_18001BC4D
0x18001bc31  lea     r8d, [r13+32h]; unsigned __int16
0x18001bc35  mov     ebx, 0C00E0014h
0x18001bc3a  lea     rdx, aCqpriv; "cqpriv"
0x18001bc41  mov     ecx, ebx; int
0x18001bc43  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001bc48  jmp     loc_18001BFEC
0x18001bc4d  cmp     [rsp+240h+var_1F0], r13d
0x18001bc52  jz      short loc_18001BC72
0x18001bc54  lea     rdx, [rbp+140h+var_160]; wchar_t *
0x18001bc58  mov     rcx, rdi; wchar_t *
0x18001bc5b  call    ?ReplaceDNSNameWithNetBiosName@@YAJPEB_WPEA_W_K@Z; ReplaceDNSNameWithNetBiosName(wchar_t const *,wchar_t *,unsigned __int64)
0x18001bc60  mov     ebx, eax
0x18001bc62  test    eax, eax
0x18001bc64  jns     short loc_18001BC6E
0x18001bc66  mov     r8d, 453h
0x18001bc6c  jmp     short loc_18001BC3A
0x18001bc6e  lea     rdi, [rbp+140h+var_160]
0x18001bc72  cmp     [rbp+140h+arg_30], r13d
0x18001bc79  jz      short loc_18001BCE3
0x18001bc7b  mov     rax, cs:?g_szMachineName@@3PEA_WEA; wchar_t * g_szMachineName
0x18001bc82  mov     [rsp+240h+var_218], rax
0x18001bc87  mov     dword ptr [rsp+240h+var_220], r13d
0x18001bc8c  lea     r8, ?m_guidQmQueue@CQueueMgr@@0U_GUID@@A; _GUID CQueueMgr::m_guidQmQueue
0x18001bc93  mov     edx, 1
0x18001bc98  lea     rcx, [rbp+140h+var_1A0]
0x18001bc9c  call    ??0CQMDSSecureableObject@@QEAA@W4AD_OBJECT@@PEBU_GUID@@HHPEB_W@Z; CQMDSSecureableObject::CQMDSSecureableObject(AD_OBJECT,_GUID const *,int,int,wchar_t const *)
0x18001bca1  nop
0x18001bca2  mov     edx, 4; unsigned int
0x18001bca7  lea     rcx, [rbp+140h+var_1A0]; this
0x18001bcab  call    ?AccessCheck@CSecureableObject@@QEAAJK@Z; CSecureableObject::AccessCheck(ulong)
0x18001bcb0  mov     ebx, eax
0x18001bcb2  test    eax, eax
0x18001bcb4  jns     short loc_18001BCCB
0x18001bcb6  mov     r8d, 50h ; 'P'; unsigned __int16
0x18001bcbc  lea     rdx, aQmsecutl; "qmsecutl"
0x18001bcc3  mov     ecx, eax; int
0x18001bcc5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001bcca  nop
0x18001bccb  lea     rcx, [rbp+140h+var_1A0]; this
0x18001bccf  call    ??1CQMDSSecureableObject@@QEAA@XZ; CQMDSSecureableObject::~CQMDSSecureableObject(void)
0x18001bcd4  test    ebx, ebx
0x18001bcd6  jns     short loc_18001BCE3
0x18001bcd8  mov     r8d, 3Ch ; '<'
0x18001bcde  jmp     loc_18001BC3A
0x18001bce3  mov     rdx, rdi; wchar_t *
0x18001bce6  call    ?IsPrivateSysQueue@CQPrivate@@QEAAHPEB_W@Z; CQPrivate::IsPrivateSysQueue(wchar_t const *)
0x18001bceb  test    eax, eax
0x18001bced  jz      short loc_18001BD30
0x18001bcef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcf6  lea     rdx, WPP_GLOBAL_Control
0x18001bcfd  cmp     rcx, rdx
0x18001bd00  jz      short loc_18001BD20
0x18001bd02  test    byte ptr [rcx+1Ch], 2
0x18001bd06  jz      short loc_18001BD20
0x18001bd08  mov     edx, 0Eh
0x18001bd0d  mov     r9, rdi
0x18001bd10  lea     r8, WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids
0x18001bd17  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bd1b  call    WPP_SF_S
0x18001bd20  mov     r8d, 454h
0x18001bd26  mov     ebx, 0C00E0005h
0x18001bd2b  jmp     loc_18001BC3A
0x18001bd30  mov     [rsp+240h+var_1D0], r13
0x18001bd35  lea     rdx, [rsp+240h+var_1D0]; void **
0x18001bd3a  mov     rcx, rdi; wchar_t *
0x18001bd3d  call    ?LQSOpen@@YAJPEB_WPEAPEAXPEA_W@Z; LQSOpen(wchar_t const *,void * *,wchar_t *)
0x18001bd42  test    eax, eax
0x18001bd44  js      short loc_18001BD95
0x18001bd46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd4d  lea     rdx, WPP_GLOBAL_Control
0x18001bd54  cmp     rcx, rdx
0x18001bd57  jz      short loc_18001BD77
0x18001bd59  test    byte ptr [rcx+1Ch], 2
0x18001bd5d  jz      short loc_18001BD77
0x18001bd5f  mov     edx, 0Fh
0x18001bd64  mov     r9, rdi
0x18001bd67  lea     r8, WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids
0x18001bd6e  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bd72  call    WPP_SF_S
0x18001bd77  mov     r8d, 455h; unsigned __int16
0x18001bd7d  lea     rdx, aCqpriv; "cqpriv"
0x18001bd84  mov     ebx, 0C00E0005h
0x18001bd89  mov     ecx, ebx; int
0x18001bd8b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001bd90  jmp     loc_18001BFE2
0x18001bd95  mov     [rsp+240h+var_1F0], r13d
0x18001bd9a  mov     [rsp+240h+var_1C8], r13
0x18001bd9f  mov     [rsp+240h+var_1D8], r13
0x18001bda4  mov     [rsp+240h+Block], r13
0x18001bda9  xor     edx, edx
0x18001bdab  xor     ecx, ecx
0x18001bdad  call    cs:__imp_?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z; MQSec_GetLocalMachineSid(int,ulong *)
0x18001bdb3  mov     [rsp+240h+var_218], rax
0x18001bdb8  mov     dword ptr [rsp+240h+var_220], r13d
0x18001bdbd  xor     r9d, r9d
0x18001bdc0  mov     r8, rsi
0x18001bdc3  lea     edx, [r9+1]
0x18001bdc7  lea     rcx, [rsp+240h+Block]
0x18001bdcc  call    cs:__imp_?MQSec_GetDefaultPrivateQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z; MQSec_GetDefaultPrivateQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)
0x18001bdd2  test    eax, eax
0x18001bdd4  jns     short loc_18001BE3B
0x18001bdd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bddd  lea     rdx, WPP_GLOBAL_Control
0x18001bde4  cmp     rcx, rdx
0x18001bde7  jz      short loc_18001BE07
0x18001bde9  test    byte ptr [rcx+1Ch], 1
0x18001bded  jz      short loc_18001BE07
0x18001bdef  mov     edx, 10h
0x18001bdf4  mov     r9d, eax
0x18001bdf7  lea     r8, WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids
0x18001bdfe  mov     rcx, [rcx+10h]
0x18001be02  call    WPP_SF_d
0x18001be07  mov     r8d, 456h; unsigned __int16
0x18001be0d  lea     rdx, aCqpriv; "cqpriv"
0x18001be14  mov     ebx, 0C00E0027h
0x18001be19  mov     ecx, ebx; int
0x18001be1b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001be20  nop
0x18001be21  mov     rcx, [rsp+240h+Block]; Block
0x18001be26  call    cs:__imp_free
0x18001be2c  nop
0x18001be2d  xor     ecx, ecx; Block
0x18001be2f  call    cs:__imp_free
0x18001be35  nop
0x18001be36  jmp     loc_18001BFE2
0x18001be3b  lea     rax, [rsp+240h+var_1D8]
0x18001be40  mov     [rsp+240h+var_200], rax; struct tagPROPVARIANT **
0x18001be45  lea     rax, [rsp+240h+var_1C8]
0x18001be4a  mov     [rsp+240h+var_208], rax; unsigned int **
0x18001be4f  lea     rax, [rsp+240h+var_1F0]
0x18001be54  mov     [rsp+240h+var_210], rax; unsigned int *
0x18001be59  mov     [rsp+240h+var_218], r12; struct tagPROPVARIANT *
0x18001be5e  mov     [rsp+240h+var_220], r15; unsigned int *
0x18001be63  mov     r9d, r14d; unsigned int
0x18001be66  mov     r8, [rsp+240h+Block]; void *
0x18001be6b  mov     rdx, rdi; wchar_t *
0x18001be6e  call    ?SetQueueProperties@CQPrivate@@AEAAJPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@PEAKPEAPEAKPEAPEAU2@@Z; CQPrivate::SetQueueProperties(wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,ulong *,ulong * *,tagPROPVARIANT * *)
0x18001be73  mov     ebx, eax
0x18001be75  test    eax, eax
0x18001be77  jns     short loc_18001BEAB
0x18001be79  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x18001be7f  lea     rdx, aCqpriv; "cqpriv"
0x18001be86  mov     ecx, eax; int
0x18001be88  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001be8d  nop
0x18001be8e  mov     rcx, [rsp+240h+Block]; Block
0x18001be93  call    cs:__imp_free
0x18001be99  nop
0x18001be9a  mov     rcx, [rsp+240h+var_1D8]; Block
0x18001be9f  call    cs:__imp_free
0x18001bea5  nop
0x18001bea6  jmp     loc_18001BFE2
0x18001beab  mov     [rsp+240h+var_1E0], r13d
0x18001beb0  lea     rdx, [rsp+240h+var_1E0]; unsigned int *
0x18001beb5  call    ?GetNextPrivateQueueId@CQPrivate@@AEAAJPEAK@Z; CQPrivate::GetNextPrivateQueueId(ulong *)
0x18001beba  mov     ebx, eax
0x18001bebc  test    eax, eax
0x18001bebe  jns     short loc_18001BEF2
0x18001bec0  mov     r8d, 64h ; 'd'; unsigned __int16
0x18001bec6  lea     rdx, aCqpriv; "cqpriv"
0x18001becd  mov     ecx, eax; int
0x18001becf  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001bed4  nop
0x18001bed5  mov     rcx, [rsp+240h+Block]; Block
0x18001beda  call    cs:__imp_free
0x18001bee0  nop
0x18001bee1  mov     rcx, [rsp+240h+var_1D8]; Block
0x18001bee6  call    cs:__imp_free
0x18001beec  nop
0x18001beed  jmp     loc_18001BFE2
0x18001bef2  mov     rsi, [rsp+240h+var_1D8]
0x18001bef7  mov     [rsp+240h+var_210], rsi; struct tagPROPVARIANT *
0x18001befc  mov     rax, [rsp+240h+var_1C8]
0x18001bf01  mov     [rsp+240h+var_218], rax; unsigned int *
0x18001bf06  mov     eax, [rsp+240h+var_1F0]
0x18001bf0a  mov     dword ptr [rsp+240h+var_220], eax; unsigned int
0x18001bf0e  mov     r8d, [rsp+240h+var_1E0]; unsigned int
0x18001bf13  mov     rdx, rdi; wchar_t *
0x18001bf16  call    ?RegisterPrivateQueueProperties@CQPrivate@@AEAAJPEB_WKEKQEAKQEAUtagPROPVARIANT@@@Z; CQPrivate::RegisterPrivateQueueProperties(wchar_t const *,ulong,uchar,ulong,ulong * const,tagPROPVARIANT * const)
0x18001bf1b  mov     ebx, eax
0x18001bf1d  test    eax, eax
0x18001bf1f  jns     short loc_18001BF51
0x18001bf21  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x18001bf27  lea     rdx, aCqpriv; "cqpriv"
0x18001bf2e  mov     ecx, eax; int
0x18001bf30  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001bf35  nop
0x18001bf36  mov     rcx, [rsp+240h+Block]; Block
0x18001bf3b  call    cs:__imp_free
0x18001bf41  nop
0x18001bf42  mov     rcx, rsi; Block
0x18001bf45  call    cs:__imp_free
0x18001bf4b  nop
0x18001bf4c  jmp     loc_18001BFE2
0x18001bf51  lea     rdx, [rsp+240h+var_1D0]; void **
0x18001bf56  mov     rcx, rdi; wchar_t *
0x18001bf59  call    ?LQSOpen@@YAJPEB_WPEAPEAXPEA_W@Z; LQSOpen(wchar_t const *,void * *,wchar_t *)
0x18001bf5e  mov     ebx, eax
0x18001bf60  test    eax, eax
0x18001bf62  jns     short loc_18001BF91
0x18001bf64  mov     r8d, 6Fh ; 'o'; unsigned __int16
0x18001bf6a  lea     rdx, aCqpriv; "cqpriv"
0x18001bf71  mov     ecx, eax; int
0x18001bf73  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001bf78  nop
0x18001bf79  mov     rcx, [rsp+240h+Block]; Block
0x18001bf7e  call    cs:__imp_free
0x18001bf84  nop
0x18001bf85  mov     rcx, rsi; Block
0x18001bf88  call    cs:__imp_free
0x18001bf8e  nop
0x18001bf8f  jmp     short loc_18001BFE2
0x18001bf91  mov     [rbp+140h+var_1BE], r13d
0x18001bf95  mov     [rbp+140h+var_1BA], r13w
0x18001bf9a  mov     [rbp+140h+var_1A4], r13d
0x18001bf9e  mov     [rbp+140h+var_1C0], 2
0x18001bfa4  movups  xmm0, xmmword ptr cs:?m_guidQmQueue@CQueueMgr@@0U_GUID@@A.Data1; _GUID CQueueMgr::m_guidQmQueue ...
0x18001bfab  movdqu  [rbp+140h+var_1B8], xmm0
0x18001bfb0  mov     eax, [rsp+240h+var_1E0]
0x18001bfb4  mov     [rbp+140h+var_1A8], eax
0x18001bfb7  mov     [rsp+240h+var_220], r12; struct tagPROPVARIANT *
0x18001bfbc  mov     r9, r15; unsigned int *
0x18001bfbf  mov     r8d, r14d; unsigned int
0x18001bfc2  lea     rdx, [rbp+140h+var_1C0]; struct QUEUE_FORMAT *
0x18001bfc6  call    ?UpdateQueueProperties@CQueueMgr@@QEAAXPEBUQUEUE_FORMAT@@KQEAKQEAUtagPROPVARIANT@@@Z; CQueueMgr::UpdateQueueProperties(QUEUE_FORMAT const *,ulong,ulong * const,tagPROPVARIANT * const)
0x18001bfcb  nop
0x18001bfcc  mov     rcx, [rsp+240h+Block]; Block
0x18001bfd1  call    cs:__imp_free
0x18001bfd7  nop
0x18001bfd8  mov     rcx, rsi; Block
0x18001bfdb  call    cs:__imp_free
0x18001bfe1  nop
0x18001bfe2  lea     rcx, [rsp+240h+var_1D0]; this
0x18001bfe7  call    ??1CHLQS@@QEAA@XZ; CHLQS::~CHLQS(void)
0x18001bfec  mov     eax, ebx
0x18001bfee  mov     rcx, [rbp+140h+var_40]
0x18001bff5  xor     rcx, rsp; StackCookie
0x18001bff8  call    __security_check_cookie
0x18001bffd  mov     rbx, [rsp+240h+arg_0]
0x18001c005  add     rsp, 210h
0x18001c00c  pop     r15
0x18001c00e  pop     r14
0x18001c010  pop     r13
0x18001c012  pop     r12
0x18001c014  pop     rdi
0x18001c015  pop     rsi
0x18001c016  pop     rbp
0x18001c017  retn
```
