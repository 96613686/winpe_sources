# ATL::CComCreator<ATL::CComObject<CEnhancedStorageFolder>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001c80`
- end: `0x180001ddd`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageFolder@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001c50`

## callees

- `0x180001c80`
- `0x180001de4`
- `0x18000684c`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CEnhancedStorageFolder>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // edi
  _DWORD *v6; // rax
  __int64 v7; // r9
  _DWORD *v8; // rbx
  int v9; // eax
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x30u);
  v8 = v6;
  if ( v6 )
  {
    v6[8] = 0;
    CItemIDFactory<_ITEMID,1450709556>::CItemIDFactory<_ITEMID,1450709556>(v6);
    *(_QWORD *)v8 = &ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `CItemIDFactory<_ITEMID,1450709556>'};
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IPersistFolder2'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IShellFolder2'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = v8[8];
    if ( v9 != 0x7FFFFFFF )
      v8[8] = v9 + 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v7);
    *((_QWORD *)v8 + 5) = 0;
    v10 = v8[8];
    if ( v10 != 0x7FFFFFFF )
      v8[8] = v10 - 1;
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180001c80  mov     [rsp+arg_10], r8
0x180001c85  mov     [rsp+arg_8], rdx
0x180001c8a  mov     [rsp+arg_0], rcx
0x180001c8f  push    rbx
0x180001c90  push    rsi
0x180001c91  push    rdi
0x180001c92  push    r14
0x180001c94  push    r15
0x180001c96  sub     rsp, 20h
0x180001c9a  mov     r14, r8
0x180001c9d  mov     r15, rdx
0x180001ca0  test    r8, r8
0x180001ca3  jz      loc_180001D82
0x180001ca9  xor     esi, esi
0x180001cab  mov     [r8], rsi
0x180001cae  mov     edi, 8007000Eh
0x180001cb3  mov     dword ptr [rsp+48h+arg_0], edi
0x180001cb7  mov     [rsp+48h+arg_18], rsi
0x180001cbc  mov     ecx, 30h ; '0'; Size
0x180001cc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001cc6  mov     rbx, rax
0x180001cc9  test    rax, rax
0x180001ccc  jz      loc_180001D7D
0x180001cd2  mov     [rax+20h], esi
0x180001cd5  mov     rcx, rax
0x180001cd8  call    ??0?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@IEAA@XZ; CItemIDFactory<_ITEMID,1450709556>::CItemIDFactory<_ITEMID,1450709556>(void)
0x180001cdd  lea     rcx, ??_7?$CComObject@VCEnhancedStorageFolder@@@ATL@@6B?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@@; const ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `CItemIDFactory<_ITEMID,1450709556>'}
0x180001ce4  mov     [rbx], rcx
0x180001ce7  lea     rax, ??_7?$CComObject@VCEnhancedStorageFolder@@@ATL@@6BIPersistFolder2@@@; const ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IPersistFolder2'}
0x180001cee  mov     [rbx+10h], rax
0x180001cf2  lea     rax, ??_7?$CComObject@VCEnhancedStorageFolder@@@ATL@@6BIShellFolder2@@@; const ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IShellFolder2'}
0x180001cf9  mov     [rbx+18h], rax
0x180001cfd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001d04  mov     rax, [rcx]
0x180001d07  mov     rax, [rax+8]
0x180001d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d10  mov     [rsp+48h+arg_18], rbx
0x180001d15  test    rbx, rbx
0x180001d18  jz      short loc_180001D6F
0x180001d1a  mov     eax, [rbx+20h]
0x180001d1d  cmp     eax, 7FFFFFFFh
0x180001d22  jz      short loc_180001D29
0x180001d24  inc     eax
0x180001d26  mov     [rbx+20h], eax
0x180001d29  lea     rax, WPP_GLOBAL_Control
0x180001d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d37  cmp     rcx, rax
0x180001d3a  jz      short loc_180001D42
0x180001d3c  test    byte ptr [rcx+1Ch], 20h
0x180001d40  jnz     short loc_180001DAD
0x180001d42  mov     [rbx+28h], rsi
0x180001d46  mov     eax, [rbx+20h]
0x180001d49  cmp     eax, 7FFFFFFFh
0x180001d4e  jz      short loc_180001D55
0x180001d50  dec     eax
0x180001d52  mov     [rbx+20h], eax
0x180001d55  mov     rax, [rbx]
0x180001d58  mov     r8, r14
0x180001d5b  mov     rdx, r15
0x180001d5e  mov     rcx, rbx
0x180001d61  mov     rax, [rax]
0x180001d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d69  mov     edi, eax
0x180001d6b  test    eax, eax
0x180001d6d  jnz     short loc_180001DC7
0x180001d6f  mov     eax, edi
0x180001d71  add     rsp, 20h
0x180001d75  pop     r15
0x180001d77  pop     r14
0x180001d79  pop     rdi
0x180001d7a  pop     rsi
0x180001d7b  pop     rbx
0x180001d7c  retn
0x180001d7d  mov     rbx, rsi
0x180001d80  jmp     short loc_180001D10
0x180001d82  mov     eax, 80004003h
0x180001d87  add     rsp, 20h
0x180001d8b  pop     r15
0x180001d8d  pop     r14
0x180001d8f  pop     rdi
0x180001d90  pop     rsi
0x180001d91  pop     rbx
0x180001d92  retn
0x180001d93  xor     esi, esi
0x180001d95  mov     r14, [rsp+48h+arg_10]
0x180001d9a  mov     r15, [rsp+48h+arg_8]
0x180001d9f  mov     edi, dword ptr [rsp+48h+arg_0]
0x180001da3  mov     rbx, [rsp+48h+arg_18]
0x180001da8  jmp     loc_180001D15
0x180001dad  mov     edx, 1Eh
0x180001db2  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180001db9  mov     rcx, [rcx+10h]
0x180001dbd  call    WPP_SF_
0x180001dc2  jmp     loc_180001D42
0x180001dc7  mov     rcx, [rbx]
0x180001dca  mov     rax, [rcx+20h]
0x180001dce  mov     edx, 1
0x180001dd3  mov     rcx, rbx
0x180001dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ddb  jmp     short loc_180001D6F
```
