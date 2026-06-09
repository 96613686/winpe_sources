# CChangeApplier::GetFilterKeyMapCompleteHandler(void)

- ea: `0x18003cb34`
- end: `0x18003ce00`
- name: `?GetFilterKeyMapCompleteHandler@CChangeApplier@@AEAAJXZ`
- size: `716`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180032244`
- `0x180034e84`
- `0x180035724`
- `0x18003cb34`
- `0x180046160`
- `0x18009323e`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003cd82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003cd82`

## string_xrefs

- `0x18003cb6d`: `CChangeApplier::GetFilterKeyMapCompleteHandler`
- `0x18003cdd1`: `CChangeApplier::GetFilterKeyMapCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetFilterKeyMapCompleteHandler(CChangeApplier *this)
{
  int FilterForgottenKnowledge; // ebx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // r14d
  unsigned int v8; // ecx
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // esi
  int v12; // r15d
  __int64 v13; // rcx
  int v14; // eax
  void *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v19; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  int v21; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetFilterKeyMapCompleteHandler");
  }
  FilterForgottenKnowledge = CChangeApplier::ChangeState((__int64)this, 2);
  if ( FilterForgottenKnowledge >= 0 )
  {
    v3 = *((_QWORD *)this + 29);
    v19 = 0;
    FilterForgottenKnowledge = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 24LL))(v3, &v19);
    if ( !FilterForgottenKnowledge )
    {
      v4 = *((_QWORD *)this + 27);
      if ( !v4
        || (FilterForgottenKnowledge = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 24LL))(
                                         v4,
                                         (char *)this + 224)) == 0 )
      {
        if ( !v19 )
        {
LABEL_30:
          if ( *((_DWORD *)this + 60) )
          {
            FilterForgottenKnowledge = CChangeApplier::BeginGetFilterForgottenKnowledge(this, 0);
          }
          else
          {
            v15 = (void *)*((_QWORD *)this + 34);
            if ( v15 )
              SetEvent(v15);
          }
          goto LABEL_34;
        }
        v5 = SeAlloc(saturated_mul(v19, 8u));
        *((_QWORD *)this + 31) = v5;
        if ( !v5 )
        {
          FilterForgottenKnowledge = -2147024882;
LABEL_38:
          FilterForgottenKnowledge = CChangeApplier::SetError(
                                       this,
                                       *((struct ISyncCallback **)this + 50),
                                       FilterForgottenKnowledge);
          goto LABEL_39;
        }
        memset_0(v5, 0, 8LL * v19);
        v6 = v19;
        v7 = 0;
        *((_DWORD *)this + 60) = v19;
        v8 = 0;
        v21 = 0;
        while ( v8 < v6 )
        {
          v9 = *((_QWORD *)this + 29);
          v18 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 40LL))(v9, v7, &v18);
          v11 = 0;
          FilterForgottenKnowledge = v10;
          v20 = 0;
          if ( !v10 )
          {
            v12 = 0;
            do
            {
              if ( v12 || v10 >= *((_DWORD *)this + 56) )
                break;
              v13 = *((_QWORD *)this + 27);
              v17 = 0;
              FilterForgottenKnowledge = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 40LL))(
                                           v13,
                                           v11,
                                           &v17);
              if ( !FilterForgottenKnowledge )
              {
                FilterForgottenKnowledge = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 24LL))(
                                             v18,
                                             v17);
                if ( FilterForgottenKnowledge )
                {
                  if ( FilterForgottenKnowledge == 1 )
                    FilterForgottenKnowledge = 0;
                }
                else
                {
                  v14 = HashTable<unsigned long,unsigned long,SimpleHashTableContext>::AddItem(
                          *((_QWORD *)this + 32),
                          &v21,
                          &v20);
                  v11 = v20;
                  FilterForgottenKnowledge = v14;
                  v12 = 1;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              }
              v20 = ++v11;
              v10 = v11;
            }
            while ( !FilterForgottenKnowledge );
          }
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v21 = ++v7;
          v8 = v7;
          if ( FilterForgottenKnowledge )
            break;
          v6 = v19;
        }
      }
    }
    if ( FilterForgottenKnowledge < 0 )
      goto LABEL_34;
    goto LABEL_30;
  }
LABEL_34:
  if ( FilterForgottenKnowledge == -2147467260 )
  {
    if ( !*((_DWORD *)this + 170) )
      goto LABEL_38;
    FilterForgottenKnowledge = 0;
  }
  else if ( FilterForgottenKnowledge < 0 )
  {
    goto LABEL_38;
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetFilterKeyMapCompleteHandler",
      FilterForgottenKnowledge);
  }
  return (unsigned int)FilterForgottenKnowledge;
}

```

## disassembly

