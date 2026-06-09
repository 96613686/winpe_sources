# CLoggingMgrImpl::TimerCallback(void)

- ea: `0x18012ba20`
- end: `0x18012bd39`
- name: `?TimerCallback@CLoggingMgrImpl@@QEAAXXZ`
- size: `793`
- prototype: `void __fastcall(CLoggingMgrImpl *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x18012b4c0`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180004b40`
- `0x180008290`
- `0x180012d4c`
- `0x18012ba20`
- `0x18012bec0`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18012bbc0`
- `ntdll!EtwEventWrite` at `0x18012bbc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012bab3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012bab3`

## pseudocode

```c
void __fastcall CLoggingMgrImpl::TimerCallback(CLoggingMgrImpl *this)
{
  __int128 v2; // xmm0
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  unsigned int v12; // esi
  __int64 v13; // rax
  unsigned int *v14; // r14
  unsigned int **v15; // rdi
  unsigned int v16; // eax
  __int128 v17; // xmm1
  __int64 i; // rdi
  unsigned int v19; // r8d
  unsigned int v20; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[24]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v22[28]; // [rsp+40h] [rbp-C0h]
  _OWORD v23[10]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+100h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
  }
  InCritSec::InCritSec((InCritSec *)v21, (CLoggingMgrImpl *)((char *)this + 40), 1);
  if ( *((_DWORD *)this + 22) || *((_DWORD *)this + 65) )
  {
    if ( *((_BYTE *)this + 256) )
    {
      v2 = *(_OWORD *)((char *)this + 92);
      v3 = *(_OWORD *)((char *)this + 108);
      v24 = *((_DWORD *)this + 63);
      v23[0] = v2;
      v4 = *(_OWORD *)((char *)this + 124);
      v23[1] = v3;
      v5 = *(_OWORD *)((char *)this + 140);
      v23[2] = v4;
      v6 = *(_OWORD *)((char *)this + 156);
      v23[3] = v5;
      v7 = *(_OWORD *)((char *)this + 172);
      v23[4] = v6;
      v8 = *(_OWORD *)((char *)this + 188);
      v23[5] = v7;
      v9 = *(_OWORD *)((char *)this + 204);
      v23[6] = v8;
      v10 = *(_OWORD *)((char *)this + 220);
      v23[7] = v9;
      v11 = *(_OWORD *)((char *)this + 236);
      v23[8] = v10;
      v23[9] = v11;
      memset_0((char *)this + 92, 0, 0xA4u);
      *((_DWORD *)this + 22) = 0;
      InCritSec::Leave((InCritSec *)v21);
      v12 = 0;
      while ( v12 < 0x29 )
      {
        v13 = v12++;
        v14 = (unsigned int *)v23 + v13;
        if ( *v14 )
        {
          v20 = v12;
          v15 = (unsigned int **)operator new[](0x20u, (const struct std::nothrow_t *)std::nothrow);
          operator delete(0);
          if ( !v15 )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
            }
            operator delete(0);
            break;
          }
          v15[1] = (unsigned int *)4;
          *v15 = &v20;
          v15[2] = v14;
          v15[3] = (unsigned int *)4;
          v16 = EtwEventWrite(*((_QWORD *)this + 1), AccumulatedEvent, 2, v15);
          if ( v16
            && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids, v16);
          }
          operator delete(v15);
        }
      }
      InCritSec::Enter((InCritSec *)v21);
      if ( !*((_DWORD *)this + 22) )
        *((_BYTE *)this + 256) = 0;
    }
  }
  else
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 3), 0, 0, 0);
    *((_BYTE *)this + 32) = 0;
  }
  if ( *((_BYTE *)this + 292) )
  {
    v17 = *(_OWORD *)((char *)this + 276);
    *(_OWORD *)v22 = *(_OWORD *)((char *)this + 264);
    *(_OWORD *)((char *)this + 264) = 0;
    *(_OWORD *)((char *)this + 276) = 0;
    *((_DWORD *)this + 65) = 0;
    *(_OWORD *)&v22[12] = v17;
    InCritSec::Leave((InCritSec *)v21);
    for ( i = 0; i != 7; ++i )
    {
      v19 = *(_DWORD *)&v22[4 * i];
      if ( v19 )
        CLoggingMgrImpl::LogAccumulatedAuditEvent(this, *((_DWORD *)qword_180180EE0 + i), v19);
    }
    InCritSec::Enter((InCritSec *)v21);
    if ( !*((_DWORD *)this + 65) )
      *((_BYTE *)this + 292) = 0;
  }
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 65) = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
  }
  InCritSec::~InCritSec((InCritSec *)v21);
}

```

