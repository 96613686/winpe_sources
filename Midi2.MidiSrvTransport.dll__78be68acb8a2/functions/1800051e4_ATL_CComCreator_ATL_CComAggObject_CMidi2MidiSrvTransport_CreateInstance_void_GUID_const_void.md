# ATL::CComCreator<ATL::CComAggObject<CMidi2MidiSrvTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800051e4`
- end: `0x1800052ec`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800051d0`

## callees

- `0x1800024c0`
- `0x1800051e4`
- `0x1800062c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2MidiSrvTransport>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v7; // rbx
  int v8; // edi
  char *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = (char *)operator new(0x58u);
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2MidiSrvTransport>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2MidiSrvTransport>::`vftable';
    *((_QWORD *)v7 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
    if ( v8 < 0 || (v7[80] = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800051e4  mov     [rsp+arg_10], r8
0x1800051e9  mov     [rsp+arg_8], rdx
0x1800051ee  push    rbx
0x1800051ef  push    rsi
0x1800051f0  push    rdi
0x1800051f1  push    r14
0x1800051f3  push    r15
0x1800051f5  sub     rsp, 30h
0x1800051f9  mov     rsi, r8
0x1800051fc  mov     r14, rdx
0x1800051ff  mov     r15, rcx
0x180005202  test    r8, r8
0x180005205  jnz     short loc_180005211
0x180005207  mov     eax, 80004003h
0x18000520c  jmp     loc_1800052E0
0x180005211  mov     qword ptr [r8], 0
0x180005218  mov     edi, 8007000Eh
0x18000521d  mov     [rsp+58h+arg_18], edi
0x180005221  mov     [rsp+58h+var_38], 0
0x18000522a  mov     ecx, 58h ; 'X'; Size
0x18000522f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005234  mov     rbx, rax
0x180005237  mov     dword ptr [rax+8], 0
0x18000523e  lea     rax, ??_7?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2MidiSrvTransport>::`vftable'
0x180005245  mov     [rbx], rax
0x180005248  xorps   xmm0, xmm0
0x18000524b  xor     eax, eax
0x18000524d  movups  xmmword ptr [rbx+28h], xmm0
0x180005251  movups  xmmword ptr [rbx+38h], xmm0
0x180005255  mov     [rbx+48h], rax
0x180005259  mov     [rbx+50h], al
0x18000525c  lea     rax, ??_7?$CComContainedObject@VCMidi2MidiSrvTransport@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2MidiSrvTransport>::`vftable'
0x180005263  mov     [rbx+18h], rax
0x180005267  mov     [rbx+20h], r15
0x18000526b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005272  mov     rax, [rcx]
0x180005275  mov     rax, [rax+8]
0x180005279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000527e  mov     [rsp+58h+var_38], rbx
0x180005283  jmp     short loc_180005298
0x180005285  mov     rsi, [rsp+58h+arg_10]
0x18000528a  mov     r14, [rsp+58h+arg_8]
0x18000528f  mov     edi, [rsp+58h+arg_18]
0x180005293  mov     rbx, [rsp+58h+var_38]
0x180005298  test    rbx, rbx
0x18000529b  jz      short loc_1800052DE
0x18000529d  lea     rcx, [rbx+28h]; this
0x1800052a1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800052a6  mov     edi, eax
0x1800052a8  test    eax, eax
0x1800052aa  js      short loc_1800052CA
0x1800052ac  mov     byte ptr [rbx+50h], 1
0x1800052b0  mov     rax, [rbx]
0x1800052b3  mov     r8, rsi
0x1800052b6  mov     rdx, r14
0x1800052b9  mov     rcx, rbx
0x1800052bc  mov     rax, [rax]
0x1800052bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c4  mov     edi, eax
0x1800052c6  test    eax, eax
0x1800052c8  jz      short loc_1800052DE
0x1800052ca  mov     rax, [rbx]
0x1800052cd  mov     edx, 1
0x1800052d2  mov     rcx, rbx
0x1800052d5  mov     rax, [rax+18h]
0x1800052d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052de  mov     eax, edi
0x1800052e0  add     rsp, 30h
0x1800052e4  pop     r15
0x1800052e6  pop     r14
0x1800052e8  pop     rdi
0x1800052e9  pop     rsi
0x1800052ea  pop     rbx
0x1800052eb  retn
```
