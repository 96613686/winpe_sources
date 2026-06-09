# CVaultMemoryStore::DeleteCredential(ushort const *)

- ea: `0x180024520`
- end: `0x180024714`
- name: `?DeleteCredential@CVaultMemoryStore@@UEAAKPEBG@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct _RTL_RESOURCE *this, const unsigned __int16 *Buf1)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x180023c90`

## callees

- `0x180012210`
- `0x180024520`
- `0x18002471c`
- `0x180024ebc`
- `0x180037b0c`
- `0x18003b7d8`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180024572`
- `ntdll!RtlReleaseResource` at `0x180024602`
- `ntdll!RtlReleaseResource` at `0x1800246b7`
- `ntdll!RtlReleaseResource` at `0x180024572`
- `ntdll!RtlReleaseResource` at `0x180024602`
- `ntdll!RtlReleaseResource` at `0x1800246b7`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002455a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002455a`

## pseudocode

```c
__int64 __fastcall CVaultMemoryStore::DeleteCredential(struct _RTL_RESOURCE *this, const unsigned __int16 *Buf1)
{
  struct _RTL_RESOURCE *v4; // r14
  __int64 v5; // rax
  unsigned int v6; // ebp
  HANDLE *p_LockSemaphore; // r15
  unsigned int *LockSemaphore; // r13
  unsigned int *v10; // rsi
  unsigned int *v11; // rdi
  char v12; // cl
  __int64 *v13; // rax
  __int64 v14; // rsi
  int ExclusiveSemaphore_high; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int updated; // eax
  _QWORD *v19; // rax
  ULONG ExclusiveWaiters; // eax

  v4 = this + 2;
  v5 = -1;
  do
    ++v5;
  while ( Buf1[v5] );
  v6 = 2 * v5;
  RtlAcquireResourceExclusive(this + 2, 1u);
  if ( LOBYTE(this[3].Lock.DebugInfo) )
  {
    RtlReleaseResource(v4);
    return 55;
  }
  p_LockSemaphore = &this->Lock.LockSemaphore;
  LockSemaphore = (unsigned int *)this->Lock.LockSemaphore;
  v10 = (unsigned int *)*((_QWORD *)LockSemaphore + 1);
  v11 = LockSemaphore;
  if ( *((_BYTE *)v10 + 25) )
    goto LABEL_13;
  do
  {
    if ( v10[8] == v6 )
    {
      if ( memcmp_0(*((const void **)v10 + 5), Buf1, v6) < 0 )
        goto LABEL_8;
    }
    else if ( v10[8] < v6 )
    {
LABEL_8:
      v12 = 1;
      goto LABEL_9;
    }
    v12 = 0;
    v11 = v10;
LABEL_9:
    v13 = (__int64 *)(v10 + 4);
    if ( !v12 )
      v13 = (__int64 *)v10;
    v10 = (unsigned int *)*v13;
  }
  while ( !*(_BYTE *)(*v13 + 25) );
  p_LockSemaphore = &this->Lock.LockSemaphore;
LABEL_13:
  if ( *((_BYTE *)v11 + 25) )
  {
LABEL_16:
    RtlReleaseResource(v4);
    return 1168;
  }
  if ( v6 != v11[8] )
  {
    if ( v6 >= v11[8] )
      goto LABEL_20;
    goto LABEL_16;
  }
  if ( memcmp_0(Buf1, *((const void **)v11 + 5), v11[8]) < 0 )
    goto LABEL_16;
LABEL_20:
  if ( v11 == LockSemaphore )
    goto LABEL_16;
  v14 = *((_QWORD *)v11 + 6);
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) & 0x40) != 0 )
  {
    ExclusiveWaiters = this->ExclusiveWaiters;
    if ( ExclusiveWaiters )
      this->ExclusiveWaiters = ExclusiveWaiters - 1;
  }
  else
  {
    ExclusiveSemaphore_high = HIDWORD(this->ExclusiveSemaphore);
    if ( ExclusiveSemaphore_high )
      HIDWORD(this->ExclusiveSemaphore) = ExclusiveSemaphore_high - 1;
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 208LL))(v14);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
    updated = CVaultMemoryStore::UpdateCredCountPerAppContainer((CVaultMemoryStore *)this, *(void **)(v17 + 16), 0);
    if ( updated && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_88c39a8abb2e32ad80f44de23670705e_Traceguids, updated);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  VaultFreeInternal(*((HLOCAL *)v11 + 5));
  v19 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>::_Extract(
                    p_LockSemaphore,
                    v11);
  std::_Deallocate<16>(v19, 0x38u);
  RtlReleaseResource(v4);
  return 0;
}

```

