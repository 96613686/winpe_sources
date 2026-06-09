# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001ea44`
- end: `0x18001eb21`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000447c`

## callees

- `0x18001defc`
- `0x18001ea44`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (Microsoft::Windows::Performance::CWinSATEventTraceExtender *)operator new(0x68u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x18001ea44  mov     rax, rsp
0x18001ea47  mov     [rax+18h], r8
0x18001ea4b  mov     [rax+10h], rdx
0x18001ea4f  mov     [rax+8], rcx
0x18001ea53  push    rbx
0x18001ea54  push    rsi
0x18001ea55  push    rdi
0x18001ea56  sub     rsp, 30h
0x18001ea5a  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001ea62  mov     rdi, r8
0x18001ea65  test    r8, r8
0x18001ea68  jnz     short loc_18001EA74
0x18001ea6a  mov     eax, 80004003h
0x18001ea6f  jmp     loc_18001EB19
0x18001ea74  and     qword ptr [r8], 0
0x18001ea78  mov     esi, 8007000Eh
0x18001ea7d  mov     [rsp+48h+arg_8], esi
0x18001ea81  and     [rsp+48h+arg_0], 0
0x18001ea87  mov     ecx, 68h ; 'h'; Size
0x18001ea8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea91  mov     rbx, rax
0x18001ea94  mov     [rsp+48h+arg_18], rax
0x18001ea99  test    rbx, rbx
0x18001ea9c  jz      short loc_18001EAC6
0x18001ea9e  mov     rcx, rax; this
0x18001eaa1  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x18001eaa6  nop
0x18001eaa7  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18001eaae  mov     [rbx], rax
0x18001eab1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001eab8  mov     rax, [rcx]
0x18001eabb  mov     rax, [rax+8]
0x18001eabf  call    cs:__guard_dispatch_icall_fptr
0x18001eac5  nop
0x18001eac6  mov     [rsp+48h+arg_0], rbx
0x18001eacb  jmp     short loc_18001EADB
0x18001eacd  mov     rdi, [rsp+48h+arg_10]
0x18001ead2  mov     esi, [rsp+48h+arg_8]
0x18001ead6  mov     rbx, [rsp+48h+arg_0]
0x18001eadb  test    rbx, rbx
0x18001eade  jz      short loc_18001EB17
0x18001eae0  mov     rax, [rbx]
0x18001eae3  mov     r8, rdi
0x18001eae6  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001eaed  mov     rcx, rbx
0x18001eaf0  mov     rax, [rax]
0x18001eaf3  call    cs:__guard_dispatch_icall_fptr
0x18001eaf9  mov     esi, eax
0x18001eafb  test    eax, eax
0x18001eafd  jz      short loc_18001EB17
0x18001eaff  mov     rdx, [rbx]
0x18001eb02  mov     rax, [rdx+88h]
0x18001eb09  mov     edx, 1
0x18001eb0e  mov     rcx, rbx
0x18001eb11  call    cs:__guard_dispatch_icall_fptr
0x18001eb17  mov     eax, esi
0x18001eb19  add     rsp, 30h
0x18001eb1d  pop     rdi
0x18001eb1e  pop     rsi
0x18001eb1f  pop     rbx
0x18001eb20  retn
```
