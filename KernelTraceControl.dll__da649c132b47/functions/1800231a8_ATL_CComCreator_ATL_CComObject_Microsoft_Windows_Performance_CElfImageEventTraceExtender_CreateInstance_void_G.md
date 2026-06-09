# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800231a8`
- end: `0x180023285`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x1800231a8`
- `0x1800248a4`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (Microsoft::Windows::Performance::CElfImageEventTraceExtender *)operator new(0x68u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v8 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v8;
  }
  if ( v7 )
  {
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, __int64))(*(_QWORD *)v7 + 160LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x1800231a8  mov     rax, rsp
0x1800231ab  mov     [rax+18h], r8
0x1800231af  mov     [rax+10h], rdx
0x1800231b3  mov     [rax+8], rcx
0x1800231b7  push    rbx
0x1800231b8  push    rsi
0x1800231b9  push    rdi
0x1800231ba  sub     rsp, 30h
0x1800231be  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800231c6  mov     rdi, r8
0x1800231c9  test    r8, r8
0x1800231cc  jnz     short loc_1800231D8
0x1800231ce  mov     eax, 80004003h
0x1800231d3  jmp     loc_18002327D
0x1800231d8  and     qword ptr [r8], 0
0x1800231dc  mov     esi, 8007000Eh
0x1800231e1  mov     [rsp+48h+arg_8], esi
0x1800231e5  and     [rsp+48h+arg_0], 0
0x1800231eb  mov     ecx, 68h ; 'h'; Size
0x1800231f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800231f5  mov     rbx, rax
0x1800231f8  mov     [rsp+48h+arg_18], rax
0x1800231fd  test    rbx, rbx
0x180023200  jz      short loc_18002322A
0x180023202  mov     rcx, rax; this
0x180023205  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x18002320a  nop
0x18002320b  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180023212  mov     [rbx], rax
0x180023215  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002321c  mov     rax, [rcx]
0x18002321f  mov     rax, [rax+8]
0x180023223  call    cs:__guard_dispatch_icall_fptr
0x180023229  nop
0x18002322a  mov     [rsp+48h+arg_0], rbx
0x18002322f  jmp     short loc_18002323F
0x180023231  mov     rdi, [rsp+48h+arg_10]
0x180023236  mov     esi, [rsp+48h+arg_8]
0x18002323a  mov     rbx, [rsp+48h+arg_0]
0x18002323f  test    rbx, rbx
0x180023242  jz      short loc_18002327B
0x180023244  mov     rax, [rbx]
0x180023247  mov     r8, rdi
0x18002324a  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180023251  mov     rcx, rbx
0x180023254  mov     rax, [rax]
0x180023257  call    cs:__guard_dispatch_icall_fptr
0x18002325d  mov     esi, eax
0x18002325f  test    eax, eax
0x180023261  jz      short loc_18002327B
0x180023263  mov     rdx, [rbx]
0x180023266  mov     rax, [rdx+0A0h]
0x18002326d  mov     edx, 1
0x180023272  mov     rcx, rbx
0x180023275  call    cs:__guard_dispatch_icall_fptr
0x18002327b  mov     eax, esi
0x18002327d  add     rsp, 30h
0x180023281  pop     rdi
0x180023282  pop     rsi
0x180023283  pop     rbx
0x180023284  retn
```
