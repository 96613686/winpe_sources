# CBroker::SebEvent::OnSignaled(ulong,void const *,uint)

- ea: `0x180005230`
- end: `0x180005a44`
- name: `?OnSignaled@SebEvent@CBroker@@QEAAXKPEBXI@Z`
- size: `2068`
- prototype: `void __fastcall(CBroker::SebEvent *__hidden this, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004610`

## callees

- `0x1800031d0`
- `0x180003950`
- `0x180003af0`
- `0x180005230`
- `0x180005a50`
- `0x180008c00`
- `0x1800169e0`
- `0x18001cf50`
- `0x18001d9a0`
- `0x1800209a4`
- `0x1800223e0`
- `0x180022440`

## import_xrefs

- `ntdll!RtlWaitForWnfMetaNotification` at `0x1800053e0`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x1800053e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005286`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005286`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000545d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000545d`
- `ntdll!RtlPublishWnfStateData` at `0x180005652`
- `ntdll!RtlPublishWnfStateData` at `0x180005652`
- `ntdll!RtlWakeAddressAll` at `0x180005685`
- `ntdll!RtlWakeAddressAll` at `0x1800059d1`
- `ntdll!RtlWakeAddressAll` at `0x180005685`
- `ntdll!RtlWakeAddressAll` at `0x1800059d1`
- `ntdll!NtQueryWnfStateData` at `0x1800053b2`
- `ntdll!NtQueryWnfStateData` at `0x1800053b2`
- `ntdll!RtlTestAndPublishWnfStateData` at `0x180005430`
- `ntdll!RtlTestAndPublishWnfStateData` at `0x180005430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000528c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000528c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000535f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005370`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000535f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005370`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBroker::SebEvent::OnSignaled(CBroker::SebEvent *this, unsigned int a2, void *a3, unsigned int a4)
{
  size_t v4; // r15
  char *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  _BYTE *v11; // rcx
  int v12; // eax
  unsigned __int64 v13; // r8
  int v14; // r14d
  GUID *v15; // r13
  int v16; // eax
  ULONGLONG TickCount64; // r15
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  char *v27; // [rsp+50h] [rbp-B0h]
  char v28; // [rsp+58h] [rbp-A8h]
  DWORD CurrentThreadId; // [rsp+5Ch] [rbp-A4h]
  void *Src; // [rsp+60h] [rbp-A0h] BYREF
  GUID v31; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[4080]; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+1070h] [rbp+F70h] BYREF
  int v34; // [rsp+1074h] [rbp+F74h]
  _BYTE v35[4088]; // [rsp+1078h] [rbp+F78h] BYREF

  v4 = a4;
  Src = a3;
  v8 = (char *)this + 240;
  v27 = (char *)this + 240;
  RtlAcquireSRWLockExclusive((char *)this + 240);
  CurrentThreadId = GetCurrentThreadId();
  v28 = 1;
  memset_0(&v31, 0, 0xFF8u);
  v11 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDLd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v10,
      *((unsigned int *)this + 28),
      *((_DWORD *)this + 29),
      *((_DWORD *)this + 24),
      *((_DWORD *)this + 38));
    v11 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 39) || !*((_BYTE *)this + 161) )
  {
    v12 = *((_DWORD *)this + 38);
    if ( !v12 || v12 == 3 )
    {
      if ( (v11[28] & 0x40) == 0 )
        goto LABEL_23;
      if ( v11[25] < 2u )
        goto LABEL_22;
      WPP_SF_(*((_QWORD *)v11 + 2), 47, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids);
      goto LABEL_21;
    }
    if ( *((_DWORD *)this + 24) == 4148 )
    {
      if ( !(unsigned int)CBroker::SebEvent::EvaluateCustomData(this, (char *)a3, (unsigned int)v4) )
      {
        v11 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_23;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          goto LABEL_22;
        v19 = 52;
        goto LABEL_77;
      }
      LOBYTE(v14) = 0;
      if ( (unsigned int)(v4 - 1) > 0xFE6 )
      {
        v15 = 0;
        LODWORD(v4) = 0;
      }
      else
      {
        v31 = CBroker::CLSID_CustomSystemTriggerDataFactory;
        memcpy_0(v32, Src, v4);
        v15 = &v31;
        LODWORD(v4) = v4 + 16;
      }
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
          *((unsigned int *)this + 28),
          *((_DWORD *)this + 29));
        v11 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v13 = *((unsigned int *)this + 44);
      if ( v4 + 8 < v13 )
      {
        if ( (v11[28] & 0x40) == 0 )
          goto LABEL_23;
        if ( v11[25] < 2u )
          goto LABEL_22;
        v23 = 48;
        goto LABEL_71;
      }
      if ( (unsigned int)v13 > 8 && !a3 )
      {
        if ( (v11[28] & 0x40) == 0 )
          goto LABEL_23;
        if ( v11[25] < 2u )
          goto LABEL_22;
        v23 = 49;
LABEL_71:
        WPP_SF_DDdd(
          *((_QWORD *)v11 + 2),
          v23,
          v13,
          *((unsigned int *)this + 28),
          *((_DWORD *)this + 29),
          v4,
          *((_DWORD *)this + 44));
LABEL_21:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_22;
      }
      if ( *((_DWORD *)this + 25) )
      {
        v14 = 0;
        if ( (v11[28] & 0x40) != 0 && v11[25] >= 4u )
        {
          WPP_SF_DDd(*((_QWORD *)v11 + 2), 83, v13, *((unsigned int *)this + 28), *((_DWORD *)this + 29), a2);
          v11 = WPP_GLOBAL_Control;
        }
        v20 = *((_DWORD *)this + 25);
        if ( v20 == 4 )
        {
          switch ( *((_DWORD *)this + 52) )
          {
            case 1:
              goto LABEL_96;
            case 2:
              goto LABEL_62;
            case 3:
              LOBYTE(v14) = a2 > *((_DWORD *)this + 62);
              break;
            case 4:
              LOBYTE(v14) = a2 >= *((_DWORD *)this + 62);
              break;
            case 5:
              LOBYTE(v14) = a2 < *((_DWORD *)this + 62);
              break;
            case 6:
              LOBYTE(v14) = a2 <= *((_DWORD *)this + 62);
              break;
            default:
              break;
          }
        }
        else if ( (unsigned int)(v20 - 1) <= 2 )
        {
          v9 = (unsigned int)(*((_DWORD *)this + 52) - 1);
          if ( *((_DWORD *)this + 52) == 1 )
          {
LABEL_96:
            LOBYTE(v14) = *((_DWORD *)this + 62) == a2;
          }
          else if ( *((_DWORD *)this + 52) == 2 )
          {
LABEL_62:
            LOBYTE(v14) = *((_DWORD *)this + 62) != a2;
          }
        }
        if ( (v11[28] & 0x40) != 0 && v11[25] >= 4u )
        {
          WPP_SF_DDd(*((_QWORD *)v11 + 2), 84, v13, *((unsigned int *)this + 28), *((_DWORD *)this + 29), v14);
          v11 = WPP_GLOBAL_Control;
        }
        v13 = *((unsigned __int8 *)this + 160);
        if ( (_BYTE)v13 == (_BYTE)v14 )
        {
          v22 = *((int *)this + 24) - 4096LL;
          v9 = 5 * v22;
          if ( (byte_180035F64[40 * v22] & 2) == 0 )
          {
            if ( (v11[28] & 0x40) == 0 )
              goto LABEL_23;
            if ( v11[25] < 4u )
              goto LABEL_22;
            WPP_SF_DDd(
              *((_QWORD *)v11 + 2),
              50,
              v13,
              *((unsigned int *)this + 28),
              *((_DWORD *)this + 29),
              *((unsigned __int8 *)this + 160));
            goto LABEL_21;
          }
        }
        *((_BYTE *)this + 160) = v14;
        v11 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            v13,
            *((unsigned int *)this + 28),
            *((_DWORD *)this + 29),
            (unsigned __int8)v14);
          v11 = WPP_GLOBAL_Control;
        }
        v21 = *((_DWORD *)this + 25);
        if ( v21 == 2 )
        {
          if ( !(_BYTE)v14 )
            goto LABEL_22;
        }
        else if ( v21 == 3 && (_BYTE)v14 == 1 )
        {
          goto LABEL_22;
        }
      }
      else
      {
        LOBYTE(v14) = 1;
        *((_BYTE *)this + 160) = 1;
        v11 = WPP_GLOBAL_Control;
      }
      v15 = (GUID *)Src;
    }
    v16 = *((_DWORD *)this + 25);
    if ( v16 == 1 || v16 == 4 )
    {
      if ( (v11[28] & 0x40) != 0 && v11[25] >= 4u )
        WPP_SF_DDd(
          *((_QWORD *)v11 + 2),
          54,
          v13,
          *((unsigned int *)this + 28),
          *((_DWORD *)this + 29),
          (unsigned __int8)v14);
      Src = (void *)*((_QWORD *)this + 14);
      v26 = 0;
      v25 = 0;
      TickCount64 = GetTickCount64();
      v24 = 8;
      while ( GetTickCount64() - TickCount64 <= 0x4E20 )
      {
        v24 = 4096;
        if ( (int)NtQueryWnfStateData(&Src, 0, 0, &v25, &v33, &v24) < 0
          || (int)RtlWaitForWnfMetaNotification(Src, 8, 20000, 100, &v26) < 0 )
        {
          goto LABEL_102;
        }
        v34 = -1;
        v33 = (2 * (unsigned __int8)v14) | 1;
        v24 = 8;
        v18 = RtlTestAndPublishWnfStateData(Src, 0, &v33, 8, 0, v25);
        if ( v18 != -1073741823 )
        {
          if ( v18 >= 0 )
            goto LABEL_21;
LABEL_102:
          v11 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_23;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 55;
            goto LABEL_77;
          }
          goto LABEL_22;
        }
      }
      goto LABEL_21;
    }
    if ( *((_DWORD *)this + 39) )
    {
      *((_BYTE *)this + 161) = 1;
      v11 = WPP_GLOBAL_Control;
    }
    if ( (!(_DWORD)v4 || v15 && (unsigned int)v4 >= 0x14) && (unsigned int)(v4 + 8) <= 0x1000 )
    {
      v34 = -1;
      v33 = (4 * (v4 & 0xFFF)) | 3;
      if ( (_DWORD)v4 )
        memcpy_0(v35, v15, (unsigned int)v4);
      if ( (int)RtlPublishWnfStateData(*((_QWORD *)this + 14), 0, &v33, (unsigned int)(v4 + 8), 0) >= 0 )
        goto LABEL_56;
      v11 = WPP_GLOBAL_Control;
    }
    if ( (v11[28] & 0x40) != 0 && v11[25] >= 2u )
      WPP_SF_DD(
        *((_QWORD *)v11 + 2),
        56,
        &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
        *((unsigned int *)this + 28),
        *((_DWORD *)this + 29));
