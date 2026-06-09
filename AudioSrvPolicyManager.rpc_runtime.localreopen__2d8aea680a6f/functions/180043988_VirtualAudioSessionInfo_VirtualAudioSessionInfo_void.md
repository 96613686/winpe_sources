# VirtualAudioSessionInfo::~VirtualAudioSessionInfo(void)

- ea: `0x180043988`
- end: `0x1800439b9`
- name: `??1VirtualAudioSessionInfo@@UEAA@XZ`
- size: `49`
- prototype: `void __fastcall(VirtualAudioSessionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043aa0`

## callees

- `0x180001c74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043995`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043995`

## pseudocode

```c
void __fastcall VirtualAudioSessionInfo::~VirtualAudioSessionInfo(LPVOID *this)
{
  CoTaskMemFree(this[3]);
  this[3] = 0;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(this + 2);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180043988  push    rbx
0x18004398a  sub     rsp, 20h
0x18004398e  mov     rbx, rcx
0x180043991  mov     rcx, [rcx+18h]; pv
0x180043995  call    cs:__imp_CoTaskMemFree
0x18004399b  lea     rcx, [rbx+10h]
0x18004399f  mov     qword ptr [rbx+18h], 0
0x1800439a7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800439ac  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800439b3  add     rsp, 20h
0x1800439b7  pop     rbx
0x1800439b8  retn
```
