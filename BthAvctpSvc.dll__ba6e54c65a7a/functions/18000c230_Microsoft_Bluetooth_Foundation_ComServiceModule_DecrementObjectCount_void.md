# Microsoft::Bluetooth::Foundation::ComServiceModule::DecrementObjectCount(void)

- ea: `0x18000c230`
- end: `0x18000c27b`
- name: `?DecrementObjectCount@ComServiceModule@Foundation@Bluetooth@Microsoft@@UEAAKXZ`
- size: `75`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Foundation::ComServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027ec0`

## callees

- `0x18000c1e4`
- `0x18000c230`
- `0x18005f010`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x18000c246`
- `combase!__imp_CoReleaseSharedService` at `0x18000c246`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::ComServiceModule::DecrementObjectCount(
        Microsoft::Bluetooth::Foundation::ComServiceModule *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx

  if ( !*((_BYTE *)this + 20) )
    return Microsoft::WRL::Module<2,Microsoft::Bluetooth::Foundation::ComServiceModule>::DecrementObjectCount();
  v2 = CoReleaseSharedService(*((unsigned int *)this + 4));
  if ( !v2 )
  {
    v3 = *((_QWORD *)this + 1);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c230  mov     [rsp+arg_0], rbx
0x18000c235  push    rdi
0x18000c236  sub     rsp, 20h
0x18000c23a  cmp     byte ptr [rcx+14h], 0
0x18000c23e  mov     rbx, rcx
0x18000c241  jz      short loc_18000C26B
0x18000c243  mov     ecx, [rcx+10h]
0x18000c246  call    cs:__imp_CoReleaseSharedService
0x18000c24c  mov     edi, eax
0x18000c24e  test    eax, eax
0x18000c250  jnz     short loc_18000C267
0x18000c252  mov     rcx, [rbx+8]
0x18000c256  test    rcx, rcx
0x18000c259  jz      short loc_18000C267
0x18000c25b  mov     rdx, [rcx]
0x18000c25e  mov     rax, [rdx+8]
0x18000c262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c267  mov     eax, edi
0x18000c269  jmp     short loc_18000C270
0x18000c26b  call    ?DecrementObjectCount@?$Module@$01VComServiceModule@Foundation@Bluetooth@Microsoft@@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Module<2,Microsoft::Bluetooth::Foundation::ComServiceModule>::DecrementObjectCount(void)
0x18000c270  mov     rbx, [rsp+28h+arg_0]
0x18000c275  add     rsp, 20h
0x18000c279  pop     rdi
0x18000c27a  retn
```
