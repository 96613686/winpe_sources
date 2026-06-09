# ATL::CComCreator<ATL::CComObject<CIconOverlayHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003fb8`
- end: `0x1800040bc`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIconOverlayHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003f90`

## callees

- `0x1800031e0`
- `0x180003fb8`
- `0x1800040c4`
- `0x18000684c`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIconOverlayHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rbx
  _DWORD *v12; // rdi
  __int64 v13; // r9

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x40u);
  if ( v7 )
    v11 = ATL::CComObject<CIconOverlayHandler>::CComObject<CIconOverlayHandler>((__int64)v7, v8, v9, v10);
  else
    v11 = 0;
  if ( v11 )
  {
    v12 = (_DWORD *)(v11 + 8);
    ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(v11 + 8);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids, v13);
    if ( *v12 != 0x7FFFFFFF )
      --*v12;
    v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v11)(v11, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 48LL))(v11, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003fb8  mov     [rsp+arg_10], r8
0x180003fbd  mov     [rsp+arg_8], rdx
0x180003fc2  mov     [rsp+arg_0], rcx
0x180003fc7  push    rbx
0x180003fc8  push    rsi
0x180003fc9  push    rdi
0x180003fca  push    r14
0x180003fcc  sub     rsp, 28h
0x180003fd0  mov     rsi, r8
0x180003fd3  mov     r14, rdx
0x180003fd6  test    r8, r8
0x180003fd9  jnz     short loc_180003FE5
0x180003fdb  mov     eax, 80004003h
0x180003fe0  jmp     loc_1800040B2
0x180003fe5  mov     qword ptr [r8], 0
0x180003fec  mov     edi, 8007000Eh
0x180003ff1  mov     dword ptr [rsp+48h+arg_0], edi
0x180003ff5  mov     [rsp+48h+arg_18], 0
0x180003ffe  mov     ecx, 40h ; '@'; Size
0x180004003  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004008  test    rax, rax
0x18000400b  jz      short loc_18000401A
0x18000400d  mov     rcx, rax
0x180004010  call    ??0?$CComObject@VCIconOverlayHandler@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CIconOverlayHandler>::CComObject<CIconOverlayHandler>(void *)
0x180004015  mov     rbx, rax
0x180004018  jmp     short loc_18000401C
0x18000401a  xor     ebx, ebx
0x18000401c  mov     [rsp+48h+arg_18], rbx
0x180004021  jmp     short loc_180004036
0x180004023  mov     rsi, [rsp+48h+arg_10]
0x180004028  mov     r14, [rsp+48h+arg_8]
0x18000402d  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004031  mov     rbx, [rsp+48h+arg_18]
0x180004036  test    rbx, rbx
0x180004039  jz      short loc_1800040B0
0x18000403b  lea     rdi, [rbx+8]
0x18000403f  mov     rcx, rdi
0x180004042  call    ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
0x180004047  lea     rax, WPP_GLOBAL_Control
0x18000404e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004055  cmp     rcx, rax
0x180004058  jz      short loc_180004075
0x18000405a  test    byte ptr [rcx+1Ch], 20h
0x18000405e  jz      short loc_180004075
0x180004060  mov     edx, 0Bh
0x180004065  lea     r8, WPP_c8fefde2d03f30a89c7cae0a6090c140_Traceguids
0x18000406c  mov     rcx, [rcx+10h]
0x180004070  call    WPP_SF_
0x180004075  mov     eax, [rdi]
0x180004077  cmp     eax, 7FFFFFFFh
0x18000407c  jz      short loc_180004082
0x18000407e  dec     eax
0x180004080  mov     [rdi], eax
0x180004082  mov     rax, [rbx]
0x180004085  mov     r8, rsi
0x180004088  mov     rdx, r14
0x18000408b  mov     rcx, rbx
0x18000408e  mov     rax, [rax]
0x180004091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004096  mov     edi, eax
0x180004098  test    eax, eax
0x18000409a  jz      short loc_1800040B0
0x18000409c  mov     rdx, [rbx]
0x18000409f  mov     rax, [rdx+30h]
0x1800040a3  mov     edx, 1
0x1800040a8  mov     rcx, rbx
0x1800040ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b0  mov     eax, edi
0x1800040b2  add     rsp, 28h
0x1800040b6  pop     r14
0x1800040b8  pop     rdi
0x1800040b9  pop     rsi
0x1800040ba  pop     rbx
0x1800040bb  retn
```
