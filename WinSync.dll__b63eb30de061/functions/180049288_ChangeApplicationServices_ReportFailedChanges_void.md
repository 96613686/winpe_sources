# ChangeApplicationServices::ReportFailedChanges(void)

- ea: `0x180049288`
- end: `0x180049516`
- name: `?ReportFailedChanges@ChangeApplicationServices@@AEAAJXZ`
- size: `654`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180047900`
- `0x180047a60`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x1800084ec`
- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001df64`
- `0x1800209f4`
- `0x180049288`
- `0x1800776d0`
- `0x180094010`

## string_xrefs

- `0x1800492c1`: `ChangeApplicationServices::ReportFailedChanges`
- `0x1800494e4`: `ChangeApplicationServices::ReportFailedChanges`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportFailedChanges(ChangeApplicationServices *this)
{
  int v2; // edi
  __int64 NextElement; // rax
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rcx
  void *v7; // rax
  __int64 *v8; // rcx
  int v9; // esi
  __int64 v10; // rax
  int v11; // r11d
  __int64 v12; // rax
  __int64 v13; // rcx
  void *v14; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+80h] [rbp+30h] BYREF
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportFailedChanges");
  }
  v2 = 0;
  v16[0] = (char *)this + 176;
  v16[1] = 0;
  while ( 1 )
  {
    NextElement = TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(v16);
    if ( !NextElement )
      break;
    v4 = NextElement + 16;
    v5 = *(_QWORD *)(NextElement + 16);
    if ( *(_DWORD *)(v5 + 72) )
    {
      v9 = 0;
      v17[0] = v5 + 56;
      v17[1] = 0;
      while ( 1 )
      {
        v10 = TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(v17);
        if ( !v10 )
          break;
        v12 = *(_QWORD *)(v10 + 16);
        if ( *(_DWORD *)(v12 + 20) == 1 )
        {
          v9 = 1;
          if ( v11 )
            goto LABEL_27;
        }
        if ( *(_DWORD *)(v12 + 20) == 2 )
        {
          v11 = 1;
          if ( v9 )
            break;
        }
      }
      if ( !v9 && !v11 )
        goto LABEL_29;
LABEL_27:
      ++*((_DWORD *)this + 55);
      v13 = *((_QWORD *)this + 19);
      if ( v13 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 72LL))(
               v13,
               *((unsigned int *)this + 54),
               *((unsigned int *)this + 55));
        if ( v2 < 0 )
          break;
      }
LABEL_29:
      if ( !*((_QWORD *)this + 18) || !v9 )
        continue;
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
      v14 = SeAlloc(0x40u);
      if ( v14 )
        v14 = (void *)ChangeApplicationRecoverableError::ChangeApplicationRecoverableError(v14, (char *)this + 40, v4);
      v2 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(&v19, (__int64)v14);
      if ( v2 >= 0 )
        v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 56LL))(*((_QWORD *)this + 18), v19);
      v8 = &v19;
      goto LABEL_36;
    }
    if ( *(_DWORD *)(v5 + 20) )
    {
      ++*((_DWORD *)this + 55);
      v6 = *((_QWORD *)this + 19);
      if ( v6 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 72LL))(
               v6,
               *((unsigned int *)this + 54),
               *((unsigned int *)this + 55));
        if ( v2 < 0 )
          break;
      }
      if ( *((_QWORD *)this + 18) && *(_DWORD *)(*(_QWORD *)v4 + 20LL) == 1 )
      {
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        v7 = SeAlloc(0x40u);
        if ( v7 )
          v7 = (void *)ChangeApplicationRecoverableError::ChangeApplicationRecoverableError(v7, (char *)this + 40, v4);
        v2 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(&v18, (__int64)v7);
        if ( v2 >= 0 )
          v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 56LL))(
                 *((_QWORD *)this + 18),
                 v18);
        v8 = &v18;
LABEL_36:
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(v8);
        goto LABEL_37;
      }
    }
    else
    {
LABEL_37:
      if ( v2 < 0 )
        break;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportFailedChanges",
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180049288  mov     [rsp-28h+arg_10], rbx
0x18004928d  push    rbp
0x18004928e  push    rsi
0x18004928f  push    rdi
0x180049290  push    r13
0x180049292  push    r14
0x180049294  mov     rbp, rsp
0x180049297  sub     rsp, 50h
0x18004929b  mov     rbx, rcx
0x18004929e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492a5  lea     r13, WPP_GLOBAL_Control
0x1800492ac  cmp     rcx, r13
0x1800492af  jz      short loc_1800492D9
0x1800492b1  test    byte ptr [rcx+1Ch], 80h
0x1800492b5  jz      short loc_1800492D9
0x1800492b7  cmp     byte ptr [rcx+19h], 5
0x1800492bb  jb      short loc_1800492D9
0x1800492bd  mov     rcx, [rcx+10h]
0x1800492c1  lea     r9, aChangeapplicat_4; "ChangeApplicationServices::ReportFailed"...
0x1800492c8  mov     edx, 36h ; '6'
0x1800492cd  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800492d4  call    WPP_SF_s
0x1800492d9  xor     edi, edi
0x1800492db  lea     rax, [rbx+0B0h]
0x1800492e2  mov     [rbp+var_20], rax
0x1800492e6  mov     [rbp+var_18], rdi
0x1800492ea  lea     rcx, [rbp+var_20]
0x1800492ee  call    ?GetNextElement@?$TableEnumerator@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(void)
0x1800492f3  test    rax, rax
0x1800492f6  jz      loc_1800494C8
0x1800492fc  lea     r14, [rax+10h]
0x180049300  mov     rax, [r14]
0x180049303  lea     rcx, [rax+38h]
0x180049307  cmp     dword ptr [rcx+10h], 0
0x18004930b  jnz     loc_1800493CA
0x180049311  cmp     dword ptr [rax+14h], 0
0x180049315  jz      loc_1800494C0
0x18004931b  inc     dword ptr [rbx+0DCh]
0x180049321  test    edi, edi
0x180049323  js      loc_1800494C8
0x180049329  mov     rcx, [rbx+98h]
0x180049330  test    rcx, rcx
0x180049333  jz      short loc_180049358
0x180049335  mov     rax, [rcx]
0x180049338  mov     r8d, [rbx+0DCh]
0x18004933f  mov     edx, [rbx+0D8h]
0x180049345  mov     rax, [rax+48h]
0x180049349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004934e  mov     edi, eax
0x180049350  test    eax, eax
0x180049352  js      loc_1800494C8
0x180049358  cmp     qword ptr [rbx+90h], 0
0x180049360  jz      short loc_1800492EA
0x180049362  mov     rcx, [r14]
0x180049365  cmp     dword ptr [rcx+14h], 1
0x180049369  jnz     loc_1800492EA
0x18004936f  lea     rcx, [rbp+arg_0]
0x180049373  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180049378  mov     ecx, 40h ; '@'; unsigned __int64
0x18004937d  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049382  test    rax, rax
0x180049385  jz      short loc_180049396
0x180049387  lea     rdx, [rbx+28h]
0x18004938b  mov     r8, r14
0x18004938e  mov     rcx, rax
0x180049391  call    ??0ChangeApplicationRecoverableError@@QEAA@AEBUIdDescription@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; ChangeApplicationRecoverableError::ChangeApplicationRecoverableError(IdDescription const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x180049396  mov     rdx, rax
0x180049399  lea     rcx, [rbp+arg_0]
0x18004939d  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x1800493a2  mov     edi, eax
0x1800493a4  test    eax, eax
0x1800493a6  js      short loc_1800493C1
0x1800493a8  mov     rcx, [rbx+90h]
0x1800493af  mov     rdx, [rbp+arg_0]
0x1800493b3  mov     rax, [rcx]
0x1800493b6  mov     rax, [rax+38h]
0x1800493ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493bf  mov     edi, eax
0x1800493c1  lea     rcx, [rbp+arg_0]
0x1800493c5  jmp     loc_1800494BB
0x1800493ca  xor     esi, esi
0x1800493cc  mov     [rbp+var_10], rcx
0x1800493d0  xor     r11d, r11d
0x1800493d3  mov     [rbp+var_8], 0
0x1800493db  test    edi, edi
0x1800493dd  js      loc_1800494C8
0x1800493e3  lea     rcx, [rbp+var_10]
0x1800493e7  call    ?GetNextElement@?$TableEnumerator@VSyncId@@HVDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@HVDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(void)
0x1800493ec  test    rax, rax
0x1800493ef  jz      short loc_180049415
0x1800493f1  mov     rax, [rax+10h]
0x1800493f5  cmp     dword ptr [rax+14h], 1
0x1800493f9  jnz     short loc_180049405
0x1800493fb  mov     esi, 1
0x180049400  test    r11d, r11d
0x180049403  jnz     short loc_18004941E
0x180049405  cmp     dword ptr [rax+14h], 2
0x180049409  jnz     short loc_1800493E3
0x18004940b  mov     r11d, 1
0x180049411  test    esi, esi
0x180049413  jz      short loc_1800493E3
0x180049415  test    esi, esi
0x180049417  jnz     short loc_18004941E
0x180049419  test    r11d, r11d
0x18004941c  jz      short loc_18004944F
0x18004941e  inc     dword ptr [rbx+0DCh]
0x180049424  mov     rcx, [rbx+98h]
0x18004942b  test    rcx, rcx
0x18004942e  jz      short loc_18004944F
0x180049430  mov     rax, [rcx]
0x180049433  mov     r8d, [rbx+0DCh]
0x18004943a  mov     edx, [rbx+0D8h]
0x180049440  mov     rax, [rax+48h]
0x180049444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049449  mov     edi, eax
0x18004944b  test    eax, eax
0x18004944d  js      short loc_1800494C8
0x18004944f  cmp     qword ptr [rbx+90h], 0
0x180049457  jz      loc_1800492EA
0x18004945d  test    esi, esi
0x18004945f  jz      loc_1800492EA
0x180049465  lea     rcx, [rbp+arg_8]
0x180049469  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004946e  mov     ecx, 40h ; '@'; unsigned __int64
0x180049473  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049478  test    rax, rax
0x18004947b  jz      short loc_18004948C
0x18004947d  lea     rdx, [rbx+28h]
0x180049481  mov     r8, r14
0x180049484  mov     rcx, rax
0x180049487  call    ??0ChangeApplicationRecoverableError@@QEAA@AEBUIdDescription@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; ChangeApplicationRecoverableError::ChangeApplicationRecoverableError(IdDescription const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x18004948c  mov     rdx, rax
0x18004948f  lea     rcx, [rbp+arg_8]
0x180049493  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x180049498  mov     edi, eax
0x18004949a  test    eax, eax
0x18004949c  js      short loc_1800494B7
0x18004949e  mov     rcx, [rbx+90h]
0x1800494a5  mov     rdx, [rbp+arg_8]
0x1800494a9  mov     rax, [rcx]
0x1800494ac  mov     rax, [rax+38h]
0x1800494b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494b5  mov     edi, eax
0x1800494b7  lea     rcx, [rbp+arg_8]
0x1800494bb  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800494c0  test    edi, edi
0x1800494c2  jns     loc_1800492EA
0x1800494c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800494cf  cmp     rcx, r13
0x1800494d2  jz      short loc_180049500
0x1800494d4  test    byte ptr [rcx+1Ch], 80h
0x1800494d8  jz      short loc_180049500
0x1800494da  cmp     byte ptr [rcx+19h], 5
0x1800494de  jb      short loc_180049500
0x1800494e0  mov     rcx, [rcx+10h]
0x1800494e4  lea     r9, aChangeapplicat_4; "ChangeApplicationServices::ReportFailed"...
0x1800494eb  mov     edx, 37h ; '7'
0x1800494f0  mov     [rsp+50h+var_30], edi
0x1800494f4  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800494fb  call    WPP_SF_sD
0x180049500  mov     rbx, [rsp+50h+arg_10]
0x180049508  mov     eax, edi
0x18004950a  add     rsp, 50h
0x18004950e  pop     r14
0x180049510  pop     r13
0x180049512  pop     rdi
0x180049513  pop     rsi
0x180049514  pop     rbp
0x180049515  retn
```
