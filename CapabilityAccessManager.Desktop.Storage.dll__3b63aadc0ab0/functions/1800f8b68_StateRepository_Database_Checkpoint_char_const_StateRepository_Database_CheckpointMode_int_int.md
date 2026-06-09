# StateRepository::Database::Checkpoint(char const *,StateRepository::Database::CheckpointMode,int *,int *)

- ea: `0x1800f8b68`
- end: `0x1800f8e8f`
- name: `?Checkpoint@Database@StateRepository@@QEAAJPEBDW4CheckpointMode@12@PEAH2@Z`
- size: `807`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x1800edc80`

## callees

- `0x18000163c`
- `0x180003060`
- `0x18000ed50`
- `0x180016f30`
- `0x1800eabf4`
- `0x1800f8388`
- `0x1800f8448`
- `0x1800f85a8`
- `0x1800f8b68`
- `0x1800f91ec`
- `0x1800fb7b4`
- `0x1800fc0cc`
- `0x1800fc228`
- `0x18010680c`

## string_xrefs

- `0x1800f8bc0`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f8c41`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f8cdc`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Checkpoint(__int64 *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // eax
  int v5; // edi
  int v6; // ecx
  __int64 v7; // rbx
  __int64 v8; // rcx
  const char *v9; // rax
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-E0h]
  char *v13; // [rsp+28h] [rbp-D8h]
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+5Ch] [rbp-A4h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  __int64 v25; // [rsp+A0h] [rbp-60h]
  int v26; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+ACh] [rbp-54h]
  int v28; // [rsp+B4h] [rbp-4Ch]
  _QWORD v29[42]; // [rsp+C0h] [rbp-40h] BYREF
  char v30[32]; // [rsp+210h] [rbp+110h] BYREF
  const char *v31; // [rsp+230h] [rbp+130h]
  int v32; // [rsp+238h] [rbp+138h]
  int v33; // [rsp+23Ch] [rbp+13Ch]
  int *v34; // [rsp+240h] [rbp+140h]
  __int64 v35; // [rsp+248h] [rbp+148h]
  int *v36; // [rsp+250h] [rbp+150h]
  __int64 v37; // [rsp+258h] [rbp+158h]
  int *v38; // [rsp+260h] [rbp+160h]
  __int64 v39; // [rsp+268h] [rbp+168h]
  __int64 *v40; // [rsp+270h] [rbp+170h]
  __int64 v41; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v29);
  v29[0] = &StateRepository::Logging::Database::Checkpoint::`vftable';
  StateRepository::Logging::Database::Checkpoint::StartActivity((StateRepository::Logging::Database::Checkpoint *)v29);
  if ( *a1 )
  {
    v22 = 0;
    v24 = 0;
    v26 = 0;
    v15 = -2;
    v14 = -2;
    v27 = 0;
    v28 = 0;
    v20 = 0;
    v21 = 0;
    v23 = 0;
    v25 = 0;
    v3 = StateRepository::ResourcePriority::AutoPriority::SetPriorities(&v20);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v4 = sqlite3_wal_checkpoint_v2(*a1, 0, 3, (unsigned int)&v15, (__int64)&v14);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x87AF0000;
      StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)&v20);
      v5 = 1;
      if ( v2 + 2018574331 > 1 && v2 + 2018574075 > 1 )
      {
        if ( v2 + 2140733433 > 8 || (v6 = 495, !_bittest(&v6, v2 + 2140733433)) )
        {
          if ( (v2 & 0x80000000) == 0 )
          {
            v7 = qword_1801402E8;
            if ( *(_DWORD *)qword_1801402E8 > 5u
              && (*(_QWORD *)(qword_1801402E8 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1801402E8 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1801402E8 + 24) )
            {
              v8 = *a1;
              v16 = v14;
              v17 = v15;
              v19 = 0x1000000;
              v18 = 3;
              if ( v8 )
                v9 = (const char *)sqlite3_db_filename(v8, 0);
              else
                v9 = 0;
              v41 = 8;
              v40 = &v19;
              v38 = &v16;
              v36 = &v17;
              v34 = &v18;
              v39 = 4;
              v37 = 4;
              v35 = 4;
              if ( v9 )
              {
                v10 = -1;
                do
                  ++v10;
                while ( v9[v10] );
                v5 = v10 + 1;
              }
              else
              {
                v9 = byte_180122168;
              }
              v31 = v9;
              v32 = v5;
              v33 = 0;
              tlgWriteTransfer_EventWriteTransfer(v7, &dword_180129C24, 0, 0, 7, v30);
            }
            wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
            v2 = 0;
          }
          else
          {
            LODWORD(v13) = 3;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x36B,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
              (const char *)v2,
              (int)"sqlite3_wal_checkpoint_v2(): Mode:%d EffectiveMode:%d Size:%d Pages:%d",
              v13,
              3,
              v15,
              v14);
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v3,
        v12);
      StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)&v20);
    }
  }
  else
  {
    v2 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      v12);
  }
  v29[0] = &StateRepository::Logging::Database::Checkpoint::`vftable';
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v29);
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v29);
  return v2;
}

```

