# StateRepository::Repository::GetSettings(StateRepository::Partition,wchar_t * *,StateRepository::Repository::Options *)

- ea: `0x180101504`
- end: `0x180101654`
- name: `?GetSettings@Repository@StateRepository@@SAJW4Partition@2@PEAPEA_WPEAW4Options@12@@Z`
- size: `336`
- prototype: `__int64 __fastcall(StateRepository::Globals *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180101ca4`

## callees

- `0x1800038f0`
- `0x1800e4c28`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x180101504`
- `0x180104c64`
- `0x180104ca4`

## string_xrefs

- `0x18010152b`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101593`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`
- `0x180101642`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Repository::GetSettings(StateRepository::Globals *a1, _QWORD *a2, _DWORD *a3)
{
  unsigned int v5; // edi
  int ServiceControl_FailIfBlocked; // eax
  unsigned int v7; // ebx
  __int64 v9; // rsi
  __int64 v10; // rbx
  _WORD *v11; // rdi
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  _WORD *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rcx
  _WORD *v17; // r8
  _WORD *v18; // rdx
  int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = (unsigned int)a1;
  ServiceControl_FailIfBlocked = StateRepository::Globals::GetServiceControl_FailIfBlocked(a1);
  v7 = ServiceControl_FailIfBlocked;
  if ( ServiceControl_FailIfBlocked < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)ServiceControl_FailIfBlocked,
      v19);
    return v7;
  }
  v9 = StateRepository::Globals::PartitionSettings::Get(v5);
  v10 = -1;
  v11 = *(_WORD **)v9;
  do
    ++v10;
  while ( v11[v10] );
  v12 = v10 + 1;
  v13 = 2 * v12;
  if ( !is_mul_ok(v12, 2u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v14 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)0x8007000ELL,
      v19);
    operator delete(0);
    return v7;
  }
  if ( !v12 )
  {
    v15 = 2147942487LL;
    goto LABEL_22;
  }
  if ( v12 > 0x7FFFFFFF )
  {
    v15 = 2147942487LL;
    *v14 = 0;
    goto LABEL_22;
  }
  v16 = 2147483646;
  v17 = v14;
  do
  {
    if ( !v16 )
      break;
    if ( !*v11 )
      break;
    *v17++ = *v11++;
    --v16;
    --v12;
  }
  while ( v12 );
  v18 = v17 - 1;
  v15 = v12 == 0 ? 0x8007007A : 0;
  if ( v12 )
    v18 = v17;
  *v18 = 0;
  if ( !v12 )
LABEL_22:
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x6F5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)v15,
      v19);
  *a2 = v14;
  *a3 = *(_DWORD *)(v9 + 24);
  operator delete(0);
  return 0;
}

```

## disassembly

```asm
0x180101504  push    rbx
0x180101506  push    rbp
0x180101507  push    rsi
0x180101508  push    rdi
0x180101509  push    r14
0x18010150b  push    r15
0x18010150d  sub     rsp, 28h
0x180101511  mov     r14, r8
0x180101514  mov     r15, rdx
0x180101517  mov     edi, ecx
0x180101519  call    ?GetServiceControl_FailIfBlocked@Globals@StateRepository@@YAJ_N@Z; StateRepository::Globals::GetServiceControl_FailIfBlocked(bool)
0x18010151e  xor     ebp, ebp
0x180101520  mov     ebx, eax
0x180101522  test    eax, eax
0x180101524  jns     short loc_18010154E
0x180101526  mov     rcx, [rsp+58h]; this
0x18010152b  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101532  mov     r9d, eax; char *
0x180101535  mov     edx, 6ECh; void *
0x18010153a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010153f  mov     eax, ebx
0x180101541  add     rsp, 28h
0x180101545  pop     r15
0x180101547  pop     r14
0x180101549  pop     rdi
0x18010154a  pop     rsi
0x18010154b  pop     rbp
0x18010154c  pop     rbx
0x18010154d  retn
0x18010154e  mov     ecx, edi
0x180101550  call    ?Get@PartitionSettings@Globals@StateRepository@@SAPEBU123@W4Partition@3@@Z; StateRepository::Globals::PartitionSettings::Get(StateRepository::Partition)
0x180101555  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180101559  mov     rsi, rax
0x18010155c  mov     rbx, rcx
0x18010155f  mov     rdi, [rax]
0x180101562  inc     rbx
0x180101565  cmp     [rdi+rbx*2], bp
0x180101569  jnz     short loc_180101562
0x18010156b  inc     rbx
0x18010156e  mov     eax, 2
0x180101573  mul     rbx
0x180101576  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010157d  cmovb   rax, rcx
0x180101581  mov     rcx, rax; unsigned __int64
0x180101584  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180101589  test    rax, rax
0x18010158c  jnz     short loc_1801015B5
0x18010158e  mov     rcx, [rsp+58h]; this
0x180101593  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18010159a  mov     ebx, 8007000Eh
0x18010159f  mov     edx, 6F4h; void *
0x1801015a4  mov     r9d, ebx; char *
0x1801015a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801015ac  xor     ecx, ecx; Block
0x1801015ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801015b3  jmp     short loc_18010153F
0x1801015b5  test    rbx, rbx
0x1801015b8  jz      short loc_18010162F
0x1801015ba  cmp     rbx, 7FFFFFFFh
0x1801015c1  jbe     short loc_1801015CB
0x1801015c3  mov     r9d, 80070057h
0x1801015c9  jmp     short loc_18010163A
0x1801015cb  mov     ecx, 7FFFFFFEh
0x1801015d0  mov     r8, rax
0x1801015d3  test    rcx, rcx
0x1801015d6  jz      short loc_1801015F5
0x1801015d8  movzx   edx, word ptr [rdi]
0x1801015db  test    dx, dx
0x1801015de  jz      short loc_1801015F5
0x1801015e0  mov     [r8], dx
0x1801015e4  add     rdi, 2
0x1801015e8  add     r8, 2
0x1801015ec  dec     rcx
0x1801015ef  sub     rbx, 1
0x1801015f3  jnz     short loc_1801015D3
0x1801015f5  mov     rcx, rbx
0x1801015f8  lea     rdx, [r8-2]
0x1801015fc  neg     rcx
0x1801015ff  sbb     r9d, r9d
0x180101602  not     r9d
0x180101605  and     r9d, 8007007Ah
0x18010160c  test    rbx, rbx
0x18010160f  cmovnz  rdx, r8
0x180101613  mov     [rdx], bp
0x180101616  jz      short loc_18010163D
0x180101618  mov     [r15], rax
0x18010161b  xor     ecx, ecx; Block
0x18010161d  mov     eax, [rsi+18h]
0x180101620  mov     [r14], eax
0x180101623  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180101628  xor     eax, eax
0x18010162a  jmp     loc_180101541
0x18010162f  mov     r9d, 80070057h; char *
0x180101635  test    rbx, rbx
0x180101638  jz      short loc_18010163D
0x18010163a  mov     [rax], bp
0x18010163d  mov     rcx, [rsp+58h]; this
0x180101642  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180101649  mov     edx, 6F5h; void *
0x18010164e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
