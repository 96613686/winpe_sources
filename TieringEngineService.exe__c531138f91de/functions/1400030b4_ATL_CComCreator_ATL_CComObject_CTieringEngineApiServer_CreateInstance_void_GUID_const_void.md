# ATL::CComCreator<ATL::CComObject<CTieringEngineApiServer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1400030b4`
- end: `0x140003215`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTieringEngineApiServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `353`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002dd0`

## callees

- `0x140001a18`
- `0x1400030b4`
- `0x1400035bc`
- `0x140004a40`
- `0x1400380d8`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CTieringEngineApiServer>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CTieringEngineApiServer *v7; // rax
  CTieringEngineApiServer *v8; // rbx
  signed __int32 v9; // eax
  int v10; // eax
  signed __int32 v11; // eax
  CTieringEngineApiServer *v14; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CTieringEngineApiServer *)operator new(0x78u);
    v8 = v7;
    if ( v7 )
    {
      CTieringEngineApiServer::CTieringEngineApiServer(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CTieringEngineApiServer>::`vftable';
      (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v14 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v14;
  }
  if ( v8 )
  {
    do
      v9 = *((_DWORD *)v8 + 2);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 2, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((CTieringEngineApiServer *)((char *)v8 + 16));
    if ( v10 >= 0 )
    {
      *((_BYTE *)v8 + 56) = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
      }
      v10 = 0;
    }
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    do
      v11 = *((_DWORD *)v8 + 2);
    while ( v11 != 0x7FFFFFFF && v11 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 2, v11 - 1, v11) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CTieringEngineApiServer *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CTieringEngineApiServer *, __int64))(*(_QWORD *)v8 + 200LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1400030b4  mov     [rsp+arg_10], r8
0x1400030b9  mov     [rsp+arg_8], rdx
0x1400030be  mov     [rsp+arg_0], rcx
0x1400030c3  push    rbx
0x1400030c4  push    rsi
0x1400030c5  push    rdi
0x1400030c6  push    r14
0x1400030c8  push    r15
0x1400030ca  sub     rsp, 20h
0x1400030ce  mov     rsi, r8
0x1400030d1  mov     r14, rdx
0x1400030d4  test    r8, r8
0x1400030d7  jnz     short loc_1400030E3
0x1400030d9  mov     eax, 80004003h
0x1400030de  jmp     loc_140003209
0x1400030e3  mov     qword ptr [r8], 0
0x1400030ea  mov     edi, 8007000Eh
0x1400030ef  mov     dword ptr [rsp+48h+arg_0], edi
0x1400030f3  mov     [rsp+48h+arg_18], 0
0x1400030fc  mov     ecx, 78h ; 'x'; Size
0x140003101  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003106  mov     rbx, rax
0x140003109  test    rbx, rbx
0x14000310c  jz      short loc_140003133
0x14000310e  mov     rcx, rax; this
0x140003111  call    ??0CTieringEngineApiServer@@QEAA@XZ; CTieringEngineApiServer::CTieringEngineApiServer(void)
0x140003116  lea     rax, ??_7?$CComObject@VCTieringEngineApiServer@@@ATL@@6B@; const ATL::CComObject<CTieringEngineApiServer>::`vftable'
0x14000311d  mov     [rbx], rax
0x140003120  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003127  mov     rax, [rcx]
0x14000312a  mov     rax, [rax+8]
0x14000312e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003133  mov     [rsp+48h+arg_18], rbx
0x140003138  jmp     short loc_14000314D
0x14000313a  mov     rsi, [rsp+48h+arg_10]
0x14000313f  mov     r14, [rsp+48h+arg_8]
0x140003144  mov     edi, dword ptr [rsp+48h+arg_0]
0x140003148  mov     rbx, [rsp+48h+arg_18]
0x14000314d  test    rbx, rbx
0x140003150  jz      loc_140003207
0x140003156  mov     r15d, 7FFFFFFFh
0x14000315c  jmp     short loc_140003168
0x14000315e  lea     ecx, [rax+1]
0x140003161  lock cmpxchg [rbx+8], ecx
0x140003166  jz      short loc_140003170
0x140003168  mov     eax, [rbx+8]
0x14000316b  cmp     eax, r15d
0x14000316e  jnz     short loc_14000315E
0x140003170  lea     rcx, [rbx+10h]; this
0x140003174  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140003179  test    eax, eax
0x14000317b  js      short loc_1400031B7
0x14000317d  mov     byte ptr [rbx+38h], 1
0x140003181  lea     rax, WPP_GLOBAL_Control
0x140003188  mov     rcx, cs:WPP_GLOBAL_Control
0x14000318f  cmp     rcx, rax
0x140003192  jz      short loc_1400031B5
0x140003194  test    byte ptr [rcx+1Ch], 1
0x140003198  jz      short loc_1400031B5
0x14000319a  cmp     byte ptr [rcx+19h], 4
0x14000319e  jb      short loc_1400031B5
0x1400031a0  mov     edx, 0Ah
0x1400031a5  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x1400031ac  mov     rcx, [rcx+10h]
0x1400031b0  call    WPP_SF_
0x1400031b5  xor     eax, eax
0x1400031b7  xor     edi, edi
0x1400031b9  test    eax, eax
0x1400031bb  cmovs   edi, eax
0x1400031be  jmp     short loc_1400031CA
0x1400031c0  lea     ecx, [rax-1]
0x1400031c3  lock cmpxchg [rbx+8], ecx
0x1400031c8  jz      short loc_1400031D2
0x1400031ca  mov     eax, [rbx+8]
0x1400031cd  cmp     eax, r15d
0x1400031d0  jnz     short loc_1400031C0
0x1400031d2  test    edi, edi
0x1400031d4  jnz     short loc_1400031F0
0x1400031d6  mov     rax, [rbx]
0x1400031d9  mov     r8, rsi
0x1400031dc  mov     rdx, r14
0x1400031df  mov     rcx, rbx
0x1400031e2  mov     rax, [rax]
0x1400031e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031ea  mov     edi, eax
0x1400031ec  test    eax, eax
0x1400031ee  jz      short loc_140003207
0x1400031f0  mov     r8, [rbx]
0x1400031f3  mov     edx, 1
0x1400031f8  mov     rcx, rbx
0x1400031fb  mov     rax, [r8+0C8h]
0x140003202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003207  mov     eax, edi
0x140003209  add     rsp, 20h
0x14000320d  pop     r15
0x14000320f  pop     r14
0x140003211  pop     rdi
0x140003212  pop     rsi
0x140003213  pop     rbx
0x140003214  retn
```
