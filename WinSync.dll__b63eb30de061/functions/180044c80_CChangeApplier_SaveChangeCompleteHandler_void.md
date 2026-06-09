# CChangeApplier::SaveChangeCompleteHandler(void)

- ea: `0x180044c80`
- end: `0x180044ef8`
- name: `?SaveChangeCompleteHandler@CChangeApplier@@AEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180035724`
- `0x18003ea50`
- `0x180040aa4`
- `0x180041f28`
- `0x180043ac0`
- `0x180044c80`
- `0x180046160`
- `0x180094010`

## string_xrefs

- `0x180044cb8`: `CChangeApplier::SaveChangeCompleteHandler`
- `0x180044ec7`: `CChangeApplier::SaveChangeCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::SaveChangeCompleteHandler(CChangeApplier *this)
{
  int v2; // ebx
  struct ISyncCallback *v3; // rdx
  __int64 v4; // rax
  int v5; // esi
  __int64 v6; // rcx
  int v7; // eax
  __int64 i; // rbp
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::SaveChangeCompleteHandler");
  }
  v2 = CChangeApplier::ChangeState((__int64)this, 12);
  if ( v2 >= 0 )
  {
    v3 = (struct ISyncCallback *)*((_QWORD *)this + 50);
    if ( !v3
      || !*(_DWORD *)(*((_QWORD *)this + 70) + 76LL)
      || (v2 = CChangeApplier::RecoverableErrorNotificationWrapper(
                 this,
                 v3,
                 *((struct CSyncChangeWrapper **)this + 68),
                 0),
          v2 >= 0) )
    {
      if ( (v4 = *((_QWORD *)this + 70), !*(_DWORD *)(v4 + 84)) && (v5 = 0, !*(_DWORD *)(v4 + 88))
        || (v2 = CChangeApplier::HandleConstraintConflict(this), v5 = 1, v2 >= 0) )
      {
        v15 = 0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 16LL))(*((_QWORD *)this + 64));
        v6 = *((_QWORD *)this + 70);
        *((_QWORD *)this + 64) = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v6 + 32LL))(
               v6,
               (char *)this + 512,
               &v15);
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v2 = v7;
          if ( v7 )
            break;
          if ( (unsigned int)i >= *((_DWORD *)this + 60) )
            goto LABEL_17;
          v9 = *(_QWORD *)(*((_QWORD *)this + 31) + 8 * i);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          *(_QWORD *)(*((_QWORD *)this + 31) + 8 * i) = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(*((_QWORD *)this + 70) + 24LL) + 32LL))(
                 *((_QWORD *)this + 70) + 24LL,
                 (unsigned int)i,
                 *((_QWORD *)this + 31) + 8 * i);
        }
        if ( v7 < 0 )
        {
          v12 = v15;
          goto LABEL_22;
        }
LABEL_17:
        v10 = v15;
        if ( !v15 )
          goto LABEL_24;
        v11 = *((_QWORD *)this + 67);
        if ( v11 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          v10 = v15;
        }
        v12 = 0;
        *((_QWORD *)this + 67) = v10;
        v15 = 0;
LABEL_22:
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_24:
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 70) + 16LL))(*((_QWORD *)this + 70));
        *((_QWORD *)this + 70) = 0;
        if ( v2 >= 0 )
        {
          if ( v5 )
          {
            *((_DWORD *)this + 98) = 1;
            v13 = CChangeApplier::ItemTransferComplete(this, 0, 1);
          }
          else
          {
            v13 = CChangeApplier::ProcessItemData(this);
          }
          v2 = v13;
        }
      }
    }
  }
  if ( v2 != -2147467260 )
  {
    if ( v2 >= 0 )
      goto LABEL_34;
LABEL_33:
    v2 = CChangeApplier::SetError(this, *((struct ISyncCallback **)this + 50), v2);
    goto LABEL_34;
  }
  if ( !*((_DWORD *)this + 170) )
    goto LABEL_33;
  v2 = 0;
LABEL_34:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      126,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::SaveChangeCompleteHandler",
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180044c80  mov     [rsp+arg_0], rbx
0x180044c85  mov     [rsp+arg_10], rbp
0x180044c8a  push    rsi
0x180044c8b  push    rdi
0x180044c8c  push    r12
0x180044c8e  sub     rsp, 30h
0x180044c92  mov     rdi, rcx
0x180044c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c9c  lea     r12, WPP_GLOBAL_Control
0x180044ca3  cmp     rcx, r12
0x180044ca6  jz      short loc_180044CD0
0x180044ca8  test    byte ptr [rcx+1Ch], 8
0x180044cac  jz      short loc_180044CD0
0x180044cae  cmp     byte ptr [rcx+19h], 5
0x180044cb2  jb      short loc_180044CD0
0x180044cb4  mov     rcx, [rcx+10h]
0x180044cb8  lea     r9, aCchangeapplier_92; "CChangeApplier::SaveChangeCompleteHandl"...
0x180044cbf  mov     edx, 7Dh ; '}'
0x180044cc4  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180044ccb  call    WPP_SF_s
0x180044cd0  mov     edx, 0Ch
0x180044cd5  mov     rcx, rdi
0x180044cd8  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x180044cdd  mov     ebx, eax
0x180044cdf  test    eax, eax
0x180044ce1  js      loc_180044E7E
0x180044ce7  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x180044cee  test    rdx, rdx
0x180044cf1  jz      short loc_180044D1C
0x180044cf3  mov     rax, [rdi+230h]
0x180044cfa  cmp     dword ptr [rax+4Ch], 0
0x180044cfe  jz      short loc_180044D1C
0x180044d00  mov     r8, [rdi+220h]; struct CSyncChangeWrapper *
0x180044d07  xor     r9d, r9d; int
0x180044d0a  mov     rcx, rdi; this
0x180044d0d  call    ?RecoverableErrorNotificationWrapper@CChangeApplier@@AEAAJPEAUISyncCallback@@PEAVCSyncChangeWrapper@@H@Z; CChangeApplier::RecoverableErrorNotificationWrapper(ISyncCallback *,CSyncChangeWrapper *,int)
0x180044d12  mov     ebx, eax
0x180044d14  test    eax, eax
0x180044d16  js      loc_180044E7E
0x180044d1c  mov     rax, [rdi+230h]
0x180044d23  cmp     dword ptr [rax+54h], 0
0x180044d27  jnz     short loc_180044D30
0x180044d29  xor     esi, esi
0x180044d2b  cmp     [rax+58h], esi
0x180044d2e  jz      short loc_180044D47
0x180044d30  mov     rcx, rdi; this
0x180044d33  call    ?HandleConstraintConflict@CChangeApplier@@AEAAJXZ; CChangeApplier::HandleConstraintConflict(void)
0x180044d38  mov     ebx, eax
0x180044d3a  mov     esi, 1
0x180044d3f  test    eax, eax
0x180044d41  js      loc_180044E7E
0x180044d47  mov     [rsp+48h+arg_8], 0
0x180044d50  lea     rbx, [rdi+200h]
0x180044d57  mov     rcx, [rbx]
0x180044d5a  mov     rax, [rcx]
0x180044d5d  mov     rax, [rax+10h]
0x180044d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d66  mov     rcx, [rdi+230h]
0x180044d6d  lea     r8, [rsp+48h+arg_8]
0x180044d72  mov     qword ptr [rbx], 0
0x180044d79  mov     rdx, rbx
0x180044d7c  mov     rax, [rcx]
0x180044d7f  mov     rax, [rax+20h]
0x180044d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d88  xor     ebp, ebp
0x180044d8a  jmp     short loc_180044DE0
0x180044d8c  cmp     ebp, [rdi+0F0h]
0x180044d92  jnb     short loc_180044DEA
0x180044d94  mov     rax, [rdi+0F8h]
0x180044d9b  mov     rcx, [rax+rbp*8]
0x180044d9f  mov     rax, [rcx]
0x180044da2  mov     rax, [rax+10h]
0x180044da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044dab  mov     rax, [rdi+0F8h]
0x180044db2  mov     qword ptr [rax+rbp*8], 0
0x180044dba  mov     rax, [rdi+0F8h]
0x180044dc1  mov     rcx, [rdi+230h]
0x180044dc8  add     rcx, 18h
0x180044dcc  lea     r8, [rax+rbp*8]
0x180044dd0  mov     rdx, [rcx]
0x180044dd3  mov     rax, [rdx+20h]
0x180044dd7  mov     edx, ebp
0x180044dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044dde  inc     ebp
0x180044de0  mov     ebx, eax
0x180044de2  test    eax, eax
0x180044de4  jz      short loc_180044D8C
0x180044de6  test    eax, eax
0x180044de8  js      short loc_180044E21
0x180044dea  mov     rax, [rsp+48h+arg_8]
0x180044def  test    rax, rax
0x180044df2  jz      short loc_180044E37
0x180044df4  mov     rcx, [rdi+218h]
0x180044dfb  test    rcx, rcx
0x180044dfe  jz      short loc_180044E11
0x180044e00  mov     rax, [rcx]
0x180044e03  mov     rax, [rax+10h]
0x180044e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e0c  mov     rax, [rsp+48h+arg_8]
0x180044e11  xor     ecx, ecx
0x180044e13  mov     [rdi+218h], rax
0x180044e1a  mov     [rsp+48h+arg_8], rcx
0x180044e1f  jmp     short loc_180044E26
0x180044e21  mov     rcx, [rsp+48h+arg_8]
0x180044e26  test    rcx, rcx
0x180044e29  jz      short loc_180044E37
0x180044e2b  mov     rax, [rcx]
0x180044e2e  mov     rax, [rax+10h]
0x180044e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e37  mov     rcx, [rdi+230h]
0x180044e3e  mov     rax, [rcx]
0x180044e41  mov     rax, [rax+10h]
0x180044e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e4a  mov     qword ptr [rdi+230h], 0
0x180044e55  test    ebx, ebx
0x180044e57  js      short loc_180044E7E
0x180044e59  mov     rcx, rdi; this
0x180044e5c  test    esi, esi
0x180044e5e  jz      short loc_180044E77
0x180044e60  xor     edx, edx; int
0x180044e62  mov     dword ptr [rdi+188h], 1
0x180044e6c  lea     r8d, [rdx+1]; int
0x180044e70  call    ?ItemTransferComplete@CChangeApplier@@AEAAJHH@Z; CChangeApplier::ItemTransferComplete(int,int)
0x180044e75  jmp     short loc_180044E7C
0x180044e77  call    ?ProcessItemData@CChangeApplier@@AEAAJXZ; CChangeApplier::ProcessItemData(void)
0x180044e7c  mov     ebx, eax
0x180044e7e  cmp     ebx, 80004004h
0x180044e84  jnz     short loc_180044E93
0x180044e86  cmp     dword ptr [rdi+2A8h], 0
0x180044e8d  jz      short loc_180044E97
0x180044e8f  xor     ebx, ebx
0x180044e91  jmp     short loc_180044EAB
0x180044e93  test    ebx, ebx
0x180044e95  jns     short loc_180044EAB
0x180044e97  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x180044e9e  mov     r8d, ebx; int
0x180044ea1  mov     rcx, rdi; this
0x180044ea4  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x180044ea9  mov     ebx, eax
0x180044eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180044eb2  cmp     rcx, r12
0x180044eb5  jz      short loc_180044EE3
0x180044eb7  test    byte ptr [rcx+1Ch], 8
0x180044ebb  jz      short loc_180044EE3
0x180044ebd  cmp     byte ptr [rcx+19h], 5
0x180044ec1  jb      short loc_180044EE3
0x180044ec3  mov     rcx, [rcx+10h]
0x180044ec7  lea     r9, aCchangeapplier_92; "CChangeApplier::SaveChangeCompleteHandl"...
0x180044ece  mov     edx, 7Eh ; '~'
0x180044ed3  mov     [rsp+48h+var_28], ebx
0x180044ed7  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180044ede  call    WPP_SF_sD
0x180044ee3  mov     rbp, [rsp+48h+arg_10]
0x180044ee8  mov     eax, ebx
0x180044eea  mov     rbx, [rsp+48h+arg_0]
0x180044eef  add     rsp, 30h
0x180044ef3  pop     r12
0x180044ef5  pop     rdi
0x180044ef6  pop     rsi
0x180044ef7  retn
```
