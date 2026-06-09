# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180023434`
- end: `0x180023506`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180022ea4`
- `0x180023434`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CElfImageEventTraceExtender *)operator new(0x50u);
    Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, __int64))(*(_QWORD *)v5 + 160LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180023434  mov     [rsp+arg_10], r8
0x180023439  mov     [rsp+arg_8], rdx
0x18002343e  mov     [rsp+arg_0], rcx
0x180023443  push    rbx
0x180023444  push    rsi
0x180023445  push    rdi
0x180023446  sub     rsp, 20h
0x18002344a  mov     rdi, r8
0x18002344d  test    r8, r8
0x180023450  jnz     short loc_18002345C
0x180023452  mov     eax, 80004003h
0x180023457  jmp     loc_1800234FE
0x18002345c  mov     qword ptr [r8], 0
0x180023463  mov     esi, 8007000Eh
0x180023468  mov     dword ptr [rsp+38h+arg_8], esi
0x18002346c  mov     [rsp+38h+arg_0], 0
0x180023475  mov     ecx, 50h ; 'P'; Size
0x18002347a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002347f  mov     rbx, rax
0x180023482  mov     [rsp+38h+arg_18], rax
0x180023487  mov     rcx, rax; this
0x18002348a  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x18002348f  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180023496  mov     [rbx], rax
0x180023499  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800234a0  mov     rax, [rcx]
0x1800234a3  mov     rax, [rax+8]
0x1800234a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ac  nop
0x1800234ad  mov     [rsp+38h+arg_0], rbx
0x1800234b2  jmp     short loc_1800234C2
0x1800234b4  mov     rdi, [rsp+38h+arg_10]
0x1800234b9  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800234bd  mov     rbx, [rsp+38h+arg_0]
0x1800234c2  test    rbx, rbx
0x1800234c5  jz      short loc_1800234FC
0x1800234c7  mov     rax, [rbx]
0x1800234ca  mov     r8, rdi
0x1800234cd  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800234d4  mov     rcx, rbx
0x1800234d7  mov     rax, [rax]
0x1800234da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234df  mov     esi, eax
0x1800234e1  test    eax, eax
0x1800234e3  jz      short loc_1800234FC
0x1800234e5  mov     rdx, [rbx]
0x1800234e8  mov     rax, [rdx+0A0h]
0x1800234ef  mov     edx, 1
0x1800234f4  mov     rcx, rbx
0x1800234f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234fc  mov     eax, esi
0x1800234fe  add     rsp, 20h
0x180023502  pop     rdi
0x180023503  pop     rsi
0x180023504  pop     rbx
0x180023505  retn
```
