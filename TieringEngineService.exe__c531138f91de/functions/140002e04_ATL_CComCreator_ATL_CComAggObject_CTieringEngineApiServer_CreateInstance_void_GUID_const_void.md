# ATL::CComCreator<ATL::CComAggObject<CTieringEngineApiServer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140002e04`
- end: `0x140002f4f`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCTieringEngineApiServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002dd0`

## callees

- `0x140001a18`
- `0x140002e04`
- `0x1400035bc`
- `0x140004a40`
- `0x1400380d8`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CTieringEngineApiServer>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  int v7; // esi
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  int v10; // eax
  _DWORD *v11; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x90u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CTieringEngineApiServer>::`vftable';
      CTieringEngineApiServer::CTieringEngineApiServer((CTieringEngineApiServer *)(v8 + 6));
      *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CTieringEngineApiServer>::`vftable';
      *((_QWORD *)v9 + 4) = a1;
      (*(void (__fastcall **)(CTieringEngineService *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 10));
    if ( v10 >= 0 )
      *((_BYTE *)v9 + 80) = 1;
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 < 0 )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_679b317bfb4035ff28fff86d621cec42_Traceguids);
    }
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3);
    if ( v7 )
LABEL_17:
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140002e04  mov     [rsp+arg_0], rbx
0x140002e09  mov     [rsp+arg_10], r8
0x140002e0e  mov     [rsp+arg_8], rdx
0x140002e13  push    rsi
0x140002e14  push    rdi
0x140002e15  push    r12
0x140002e17  push    r14
0x140002e19  push    r15
0x140002e1b  sub     rsp, 30h
0x140002e1f  mov     r14, r8
0x140002e22  mov     r15, rdx
0x140002e25  mov     r12, rcx
0x140002e28  test    r8, r8
0x140002e2b  jnz     short loc_140002E37
0x140002e2d  mov     eax, 80004003h
0x140002e32  jmp     loc_140002F3D
0x140002e37  mov     qword ptr [r8], 0
0x140002e3e  mov     esi, 8007000Eh
0x140002e43  mov     [rsp+58h+arg_18], esi
0x140002e47  mov     [rsp+58h+var_38], 0
0x140002e50  mov     ecx, 90h; Size
0x140002e55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002e5a  mov     rdi, rax
0x140002e5d  test    rdi, rdi
0x140002e60  jz      short loc_140002E9E
0x140002e62  mov     dword ptr [rax+8], 0
0x140002e69  lea     rax, ??_7?$CComAggObject@VCTieringEngineApiServer@@@ATL@@6B@; const ATL::CComAggObject<CTieringEngineApiServer>::`vftable'
0x140002e70  mov     [rdi], rax
0x140002e73  lea     rcx, [rdi+18h]; this
0x140002e77  call    ??0CTieringEngineApiServer@@QEAA@XZ; CTieringEngineApiServer::CTieringEngineApiServer(void)
0x140002e7c  lea     rax, ??_7?$CComContainedObject@VCTieringEngineApiServer@@@ATL@@6B@; const ATL::CComContainedObject<CTieringEngineApiServer>::`vftable'
0x140002e83  mov     [rdi+18h], rax
0x140002e87  mov     [rdi+20h], r12
0x140002e8b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002e92  mov     rax, [rcx]
0x140002e95  mov     rax, [rax+8]
0x140002e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e9e  mov     [rsp+58h+var_38], rdi
0x140002ea3  jmp     short loc_140002EB8
0x140002ea5  mov     r14, [rsp+58h+arg_10]
0x140002eaa  mov     r15, [rsp+58h+arg_8]
0x140002eaf  mov     esi, [rsp+58h+arg_18]
0x140002eb3  mov     rdi, [rsp+58h+var_38]
0x140002eb8  test    rdi, rdi
0x140002ebb  jz      short loc_140002F3B
0x140002ebd  lea     rcx, [rdi+28h]; this
0x140002ec1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140002ec6  test    eax, eax
0x140002ec8  js      short loc_140002ECE
0x140002eca  mov     byte ptr [rdi+50h], 1
0x140002ece  xor     esi, esi
0x140002ed0  test    eax, eax
0x140002ed2  cmovs   esi, eax
0x140002ed5  test    esi, esi
0x140002ed7  js      short loc_140002F27
0x140002ed9  lea     rax, WPP_GLOBAL_Control
0x140002ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ee7  cmp     rcx, rax
0x140002eea  jz      short loc_140002F0D
0x140002eec  test    byte ptr [rcx+1Ch], 1
0x140002ef0  jz      short loc_140002F0D
0x140002ef2  cmp     byte ptr [rcx+19h], 4
0x140002ef6  jb      short loc_140002F0D
0x140002ef8  mov     edx, 0Ah
0x140002efd  lea     r8, WPP_679b317bfb4035ff28fff86d621cec42_Traceguids
0x140002f04  mov     rcx, [rcx+10h]
0x140002f08  call    WPP_SF_
0x140002f0d  mov     rax, [rdi]
0x140002f10  mov     r8, r14
0x140002f13  mov     rdx, r15
0x140002f16  mov     rcx, rdi
0x140002f19  mov     rax, [rax]
0x140002f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f21  mov     esi, eax
0x140002f23  test    eax, eax
0x140002f25  jz      short loc_140002F3B
0x140002f27  mov     r8, [rdi]
0x140002f2a  mov     edx, 1
0x140002f2f  mov     rcx, rdi
0x140002f32  mov     rax, [r8+18h]
0x140002f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f3b  mov     eax, esi
0x140002f3d  mov     rbx, [rsp+58h+arg_0]
0x140002f42  add     rsp, 30h
0x140002f46  pop     r15
0x140002f48  pop     r14
0x140002f4a  pop     r12
0x140002f4c  pop     rdi
0x140002f4d  pop     rsi
0x140002f4e  retn
```
