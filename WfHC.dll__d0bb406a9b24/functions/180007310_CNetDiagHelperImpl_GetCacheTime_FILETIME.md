# CNetDiagHelperImpl::GetCacheTime(_FILETIME *)

- ea: `0x180007310`
- end: `0x180007351`
- name: `?GetCacheTime@CNetDiagHelperImpl@@UEAAJPEAU_FILETIME@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007310`
- `0x18000c168`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetCacheTime(CNetDiagHelperImpl *this, struct _FILETIME *a2)
{
  struct _FILETIME *v2; // rbx
  __int64 result; // rax

  v2 = a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 8;
  do
  {
    LOBYTE(v2->dwLowDateTime) = 0;
    v2 = (struct _FILETIME *)((char *)v2 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x180007310  mov     [rsp+arg_0], rbx
0x180007315  push    rdi
0x180007316  sub     rsp, 20h
0x18000731a  mov     rbx, rdx
0x18000731d  mov     rdi, rcx
0x180007320  test    rdx, rdx
0x180007323  jnz     short loc_18000732A
0x180007325  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000732a  cmp     dword ptr [rdi+10h], 1
0x18000732e  jz      short loc_180007335
0x180007330  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007335  mov     eax, 8
0x18000733a  mov     byte ptr [rbx], 0
0x18000733d  inc     rbx
0x180007340  sub     rax, 1
0x180007344  jnz     short loc_18000733A
0x180007346  mov     rbx, [rsp+28h+arg_0]
0x18000734b  add     rsp, 20h
0x18000734f  pop     rdi
0x180007350  retn
```
