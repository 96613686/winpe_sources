# ipx::mtf::ContextPropertyFactory::_CreateIUnknownInstance(IUnknown *,IUnknown * *)

- ea: `0x180007df0`
- end: `0x180007eaa`
- name: `?_CreateIUnknownInstance@ContextPropertyFactory@mtf@ipx@@UEAAJPEAUIUnknown@@PEAPEAU4@@Z`
- size: `186`
- prototype: `__int64 __fastcall(ipx::mtf::ContextPropertyFactory *__hidden this, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001fc4`
- `0x180007df0`
- `0x180010688`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall ipx::mtf::ContextPropertyFactory::_CreateIUnknownInstance(
        ipx::mtf::ContextPropertyFactory *this,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  struct IUnknown *v5; // rax
  struct IUnknown *v6; // rbx

  if ( a2 )
    return 2147746064LL;
  v5 = (struct IUnknown *)operator new(0x98u);
  v6 = v5;
  if ( v5 )
  {
    LODWORD(v5[2].lpVtbl) = 0;
    v5->lpVtbl = (struct IUnknownVtbl *)&ipx::mtf::CMtfContextProp::`vftable'{for `IMtfSuggestionContextProperty'};
    v5[1].lpVtbl = (struct IUnknownVtbl *)&ipx::mtf::CMtfContextProp::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSerializable,void,void,void,void>'};
    v5[13].lpVtbl = 0;
    v5[14].lpVtbl = 0;
    v5[15].lpVtbl = 0;
    v5[16].lpVtbl = 0;
    v5[17].lpVtbl = 0;
    v5[18].lpVtbl = 0;
    ipx::mtf::CMtfContextProp::Clear((ipx::mtf::CMtfContextProp *)v5);
    _InterlockedIncrement(&g_cRefDll);
  }
  else
  {
    v6 = 0;
  }
  *a3 = v6;
  ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->AddRef)(v6);
  return 0;
}

```

## disassembly

```asm
0x180007df0  mov     [rsp+arg_0], rbx
0x180007df5  push    rdi
0x180007df6  sub     rsp, 20h
0x180007dfa  mov     rdi, r8
0x180007dfd  test    rdx, rdx
0x180007e00  jz      short loc_180007E0C
0x180007e02  mov     eax, 80040110h
0x180007e07  jmp     loc_180007E9F
0x180007e0c  mov     ecx, 98h; Size
0x180007e11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007e16  mov     [rsp+28h+arg_8], rax
0x180007e1b  mov     rbx, rax
0x180007e1e  test    rax, rax
0x180007e21  jz      short loc_180007E89
0x180007e23  mov     dword ptr [rax+10h], 0
0x180007e2a  mov     rcx, rbx; this
0x180007e2d  lea     rax, ??_7CMtfContextProp@mtf@ipx@@6BIMtfSuggestionContextProperty@@@; const ipx::mtf::CMtfContextProp::`vftable'{for `IMtfSuggestionContextProperty'}
0x180007e34  mov     [rbx], rax
0x180007e37  lea     rax, ??_7CMtfContextProp@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfSerializable@@XXXX@@@; const ipx::mtf::CMtfContextProp::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSerializable,void,void,void,void>'}
0x180007e3e  mov     [rbx+8], rax
0x180007e42  mov     qword ptr [rbx+68h], 0
0x180007e4a  mov     qword ptr [rbx+70h], 0
0x180007e52  mov     qword ptr [rbx+78h], 0
0x180007e5a  mov     qword ptr [rbx+80h], 0
0x180007e65  mov     qword ptr [rbx+88h], 0
0x180007e70  mov     qword ptr [rbx+90h], 0
0x180007e7b  call    ?Clear@CMtfContextProp@mtf@ipx@@IEAAXXZ; ipx::mtf::CMtfContextProp::Clear(void)
0x180007e80  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x180007e87  jmp     short loc_180007E8B
0x180007e89  xor     ebx, ebx
0x180007e8b  mov     [rdi], rbx
0x180007e8e  mov     rcx, rbx
0x180007e91  mov     rax, [rbx]
0x180007e94  mov     rax, [rax+8]
0x180007e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e9d  xor     eax, eax
0x180007e9f  mov     rbx, [rsp+28h+arg_0]
0x180007ea4  add     rsp, 20h
0x180007ea8  pop     rdi
0x180007ea9  retn
```
