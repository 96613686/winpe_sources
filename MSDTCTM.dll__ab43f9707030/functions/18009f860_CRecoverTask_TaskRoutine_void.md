# CRecoverTask::TaskRoutine(void)

- ea: `0x18009f860`
- end: `0x18009fe58`
- name: `?TaskRoutine@CRecoverTask@@UEAAXXZ`
- size: `1528`
- prototype: `void __fastcall(CRecoverTask *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18009b528`
- `0x18009e0e8`
- `0x18009f860`
- `0x1800a05e4`
- `0x1800a06b8`
- `0x1800b83e2`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f8fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f8fb`

## string_xrefs

- `0x18009fdbe`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f962`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f9ca`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009fb20`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009fb7f`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009fca3`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009fd02`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f942`: `CRecoverTask::TaskRoutine - calling xa_recover - DLL=%S`
- `0x18009f9aa`: `CRecoverTask::TaskRoutine - returned from xa_recover with count=%d - DLL=%S`
- `0x18009f8c5`: `CRecoverTask::TaskRoutine`
- `0x18009fb0e`: `CRecoverTask::TaskRoutine`
- `0x18009fb6d`: `CRecoverTask::TaskRoutine`
- `0x18009fc91`: `CRecoverTask::TaskRoutine`
- `0x18009fcf0`: `CRecoverTask::TaskRoutine`
- `0x18009faf9`: `CRecoverTask::TaskRoutine - calling xa_rollback - DLL=%S`
- `0x18009fb58`: `CRecoverTask::TaskRoutine - returned from xa_rollback with error=%d - DLL=%S`
- `0x18009fcdb`: `CRecoverTask::TaskRoutine - returned from xa_commit with error=%d - DLL=%S`
- `0x18009fc7c`: `CRecoverTask::TaskRoutine - calling xa_commit - DLL=%S`

## pseudocode

