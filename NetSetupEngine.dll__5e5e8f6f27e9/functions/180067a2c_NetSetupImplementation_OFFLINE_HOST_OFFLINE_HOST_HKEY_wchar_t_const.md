# NetSetupImplementation::OFFLINE_HOST::OFFLINE_HOST(HKEY__ *,wchar_t const *)

- ea: `0x180067a2c`
- end: `0x180067ac3`
- name: `??0OFFLINE_HOST@NetSetupImplementation@@QEAA@PEAUHKEY__@@PEB_W@Z`
- size: `151`
- prototype: `NetSetupImplementation::OFFLINE_HOST *__fastcall(NetSetupImplementation::OFFLINE_HOST *this, HKEY, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18003cbb4`

## callees

- `0x180005580`
- `0x180028720`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180067ab0`
- `RPCRT4!UuidCreate` at `0x180067ab0`

## pseudocode

```c
NetSetupImplementation::OFFLINE_HOST *__fastcall NetSetupImplementation::OFFLINE_HOST::OFFLINE_HOST(
        NetSetupImplementation::OFFLINE_HOST *this,
        HKEY a2,
        const wchar_t *a3)
{
  char *v5; // rbx

  *(_QWORD *)this = &NetSetupImplementation::OFFLINE_HOST::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  *((_BYTE *)this + 66) = 0;
  *((_DWORD *)this + 17) = -1;
  v5 = (char *)this + 88;
  RegistryKey::RegistryKey((NetSetupImplementation::OFFLINE_HOST *)((char *)this + 88), a2);
  std::wstring::wstring((char *)this + 96, a3);
  *((_QWORD *)this + 1) = v5;
  *((_QWORD *)this + 5) = this;
  *((_QWORD *)this + 4) = 0;
  *((_WORD *)this + 32) = 0;
  *((_BYTE *)this + 66) = 0;
  UuidCreate((UUID *)((char *)this + 72));
  return this;
}

```

## disassembly

```asm
0x180067a2c  mov     [rsp+arg_0], rcx
0x180067a31  push    rbx
0x180067a32  push    rbp
0x180067a33  push    rsi
0x180067a34  push    rdi
0x180067a35  sub     rsp, 38h
0x180067a39  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180067a42  mov     rdi, r8
0x180067a45  mov     rsi, rcx
0x180067a48  lea     rax, ??_7OFFLINE_HOST@NetSetupImplementation@@6B@; const NetSetupImplementation::OFFLINE_HOST::`vftable'
0x180067a4f  mov     [rcx], rax
0x180067a52  xor     ebp, ebp
0x180067a54  mov     [rcx+8], rbp
0x180067a58  mov     [rcx+10h], rbp
0x180067a5c  mov     [rcx+18h], rbp
0x180067a60  mov     [rcx+20h], rbp
0x180067a64  mov     [rcx+28h], rbp
0x180067a68  mov     [rcx+30h], rbp
0x180067a6c  mov     [rcx+38h], rbp
0x180067a70  mov     [rcx+40h], bp
0x180067a74  mov     [rcx+42h], bpl
0x180067a78  mov     dword ptr [rcx+44h], 0FFFFFFFFh
0x180067a7f  lea     rbx, [rcx+58h]
0x180067a83  mov     rcx, rbx; this
0x180067a86  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180067a8b  nop
0x180067a8c  lea     rcx, [rsi+60h]
0x180067a90  mov     rdx, rdi
0x180067a93  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180067a98  mov     [rsi+8], rbx
0x180067a9c  mov     [rsi+28h], rsi
0x180067aa0  mov     [rsi+20h], rbp
0x180067aa4  mov     [rsi+40h], bp
0x180067aa8  mov     [rsi+42h], bpl
0x180067aac  lea     rcx, [rsi+48h]; Uuid
0x180067ab0  call    cs:__imp_UuidCreate
0x180067ab6  nop
0x180067ab7  mov     rax, rsi
0x180067aba  add     rsp, 38h
0x180067abe  pop     rdi
0x180067abf  pop     rsi
0x180067ac0  pop     rbp
0x180067ac1  pop     rbx
0x180067ac2  retn
```
