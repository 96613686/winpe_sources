# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002f2e4`
- end: `0x18002f3b6`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ccc`

## callees

- `0x180001b84`
- `0x18002f00c`
- `0x18002f2e4`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CWinSATEventTraceExtender *)operator new(0x68u);
    Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v7 = v5;
  }
  catch ( ... )
  {
    v3 = a3;
    v6 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18002f2e4  mov     [rsp+arg_10], r8
0x18002f2e9  mov     [rsp+arg_8], rdx
0x18002f2ee  mov     [rsp+arg_0], rcx
0x18002f2f3  push    rbx
0x18002f2f4  push    rsi
0x18002f2f5  push    rdi
0x18002f2f6  sub     rsp, 20h
0x18002f2fa  mov     rdi, r8
0x18002f2fd  test    r8, r8
0x18002f300  jnz     short loc_18002F30C
0x18002f302  mov     eax, 80004003h
0x18002f307  jmp     loc_18002F3AE
0x18002f30c  mov     qword ptr [r8], 0
0x18002f313  mov     esi, 8007000Eh
0x18002f318  mov     dword ptr [rsp+38h+arg_8], esi
0x18002f31c  mov     [rsp+38h+arg_0], 0
0x18002f325  mov     ecx, 68h ; 'h'; Size
0x18002f32a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f32f  mov     rbx, rax
0x18002f332  mov     [rsp+38h+arg_18], rax
0x18002f337  mov     rcx, rax; this
0x18002f33a  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x18002f33f  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18002f346  mov     [rbx], rax
0x18002f349  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002f350  mov     rax, [rcx]
0x18002f353  mov     rax, [rax+8]
0x18002f357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f35c  nop
0x18002f35d  mov     [rsp+38h+arg_0], rbx
0x18002f362  jmp     short loc_18002F372
0x18002f364  mov     rdi, [rsp+38h+arg_10]
0x18002f369  mov     esi, dword ptr [rsp+38h+arg_8]
0x18002f36d  mov     rbx, [rsp+38h+arg_0]
0x18002f372  test    rbx, rbx
0x18002f375  jz      short loc_18002F3AC
0x18002f377  mov     rax, [rbx]
0x18002f37a  mov     r8, rdi
0x18002f37d  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002f384  mov     rcx, rbx
0x18002f387  mov     rax, [rax]
0x18002f38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f38f  mov     esi, eax
0x18002f391  test    eax, eax
0x18002f393  jz      short loc_18002F3AC
0x18002f395  mov     rdx, [rbx]
0x18002f398  mov     rax, [rdx+88h]
0x18002f39f  mov     edx, 1
0x18002f3a4  mov     rcx, rbx
0x18002f3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ac  mov     eax, esi
0x18002f3ae  add     rsp, 20h
0x18002f3b2  pop     rdi
0x18002f3b3  pop     rsi
0x18002f3b4  pop     rbx
0x18002f3b5  retn
```
