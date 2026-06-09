# Broker::CKeepAliveEvent::SignalEvent(__int64)

- ea: `0x180017240`
- end: `0x1800177c7`
- name: `?SignalEvent@CKeepAliveEvent@Broker@@MEAAX_J@Z`
- size: `1415`
- prototype: `void __fastcall(Broker::CKeepAliveEvent *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003840`
- `0x180009f70`
- `0x180017240`
- `0x1800177d0`
- `0x180017828`
- `0x1800178b4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001730c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180017331`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800174c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001776f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001730c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180017331`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800174c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001776f`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001747d`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180017558`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001760c`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001768c`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180017723`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001747d`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180017558`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001760c`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001768c`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180017723`

## pseudocode

```c
void __fastcall Broker::CKeepAliveEvent::SignalEvent(Broker::CKeepAliveEvent *this, __int64 a2)
{
  unsigned __int64 v3; // rbp
  __int64 v4; // rbx
  _QWORD *v5; // r10
  int v6; // esi
  __int64 v7; // r15
  __int64 v8; // r12
  int v9; // r13d
  ULONGLONG v10; // r14
  ULONGLONG TickCount64; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // r14
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  int v17; // eax
  ULONGLONG v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  char v29; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+10h]
  __int64 v31; // [rsp+B0h] [rbp+18h]
  __int64 v32; // [rsp+B8h] [rbp+20h]

  v30 = a2;
  v3 = *((_QWORD *)this + 8);
  v4 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v29 = 1;
  v31 = *((_QWORD *)this + 7);
  v32 = v4;
  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v4,
      HIDWORD(v4));
    v5 = WPP_GLOBAL_Control;
  }
  v6 = HIDWORD(v32);
  if ( v3 || !*((_BYTE *)this + 313) )
  {
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = GetTickCount64() - *((_QWORD *)this + 38);
    v5 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      TickCount64 = GetTickCount64();
      WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v10, TickCount64);
      v5 = WPP_GLOBAL_Control;
    }
    v14 = 10000 * v10;
    if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 5u )
    {
      WPP_SF_DDLidd(
        v5[2],
        (*((_QWORD *)this + 3) + *((_QWORD *)this + 4)) % 2LL,
        *((_QWORD *)this + 6) / 600000000LL,
        (unsigned int)v4,
        v6,
        *((_DWORD *)this + 18),
        (*((_QWORD *)this + 3) + *((_QWORD *)this + 4)) / 2LL,
        (int)*((_QWORD *)this + 7) / 10000000,
        *((_QWORD *)this + 6) / 600000000LL);
      v5 = WPP_GLOBAL_Control;
    }
    v15 = *((_QWORD *)this + 32);
    v16 = *((_QWORD *)this + 33) - v15;
    if ( v16 > 0x10 )
    {
      v7 = *((_QWORD *)this + 32);
      v8 = v15 + 16;
      v9 = v16 - 16;
    }
    if ( !*((_BYTE *)this + 314) )
    {
      if ( v14 < v3 - v31 )
        goto LABEL_66;
      if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        WPP_SF_DD(v5[2], 22, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6);
      v17 = BrSignalBrokerEvent2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), &v29, v7, v9, v8);
      if ( v17 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_DDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
          (unsigned int)v4,
          v6,
          v17);
      *((_QWORD *)this + 37) = v30;
      v18 = GetTickCount64();
      *((_BYTE *)this + 313) = 1;
      goto LABEL_64;
    }
    if ( v30 < *((_QWORD *)this + 4) )
    {
      if ( !*((_BYTE *)this + 312) && v14 >= v3 - v31 )
      {
        if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 4u )
          WPP_SF_DD(v5[2], 24, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6);
        v19 = BrSignalBrokerEvent2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), &v29, v7, v9, v8);
        if ( v19 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_DDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
            (unsigned int)v4,
            v6,
            v19);
        *((_BYTE *)this + 312) = 1;
        goto LABEL_65;
      }
      goto LABEL_66;
    }
    if ( v14 < v3 )
      goto LABEL_66;
    if ( *((_BYTE *)this + 312) )
    {
      if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        WPP_SF_DD(v5[2], 26, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6);
      v20 = *((_QWORD *)this + 31);
      v21 = *((_QWORD *)this + 30);
      v29 = 0;
      v22 = BrSignalBrokerEvent2(v21, v20, &v29, v7, v9, v8);
      if ( !v22 )
        goto LABEL_63;
      v23 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_63;
      v24 = 27;
      goto LABEL_62;
    }
    if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_DD(v5[2], 28, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6);
    v25 = BrSignalBrokerEvent2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), &v29, v7, v9, v8);
    if ( v25 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      {
LABEL_58:
        v27 = *((_QWORD *)this + 31);
        v28 = *((_QWORD *)this + 30);
        v29 = 0;
        v22 = BrSignalBrokerEvent2(v28, v27, &v29, v7, v9, v8);
        if ( !v22 )
          goto LABEL_63;
        v23 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_63;
        v24 = 31;
LABEL_62:
        WPP_SF_DDD(v23[2], v24, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6, v22);
LABEL_63:
        *((_QWORD *)this + 37) = v30;
        v18 = GetTickCount64();
        *((_WORD *)this + 156) = 256;
LABEL_64:
        *((_QWORD *)this + 38) = v18;
        goto LABEL_65;
      }
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_55:
        if ( (*((_BYTE *)v26 + 28) & 0x40) != 0 && *((_BYTE *)v26 + 25) >= 4u )
          WPP_SF_DD(v26[2], 30, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6);
        goto LABEL_58;
      }
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
        (unsigned int)v4,
        v6,
        v25);
    }
    v26 = WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  if ( (*((_BYTE *)v5 + 28) & 0x40) == 0 )
    return;
  if ( *((_BYTE *)v5 + 25) >= 4u )
  {
    WPP_SF_(v5[2], 19, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids);
LABEL_65:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_66:
  if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_DD(v5[2], 32, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, (unsigned int)v4, v6);
}

```

