# RemoteAppIntegrationServer::AddHostIdMapping(uint,MessageObjectID,tagMsgRoutingInfo,tagMsgRoutingInfo,Microsoft::WRL::ComPtr<RemoteAppIntegrationHost>)

- ea: `0x1800290cc`
- end: `0x18002932a`
- name: `?AddHostIdMapping@RemoteAppIntegrationServer@@QEAAIIUMessageObjectID@@UtagMsgRoutingInfo@@1V?$ComPtr@VRemoteAppIntegrationHost@@@WRL@Microsoft@@@Z`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002d260`

## callees

- `0x18000275c`
- `0x180013670`
- `0x1800290cc`
- `0x18002c7d4`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800292eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800292eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029103`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029103`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RemoteAppIntegrationServer::AddHostIdMapping(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        __int128 *a3,
        __int128 *a4,
        __int128 *a5,
        _QWORD *a6)
{
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rdi
  RTL_SRWLOCK *v11; // rdx
  __int64 Ptr; // rax
  int v13; // r13d
  __int64 v14; // rcx
  char *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-B9h]
  __int64 v22; // [rsp+30h] [rbp-A9h] BYREF
  int v23; // [rsp+38h] [rbp-A1h]
  int v24; // [rsp+3Ch] [rbp-9Dh]
  __int64 v25; // [rsp+40h] [rbp-99h]
  RTL_SRWLOCK *v26; // [rsp+48h] [rbp-91h]
  _QWORD *v27; // [rsp+50h] [rbp-89h]
  RTL_SRWLOCK *v28; // [rsp+58h] [rbp-81h]
  RTL_SRWLOCK *v29; // [rsp+60h] [rbp-79h]
  __int64 v30; // [rsp+68h] [rbp-71h]
  __int64 v31; // [rsp+70h] [rbp-69h]
  __int128 v32; // [rsp+78h] [rbp-61h]
  __int128 v33; // [rsp+88h] [rbp-51h]
  __int64 v34; // [rsp+98h] [rbp-41h]
  __int128 v35; // [rsp+A0h] [rbp-39h]
  __int128 v36; // [rsp+B0h] [rbp-29h]
  __int64 v37; // [rsp+C0h] [rbp-19h]
  __int128 v38; // [rsp+C8h] [rbp-11h]

  v27 = a6;
  v9 = a1 + 13;
  AcquireSRWLockExclusive(a1 + 13);
  v28 = v9;
  v10 = *a6;
  v31 = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v32 = *a5;
  v33 = a5[1];
  v34 = *((_QWORD *)a5 + 4);
  v35 = *a4;
  v36 = a4[1];
  v37 = *((_QWORD *)a4 + 4);
  v38 = *a3;
  v11 = a1 + 10;
  v26 = a1 + 10;
  Ptr = (__int64)a1[10].Ptr;
  v22 = Ptr;
  v20 = *(_QWORD *)(Ptr + 8);
  v13 = 0;
  v25 = 0;
  v14 = v20;
  while ( !*(_BYTE *)(v14 + 25) )
  {
    v20 = v14;
    if ( *(_DWORD *)(v14 + 32) >= a2 )
    {
      v13 = 1;
      Ptr = v14;
      v14 = *(_QWORD *)v14;
    }
    else
    {
      v13 = 0;
      v14 = *(_QWORD *)(v14 + 16);
    }
  }
  if ( *(_BYTE *)(Ptr + 25) || a2 < *(_DWORD *)(Ptr + 32) )
  {
    if ( v11[1].Ptr == (PVOID)0x1C71C71C71C71C7LL )
      std::_Throw_tree_length_error();
    v29 = v11;
    v30 = 0;
    v15 = (char *)operator new(0x90u);
    *((_DWORD *)v15 + 8) = a2;
    *((_QWORD *)v15 + 5) = 0;
    *((_OWORD *)v15 + 3) = 0;
    *((_OWORD *)v15 + 4) = 0;
    *((_QWORD *)v15 + 10) = 0;
    *(_OWORD *)(v15 + 88) = 0;
    *(_OWORD *)(v15 + 104) = 0;
    *((_QWORD *)v15 + 15) = 0;
    *((_QWORD *)v15 + 16) = 0;
    *((_DWORD *)v15 + 34) = 0;
    v16 = v22;
    *(_QWORD *)v15 = v22;
    *((_QWORD *)v15 + 1) = v16;
    *((_QWORD *)v15 + 2) = v16;
    *((_WORD *)v15 + 12) = 0;
    v22 = v20;
    v23 = v13;
    v24 = v25;
    Ptr = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::vector<std::tuple<unsigned __int64,unsigned int,enum IPduIdHelper::ObjectType>>>>>::_Insert_node(
            v26,
            &v22,
            v15);
  }
  *(_OWORD *)(Ptr + 128) = *a3;
  *(_OWORD *)(Ptr + 88) = *a4;
  *(_OWORD *)(Ptr + 104) = a4[1];
  *(_QWORD *)(Ptr + 120) = *((_QWORD *)a4 + 4);
  *(_OWORD *)(Ptr + 48) = *a5;
  *(_OWORD *)(Ptr + 64) = a5[1];
  *(_QWORD *)(Ptr + 80) = *((_QWORD *)a5 + 4);
  v31 = 0;
  v17 = *(_QWORD *)(Ptr + 40);
  *(_QWORD *)(Ptr + 40) = v10;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  v18 = *a6;
  if ( *a6 )
  {
    *a6 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1800290cc  push    rbp
0x1800290ce  push    rbx
0x1800290cf  push    rsi
0x1800290d0  push    rdi
0x1800290d1  push    r12
0x1800290d3  push    r13
0x1800290d5  push    r14
0x1800290d7  push    r15
0x1800290d9  lea     rbp, [rsp-0Fh]
0x1800290de  sub     rsp, 0E8h
0x1800290e5  mov     r15, r9
0x1800290e8  mov     [rsp+120h+var_F8], r8
0x1800290ed  mov     r14d, edx
0x1800290f0  mov     r13, rcx
0x1800290f3  mov     rsi, [rbp+47h+arg_28]
0x1800290f7  mov     [rsp+120h+var_D0], rsi
0x1800290fc  lea     rbx, [rcx+68h]
0x180029100  mov     rcx, rbx; SRWLock
0x180029103  call    cs:__imp_AcquireSRWLockExclusive
0x180029109  mov     [rsp+120h+var_C8], rbx
0x18002910e  mov     rdi, [rsi]
0x180029111  mov     [rbp+47h+var_B0], rdi
0x180029115  test    rdi, rdi
0x180029118  jz      short loc_18002912A
0x18002911a  mov     rax, [rdi]
0x18002911d  mov     rcx, rdi
0x180029120  mov     rax, [rax+8]
0x180029124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029129  nop
0x18002912a  mov     r12, [rbp+47h+arg_20]
0x18002912e  movups  xmm0, xmmword ptr [r12]
0x180029133  movups  [rbp+47h+var_A8], xmm0
0x180029137  movups  xmm1, xmmword ptr [r12+10h]
0x18002913d  movups  [rbp+47h+var_98], xmm1
0x180029141  movsd   xmm0, qword ptr [r12+20h]
0x180029148  movsd   [rbp+47h+var_88], xmm0
0x18002914d  movups  xmm1, xmmword ptr [r15]
0x180029151  movaps  [rbp+47h+var_80], xmm1
0x180029155  movups  xmm0, xmmword ptr [r15+10h]
0x18002915a  movaps  [rbp+47h+var_70], xmm0
0x18002915e  movsd   xmm1, qword ptr [r15+20h]
0x180029164  movsd   [rbp+47h+var_60], xmm1
0x180029169  mov     rax, [rsp+120h+var_F8]
0x18002916e  movups  xmm0, xmmword ptr [rax]
0x180029171  movdqu  [rbp+47h+var_58], xmm0
0x180029176  lea     rdx, [r13+50h]
0x18002917a  mov     [rsp+120h+var_D8], rdx
0x18002917f  mov     rax, [rdx]
0x180029182  mov     [rsp+120h+var_F0], rax
0x180029187  mov     r8, [rax+8]
0x18002918b  mov     [rsp+120h+var_100], r8
0x180029190  xor     r13d, r13d
0x180029193  xor     ecx, ecx
0x180029195  mov     [rsp+120h+var_E0], rcx
0x18002919a  mov     rcx, r8
0x18002919d  cmp     [r8+19h], r13b
0x1800291a1  jnz     short loc_1800291C9
0x1800291a3  mov     [rsp+120h+var_100], rcx
0x1800291a8  cmp     [rcx+20h], r14d
0x1800291ac  jnb     short loc_1800291B7
0x1800291ae  xor     r13d, r13d
0x1800291b1  mov     rcx, [rcx+10h]
0x1800291b5  jmp     short loc_1800291C3
0x1800291b7  mov     r13d, 1
0x1800291bd  mov     rax, rcx
0x1800291c0  mov     rcx, [rcx]
0x1800291c3  cmp     byte ptr [rcx+19h], 0
0x1800291c7  jz      short loc_1800291A3
0x1800291c9  cmp     byte ptr [rax+19h], 0
0x1800291cd  jnz     short loc_1800291D9
0x1800291cf  cmp     r14d, [rax+20h]
0x1800291d3  jnb     loc_180029276
0x1800291d9  mov     rax, 1C71C71C71C71C7h
0x1800291e3  cmp     [rdx+8], rax
0x1800291e7  jz      loc_180029324
0x1800291ed  mov     [rbp+47h+var_C0], rdx
0x1800291f1  mov     [rbp+47h+var_B8], 0
0x1800291f9  mov     ecx, 90h; Size
0x1800291fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029203  nop
0x180029204  mov     [rax+20h], r14d
0x180029208  xor     edx, edx
0x18002920a  mov     [rax+28h], rdx
0x18002920e  xorps   xmm0, xmm0
0x180029211  xor     ecx, ecx
0x180029213  movups  xmmword ptr [rax+30h], xmm0
0x180029217  movups  xmmword ptr [rax+40h], xmm0
0x18002921b  mov     [rax+50h], rcx
0x18002921f  movups  xmmword ptr [rax+58h], xmm0
0x180029223  movups  xmmword ptr [rax+68h], xmm0
0x180029227  mov     [rax+78h], rcx
0x18002922b  mov     [rax+80h], rdx
0x180029232  mov     [rax+88h], edx
0x180029238  mov     rcx, [rsp+120h+var_F0]
0x18002923d  mov     [rax], rcx
0x180029240  mov     [rax+8], rcx
0x180029244  mov     [rax+10h], rcx
0x180029248  mov     [rax+18h], dx
0x18002924c  mov     rcx, [rsp+120h+var_100]
0x180029251  mov     [rsp+120h+var_F0], rcx
0x180029256  mov     [rsp+120h+var_E8], r13d
0x18002925b  mov     rcx, [rsp+120h+var_E0]
0x180029260  mov     [rsp+120h+var_E4], ecx
0x180029264  mov     r8, rax
0x180029267  lea     rdx, [rsp+120h+var_F0]
0x18002926c  mov     rcx, [rsp+120h+var_D8]
0x180029271  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$vector@V?$tuple@_KIW4ObjectType@IPduIdHelper@@@std@@V?$allocator@V?$tuple@_KIW4ObjectType@IPduIdHelper@@@std@@@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBIV?$vector@V?$tuple@_KIW4ObjectType@IPduIdHelper@@@std@@V?$allocator@V?$tuple@_KIW4ObjectType@IPduIdHelper@@@std@@@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBIV?$vector@V?$tuple@_KIW4ObjectType@IPduIdHelper@@@std@@V?$allocator@V?$tuple@_KIW4ObjectType@IPduIdHelper@@@std@@@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::vector<std::tuple<unsigned __int64,uint,IPduIdHelper::ObjectType>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uint const,std::vector<std::tuple<unsigned __int64,uint,IPduIdHelper::ObjectType>>>,void *> *>,std::_Tree_node<std::pair<uint const,std::vector<std::tuple<unsigned __int64,uint,IPduIdHelper::ObjectType>>>,void *> * const)
0x180029276  mov     rcx, [rsp+120h+var_F8]
0x18002927b  movups  xmm0, xmmword ptr [rcx]
0x18002927e  movdqu  xmmword ptr [rax+80h], xmm0
0x180029286  movups  xmm0, xmmword ptr [r15]
0x18002928a  movups  xmmword ptr [rax+58h], xmm0
0x18002928e  movups  xmm1, xmmword ptr [r15+10h]
0x180029293  movups  xmmword ptr [rax+68h], xmm1
0x180029297  movsd   xmm0, qword ptr [r15+20h]
0x18002929d  movsd   qword ptr [rax+78h], xmm0
0x1800292a2  movups  xmm0, xmmword ptr [r12]
0x1800292a7  movups  xmmword ptr [rax+30h], xmm0
0x1800292ab  movups  xmm1, xmmword ptr [r12+10h]
0x1800292b1  movups  xmmword ptr [rax+40h], xmm1
0x1800292b5  movsd   xmm0, qword ptr [r12+20h]
0x1800292bc  movsd   qword ptr [rax+50h], xmm0
0x1800292c1  mov     [rbp+47h+var_B0], 0
0x1800292c9  mov     rcx, [rax+28h]
0x1800292cd  mov     [rax+28h], rdi
0x1800292d1  test    rcx, rcx
0x1800292d4  jz      short loc_1800292E3
0x1800292d6  mov     rax, [rcx]
0x1800292d9  mov     rax, [rax+10h]
0x1800292dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292e2  nop
0x1800292e3  test    rbx, rbx
0x1800292e6  jz      short loc_1800292F2
0x1800292e8  mov     rcx, rbx; SRWLock
0x1800292eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800292f1  nop
0x1800292f2  mov     rcx, [rsi]
0x1800292f5  test    rcx, rcx
0x1800292f8  jz      short loc_18002930E
0x1800292fa  mov     qword ptr [rsi], 0
0x180029301  mov     rax, [rcx]
0x180029304  mov     rax, [rax+10h]
0x180029308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002930d  nop
0x18002930e  xor     eax, eax
0x180029310  add     rsp, 0E8h
0x180029317  pop     r15
0x180029319  pop     r14
0x18002931b  pop     r13
0x18002931d  pop     r12
0x18002931f  pop     rdi
0x180029320  pop     rsi
0x180029321  pop     rbx
0x180029322  pop     rbp
0x180029323  retn
0x180029324  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
