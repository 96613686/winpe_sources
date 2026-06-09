# Broker::SebEvent::OnEnable(void)

- ea: `0x180008630`
- end: `0x180008bf4`
- name: `?OnEnable@SebEvent@Broker@@QEAAXXZ`
- size: `1476`
- prototype: `void __fastcall(Broker::SebEvent *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006360`

## callees

- `0x1800030e0`
- `0x180003120`
- `0x180008630`
- `0x180008c00`
- `0x180017cd0`
- `0x18001cf50`
- `0x18001d9ac`
- `0x1800223e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800086a6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000894a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800086a6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000894a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008810`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000891a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008810`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000891a`
- `ntdll!RtlWakeAddressAll` at `0x1800087fa`
- `ntdll!RtlWakeAddressAll` at `0x180008906`
- `ntdll!RtlWakeAddressAll` at `0x180008a95`
- `ntdll!RtlWakeAddressAll` at `0x1800087fa`
- `ntdll!RtlWakeAddressAll` at `0x180008906`
- `ntdll!RtlWakeAddressAll` at `0x180008a95`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800087e2`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800087e2`
- `ntdll!NtQueryWnfStateData` at `0x18000871d`
- `ntdll!NtQueryWnfStateData` at `0x18000871d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008950`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::SebEvent::OnEnable(Broker::SebEvent *this)
{
  char *v2; // rsi
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  _DWORD *v5; // r15
  __int64 v6; // rdx
  int v7; // r14d
  _QWORD *v8; // rax
  unsigned __int8 *v9; // r13
  unsigned __int8 v10; // r14
  _QWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // eax
  unsigned __int8 *Data4; // r8
  struct _GUID *v15; // [rsp+20h] [rbp-10F8h]
  unsigned int v16; // [rsp+44h] [rbp-10D4h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-10D0h] BYREF
  char *v18; // [rsp+50h] [rbp-10C8h]
  char v19; // [rsp+58h] [rbp-10C0h]
  DWORD CurrentThreadId; // [rsp+5Ch] [rbp-10BCh]
  Broker::SebEvent *v21; // [rsp+60h] [rbp-10B8h]
  char *v22; // [rsp+68h] [rbp-10B0h]
  char *v23; // [rsp+70h] [rbp-10A8h]
  char *v24; // [rsp+78h] [rbp-10A0h]
  void **pExceptionObject; // [rsp+80h] [rbp-1098h] BYREF
  __int128 v26; // [rsp+88h] [rbp-1090h]
  int v27; // [rsp+98h] [rbp-1080h]
  void **v28; // [rsp+A0h] [rbp-1078h] BYREF
  __int128 v29; // [rsp+A8h] [rbp-1070h]
  int v30; // [rsp+B8h] [rbp-1060h]
  void **v31; // [rsp+C0h] [rbp-1058h] BYREF
  __int128 v32; // [rsp+C8h] [rbp-1050h]
  int v33; // [rsp+D8h] [rbp-1040h]
  struct _GUID v34; // [rsp+E0h] [rbp-1038h] BYREF

  v21 = this;
  v17 = 0;
  v16 = 0;
  v2 = (char *)this + 208;
  v18 = (char *)this + 208;
  v19 = 0;
  v3 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
      *((_QWORD *)this + 28));
    v3 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 34) || !*((_BYTE *)this + 169) )
  {
    RtlAcquireSRWLockExclusive(v2);
    CurrentThreadId = GetCurrentThreadId();
    v19 = 1;
    v5 = (_DWORD *)((char *)this + 132);
    v23 = (char *)this + 132;
    if ( (unsigned int)(*((_DWORD *)this + 33) - 1) <= 1 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
            *((_QWORD *)this + 28));
          goto LABEL_20;
        }
