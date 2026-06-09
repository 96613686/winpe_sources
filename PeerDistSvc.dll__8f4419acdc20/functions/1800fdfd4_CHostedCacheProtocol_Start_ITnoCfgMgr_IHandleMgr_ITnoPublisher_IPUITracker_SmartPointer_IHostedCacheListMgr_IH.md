# CHostedCacheProtocol::Start(ITnoCfgMgr *,IHandleMgr *,ITnoPublisher *,IPUITracker *,SmartPointer<IHostedCacheListMgr> &,IHostedCacheReqNotification *,bool)

- ea: `0x1800fdfd4`
- end: `0x1800fe3a4`
- name: `?Start@CHostedCacheProtocol@@QEAAJPEAVITnoCfgMgr@@PEAVIHandleMgr@@PEAVITnoPublisher@@PEAVIPUITracker@@AEAV?$SmartPointer@VIHostedCacheListMgr@@@@PEAVIHostedCacheReqNotification@@_N@Z`
- size: `976`
- prototype: `__int64 __usercall@<rax>(CHostedCacheProtocol *this@<rcx>, struct ITnoCfgMgr *@<rdx>, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f0c50`

## callees

- `0x1800034a4`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x1800f64a4`
- `0x1800fb19c`
- `0x1800fbaec`
- `0x1800fdfd4`
- `0x1800fe3ac`
- `0x1800fe7bc`
- `0x180144882`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe14a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe14a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe211`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800fe1af`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800fe1ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800fe1af`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800fe1ff`
- `WS2_32!__imp_WSAStartup` at `0x1800fe140`
- `WS2_32!__imp_WSAStartup` at `0x1800fe140`

## pseudocode

```c
__int64 __fastcall CHostedCacheProtocol::Start(
        CHostedCacheProtocol *this,
        struct ITnoCfgMgr *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        char a8)
{
  signed int Settings; // ebx
  CHostedCacheMsgEncoding *v14; // rcx
  __int64 v15; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_TIMER v17; // rax
  __int16 v18; // si
  _WORD *v19; // rbx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  CHostedCacheMsgEncoding *v21; // rcx
  __int64 v22; // rdx
  _BYTE v23[32]; // [rsp+20h] [rbp-218h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-1F8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_54be81ea90983cb591d6a2d511652152_Traceguids);
  }
  if ( !a2 || !a3 || !a4 || !a5 || !*a6 )
    return 2147500035LL;
  if ( a8 )
  {
    if ( a7 )
    {
LABEL_12:
      InCritSec::InCritSec((InCritSec *)v23, this, 1);
      *((_BYTE *)this + 144) = a8;
      SmartPointer<IHostedCacheListMgr>::operator=((char *)this + 88, *a6);
      *((_QWORD *)this + 6) = a2;
      *((_QWORD *)this + 7) = a3;
      *((_QWORD *)this + 8) = a4;
      *((_QWORD *)this + 9) = a5;
      *((_QWORD *)this + 10) = a7;
      Settings = CHostedCacheProtocol::RetrieveSettings(this, a2);
      if ( Settings < 0 )
        goto LABEL_13;
      Settings = CHostedCacheProtocol::RefreshHostedCacheList(this);
      if ( Settings < 0 )
        goto LABEL_13;
      if ( !a8 && !*((_QWORD *)this + 15) )
      {
        Settings = -2147020833;
        goto LABEL_13;
      }
      if ( WSAStartup(0x202u, &WSAData) )
      {
        Settings = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_26;
        }
        v15 = 11;
      }
      else
      {
        ThreadpoolTimer = CreateThreadpoolTimer(HostedCacheProtocolTimerCallback, this, 0);
        *((_QWORD *)this + 102) = ThreadpoolTimer;
        if ( ThreadpoolTimer )
        {
          v17 = CreateThreadpoolTimer(HostedCacheProtocolBatchingIdleTimerCallback, this, 0);
          *((_QWORD *)this + 139) = v17;
          if ( v17 )
          {
            v18 = *((_WORD *)this + 344);
            v19 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
            if ( v19 )
            {
              v19[4] = v18;
              *(_QWORD *)v19 = &CHostedCacheMsgEncoding::`vftable';
            }
            else
            {
              v19 = 0;
            }
            v20 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 129);
            if ( v19 != (_WORD *)v20 && v20 )
              (**v20)(v20, 1);
            *((_QWORD *)this + 129) = v19;
            Settings = CHostedCacheProtocol::StartSecureHttpTransport(this);
            if ( Settings >= 0 )
            {
              Settings = CHostedCacheProtocol::StartHttpTransport(this);
              if ( Settings >= 0 )
              {
                v21 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 105) < 4u )
                {
                  goto LABEL_13;
                }
                v22 = 16;
              }
              else
              {
                v21 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_13;
                }
                v22 = 15;
              }
            }
            else
            {
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                goto LABEL_13;
              }
              v22 = 14;
            }
            WPP_SF_d(
              *((_QWORD *)v21 + 12),
              v22,
              WPP_54be81ea90983cb591d6a2d511652152_Traceguids,
              (unsigned int)Settings);
LABEL_13:
            InCritSec::~InCritSec((InCritSec *)v23);
            return (unsigned int)Settings;
          }
          Settings = GetLastError();
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
LABEL_26:
            if ( Settings > 0 )
              Settings = (unsigned __int16)Settings | 0x80070000;
            goto LABEL_13;
          }
          v15 = 13;
        }
        else
        {
          Settings = GetLastError();
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_26;
          }
          v15 = 12;
        }
      }
      WPP_SF_d(*((_QWORD *)v14 + 12), v15, WPP_54be81ea90983cb591d6a2d511652152_Traceguids, (unsigned int)Settings);
      goto LABEL_26;
    }
    return 2147500035LL;
  }
  if ( !a7 )
    goto LABEL_12;
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800fdfd4  push    rbx
0x1800fdfd6  push    rbp
0x1800fdfd7  push    rsi
0x1800fdfd8  push    rdi
0x1800fdfd9  push    r12
0x1800fdfdb  push    r13
0x1800fdfdd  push    r14
0x1800fdfdf  push    r15
0x1800fdfe1  sub     rsp, 1F8h
0x1800fdfe8  mov     rax, cs:__security_cookie
0x1800fdfef  xor     rax, rsp
0x1800fdff2  mov     [rsp+238h+var_58], rax
0x1800fdffa  mov     r13, [rsp+238h+arg_28]
0x1800fe002  mov     r12, r8
0x1800fe005  mov     r14, rdx
0x1800fe008  mov     rdi, rcx
0x1800fe00b  xor     edx, edx; Val
0x1800fe00d  lea     rcx, [rsp+238h+WSAData]; void *
0x1800fe012  mov     r8d, 198h; Size
0x1800fe018  mov     r15, r9
0x1800fe01b  call    memset_0
0x1800fe020  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe027  lea     rax, WPP_GLOBAL_Control
0x1800fe02e  cmp     rcx, rax
0x1800fe031  jz      short loc_1800FE057
0x1800fe033  test    dword ptr [rcx+6Ch], 1000h
0x1800fe03a  jz      short loc_1800FE057
0x1800fe03c  cmp     byte ptr [rcx+69h], 4
0x1800fe040  jb      short loc_1800FE057
0x1800fe042  mov     rcx, [rcx+60h]
0x1800fe046  lea     r8, WPP_54be81ea90983cb591d6a2d511652152_Traceguids
0x1800fe04d  mov     edx, 0Ah
0x1800fe052  call    WPP_SF_
0x1800fe057  test    r14, r14
0x1800fe05a  jz      loc_1800FE37B
0x1800fe060  test    r12, r12
0x1800fe063  jz      loc_1800FE37B
0x1800fe069  test    r15, r15
0x1800fe06c  jz      loc_1800FE37B
0x1800fe072  mov     rbp, [rsp+238h+arg_20]
0x1800fe07a  test    rbp, rbp
0x1800fe07d  jz      loc_1800FE37B
0x1800fe083  cmp     qword ptr [r13+0], 0
0x1800fe088  jz      loc_1800FE37B
0x1800fe08e  mov     sil, [rsp+238h+arg_38]
0x1800fe096  mov     rbx, [rsp+238h+arg_30]
0x1800fe09e  test    sil, sil
0x1800fe0a1  jz      short loc_1800FE106
0x1800fe0a3  test    rbx, rbx
0x1800fe0a6  jz      loc_1800FE37B
0x1800fe0ac  mov     r8b, 1; bool
0x1800fe0af  lea     rcx, [rsp+238h+var_218]; this
0x1800fe0b4  mov     rdx, rdi; struct CritSec *
0x1800fe0b7  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800fe0bc  mov     [rdi+90h], sil
0x1800fe0c3  lea     rcx, [rdi+58h]
0x1800fe0c7  mov     rdx, [r13+0]
0x1800fe0cb  call    ??4?$SmartPointer@VIHostedCacheListMgr@@@@QEAAAEAV0@PEAVIHostedCacheListMgr@@@Z; SmartPointer<IHostedCacheListMgr>::operator=(IHostedCacheListMgr *)
0x1800fe0d0  mov     rdx, r14; struct ITnoCfgMgr *
0x1800fe0d3  mov     [rdi+30h], r14
0x1800fe0d7  mov     rcx, rdi; this
0x1800fe0da  mov     [rdi+38h], r12
0x1800fe0de  mov     [rdi+40h], r15
0x1800fe0e2  mov     [rdi+48h], rbp
0x1800fe0e6  mov     [rdi+50h], rbx
0x1800fe0ea  call    ?RetrieveSettings@CHostedCacheProtocol@@AEAAJPEAVITnoCfgMgr@@@Z; CHostedCacheProtocol::RetrieveSettings(ITnoCfgMgr *)
0x1800fe0ef  mov     ebx, eax
0x1800fe0f1  test    eax, eax
0x1800fe0f3  jns     short loc_1800FE115
0x1800fe0f5  lea     rcx, [rsp+238h+var_218]; this
0x1800fe0fa  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800fe0ff  mov     eax, ebx
0x1800fe101  jmp     loc_1800FE380
0x1800fe106  test    rbx, rbx
0x1800fe109  jz      short loc_1800FE0AC
0x1800fe10b  mov     eax, 80070057h
0x1800fe110  jmp     loc_1800FE380
0x1800fe115  mov     rcx, rdi; this
0x1800fe118  call    ?RefreshHostedCacheList@CHostedCacheProtocol@@QEAAJXZ; CHostedCacheProtocol::RefreshHostedCacheList(void)
0x1800fe11d  mov     ebx, eax
0x1800fe11f  test    eax, eax
0x1800fe121  js      short loc_1800FE0F5
0x1800fe123  test    sil, sil
0x1800fe126  jnz     short loc_1800FE136
0x1800fe128  cmp     qword ptr [rdi+78h], 0
0x1800fe12d  jnz     short loc_1800FE136
0x1800fe12f  mov     ebx, 80070FDFh
0x1800fe134  jmp     short loc_1800FE0F5
0x1800fe136  mov     ecx, 202h; wVersionRequested
0x1800fe13b  lea     rdx, [rsp+238h+WSAData]; lpWSAData
0x1800fe140  call    cs:__imp_WSAStartup
0x1800fe146  test    eax, eax
0x1800fe148  jz      short loc_1800FE1A2
0x1800fe14a  call    cs:__imp_GetLastError
0x1800fe150  mov     ebx, eax
0x1800fe152  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe159  lea     rax, WPP_GLOBAL_Control
0x1800fe160  cmp     rcx, rax
0x1800fe163  jz      short loc_1800FE18C
0x1800fe165  test    dword ptr [rcx+6Ch], 1000h
0x1800fe16c  jz      short loc_1800FE18C
0x1800fe16e  cmp     byte ptr [rcx+69h], 1
0x1800fe172  jb      short loc_1800FE18C
0x1800fe174  mov     edx, 0Bh
0x1800fe179  mov     rcx, [rcx+60h]
0x1800fe17d  lea     r8, WPP_54be81ea90983cb591d6a2d511652152_Traceguids
0x1800fe184  mov     r9d, ebx
0x1800fe187  call    WPP_SF_d
0x1800fe18c  test    ebx, ebx
0x1800fe18e  jle     loc_1800FE0F5
0x1800fe194  movzx   ebx, bx
0x1800fe197  or      ebx, 80070000h
0x1800fe19d  jmp     loc_1800FE0F5
0x1800fe1a2  xor     r8d, r8d; pcbe
0x1800fe1a5  lea     rcx, ?HostedCacheProtocolTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800fe1ac  mov     rdx, rdi; pv
0x1800fe1af  call    cs:__imp_CreateThreadpoolTimer
0x1800fe1b5  mov     [rdi+330h], rax
0x1800fe1bc  test    rax, rax
0x1800fe1bf  jnz     short loc_1800FE1F2
0x1800fe1c1  call    cs:__imp_GetLastError
0x1800fe1c7  mov     ebx, eax
0x1800fe1c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe1d0  lea     rax, WPP_GLOBAL_Control
0x1800fe1d7  cmp     rcx, rax
0x1800fe1da  jz      short loc_1800FE18C
0x1800fe1dc  test    dword ptr [rcx+6Ch], 1000h
0x1800fe1e3  jz      short loc_1800FE18C
0x1800fe1e5  cmp     byte ptr [rcx+69h], 1
0x1800fe1e9  jb      short loc_1800FE18C
0x1800fe1eb  mov     edx, 0Ch
0x1800fe1f0  jmp     short loc_1800FE179
0x1800fe1f2  xor     r8d, r8d; pcbe
0x1800fe1f5  lea     rcx, ?HostedCacheProtocolBatchingIdleTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800fe1fc  mov     rdx, rdi; pv
0x1800fe1ff  call    cs:__imp_CreateThreadpoolTimer
0x1800fe205  mov     [rdi+458h], rax
0x1800fe20c  test    rax, rax
0x1800fe20f  jnz     short loc_1800FE251
0x1800fe211  call    cs:__imp_GetLastError
0x1800fe217  mov     ebx, eax
0x1800fe219  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe220  lea     rax, WPP_GLOBAL_Control
0x1800fe227  cmp     rcx, rax
0x1800fe22a  jz      loc_1800FE18C
0x1800fe230  test    dword ptr [rcx+6Ch], 1000h
0x1800fe237  jz      loc_1800FE18C
0x1800fe23d  cmp     byte ptr [rcx+69h], 1
0x1800fe241  jb      loc_1800FE18C
0x1800fe247  mov     edx, 0Dh
0x1800fe24c  jmp     loc_1800FE179
0x1800fe251  movzx   esi, word ptr [rdi+2B0h]
0x1800fe258  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800fe25f  mov     ebp, 10h
0x1800fe264  mov     ecx, ebp; unsigned __int64
0x1800fe266  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800fe26b  mov     rbx, rax
0x1800fe26e  test    rax, rax
0x1800fe271  jz      short loc_1800FE283
0x1800fe273  lea     rax, ??_7CHostedCacheMsgEncoding@@6B@; const CHostedCacheMsgEncoding::`vftable'
0x1800fe27a  mov     [rbx+8], si
0x1800fe27e  mov     [rbx], rax
0x1800fe281  jmp     short loc_1800FE285
0x1800fe283  xor     ebx, ebx
0x1800fe285  mov     rcx, [rdi+408h]
0x1800fe28c  cmp     rbx, rcx
0x1800fe28f  jz      short loc_1800FE2A6
0x1800fe291  test    rcx, rcx
0x1800fe294  jz      short loc_1800FE2A6
0x1800fe296  mov     rax, [rcx]
0x1800fe299  mov     edx, 1
0x1800fe29e  mov     rax, [rax]
0x1800fe2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe2a6  mov     rcx, rdi; this
0x1800fe2a9  mov     [rdi+408h], rbx
0x1800fe2b0  call    ?StartSecureHttpTransport@CHostedCacheProtocol@@AEAAJXZ; CHostedCacheProtocol::StartSecureHttpTransport(void)
0x1800fe2b5  mov     ebx, eax
0x1800fe2b7  test    eax, eax
0x1800fe2b9  jns     short loc_1800FE2F0
0x1800fe2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe2c2  lea     rax, WPP_GLOBAL_Control
0x1800fe2c9  cmp     rcx, rax
0x1800fe2cc  jz      loc_1800FE0F5
0x1800fe2d2  test    dword ptr [rcx+6Ch], 1000h
0x1800fe2d9  jz      loc_1800FE0F5
0x1800fe2df  cmp     byte ptr [rcx+69h], 1
0x1800fe2e3  jb      loc_1800FE0F5
0x1800fe2e9  mov     edx, 0Eh
0x1800fe2ee  jmp     short loc_1800FE331
0x1800fe2f0  mov     rcx, rdi; this
0x1800fe2f3  call    ?StartHttpTransport@CHostedCacheProtocol@@AEAAJXZ; CHostedCacheProtocol::StartHttpTransport(void)
0x1800fe2f8  mov     ebx, eax
0x1800fe2fa  test    eax, eax
0x1800fe2fc  jns     short loc_1800FE349
0x1800fe2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe305  lea     rax, WPP_GLOBAL_Control
0x1800fe30c  cmp     rcx, rax
0x1800fe30f  jz      loc_1800FE0F5
0x1800fe315  test    dword ptr [rcx+6Ch], 1000h
0x1800fe31c  jz      loc_1800FE0F5
0x1800fe322  cmp     byte ptr [rcx+69h], 1
0x1800fe326  jb      loc_1800FE0F5
0x1800fe32c  mov     edx, 0Fh
0x1800fe331  mov     rcx, [rcx+60h]
0x1800fe335  lea     r8, WPP_54be81ea90983cb591d6a2d511652152_Traceguids
0x1800fe33c  mov     r9d, ebx
0x1800fe33f  call    WPP_SF_d
0x1800fe344  jmp     loc_1800FE0F5
0x1800fe349  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fe350  lea     rax, WPP_GLOBAL_Control
0x1800fe357  cmp     rcx, rax
0x1800fe35a  jz      loc_1800FE0F5
0x1800fe360  test    dword ptr [rcx+6Ch], 1000h
0x1800fe367  jz      loc_1800FE0F5
0x1800fe36d  cmp     byte ptr [rcx+69h], 4
0x1800fe371  jb      loc_1800FE0F5
0x1800fe377  mov     edx, ebp
0x1800fe379  jmp     short loc_1800FE331
0x1800fe37b  mov     eax, 80004003h
0x1800fe380  mov     rcx, [rsp+238h+var_58]
0x1800fe388  xor     rcx, rsp; StackCookie
0x1800fe38b  call    __security_check_cookie
0x1800fe390  add     rsp, 1F8h
0x1800fe397  pop     r15
0x1800fe399  pop     r14
0x1800fe39b  pop     r13
0x1800fe39d  pop     r12
0x1800fe39f  pop     rdi
0x1800fe3a0  pop     rsi
0x1800fe3a1  pop     rbp
0x1800fe3a2  pop     rbx
0x1800fe3a3  retn
```