## disassembly

```asm
0x18012ba20  push    rbp
0x18012ba22  push    rbx
0x18012ba23  push    rsi
0x18012ba24  push    rdi
0x18012ba25  push    r12
0x18012ba27  push    r13
0x18012ba29  push    r14
0x18012ba2b  push    r15
0x18012ba2d  lea     rbp, [rsp-28h]
0x18012ba32  sub     rsp, 128h
0x18012ba39  mov     rax, cs:__security_cookie
0x18012ba40  xor     rax, rsp
0x18012ba43  mov     [rbp+60h+var_50], rax
0x18012ba47  mov     rbx, rcx
0x18012ba4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18012ba51  lea     r13, WPP_GLOBAL_Control
0x18012ba58  mov     r12d, 2000h
0x18012ba5e  cmp     rcx, r13
0x18012ba61  jz      short loc_18012BA84
0x18012ba63  test    [rcx+6Ch], r12d
0x18012ba67  jz      short loc_18012BA84
0x18012ba69  cmp     byte ptr [rcx+69h], 4
0x18012ba6d  jb      short loc_18012BA84
0x18012ba6f  mov     rcx, [rcx+60h]
0x18012ba73  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012ba7a  mov     edx, 15h
0x18012ba7f  call    WPP_SF_
0x18012ba84  lea     rdx, [rbx+28h]; struct CritSec *
0x18012ba88  mov     r8b, 1; bool
0x18012ba8b  lea     rcx, [rsp+160h+var_138]; this
0x18012ba90  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18012ba95  xor     r15d, r15d
0x18012ba98  cmp     [rbx+58h], r15d
0x18012ba9c  jnz     short loc_18012BAC2
0x18012ba9e  cmp     [rbx+104h], r15d
0x18012baa5  jnz     short loc_18012BAC2
0x18012baa7  mov     rcx, [rbx+18h]; pti
0x18012baab  xor     r9d, r9d; msWindowLength
0x18012baae  xor     r8d, r8d; msPeriod
0x18012bab1  xor     edx, edx; pftDueTime
0x18012bab3  call    cs:__imp_SetThreadpoolTimer
0x18012bab9  mov     [rbx+20h], r15b
0x18012babd  jmp     loc_18012BC52
0x18012bac2  cmp     [rbx+100h], r15b
0x18012bac9  jz      loc_18012BC52
0x18012bacf  lea     rcx, [rbx+5Ch]; void *
0x18012bad3  xor     edx, edx; Val
0x18012bad5  movups  xmm0, xmmword ptr [rcx]
0x18012bad8  mov     eax, [rcx+0A0h]
0x18012bade  mov     r8d, 0A4h; Size
0x18012bae4  movups  xmm1, xmmword ptr [rcx+10h]
0x18012bae8  mov     [rbp+60h+var_60], eax
0x18012baeb  movups  [rsp+160h+var_100], xmm0
0x18012baf0  movups  xmm0, xmmword ptr [rcx+20h]
0x18012baf4  movups  [rsp+160h+var_F0], xmm1
0x18012baf9  movups  xmm1, xmmword ptr [rcx+30h]
0x18012bafd  movups  [rbp+60h+var_E0], xmm0
0x18012bb01  movups  xmm0, xmmword ptr [rcx+40h]
0x18012bb05  movups  [rbp+60h+var_D0], xmm1
0x18012bb09  movups  xmm1, xmmword ptr [rcx+50h]
0x18012bb0d  movups  [rbp+60h+var_C0], xmm0
0x18012bb11  movups  xmm0, xmmword ptr [rcx+60h]
0x18012bb15  movups  [rbp+60h+var_B0], xmm1
0x18012bb19  movups  xmm1, xmmword ptr [rcx+70h]
0x18012bb1d  movups  [rbp+60h+var_A0], xmm0
0x18012bb21  movups  xmm0, xmmword ptr [rcx+80h]
0x18012bb28  movups  [rbp+60h+var_90], xmm1
0x18012bb2c  movups  xmm1, xmmword ptr [rcx+90h]
0x18012bb33  movups  [rbp+60h+var_80], xmm0
0x18012bb37  movups  [rbp+60h+var_70], xmm1
0x18012bb3b  call    memset_0
0x18012bb40  lea     rcx, [rsp+160h+var_138]; this
0x18012bb45  mov     [rbx+58h], r15d
0x18012bb49  call    ?Leave@InCritSec@@QEAAXXZ; InCritSec::Leave(void)
0x18012bb4e  mov     esi, r15d
0x18012bb51  cmp     esi, 29h ; ')'
0x18012bb54  jnb     loc_18012BC3B
0x18012bb5a  mov     eax, esi
0x18012bb5c  lea     r14, [rsp+160h+var_100]
0x18012bb61  inc     esi
0x18012bb63  lea     r14, [r14+rax*4]
0x18012bb67  cmp     [r14], r15d
0x18012bb6a  jbe     short loc_18012BB51
0x18012bb6c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012bb73  mov     [rsp+160h+var_140], esi
0x18012bb77  mov     ecx, 20h ; ' '; unsigned __int64
0x18012bb7c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18012bb81  xor     ecx, ecx; Block
0x18012bb83  mov     rdi, rax
0x18012bb86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012bb8b  test    rdi, rdi
0x18012bb8e  jz      short loc_18012BC07
0x18012bb90  mov     qword ptr [rdi+8], 4
0x18012bb98  lea     rax, [rsp+160h+var_140]
0x18012bb9d  mov     [rdi], rax
0x18012bba0  lea     rdx, AccumulatedEvent
0x18012bba7  mov     [rdi+10h], r14
0x18012bbab  mov     r9, rdi
0x18012bbae  mov     qword ptr [rdi+18h], 4
0x18012bbb6  mov     r8d, 2
0x18012bbbc  mov     rcx, [rbx+8]
0x18012bbc0  call    cs:__imp_EtwEventWrite
0x18012bbc6  test    eax, eax
0x18012bbc8  jz      short loc_18012BBFA
0x18012bbca  mov     rcx, cs:WPP_GLOBAL_Control
0x18012bbd1  cmp     rcx, r13
0x18012bbd4  jz      short loc_18012BBFA
0x18012bbd6  test    [rcx+6Ch], r12d
0x18012bbda  jz      short loc_18012BBFA
0x18012bbdc  cmp     byte ptr [rcx+69h], 1
0x18012bbe0  jb      short loc_18012BBFA
0x18012bbe2  mov     rcx, [rcx+60h]
0x18012bbe6  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012bbed  mov     edx, 17h
0x18012bbf2  mov     r9d, eax
0x18012bbf5  call    WPP_SF_d
0x18012bbfa  mov     rcx, rdi; Block
0x18012bbfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012bc02  jmp     loc_18012BB51
0x18012bc07  mov     rcx, cs:WPP_GLOBAL_Control
0x18012bc0e  cmp     rcx, r13
0x18012bc11  jz      short loc_18012BC34
0x18012bc13  test    [rcx+6Ch], r12d
0x18012bc17  jz      short loc_18012BC34
0x18012bc19  cmp     byte ptr [rcx+69h], 1
0x18012bc1d  jb      short loc_18012BC34
0x18012bc1f  mov     rcx, [rcx+60h]
0x18012bc23  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012bc2a  mov     edx, 16h
0x18012bc2f  call    WPP_SF_
0x18012bc34  xor     ecx, ecx; Block
0x18012bc36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012bc3b  lea     rcx, [rsp+160h+var_138]; this
0x18012bc40  call    ?Enter@InCritSec@@QEAAXXZ; InCritSec::Enter(void)
0x18012bc45  cmp     [rbx+58h], r15d
0x18012bc49  jnz     short loc_18012BC52
0x18012bc4b  mov     [rbx+100h], r15b
0x18012bc52  cmp     [rbx+124h], r15b
0x18012bc59  jz      short loc_18012BCD7
0x18012bc5b  movups  xmm0, xmmword ptr [rbx+108h]
0x18012bc62  lea     rcx, [rsp+160h+var_138]; this
0x18012bc67  movups  xmm1, xmmword ptr [rbx+114h]
0x18012bc6e  movups  xmmword ptr [rsp+160h+var_120], xmm0
0x18012bc73  xorps   xmm0, xmm0
0x18012bc76  movups  xmmword ptr [rbx+108h], xmm0
0x18012bc7d  movups  xmmword ptr [rbx+114h], xmm0
0x18012bc84  mov     [rbx+104h], r15d
0x18012bc8b  movups  xmmword ptr [rsp+160h+var_120+0Ch], xmm1
0x18012bc90  call    ?Leave@InCritSec@@QEAAXXZ; InCritSec::Leave(void)
0x18012bc95  mov     rdi, r15
0x18012bc98  mov     r8d, [rsp+rdi*4+160h+var_120]; unsigned int
0x18012bc9d  test    r8d, r8d
0x18012bca0  jz      short loc_18012BCB4
0x18012bca2  lea     rdx, qword_180180EE0
0x18012bca9  mov     rcx, rbx; this
0x18012bcac  mov     edx, [rdx+rdi*4]; unsigned int
0x18012bcaf  call    ?LogAccumulatedAuditEvent@CLoggingMgrImpl@@AEAAJKK@Z; CLoggingMgrImpl::LogAccumulatedAuditEvent(ulong,ulong)
0x18012bcb4  inc     rdi
0x18012bcb7  cmp     rdi, 7
0x18012bcbb  jnz     short loc_18012BC98
0x18012bcbd  lea     rcx, [rsp+160h+var_138]; this
0x18012bcc2  call    ?Enter@InCritSec@@QEAAXXZ; InCritSec::Enter(void)
0x18012bcc7  cmp     [rbx+104h], r15d
0x18012bcce  jnz     short loc_18012BCD7
0x18012bcd0  mov     [rbx+124h], r15b
0x18012bcd7  mov     [rbx+58h], r15d
0x18012bcdb  mov     [rbx+104h], r15d
0x18012bce2  mov     rcx, cs:WPP_GLOBAL_Control
0x18012bce9  cmp     rcx, r13
0x18012bcec  jz      short loc_18012BD0F
0x18012bcee  test    [rcx+6Ch], r12d
0x18012bcf2  jz      short loc_18012BD0F
0x18012bcf4  cmp     byte ptr [rcx+69h], 4
0x18012bcf8  jb      short loc_18012BD0F
0x18012bcfa  mov     rcx, [rcx+60h]
0x18012bcfe  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012bd05  mov     edx, 18h
0x18012bd0a  call    WPP_SF_
0x18012bd0f  lea     rcx, [rsp+160h+var_138]; this
0x18012bd14  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18012bd19  mov     rcx, [rbp+60h+var_50]
0x18012bd1d  xor     rcx, rsp; StackCookie
0x18012bd20  call    __security_check_cookie
0x18012bd25  add     rsp, 128h
0x18012bd2c  pop     r15
0x18012bd2e  pop     r14
0x18012bd30  pop     r13
0x18012bd32  pop     r12
0x18012bd34  pop     rdi
0x18012bd35  pop     rsi
0x18012bd36  pop     rbx
0x18012bd37  pop     rbp
0x18012bd38  retn
```
