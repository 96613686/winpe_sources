# TransientSubChecker::CheckerThread::ProcessCheckerArgs(TransientSubChecker::CheckerThread::CheckerArgs *)

- ea: `0x1800116d8`
- end: `0x180011a27`
- name: `?ProcessCheckerArgs@CheckerThread@TransientSubChecker@@AEAAJPEAUCheckerArgs@12@@Z`
- size: `847`
- prototype: `__int64 __fastcall(TransientSubChecker::CheckerThread *__hidden this, struct TransientSubChecker::CheckerThread::CheckerArgs *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800114e0`

## callees

- `0x180003d54`
- `0x180010210`
- `0x180010410`
- `0x180011420`
- `0x1800116d8`
- `0x180011a30`
- `0x18002569c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117e7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800119a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800119a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a16`

## string_xrefs

- `0x18001191c`: `com\complus\src\events\tier2\eventsystem2.cpp`

## pseudocode

```c
__int64 __fastcall TransientSubChecker::CheckerThread::ProcessCheckerArgs(
        TransientSubChecker::CheckerThread *this,
        struct TransientSubChecker::CheckerThread::CheckerArgs *a2)
{
  struct TransientSubChecker::CheckerThread::CheckerArgs *v2; // r12
  __int64 v4; // rcx
  int v5; // r15d
  __int64 v6; // r14
  __int64 v7; // rsi
  signed int v8; // ebx
  __m128i v9; // xmm6
  __int64 v10; // r9
  unsigned int v11; // eax
  __int64 v12; // r8
  __int64 *i; // rdx
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  unsigned __int16 v16; // cx
  int v17; // eax
  int v18; // esi
  int v19; // eax
  __int64 v21; // [rsp+38h] [rbp-70h] BYREF
  HANDLE Token[2]; // [rsp+40h] [rbp-68h] BYREF
  __m128i v23; // [rsp+50h] [rbp-58h]
  __int64 v26; // [rsp+C8h] [rbp+20h] BYREF

  v2 = a2;
  v21 = 0;
  *(_OWORD *)Token = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v6 = *((_QWORD *)this + 2);
  v7 = *((_QWORD *)a2 + 1);
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v21 = 0;
  LOBYTE(Token[0]) = 0;
  Token[1] = 0;
  if ( *(_DWORD *)(v6 + 400) )
  {
    v8 = -2147417848;
  }
  else
  {
    CSemExclusiveES::Lock((CSemExclusiveES *)(v6 + 120));
    v11 = HashKey<unsigned short const *>(v7);
    v12 = *(_QWORD *)(v6 + 40);
    if ( !v12 )
      goto LABEL_35;
    for ( i = *(__int64 **)(v12 + 8LL * (v11 % *(_DWORD *)(v6 + 48))); i; i = (__int64 *)*i )
    {
      v14 = (unsigned __int16 *)i[2];
      if ( v7 )
      {
        v15 = v7 - (_QWORD)v14;
        while ( 1 )
        {
          v16 = *v14;
          if ( *v14 != *(unsigned __int16 *)((char *)v14 + v15) )
            break;
          ++v14;
          if ( !v16 )
          {
            v17 = 0;
            goto LABEL_10;
          }
        }
        v17 = v16 < *(unsigned __int16 *)((char *)v14 + v15) ? -1 : 1;
      }
      else
      {
        if ( !*((_DWORD *)v14 - 2) )
          break;
        v17 = 1;
      }
LABEL_10:
      if ( !v17 )
        break;
    }
    if ( i )
    {
      v9 = *(__m128i *)(i + 3);
      v23 = v9;
      v18 = 1;
      v8 = ImpersonateOther_Save((HANDLE)_mm_srli_si128(v9, 8).m128i_i64[0], (struct SavedImpersonationState *)Token);
    }
    else
    {
LABEL_35:
      v18 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 120));
    if ( v8 >= 0 )
    {
      if ( v18 )
      {
        if ( !*(_QWORD *)(v6 + 32) )
          InternalError(L"com\\complus\\src\\events\\tier2\\eventsystem2.cpp", 0x47Eu, 0x80001203, 0x11u);
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(**(_QWORD **)(v6 + 32) + 40LL))(
               *(_QWORD *)(v6 + 32),
               (unsigned int)_mm_cvtsi128_si32(v9),
               &GUID_00000000_0000_0000_c000_000000000046,
               &v21);
        if ( v8 < 0 )
          ImpersonateOther_Restore((struct SavedImpersonationState *)Token);
      }
      else
      {
        v8 = 1;
      }
    }
    v10 = v21;
    v4 = v26;
    v2 = a2;
  }
  if ( !v8 )
  {
    v19 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v10)(v10, qword_180053120, &v26);
    if ( v19 >= 0 )
    {
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    else if ( (unsigned int)(v19 + 2147467263) > 1 && v19 != -2147024891 && v19 != -2147023113 )
    {
      v10 = v21;
      v4 = v26;
LABEL_40:
      v5 = 1;
      goto LABEL_41;
    }
    v4 = 0;
    v26 = 0;
    v10 = v21;
    goto LABEL_41;
  }
  if ( v8 == -2147023174 || v8 == -2147417848 || (unsigned int)(v8 + 2147023170) <= 1 )
    goto LABEL_40;
LABEL_41:
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v4 = v26;
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( LOBYTE(Token[0]) )
  {
    SetThreadToken(0, Token[1]);
    LOBYTE(Token[0]) = 0;
  }
  if ( Token[1] )
  {
    CloseHandle(Token[1]);
    Token[1] = 0;
  }
  if ( v5 )
    CEventSystem2::RemoveInternal(*((_QWORD *)this + 2), 1, *((_QWORD *)v2 + 1));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800116d8  mov     r11, rsp
0x1800116db  mov     [r11+10h], rdx
0x1800116df  mov     [r11+8], rcx
0x1800116e3  push    rbx
0x1800116e4  push    rsi
0x1800116e5  push    r12
0x1800116e7  push    r13
0x1800116e9  push    r14
0x1800116eb  push    r15
0x1800116ed  sub     rsp, 78h
0x1800116f1  movaps  [rsp+0A8h+var_48], xmm6
0x1800116f6  mov     r12, rdx
0x1800116f9  mov     rax, rcx
0x1800116fc  mov     qword ptr [r11-70h], 0
0x180011704  xorps   xmm0, xmm0
0x180011707  movups  xmmword ptr [rsp+0A8h+Token], xmm0
0x18001170c  xor     ecx, ecx
0x18001170e  mov     [r11+20h], rcx
0x180011712  xor     r15d, r15d
0x180011715  mov     r14, [rax+10h]
0x180011719  mov     rsi, [rdx+8]
0x18001171d  xor     ebx, ebx
0x18001171f  mov     [rsp+0A8h+var_78], ebx
0x180011723  xorps   xmm6, xmm6
0x180011726  xor     r9d, r9d
0x180011729  mov     [r11-70h], r9
0x18001172d  xor     r13d, r13d
0x180011730  mov     [r11+18h], r13d
0x180011734  mov     byte ptr [rsp+0A8h+Token], bl
0x180011738  mov     [r11-60h], rbx
0x18001173c  cmp     [r14+190h], ebx
0x180011743  jnz     loc_18001192D
0x180011749  lea     rcx, [r14+78h]; this
0x18001174d  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x180011752  mov     rcx, rsi
0x180011755  call    ??$HashKey@PEBG@@YAIPEBG@Z; HashKey<ushort const *>(ushort const *)
0x18001175a  mov     r8, [r14+28h]
0x18001175e  test    r8, r8
0x180011761  jz      loc_180011937
0x180011767  xor     edx, edx
0x180011769  div     dword ptr [r14+30h]
0x18001176d  mov     rdx, [r8+rdx*8]
0x180011771  test    rdx, rdx
0x180011774  jz      short loc_1800117AE
0x180011776  mov     rax, [rdx+10h]
0x18001177a  test    rsi, rsi
0x18001177d  jz      loc_1800118F8
0x180011783  mov     r8, rsi
0x180011786  sub     r8, rax
0x180011789  movzx   ecx, word ptr [rax]
0x18001178c  cmp     cx, [rax+r8]
0x180011791  jnz     short loc_1800117A7
0x180011793  add     rax, 2
0x180011797  test    cx, cx
0x18001179a  jnz     short loc_180011789
0x18001179c  xor     eax, eax
0x18001179e  test    eax, eax
0x1800117a0  jz      short loc_1800117AE
0x1800117a2  mov     rdx, [rdx]
0x1800117a5  jmp     short loc_180011771
0x1800117a7  sbb     eax, eax
0x1800117a9  or      eax, 1
0x1800117ac  jmp     short loc_18001179E
0x1800117ae  test    rdx, rdx
0x1800117b1  jz      loc_180011937
0x1800117b7  movups  xmm6, xmmword ptr [rdx+18h]
0x1800117bb  movups  [rsp+0A8h+var_58], xmm6
0x1800117c0  mov     esi, 1
0x1800117c5  lea     rdx, [rsp+0A8h+Token]; struct SavedImpersonationState *
0x1800117ca  movdqa  xmm0, xmm6
0x1800117ce  psrldq  xmm0, 8
0x1800117d3  movq    rcx, xmm0; Token
0x1800117d8  call    ?ImpersonateOther_Save@@YAJPEAXAEAUSavedImpersonationState@@@Z; ImpersonateOther_Save(void *,SavedImpersonationState &)
0x1800117dd  mov     ebx, eax
0x1800117df  mov     [rsp+0A8h+var_78], eax
0x1800117e3  lea     rcx, [r14+78h]; lpCriticalSection
0x1800117e7  call    cs:__imp_LeaveCriticalSection
0x1800117ed  test    ebx, ebx
0x1800117ef  js      short loc_180011848
0x1800117f1  test    esi, esi
0x1800117f3  jz      loc_18001193E
0x1800117f9  mov     rax, [r14+20h]
0x1800117fd  test    rax, rax
0x180011800  jz      loc_18001190B
0x180011806  mov     rcx, [r14+20h]
0x18001180a  mov     rax, [rcx]
0x18001180d  lea     r9, [rsp+0A8h+var_70]
0x180011812  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x180011819  movd    edx, xmm6
0x18001181d  mov     rax, [rax+28h]
0x180011821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011826  mov     ebx, eax
0x180011828  mov     [rsp+0A8h+var_78], eax
0x18001182c  test    eax, eax
0x18001182e  js      loc_1800118C1
0x180011834  lea     rax, [rsp+0A8h+arg_10]
0x18001183c  movss   dword ptr [rax], xmm6
0x180011840  mov     r13d, [rsp+0A8h+arg_10]
0x180011848  mov     r9, [rsp+0A8h+var_70]
0x18001184d  mov     rcx, [rsp+0A8h+arg_18]
0x180011855  mov     r12, [rsp+0A8h+arg_8]
0x18001185d  test    ebx, ebx
0x18001185f  jnz     short loc_1800118D3
0x180011861  mov     rax, [r9]
0x180011864  lea     r8, [rsp+0A8h+arg_18]
0x18001186c  lea     rdx, qword_180053120
0x180011873  mov     rcx, r9
0x180011876  mov     rax, [rax]
0x180011879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001187e  mov     ecx, eax
0x180011880  test    eax, eax
0x180011882  jns     short loc_1800118A6
0x180011884  add     eax, 7FFFBFFFh
0x180011889  cmp     eax, 1
0x18001188c  ja      loc_18001194C
0x180011892  xor     ecx, ecx
0x180011894  mov     [rsp+0A8h+arg_18], rcx
0x18001189c  mov     r9, [rsp+0A8h+var_70]
0x1800118a1  jmp     loc_180011977
0x1800118a6  mov     rcx, [rsp+0A8h+arg_18]
0x1800118ae  test    rcx, rcx
0x1800118b1  jz      short loc_180011892
0x1800118b3  mov     rax, [rcx]
0x1800118b6  mov     rax, [rax+10h]
0x1800118ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118bf  jmp     short loc_180011892
0x1800118c1  lea     rax, [rsp+0A8h+Token]
0x1800118c6  mov     rcx, rax; struct SavedImpersonationState *
0x1800118c9  call    ?ImpersonateOther_Restore@@YAXAEAUSavedImpersonationState@@@Z; ImpersonateOther_Restore(SavedImpersonationState &)
0x1800118ce  jmp     loc_180011848
0x1800118d3  cmp     ebx, 800706BAh
0x1800118d9  jz      loc_180011971
0x1800118df  cmp     ebx, 80010108h
0x1800118e5  jz      loc_180011971
0x1800118eb  lea     eax, [rbx+7FF8F942h]
0x1800118f1  cmp     eax, 1
0x1800118f4  jbe     short loc_180011971
0x1800118f6  jmp     short loc_180011977
0x1800118f8  cmp     [rax-8], ebx
0x1800118fb  jz      loc_1800117AE
0x180011901  mov     eax, 1
0x180011906  jmp     loc_18001179E
0x18001190b  mov     edx, 47Eh; unsigned int
0x180011910  mov     r9d, 11h; unsigned __int16
0x180011916  mov     r8d, 80001203h; unsigned int
0x18001191c  lea     rcx, aComComplusSrcE_18; "com\\complus\\src\\events\\tier2\\event"...
0x180011923  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180011928  jmp     loc_180011806
0x18001192d  mov     ebx, 80010108h
0x180011932  jmp     loc_18001185D
0x180011937  xor     esi, esi
0x180011939  jmp     loc_1800117E3
0x18001193e  mov     ebx, 1
0x180011943  mov     [rsp+0A8h+var_78], ebx
0x180011947  jmp     loc_180011848
0x18001194c  cmp     ecx, 80070005h
0x180011952  jz      loc_180011892
0x180011958  cmp     ecx, 800706F7h
0x18001195e  jz      loc_180011892
0x180011964  mov     r9, [rsp+0A8h+var_70]
0x180011969  mov     rcx, [rsp+0A8h+arg_18]
0x180011971  mov     r15d, 1
0x180011977  test    r9, r9
0x18001197a  jz      short loc_180011993
0x18001197c  mov     rax, [r9]
0x18001197f  mov     rcx, r9
0x180011982  mov     rax, [rax+10h]
0x180011986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001198b  mov     rcx, [rsp+0A8h+arg_18]
0x180011993  test    rcx, rcx
0x180011996  jnz     short loc_180011A08
0x180011998  cmp     byte ptr [rsp+0A8h+Token], 0
0x18001199d  jz      short loc_1800119B1
0x18001199f  mov     rdx, [rsp+0A8h+Token+8]; Token
0x1800119a4  xor     ecx, ecx; Thread
0x1800119a6  call    cs:__imp_SetThreadToken
0x1800119ac  mov     byte ptr [rsp+0A8h+Token], 0
0x1800119b1  mov     rcx, [rsp+0A8h+Token+8]; hObject
0x1800119b6  test    rcx, rcx
0x1800119b9  jnz     short loc_180011A16
0x1800119bb  test    r15d, r15d
0x1800119be  jz      short loc_1800119F2
0x1800119c0  mov     [rsp+0A8h+arg_10], r13d
0x1800119c8  lea     rax, [rsp+0A8h+arg_10]
0x1800119d0  mov     [rsp+0A8h+var_88], rax
0x1800119d5  xor     r9d, r9d
0x1800119d8  mov     r8, [r12+8]
0x1800119dd  lea     edx, [r9+1]
0x1800119e1  mov     rcx, [rsp+0A8h+arg_0]
0x1800119e9  mov     rcx, [rcx+10h]
0x1800119ed  call    ?RemoveInternal@CEventSystem2@@AEAAJW4__MIDL___MIDL_itf_esstruct_0000_0000_0001@@PEBGHPEAK@Z; CEventSystem2::RemoveInternal(__MIDL___MIDL_itf_esstruct_0000_0000_0001,ushort const *,int,ulong *)
0x1800119f2  mov     eax, ebx
0x1800119f4  movaps  xmm6, [rsp+0A8h+var_48]
0x1800119f9  add     rsp, 78h
0x1800119fd  pop     r15
0x1800119ff  pop     r14
0x180011a01  pop     r13
0x180011a03  pop     r12
0x180011a05  pop     rsi
0x180011a06  pop     rbx
0x180011a07  retn
0x180011a08  mov     rax, [rcx]
0x180011a0b  mov     rax, [rax+10h]
0x180011a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a14  jmp     short loc_180011998
0x180011a16  call    cs:__imp_CloseHandle
0x180011a1c  mov     [rsp+0A8h+Token+8], 0
0x180011a25  jmp     short loc_1800119BB
0x180043f2a  push    rbp
0x180043f2c  sub     rsp, 30h
0x180043f30  mov     rbp, rdx
0x180043f33  mov     rcx, [rbp+38h]
0x180043f37  test    rcx, rcx
0x180043f3a  jz      short loc_180043F49
0x180043f3c  mov     rax, [rcx]
0x180043f3f  mov     rax, [rax+10h]
0x180043f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f48  nop
0x180043f49  mov     rcx, [rbp+0C8h]
0x180043f50  test    rcx, rcx
0x180043f53  jz      short loc_180043F62
0x180043f55  mov     rax, [rcx]
0x180043f58  mov     rax, [rax+10h]
0x180043f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f61  nop
0x180043f62  lea     rcx, [rbp+40h]; struct SavedImpersonationState *
0x180043f66  call    ?ImpersonateOther_Restore@@YAXAEAUSavedImpersonationState@@@Z; ImpersonateOther_Restore(SavedImpersonationState &)
0x180043f6b  nop
0x180043f6c  add     rsp, 30h
0x180043f70  pop     rbp
0x180043f71  retn
```
