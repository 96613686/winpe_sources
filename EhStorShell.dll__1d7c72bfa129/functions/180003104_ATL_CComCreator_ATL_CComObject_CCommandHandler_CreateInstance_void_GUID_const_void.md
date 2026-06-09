# ATL::CComCreator<ATL::CComObject<CCommandHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003104`
- end: `0x1800031d7`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCommandHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a860`

## callees

- `0x180003104`
- `0x1800031e0`
- `0x180006b8c`
- `0x18000a624`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CCommandHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rbx
  _DWORD *v9; // rcx
  __int64 v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x58u);
    if ( v7 )
      v8 = ATL::CComObject<CCommandHandler>::CComObject<CCommandHandler>((__int64)v7);
    else
      v8 = 0;
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(v8 + 32);
    if ( *v9 != 0x7FFFFFFF )
      --*v9;
    v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003104  mov     [rsp+arg_10], r8
0x180003109  mov     [rsp+arg_8], rdx
0x18000310e  mov     [rsp+arg_0], rcx
0x180003113  push    rbx
0x180003114  push    rsi
0x180003115  push    rdi
0x180003116  push    r14
0x180003118  sub     rsp, 28h
0x18000311c  mov     rsi, r8
0x18000311f  mov     r14, rdx
0x180003122  test    r8, r8
0x180003125  jnz     short loc_180003131
0x180003127  mov     eax, 80004003h
0x18000312c  jmp     loc_1800031CD
0x180003131  mov     qword ptr [r8], 0
0x180003138  mov     edi, 8007000Eh
0x18000313d  mov     dword ptr [rsp+48h+arg_0], edi
0x180003141  mov     [rsp+48h+arg_18], 0
0x18000314a  mov     ecx, 58h ; 'X'; Size
0x18000314f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003154  test    rax, rax
0x180003157  jz      short loc_180003166
0x180003159  mov     rcx, rax
0x18000315c  call    ??0?$CComObject@VCCommandHandler@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CCommandHandler>::CComObject<CCommandHandler>(void *)
0x180003161  mov     rbx, rax
0x180003164  jmp     short loc_180003168
0x180003166  xor     ebx, ebx
0x180003168  mov     [rsp+48h+arg_18], rbx
0x18000316d  jmp     short loc_180003182
0x18000316f  mov     rsi, [rsp+48h+arg_10]
0x180003174  mov     r14, [rsp+48h+arg_8]
0x180003179  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000317d  mov     rbx, [rsp+48h+arg_18]
0x180003182  test    rbx, rbx
0x180003185  jz      short loc_1800031CB
0x180003187  lea     rcx, [rbx+20h]
0x18000318b  call    ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
0x180003190  mov     eax, [rcx]
0x180003192  cmp     eax, 7FFFFFFFh
0x180003197  jz      short loc_18000319D
0x180003199  dec     eax
0x18000319b  mov     [rcx], eax
0x18000319d  mov     rax, [rbx]
0x1800031a0  mov     r8, rsi
0x1800031a3  mov     rdx, r14
0x1800031a6  mov     rcx, rbx
0x1800031a9  mov     rax, [rax]
0x1800031ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b1  mov     edi, eax
0x1800031b3  test    eax, eax
0x1800031b5  jz      short loc_1800031CB
0x1800031b7  mov     rdx, [rbx]
0x1800031ba  mov     rax, [rdx+28h]
0x1800031be  mov     edx, 1
0x1800031c3  mov     rcx, rbx
0x1800031c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cb  mov     eax, edi
0x1800031cd  add     rsp, 28h
0x1800031d1  pop     r14
0x1800031d3  pop     rdi
0x1800031d4  pop     rsi
0x1800031d5  pop     rbx
0x1800031d6  retn
```