## disassembly

```asm
0x180024520  push    rbx
0x180024522  push    rbp
0x180024523  push    rsi
0x180024524  push    rdi
0x180024525  push    r12
0x180024527  push    r13
0x180024529  push    r14
0x18002452b  push    r15
0x18002452d  sub     rsp, 58h
0x180024531  mov     r12, rdx
0x180024534  mov     rbx, rcx
0x180024537  lea     r14, [rcx+0C0h]
0x18002453e  mov     [rsp+98h+var_78], r14
0x180024543  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024547  xor     ebp, ebp
0x180024549  inc     rax
0x18002454c  cmp     [rdx+rax*2], bp
0x180024550  jnz     short loc_180024549
0x180024552  lea     ebp, [rax+rax]
0x180024555  mov     dl, 1; Wait
0x180024557  mov     rcx, r14; Resource
0x18002455a  call    cs:__imp_RtlAcquireResourceExclusive
0x180024560  mov     [rsp+98h+var_70], 1
0x180024565  xor     edx, edx
0x180024567  cmp     [rbx+120h], dl
0x18002456d  jz      short loc_18002458E
0x18002456f  mov     rcx, r14; Resource
0x180024572  call    cs:__imp_RtlReleaseResource
0x180024578  mov     eax, 37h ; '7'
0x18002457d  add     rsp, 58h
0x180024581  pop     r15
0x180024583  pop     r14
0x180024585  pop     r13
0x180024587  pop     r12
0x180024589  pop     rdi
0x18002458a  pop     rsi
0x18002458b  pop     rbp
0x18002458c  pop     rbx
0x18002458d  retn
0x18002458e  lea     r15, [rbx+18h]
0x180024592  mov     r13, [r15]
0x180024595  mov     rsi, [r13+8]
0x180024599  xor     eax, eax
0x18002459b  mov     [rsp+98h+var_5C], eax
0x18002459f  mov     rdi, r13
0x1800245a2  cmp     [rsi+19h], dl
0x1800245a5  jnz     short loc_1800245DD
0x1800245a7  mov     r15d, ebp
0x1800245aa  cmp     [rsi+20h], r15d
0x1800245ae  jnz     short loc_180024619
0x1800245b0  mov     r8, r15; Size
0x1800245b3  mov     rdx, r12; Buf2
0x1800245b6  mov     rcx, [rsi+28h]; Buf1
0x1800245ba  call    memcmp_0
0x1800245bf  xor     edx, edx
0x1800245c1  test    eax, eax
0x1800245c3  jns     short loc_180024612
0x1800245c5  mov     cl, 1
0x1800245c7  lea     rax, [rsi+10h]
0x1800245cb  test    cl, cl
0x1800245cd  cmovz   rax, rsi
0x1800245d1  mov     rsi, [rax]
0x1800245d4  cmp     [rsi+19h], dl
0x1800245d7  jz      short loc_1800245AA
0x1800245d9  lea     r15, [rbx+18h]
0x1800245dd  cmp     [rdi+19h], dl
0x1800245e0  jnz     short loc_1800245FF
0x1800245e2  cmp     ebp, [rdi+20h]
0x1800245e5  jnz     loc_1800246C4
0x1800245eb  mov     r8d, [rdi+20h]; Size
0x1800245ef  mov     rdx, [rdi+28h]; Buf2
0x1800245f3  mov     rcx, r12; Buf1
0x1800245f6  call    memcmp_0
0x1800245fb  test    eax, eax
0x1800245fd  jns     short loc_18002461D
0x1800245ff  mov     rcx, r14; Resource
0x180024602  call    cs:__imp_RtlReleaseResource
0x180024608  mov     eax, 490h
0x18002460d  jmp     loc_18002457D
0x180024612  mov     cl, dl
0x180024614  mov     rdi, rsi
0x180024617  jmp     short loc_1800245C7
0x180024619  jnb     short loc_180024612
0x18002461b  jmp     short loc_1800245C5
0x18002461d  cmp     rdi, r13
0x180024620  jz      short loc_1800245FF
0x180024622  mov     rsi, [rdi+30h]
0x180024626  mov     rax, [rsi]
0x180024629  mov     rcx, rsi
0x18002462c  mov     rax, [rax+0A0h]
0x180024633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024638  test    al, 40h
0x18002463a  jnz     loc_1800246CF
0x180024640  mov     eax, [rbx+3Ch]
0x180024643  test    eax, eax
0x180024645  jz      short loc_18002464C
0x180024647  dec     eax
0x180024649  mov     [rbx+3Ch], eax
0x18002464c  mov     rax, [rsi]
0x18002464f  mov     rcx, rsi
0x180024652  mov     rax, [rax+0D0h]
0x180024659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002465e  mov     rdx, rax
0x180024661  mov     rcx, [rax]
0x180024664  mov     rax, [rcx+20h]
0x180024668  mov     rcx, rdx
0x18002466b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024670  xor     r8d, r8d; int
0x180024673  mov     rdx, [rax+10h]; void *
0x180024677  mov     rcx, rbx; this
0x18002467a  call    ?UpdateCredCountPerAppContainer@CVaultMemoryStore@@IEAAKPEAXH@Z; CVaultMemoryStore::UpdateCredCountPerAppContainer(void *,int)
0x18002467f  test    eax, eax
0x180024681  jnz     short loc_1800246DD
0x180024683  mov     rax, [rsi]
0x180024686  mov     rcx, rsi
0x180024689  mov     rax, [rax+8]
0x18002468d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024692  mov     rcx, [rdi+28h]; hMem
0x180024696  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18002469b  mov     rdx, rdi
0x18002469e  mov     rcx, r15
0x1800246a1  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>,std::_Iterator_base0>)
0x1800246a6  mov     edx, 38h ; '8'
0x1800246ab  mov     rcx, rax
0x1800246ae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800246b3  nop
0x1800246b4  mov     rcx, r14; Resource
0x1800246b7  call    cs:__imp_RtlReleaseResource
0x1800246bd  xor     eax, eax
0x1800246bf  jmp     loc_18002457D
0x1800246c4  jb      loc_1800245FF
0x1800246ca  jmp     loc_18002461D
0x1800246cf  mov     eax, [rbx+40h]
0x1800246d2  test    eax, eax
0x1800246d4  jz      short loc_180024683
0x1800246d6  dec     eax
0x1800246d8  mov     [rbx+40h], eax
0x1800246db  jmp     short loc_180024683
0x1800246dd  lea     rdx, WPP_GLOBAL_Control
0x1800246e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246eb  cmp     rcx, rdx
0x1800246ee  jz      short loc_180024683
0x1800246f0  test    byte ptr [rcx+1Ch], 4
0x1800246f4  jz      short loc_180024683
0x1800246f6  mov     edx, 11h
0x1800246fb  mov     r9d, eax
0x1800246fe  lea     r8, WPP_88c39a8abb2e32ad80f44de23670705e_Traceguids
0x180024705  mov     rcx, [rcx+10h]
0x180024709  call    WPP_SF_d
0x18002470e  jmp     loc_180024683
```
