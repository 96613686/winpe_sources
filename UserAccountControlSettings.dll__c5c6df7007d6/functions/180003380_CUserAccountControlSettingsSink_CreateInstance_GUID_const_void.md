# CUserAccountControlSettingsSink_CreateInstance(_GUID const &,void * *)

- ea: `0x180003380`
- end: `0x1800033f9`
- name: `?CUserAccountControlSettingsSink_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001a04`
- `0x18000335c`
- `0x180003380`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CUserAccountControlSettingsSink_CreateInstance(const struct _GUID *a1, void **a2)
{
  CUserAccountControlSettingsSink *v4; // rax
  CUserAccountControlSettingsSink *v5; // rax
  CUserAccountControlSettingsSink *v6; // rbx
  unsigned int v7; // edi

  *a2 = 0;
  v4 = (CUserAccountControlSettingsSink *)operator new(0x10u);
  if ( v4 && (v5 = CUserAccountControlSettingsSink::CUserAccountControlSettingsSink(v4), (v6 = v5) != 0) )
  {
    v7 = (**(__int64 (__fastcall ***)(CUserAccountControlSettingsSink *, const struct _GUID *, void **))v5)(v5, a1, a2);
    (*(void (__fastcall **)(CUserAccountControlSettingsSink *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180003380  mov     [rsp+arg_0], rbx
0x180003385  mov     [rsp+arg_8], rsi
0x18000338a  push    rdi
0x18000338b  sub     rsp, 20h
0x18000338f  mov     rsi, rcx
0x180003392  mov     qword ptr [rdx], 0
0x180003399  mov     ecx, 10h; Size
0x18000339e  mov     rdi, rdx
0x1800033a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800033a6  test    rax, rax
0x1800033a9  jz      short loc_1800033E2
0x1800033ab  mov     rcx, rax; this
0x1800033ae  call    ??0CUserAccountControlSettingsSink@@QEAA@XZ; CUserAccountControlSettingsSink::CUserAccountControlSettingsSink(void)
0x1800033b3  mov     rbx, rax
0x1800033b6  test    rax, rax
0x1800033b9  jz      short loc_1800033E2
0x1800033bb  mov     rcx, [rax]
0x1800033be  mov     r8, rdi
0x1800033c1  mov     rdx, rsi
0x1800033c4  mov     rax, [rcx]
0x1800033c7  mov     rcx, rbx
0x1800033ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033cf  mov     rcx, [rbx]
0x1800033d2  mov     edi, eax
0x1800033d4  mov     rax, [rcx+10h]
0x1800033d8  mov     rcx, rbx
0x1800033db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e0  jmp     short loc_1800033E7
0x1800033e2  mov     edi, 8007000Eh
0x1800033e7  mov     rbx, [rsp+28h+arg_0]
0x1800033ec  mov     eax, edi
0x1800033ee  mov     rsi, [rsp+28h+arg_8]
0x1800033f3  add     rsp, 20h
0x1800033f7  pop     rdi
0x1800033f8  retn
```
