# NLInternal::CAudioPolicyWrapper::~CAudioPolicyWrapper(void)

- ea: `0x14001c224`
- end: `0x14001c249`
- name: `??1CAudioPolicyWrapper@NLInternal@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(NLInternal::CAudioPolicyWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019d74`

## callees

- `0x14000c32c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c236`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c236`

## pseudocode

```c
void __fastcall NLInternal::CAudioPolicyWrapper::~CAudioPolicyWrapper(NLInternal::CAudioPolicyWrapper *this)
{
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this);
}

```

## disassembly

```asm
0x14001c224  push    rbx
0x14001c226  sub     rsp, 20h
0x14001c22a  mov     rbx, rcx
0x14001c22d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001c232  lea     rcx, [rbx+8]; lpCriticalSection
0x14001c236  call    cs:__imp_DeleteCriticalSection
0x14001c23c  mov     rcx, rbx
0x14001c23f  add     rsp, 20h
0x14001c243  pop     rbx
0x14001c244  jmp     ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
```
