# ipx::mtf::InputQueryFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x180007eb0`
- end: `0x180007f8d`
- name: `?_CreateIUnknownInstance@InputQueryFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `221`
- prototype: `__int64 __fastcall(ipx::mtf::InputQueryFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001fc4`
- `0x180007eb0`
- `0x180012990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180007f15`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180007f15`

## pseudocode

```c
__int64 __fastcall ipx::mtf::InputQueryFactory::_CreateIUnknownInstance(
        ipx::mtf::InputQueryFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  RTL_SRWLOCK *v5; // rax
  struct IUnknown *v6; // rbx

  if ( a2 )
    return 2147746064LL;
  v5 = (RTL_SRWLOCK *)operator new(0xC8u);
  v6 = (struct IUnknown *)v5;
  if ( v5 )
  {
    LODWORD(v5[3].Ptr) = 1;
    v5->Ptr = &ipx::mtf::CMtfPredictionInputQuery::`vftable';
    v5[1].Ptr = &ipx::mtf::CMtfPredictionInputQuery::`vftable'{for `IMtfSuggestionInputLatticeQuery'};
    v5[2].Ptr = &ipx::mtf::CMtfPredictionInputQuery::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSerializable,void,void,void,void>'};
    InitializeSRWLock(v5 + 16);
    v6[17].lpVtbl = 0;
    LODWORD(v6[18].lpVtbl) = 0;
    v6[19].lpVtbl = 0;
    v6[20].lpVtbl = 0;
    v6[21].lpVtbl = 0;
    v6[22].lpVtbl = 0;
    v6[23].lpVtbl = 0;
    _InterlockedIncrement(&g_cRefDll);
    ipx::mtf::CMtfPredictionInputQuery::InitializeProperty((ipx::mtf::CMtfPredictionInputQuery *)v6, -1);
  }
  else
  {
    v6 = 0;
  }
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x180007eb0  mov     [rsp+arg_0], rbx
0x180007eb5  push    rdi
0x180007eb6  sub     rsp, 20h
0x180007eba  mov     rdi, r8
0x180007ebd  test    rdx, rdx
0x180007ec0  jz      short loc_180007ECC
0x180007ec2  mov     eax, 80040110h
0x180007ec7  jmp     loc_180007F82
0x180007ecc  mov     ecx, 0C8h; Size
0x180007ed1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ed6  mov     [rsp+28h+arg_8], rax
0x180007edb  mov     rbx, rax
0x180007ede  test    rax, rax
0x180007ee1  jz      loc_180007F7B
0x180007ee7  mov     dword ptr [rax+18h], 1
0x180007eee  lea     rcx, [rbx+80h]; SRWLock
0x180007ef5  lea     rax, ??_7CMtfPredictionInputQuery@mtf@ipx@@6B@; const ipx::mtf::CMtfPredictionInputQuery::`vftable'
0x180007efc  mov     [rbx], rax
0x180007eff  lea     rax, ??_7CMtfPredictionInputQuery@mtf@ipx@@6BIMtfSuggestionInputLatticeQuery@@@; const ipx::mtf::CMtfPredictionInputQuery::`vftable'{for `IMtfSuggestionInputLatticeQuery'}
0x180007f06  mov     [rbx+8], rax
0x180007f0a  lea     rax, ??_7CMtfPredictionInputQuery@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfSerializable@@XXXX@@@; const ipx::mtf::CMtfPredictionInputQuery::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSerializable,void,void,void,void>'}
0x180007f11  mov     [rbx+10h], rax
0x180007f15  call    cs:__imp_InitializeSRWLock
0x180007f1b  mov     qword ptr [rbx+88h], 0
0x180007f26  mov     dword ptr [rbx+90h], 0
0x180007f30  mov     qword ptr [rbx+98h], 0
0x180007f3b  mov     qword ptr [rbx+0A0h], 0
0x180007f46  mov     qword ptr [rbx+0A8h], 0
0x180007f51  mov     qword ptr [rbx+0B0h], 0
0x180007f5c  mov     qword ptr [rbx+0B8h], 0
0x180007f67  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180007f6e  or      edx, 0FFFFFFFFh; unsigned int
0x180007f71  mov     rcx, rbx; this
0x180007f74  call    ?InitializeProperty@CMtfPredictionInputQuery@mtf@ipx@@UEAAJK@Z; ipx::mtf::CMtfPredictionInputQuery::InitializeProperty(ulong)
0x180007f79  jmp     short loc_180007F7D
0x180007f7b  xor     ebx, ebx
0x180007f7d  mov     [rdi], rbx
0x180007f80  xor     eax, eax
0x180007f82  mov     rbx, [rsp+28h+arg_0]
0x180007f87  add     rsp, 20h
0x180007f8b  pop     rdi
0x180007f8c  retn
```
