# CW32System::WriteClassStg(IStorage *,_GUID const &)

- ea: `0x180090f20`
- end: `0x180090f85`
- name: `?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(struct IStorage *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005361c`

## callees

- `0x180041adc`
- `0x1800907ac`
- `0x180090f20`
- `0x180092010`

## string_xrefs

- `0x180090f47`: `WriteClassStg`

## pseudocode

```c
__int64 __fastcall CW32System::WriteClassStg(struct IStorage *a1, const struct _GUID *a2)
{
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v5)(struct IStorage *, const struct _GUID *); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v5 = (__int64 (__fastcall **)(struct IStorage *, const struct _GUID *))((char *)Ole32Procs + 224);
  if ( !*((_QWORD *)Ole32Procs + 28) )
    SetProcAddr((FARPROC *)Ole32Procs + 28, 1, "WriteClassStg");
  if ( *v5 )
    return (*v5)(a1, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180090f20  mov     [rsp+arg_0], rbx
0x180090f25  mov     [rsp+arg_8], rsi
0x180090f2a  push    rdi
0x180090f2b  sub     rsp, 20h
0x180090f2f  mov     rdi, rdx
0x180090f32  mov     rsi, rcx
0x180090f35  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180090f3a  lea     rbx, [rax+0E0h]
0x180090f41  cmp     qword ptr [rbx], 0
0x180090f45  jnz     short loc_180090F5B
0x180090f47  lea     r8, aWriteclassstg; "WriteClassStg"
0x180090f4e  mov     edx, 1
0x180090f53  mov     rcx, rbx
0x180090f56  call    SetProcAddr
0x180090f5b  mov     rax, [rbx]
0x180090f5e  test    rax, rax
0x180090f61  jz      short loc_180090F70
0x180090f63  mov     rdx, rdi
0x180090f66  mov     rcx, rsi
0x180090f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090f6e  jmp     short loc_180090F75
0x180090f70  mov     eax, 80004005h
0x180090f75  mov     rbx, [rsp+28h+arg_0]
0x180090f7a  mov     rsi, [rsp+28h+arg_8]
0x180090f7f  add     rsp, 20h
0x180090f83  pop     rdi
0x180090f84  retn
```
