# CD3DShaderCacheInstaller::UnregisterDriverUpdateListener(void)

- ea: `0x18012c640`
- end: `0x18012c680`
- name: `?UnregisterDriverUpdateListener@CD3DShaderCacheInstaller@@UEAAJXZ`
- size: `64`
- prototype: `__int64 __fastcall(CD3DShaderCacheInstaller *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18012c640`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18012c65c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18012c65c`

## pseudocode

```c
__int64 __fastcall CD3DShaderCacheInstaller::UnregisterDriverUpdateListener(CD3DShaderCacheInstaller *this)
{
  if ( !*((_QWORD *)this + 17) )
    return 2147942487LL;
  if ( (int)RtlUnsubscribeWnfNotificationWaitForCompletion() < 0 )
    return 2147500037LL;
  *((_QWORD *)this + 17) = 0;
  return 0;
}

```

## disassembly

```asm
0x18012c640  push    rbx
0x18012c642  sub     rsp, 20h
0x18012c646  mov     rbx, rcx
0x18012c649  mov     rcx, [rcx+88h]
0x18012c650  test    rcx, rcx
0x18012c653  jnz     short loc_18012C65C
0x18012c655  mov     eax, 80070057h
0x18012c65a  jmp     short loc_18012C67A
0x18012c65c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18012c662  test    eax, eax
0x18012c664  js      short loc_18012C675
0x18012c666  mov     qword ptr [rbx+88h], 0
0x18012c671  xor     eax, eax
0x18012c673  jmp     short loc_18012C67A
0x18012c675  mov     eax, 80004005h
0x18012c67a  add     rsp, 20h
0x18012c67e  pop     rbx
0x18012c67f  retn
```
