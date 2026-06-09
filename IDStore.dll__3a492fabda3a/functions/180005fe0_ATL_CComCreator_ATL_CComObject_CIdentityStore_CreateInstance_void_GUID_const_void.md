# ATL::CComCreator<ATL::CComObject<CIdentityStore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005fe0`
- end: `0x18000622a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIdentityStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `586`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005fb0`

## callees

- `0x180005fe0`
- `0x180006230`
- `0x180006260`
- `0x18000f088`
- `0x18001448c`
- `0x1800191ac`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIdentityStore>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  CIdentityProfileHandler *v7; // rcx
  signed __int32 i; // eax
  int v9; // eax
  unsigned int v10; // edi
  signed __int32 j; // eax
  __int64 v13; // r8

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v10 = -2147024882;
    v5 = operator new(0x90u);
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v10 = -2147024882;
    v6 = 0;
    goto LABEL_14;
  }
  v6 = v5;
  if ( v5 )
  {
    v5[6] = 0;
    *((_OWORD *)v5 + 2) = 0;
    *((_OWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 8) = 0;
    *((_BYTE *)v5 + 72) = 0;
    *((_QWORD *)v5 + 12) = -1;
    *((_QWORD *)v5 + 14) = 0;
    *((_QWORD *)v5 + 15) = 0;
    *((_BYTE *)v5 + 88) = 0;
    *((_QWORD *)v5 + 13) = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_26bbe41ed1573859b2bf32c7137c1e46_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
        WPP_SF_s(*((_QWORD *)v7 + 2), 10, v13, "CIdentityStore::CIdentityStore");
    }
    v6[20] = 0;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v13, "CIdentityStore::CIdentityStore");
    }
    *(_QWORD *)v6 = &ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore2'};
    *((_QWORD *)v6 + 2) = &ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStoreEx'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v6 = 0;
  }
LABEL_14:
  if ( v6 )
  {
    for ( i = v6[6]; i != 0x7FFFFFFF; i = v6[6] )
    {
      if ( i == _InterlockedCompareExchange(v6 + 6, i + 1, i) )
        break;
    }
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v6 + 8));
    if ( v9 >= 0 )
    {
      *((_BYTE *)v6 + 72) = 1;
      *((_QWORD *)v6 + 17) = 0;
      v9 = CIdentityProviderReg::Initialize((CIdentityProviderReg *)(v6 + 22));
    }
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    for ( j = v6[6]; j != 0x7FFFFFFF; j = v6[6] )
    {
      if ( j == _InterlockedCompareExchange(v6 + 6, j - 1, j) )
        break;
    }
    if ( v10 || (v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v6)(v6, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v6 + 72LL))(v6, 1);
  }
  return v10;
}