LABEL_56:
    if ( *((_DWORD *)this + 39) )
    {
      *((_BYTE *)this + 161) = 1;
      *((_DWORD *)this + 38) = 3;
    }
    else
    {
      *((_QWORD *)this + 25) = 0;
      *((_DWORD *)this + 38) = 1;
    }
    RtlWakeAddressAll((char *)this + 152, v9);
    goto LABEL_21;
  }
  if ( (v11[28] & 0x40) == 0 )
    goto LABEL_23;
  if ( v11[25] >= 2u )
  {
    v19 = 46;
LABEL_77:
    WPP_SF_DD(
      *((_QWORD *)v11 + 2),
      v19,
      &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
      *((unsigned int *)this + 28),
      *((_DWORD *)this + 29));
    goto LABEL_21;
  }
LABEL_22:
  if ( (v11[28] & 0x40) != 0 && v11[25] >= 4u )
    WPP_SF__guid_(*((_QWORD *)v11 + 2), 57, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (char *)this + 120);
LABEL_23:
  RtlReleaseSRWLockExclusive(v8);
}

```

## disassembly

```asm
0x180005230  mov     [rsp-8+arg_8], rbx
0x180005235  push    rbp
0x180005236  push    rsi
0x180005237  push    rdi
0x180005238  push    r12
0x18000523a  push    r13
0x18000523c  push    r14
0x18000523e  push    r15
0x180005240  lea     rbp, [rsp-1F80h]
0x180005248  mov     eax, 2080h
0x18000524d  call    _alloca_probe
0x180005252  sub     rsp, rax
0x180005255  mov     rax, cs:__security_cookie
0x18000525c  xor     rax, rsp
0x18000525f  mov     [rbp+1FB0h+var_40], rax
0x180005266  mov     r15d, r9d
0x180005269  mov     rsi, r8
0x18000526c  mov     [rsp+20B0h+Src], r8
0x180005271  mov     r13d, edx
0x180005274  mov     rbx, rcx
0x180005277  lea     rdi, [rcx+0F0h]
0x18000527e  mov     [rsp+20B0h+var_2060], rdi
0x180005283  mov     rcx, rdi
0x180005286  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000528c  call    cs:__imp_GetCurrentThreadId
0x180005292  mov     [rsp+20B0h+var_2054], eax
0x180005296  mov     [rsp+20B0h+var_2058], 1
0x18000529b  xor     edx, edx; Val
0x18000529d  mov     r8d, 0FF8h; Size
0x1800052a3  lea     rcx, [rsp+20B0h+var_2040]; void *
0x1800052a8  call    memset_0
0x1800052ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052b4  test    byte ptr [rcx+1Ch], 40h
0x1800052b8  jz      short loc_1800052C4
0x1800052ba  cmp     byte ptr [rcx+19h], 4
0x1800052be  jnb     loc_180005788
0x1800052c4  cmp     dword ptr [rbx+9Ch], 0
0x1800052cb  jnz     loc_18000548D
0x1800052d1  mov     eax, [rbx+98h]
0x1800052d7  test    eax, eax
0x1800052d9  jz      loc_1800059FC
0x1800052df  cmp     eax, 3
0x1800052e2  jz      loc_1800059FC
0x1800052e8  cmp     dword ptr [rbx+60h], 1034h
0x1800052ef  jz      loc_180005820
0x1800052f5  mov     r8d, [rbx+0B0h]
0x1800052fc  lea     rax, [r15+8]
0x180005300  cmp     rax, r8
0x180005303  jb      loc_1800058D9
0x180005309  cmp     r8d, 8
0x18000530d  ja      loc_18000570C
0x180005313  xor     esi, esi
0x180005315  cmp     [rbx+64h], esi
0x180005318  jnz     loc_1800054B0
0x18000531e  mov     r14b, 1
0x180005321  mov     [rbx+0A0h], r14b
0x180005328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000532f  mov     r13, [rsp+20B0h+Src]
0x180005334  mov     eax, [rbx+64h]
0x180005337  cmp     eax, 1
0x18000533a  jnz     loc_1800055E6
0x180005340  test    byte ptr [rcx+1Ch], 40h
0x180005344  jnz     loc_18000553A
0x18000534a  mov     rax, [rbx+70h]
0x18000534e  mov     [rsp+20B0h+Src], rax
0x180005353  mov     [rsp+20B0h+var_2068], esi
0x180005357  mov     [rsp+20B0h+var_206C], esi
0x18000535b  mov     [rsp+20B0h+var_2070], esi
0x18000535f  call    cs:__imp_GetTickCount64
0x180005365  mov     r15, rax
0x180005368  mov     [rsp+20B0h+var_2070], 8
0x180005370  call    cs:__imp_GetTickCount64
0x180005376  sub     rax, r15
0x180005379  cmp     rax, 4E20h
0x18000537f  ja      loc_180005449
0x180005385  mov     [rsp+20B0h+var_2070], 1000h
0x18000538d  lea     rax, [rsp+20B0h+var_2070]
0x180005392  mov     [rsp+20B0h+var_2088], rax
0x180005397  lea     rax, [rbp+1FB0h+var_1040]
0x18000539e  mov     [rsp+20B0h+var_2090], rax
0x1800053a3  lea     r9, [rsp+20B0h+var_206C]
0x1800053a8  xor     r8d, r8d
0x1800053ab  xor     edx, edx
0x1800053ad  lea     rcx, [rsp+20B0h+Src]
0x1800053b2  call    cs:__imp_NtQueryWnfStateData
0x1800053b8  test    eax, eax
0x1800053ba  js      loc_1800059DC
0x1800053c0  lea     rax, [rsp+20B0h+var_2068]
0x1800053c5  mov     [rsp+20B0h+var_2090], rax
0x1800053ca  mov     edx, 8
0x1800053cf  mov     r9d, 64h ; 'd'
0x1800053d5  mov     r8d, 4E20h
0x1800053db  mov     rcx, [rsp+20B0h+Src]
0x1800053e0  call    cs:__imp_RtlWaitForWnfMetaNotification
0x1800053e6  test    eax, eax
0x1800053e8  js      loc_1800059DC
0x1800053ee  mov     [rbp+1FB0h+var_103C], 0FFFFFFFFh
0x1800053f8  movzx   eax, r14b
0x1800053fc  add     eax, eax
0x1800053fe  or      eax, 1
0x180005401  mov     [rbp+1FB0h+var_1040], eax
0x180005407  mov     [rsp+20B0h+var_2070], 8
0x18000540f  mov     eax, [rsp+20B0h+var_206C]
0x180005413  mov     dword ptr [rsp+20B0h+var_2088], eax
0x180005417  mov     [rsp+20B0h+var_2090], rsi
0x18000541c  mov     r9d, 8
0x180005422  lea     r8, [rbp+1FB0h+var_1040]
0x180005429  xor     edx, edx
0x18000542b  mov     rcx, [rsp+20B0h+Src]
0x180005430  call    cs:__imp_RtlTestAndPublishWnfStateData
0x180005436  cmp     eax, 0C0000001h
0x18000543b  jz      loc_180005370
0x180005441  test    eax, eax
0x180005443  js      loc_1800059DC
0x180005449  mov     rcx, cs:WPP_GLOBAL_Control
0x180005450  test    byte ptr [rcx+1Ch], 40h
0x180005454  jnz     loc_1800055BE
0x18000545a  mov     rcx, rdi
0x18000545d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005463  mov     rcx, [rbp+1FB0h+var_40]
0x18000546a  xor     rcx, rsp; StackCookie
0x18000546d  call    __security_check_cookie
0x180005472  mov     rbx, [rsp+20B0h+arg_8]
0x18000547a  add     rsp, 2080h
0x180005481  pop     r15
0x180005483  pop     r14
0x180005485  pop     r13
0x180005487  pop     r12
0x180005489  pop     rdi
0x18000548a  pop     rsi
0x18000548b  pop     rbp
0x18000548c  retn
0x18000548d  cmp     byte ptr [rbx+0A1h], 0
0x180005494  jz      loc_1800052D1
0x18000549a  test    byte ptr [rcx+1Ch], 40h
0x18000549e  jz      short loc_18000545A
0x1800054a0  cmp     byte ptr [rcx+19h], 2
0x1800054a4  jb      short loc_180005450
0x1800054a6  mov     edx, 2Eh ; '.'
0x1800054ab  jmp     loc_180005800
0x1800054b0  mov     r14d, esi
0x1800054b3  test    byte ptr [rcx+1Ch], 40h
0x1800054b7  jz      short loc_1800054C3
0x1800054b9  cmp     byte ptr [rcx+19h], 4
0x1800054bd  jnb     loc_1800057B9
0x1800054c3  mov     eax, [rbx+64h]
0x1800054c6  lea     r9, __ImageBase
0x1800054cd  cmp     eax, 4
0x1800054d0  jnz     loc_180005690
0x1800054d6  mov     eax, [rbx+0D0h]
0x1800054dc  dec     eax; switch 6 cases
0x1800054de  cmp     eax, 5
0x1800054e1  jbe     loc_1800058F7
0x1800054e7  test    byte ptr [rcx+1Ch], 40h; jumptable 0000000180005904 default case
0x1800054eb  jnz     loc_1800056C3
0x1800054f1  movzx   r8d, byte ptr [rbx+0A0h]
0x1800054f9  cmp     r8b, r14b
0x1800054fc  jz      short loc_18000556A
0x1800054fe  mov     [rbx+0A0h], r14b
0x180005505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000550c  test    byte ptr [rcx+1Ch], 40h
0x180005510  jnz     loc_180005751
0x180005516  mov     eax, [rbx+64h]
0x180005519  cmp     eax, 2
0x18000551c  jz      loc_1800056FE
0x180005522  cmp     eax, 3
0x180005525  jnz     loc_18000532F
0x18000552b  cmp     r14b, 1
0x18000552f  jz      loc_180005450
0x180005535  jmp     loc_18000532F
0x18000553a  cmp     byte ptr [rcx+19h], 4
0x18000553e  jb      loc_18000534A
0x180005544  movzx   eax, r14b
0x180005548  mov     edx, 36h ; '6'
0x18000554d  mov     dword ptr [rsp+20B0h+var_2088], eax
0x180005551  mov     eax, [rbx+74h]
0x180005554  mov     dword ptr [rsp+20B0h+var_2090], eax
0x180005558  mov     r9d, [rbx+70h]
0x18000555c  mov     rcx, [rcx+10h]
0x180005560  call    WPP_SF_DDd
0x180005565  jmp     loc_18000534A
0x18000556a  movsxd  rax, dword ptr [rbx+60h]
0x18000556e  sub     rax, 1000h
0x180005574  lea     rdx, [rax+rax*4]
0x180005578  test    rva byte_180035F64[r9+rdx*8], 2
0x180005581  jnz     loc_1800054FE
0x180005587  test    byte ptr [rcx+1Ch], 40h
0x18000558b  jz      loc_18000545A
0x180005591  cmp     byte ptr [rcx+19h], 4
0x180005595  jb      loc_180005450
0x18000559b  mov     edx, 32h ; '2'
0x1800055a0  mov     dword ptr [rsp+20B0h+var_2088], r8d
0x1800055a5  mov     eax, [rbx+74h]
0x1800055a8  mov     dword ptr [rsp+20B0h+var_2090], eax
0x1800055ac  mov     r9d, [rbx+70h]
0x1800055b0  mov     rcx, [rcx+10h]
0x1800055b4  call    WPP_SF_DDd
0x1800055b9  jmp     loc_180005449
0x1800055be  cmp     byte ptr [rcx+19h], 4
0x1800055c2  jb      loc_18000545A
0x1800055c8  lea     r9, [rbx+78h]
0x1800055cc  mov     edx, 39h ; '9'
0x1800055d1  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x1800055d8  mov     rcx, [rcx+10h]
0x1800055dc  call    WPP_SF__guid_
0x1800055e1  jmp     loc_18000545A
0x1800055e6  cmp     eax, 4
0x1800055e9  jz      loc_180005340
0x1800055ef  cmp     dword ptr [rbx+9Ch], 0
0x1800055f6  jnz     loc_180005956
0x1800055fc  test    r15d, r15d
0x1800055ff  jnz     loc_1800057E3
0x180005605  lea     r14d, [r15+8]
0x180005609  cmp     r14d, 1000h
0x180005610  ja      loc_180005987
0x180005616  mov     [rbp+1FB0h+var_103C], 0FFFFFFFFh
0x180005620  mov     eax, r15d
0x180005623  and     eax, 0FFFh
0x180005628  shl     eax, 2
0x18000562b  or      eax, 3
0x18000562e  mov     [rbp+1FB0h+var_1040], eax
0x180005634  test    r15d, r15d
0x180005637  jnz     loc_180005969
0x18000563d  mov     [rsp+20B0h+var_2090], rsi
0x180005642  mov     r9d, r14d
0x180005645  lea     r8, [rbp+1FB0h+var_1040]
0x18000564c  xor     edx, edx
0x18000564e  mov     rcx, [rbx+70h]
0x180005652  call    cs:__imp_RtlPublishWnfStateData
0x180005658  test    eax, eax
0x18000565a  js      loc_180005980
0x180005660  lea     rcx, [rbx+98h]
0x180005667  cmp     dword ptr [rbx+9Ch], 0
0x18000566e  jnz     loc_1800059C0
0x180005674  mov     [rbx+0C8h], rsi
0x18000567b  mov     dword ptr [rbx+98h], 1
0x180005685  call    cs:__imp_RtlWakeAddressAll
0x18000568b  jmp     loc_180005449
0x180005690  dec     eax
0x180005692  cmp     eax, 2
0x180005695  ja      def_180005904; jumptable 0000000180005904 default case
0x18000569b  mov     edx, [rbx+0D0h]
0x1800056a1  sub     edx, 1
0x1800056a4  jz      loc_180005946; jumptable 0000000180005904 case 1
0x1800056aa  cmp     edx, 1
0x1800056ad  jnz     def_180005904; jumptable 0000000180005904 default case
0x1800056b3  cmp     [rbx+0F8h], r13d; jumptable 0000000180005904 case 2
0x1800056ba  setnz   r14b
0x1800056be  jmp     def_180005904; jumptable 0000000180005904 default case
0x1800056c3  cmp     byte ptr [rcx+19h], 4
0x1800056c7  jb      loc_1800054F1
0x1800056cd  mov     edx, 54h ; 'T'
0x1800056d2  mov     dword ptr [rsp+20B0h+var_2088], r14d
0x1800056d7  mov     eax, [rbx+74h]
0x1800056da  mov     dword ptr [rsp+20B0h+var_2090], eax
0x1800056de  mov     r9d, [rbx+70h]
0x1800056e2  mov     rcx, [rcx+10h]
0x1800056e6  call    WPP_SF_DDd
0x1800056eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056f2  lea     r9, __ImageBase
0x1800056f9  jmp     loc_1800054F1
0x1800056fe  test    r14b, r14b
0x180005701  jz      loc_180005450
0x180005707  jmp     loc_18000532F
0x18000570c  test    rsi, rsi
0x18000570f  jnz     loc_180005313
0x180005715  test    byte ptr [rcx+1Ch], 40h
0x180005719  jz      loc_18000545A
0x18000571f  cmp     byte ptr [rcx+19h], 2
0x180005723  jb      loc_180005450
0x180005729  mov     edx, 31h ; '1'
0x18000572e  mov     [rsp+20B0h+var_2080], r8d
0x180005733  mov     dword ptr [rsp+20B0h+var_2088], r15d
0x180005738  mov     eax, [rbx+74h]
0x18000573b  mov     dword ptr [rsp+20B0h+var_2090], eax
0x18000573f  mov     r9d, [rbx+70h]
0x180005743  mov     rcx, [rcx+10h]
0x180005747  call    WPP_SF_DDdd
0x18000574c  jmp     loc_180005449
0x180005751  cmp     byte ptr [rcx+19h], 4
0x180005755  jb      loc_180005516
0x18000575b  movzx   eax, r14b
0x18000575f  mov     edx, 33h ; '3'
0x180005764  mov     dword ptr [rsp+20B0h+var_2088], eax
0x180005768  mov     eax, [rbx+74h]
0x18000576b  mov     dword ptr [rsp+20B0h+var_2090], eax
0x18000576f  mov     r9d, [rbx+70h]
0x180005773  mov     rcx, [rcx+10h]
0x180005777  call    WPP_SF_DDd
0x18000577c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005783  jmp     loc_180005516
0x180005788  mov     eax, [rbx+98h]
0x18000578e  mov     [rsp+20B0h+var_2080], eax
0x180005792  mov     eax, [rbx+60h]
0x180005795  mov     dword ptr [rsp+20B0h+var_2088], eax
0x180005799  mov     eax, [rbx+74h]
0x18000579c  mov     dword ptr [rsp+20B0h+var_2090], eax
0x1800057a0  mov     r9d, [rbx+70h]
0x1800057a4  mov     rcx, [rcx+10h]
0x1800057a8  call    WPP_SF_DDLd
  ... truncated ...
```
