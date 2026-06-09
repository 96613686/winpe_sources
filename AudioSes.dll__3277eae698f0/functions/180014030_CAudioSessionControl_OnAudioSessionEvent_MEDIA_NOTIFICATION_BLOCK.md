# CAudioSessionControl::OnAudioSessionEvent(MEDIA_NOTIFICATION_BLOCK *)

- ea: `0x180014030`
- end: `0x180014323`
- name: `?OnAudioSessionEvent@CAudioSessionControl@@IEAAXPEAUMEDIA_NOTIFICATION_BLOCK@@@Z`
- size: `755`
- prototype: `void(CAudioSessionControl *__hidden this, struct MEDIA_NOTIFICATION_BLOCK *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013f60`

## callees

- `0x180014030`
- `0x180014330`
- `0x180015350`
- `0x180087e80`
- `0x1800a0fcc`
- `0x180123010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014091`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014091`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014072`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800140ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001412e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800140ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001412e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001429b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001429b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAudioSessionControl::OnAudioSessionEvent(
        CAudioSessionControl *this,
        struct MEDIA_NOTIFICATION_BLOCK *a2)
{
  unsigned int v4; // eax
  __int32 v5; // ecx
  __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  char *v9; // rdi
  void **v10; // rax
  unsigned int v11; // eax
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  void **v13; // [rsp+38h] [rbp-28h]
  __int128 v14; // [rsp+40h] [rbp-20h]
  char *v15; // [rsp+50h] [rbp-10h]

  if ( !(unsigned int)ValidateNotificationBlock(a2) )
    return;
  if ( *((_DWORD *)this + 80) == 2 )
    goto LABEL_7;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  v13 = (void **)((char *)this + 224);
  if ( *((_QWORD *)this + 25) )
    goto LABEL_4;
  pv = 0;
  if ( (*(int (__fastcall **)(char *, LPVOID *))(*((_QWORD *)this + 2) + 104LL))((char *)this + 16, &pv) >= 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
LABEL_4:
    if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 25), (char *)a2 + 72) )
    {
      if ( this != (CAudioSessionControl *)-224LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
LABEL_7:
      v4 = *((_DWORD *)a2 + 1);
      if ( v4 == 8 )
      {
        v5 = *((_DWORD *)a2 + 12);
        if ( *((_DWORD *)this + 80) != 2 && v5 == _InterlockedExchange((volatile __int32 *)this + 72, v5) )
          return;
        v13 = &CStateChanged::`vftable';
        LODWORD(v14) = v5;
        goto LABEL_17;
      }
      if ( v4 > 0x10 )
      {
        if ( v4 == 32 )
        {
          v8 = *((_DWORD *)a2 + 12);
          if ( v8 <= 2 || v8 == 4 )
          {
            _InterlockedExchange((volatile __int32 *)this + 73, -2004287484);
          }
          else if ( v8 == 5 )
          {
            *((_DWORD *)this + 73) = -2004287484;
          }
          v13 = &CSessionDisconnect::`vftable';
          LODWORD(v14) = *((_DWORD *)a2 + 12);
          goto LABEL_17;
        }
        if ( v4 != 256 )
          goto LABEL_18;
        v9 = (char *)a2 + *((unsigned int *)a2 + 13);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2 + 28);
        }
        v10 = &CIconPathChanged::`vftable';
      }
      else
      {
        if ( v4 != 16 )
        {
          v7 = v4 - 1;
          if ( !v7 )
          {
            v13 = &CSimpleVolumeChanged::`vftable';
            LODWORD(v14) = *((_DWORD *)a2 + 12);
            DWORD1(v14) = *((unsigned __int8 *)a2 + 52);
            *((_QWORD *)&v14 + 1) = (char *)a2 + 28;
