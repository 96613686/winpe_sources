# ATL::CComObject<CContextMenuHandler>::CreateInstance(ATL::CComObject<CContextMenuHandler> * *)

- ea: `0x180005c80`
- end: `0x180005d50`
- name: `?CreateInstance@?$CComObject@VCContextMenuHandler@@@ATL@@SAJPEAPEAV12@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CContextMenuHandler **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800048e0`

## callees

- `0x1800031e0`
- `0x180005a30`
- `0x180005c80`
- `0x180005d58`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::CreateInstance(CContextMenuHandler **a1)
{
  CContextMenuHandler **v1; // rsi
  unsigned int v3; // edi
  void *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  CContextMenuHandler *v8; // rbx
  _DWORD *v9; // r14
  int v10; // eax
  CContextMenuHandler *v12; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x48u);
    if ( v4 )
      v8 = (CContextMenuHandler *)ATL::CComObject<CContextMenuHandler>::CComObject<CContextMenuHandler>(
                                    (__int64)v4,
                                    v5,
                                    v6,
                                    v7);
    else
      v8 = 0;
    v12 = v8;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    v9 = (_DWORD *)((char *)v8 + 16);
    ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef((char *)v8 + 16);
    v10 = CContextMenuHandler::FinalConstruct(v8);
    v3 = 0;
    if ( v10 < 0 )
      v3 = v10;
    if ( *v9 != 0x7FFFFFFF )
      --*v9;
    if ( v3 )
    {
      (*(void (__fastcall **)(CContextMenuHandler *, __int64))(*(_QWORD *)v8 + 48LL))(v8, 1);
      v8 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *v1 = v8;
  return v3;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_18], rbx
0x180005c85  mov     [rsp+arg_0], rcx
0x180005c8a  push    rsi
0x180005c8b  push    rdi
0x180005c8c  push    r14
0x180005c8e  sub     rsp, 20h
0x180005c92  mov     rsi, rcx
0x180005c95  test    rcx, rcx
0x180005c98  jnz     short loc_180005CA4
0x180005c9a  mov     eax, 80004003h
0x180005c9f  jmp     loc_180005D42
0x180005ca4  mov     qword ptr [rcx], 0
0x180005cab  mov     edi, 8007000Eh
0x180005cb0  mov     [rsp+38h+arg_8], edi
0x180005cb4  mov     [rsp+38h+arg_10], 0
0x180005cbd  mov     ecx, 48h ; 'H'; Size
0x180005cc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cc7  test    rax, rax
0x180005cca  jz      short loc_180005CD9
0x180005ccc  mov     rcx, rax
0x180005ccf  call    ??0?$CComObject@VCContextMenuHandler@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CContextMenuHandler>::CComObject<CContextMenuHandler>(void *)
0x180005cd4  mov     rbx, rax
0x180005cd7  jmp     short loc_180005CDB
0x180005cd9  xor     ebx, ebx
0x180005cdb  mov     [rsp+38h+arg_10], rbx
0x180005ce0  jmp     short loc_180005CF0
0x180005ce2  mov     rsi, [rsp+38h+arg_0]
0x180005ce7  mov     edi, [rsp+38h+arg_8]
0x180005ceb  mov     rbx, [rsp+38h+arg_10]
0x180005cf0  test    rbx, rbx
0x180005cf3  jz      short loc_180005D3D
0x180005cf5  lea     r14, [rbx+10h]
0x180005cf9  mov     rcx, r14
0x180005cfc  call    ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
0x180005d01  mov     rcx, rbx; this
0x180005d04  call    ?FinalConstruct@CContextMenuHandler@@QEAAJXZ; CContextMenuHandler::FinalConstruct(void)
0x180005d09  xor     edi, edi
0x180005d0b  test    eax, eax
0x180005d0d  cmovs   edi, eax
0x180005d10  mov     eax, [r14]
0x180005d13  cmp     eax, 7FFFFFFFh
0x180005d18  jz      short loc_180005D1F
0x180005d1a  dec     eax
0x180005d1c  mov     [r14], eax
0x180005d1f  test    edi, edi
0x180005d21  jz      short loc_180005D3B
0x180005d23  mov     rax, [rbx]
0x180005d26  mov     edx, 1
0x180005d2b  mov     rcx, rbx
0x180005d2e  mov     rax, [rax+30h]
0x180005d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d37  xor     ebx, ebx
0x180005d39  jmp     short loc_180005D3D
0x180005d3b  xor     edi, edi
0x180005d3d  mov     [rsi], rbx
0x180005d40  mov     eax, edi
0x180005d42  mov     rbx, [rsp+38h+arg_18]
0x180005d47  add     rsp, 20h
0x180005d4b  pop     r14
0x180005d4d  pop     rdi
0x180005d4e  pop     rsi
0x180005d4f  retn
```
