# HtmlDocForParsingSite::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x180009ca0`
- end: `0x180009d69`
- name: `?QueryService@HtmlDocForParsingSite@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `201`
- prototype: `__int64 __fastcall(HtmlDocForParsingSite *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001184`
- `0x180009ca0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall HtmlDocForParsingSite::QueryService(
        HtmlDocForParsingSite *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  MaxSecurityManager *v7; // rax
  MaxSecurityManager *v8; // rdi
  __int64 v9; // rcx

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( *(_OWORD *)a3 != *(_OWORD *)&GUID_f164edf1_cc7c_4f0d_9a94_34222625c393 )
    return 2147500034LL;
  if ( !*((_QWORD *)this + 5) )
  {
    v7 = (MaxSecurityManager *)operator new(0x10u);
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    *((_DWORD *)v7 + 2) = 1;
    *(_QWORD *)v7 = &MaxSecurityManager::`vftable';
    MaxSecurityManager::AddRef(v7);
    *((_QWORD *)this + 5) = v8;
    (*(void (__fastcall **)(MaxSecurityManager *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *a4 = (void *)*((_QWORD *)this + 5);
  v9 = *((_QWORD *)this + 5);
  if ( v9 )
    (*(void (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v9 + 8LL))(v9, a2);
  return 0;
}

```

## disassembly

```asm
0x180009ca0  mov     [rsp+arg_0], rbx
0x180009ca5  mov     [rsp+arg_8], rsi
0x180009caa  push    rdi
0x180009cab  sub     rsp, 20h
0x180009caf  mov     rsi, r9
0x180009cb2  mov     rbx, rcx
0x180009cb5  test    r9, r9
0x180009cb8  jnz     short loc_180009CC4
0x180009cba  mov     eax, 80070057h
0x180009cbf  jmp     loc_180009D59
0x180009cc4  mov     qword ptr [r9], 0
0x180009ccb  mov     rax, [r8]
0x180009cce  cmp     rax, qword ptr cs:_GUID_f164edf1_cc7c_4f0d_9a94_34222625c393.Data1
0x180009cd5  jnz     short loc_180009D54
0x180009cd7  mov     rax, [r8+8]
0x180009cdb  cmp     rax, qword ptr cs:_GUID_f164edf1_cc7c_4f0d_9a94_34222625c393.Data4
0x180009ce2  jnz     short loc_180009D54
0x180009ce4  cmp     qword ptr [rcx+28h], 0
0x180009ce9  jnz     short loc_180009D2D
0x180009ceb  mov     ecx, 10h; Size
0x180009cf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cf5  mov     rdi, rax
0x180009cf8  test    rax, rax
0x180009cfb  jz      short loc_180009D4D
0x180009cfd  lea     rax, ??_7MaxSecurityManager@@6B@; const MaxSecurityManager::`vftable'
0x180009d04  mov     dword ptr [rdi+8], 1
0x180009d0b  mov     [rdi], rax
0x180009d0e  mov     rcx, rdi
0x180009d11  mov     rax, [rax+8]
0x180009d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d1a  mov     [rbx+28h], rdi
0x180009d1e  mov     rcx, [rdi]
0x180009d21  mov     rax, [rcx+10h]
0x180009d25  mov     rcx, rdi
0x180009d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2d  mov     rax, [rbx+28h]
0x180009d31  mov     [rsi], rax
0x180009d34  mov     rcx, [rbx+28h]
0x180009d38  test    rcx, rcx
0x180009d3b  jz      short loc_180009D49
0x180009d3d  mov     rax, [rcx]
0x180009d40  mov     rax, [rax+8]
0x180009d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d49  xor     eax, eax
0x180009d4b  jmp     short loc_180009D59
0x180009d4d  mov     eax, 8007000Eh
0x180009d52  jmp     short loc_180009D59
0x180009d54  mov     eax, 80004002h
0x180009d59  mov     rbx, [rsp+28h+arg_0]
0x180009d5e  mov     rsi, [rsp+28h+arg_8]
0x180009d63  add     rsp, 20h
0x180009d67  pop     rdi
0x180009d68  retn
```
