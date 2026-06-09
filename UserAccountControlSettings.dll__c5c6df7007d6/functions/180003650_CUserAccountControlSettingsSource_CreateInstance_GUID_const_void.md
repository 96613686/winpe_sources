# CUserAccountControlSettingsSource_CreateInstance(_GUID const &,void * *)

- ea: `0x180003650`
- end: `0x1800036c9`
- name: `?CUserAccountControlSettingsSource_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001a04`
- `0x180003628`
- `0x180003650`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CUserAccountControlSettingsSource_CreateInstance(const struct _GUID *a1, void **a2)
{
  CUserAccountControlSettingsSource *v4; // rax
  CUserAccountControlSettingsSource *v5; // rax
  CUserAccountControlSettingsSource *v6; // rbx
  unsigned int v7; // edi

  *a2 = 0;
  v4 = (CUserAccountControlSettingsSource *)operator new(0x10u);
  if ( v4 && (v5 = CUserAccountControlSettingsSource::CUserAccountControlSettingsSource(v4), (v6 = v5) != 0) )
  {
    v7 = (**(__int64 (__fastcall ***)(CUserAccountControlSettingsSource *, const struct _GUID *, void **))v5)(
           v5,
           a1,
           a2);
    (*(void (__fastcall **)(CUserAccountControlSettingsSource *))(*(_QWORD *)v6 + 16LL))(v6);
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
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  mov     [rsp+arg_8], rsi
0x18000365a  push    rdi
0x18000365b  sub     rsp, 20h
0x18000365f  mov     rsi, rcx
0x180003662  mov     qword ptr [rdx], 0
0x180003669  mov     ecx, 10h; Size
0x18000366e  mov     rdi, rdx
0x180003671  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003676  test    rax, rax
0x180003679  jz      short loc_1800036B2
0x18000367b  mov     rcx, rax; this
0x18000367e  call    ??0CUserAccountControlSettingsSource@@QEAA@XZ; CUserAccountControlSettingsSource::CUserAccountControlSettingsSource(void)
0x180003683  mov     rbx, rax
0x180003686  test    rax, rax
0x180003689  jz      short loc_1800036B2
0x18000368b  mov     rcx, [rax]
0x18000368e  mov     r8, rdi
0x180003691  mov     rdx, rsi
0x180003694  mov     rax, [rcx]
0x180003697  mov     rcx, rbx
0x18000369a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369f  mov     rcx, [rbx]
0x1800036a2  mov     edi, eax
0x1800036a4  mov     rax, [rcx+10h]
0x1800036a8  mov     rcx, rbx
0x1800036ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b0  jmp     short loc_1800036B7
0x1800036b2  mov     edi, 8007000Eh
0x1800036b7  mov     rbx, [rsp+28h+arg_0]
0x1800036bc  mov     eax, edi
0x1800036be  mov     rsi, [rsp+28h+arg_8]
0x1800036c3  add     rsp, 20h
0x1800036c7  pop     rdi
0x1800036c8  retn
```
