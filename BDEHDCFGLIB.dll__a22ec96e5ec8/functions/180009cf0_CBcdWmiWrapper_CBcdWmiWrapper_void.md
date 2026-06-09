# CBcdWmiWrapper::~CBcdWmiWrapper(void)

- ea: `0x180009cf0`
- end: `0x180009d5a`
- name: `??1CBcdWmiWrapper@@MEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CBcdWmiWrapper *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ec0`
- `0x180001f00`
- `0x180001f80`
- `0x180009f40`

## callees

- `0x180009cf0`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009d46`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d46`

## pseudocode

```c
void __fastcall CBcdWmiWrapper::~CBcdWmiWrapper(CBcdWmiWrapper *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  OLECHAR *v4; // rcx

  *(_QWORD *)this = &CBcdWmiWrapper::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180009cf0  push    rbx
0x180009cf2  sub     rsp, 20h
0x180009cf6  lea     rax, ??_7CBcdWmiWrapper@@6B@; const CBcdWmiWrapper::`vftable'
0x180009cfd  mov     rbx, rcx
0x180009d00  mov     [rcx], rax
0x180009d03  mov     rcx, [rcx+10h]
0x180009d07  test    rcx, rcx
0x180009d0a  jz      short loc_180009D20
0x180009d0c  mov     rax, [rcx]
0x180009d0f  mov     rax, [rax+10h]
0x180009d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d18  mov     qword ptr [rbx+10h], 0
0x180009d20  mov     rcx, [rbx+18h]
0x180009d24  test    rcx, rcx
0x180009d27  jz      short loc_180009D3D
0x180009d29  mov     rax, [rcx]
0x180009d2c  mov     rax, [rax+10h]
0x180009d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d35  mov     qword ptr [rbx+18h], 0
0x180009d3d  mov     rcx, [rbx+20h]; bstrString
0x180009d41  test    rcx, rcx
0x180009d44  jz      short loc_180009D54
0x180009d46  call    cs:__imp_SysFreeString
0x180009d4c  mov     qword ptr [rbx+20h], 0
0x180009d54  add     rsp, 20h
0x180009d58  pop     rbx
0x180009d59  retn
```
