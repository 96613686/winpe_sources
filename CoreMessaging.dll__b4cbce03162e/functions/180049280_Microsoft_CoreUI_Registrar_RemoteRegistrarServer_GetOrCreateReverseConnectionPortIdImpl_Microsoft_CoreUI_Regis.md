# Microsoft::CoreUI::Registrar::RemoteRegistrarServer::GetOrCreateReverseConnectionPortIdImpl(Microsoft::CoreUI::Registrar::RegistrarThreadContext *,Microsoft::CoreUI::Registrar::RegistrarThreadContext *,Microsoft::CoreUI::RoutingInfo,System::Guid)

- ea: `0x180049280`
- end: `0x1800495c9`
- name: `?GetOrCreateReverseConnectionPortIdImpl@RemoteRegistrarServer@Registrar@CoreUI@Microsoft@@SA?AUGuid@System@@PEAVRegistrarThreadContext@234@0URoutingInfo@34@U56@@Z`
- size: `841`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18007a15c`
- `0x180082c50`

## callees

- `0x18000ec10`
- `0x180010ed0`
- `0x1800191b8`
- `0x180019c44`
- `0x18001ab10`
- `0x1800262e4`
- `0x180027c60`
- `0x180027e10`
- `0x180049280`
- `0x1800496d0`
- `0x180056a28`
- `0x18008ae1c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800493a0`
- `RPCRT4!UuidCreate` at `0x1800493a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::CoreUI::Registrar::RemoteRegistrarServer::GetOrCreateReverseConnectionPortIdImpl(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  System::Object **v8; // r14
  System::Object *v9; // rcx
  System::Object *v10; // rcx
  System::Object **v11; // rsi
  System::Object *v12; // rdi
  _QWORD *v13; // rax
  int v14; // r15d
  RPC_STATUS v15; // eax
  bool v16; // cl
  System::Object *v17; // rdi
  _QWORD *v18; // rax
  System::Object *v19; // rdi
  _QWORD *v20; // rax
  __int64 v22; // rcx
  unsigned int v23; // r11d
  unsigned __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // r14
  __int64 v27; // rax
  __int64 v28; // rcx
  UUID Uuid; // [rsp+20h] [rbp-71h] BYREF
  __int64 v30; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v31; // [rsp+38h] [rbp-59h]
  __int64 v32; // [rsp+40h] [rbp-51h]
  __int128 v33; // [rsp+48h] [rbp-49h]
  __int64 v34; // [rsp+58h] [rbp-39h]
  __int64 v35; // [rsp+60h] [rbp-31h]
  _QWORD v36[3]; // [rsp+70h] [rbp-21h] BYREF
  __int128 v37; // [rsp+88h] [rbp-9h]
  __int64 v38; // [rsp+98h] [rbp+7h]
  __int64 v39; // [rsp+A0h] [rbp+Fh]
  System::Object *v40; // [rsp+F0h] [rbp+5Fh] BYREF
  System::Object *v41; // [rsp+F8h] [rbp+67h]
  __int64 v42; // [rsp+100h] [rbp+6Fh]

  v42 = a3;
  *a1 = 0;
  a1[1] = 0;
  v8 = (System::Object **)(a2 + 120);
  if ( *(_QWORD *)(a2 + 120) )
  {
    v11 = (System::Object **)(a2 + 128);
  }
  else
  {
    CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>>(&v40);
    v9 = (System::Object *)*((_QWORD *)v40 + 3);
    *((_QWORD *)v40 + 3) = &`System::Array::Empty<CFlat::SmartPtr<System::Object>>'::`2'::value;
    if ( v9 )
      System::Object::Release$(v9);
    CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(v8, &v40);
    if ( v40 )
      System::Object::ReleaseNotFrozen$(v40);
    CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>>(&v40);
    v10 = (System::Object *)*((_QWORD *)v40 + 3);
    *((_QWORD *)v40 + 3) = &`System::Array::Empty<CFlat::SmartPtr<System::Object>>'::`2'::value;
    if ( v10 )
      System::Object::Release$(v10);
    v11 = (System::Object **)(a2 + 128);
    CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(a2 + 128, &v40);
    if ( v40 )
      System::Object::ReleaseNotFrozen$(v40);
  }
  v12 = *v11;
  v41 = v12;
  if ( v12 )
    ++*((_DWORD *)v12 + 4);
  v13 = (_QWORD *)CFlat::Cast::Unchecked<CFlat::SmartPtr<System::Object>,System::Guid &>(&v40, a5);
  v14 = System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::IndexOf(v12, *v13);
  if ( v40 )
    System::Object::Release$(v40);
  if ( v12 )
    System::Object::ReleaseNotFrozen$(v12);
  if ( v14 >= 0 )
  {
    v22 = *(_QWORD *)System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::get_Item(
                       *v8,
                       &v40,
                       (unsigned int)v14);
    if ( !v22 )
      CFlat::Abandonment::Fail(0);
    if ( *(const char16_t **)(v22 + 8) != &word_1800D82E0 )
      CFlat::Abandonment::Fail((const char16_t *)v22);
    *(_OWORD *)a1 = *(_OWORD *)(v22 + 24);
    if ( v40 )
      System::Object::Release$(v40);
  }
  else
  {
    *(_QWORD *)&Uuid.Data1 = 0;
    *(_QWORD *)Uuid.Data4 = 0;
    v15 = UuidCreate(&Uuid);
    if ( !v15 || (v16 = 0, v15 == 1824) )
      v16 = 1;
    CFlat::Contracts::Contract::Requires(v16);
    *(UUID *)a1 = Uuid;
    v17 = *v8;
    if ( *v8 )
      ++*((_DWORD *)v17 + 4);
    v18 = (_QWORD *)CFlat::Cast::Unchecked<CFlat::SmartPtr<System::Object>,System::Guid &>(&v40, a1);
    System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::Add(v17, *v18);
    if ( v40 )
      System::Object::Release$(v40);
    if ( v17 )
      System::Object::ReleaseNotFrozen$(v17);
    v19 = *v11;
    if ( *v11 )
      ++*((_DWORD *)v19 + 4);
    v20 = (_QWORD *)CFlat::Cast::Unchecked<CFlat::SmartPtr<System::Object>,System::Guid &>(&v40, a5);
    System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::Add(v19, *v20);
    if ( v40 )
      System::Object::Release$(v40);
    if ( v19 )
      System::Object::ReleaseNotFrozen$(v19);
    if ( v42 )
    {
      v23 = *(_DWORD *)(a4 + 4);
      v24 = *(_QWORD *)(a4 + 8);
      v25 = *(_QWORD *)(a4 + 16);
      v26 = *(_QWORD *)(a4 + 24);
      v27 = *(_QWORD *)(a4 + 32);
      LODWORD(v30) = *(_DWORD *)a4;
      HIDWORD(v30) = v23;
      v31 = v24;
      v32 = v25;
      if ( __PAIR128__(v24, __PAIR64__(v23, v30)) != Microsoft::CoreUI::RoutingInfo::Invalid
        || v25 != (_QWORD)xmmword_1801065F8 )
      {
        goto LABEL_44;
      }
      v28 = v26 - *((_QWORD *)&xmmword_1801065F8 + 1);
      if ( v26 == *((_QWORD *)&xmmword_1801065F8 + 1) )
        v28 = v27 - qword_180106608;
      if ( v28 )
      {
LABEL_44:
        v37 = 0;
        v38 = 0;
        v39 = 0;
        v30 = 0;
        v31 = 0;
        v32 = 0;
        v33 = 0u;
        v34 = 0;
        v35 = 0;
        v36[0] = *(_QWORD *)a4;
        v36[1] = v24;
        v36[2] = v25;
        *(_QWORD *)&v37 = v26;
        *((_QWORD *)&v37 + 1) = v27;
        Microsoft::CoreUI::Registrar::RemoteRegistrarServer::ReserveGroupsForNewConnection(v36, a2, v42, &v30);
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180049280  mov     [rsp-8+arg_18], rbx
0x180049285  mov     [rsp-8+arg_10], r8
0x18004928a  push    rbp
0x18004928b  push    rsi
0x18004928c  push    rdi
0x18004928d  push    r12
0x18004928f  push    r13
0x180049291  push    r14
0x180049293  push    r15
0x180049295  lea     rbp, [rsp-1Fh]
0x18004929a  sub     rsp, 0B0h
0x1800492a1  mov     r12, r9
0x1800492a4  mov     r13, rdx
0x1800492a7  mov     rbx, rcx
0x1800492aa  xor     r15d, r15d
0x1800492ad  mov     [rcx], r15
0x1800492b0  mov     [rcx+8], r15
0x1800492b4  lea     r14, [rdx+78h]
0x1800492b8  cmp     [r14], r15
0x1800492bb  jnz     loc_18004945F
0x1800492c1  lea     rcx, [rbp+4Fh+arg_0]
0x1800492c5  call    ??$Allocate@V?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>>(void)
0x1800492ca  mov     rax, [rbp+4Fh+arg_0]
0x1800492ce  mov     rcx, [rax+18h]; this
0x1800492d2  lea     rdi, ?value@?1???$Empty@V?$SmartPtr@VObject@System@@@CFlat@@@Array@System@@SAPEAV?$Array$2@V?$SmartPtr@VObject@System@@@CFlat@@$00@CFlat@@XZ@4V34@B; CFlat::Array$2<CFlat::SmartPtr<System::Object>,1> const `System::Array::Empty<CFlat::SmartPtr<System::Object>>(void)'::`2'::value
0x1800492d9  mov     [rax+18h], rdi
0x1800492dd  test    rcx, rcx
0x1800492e0  jz      short loc_1800492E7
0x1800492e2  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800492e7  lea     rdx, [rbp+4Fh+arg_0]
0x1800492eb  mov     rcx, r14
0x1800492ee  call    ??4?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>> &&)
0x1800492f3  mov     rcx, [rbp+4Fh+arg_0]; this
0x1800492f7  test    rcx, rcx
0x1800492fa  jz      short loc_180049301
0x1800492fc  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180049301  lea     rcx, [rbp+4Fh+arg_0]
0x180049305  call    ??$Allocate@V?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>>(void)
0x18004930a  mov     rax, [rbp+4Fh+arg_0]
0x18004930e  mov     rcx, [rax+18h]; this
0x180049312  mov     [rax+18h], rdi
0x180049316  test    rcx, rcx
0x180049319  jz      short loc_180049320
0x18004931b  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180049320  lea     rsi, [r13+80h]
0x180049327  lea     rdx, [rbp+4Fh+arg_0]
0x18004932b  mov     rcx, rsi
0x18004932e  call    ??4?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>> &&)
0x180049333  mov     rcx, [rbp+4Fh+arg_0]; this
0x180049337  test    rcx, rcx
0x18004933a  jz      short loc_180049341
0x18004933c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180049341  mov     rdi, [rsi]
0x180049344  mov     [rbp+4Fh+arg_8], rdi
0x180049348  test    rdi, rdi
0x18004934b  jz      short loc_180049350
0x18004934d  inc     dword ptr [rdi+10h]
0x180049350  mov     rdx, [rbp+4Fh+arg_20]
0x180049354  lea     rcx, [rbp+4Fh+arg_0]
0x180049358  call    ??$Unchecked@V?$SmartPtr@VObject@System@@@CFlat@@AEAUGuid@System@@@Cast@CFlat@@SA?A_PAEAUGuid@System@@@Z
0x18004935d  nop
0x18004935e  mov     rdx, [rax]
0x180049361  mov     rcx, rdi
0x180049364  call    ?IndexOf@?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@QEAAHPEAVObject@4@@Z; System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::IndexOf(System::Object *)
0x180049369  mov     r15d, eax
0x18004936c  mov     rcx, [rbp+4Fh+arg_0]; this
0x180049370  test    rcx, rcx
0x180049373  jz      short loc_18004937B
0x180049375  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18004937a  nop
0x18004937b  test    rdi, rdi
0x18004937e  jz      short loc_180049388
0x180049380  mov     rcx, rdi; this
0x180049383  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180049388  test    r15d, r15d
0x18004938b  jns     loc_18004946B
0x180049391  xor     r15d, r15d
0x180049394  mov     qword ptr [rbp+4Fh+Uuid.Data1], r15
0x180049398  mov     qword ptr [rbp+4Fh+Uuid.Data4], r15
0x18004939c  lea     rcx, [rbp+4Fh+Uuid]; Uuid
0x1800493a0  call    cs:__imp_UuidCreate
0x1800493a6  test    eax, eax
0x1800493a8  jnz     loc_1800495B6
0x1800493ae  mov     cl, 1; bool
0x1800493b0  call    ?Requires@Contract@Contracts@CFlat@@SAX_N@Z; CFlat::Contracts::Contract::Requires(bool)
0x1800493b5  movups  xmm0, xmmword ptr [rbp+4Fh+Uuid.Data1]
0x1800493b9  movdqu  xmmword ptr [rbx], xmm0
0x1800493bd  mov     rdi, [r14]
0x1800493c0  test    rdi, rdi
0x1800493c3  jz      short loc_1800493C8
0x1800493c5  inc     dword ptr [rdi+10h]
0x1800493c8  mov     rdx, rbx
0x1800493cb  lea     rcx, [rbp+4Fh+arg_0]
0x1800493cf  call    ??$Unchecked@V?$SmartPtr@VObject@System@@@CFlat@@AEAUGuid@System@@@Cast@CFlat@@SA?A_PAEAUGuid@System@@@Z
0x1800493d4  mov     rdx, [rax]
0x1800493d7  mov     rcx, rdi
0x1800493da  call    ?Add@?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@QEAAXPEAVObject@4@@Z; System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::Add(System::Object *)
0x1800493df  mov     rcx, [rbp+4Fh+arg_0]; this
0x1800493e3  test    rcx, rcx
0x1800493e6  jz      short loc_1800493ED
0x1800493e8  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800493ed  test    rdi, rdi
0x1800493f0  jz      short loc_1800493FA
0x1800493f2  mov     rcx, rdi; this
0x1800493f5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800493fa  mov     rdi, [rsi]
0x1800493fd  test    rdi, rdi
0x180049400  jz      short loc_180049405
0x180049402  inc     dword ptr [rdi+10h]
0x180049405  mov     rdx, [rbp+4Fh+arg_20]
0x180049409  lea     rcx, [rbp+4Fh+arg_0]
0x18004940d  call    ??$Unchecked@V?$SmartPtr@VObject@System@@@CFlat@@AEAUGuid@System@@@Cast@CFlat@@SA?A_PAEAUGuid@System@@@Z
0x180049412  mov     rdx, [rax]
0x180049415  mov     rcx, rdi
0x180049418  call    ?Add@?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@QEAAXPEAVObject@4@@Z; System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::Add(System::Object *)
0x18004941d  mov     rcx, [rbp+4Fh+arg_0]; this
0x180049421  test    rcx, rcx
0x180049424  jz      short loc_18004942B
0x180049426  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18004942b  test    rdi, rdi
0x18004942e  jz      short loc_180049438
0x180049430  mov     rcx, rdi; this
0x180049433  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180049438  mov     r15, [rbp+4Fh+arg_10]
0x18004943c  test    r15, r15
0x18004943f  jnz     short loc_1800494B1
0x180049441  mov     rax, rbx
0x180049444  mov     rbx, [rsp+0E0h+arg_18]
0x18004944c  add     rsp, 0B0h
0x180049453  pop     r15
0x180049455  pop     r14
0x180049457  pop     r13
0x180049459  pop     r12
0x18004945b  pop     rdi
0x18004945c  pop     rsi
0x18004945d  pop     rbp
0x18004945e  retn
0x18004945f  lea     rsi, [rdx+80h]
0x180049466  jmp     loc_180049341
0x18004946b  mov     r8d, r15d
0x18004946e  lea     rdx, [rbp+4Fh+arg_0]
0x180049472  mov     rcx, [r14]
0x180049475  call    ?get_Item@?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@QEAA?AV?$SmartPtr@VObject@System@@@CFlat@@H@Z; System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>::get_Item(int)
0x18004947a  mov     rcx, [rax]; char16_t *
0x18004947d  test    rcx, rcx
0x180049480  jz      loc_1800495B0
0x180049486  lea     rax, word_1800D82E0
0x18004948d  cmp     [rcx+8], rax
0x180049491  jz      short loc_180049499
0x180049493  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180049499  movups  xmm0, xmmword ptr [rcx+18h]
0x18004949d  movdqu  xmmword ptr [rbx], xmm0
0x1800494a1  mov     rcx, [rbp+4Fh+arg_0]; this
0x1800494a5  test    rcx, rcx
0x1800494a8  jz      short loc_180049441
0x1800494aa  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800494af  jmp     short loc_180049441
0x1800494b1  mov     edx, dword ptr cs:?Invalid@RoutingInfo@CoreUI@Microsoft@@2U123@A; Microsoft::CoreUI::RoutingInfo Microsoft::CoreUI::RoutingInfo::Invalid
0x1800494b7  mov     r10d, dword ptr cs:?Invalid@RoutingInfo@CoreUI@Microsoft@@2U123@A+4; Microsoft::CoreUI::RoutingInfo Microsoft::CoreUI::RoutingInfo::Invalid
0x1800494be  mov     rdi, qword ptr cs:?Invalid@RoutingInfo@CoreUI@Microsoft@@2U123@A+8; Microsoft::CoreUI::RoutingInfo Microsoft::CoreUI::RoutingInfo::Invalid
0x1800494c5  mov     rsi, qword ptr cs:xmmword_1801065F8
0x1800494cc  mov     ecx, [r12]
0x1800494d0  mov     r11d, [r12+4]
0x1800494d5  mov     r9, [r12+8]
0x1800494da  mov     r8, [r12+10h]
0x1800494df  mov     r14, [r12+18h]
0x1800494e4  mov     rax, [r12+20h]
0x1800494e9  mov     dword ptr [rbp+4Fh+var_B0], edx
0x1800494ec  mov     dword ptr [rbp+4Fh+var_B0+4], r10d
0x1800494f0  mov     [rbp+4Fh+var_A8], rdi
0x1800494f4  mov     [rbp+4Fh+var_A0], rsi
0x1800494f8  mov     dword ptr [rbp+4Fh+var_B0], ecx
0x1800494fb  mov     dword ptr [rbp+4Fh+var_B0+4], r11d
0x1800494ff  mov     [rbp+4Fh+var_A8], r9
0x180049503  mov     [rbp+4Fh+var_A0], r8
0x180049507  cmp     r9, rdi
0x18004950a  jnz     loc_1800495AC
0x180049510  cmp     ecx, edx
0x180049512  jnz     loc_1800495AC
0x180049518  cmp     r11d, r10d
0x18004951b  jnz     loc_1800495AC
0x180049521  cmp     r8, rsi
0x180049524  jnz     loc_1800495AC
0x18004952a  mov     rcx, r14
0x18004952d  sub     rcx, qword ptr cs:xmmword_1801065F8+8
0x180049534  jnz     short loc_180049540
0x180049536  mov     rcx, rax
0x180049539  sub     rcx, cs:qword_180106608
0x180049540  xor     edx, edx
0x180049542  test    rcx, rcx
0x180049545  jz      loc_180049441
0x18004954b  xor     ecx, ecx
0x18004954d  xorps   xmm0, xmm0
0x180049550  movups  [rbp+4Fh+var_58], xmm0
0x180049554  mov     [rbp+4Fh+var_48], rcx
0x180049558  mov     [rbp+4Fh+var_40], rdx
0x18004955c  mov     [rbp+4Fh+var_B0], rcx
0x180049560  mov     [rbp+4Fh+var_A8], rdx
0x180049564  mov     [rbp+4Fh+var_A0], rdx
0x180049568  movups  [rbp+4Fh+var_98], xmm0
0x18004956c  mov     qword ptr [rbp+4Fh+var_98], rcx
0x180049570  mov     qword ptr [rbp+4Fh+var_98+8], rcx
0x180049574  mov     [rbp+4Fh+var_88], rcx
0x180049578  mov     [rbp+4Fh+var_80], rdx
0x18004957c  mov     rcx, [r12]
0x180049580  mov     [rbp+4Fh+var_70], rcx
0x180049584  mov     [rbp+4Fh+var_68], r9
0x180049588  mov     [rbp+4Fh+var_60], r8
0x18004958c  mov     qword ptr [rbp+4Fh+var_58], r14
0x180049590  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x180049594  lea     r9, [rbp+4Fh+var_B0]
0x180049598  mov     r8, r15
0x18004959b  mov     rdx, r13
0x18004959e  lea     rcx, [rbp+4Fh+var_70]
0x1800495a2  call    ?ReserveGroupsForNewConnection@RemoteRegistrarServer@Registrar@CoreUI@Microsoft@@CA?AW4MessagingResults@Messaging@34@U?$Ref@UPendingConnection@Registrar@CoreUI@Microsoft@@@CFlat@@PEAVRegistrarThreadContext@234@10@Z; Microsoft::CoreUI::Registrar::RemoteRegistrarServer::ReserveGroupsForNewConnection(CFlat::Ref<Microsoft::CoreUI::Registrar::PendingConnection>,Microsoft::CoreUI::Registrar::RegistrarThreadContext *,Microsoft::CoreUI::Registrar::RegistrarThreadContext *,CFlat::Ref<Microsoft::CoreUI::Registrar::PendingConnection>)
0x1800495a7  jmp     loc_180049441
0x1800495ac  xor     edx, edx
0x1800495ae  jmp     short loc_18004954B
0x1800495b0  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800495b6  cmp     eax, 720h
0x1800495bb  mov     cl, r15b
0x1800495be  jnz     loc_1800493B0
0x1800495c4  jmp     loc_1800493AE
```