## disassembly

```asm
0x1800f8b68  push    rbp
0x1800f8b6a  push    rbx
0x1800f8b6b  push    rsi
0x1800f8b6c  push    rdi
0x1800f8b6d  push    r12
0x1800f8b6f  push    r14
0x1800f8b71  lea     rbp, [rsp-198h]
0x1800f8b79  sub     rsp, 298h
0x1800f8b80  mov     rax, cs:__security_cookie
0x1800f8b87  xor     rax, rsp
0x1800f8b8a  mov     [rbp+1C0h+var_40], rax
0x1800f8b91  mov     rsi, rcx
0x1800f8b94  lea     rcx, [rbp+1C0h+var_200]; struct wil::details::IFailureCallback *
0x1800f8b98  call    ??0?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800f8b9d  lea     r12, ??_7Checkpoint@Database@Logging@StateRepository@@6B@; const StateRepository::Logging::Database::Checkpoint::`vftable'
0x1800f8ba4  lea     rcx, [rbp+1C0h+var_200]; this
0x1800f8ba8  mov     [rbp+1C0h+var_200], r12
0x1800f8bac  call    ?StartActivity@Checkpoint@Database@Logging@StateRepository@@QEAAXXZ; StateRepository::Logging::Database::Checkpoint::StartActivity(void)
0x1800f8bb1  xor     r14d, r14d
0x1800f8bb4  cmp     [rsi], r14
0x1800f8bb7  jnz     short loc_1800F8BDE
0x1800f8bb9  mov     rcx, [rbp+1C8h]; this
0x1800f8bc0  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8bc7  mov     ebx, 8007139Fh
0x1800f8bcc  mov     edx, 347h; void *
0x1800f8bd1  mov     r9d, ebx; char *
0x1800f8bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8bd9  jmp     loc_1800F8E58
0x1800f8bde  mov     eax, 0FFFFFFFEh
0x1800f8be3  mov     [rbp+1C0h+var_238], r14
0x1800f8be7  mov     [rbp+1C0h+var_228], r14
0x1800f8beb  lea     rcx, [rsp+2C0h+var_250]
0x1800f8bf0  mov     [rbp+1C0h+var_218], r14
0x1800f8bf4  xorps   xmm0, xmm0
0x1800f8bf7  mov     qword ptr [rbp+1C0h+var_210], r14
0x1800f8bfb  mov     [rsp+2C0h+var_26C], eax
0x1800f8bff  mov     [rsp+2C0h+var_270], eax
0x1800f8c03  xor     eax, eax
0x1800f8c05  mov     dword ptr [rbp+1C0h+var_238+4], eax
0x1800f8c08  mov     dword ptr [rbp+1C0h+var_228+4], eax
0x1800f8c0b  mov     [rbp+1C0h+var_218+4], rax
0x1800f8c0f  mov     [rbp+1C0h+var_210+4], eax
0x1800f8c12  movups  [rsp+2C0h+var_250], xmm0
0x1800f8c17  mov     [rbp+1C0h+var_240], r14
0x1800f8c1b  mov     byte ptr [rbp+1C0h+var_238], r14b
0x1800f8c1f  mov     [rbp+1C0h+var_230], r14
0x1800f8c23  mov     byte ptr [rbp+1C0h+var_228], r14b
0x1800f8c27  mov     [rbp+1C0h+var_220], r14
0x1800f8c2b  mov     byte ptr [rbp+1C0h+var_218], r14b
0x1800f8c2f  call    ?SetPriorities@AutoPriority@ResourcePriority@StateRepository@@QEAAJJKW4_IO_PRIORITY_HINT@@_N1PEA_N@Z; StateRepository::ResourcePriority::AutoPriority::SetPriorities(long,ulong,_IO_PRIORITY_HINT,bool,bool,bool *)
0x1800f8c34  mov     ebx, eax
0x1800f8c36  test    eax, eax
0x1800f8c38  jns     short loc_1800F8C64
0x1800f8c3a  mov     rcx, [rbp+1C8h]; this
0x1800f8c41  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8c48  mov     r9d, eax; char *
0x1800f8c4b  mov     edx, 35Ah; void *
0x1800f8c50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8c55  lea     rcx, [rsp+2C0h+var_250]; this
0x1800f8c5a  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x1800f8c5f  jmp     loc_1800F8E58
0x1800f8c64  mov     rcx, [rsi]
0x1800f8c67  lea     rax, [rsp+2C0h+var_270]
0x1800f8c6c  xor     edx, edx
0x1800f8c6e  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x1800f8c73  lea     r9, [rsp+2C0h+var_26C]
0x1800f8c78  lea     r8d, [rdx+3]
0x1800f8c7c  call    sqlite3_wal_checkpoint_v2
0x1800f8c81  mov     ebx, eax
0x1800f8c83  test    eax, eax
0x1800f8c85  jle     short loc_1800F8C90
0x1800f8c87  movzx   ebx, ax
0x1800f8c8a  or      ebx, 87AF0000h
0x1800f8c90  lea     rcx, [rsp+2C0h+var_250]; this
0x1800f8c95  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x1800f8c9a  lea     eax, [rbx+7850FFFBh]
0x1800f8ca0  mov     edi, 1
0x1800f8ca5  cmp     eax, edi
0x1800f8ca7  jbe     loc_1800F8E58
0x1800f8cad  lea     eax, [rbx+7850FEFBh]
0x1800f8cb3  cmp     eax, edi
0x1800f8cb5  jbe     loc_1800F8E58
0x1800f8cbb  lea     eax, [rbx+7F98FFF9h]
0x1800f8cc1  cmp     eax, 8
0x1800f8cc4  ja      short loc_1800F8CD4
0x1800f8cc6  mov     ecx, 1EFh
0x1800f8ccb  bt      ecx, eax
0x1800f8cce  jb      loc_1800F8E58
0x1800f8cd4  test    ebx, ebx
0x1800f8cd6  jns     short loc_1800F8D24
0x1800f8cd8  mov     eax, [rsp+2C0h+var_270]
0x1800f8cdc  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8ce3  mov     rcx, [rbp+1C8h]; this
0x1800f8cea  mov     r9d, ebx; char *
0x1800f8ced  mov     [rsp+2C0h+var_280], eax
0x1800f8cf1  mov     edx, 36Bh; void *
0x1800f8cf6  mov     eax, [rsp+2C0h+var_26C]
0x1800f8cfa  mov     [rsp+2C0h+var_288], eax
0x1800f8cfe  lea     rax, aSqlite3WalChec; "sqlite3_wal_checkpoint_v2(): Mode:%d Ef"...
0x1800f8d05  mov     [rsp+2C0h+var_290], 3
0x1800f8d0d  mov     dword ptr [rsp+2C0h+var_298], 3; char *
0x1800f8d15  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x1800f8d1a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f8d1f  jmp     loc_1800F8E58
0x1800f8d24  mov     rbx, cs:qword_1801402E8
0x1800f8d2b  mov     eax, [rbx]
0x1800f8d2d  cmp     eax, 5
0x1800f8d30  jbe     loc_1800F8E4C
0x1800f8d36  mov     rcx, [rbx+18h]
0x1800f8d3a  mov     rdx, 200000000000h
0x1800f8d44  mov     rax, [rbx+10h]
0x1800f8d48  test    rdx, rax
0x1800f8d4b  jz      loc_1800F8E4C
0x1800f8d51  mov     rax, rcx
0x1800f8d54  and     rax, rdx
0x1800f8d57  cmp     rax, rcx
0x1800f8d5a  jnz     loc_1800F8E4C
0x1800f8d60  mov     eax, [rsp+2C0h+var_270]
0x1800f8d64  mov     rcx, [rsi]
0x1800f8d67  mov     [rsp+2C0h+var_268], eax
0x1800f8d6b  mov     eax, [rsp+2C0h+var_26C]
0x1800f8d6f  mov     [rsp+2C0h+var_264], eax
0x1800f8d73  mov     [rsp+2C0h+var_258], 1000000h
0x1800f8d7c  mov     [rsp+2C0h+var_260], 3
0x1800f8d84  test    rcx, rcx
0x1800f8d87  jz      short loc_1800F8D92
0x1800f8d89  xor     edx, edx
0x1800f8d8b  call    sqlite3_db_filename
0x1800f8d90  jmp     short loc_1800F8D95
0x1800f8d92  mov     rax, r14
0x1800f8d95  mov     [rbp+1C0h+var_48], 8
0x1800f8da0  lea     rcx, [rsp+2C0h+var_258]
0x1800f8da5  mov     [rbp+1C0h+var_50], rcx
0x1800f8dac  lea     rcx, [rsp+2C0h+var_268]
0x1800f8db1  mov     [rbp+1C0h+var_60], rcx
0x1800f8db8  lea     rcx, [rsp+2C0h+var_264]
0x1800f8dbd  mov     [rbp+1C0h+var_70], rcx
0x1800f8dc4  lea     rcx, [rsp+2C0h+var_260]
0x1800f8dc9  mov     [rbp+1C0h+var_80], rcx
0x1800f8dd0  mov     [rbp+1C0h+var_58], 4
0x1800f8ddb  mov     [rbp+1C0h+var_68], 4
0x1800f8de6  mov     [rbp+1C0h+var_78], 4
0x1800f8df1  test    rax, rax
0x1800f8df4  jz      short loc_1800F8E08
0x1800f8df6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f8dfa  inc     rcx
0x1800f8dfd  cmp     [rax+rcx], r14b
0x1800f8e01  jnz     short loc_1800F8DFA
0x1800f8e03  lea     edi, [rcx+1]
0x1800f8e06  jmp     short loc_1800F8E0F
0x1800f8e08  lea     rax, byte_180122168
0x1800f8e0f  mov     [rbp+1C0h+var_90], rax
0x1800f8e16  lea     rdx, dword_180129C24
0x1800f8e1d  lea     rax, [rbp+1C0h+var_B0]
0x1800f8e24  mov     [rbp+1C0h+var_88], edi
0x1800f8e2a  mov     [rsp+2C0h+var_298], rax
0x1800f8e2f  xor     r9d, r9d
0x1800f8e32  xor     r8d, r8d
0x1800f8e35  mov     [rsp+2C0h+var_2A0], 7
0x1800f8e3d  mov     rcx, rbx
0x1800f8e40  mov     [rbp+1C0h+var_84], r14d
0x1800f8e47  call    _tlgWriteTransfer_EventWriteTransfer
0x1800f8e4c  lea     rcx, [rbp+1C0h+var_200]
0x1800f8e50  call    ?Stop@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800f8e55  mov     ebx, r14d
0x1800f8e58  lea     rcx, [rbp+1C0h+var_200]
0x1800f8e5c  mov     [rbp+1C0h+var_200], r12
0x1800f8e60  call    ?Destroy@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800f8e65  lea     rcx, [rbp+1C0h+var_200]
0x1800f8e69  call    ??1?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800f8e6e  mov     eax, ebx
0x1800f8e70  mov     rcx, [rbp+1C0h+var_40]
0x1800f8e77  xor     rcx, rsp; StackCookie
0x1800f8e7a  call    __security_check_cookie
0x1800f8e7f  add     rsp, 298h
0x1800f8e86  pop     r14
0x1800f8e88  pop     r12
0x1800f8e8a  pop     rdi
0x1800f8e8b  pop     rsi
0x1800f8e8c  pop     rbx
0x1800f8e8d  pop     rbp
0x1800f8e8e  retn
```