LABEL_17:
            CLockedList_AllowDuplicates<IAudioSessionEvents,1>::ForEachEntry((LPCRITICAL_SECTION)this + 3);
            goto LABEL_18;
          }
          v11 = v7 - 1;
          if ( !v11 )
          {
            v13 = &CChannelVolumeChanged::`vftable';
            *(_QWORD *)&v14 = (char *)a2 + *((unsigned int *)a2 + 12);
            DWORD2(v14) = *((_DWORD *)a2 + 14);
            HIDWORD(v14) = *((_DWORD *)a2 + 13);
            v15 = (char *)a2 + 28;
            goto LABEL_17;
          }
          if ( v11 == 2 )
          {
            v13 = &CGroupingParamChanged::`vftable';
            v14 = *((_OWORD *)a2 + 3);
            v15 = (char *)a2 + 28;
            goto LABEL_17;
          }
LABEL_18:
          v6 = *((_QWORD *)this + 39);
          if ( v6 )
            (*(void (__fastcall **)(__int64, struct MEDIA_NOTIFICATION_BLOCK *))(*(_QWORD *)v6 + 24LL))(v6, a2);
          return;
        }
        v9 = (char *)a2 + *((unsigned int *)a2 + 13);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2 + 28);
        }
        v10 = &CDisplayNameChanged::`vftable';
      }
      v13 = v10;
      *(_QWORD *)&v14 = v9;
      *((_QWORD *)&v14 + 1) = (char *)a2 + 28;
      goto LABEL_17;
    }
    goto LABEL_11;
  }
  if ( pv )
    CoTaskMemFree(pv);
LABEL_11:
  if ( this != (CAudioSessionControl *)-224LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
}

```

## disassembly