## disassembly

```asm
0x180017240  mov     rax, rsp
0x180017243  mov     [rax+10h], rdx
0x180017247  push    rbx
0x180017248  push    rbp
0x180017249  push    rsi
0x18001724a  push    rdi
0x18001724b  push    r12
0x18001724d  push    r13
0x18001724f  push    r14
0x180017251  push    r15
0x180017253  sub     rsp, 58h
0x180017257  mov     rbx, [rcx+0F8h]
0x18001725e  mov     rdi, rcx
0x180017261  mov     rbp, [rcx+40h]
0x180017265  mov     rbx, [rbx+10h]
0x180017269  mov     byte ptr [rax+8], 1
0x18001726d  mov     rax, [rcx+38h]
0x180017271  mov     [rsp+98h+arg_10], rax
0x180017279  mov     [rsp+98h+arg_18], rbx
0x180017281  mov     r10, cs:WPP_GLOBAL_Control
0x180017288  test    byte ptr [r10+1Ch], 40h
0x18001728d  jz      short loc_1800172C0
0x18001728f  cmp     byte ptr [r10+19h], 4
0x180017294  jb      short loc_1800172C0
0x180017296  mov     rcx, [r10+10h]
0x18001729a  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800172a1  mov     rax, rbx
0x1800172a4  mov     edx, 12h
0x1800172a9  shr     rax, 20h
0x1800172ad  mov     r9d, ebx
0x1800172b0  mov     dword ptr [rsp+98h+var_78], eax
0x1800172b4  call    WPP_SF_DD
0x1800172b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800172c0  mov     esi, dword ptr [rsp+98h+arg_18+4]
0x1800172c7  test    rbp, rbp
0x1800172ca  jnz     short loc_180017303
0x1800172cc  cmp     [rdi+139h], bpl
0x1800172d3  jz      short loc_180017303
0x1800172d5  test    byte ptr [r10+1Ch], 40h
0x1800172da  jz      loc_1800177B6
0x1800172e0  cmp     byte ptr [r10+19h], 4
0x1800172e5  jb      loc_18001778C
0x1800172eb  mov     rcx, [r10+10h]
0x1800172ef  lea     edx, [rbp+13h]
0x1800172f2  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800172f9  call    WPP_SF_
0x1800172fe  jmp     loc_180017785
0x180017303  xor     r15d, r15d
0x180017306  xor     r12d, r12d
0x180017309  xor     r13d, r13d
0x18001730c  call    cs:__imp_GetTickCount64
0x180017312  mov     r14, rax
0x180017315  sub     r14, [rdi+130h]
0x18001731c  mov     r10, cs:WPP_GLOBAL_Control
0x180017323  test    byte ptr [r10+1Ch], 40h
0x180017328  jz      short loc_180017356
0x18001732a  cmp     byte ptr [r10+19h], 5
0x18001732f  jb      short loc_180017356
0x180017331  call    cs:__imp_GetTickCount64
0x180017337  mov     rcx, cs:WPP_GLOBAL_Control
0x18001733e  mov     r9, r14
0x180017341  mov     [rsp+98h+var_78], rax
0x180017346  mov     rcx, [rcx+10h]
0x18001734a  call    WPP_SF_II
0x18001734f  mov     r10, cs:WPP_GLOBAL_Control
0x180017356  imul    r14, 2710h
0x18001735d  test    byte ptr [r10+1Ch], 40h
0x180017362  mov     r9d, 2
0x180017368  jz      loc_1800173F0
0x18001736e  cmp     byte ptr [r10+19h], 5
0x180017373  jb      short loc_1800173F0
0x180017375  mov     rax, 1CA213D840BAF7D5h
0x18001737f  imul    qword ptr [rdi+30h]
0x180017383  mov     r8, rdx
0x180017386  sar     r8, 1Ah
0x18001738a  mov     rax, r8
0x18001738d  shr     rax, 3Fh
0x180017391  add     r8, rax
0x180017394  mov     rax, 0D6BF94D5E57A42BDh
0x18001739e  imul    qword ptr [rdi+38h]
0x1800173a2  mov     [rsp+98h+var_58], r8d
0x1800173a7  mov     rcx, rdx
0x1800173aa  add     rcx, [rdi+38h]
0x1800173ae  sar     rcx, 17h
0x1800173b2  mov     rax, rcx
0x1800173b5  shr     rax, 3Fh
0x1800173b9  add     rcx, rax
0x1800173bc  mov     rax, [rdi+20h]
0x1800173c0  add     rax, [rdi+18h]
0x1800173c4  cqo
0x1800173c6  mov     [rsp+98h+var_60], ecx
0x1800173ca  mov     rcx, [r10+10h]
0x1800173ce  idiv    r9
0x1800173d1  mov     r9d, ebx
0x1800173d4  mov     [rsp+98h+var_68], rax
0x1800173d9  mov     eax, [rdi+48h]
0x1800173dc  mov     dword ptr [rsp+98h+var_70], eax
0x1800173e0  mov     dword ptr [rsp+98h+var_78], esi
0x1800173e4  call    WPP_SF_DDLidd
0x1800173e9  mov     r10, cs:WPP_GLOBAL_Control
0x1800173f0  mov     rcx, [rdi+100h]
0x1800173f7  mov     rax, [rdi+108h]
0x1800173fe  sub     rax, rcx
0x180017401  cmp     rax, 10h
0x180017405  jbe     short loc_180017412
0x180017407  mov     r15, rcx
0x18001740a  lea     r12, [rcx+10h]
0x18001740e  lea     r13d, [rax-10h]
0x180017412  cmp     byte ptr [rdi+13Ah], 0
0x180017419  jnz     loc_1800174DB
0x18001741f  sub     rbp, [rsp+98h+arg_10]
0x180017427  cmp     r14, rbp
0x18001742a  jb      loc_18001778C
0x180017430  test    byte ptr [r10+1Ch], 40h
0x180017435  jz      short loc_18001745A
0x180017437  cmp     byte ptr [r10+19h], 4
0x18001743c  jb      short loc_18001745A
0x18001743e  mov     rcx, [r10+10h]
0x180017442  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017449  mov     edx, 16h
0x18001744e  mov     dword ptr [rsp+98h+var_78], esi
0x180017452  mov     r9d, ebx
0x180017455  call    WPP_SF_DD
0x18001745a  mov     rdx, [rdi+0F8h]
0x180017461  lea     r8, [rsp+98h+arg_0]
0x180017469  mov     rcx, [rdi+0F0h]
0x180017470  mov     r9, r15
0x180017473  mov     [rsp+98h+var_70], r12
0x180017478  mov     dword ptr [rsp+98h+var_78], r13d
0x18001747d  call    cs:__imp_BrSignalBrokerEvent2
0x180017483  test    eax, eax
0x180017485  jz      short loc_1800174BA
0x180017487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001748e  test    byte ptr [rcx+1Ch], 40h
0x180017492  jz      short loc_1800174BA
0x180017494  cmp     byte ptr [rcx+19h], 2
0x180017498  jb      short loc_1800174BA
0x18001749a  mov     rcx, [rcx+10h]
0x18001749e  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800174a5  mov     dword ptr [rsp+98h+var_70], eax
0x1800174a9  mov     edx, 17h
0x1800174ae  mov     r9d, ebx
0x1800174b1  mov     dword ptr [rsp+98h+var_78], esi
0x1800174b5  call    WPP_SF_DDD
0x1800174ba  mov     rax, [rsp+98h+arg_8]
0x1800174c2  mov     [rdi+128h], rax
0x1800174c9  call    cs:__imp_GetTickCount64
0x1800174cf  mov     byte ptr [rdi+139h], 1
0x1800174d6  jmp     loc_18001777E
0x1800174db  mov     rax, [rsp+98h+arg_8]
0x1800174e3  cmp     rax, [rdi+20h]
0x1800174e7  jge     loc_1800175A1
0x1800174ed  cmp     byte ptr [rdi+138h], 0
0x1800174f4  jnz     loc_18001778C
0x1800174fa  sub     rbp, [rsp+98h+arg_10]
0x180017502  cmp     r14, rbp
0x180017505  jb      loc_18001778C
0x18001750b  test    byte ptr [r10+1Ch], 40h
0x180017510  jz      short loc_180017535
0x180017512  cmp     byte ptr [r10+19h], 4
0x180017517  jb      short loc_180017535
0x180017519  mov     rcx, [r10+10h]
0x18001751d  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017524  mov     edx, 18h
0x180017529  mov     dword ptr [rsp+98h+var_78], esi
0x18001752d  mov     r9d, ebx
0x180017530  call    WPP_SF_DD
0x180017535  mov     rdx, [rdi+0F8h]
0x18001753c  lea     r8, [rsp+98h+arg_0]
0x180017544  mov     rcx, [rdi+0F0h]
0x18001754b  mov     r9, r15
0x18001754e  mov     [rsp+98h+var_70], r12
0x180017553  mov     dword ptr [rsp+98h+var_78], r13d
0x180017558  call    cs:__imp_BrSignalBrokerEvent2
0x18001755e  test    eax, eax
0x180017560  jz      short loc_180017595
0x180017562  mov     rcx, cs:WPP_GLOBAL_Control
0x180017569  test    byte ptr [rcx+1Ch], 40h
0x18001756d  jz      short loc_180017595
0x18001756f  cmp     byte ptr [rcx+19h], 2
0x180017573  jb      short loc_180017595
0x180017575  mov     rcx, [rcx+10h]
0x180017579  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017580  mov     dword ptr [rsp+98h+var_70], eax
0x180017584  mov     edx, 19h
0x180017589  mov     r9d, ebx
0x18001758c  mov     dword ptr [rsp+98h+var_78], esi
0x180017590  call    WPP_SF_DDD
0x180017595  mov     byte ptr [rdi+138h], 1
0x18001759c  jmp     loc_180017785
0x1800175a1  cmp     r14, rbp
0x1800175a4  jb      loc_18001778C
0x1800175aa  xor     ebp, ebp
0x1800175ac  cmp     [rdi+138h], bpl
0x1800175b3  jz      loc_18001763F
0x1800175b9  test    byte ptr [r10+1Ch], 40h
0x1800175be  jz      short loc_1800175E1
0x1800175c0  cmp     byte ptr [r10+19h], 4
0x1800175c5  jb      short loc_1800175E1
0x1800175c7  mov     rcx, [r10+10h]
0x1800175cb  lea     edx, [rbp+1Ah]
0x1800175ce  mov     r9d, ebx
0x1800175d1  mov     dword ptr [rsp+98h+var_78], esi
0x1800175d5  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800175dc  call    WPP_SF_DD
0x1800175e1  mov     rdx, [rdi+0F8h]
0x1800175e8  lea     r8, [rsp+98h+arg_0]
0x1800175f0  mov     rcx, [rdi+0F0h]
0x1800175f7  mov     r9, r15
0x1800175fa  mov     [rsp+98h+var_70], r12
0x1800175ff  mov     dword ptr [rsp+98h+var_78], r13d
0x180017604  mov     [rsp+98h+arg_0], bpl
0x18001760c  call    cs:__imp_BrSignalBrokerEvent2
0x180017612  test    eax, eax
0x180017614  jz      loc_180017760
0x18001761a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017621  test    byte ptr [rcx+1Ch], 40h
0x180017625  jz      loc_180017760
0x18001762b  cmp     byte ptr [rcx+19h], 2
0x18001762f  jb      loc_180017760
0x180017635  mov     edx, 1Bh
0x18001763a  jmp     loc_180017745
0x18001763f  test    byte ptr [r10+1Ch], 40h
0x180017644  jz      short loc_180017669
0x180017646  cmp     byte ptr [r10+19h], 4
0x18001764b  jb      short loc_180017669
0x18001764d  mov     rcx, [r10+10h]
0x180017651  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017658  mov     edx, 1Ch
0x18001765d  mov     dword ptr [rsp+98h+var_78], esi
0x180017661  mov     r9d, ebx
0x180017664  call    WPP_SF_DD
0x180017669  mov     rdx, [rdi+0F8h]
0x180017670  lea     r8, [rsp+98h+arg_0]
0x180017678  mov     rcx, [rdi+0F0h]
0x18001767f  mov     r9, r15
0x180017682  mov     [rsp+98h+var_70], r12
0x180017687  mov     dword ptr [rsp+98h+var_78], r13d
0x18001768c  call    cs:__imp_BrSignalBrokerEvent2
0x180017692  test    eax, eax
0x180017694  jz      short loc_1800176C9
0x180017696  mov     rcx, cs:WPP_GLOBAL_Control
0x18001769d  test    byte ptr [rcx+1Ch], 40h
0x1800176a1  jz      short loc_1800176F8
0x1800176a3  cmp     byte ptr [rcx+19h], 2
0x1800176a7  jb      short loc_1800176D0
0x1800176a9  mov     rcx, [rcx+10h]
0x1800176ad  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800176b4  mov     dword ptr [rsp+98h+var_70], eax
0x1800176b8  mov     edx, 1Dh
0x1800176bd  mov     r9d, ebx
0x1800176c0  mov     dword ptr [rsp+98h+var_78], esi
0x1800176c4  call    WPP_SF_DDD
0x1800176c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176d0  test    byte ptr [rcx+1Ch], 40h
0x1800176d4  jz      short loc_1800176F8
0x1800176d6  cmp     byte ptr [rcx+19h], 4
0x1800176da  jb      short loc_1800176F8
0x1800176dc  mov     rcx, [rcx+10h]
0x1800176e0  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800176e7  mov     edx, 1Eh
0x1800176ec  mov     dword ptr [rsp+98h+var_78], esi
0x1800176f0  mov     r9d, ebx
0x1800176f3  call    WPP_SF_DD
0x1800176f8  mov     rdx, [rdi+0F8h]
0x1800176ff  lea     r8, [rsp+98h+arg_0]
0x180017707  mov     rcx, [rdi+0F0h]
0x18001770e  mov     r9, r15
0x180017711  mov     [rsp+98h+var_70], r12
0x180017716  mov     dword ptr [rsp+98h+var_78], r13d
0x18001771b  mov     [rsp+98h+arg_0], bpl
0x180017723  call    cs:__imp_BrSignalBrokerEvent2
0x180017729  test    eax, eax
0x18001772b  jz      short loc_180017760
0x18001772d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017734  test    byte ptr [rcx+1Ch], 40h
0x180017738  jz      short loc_180017760
0x18001773a  cmp     byte ptr [rcx+19h], 2
0x18001773e  jb      short loc_180017760
0x180017740  mov     edx, 1Fh
0x180017745  mov     rcx, [rcx+10h]
0x180017749  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017750  mov     dword ptr [rsp+98h+var_70], eax
0x180017754  mov     r9d, ebx
0x180017757  mov     dword ptr [rsp+98h+var_78], esi
0x18001775b  call    WPP_SF_DDD
0x180017760  mov     rax, [rsp+98h+arg_8]
0x180017768  mov     [rdi+128h], rax
0x18001776f  call    cs:__imp_GetTickCount64
0x180017775  mov     word ptr [rdi+138h], 100h
0x18001777e  mov     [rdi+130h], rax
0x180017785  mov     r10, cs:WPP_GLOBAL_Control
0x18001778c  test    byte ptr [r10+1Ch], 40h
0x180017791  jz      short loc_1800177B6
0x180017793  cmp     byte ptr [r10+19h], 4
0x180017798  jb      short loc_1800177B6
0x18001779a  mov     rcx, [r10+10h]
0x18001779e  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x1800177a5  mov     edx, 20h ; ' '
0x1800177aa  mov     dword ptr [rsp+98h+var_78], esi
  ... truncated ...
```
