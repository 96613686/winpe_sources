# Windows::Services::Cortana::CortanaSettings::~CortanaSettings(void)

- ea: `0x180010638`
- end: `0x180010677`
- name: `??1CortanaSettings@Cortana@Services@Windows@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(Windows::Services::Cortana::CortanaSettings *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800109e0`

## callees

- `0x18000aeec`
- `0x180010638`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010645`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010645`

## pseudocode

```c
void __fastcall Windows::Services::Cortana::CortanaSettings::~CortanaSettings(
        Windows::Services::Cortana::CortanaSettings *this)
{
  __int64 v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180010638  push    rbx
0x18001063a  sub     rsp, 20h
0x18001063e  mov     rbx, rcx
0x180010641  add     rcx, 48h ; 'H'; lpCriticalSection
0x180010645  call    cs:__imp_DeleteCriticalSection
0x18001064b  nop
0x18001064c  mov     rcx, [rbx+40h]
0x180010650  test    rcx, rcx
0x180010653  jz      short loc_18001066A
0x180010655  mov     qword ptr [rbx+40h], 0
0x18001065d  mov     rax, [rcx]
0x180010660  mov     rax, [rax+10h]
0x180010664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010669  nop
0x18001066a  mov     rcx, rbx
0x18001066d  add     rsp, 20h
0x180010671  pop     rbx
0x180010672  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIProcessLauncherOptions@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>(void)
```