```asm
0x180014030  mov     [rsp-18h+arg_10], rbx
0x180014035  push    rbp
0x180014036  push    rsi
0x180014037  push    rdi
0x180014038  mov     rbp, rsp
0x18001403b  sub     rsp, 60h
0x18001403f  mov     rax, cs:__security_cookie
0x180014046  xor     rax, rsp
0x180014049  mov     [rbp+var_8], rax
0x18001404d  mov     rsi, rdx
0x180014050  mov     rbx, rcx
0x180014053  mov     rcx, rdx; struct AUDIO_NOTIFICATION_BLOCK *
0x180014056  call    ?ValidateNotificationBlock@@YAHPEAUAUDIO_NOTIFICATION_BLOCK@@@Z; ValidateNotificationBlock(AUDIO_NOTIFICATION_BLOCK *)
0x18001405b  test    eax, eax
0x18001405d  jz      short loc_1800140C9
0x18001405f  cmp     dword ptr [rbx+140h], 2
0x180014066  jz      short loc_1800140A5
0x180014068  lea     rdi, [rbx+0E0h]
0x18001406f  mov     rcx, rdi; lpCriticalSection
0x180014072  call    cs:__imp_EnterCriticalSection
0x180014078  mov     [rbp+var_28], rdi
0x18001407c  cmp     qword ptr [rbx+0C8h], 0
0x180014084  jz      short loc_1800140F5
0x180014086  lea     rdx, [rsi+48h]
0x18001408a  mov     rcx, [rbx+0C8h]
0x180014091  call    cs:__imp__o__wcsicmp
0x180014097  nop
0x180014098  test    eax, eax
0x18001409a  jnz     short loc_1800140E5
0x18001409c  test    rdi, rdi
0x18001409f  jnz     loc_18001412B
0x1800140a5  mov     eax, [rsi+4]
0x1800140a8  cmp     eax, 8
0x1800140ab  jnz     loc_180014178
0x1800140b1  mov     ecx, [rsi+30h]
0x1800140b4  cmp     dword ptr [rbx+140h], 2
0x1800140bb  jz      short loc_180014139
0x1800140bd  mov     eax, ecx
0x1800140bf  xchg    eax, [rbx+120h]
0x1800140c5  cmp     ecx, eax
0x1800140c7  jnz     short loc_180014139
0x1800140c9  mov     rcx, [rbp+var_8]
0x1800140cd  xor     rcx, rsp; StackCookie
0x1800140d0  call    __security_check_cookie
0x1800140d5  mov     rbx, [rsp+60h+arg_10]
0x1800140dd  add     rsp, 60h
0x1800140e1  pop     rdi
0x1800140e2  pop     rsi
0x1800140e3  pop     rbp
0x1800140e4  retn
0x1800140e5  test    rdi, rdi
0x1800140e8  jz      short loc_1800140C9
0x1800140ea  mov     rcx, rdi; lpCriticalSection
0x1800140ed  call    cs:__imp_LeaveCriticalSection
0x1800140f3  jmp     short loc_1800140C9
0x1800140f5  lea     rcx, [rbx+10h]
0x1800140f9  mov     [rbp+pv], 0
0x180014101  mov     rax, [rcx]
0x180014104  lea     rdx, [rbp+pv]
0x180014108  mov     rax, [rax+68h]
0x18001410c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014111  nop
0x180014112  mov     rcx, [rbp+pv]; pv
0x180014116  test    eax, eax
0x180014118  jns     loc_180014292
0x18001411e  test    rcx, rcx
0x180014121  jz      short loc_1800140E5
0x180014123  call    cs:__imp_CoTaskMemFree
0x180014129  jmp     short loc_1800140E5
0x18001412b  mov     rcx, rdi; lpCriticalSection
0x18001412e  call    cs:__imp_LeaveCriticalSection
0x180014134  jmp     loc_1800140A5
0x180014139  lea     rax, ??_7CStateChanged@@6B@; const CStateChanged::`vftable'
0x180014140  mov     [rbp+var_28], rax
0x180014144  mov     dword ptr [rbp+var_20], ecx
0x180014147  lea     rdx, [rbp+var_28]
0x18001414b  lea     rcx, [rbx+78h]; lpCriticalSection
0x18001414f  call    ?ForEachEntry@?$CLockedList_AllowDuplicates@UIAudioSessionEvents@@$00@@QEAAJ$$QEAVCListWorker@1@@Z; CLockedList_AllowDuplicates<IAudioSessionEvents,1>::ForEachEntry(CLockedList_AllowDuplicates<IAudioSessionEvents,1>::CListWorker &&)
0x180014154  mov     rcx, [rbx+138h]
0x18001415b  test    rcx, rcx
0x18001415e  jz      loc_1800140C9
0x180014164  mov     rax, [rcx]
0x180014167  mov     rdx, rsi
0x18001416a  mov     rax, [rax+18h]
0x18001416e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014173  jmp     loc_1800140C9
0x180014178  cmp     eax, 10h
0x18001417b  ja      short loc_1800141B2
0x18001417d  jz      loc_1800142D8
0x180014183  sub     eax, 1
0x180014186  jnz     loc_180014260
0x18001418c  lea     rax, ??_7CSimpleVolumeChanged@@6B@; const CSimpleVolumeChanged::`vftable'
0x180014193  mov     [rbp+var_28], rax
0x180014197  movss   xmm0, dword ptr [rsi+30h]
0x18001419c  movss   dword ptr [rbp+var_20], xmm0
0x1800141a1  movzx   eax, byte ptr [rsi+34h]
0x1800141a5  mov     dword ptr [rbp+var_20+4], eax
0x1800141a8  lea     rax, [rsi+1Ch]
0x1800141ac  mov     qword ptr [rbp+var_20+8], rax
0x1800141b0  jmp     short loc_180014147
0x1800141b2  cmp     eax, 20h ; ' '
0x1800141b5  jnz     short loc_1800141FA
0x1800141b7  mov     eax, [rsi+30h]
0x1800141ba  cmp     eax, 2
0x1800141bd  ja      short loc_1800141E4
0x1800141bf  mov     eax, 88890004h
0x1800141c4  xchg    eax, [rbx+124h]
0x1800141ca  lea     rax, ??_7CSessionDisconnect@@6B@; const CSessionDisconnect::`vftable'
0x1800141d1  mov     [rbp+var_28], rax
0x1800141d5  mov     eax, [rsi+30h]
0x1800141d8  mov     dword ptr [rbp+var_20], eax
0x1800141db  lea     rdx, [rbp+var_28]
0x1800141df  jmp     loc_18001414B
0x1800141e4  cmp     eax, 4
0x1800141e7  jz      short loc_1800141BF
0x1800141e9  cmp     eax, 5
0x1800141ec  jnz     short loc_1800141CA
0x1800141ee  mov     dword ptr [rbx+124h], 88890004h
0x1800141f8  jmp     short loc_1800141CA
0x1800141fa  cmp     eax, 100h
0x1800141ff  jnz     loc_180014154
0x180014205  mov     edi, [rsi+34h]
0x180014208  add     rdi, rsi
0x18001420b  lea     rax, WPP_GLOBAL_Control
0x180014212  mov     rcx, cs:WPP_GLOBAL_Control
0x180014219  cmp     rcx, rax
0x18001421c  jz      short loc_180014244
0x18001421e  test    byte ptr [rcx+1Ch], 80h
0x180014222  jz      short loc_180014244
0x180014224  cmp     byte ptr [rcx+19h], 4
0x180014228  jb      short loc_180014244
0x18001422a  lea     rax, [rsi+1Ch]
0x18001422e  mov     edx, 42h ; 'B'
0x180014233  mov     [rsp+60h+var_40], rax; __int64
0x180014238  mov     r9, rdi
0x18001423b  mov     rcx, [rcx+10h]; LoggerHandle
0x18001423f  call    WPP_SF_S_guid_
0x180014244  lea     rax, ??_7CIconPathChanged@@6B@; const CIconPathChanged::`vftable'
0x18001424b  mov     [rbp+var_28], rax
0x18001424f  mov     qword ptr [rbp+var_20], rdi
0x180014253  lea     rax, [rsi+1Ch]
0x180014257  mov     qword ptr [rbp+var_20+8], rax
0x18001425b  jmp     loc_180014147
0x180014260  sub     eax, 1
0x180014263  jz      short loc_1800142A6
0x180014265  cmp     eax, 2
0x180014268  jnz     loc_180014154
0x18001426e  lea     rax, ??_7CGroupingParamChanged@@6B@; const CGroupingParamChanged::`vftable'
0x180014275  mov     [rbp+var_28], rax
0x180014279  movups  xmm0, xmmword ptr [rsi+30h]
0x18001427d  movups  [rbp+var_20], xmm0
0x180014281  lea     rax, [rsi+1Ch]
0x180014285  mov     [rbp+var_10], rax
0x180014289  lea     rdx, [rbp+var_28]
0x18001428d  jmp     loc_18001414B
0x180014292  test    rcx, rcx
0x180014295  jz      loc_180014086
0x18001429b  call    cs:__imp_CoTaskMemFree
0x1800142a1  jmp     loc_180014086
0x1800142a6  lea     rax, ??_7CChannelVolumeChanged@@6B@; const CChannelVolumeChanged::`vftable'
0x1800142ad  mov     [rbp+var_28], rax
0x1800142b1  mov     eax, [rsi+30h]
0x1800142b4  add     rax, rsi
0x1800142b7  mov     qword ptr [rbp+var_20], rax
0x1800142bb  mov     eax, [rsi+38h]
0x1800142be  mov     dword ptr [rbp+var_20+8], eax
0x1800142c1  mov     eax, [rsi+34h]
0x1800142c4  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800142c7  lea     rax, [rsi+1Ch]
0x1800142cb  mov     [rbp+var_10], rax
0x1800142cf  lea     rdx, [rbp+var_28]
0x1800142d3  jmp     loc_18001414B
0x1800142d8  mov     edi, [rsi+34h]
0x1800142db  add     rdi, rsi
0x1800142de  lea     rax, WPP_GLOBAL_Control
0x1800142e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142ec  cmp     rcx, rax
0x1800142ef  jz      short loc_180014317
0x1800142f1  test    byte ptr [rcx+1Ch], 80h
0x1800142f5  jz      short loc_180014317
0x1800142f7  cmp     byte ptr [rcx+19h], 4
0x1800142fb  jb      short loc_180014317
0x1800142fd  lea     rax, [rsi+1Ch]
0x180014301  mov     edx, 41h ; 'A'
0x180014306  mov     [rsp+60h+var_40], rax; __int64
0x18001430b  mov     r9, rdi
0x18001430e  mov     rcx, [rcx+10h]; LoggerHandle
0x180014312  call    WPP_SF_S_guid_
0x180014317  lea     rax, ??_7CDisplayNameChanged@@6B@; const CDisplayNameChanged::`vftable'
0x18001431e  jmp     loc_18001424B
```
