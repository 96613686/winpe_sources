# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180003820`
- end: `0x180003892`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `114`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800016f8`
- `0x180003820`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180003878`
- `msvcrt!free` at `0x180003878`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  char *v3; // rcx
  char *v4; // rdi

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 24) = 0;
    v3 = *(char **)(a1 + 40);
    if ( v3 )
    {
      v4 = v3 - 8;
      `eh vector destructor iterator'(v3, 0x10u, *((_QWORD *)v3 - 1), (void (*)(void *))ATL::CComBSTR::~CComBSTR);
      if ( v4 )
        free(v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180003820  test    rcx, rcx
0x180003823  jz      short locret_180003891
0x180003825  mov     [rsp+arg_0], rbx
0x18000382a  push    rdi
0x18000382b  sub     rsp, 20h
0x18000382f  mov     rbx, rcx
0x180003832  mov     rcx, [rcx+18h]
0x180003836  test    rcx, rcx
0x180003839  jz      short loc_180003847
0x18000383b  mov     rax, [rcx]
0x18000383e  mov     rax, [rax+10h]
0x180003842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003847  mov     qword ptr [rbx+18h], 0
0x18000384f  mov     rcx, [rbx+28h]; void *
0x180003853  test    rcx, rcx
0x180003856  jz      short loc_18000387F
0x180003858  lea     rdi, [rcx-8]
0x18000385c  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180003863  mov     r8, [rdi]; unsigned __int64
0x180003866  mov     edx, 10h; unsigned __int64
0x18000386b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180003870  test    rdi, rdi
0x180003873  jz      short loc_18000387F
0x180003875  mov     rcx, rdi; Block
0x180003878  call    cs:__imp_free
0x18000387e  nop
0x18000387f  mov     qword ptr [rbx+28h], 0
0x180003887  mov     rbx, [rsp+28h+arg_0]
0x18000388c  add     rsp, 20h
0x180003890  pop     rdi
0x180003891  retn
```
