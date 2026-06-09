# CCbsIdentity::~CCbsIdentity(void)

- ea: `0x140022ab0`
- end: `0x140022ad4`
- name: `??1CCbsIdentity@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CCbsIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400259a0`

## callees

- `0x140022a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140022ac0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140022ac0`

## pseudocode

```c
void __fastcall CCbsIdentity::~CCbsIdentity(CCbsIdentity *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 784));
  wil::com_ptr_t<IMalloc,wil::err_returncode_policy>::~com_ptr_t<IMalloc,wil::err_returncode_policy>((__int64 *)this + 2);
}

```

## disassembly

```asm
0x140022ab0  push    rbx
0x140022ab2  sub     rsp, 20h
0x140022ab6  mov     rbx, rcx
0x140022ab9  add     rcx, 310h; lpCriticalSection
0x140022ac0  call    cs:__imp_DeleteCriticalSection
0x140022ac6  lea     rcx, [rbx+10h]
0x140022aca  add     rsp, 20h
0x140022ace  pop     rbx
0x140022acf  jmp     ??1?$com_ptr_t@UIMalloc@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMalloc,wil::err_returncode_policy>::~com_ptr_t<IMalloc,wil::err_returncode_policy>(void)
```