```asm
0x18003cb34  mov     [rsp-28h+arg_0], rbx
0x18003cb39  push    rbp
0x18003cb3a  push    rsi
0x18003cb3b  push    rdi
0x18003cb3c  push    r14
0x18003cb3e  push    r15
0x18003cb40  mov     rbp, rsp
0x18003cb43  sub     rsp, 40h
0x18003cb47  mov     rdi, rcx
0x18003cb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb51  lea     rsi, WPP_GLOBAL_Control
0x18003cb58  cmp     rcx, rsi
0x18003cb5b  jz      short loc_18003CB85
0x18003cb5d  test    byte ptr [rcx+1Ch], 8
0x18003cb61  jz      short loc_18003CB85
0x18003cb63  cmp     byte ptr [rcx+19h], 5
0x18003cb67  jb      short loc_18003CB85
0x18003cb69  mov     rcx, [rcx+10h]
0x18003cb6d  lea     r9, aCchangeapplier_78; "CChangeApplier::GetFilterKeyMapComplete"...
0x18003cb74  mov     edx, 75h ; 'u'
0x18003cb79  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003cb80  call    WPP_SF_s
0x18003cb85  mov     edx, 2
0x18003cb8a  mov     rcx, rdi
0x18003cb8d  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x18003cb92  mov     ebx, eax
0x18003cb94  test    eax, eax
0x18003cb96  js      loc_18003CD88
0x18003cb9c  mov     rcx, [rdi+0E8h]
0x18003cba3  lea     rdx, [rbp+arg_8]
0x18003cba7  mov     [rbp+arg_8], 0
0x18003cbae  mov     rax, [rcx]
0x18003cbb1  mov     rax, [rax+18h]
0x18003cbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbba  mov     ebx, eax
0x18003cbbc  test    eax, eax
0x18003cbbe  jnz     loc_18003CD5B
0x18003cbc4  mov     rcx, [rdi+0D8h]
0x18003cbcb  test    rcx, rcx
0x18003cbce  jz      short loc_18003CBED
0x18003cbd0  mov     rax, [rcx]
0x18003cbd3  lea     rdx, [rdi+0E0h]
0x18003cbda  mov     rax, [rax+18h]
0x18003cbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbe3  mov     ebx, eax
0x18003cbe5  test    eax, eax
0x18003cbe7  jnz     loc_18003CD5B
0x18003cbed  mov     eax, [rbp+arg_8]
0x18003cbf0  test    eax, eax
0x18003cbf2  jz      loc_18003CD5F
0x18003cbf8  mov     ecx, eax
0x18003cbfa  mov     eax, 8
0x18003cbff  mul     rcx
0x18003cc02  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003cc09  cmovb   rax, rcx
0x18003cc0d  mov     rcx, rax; unsigned __int64
0x18003cc10  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18003cc15  mov     [rdi+0F8h], rax
0x18003cc1c  test    rax, rax
0x18003cc1f  jnz     short loc_18003CC2B
0x18003cc21  mov     ebx, 8007000Eh
0x18003cc26  jmp     loc_18003CDA1
0x18003cc2b  mov     r8d, [rbp+arg_8]
0x18003cc2f  xor     edx, edx; Val
0x18003cc31  shl     r8, 3; Size
0x18003cc35  mov     rcx, rax; void *
0x18003cc38  call    memset_0
0x18003cc3d  mov     eax, [rbp+arg_8]
0x18003cc40  xor     r14d, r14d
0x18003cc43  mov     [rdi+0F0h], eax
0x18003cc49  xor     ecx, ecx
0x18003cc4b  mov     [rbp+arg_18], r14d
0x18003cc4f  cmp     ecx, eax
0x18003cc51  jnb     loc_18003CD54
0x18003cc57  mov     rcx, [rdi+0E8h]
0x18003cc5e  lea     r8, [rbp+var_8]
0x18003cc62  mov     [rbp+var_8], 0
0x18003cc6a  mov     edx, r14d
0x18003cc6d  mov     rax, [rcx]
0x18003cc70  mov     rax, [rax+28h]
0x18003cc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc79  xor     esi, esi
0x18003cc7b  mov     ebx, eax
0x18003cc7d  mov     [rbp+arg_10], esi
0x18003cc80  test    eax, eax
0x18003cc82  jnz     loc_18003CD29
0x18003cc88  xor     r15d, r15d
0x18003cc8b  test    r15d, r15d
0x18003cc8e  jnz     loc_18003CD29
0x18003cc94  cmp     eax, [rdi+0E0h]
0x18003cc9a  jnb     loc_18003CD29
0x18003cca0  mov     rcx, [rdi+0D8h]
0x18003cca7  lea     r8, [rbp+var_10]
0x18003ccab  mov     [rbp+var_10], 0
0x18003ccb3  mov     edx, esi
0x18003ccb5  mov     rax, [rcx]
0x18003ccb8  mov     rax, [rax+28h]
0x18003ccbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccc1  mov     ebx, eax
0x18003ccc3  test    eax, eax
0x18003ccc5  jnz     short loc_18003CD1A
0x18003ccc7  mov     rcx, [rbp+var_8]
0x18003cccb  mov     rdx, [rbp+var_10]
0x18003cccf  mov     rax, [rcx]
0x18003ccd2  mov     rax, [rax+18h]
0x18003ccd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccdb  mov     ebx, eax
0x18003ccdd  test    eax, eax
0x18003ccdf  jnz     short loc_18003CD02
0x18003cce1  mov     rcx, [rdi+100h]
0x18003cce8  lea     r8, [rbp+arg_10]
0x18003ccec  lea     rdx, [rbp+arg_18]
0x18003ccf0  call    ?AddItem@?$HashTable@KKVSimpleHashTableContext@@@@QEAAJAEBK0@Z; HashTable<ulong,ulong,SimpleHashTableContext>::AddItem(ulong const &,ulong const &)
0x18003ccf5  mov     esi, [rbp+arg_10]
0x18003ccf8  mov     ebx, eax
0x18003ccfa  mov     r15d, 1
0x18003cd00  jmp     short loc_18003CD0A
0x18003cd02  xor     eax, eax
0x18003cd04  cmp     ebx, 1
0x18003cd07  cmovz   ebx, eax
0x18003cd0a  mov     rcx, [rbp+var_10]
0x18003cd0e  mov     rax, [rcx]
0x18003cd11  mov     rax, [rax+10h]
0x18003cd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd1a  inc     esi
0x18003cd1c  mov     [rbp+arg_10], esi
0x18003cd1f  mov     eax, esi
0x18003cd21  test    ebx, ebx
0x18003cd23  jz      loc_18003CC8B
0x18003cd29  mov     rcx, [rbp+var_8]
0x18003cd2d  test    rcx, rcx
0x18003cd30  jz      short loc_18003CD3E
0x18003cd32  mov     rax, [rcx]
0x18003cd35  mov     rax, [rax+10h]
0x18003cd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd3e  inc     r14d
0x18003cd41  mov     [rbp+arg_18], r14d
0x18003cd45  mov     ecx, r14d
0x18003cd48  test    ebx, ebx
0x18003cd4a  jnz     short loc_18003CD54
0x18003cd4c  mov     eax, [rbp+arg_8]
0x18003cd4f  jmp     loc_18003CC4F
0x18003cd54  lea     rsi, WPP_GLOBAL_Control
0x18003cd5b  test    ebx, ebx
0x18003cd5d  js      short loc_18003CD88
0x18003cd5f  cmp     dword ptr [rdi+0F0h], 0
0x18003cd66  jbe     short loc_18003CD76
0x18003cd68  xor     edx, edx; unsigned int
0x18003cd6a  mov     rcx, rdi; this
0x18003cd6d  call    ?BeginGetFilterForgottenKnowledge@CChangeApplier@@AEAAJK@Z; CChangeApplier::BeginGetFilterForgottenKnowledge(ulong)
0x18003cd72  mov     ebx, eax
0x18003cd74  jmp     short loc_18003CD88
0x18003cd76  mov     rcx, [rdi+110h]; hEvent
0x18003cd7d  test    rcx, rcx
0x18003cd80  jz      short loc_18003CD88
0x18003cd82  call    cs:__imp_SetEvent
0x18003cd88  cmp     ebx, 80004004h
0x18003cd8e  jnz     short loc_18003CD9D
0x18003cd90  cmp     dword ptr [rdi+2A8h], 0
0x18003cd97  jz      short loc_18003CDA1
0x18003cd99  xor     ebx, ebx
0x18003cd9b  jmp     short loc_18003CDB5
0x18003cd9d  test    ebx, ebx
0x18003cd9f  jns     short loc_18003CDB5
0x18003cda1  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x18003cda8  mov     r8d, ebx; int
0x18003cdab  mov     rcx, rdi; this
0x18003cdae  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003cdb3  mov     ebx, eax
0x18003cdb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cdbc  cmp     rcx, rsi
0x18003cdbf  jz      short loc_18003CDED
0x18003cdc1  test    byte ptr [rcx+1Ch], 8
0x18003cdc5  jz      short loc_18003CDED
0x18003cdc7  cmp     byte ptr [rcx+19h], 5
0x18003cdcb  jb      short loc_18003CDED
0x18003cdcd  mov     rcx, [rcx+10h]
0x18003cdd1  lea     r9, aCchangeapplier_78; "CChangeApplier::GetFilterKeyMapComplete"...
0x18003cdd8  mov     edx, 76h ; 'v'
0x18003cddd  mov     [rsp+40h+var_20], ebx
0x18003cde1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003cde8  call    WPP_SF_sD
0x18003cded  mov     eax, ebx
0x18003cdef  mov     rbx, [rsp+40h+arg_0]
0x18003cdf4  add     rsp, 40h
0x18003cdf8  pop     r15
0x18003cdfa  pop     r14
0x18003cdfc  pop     rdi
0x18003cdfd  pop     rsi
0x18003cdfe  pop     rbp
0x18003cdff  retn
```