```

## disassembly

```asm
0x180005fe0  mov     [rsp+arg_10], r8
0x180005fe5  mov     [rsp+arg_8], rdx
0x180005fea  mov     [rsp+arg_0], rcx
0x180005fef  push    rbx
0x180005ff0  push    rsi
0x180005ff1  push    rdi
0x180005ff2  push    r12
0x180005ff4  push    r14
0x180005ff6  push    r15
0x180005ff8  sub     rsp, 28h
0x180005ffc  mov     r14, r8
0x180005fff  mov     r15, rdx
0x180006002  test    r8, r8
0x180006005  jz      loc_180006172
0x18000600b  xor     esi, esi
0x18000600d  mov     [r8], rsi
0x180006010  mov     edi, 8007000Eh
0x180006015  mov     dword ptr [rsp+58h+arg_0], edi
0x180006019  mov     [rsp+58h+arg_18], rsi
0x18000601e  mov     ecx, 90h; Size
0x180006023  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006028  mov     rbx, rax
0x18000602b  test    rax, rax
0x18000602e  jz      loc_1800061CE
0x180006034  mov     [rax+18h], esi
0x180006037  xorps   xmm0, xmm0
0x18000603a  xor     eax, eax
0x18000603c  movups  xmmword ptr [rbx+20h], xmm0
0x180006040  movups  xmmword ptr [rbx+30h], xmm0
0x180006044  mov     [rbx+40h], rax
0x180006048  mov     [rbx+48h], al
0x18000604b  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x180006053  mov     [rbx+70h], rsi
0x180006057  mov     [rbx+78h], rsi
0x18000605b  mov     [rbx+58h], al
0x18000605e  mov     [rbx+68h], rax
0x180006062  lea     r12, WPP_GLOBAL_Control
0x180006069  mov     rcx, cs:WPP_GLOBAL_Control
0x180006070  cmp     rcx, r12
0x180006073  jz      short loc_180006091
0x180006075  test    byte ptr [rcx+1Ch], 10h
0x180006079  jnz     loc_180006179
0x18000607f  cmp     rcx, r12
0x180006082  jz      short loc_180006091
0x180006084  test    dword ptr [rcx+1Ch], 400h
0x18000608b  jnz     loc_18000619A
0x180006091  mov     [rbx+50h], esi
0x180006094  mov     rcx, cs:WPP_GLOBAL_Control
0x18000609b  cmp     rcx, r12
0x18000609e  jz      short loc_1800060AD
0x1800060a0  test    dword ptr [rcx+1Ch], 400h
0x1800060a7  jnz     loc_1800061B4
0x1800060ad  lea     rax, ??_7?$CComObject@VCIdentityStore@@@ATL@@6BIIdentityStore@@@; const ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore'}
0x1800060b4  mov     [rbx], rax
0x1800060b7  lea     rax, ??_7?$CComObject@VCIdentityStore@@@ATL@@6BIIdentityStore2@@@; const ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore2'}
0x1800060be  mov     [rbx+8], rax
0x1800060c2  lea     rax, ??_7?$CComObject@VCIdentityStore@@@ATL@@6BIIdentityStoreEx@@@; const ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStoreEx'}
0x1800060c9  mov     [rbx+10h], rax
0x1800060cd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060d4  mov     rax, [rcx]
0x1800060d7  mov     rax, [rax+8]
0x1800060db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e0  mov     [rsp+58h+arg_18], rbx
0x1800060e5  test    rbx, rbx
0x1800060e8  jz      short loc_18000614C
0x1800060ea  mov     eax, [rbx+18h]
0x1800060ed  cmp     eax, 7FFFFFFFh
0x1800060f2  jnz     loc_1800061F0
0x1800060f8  lea     rcx, [rbx+20h]; this
0x1800060fc  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006101  test    eax, eax
0x180006103  js      short loc_180006119
0x180006105  mov     byte ptr [rbx+48h], 1
0x180006109  mov     [rbx+88h], rsi
0x180006110  lea     rcx, [rbx+58h]; this
0x180006114  call    ?Initialize@CIdentityProviderReg@@QEAAJXZ; CIdentityProviderReg::Initialize(void)
0x180006119  mov     edi, esi
0x18000611b  test    eax, eax
0x18000611d  cmovs   edi, eax
0x180006120  mov     eax, [rbx+18h]
0x180006123  cmp     eax, 7FFFFFFFh
0x180006128  jnz     loc_18000620D
0x18000612e  test    edi, edi
0x180006130  jnz     short loc_18000615C
0x180006132  mov     rax, [rbx]
0x180006135  mov     r8, r14
0x180006138  mov     rdx, r15
0x18000613b  mov     rcx, rbx
0x18000613e  mov     rax, [rax]
0x180006141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006146  mov     edi, eax
0x180006148  test    eax, eax
0x18000614a  jnz     short loc_18000615C
0x18000614c  mov     eax, edi
0x18000614e  add     rsp, 28h
0x180006152  pop     r15
0x180006154  pop     r14
0x180006156  pop     r12
0x180006158  pop     rdi
0x180006159  pop     rsi
0x18000615a  pop     rbx
0x18000615b  retn
0x18000615c  mov     rcx, [rbx]
0x18000615f  mov     rax, [rcx+48h]
0x180006163  mov     edx, 1
0x180006168  mov     rcx, rbx
0x18000616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006170  jmp     short loc_18000614C
0x180006172  mov     eax, 80004003h
0x180006177  jmp     short loc_18000614E
0x180006179  mov     edx, 0Ah
0x18000617e  lea     r8, WPP_26bbe41ed1573859b2bf32c7137c1e46_Traceguids
0x180006185  mov     rcx, [rcx+10h]
0x180006189  call    WPP_SF_
0x18000618e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006195  jmp     loc_18000607F
0x18000619a  mov     edx, 0Ah
0x18000619f  lea     r9, aCidentitystore_9; "CIdentityStore::CIdentityStore"
0x1800061a6  mov     rcx, [rcx+10h]
0x1800061aa  call    WPP_SF_s
0x1800061af  jmp     loc_180006091
0x1800061b4  mov     edx, 0Ch
0x1800061b9  lea     r9, aCidentitystore_9; "CIdentityStore::CIdentityStore"
0x1800061c0  mov     rcx, [rcx+10h]
0x1800061c4  call    WPP_SF_s
0x1800061c9  jmp     loc_1800060AD
0x1800061ce  mov     rbx, rsi
0x1800061d1  jmp     loc_1800060E0
0x1800061d6  xor     esi, esi
0x1800061d8  mov     r14, [rsp+58h+arg_10]
0x1800061dd  mov     r15, [rsp+58h+arg_8]
0x1800061e2  mov     edi, dword ptr [rsp+58h+arg_0]
0x1800061e6  mov     rbx, [rsp+58h+arg_18]
0x1800061eb  jmp     loc_1800060E5
0x1800061f0  lea     ecx, [rax+1]
0x1800061f3  lock cmpxchg [rbx+18h], ecx
0x1800061f8  jz      loc_1800060F8
0x1800061fe  mov     eax, [rbx+18h]
0x180006201  cmp     eax, 7FFFFFFFh
0x180006206  jnz     short loc_1800061F0
0x180006208  jmp     loc_1800060F8
0x18000620d  lea     ecx, [rax-1]
0x180006210  lock cmpxchg [rbx+18h], ecx
0x180006215  jz      loc_18000612E
0x18000621b  mov     eax, [rbx+18h]
0x18000621e  cmp     eax, 7FFFFFFFh
0x180006223  jnz     short loc_18000620D
0x180006225  jmp     loc_18000612E
```