```c
void __fastcall CRecoverTask::TaskRoutine(CRecoverTask *this)
{
  int v2; // r12d
  BOOL v3; // esi
  int v4; // r15d
  unsigned int v5; // edi
  _QWORD *v6; // r14
  int *v7; // rax
  int v8; // eax
  _DWORD *v9; // r13
  _QWORD *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+20h] [rbp-628h]
  __int64 v13; // [rsp+28h] [rbp-620h]
  __int64 v14; // [rsp+38h] [rbp-610h]
  unsigned int v15; // [rsp+50h] [rbp-5F8h]
  int v16; // [rsp+58h] [rbp-5F0h]
  __int128 v18; // [rsp+68h] [rbp-5E0h] BYREF
  __int128 v19; // [rsp+78h] [rbp-5D0h]
  _DWORD v20[352]; // [rsp+90h] [rbp-5B8h] BYREF

  v2 = 0;
  v3 = 1;
  v4 = 1;
  v18 = 0;
  v19 = 0;
  v5 = 0x1000000;
  v15 = XaRmId(*((_DWORD *)this + 20));
  while ( v3 )
  {
    v6 = (_QWORD *)((char *)this + 88);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
    **((_DWORD **)this + 16) = 0;
    EnterCriticalSection(&stru_180153898);
    if ( *((_DWORD *)CTaskManager::GetMyXaOpenState(*((_DWORD *)this + 20)) + 29) )
      **((_DWORD **)this + 16) = -3;
    LeaveCriticalSection(&stru_180153898);
    if ( !**((_DWORD **)this + 16) )
    {
      try
      {
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1583,
          L"CRecoverTask::TaskRoutine",
          0,
          L"CRecoverTask::TaskRoutine - calling xa_recover - DLL=%S",
          *((_QWORD *)this + 8));
        v2 = (*(__int64 (__fastcall **)(_DWORD *, __int64, _QWORD, _QWORD))(*((_QWORD *)this + 15) + 96LL))(
               v20,
               10,
               v15,
               v5);
        LODWORD(v14) = v2;
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1587,
          L"CRecoverTask::TaskRoutine",
          0,
          L"CRecoverTask::TaskRoutine - returned from xa_recover with count=%d - DLL=%S",
          v14,
          *((_QWORD *)this + 8));
      }
      catch ( ... )
      {
        LODWORD(v13) = -2147430317;
        TraceStringInline(
          11,
          1,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1592,
          L"CRecoverTask::TaskRoutine",
          v13,
          L"CRecoverTask::TaskRoutine - exception thrown calling xa_recover - DLL=%S",
          *((_QWORD *)this + 8));
        XA_TRACE_WARNING(
          0x8000D053,
          "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1593,
          *((char **)this + 8),
          v12);
        DtcXaException("xa_recovery");
      }
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 40LL))(*v6);
    v7 = (int *)*((_QWORD *)this + 16);
    if ( *v7 )
      goto LABEL_24;
    if ( v2 < 0 )
    {
      *v7 = v2;
      goto LABEL_24;
    }
    v8 = 0;
    v3 = (unsigned int)v2 >= 0xA;
    while ( 1 )
    {
      v16 = v8;
      if ( v8 >= v2 )
        break;
      v9 = &v20[35 * v8];
      if ( !memcmp_0(&g_guidXATM, v9 + 7, 0x10u) )
      {
        v10 = (_QWORD *)*((_QWORD *)this + 13);
        v11 = *v10 - *(_QWORD *)(v9 + 11);
        if ( *v10 == *(_QWORD *)(v9 + 11) )
          v11 = v10[1] - *(_QWORD *)(v9 + 13);
        if ( !v11 )
        {
          v18 = *(_OWORD *)(v9 + 3);
          v19 = *(_OWORD *)(v9 + 11);
          if ( (*(unsigned int (__fastcall **)(_QWORD, __int128 *, __int64))(**((_QWORD **)this + 12) + 32LL))(
                 *((_QWORD *)this + 12),
                 &v18,
                 32) )
          {
            **((_DWORD **)this + 16) = -3;
          }
          else
          {
            XA_TRACE_WARNING(0x8000D027, 0, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1837);
            v4 = 0;
          }
          v3 = 0;
          break;
        }
      }
      v8 = v16 + 1;
    }
    v5 = 0;
  }
  if ( v4 == 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 40LL))(*((_QWORD *)this + 12));
  v6 = (_QWORD *)((char *)this + 88);
LABEL_24:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 16LL))(*((_QWORD *)this + 12));
  *((_QWORD *)this + 12) = 0;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 24LL))(*v6);
  *v6 = 0;
  (*(void (__fastcall **)(CRecoverTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009f860  mov     [rsp+arg_8], rbx
0x18009f865  mov     [rsp+arg_10], rsi
0x18009f86a  push    rdi
0x18009f86b  push    r12
0x18009f86d  push    r13
0x18009f86f  push    r14
0x18009f871  push    r15
0x18009f873  sub     rsp, 620h
0x18009f87a  mov     rax, cs:__security_cookie
0x18009f881  xor     rax, rsp
0x18009f884  mov     [rsp+648h+var_38], rax
0x18009f88c  mov     rbx, rcx
0x18009f88f  mov     [rsp+648h+var_5E8], rcx
0x18009f894  xor     r12d, r12d
0x18009f897  lea     r14d, [r12+1]
0x18009f89c  mov     esi, r14d
0x18009f89f  mov     r15d, r14d
0x18009f8a2  mov     [rsp+648h+var_5F4], r12d
0x18009f8a7  xorps   xmm0, xmm0
0x18009f8aa  movups  [rsp+648h+var_5E0], xmm0
0x18009f8af  movups  [rsp+648h+var_5D0], xmm0
0x18009f8b4  mov     edi, 1000000h
0x18009f8b9  mov     ecx, [rcx+50h]; unsigned int
0x18009f8bc  call    ?XaRmId@@YAKI@Z; XaRmId(uint)
0x18009f8c1  mov     [rsp+648h+var_5F8], eax
0x18009f8c5  lea     r13, aCrecovertaskTa_6; "CRecoverTask::TaskRoutine"
0x18009f8cc  test    esi, esi
0x18009f8ce  jz      loc_18009FDD4
0x18009f8d4  lea     r14, [rbx+58h]
0x18009f8d8  mov     rcx, [r14]
0x18009f8db  mov     rax, [rcx]
0x18009f8de  mov     rax, [rax+20h]
0x18009f8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f8e7  mov     rax, [rbx+80h]
0x18009f8ee  mov     dword ptr [rax], 0
0x18009f8f4  lea     rcx, stru_180153898; lpCriticalSection
0x18009f8fb  call    cs:__imp_EnterCriticalSection
0x18009f901  mov     ecx, [rbx+50h]; unsigned int
0x18009f904  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x18009f909  cmp     dword ptr [rax+74h], 0
0x18009f90d  jz      short loc_18009F91C
0x18009f90f  mov     rax, [rbx+80h]
0x18009f916  mov     dword ptr [rax], 0FFFFFFFDh
0x18009f91c  lea     rcx, stru_180153898; lpCriticalSection
0x18009f923  call    cs:__imp_LeaveCriticalSection
0x18009f929  mov     rax, [rbx+80h]
0x18009f930  cmp     dword ptr [rax], 0
0x18009f933  jnz     loc_18009F9E1
0x18009f939  mov     rax, [rbx+40h]
0x18009f93d  mov     [rsp+648h+var_610], rax
0x18009f942  lea     rax, aCrecovertaskTa_4; "CRecoverTask::TaskRoutine - calling xa_"...
0x18009f949  mov     [rsp+648h+var_618], rax
0x18009f94e  mov     [rsp+648h+var_620], 0
0x18009f957  mov     [rsp+648h+var_628], r13
0x18009f95c  mov     r9d, 62Fh
0x18009f962  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f969  mov     edx, 4
0x18009f96e  lea     ecx, [rdx+7]
0x18009f971  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f976  mov     rax, [rbx+78h]
0x18009f97a  mov     r9d, edi
0x18009f97d  mov     edi, [rsp+648h+var_5F8]
0x18009f981  mov     r8d, edi
0x18009f984  mov     edx, 0Ah
0x18009f989  lea     rcx, [rsp+648h+var_5B8]
0x18009f991  mov     rax, [rax+60h]
0x18009f995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f99a  mov     r12d, eax
0x18009f99d  mov     rcx, [rbx+40h]
0x18009f9a1  mov     [rsp+648h+var_608], rcx
0x18009f9a6  mov     dword ptr [rsp+648h+var_610], eax
0x18009f9aa  lea     rax, aCrecovertaskTa_2; "CRecoverTask::TaskRoutine - returned fr"...
0x18009f9b1  mov     [rsp+648h+var_618], rax
0x18009f9b6  mov     [rsp+648h+var_620], 0
0x18009f9bf  mov     [rsp+648h+var_628], r13
0x18009f9c4  mov     r9d, 633h
0x18009f9ca  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f9d1  mov     edx, 4
0x18009f9d6  lea     ecx, [rdx+7]
0x18009f9d9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f9de  nop
0x18009f9df  jmp     short loc_18009F9E5
0x18009f9e1  mov     edi, [rsp+648h+var_5F8]
0x18009f9e5  mov     rcx, [r14]
0x18009f9e8  mov     rax, [rcx]
0x18009f9eb  mov     rax, [rax+28h]
0x18009f9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9f4  mov     rax, [rbx+80h]
0x18009f9fb  cmp     dword ptr [rax], 0
0x18009f9fe  jnz     loc_18009FDEE
0x18009fa04  test    r12d, r12d
0x18009fa07  jns     short loc_18009FA11
0x18009fa09  mov     [rax], r12d
0x18009fa0c  jmp     loc_18009FDEE
0x18009fa11  xor     eax, eax
0x18009fa13  xor     esi, esi
0x18009fa15  cmp     r12d, 0Ah
0x18009fa19  setnb   sil
0x18009fa1d  mov     [rsp+648h+var_5F0], eax
0x18009fa21  cmp     eax, r12d
0x18009fa24  jge     loc_18009FAC9
0x18009fa2a  cdqe
0x18009fa2c  imul    rcx, rax, 8Ch
0x18009fa33  lea     r13, [rsp+648h+var_5B8]
0x18009fa3b  add     r13, rcx
0x18009fa3e  lea     rdx, [r13+1Ch]; Buf2
0x18009fa42  mov     r8d, 10h; Size
0x18009fa48  lea     rcx, ?g_guidXATM@@3U_GUID@@A; Buf1
0x18009fa4f  call    memcmp_0
0x18009fa54  test    eax, eax
0x18009fa56  jnz     loc_18009FDA9
0x18009fa5c  mov     rcx, [rbx+68h]
0x18009fa60  mov     rax, [rcx]
0x18009fa63  sub     rax, [r13+2Ch]
0x18009fa67  jnz     short loc_18009FA71
0x18009fa69  mov     rax, [rcx+8]
0x18009fa6d  sub     rax, [r13+34h]
0x18009fa71  test    rax, rax
0x18009fa74  jnz     loc_18009FDA9
0x18009fa7a  movups  xmm0, xmmword ptr [r13+0Ch]
0x18009fa7f  movdqu  [rsp+648h+var_5E0], xmm0
0x18009fa85  movups  xmm1, xmmword ptr [r13+2Ch]
0x18009fa8a  movdqu  [rsp+648h+var_5D0], xmm1
0x18009fa90  mov     rcx, [rbx+60h]
0x18009fa94  mov     rax, [rcx]
0x18009fa97  lea     rdx, [rsp+648h+var_5F4]
0x18009fa9c  mov     [rsp+648h+var_628], rdx
0x18009faa1  xor     r9d, r9d
0x18009faa4  lea     r8d, [r9+20h]
0x18009faa8  lea     rdx, [rsp+648h+var_5E0]
0x18009faad  mov     rax, [rax+20h]
0x18009fab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fab6  test    eax, eax
0x18009fab8  jz      short loc_18009FAD0
0x18009faba  mov     rax, [rbx+80h]
0x18009fac1  mov     dword ptr [rax], 0FFFFFFFDh
0x18009fac7  xor     esi, esi
0x18009fac9  xor     edi, edi
0x18009facb  jmp     loc_18009F8C5
0x18009fad0  mov     edx, [rsp+648h+var_5F4]; unsigned int
0x18009fad4  cmp     edx, 200h
0x18009fada  jnz     loc_18009FC57
0x18009fae0  mov     rcx, [r14]
0x18009fae3  mov     rax, [rcx]
0x18009fae6  mov     rax, [rax+20h]
0x18009faea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009faef  nop
0x18009faf0  mov     rax, [rbx+40h]
0x18009faf4  mov     [rsp+648h+var_610], rax
0x18009faf9  lea     rax, aCrecovertaskTa_0; "CRecoverTask::TaskRoutine - calling xa_"...
0x18009fb00  mov     [rsp+648h+var_618], rax
0x18009fb05  mov     [rsp+648h+var_620], 0
0x18009fb0e  lea     rax, aCrecovertaskTa_6; "CRecoverTask::TaskRoutine"
0x18009fb15  mov     [rsp+648h+var_628], rax
0x18009fb1a  mov     r9d, 688h
0x18009fb20  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009fb27  mov     edx, 4
0x18009fb2c  lea     ecx, [rdx+7]
0x18009fb2f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009fb34  mov     rax, [rbx+78h]
0x18009fb38  xor     r8d, r8d
0x18009fb3b  mov     edx, edi
0x18009fb3d  mov     rcx, r13
0x18009fb40  mov     rax, [rax+48h]
0x18009fb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fb49  mov     edi, eax
0x18009fb4b  mov     rcx, [rbx+40h]
0x18009fb4f  mov     [rsp+648h+var_608], rcx
0x18009fb54  mov     dword ptr [rsp+648h+var_610], eax
0x18009fb58  lea     rax, aCrecovertaskTa_7; "CRecoverTask::TaskRoutine - returned fr"...
0x18009fb5f  mov     [rsp+648h+var_618], rax
0x18009fb64  mov     [rsp+648h+var_620], 0
0x18009fb6d  lea     rax, aCrecovertaskTa_6; "CRecoverTask::TaskRoutine"
0x18009fb74  mov     [rsp+648h+var_628], rax
0x18009fb79  mov     r9d, 68Ch
0x18009fb7f  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009fb86  mov     edx, 4
0x18009fb8b  lea     ecx, [rdx+7]
0x18009fb8e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009fb93  nop
0x18009fb94  mov     rcx, [r14]
0x18009fb97  mov     rax, [rcx]
0x18009fb9a  mov     rax, [rax+28h]
0x18009fb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fba3  test    edi, edi
0x18009fba5  jz      loc_18009FDA9
0x18009fbab  jns     short loc_18009FBBE
0x18009fbad  mov     rax, [rbx+80h]
0x18009fbb4  mov     [rax], edi
0x18009fbb6  xor     r15d, r15d
0x18009fbb9  jmp     loc_18009FAC7
0x18009fbbe  cmp     edi, 65h ; 'e'
0x18009fbc1  jg      short loc_18009FC0E
0x18009fbc3  jz      loc_18009FDA9
0x18009fbc9  mov     ecx, edi
0x18009fbcb  sub     ecx, 4
0x18009fbce  jz      short loc_18009FBF9
0x18009fbd0  sub     ecx, 1
0x18009fbd3  jz      loc_18009FD89
0x18009fbd9  sub     ecx, 1
0x18009fbdc  jz      loc_18009FDA9
0x18009fbe2  sub     ecx, 1
0x18009fbe5  jz      loc_18009FD89
0x18009fbeb  sub     ecx, 1
0x18009fbee  jz      loc_18009FD89
0x18009fbf4  cmp     ecx, 5Ch ; '\'
0x18009fbf7  jmp     short loc_18009FC40
0x18009fbf9  xor     r15d, r15d
0x18009fbfc  mov     rax, [rbx+80h]
0x18009fc03  mov     dword ptr [rax], 4
0x18009fc09  jmp     loc_18009FDA7
0x18009fc0e  mov     ecx, edi
0x18009fc10  sub     ecx, 66h ; 'f'
0x18009fc13  jz      loc_18009FDA9
0x18009fc19  sub     ecx, 1
0x18009fc1c  jz      loc_18009FDA9
0x18009fc22  sub     ecx, 1
0x18009fc25  jz      loc_18009FDA9
0x18009fc2b  sub     ecx, 1
0x18009fc2e  jz      loc_18009FDA9
0x18009fc34  sub     ecx, 1
0x18009fc37  jz      loc_18009FDA9
0x18009fc3d  cmp     ecx, 1
0x18009fc40  jz      loc_18009FDA9
0x18009fc46  xor     r15d, r15d
0x18009fc49  mov     rax, [rbx+80h]
0x18009fc50  mov     [rax], edi
0x18009fc52  jmp     loc_18009FDA7
0x18009fc57  cmp     edx, 400h
0x18009fc5d  jnz     loc_18009FDB8
0x18009fc63  mov     rcx, [r14]
0x18009fc66  mov     rax, [rcx]
0x18009fc69  mov     rax, [rax+20h]
0x18009fc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fc72  nop
0x18009fc73  mov     rax, [rbx+40h]
0x18009fc77  mov     [rsp+648h+var_610], rax
0x18009fc7c  lea     rax, aCrecovertaskTa_1; "CRecoverTask::TaskRoutine - calling xa_"...
0x18009fc83  mov     [rsp+648h+var_618], rax
0x18009fc88  mov     [rsp+648h+var_620], 0
0x18009fc91  lea     rax, aCrecovertaskTa_6; "CRecoverTask::TaskRoutine"
0x18009fc98  mov     [rsp+648h+var_628], rax
0x18009fc9d  mov     r9d, 6DCh
0x18009fca3  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009fcaa  mov     edx, 4
0x18009fcaf  lea     ecx, [rdx+7]
0x18009fcb2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009fcb7  mov     rax, [rbx+78h]
0x18009fcbb  xor     r8d, r8d
0x18009fcbe  mov     edx, edi
0x18009fcc0  mov     rcx, r13
0x18009fcc3  mov     rax, [rax+58h]
0x18009fcc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fccc  mov     edi, eax
0x18009fcce  mov     rcx, [rbx+40h]
0x18009fcd2  mov     [rsp+648h+var_608], rcx
0x18009fcd7  mov     dword ptr [rsp+648h+var_610], eax
0x18009fcdb  lea     rax, aCrecovertaskTa_8; "CRecoverTask::TaskRoutine - returned fr"...
0x18009fce2  mov     [rsp+648h+var_618], rax
0x18009fce7  mov     [rsp+648h+var_620], 0
0x18009fcf0  lea     rax, aCrecovertaskTa_6; "CRecoverTask::TaskRoutine"
0x18009fcf7  mov     [rsp+648h+var_628], rax
0x18009fcfc  mov     r9d, 6E0h
0x18009fd02  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009fd09  mov     edx, 4
0x18009fd0e  lea     ecx, [rdx+7]
0x18009fd11  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009fd16  nop
0x18009fd17  mov     rcx, [r14]
0x18009fd1a  mov     rax, [rcx]
0x18009fd1d  mov     rax, [rax+28h]
0x18009fd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fd26  test    edi, edi
0x18009fd28  jz      short loc_18009FDA9
0x18009fd2a  jns     short loc_18009FD3A
0x18009fd2c  mov     rax, [rbx+80h]
0x18009fd33  mov     [rax], edi
0x18009fd35  xor     r15d, r15d
0x18009fd38  jmp     short loc_18009FDA7
0x18009fd3a  cmp     edi, 65h ; 'e'
0x18009fd3d  jg      short loc_18009FD65
0x18009fd3f  jz      short loc_18009FD89
0x18009fd41  mov     ecx, edi
0x18009fd43  sub     ecx, 4
0x18009fd46  jz      loc_18009FBF9
0x18009fd4c  sub     ecx, 1
0x18009fd4f  jz      short loc_18009FD89
0x18009fd51  sub     ecx, 1
0x18009fd54  jz      short loc_18009FD89
0x18009fd56  sub     ecx, 1
0x18009fd59  jz      short loc_18009FDA9
0x18009fd5b  sub     ecx, 1
0x18009fd5e  jz      short loc_18009FD89
0x18009fd60  cmp     ecx, 5Ch ; '\'
0x18009fd63  jmp     short loc_18009FD83
0x18009fd65  mov     ecx, edi
0x18009fd67  sub     ecx, 66h ; 'f'
0x18009fd6a  jz      short loc_18009FD89
0x18009fd6c  sub     ecx, 1
0x18009fd6f  jz      short loc_18009FD89
  ... truncated ...
```