LABEL_21:
        if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 4u )
          WPP_SF__guid_(v8[2], 28, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28));
      }
    }
    else
    {
      if ( *((_DWORD *)this + 43) )
      {
LABEL_19:
        *v5 = 1;
        RtlWakeAddressAll((char *)this + 132, v4);
LABEL_20:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_21;
      }
      if ( !*((_DWORD *)this + 31) && !*((_DWORD *)this + 32) )
      {
        *((_QWORD *)this + 22) = 0;
        *v5 = 0;
        RtlWakeAddressAll((char *)this + 132, v4);
        goto LABEL_20;
      }
      v16 = 4096;
      v7 = NtQueryWnfStateData((char *)this + 124, 0, 0, &v17, &v34, &v16);
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF__guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
          *((_QWORD *)this + 28),
          v16);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v7 >= 0 )
      {
        v22 = (char *)this + 124;
        v9 = (unsigned __int8 *)this + 168;
        v24 = (char *)this + 168;
        *((_BYTE *)this + 168) = 0;
        if ( v16 < *((_DWORD *)this + 46) )
        {
          v10 = 0;
          v11 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_12:
            v12 = *((_DWORD *)this + 25);
            if ( v12 == 1 )
            {
              *v5 = 1;
              RtlWakeAddressAll((char *)this + 132, v6);
              if ( v16 < 8 )
              {
                v16 = 8;
                *v9 = 1;
              }
              RtlReleaseSRWLockExclusive(v2);
              Data4 = v34.Data4;
              if ( v16 <= 8 )
                Data4 = 0;
              Broker::SebEvent::OnSignaled(this, v10, Data4, v16 - 8, v15);
              RtlAcquireSRWLockExclusive(v2);
              CurrentThreadId = GetCurrentThreadId();
              v19 = 1;
            }
            else if ( (unsigned int)(v12 - 2) > 1 )
            {
              goto LABEL_14;
            }
            *v9 = v10;
            v11 = WPP_GLOBAL_Control;
LABEL_14:
            if ( (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
            {
              WPP_SF__guid_D(v11[2], 25, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28), *v9);
              v11 = WPP_GLOBAL_Control;
            }
            if ( (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 4u )
              WPP_SF__guid_(v11[2], 26, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28));
            v13 = RtlSubscribeWnfStateChangeNotification(
                    (char *)this + 176,
                    *(_QWORD *)((char *)this + 124),
                    v17,
                    Broker::SebPublishWnfEventCallback,
                    this,
                    0,
                    0,
                    0);
            if ( v13 )
            {
              if ( v13 == -1073741790 )
              {
                v26 = 0;
                v27 = 5;
                pExceptionObject = &Broker::AccessDenied::`vftable';
                throw (Broker::AccessDenied *)&pExceptionObject;
              }
              if ( v13 == -1073741772 )
              {
                v29 = 0;
                v30 = 3;
                v28 = &Broker::NotFound::`vftable';
                throw (Broker::NotFound *)&v28;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, v13);
              v32 = 0;
              v33 = 7;
              v31 = &Broker::EventInternalError::`vftable';
              throw (Broker::EventInternalError *)&v31;
            }
            goto LABEL_19;
          }
          WPP_SF__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids,
            *((_QWORD *)this + 28));
        }
        else
        {
          v10 = (v34.Data1 & 2) != 0;
          if ( (v34.Data1 & 2) == 0 )
            *v9 = 1;
        }
        v11 = WPP_GLOBAL_Control;
        goto LABEL_12;
      }
      if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 )
      {
        if ( *((_BYTE *)v8 + 25) >= 2u )
        {
          WPP_SF__guid_D(v8[2], 22, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28), v7);
          goto LABEL_20;
        }
        goto LABEL_21;
      }
    }
    RtlReleaseSRWLockExclusive(v2);
    return;
  }
  if ( (*((_BYTE *)v3 + 28) & 0x40) != 0 && *((_BYTE *)v3 + 25) >= 4u )
    WPP_SF__guid_(v3[2], 19, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28));
}

```

## disassembly

```asm
0x180008630  mov     [rsp+arg_8], rbx
0x180008635  mov     [rsp+arg_10], rsi
0x18000863a  push    rdi
0x18000863b  push    r12
0x18000863d  push    r13
0x18000863f  push    r14
0x180008641  push    r15
0x180008643  mov     eax, 10F0h
0x180008648  call    _alloca_probe
0x18000864d  sub     rsp, rax
0x180008650  mov     rax, cs:__security_cookie
0x180008657  xor     rax, rsp
0x18000865a  mov     [rsp+1118h+var_38], rax
0x180008662  mov     rbx, rcx
0x180008665  mov     [rsp+1118h+var_10B8], rcx
0x18000866a  xor     edi, edi
0x18000866c  mov     [rsp+1118h+var_10D0], edi
0x180008670  mov     [rsp+1118h+var_10D4], edi
0x180008674  lea     rsi, [rcx+0D0h]
0x18000867b  mov     [rsp+1118h+var_10C8], rsi
0x180008680  mov     [rsp+1118h+var_10C0], dil
0x180008685  mov     rcx, cs:WPP_GLOBAL_Control
0x18000868c  test    byte ptr [rcx+1Ch], 40h
0x180008690  jnz     loc_180008843
0x180008696  cmp     dword ptr [rbx+88h], 0
0x18000869d  jnz     loc_18000889C
0x1800086a3  mov     rcx, rsi
0x1800086a6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800086ac  call    cs:__imp_GetCurrentThreadId
0x1800086b2  mov     [rsp+1118h+var_10BC], eax
0x1800086b6  mov     [rsp+1118h+var_10C0], 1
0x1800086bb  lea     r15, [rbx+84h]
0x1800086c2  mov     [rsp+1118h+var_10A8], r15
0x1800086c7  mov     eax, [r15]
0x1800086ca  dec     eax
0x1800086cc  cmp     eax, 1
0x1800086cf  jbe     loc_1800089A9
0x1800086d5  cmp     dword ptr [rbx+0ACh], 0
0x1800086dc  jnz     loc_1800087F0
0x1800086e2  lea     r12, [rbx+7Ch]
0x1800086e6  cmp     dword ptr [r12], 0
0x1800086eb  jz      loc_180008A7B
0x1800086f1  mov     [rsp+1118h+var_10D4], 1000h
0x1800086f9  lea     rax, [rsp+1118h+var_10D4]
0x1800086fe  mov     [rsp+1118h+var_10F0], rax
0x180008703  lea     rax, [rsp+1118h+var_1038]
0x18000870b  mov     [rsp+1118h+var_10F8], rax; struct _GUID *
0x180008710  lea     r9, [rsp+1118h+var_10D0]
0x180008715  xor     r8d, r8d
0x180008718  xor     edx, edx
0x18000871a  mov     rcx, r12
0x18000871d  call    cs:__imp_NtQueryWnfStateData
0x180008723  mov     r14d, eax
0x180008726  mov     rax, cs:WPP_GLOBAL_Control
0x18000872d  test    byte ptr [rax+1Ch], 40h
0x180008731  jnz     loc_18000896F
0x180008737  test    r14d, r14d
0x18000873a  js      loc_180008A41
0x180008740  mov     [rsp+1118h+var_10B0], r12
0x180008745  lea     r13, [rbx+0A8h]
0x18000874c  mov     [rsp+1118h+var_10A0], r13
0x180008751  mov     byte ptr [r13+0], 0
0x180008756  mov     eax, [rbx+0B8h]
0x18000875c  cmp     [rsp+1118h+var_10D4], eax
0x180008760  jb      loc_1800088B8
0x180008766  mov     r14d, [rsp+1118h+var_1038.Data1]
0x18000876e  shr     r14d, 1
0x180008771  and     r14b, 1
0x180008775  mov     [rsp+1118h+var_10D8], r14b
0x18000877a  jz      loc_180008ACB
0x180008780  mov     rcx, cs:WPP_GLOBAL_Control
0x180008787  mov     eax, [rbx+64h]
0x18000878a  cmp     eax, 1
0x18000878d  jz      loc_1800088FC
0x180008793  add     eax, 0FFFFFFFEh
0x180008796  cmp     eax, 1
0x180008799  jbe     loc_18000895F
0x18000879f  test    byte ptr [rcx+1Ch], 1
0x1800087a3  jz      short loc_1800087AF
0x1800087a5  cmp     byte ptr [rcx+19h], 4
0x1800087a9  jnb     loc_180008A10
0x1800087af  test    byte ptr [rcx+1Ch], 40h
0x1800087b3  jnz     loc_1800089E5
0x1800087b9  lea     rcx, [rbx+0B0h]
0x1800087c0  mov     [rsp+1118h+var_10E0], edi
0x1800087c4  mov     [rsp+1118h+var_10E8], edi
0x1800087c8  mov     [rsp+1118h+var_10F0], rdi
0x1800087cd  mov     [rsp+1118h+var_10F8], rbx
0x1800087d2  lea     r9, ?SebPublishWnfEventCallback@Broker@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Broker::SebPublishWnfEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800087d9  mov     r8d, [rsp+1118h+var_10D0]
0x1800087de  mov     rdx, [r12]
0x1800087e2  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800087e8  test    eax, eax
0x1800087ea  jnz     loc_180008B0D
0x1800087f0  mov     dword ptr [r15], 1
0x1800087f7  mov     rcx, r15
0x1800087fa  call    cs:__imp_RtlWakeAddressAll
0x180008800  mov     rax, cs:WPP_GLOBAL_Control
0x180008807  test    byte ptr [rax+1Ch], 40h
0x18000880b  jnz     short loc_180008875
0x18000880d  mov     rcx, rsi
0x180008810  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008816  mov     rcx, [rsp+1118h+var_38]
0x18000881e  xor     rcx, rsp; StackCookie
0x180008821  call    __security_check_cookie
0x180008826  lea     r11, [rsp+1118h+var_28]
0x18000882e  mov     rbx, [r11+38h]
0x180008832  mov     rsi, [r11+40h]
0x180008836  mov     rsp, r11
0x180008839  pop     r15
0x18000883b  pop     r14
0x18000883d  pop     r13
0x18000883f  pop     r12
0x180008841  pop     rdi
0x180008842  retn
0x180008843  cmp     byte ptr [rcx+19h], 4
0x180008847  jb      loc_180008696
0x18000884d  mov     edx, 12h
0x180008852  mov     r9, [rbx+0E0h]
0x180008859  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008860  mov     rcx, [rcx+10h]
0x180008864  call    WPP_SF__guid_
0x180008869  mov     rcx, cs:WPP_GLOBAL_Control
0x180008870  jmp     loc_180008696
0x180008875  cmp     byte ptr [rax+19h], 4
0x180008879  jb      short loc_18000880D
0x18000887b  mov     edx, 1Ch
0x180008880  mov     r9, [rbx+0E0h]
0x180008887  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x18000888e  mov     rcx, [rax+10h]
0x180008892  call    WPP_SF__guid_
0x180008897  jmp     loc_18000880D
0x18000889c  cmp     byte ptr [rbx+0A9h], 0
0x1800088a3  jz      loc_1800086A3
0x1800088a9  test    byte ptr [rcx+1Ch], 40h
0x1800088ad  jnz     loc_180008AA0
0x1800088b3  jmp     loc_180008816
0x1800088b8  xor     r14b, r14b
0x1800088bb  mov     [rsp+1118h+var_10D8], r14b
0x1800088c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088c7  test    byte ptr [rcx+1Ch], 40h
0x1800088cb  jz      loc_180008787
0x1800088d1  cmp     byte ptr [rcx+19h], 2
0x1800088d5  jb      loc_180008787
0x1800088db  mov     edx, 17h
0x1800088e0  mov     r9, [rbx+0E0h]
0x1800088e7  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x1800088ee  mov     rcx, [rcx+10h]
0x1800088f2  call    WPP_SF__guid_
0x1800088f7  jmp     loc_180008780
0x1800088fc  mov     dword ptr [r15], 1
0x180008903  mov     rcx, r15
0x180008906  call    cs:__imp_RtlWakeAddressAll
0x18000890c  cmp     [rsp+1118h+var_10D4], 8
0x180008911  jb      loc_180008AD5
0x180008917  mov     rcx, rsi
0x18000891a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008920  nop
0x180008921  lea     r8, [rsp+1118h+var_1038.Data4]
0x180008929  mov     r9d, [rsp+1118h+var_10D4]
0x18000892e  cmp     r9d, 8
0x180008932  cmovbe  r8, rdi; void *
0x180008936  add     r9d, 0FFFFFFF8h; unsigned int
0x18000893a  movzx   edx, r14b; unsigned __int8
0x18000893e  mov     rcx, rbx; this
0x180008941  call    ?OnSignaled@SebEvent@Broker@@QEAAKEPEBXIPEBU_GUID@@@Z; Broker::SebEvent::OnSignaled(uchar,void const *,uint,_GUID const *)
0x180008946  nop
0x180008947  mov     rcx, rsi
0x18000894a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180008950  call    cs:__imp_GetCurrentThreadId
0x180008956  mov     [rsp+1118h+var_10BC], eax
0x18000895a  mov     [rsp+1118h+var_10C0], 1
0x18000895f  mov     [r13+0], r14b
0x180008963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000896a  jmp     loc_18000879F
0x18000896f  cmp     byte ptr [rax+19h], 4
0x180008973  jb      loc_180008737
0x180008979  mov     edx, 15h
0x18000897e  mov     ecx, [rsp+1118h+var_10D4]
0x180008982  mov     dword ptr [rsp+1118h+var_10F8], ecx
0x180008986  mov     r9, [rbx+0E0h]
0x18000898d  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008994  mov     rcx, [rax+10h]
0x180008998  call    WPP_SF__guid_D
0x18000899d  mov     rax, cs:WPP_GLOBAL_Control
0x1800089a4  jmp     loc_180008737
0x1800089a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800089b0  test    byte ptr [rax+1Ch], 40h
0x1800089b4  jz      loc_18000880D
0x1800089ba  cmp     byte ptr [rax+19h], 4
0x1800089be  jb      loc_180008807
0x1800089c4  mov     edx, 14h
0x1800089c9  mov     r9, [rbx+0E0h]
0x1800089d0  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x1800089d7  mov     rcx, [rax+10h]
0x1800089db  call    WPP_SF__guid_
0x1800089e0  jmp     loc_180008800
0x1800089e5  cmp     byte ptr [rcx+19h], 4
0x1800089e9  jb      loc_1800087B9
0x1800089ef  mov     edx, 1Ah
0x1800089f4  mov     r9, [rbx+0E0h]
0x1800089fb  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008a02  mov     rcx, [rcx+10h]
0x180008a06  call    WPP_SF__guid_
0x180008a0b  jmp     loc_1800087B9
0x180008a10  movzx   eax, byte ptr [r13+0]
0x180008a15  mov     edx, 19h
0x180008a1a  mov     dword ptr [rsp+1118h+var_10F8], eax
0x180008a1e  mov     r9, [rbx+0E0h]
0x180008a25  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008a2c  mov     rcx, [rcx+10h]
0x180008a30  call    WPP_SF__guid_D
0x180008a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a3c  jmp     loc_1800087AF
0x180008a41  test    byte ptr [rax+1Ch], 40h
0x180008a45  jz      loc_18000880D
0x180008a4b  cmp     byte ptr [rax+19h], 2
0x180008a4f  jb      loc_180008807
0x180008a55  mov     edx, 16h
0x180008a5a  mov     dword ptr [rsp+1118h+var_10F8], r14d
0x180008a5f  mov     r9, [rbx+0E0h]
0x180008a66  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008a6d  mov     rcx, [rax+10h]
0x180008a71  call    WPP_SF__guid_D
0x180008a76  jmp     loc_180008800
0x180008a7b  cmp     dword ptr [rbx+80h], 0
0x180008a82  jnz     loc_1800086F1
0x180008a88  mov     [rbx+0B0h], rdi
0x180008a8f  mov     [r15], edi
0x180008a92  mov     rcx, r15
0x180008a95  call    cs:__imp_RtlWakeAddressAll
0x180008a9b  jmp     loc_180008800
0x180008aa0  cmp     byte ptr [rcx+19h], 4
0x180008aa4  jb      loc_1800088B3
0x180008aaa  mov     edx, 13h
0x180008aaf  mov     r9, [rbx+0E0h]
0x180008ab6  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008abd  mov     rcx, [rcx+10h]
0x180008ac1  call    WPP_SF__guid_
0x180008ac6  jmp     loc_1800088B3
0x180008acb  mov     byte ptr [r13+0], 1
0x180008ad0  jmp     loc_180008780
0x180008ad5  mov     [rsp+1118h+var_10D4], 8
0x180008add  mov     byte ptr [r13+0], 1
0x180008ae2  jmp     loc_180008917
0x180008ae7  xor     edi, edi
0x180008ae9  movzx   r14d, [rsp+1118h+var_10D8]
0x180008aef  mov     rsi, [rsp+1118h+var_10C8]
0x180008af4  mov     rbx, [rsp+1118h+var_10B8]
0x180008af9  mov     r12, [rsp+1118h+var_10B0]
0x180008afe  mov     r15, [rsp+1118h+var_10A8]
0x180008b03  mov     r13, [rsp+1118h+var_10A0]
0x180008b08  jmp     loc_180008947
0x180008b0d  cmp     eax, 0C0000022h
0x180008b12  jnz     short loc_180008B4E
0x180008b14  xorps   xmm0, xmm0
0x180008b17  movups  [rsp+1118h+var_1090], xmm0
0x180008b1f  mov     [rsp+1118h+var_1080], 5
0x180008b2a  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180008b31  mov     [rsp+1118h+pExceptionObject], rax
0x180008b39  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180008b40  lea     rcx, [rsp+1118h+pExceptionObject]; pExceptionObject
0x180008b48  call    _CxxThrowException_0
0x180008b4e  cmp     eax, 0C0000034h
0x180008b53  jnz     short loc_180008B8F
0x180008b55  xorps   xmm0, xmm0
0x180008b58  movups  [rsp+1118h+var_1070], xmm0
0x180008b60  mov     [rsp+1118h+var_1060], 3
0x180008b6b  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180008b72  mov     [rsp+1118h+var_1078], rax
0x180008b7a  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180008b81  lea     rcx, [rsp+1118h+var_1078]; pExceptionObject
0x180008b89  call    _CxxThrowException_0
0x180008b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b96  test    byte ptr [rcx+1Ch], 40h
0x180008b9a  jz      short loc_180008BBA
0x180008b9c  cmp     byte ptr [rcx+19h], 2
0x180008ba0  jb      short loc_180008BBA
0x180008ba2  mov     edx, 1Bh
0x180008ba7  mov     r9d, eax
0x180008baa  lea     r8, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180008bb1  mov     rcx, [rcx+10h]
0x180008bb5  call    WPP_SF_d
0x180008bba  xorps   xmm0, xmm0
0x180008bbd  movups  [rsp+1118h+var_1050], xmm0
0x180008bc5  mov     [rsp+1118h+var_1040], 7
0x180008bd0  lea     rax, ??_7EventInternalError@Broker@@6B@; const Broker::EventInternalError::`vftable'
0x180008bd7  mov     [rsp+1118h+var_1058], rax
0x180008bdf  lea     rdx, _TI3?AUEventInternalError@Broker@@; pThrowInfo
0x180008be6  lea     rcx, [rsp+1118h+var_1058]; pExceptionObject
0x180008bee  call    _CxxThrowException_0
```
