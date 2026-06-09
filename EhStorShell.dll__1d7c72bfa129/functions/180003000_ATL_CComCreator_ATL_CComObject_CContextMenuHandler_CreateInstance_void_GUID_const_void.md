# ATL::CComCreator<ATL::CComObject<CContextMenuHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003000`
- end: `0x1800030fb`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCContextMenuHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `251`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002fd0`

## callees

- `0x180003000`
- `0x1800031e0`
- `0x180005a30`
- `0x180005d58`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CContextMenuHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  unsigned int v6; // r14d
  void *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  CContextMenuHandler *v11; // rsi
  int v12; // eax
  int v13; // eax
  CContextMenuHandler *v16; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x48u);
    if ( v7 )
      v11 = (CContextMenuHandler *)ATL::CComObject<CContextMenuHandler>::CComObject<CContextMenuHandler>(
                                     (__int64)v7,
                                     v8,
                                     v9,
                                     v10);
    else
      v11 = 0;
    v16 = v11;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v11 = v16;
  }
  if ( v11 )
  {
    ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef((char *)v11 + 16);
    v12 = CContextMenuHandler::FinalConstruct(v11);
    v6 = 0;
    if ( v12 < 0 )
      v6 = v12;
    v13 = *((_DWORD *)v11 + 4);
    if ( v13 != 0x7FFFFFFF )
      *((_DWORD *)v11 + 4) = v13 - 1;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CContextMenuHandler *, __int64, _QWORD *))v11)(v11, v4, v3)) != 0 )
      (*(void (__fastcall **)(CContextMenuHandler *, __int64))(*(_QWORD *)v11 + 48LL))(v11, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003000  mov     [rsp+arg_10], r8
0x180003005  mov     [rsp+arg_8], rdx
0x18000300a  mov     [rsp+arg_0], rcx
0x18000300f  push    rbx
0x180003010  push    rsi
0x180003011  push    rdi
0x180003012  push    r14
0x180003014  push    r15
0x180003016  sub     rsp, 20h
0x18000301a  mov     rbx, r8
0x18000301d  mov     rdi, rdx
0x180003020  test    r8, r8
0x180003023  jnz     short loc_180003036
0x180003025  mov     eax, 80004003h
0x18000302a  add     rsp, 20h
0x18000302e  pop     r15
0x180003030  pop     r14
0x180003032  pop     rdi
0x180003033  pop     rsi
0x180003034  pop     rbx
0x180003035  retn
0x180003036  mov     qword ptr [r8], 0
0x18000303d  mov     r14d, 8007000Eh
0x180003043  mov     dword ptr [rsp+48h+arg_0], r14d
0x180003048  mov     [rsp+48h+arg_18], 0
0x180003051  mov     ecx, 48h ; 'H'; Size
0x180003056  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000305b  test    rax, rax
0x18000305e  jz      short loc_18000306D
0x180003060  mov     rcx, rax
0x180003063  call    ??0?$CComObject@VCContextMenuHandler@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CContextMenuHandler>::CComObject<CContextMenuHandler>(void *)
0x180003068  mov     rsi, rax
0x18000306b  jmp     short loc_18000306F
0x18000306d  xor     esi, esi
0x18000306f  mov     [rsp+48h+arg_18], rsi
0x180003074  jmp     short loc_18000308A
0x180003076  mov     rbx, [rsp+48h+arg_10]
0x18000307b  mov     rdi, [rsp+48h+arg_8]
0x180003080  mov     r14d, dword ptr [rsp+48h+arg_0]
0x180003085  mov     rsi, [rsp+48h+arg_18]
0x18000308a  test    rsi, rsi
0x18000308d  jz      short loc_1800030EC
0x18000308f  lea     rcx, [rsi+10h]
0x180003093  call    ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
0x180003098  mov     rcx, rsi; this
0x18000309b  call    ?FinalConstruct@CContextMenuHandler@@QEAAJXZ; CContextMenuHandler::FinalConstruct(void)
0x1800030a0  xor     r14d, r14d
0x1800030a3  test    eax, eax
0x1800030a5  cmovs   r14d, eax
0x1800030a9  mov     eax, [rsi+10h]
0x1800030ac  cmp     eax, 7FFFFFFFh
0x1800030b1  jz      short loc_1800030B8
0x1800030b3  dec     eax
0x1800030b5  mov     [rsi+10h], eax
0x1800030b8  test    r14d, r14d
0x1800030bb  jnz     short loc_1800030D8
0x1800030bd  mov     rax, [rsi]
0x1800030c0  mov     r8, rbx
0x1800030c3  mov     rdx, rdi
0x1800030c6  mov     rcx, rsi
0x1800030c9  mov     rax, [rax]
0x1800030cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d1  mov     r14d, eax
0x1800030d4  test    eax, eax
0x1800030d6  jz      short loc_1800030EC
0x1800030d8  mov     rdx, [rsi]
0x1800030db  mov     rax, [rdx+30h]
0x1800030df  mov     edx, 1
0x1800030e4  mov     rcx, rsi
0x1800030e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ec  mov     eax, r14d
0x1800030ef  add     rsp, 20h
0x1800030f3  pop     r15
0x1800030f5  pop     r14
0x1800030f7  pop     rdi
0x1800030f8  pop     rsi
0x1800030f9  pop     rbx
0x1800030fa  retn
```
